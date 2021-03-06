# Monday December 28

## House Keeping

- Schedule Calendly Meeting For Tomorrow Lab
- Make sure assignments are pushed
  * I'll be grading from Recipe Card back

## Schedule

- HW Review/Stand Up (15mins)
- Introduce Final Homework (20mins)
- Introduce Page Objects (20mins)
- Break (15mins)
- Write a Page Object and Tests for store index page (40mins)
- Break (5mins)
- Data Modeling for eCommerce (40mins)

### Lab Schedule

- Next acceptance test to pass for Razer Cars
- Work on HW

## Topics

- Page Objects
  * Why use Page Objects?
  * `ember install ember-cli-page-object`
  * `ember g page-object`
  * Describing Pages
    * `visitable`
    * `text`
    * `clickable`
    * `fillable`
    * `count`<sup>*</sup>
    * `value`
  * Describing Components and Lists
    * `collection`
      * `itemScope`
      * `item`
  * Example Page Object
    - [Razer Cars Car Type Index](https://github.com/TIY-LR-FEE-2015-Fall/razer-cars-app/blob/master/tests/acceptance/car-types/index-test.js#L6)

## Standups

* Jeremy
  - Going Well: Reducing some stress
  - Needs Work: Finishing up surf & paddle (Overlay photos) and recipe card
  - Learned: How Ember is Setup and Understanding
  - Share From The Field: Too much ham
* David
  - Going Well: Was able to review past assignments
  - Needs Work: Recipe Card (just time)
  - Learned: Acceptance testing is making more sense
  - Share From The Field: Jaguars still are terrible
* Brandi
  - Going Well: Most assignments are caught up
  - Needs Work: Recipe Card (knowing what to write in the tests)
  - Learned: We've done ALOT
  - Share From The Field: Dogs are GREAT!
* Chancey
  - Going Well: Starting to figure out routes in Ember
  - Needs Work: Testing
  - Learned: Testing takes time but is more guaranteed
  - Share From The Field: Sold the XBOX!
* Ryan
  - Going Well: Intro to Driven API
  - Needs Work: API Kit and Server Side Testing
  - Learned: Ember.Object.create && Flexbox Froggy
  - Share From The Field: Walker is in ATL 😬, Fire Alarm

## Needs Review (or Broken Links)

- SASS stuff
- Layout

## Razer Cars

### Done

* Car Types
  - Index
  - Create
  - Edit
* Inventory
  - Index
* Login
  - User can login
  - User can have invalid credentials

## Restaurant Menu Notes

* Models
  - Menu Item
    * Name
    * Description
    * Price
    * Category
  - Order
    * Payment Info
    * Shipping Info
    * Customer Info
    * Delivery or Pickup
    * items (hasMany(OrderItem))
  - Order Item
    * Price when Purchased
    * Quantity
    * menuItem (belongsTo(MenuItem))

## Screencasts


## Homework

* Example:
  - http://obese-finger.surge.sh
  - http://obese-finger.surge.sh/admin/orders
