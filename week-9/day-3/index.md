# Tuesday December 15

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

## Screencasts
