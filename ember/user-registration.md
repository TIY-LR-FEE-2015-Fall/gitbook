# User Registration with Ember Simple Auth

* Create a Server using API Kit
  * `npm install -g generator-api-kit`
  * `yo api-kit`
    - If you already have an API, pick "NO" for new project (this will update your current API Kit app)
  * Change directory into the new project
  * Open in Atom `atom .`
  * `nodemon bin/www` (Starts the server and reloads when changed)
* Add fields to the User model
  * Edit the Schema in `app/models/user.js` to hold any properties you would like
    - We'll assume the user has a `firstName` and `lastName`
* Add User Registration To Ember Project
  * `ember install ember-simple-auth-registration`
* Create Registration Route
  * `ember g route registration`
* Create Form for Registration

```
{{#simple-form onsubmit="registerUser" as |formValues|}}
  {{input value=formValues.email placeholder="Email"}}
  {{input type="password" value=formValues.password placeholder="Password"}}

  {{input value=formValues.firstName placeholder="First Name"}}
  {{input value=formValues.lastName placeholder="Last Name"}}

  <button>Submit</button>
{{/simple-form}}
```

* Create `app/authenticators/register.js`:

```hbs
import Registration from 'ember-simple-auth-registration/authenticators/oauth2-password-registration';
import config from '../config/environment';

export default Registration.extend({
  registrationEndpoint: `${config.apiHost}/api/register`,
});
```

* Create Action Handler for `registerUser`

```hbs
export default Ember.Route.extend({
  session: Ember.inject.service(),
  actions: {
    registerUser(formValues) {
      let {email, password} = formValues;
      let userData = Ember.getProperties(formValues, ['firstName', 'lastName']);

      this.get('session').authenticate('authenticator:register', email, password, userData).catch((reason) => {});
    },
  },
});
```
