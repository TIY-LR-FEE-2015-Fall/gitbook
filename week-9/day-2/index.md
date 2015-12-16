# Tuesday December 15

## Schedule

- HW Review/Stand Up (15mins)
- API Kit Intro (20 mins)
- User Password and Register (20 mins)
- Break (15 mins)
- Sessions - What Are They (20 mins)
- OAuth - What is It? (20 mins)
- Break (5 mins)
- OAuth with Ember and API Kit (Rest of class)

## Topics

- API Kit Intro
  * Install
    - `brew install mongodb` - Install MongoDB
    - `ln -sfv /usr/local/opt/mongodb/*.plist ~/Library/LaunchAgents` - Make Mongo Start at login
    - `launchctl load ~/Library/LaunchAgents/homebrew.mxcl.mongodb.plist` - Start Mongo Now
    - `npm install generator-api-kit -g` - Install
  * Explanation
    - What is Mongo?
    - What is API Kit?
- User Password and Registration
  * API Kit Intro
  * User Password Hashes
- Sessions - What Are They
  * Types of Sessions
    - Cookie
    - Token
    - Other
  * Security
    - Refreshing
- OAuth What is it
  * Standard way to do Authorization
  * Authorization - What does this current user have access to?
  * OAuth Flows or Grants
    - Password or Bearer Grant - Only for trusted applications
      * Send plain text username & password
      * Immediately send back a session token
    - Refresh Token Grant
      * Send a one time use refresh token with all session tokens
        - Like a one time password
  * What it doesn't do
    - How to save email and password
    - How to compare email or password
    - How to save session info
- Ember Simple Auth
  * Provides Session Management
  * Deals with OAuth Stuff for us
    - We send in username & password
    - It does the rest
  * Installing
    - `ember install ember-simple-auth`

## Ember Simple Auth Steps

* User Submits Form and Action is received by Route Handler
* Simple Auth Authenticator (oauth2) makes a POST request to `/token`
* Mirage or Server responds to HTTP request
* Simple Auth reads HTTP response
* Simple Auth stores session info
* Simple Auth Broadcasts `sessionAuthenticated` Action
* Application route recieves `sessionAuthenticated` action and redirects to configured `routeAfterAuthentication`

## Challenge

For this week we will be working on a weekly budgeting app.

* Users can...
  - **Register using Email and Password*
  - **Login using Email and Password (More on that tomorrow)*
  - Start budget for a week
  - Create a deposit
  - Create an expense
  - See if they are over budget for a week

## Data Modeling

### What Are We Storing

- Users
- Emails
- Passwords
- Expenses
- Budgets
- Deposits
- Dates/Timeframes
- Under/Over Budget

### Organize By Ownership

- User
  * email
  * password
  * Array of Budgets
    - Array of Expenses
    - Array of Deposits
    - Timeframe
      * Start Date
      * End Date
    - totalMoney
    - overUnder

## Screencasts

* [Part 1](https://vimeo.com/149045855)
* [Part 2](https://vimeo.com/149048373)
* [Part 3](https://vimeo.com/149076284)
