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
