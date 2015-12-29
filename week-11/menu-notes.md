# Menu Notes

## Models

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

## Cart Service Pseudo Code

```js
Ember.Service.extend({
  store: Ember.inject.service(),

  order: null,

  newOrder() {
    let order = this.get('store').createRecord('order');

    this.set('order', order);
  },

  init(...args) {
    this._super(...args);

    this.newOrder();
  },

  // Probably want to unit test this...
  existsInCart(item) {
    // Check if item is already in the cart/order
  },

  // Probably want to unit test this...
  addItem(item) {
    if (this.existsInCart(item)) {
      // Increment existing quantity
    } else {
      // Create a new order item for the current order
    }
  },

  sendOrder() {
    // Save the order
    // Then Save all order items
    // Then this.newOrder()
  },
})
```
