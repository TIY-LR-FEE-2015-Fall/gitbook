# Thursday December 17

## Schedule

- HW Review/Stand Up (15mins)
- Better (Easier) APIS with API Kit 2.0! (30mins)
- Relational Data (All the time!!!)

## Topics



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
    - name

### Budget

- name (String)
- startDate (Date)
- startingAmount (Number)
- transactions (HasMany:Transaction)
- endDate (compute)
- remaining (compute)
- over/under (compute:boolen)

### Transaction

- notes (String)
- amount (Number)
- createdAt (Date)
- budget (BelongsTo:Budget)

## Standup

- David
  * What's good: 4 Hours of Sleep is > 3
  * What's bad: Laundry does not just eat socks...
  * What's learning: Cool to see some progress blocking user access and such
- Brandi
  * What's good: Able to replace hardcoded template with {{#each}} loop and handlebars w/ model data
  * What's bad: Header is still hardcoded. What is the logic to get input to calculate servings
  * What's learning: Testing will make us a [superstar](http://i.imgur.com/29KhR.gif)
- Jeremy
  * What's good: Sleep groove
  * What's bad: Homework is still not quite sorted out (mirage folders...?)
  * What's learning: Want to feel a bit more comfortable about testing
- Ryan
  * What's good: API Kit 2.0 is done... ish
  * What's bad: API Kit 3.0 is gonna be tough
  * What's learning: Reduce functions are pretty awesome

## Screencasts

- [Part 1](https://vimeo.com/149326018)
- [Part 2](https://vimeo.com/149326017)
- [Part 3](https://vimeo.com/149326019)
