# Current Logged In User

- Create a `profile` model to represent the current user
  * `ember g model profile`
  * Add `roles: DS.attr(),` - We'll use this later
  * Add properties you care about
- Add Current User Service

```handlebars
import Ember from 'ember';
import DS from 'ember-data';

export default Ember.Service.extend({
  session: Ember.inject.service(),
  store: Ember.inject.service(),

  user: Ember.computed('session.isAuthenticated', function() {
    if (this.get('session.isAuthenticated')) {
      return DS.PromiseObject.create({
        promise: this.get('store').queryRecord('profile', {current: true}),
      });
    }
  }),
});
```

- Add `admin` Route
  * `ember g route admin`
- Make Admin Route Load Current User Before Routing:

```handlebars
import Ember from 'ember';
let { RSVP } = Ember;

export default Ember.Route.extend({
  sessionUser: Ember.inject.service('session-user'),

  beforeModel() {
    return new RSVP.Promise((resolve, reject) => {
      this.get('sessionUser.user').then((user) => {
        if (Ember.get(user, 'isAdmin')) {
          return resolve();
        }

        // Make the user go to the login screen
        this.transitionTo('login');
        return reject();
      });
    });
  },

  model() {
    // Sets model as the current logged in user
    return this.get('sessionUser.user');
  }
});
```
