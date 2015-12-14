# Monday December 14

## Schedule

- HW Review/Stand Up (15mins)
- Data Modeling Relationships (20mins)
- Mirage Mocks (20mins)
- Break (15mins)
- TDD User can start Budget(40mins)
- Break (5mins)
- TDD User can add a deposit(40mins)

## Topics

- Data Modeling
  * Relationships
  * Ownership
  * Computed Properties vs Stored Values
  * API is not the same as the database
    - Hidden Fields
    - Encrypted Fields
    - Embedded Records
  * Foreign Keys
- Mirage Mocks
  * Raw Requests
  * Models
  * Factories
  * Serializers

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
