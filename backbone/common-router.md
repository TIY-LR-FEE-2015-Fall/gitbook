# Common Router Patterns in Backbone.js

There are many differing opinions when it comes to how to use the Backbone Router.
However, in almost every other client-side framework, the URL is considered VITAL.
It should reflect the views that are on screen and the data that lies behind it.
So, using Backbone's Router as a centralized way to manage the data and views shown to the user is the best way to keep the app and URL in sync.

## The `initialize` function

While the router is used to switch between different views, there are usually some pieces of your application that will be around no matter what screen you are on (think menus, sidebars, etc).


These elements and the data under them can be set up using the `initialize` function.
Since the `initialize` function is run whenever you instantiate the router, these shared elements will be immediately set up.
So, assume you have a sidebar of contacts:

    var AppRouter = Backbone.Router.extend({
        initialize: function() {
            /**
             * Let's assume that ContactList extends Backbone.Collection
             * This represents all of the Contact models
             * @type {ContactList}
             */
            this.contacts = new ContactList();

            /**
             * Instantiate the sidebar and send in the contact list
             * SidebarView can be either an ItemView or a CollectionView
             * @type {Sidebar}
             */
            this.sidebar = new Sidebar({collection: this.contacts});

            /**
             * Renders the sidebar and then inserts
             * it into the DOM inside of an element
             * with an id of `sidebar`
             */
            $('#sidebar').html(this.sidebar.render().el);
        },
    });

## Setting Up Views Before Fetching Data

One common thing is to wait for a collection to sync, and use the `then` function from a sync or `get` operation to wait until the data comes back and THEN set up your views.
However, this means that you could have to wait until your collection is synced for any UI to show up.
It also means that you would have multiple times where you call `collection.fetch()` which would lead to more network requests than you actually need AND would lead to a lot of renders happening on screen.

Instead if your views are all set up to listen for `change` and `sync` events, then you can setup your views while your data is coming down from the server.
Let's say that you had an index view that showed a list of filtered results from the main collection above:

    var AppRouter = Backbone.Router.extend({
        initialize: function() {
            this.contacts = new ContactList();
            this.sidebar = new Sidebar({collection: this.contacts});
            $('#sidebar').html(this.sidebar.render().el);

            /**
             * Starts the master list of contacts
             * syncing with the server: shared across all
             * views
             */
            this.contacts.fetch();
        },

        routes: {
            '': 'index',
        },

        index: function() {
            /**
             * Creates a new IndexView with the existing contacts
             * collection
             * @type {IndexView}
             */
            this.mainView = new IndexView({collection: this.contacts});

            /**
             * Renders the mainView and then inserts
             * it into the DOM inside of an element
             * with an id of `content`
             */
            $('#content').html(this.mainView.render().el);
        }
    });

## Working with Dyanmic Segments and Single Models

Often times you will want to show a detail view for a single model and show this application state in your URL.
This is where dynamic segments in your route definitions come in.
To add a dynamic segment: start with a colon (`:`) and everything after that will just be polish to name that segment of the URL.
For instance if I wanted to see a post by it's id:

    routes: {
        'post/:id': 'showPost',
    },

This will match any route that looks like `post/1` or `post/j123jisjife` and run the `showPost` function from your current router, but it will not match a URL `post/`.
And the dynamic segment where the `:id` is in your route definition will be passed as an argument to your `showPost` function.

However, matching the right URL is only half of the battle.
Once you have the route, you need to actually do something about it.
From here you'll will need to look up an model by it's `id` from the existing collection and then render your view.
You might think you could do something like this:

<strong style="color:red">Caution: </strong> This will not work

    showPost: function(id) {
        /**
         * Grab a single contact from the
         * contacts collection by its id
         * @type {Backbone.Model}
         */
        var contact = this.contacts.get(id);

        /**
         * Creates a DetailView instance passing
         * in the single contact found by id
         * @type {DetailView}
         */
        this.detailView = new DetailView({model: contact});

        /**
         * Renders the detailView and then inserts
         * it into the DOM inside of an element
         * with an id of `content`
         */
        $('#content').html(this.detailView.render().el);
    }

While this will work for in an already running application, this will not work if the app is refreshed.
Because this code is immediately and happens before the collection is done fetching from the server.
So the `this.contacts.get(id)` returns null.

Instead you can leverage the same events that your views are listening to and use these to setup views and their data in your router.
To do this you will need to put the above code in a function that can be run BOTH immediately (in case the app is already booted) and when a collection `sync` event fires.

    var AppRouter = Backbone.Router.extend({
        initialize: function() {
            this.contacts = new ContactList();
            this.sidebar = new Sidebar({collection: this.contacts});
            $('#sidebar').html(this.sidebar.render().el);

            /**
             * Starts the master list of contacts
             * syncing with the server: shared across all
             * views
             */
            this.contacts.fetch();
        },

        routes: {
            '': 'index',
            'post/:id': 'showPost',
        },

        index: function() {
            this.mainView = new IndexView({collection: this.contacts});

            $('#content').html(this.mainView.render().el);
        },

        showPost: function(id) {
            /**
             * While the `listenTo` function keeps
             * the `this` variable the same
             * this is required for running 
             * this code immediately
             * @type {Backbone.Router}
             */
            var _this = this;

            /**
             * Move the above code to a function that can
             * be run and set as a callback
             */
            var attachDetail = function() {
                var contact = _this.contacts.get(id);
                _this.mainView = new DetailView({model: contact});

                $('#content').html(this.mainView.render().el);
            };

            /**
             * Runs the `attachDetail` function
             * immediately in case the collection
             * is already synced
             */
            attachDetail();

            /**
             * Runs the `attachDetail` function
             * whenever this.contacts fires
             * a sync event
             */
            this.listenTo(this.contacts, 'sync', attachDetail);
        }
    });

## Optional Route Segments

Similar to the way that you can use the router to match a dynamic id, you can make parts of the URL optional.
To do this, wrap the optional parts of the URL in parenthesis:

    routes: {
        'search/(:term)': 'search',
    }

This will mean that the `search` function will be run for the URLs `search`, `search/s`, `search/hey`.

This can be used to filter collections to search and look for things.
For instance, we can setup this search function to set things up for titles that match the search term in the url

    var AppRouter = Backbone.Router.extend({
        initialize: function() {
            this.contacts = new ContactList();
            this.sidebar = new Sidebar({collection: this.contacts});
            $('#sidebar').html(this.sidebar.render().el);

            /**
             * Starts the master list of contacts
             * syncing with the server: shared across all
             * views
             */
            this.contacts.fetch();
        },

        routes: {
            '': 'index',
            'post/:id': 'showPost',
            'search/(:term)',
        },

        index: function() {
            this.mainView = new IndexView({collection: this.contacts});

            $('#content').html(this.mainView.render().el);
        },

        showPost: function(id) {
            var _this = this;

            var attachDetail = function() {
                var contact = _this.contacts.get(id);
                _this.mainView = new DetailView({model: contact});

                $('#content').html(this.mainView.render().el);
            };

            attachDetail();
            this.listenTo(this.contacts, 'sync', attachDetail);
        },

        search: function(term) {
            var _this = this;

            var attachSearch = function() {
                /**
                 * Filters contacts from the collection of contacts
                 */
                var filteredContacts = _this.contacts.filter(function(model) {
                    return model.get('title').indexOf(term) > -1;
                });

                this.mainView = new IndexView({collection: filteredContacts});

                $('#content').html(this.mainView.render().el);
            }

            attachSearch();
            this.listenTo(this.contacts, 'sync', attachSearch);
        }
    });

Since the search and index are so similar, this can actually be modified to share the search function by just updating the filter to return true if there is no term.

    var AppRouter = Backbone.Router.extend({
        initialize: function() {
            this.contacts = new ContactList();
            this.sidebar = new Sidebar({collection: this.contacts});
            $('#sidebar').html(this.sidebar.render().el);

            /**
             * Starts the master list of contacts
             * syncing with the server: shared across all
             * views
             */
            this.contacts.fetch();
        },

        routes: {
            'post/:id': 'showPost',
            /**
             * Make all of the search and term optional
             * Matches an empty route or `search/:term`
             */
            '(search/:term)': 'search',
        },

        showPost: function(id) {
            var _this = this;

            var attachDetail = function() {
                var contact = _this.contacts.get(id);
                _this.mainView = new DetailView({model: contact});

                $('#content').html(this.mainView.render().el);
            };

            attachDetail();
            this.listenTo(this.contacts, 'sync', attachDetail);
        },

        search: function(term) {
            var _this = this;

            var attachSearch = function() {
                /**
                 * Filters contacts from the collection of contacts
                 */
                var filteredContacts = _this.contacts.filter(function(model) {
                    if (!term) {
                        return true;
                    }
                    
                    /**
                     * This is how the collection is filtered,
                     * this is the bit of code you will change
                     * in your project
                     *
                     * Here the model's `title` property is tested
                     * to see if the search term exists in the string
                     */
                    return model.get('title').indexOf(term) > -1;
                });

                this.mainView = new IndexView({collection: filteredContacts});

                $('#content').html(this.mainView.render().el);
            }

            attachSearch();
            this.listenTo(this.contacts, 'sync', attachSearch);
        }
    });
