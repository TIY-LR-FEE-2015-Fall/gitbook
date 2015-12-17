# Wednesday December 16

## Schedule

- HW Review/Stand Up (15mins)
- User Access (40mins)
- Break (15mins)
- Hooking Up Our Server (20mins)
- Creating an API Resource w/ API Kit (20mins)
- Break (5mins)
- Related Data (Rest of Class)

## Topics

- User Access
  * Authenticated Routes
  * Guest Routes
  * Test Setup
    - `authenticateSession`
    - `invalidateSession`
    - `currentSession`
  * Better test helpers (Because Less Work is Better)
    - `login`
    - `logout`
    - `getSession`
- Hooking Up Our Server
  * Environment Variables
  * Port Number Customization `-p 5200`
    - Makes server run at `http://localhost:5200`
  * Configuration

```js
if (process.env.MIRAGE === 'false') {
  ENV['ember-cli-mirage'] = {
    enabled: false,
  };
}
```

- Creating an API Resource w/ API Kit
  * Mongoose Models
  * Loading Models
  * Routes
    - `get('/')`
    - `post('/')`
    - `get('/:id')`
    - `put('/:id')`
    - `delete('/:id')`
- Related Data
  * Make a model for HistoryItems
    - Date
    - amount (could be plus or minus)
  * Mirage it up!
    - Related Data
    - Hard Code `id` (foreign keys)
    - Add new routes
  * Update API
    - Mongoose `Schema.Types.ObjectId`
    - `after` hook in API Kit

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

## Standup

- David
  * What's good: Maybe going home for Christmas
  * What's bad: Not enough time
  * What's learning: Testing is very interesting. Starting to see why to test.
- Brandi
  * What's good: All Christmas shopping is done
  * What's bad: Hung up on an error saying "cannot find input class"
  * What's learning: Testing is great when you understand it. Knowing that things are functioning without having to see it every time is 👍
- Jeremy
  * What's good: Getting some sleep and exercise
  * What's bad: Haven't been able to do HW cause of errors (but that's fixed now... Maybe?)
  * What's learning: Testing is making more sense, but not all the way
- Ryan
  * What's good: Talking to people to make things easier to test
  * What's bad: There's a lot of times where I'm writing code where the test isn't really driven by my tests (ideally )
  * What's learning: Better, easier APIs

## Screencasts
