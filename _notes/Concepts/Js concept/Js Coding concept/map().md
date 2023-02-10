1. What is Map() method
	- In JavaScript, the `map()` method is used to create a new array with the results of calling a provided function on every element in the calling array. The `map()` method is used to iterate through each element of an array, apply a function on each element, and return a new array with the results. Here is an example of using the `map()` method:

```js
let people = [ 
{ name: "John", age: 25 }, 
{ name: "Mary", age: 30 }, 
{ name: "Bob", age: 35 }, 
{ name: "Jane", age: 40 } 
]; 
let names = people.map(function(person) { return person.name; });

console.log(names); // Output: ["John", "Mary", "Bob", "Jane"]
```