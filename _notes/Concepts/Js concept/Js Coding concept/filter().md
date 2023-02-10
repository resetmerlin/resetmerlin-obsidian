1. What is filter?
	- In JavaScript, the `filter()` method is used to create a new array with all elements that pass a certain test implemented by a provided function. The function is called for each element in the original array, and the element is included in the new array if the function returns true. Here is an example of using the `filter()` method:


```js
let numbers = [1, 2, 3, 4, 5, 6]; let evenNumbers = numbers.filter(function(number) { return number % 2 == 0; }); console.log(evenNumbers); // Output: [2, 4, 6]
	```

```js
let people = [ 
{ name: "John", age: 25 }, 
{ name: "Mary", age: 30 }, 
{ name: "Bob", age: 35 }, 
{ name: "Jane", age: 40 } ]; 

let adults = people.filter(function(person) { return person.age >= 18; }); console.log(adults); 
/* Output: [ 
{ name: "John", age: 25 }, 
{ name: "Mary", age: 30 },
{ name: "Bob", age: 35 }, 
{ name: "Jane", age: 40 } ] */
```


- these are more advanced code with filter()
```js
let numbers = [1, 2, 3, 4, 5, 6]; 
let filteredNumbers = numbers.filter(n => n > 3 && n < 6); console.log(filteredNumbers); // Output: [4, 5]
```

- U can use it even there is an object inside of array
```js
let nestedArray = [ 
{ name: "John", age: 25, fruits: ["apple","orange"] }, 
{ name: "Mary", age: 30, fruits: ["banana","kiwi"] }, 
{ name: "Bob", age: 35, fruits: ["cherry","date"] }, 
]; 
let filteredList = nestedArray.filter(list => list.fruits.filter(fruit => fruit == "banana")); 

console.log(filteredList); /* Output: [ { name: "Mary", age: 30, fruits: ["banana","kiwi"] } ] */
```