1. In Mongoose, a popular ODM (Object Document Mapping) library for MongoDB, a method is a function that is defined on a Mongoose model. Methods can be used to perform various operations on the instances of that model, such as querying the database, updating or deleting instances, or performing custom logic.

2. For example, you can define a custom method on a Mongoose model to calculate the total price of all items in an order, as follows:

```js
const mongoose = require('mongoose'); 

const orderSchema = new mongoose.Schema({ 
items: [{ name: String, price: Number }], 
}); 

orderSchema.methods.totalPrice = function () { 
return this.items.reduce((total, item) => total + item.price, 0); }; 

const Order = mongoose.model('Order', orderSchema);
```
	In this example, the `totalPrice` method can be called on an instance(객체) of the `Order` model to calculate the total price of all items in the order.

Mongoose also provides a number of built-in model methods for performing common operations, such as `find`, `findOne`, `findById`, `update`, `remove`, etc. These methods are available on the model itself, and return a Mongoose query that can be executed using the `exec` method.