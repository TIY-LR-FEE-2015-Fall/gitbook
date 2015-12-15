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

## Challenge

For this week we will be working on a weekly budgeting app.

* Users can...
  - **Register using Email and Password*
  - **Login using Email and Password (More on that tomorrow)*
  - Start budget for a week
  - Create a deposit
  - Create an expense
  - See if they are over budget for a week

## Standups

* Jeremy
  - Learned: Backbone Routing
  - Need to work on: Ember Startup
  - Going well: things are starting to click
* David
  - Going well: BB project is functioning, Ember is starting to click, just needs repetition
  - Need to work on: Scheduling & Syntax Exercises
  - Learned: CSS and HTML are coming together
* Brandi
  - Going Well: Laying things out is easier
  - Needs work: Writing functions, knowing where to begin, remembering structure for Ember and BB
  - Learned: Recognizing Ember vs Backbone similarities and differences

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

* [Part 1](https://vimeo.com/148915814)
