
1. Both `map()` and `filter()` are array methods in JavaScript that are used to iterate over the elements of an array, but they work in different ways.

2. `map()` creates a new array with the results of calling a provided function on every element in the calling array. It is used to transform the elements of an array, by applying a function on each element and returning a new array with the results.

3. `filter()` creates a new array with all elements that pass a certain test implemented by a provided function. It is used to filter the elements of an array, by calling a function on each element and including the element in the new array if the function returns true.

Here is an example that illustrates the difference between `map()` and `filter()`:

```js
let numbers = [1, 2, 3, 4, 5]; 
let doubledNumbers = numbers.map(function(number) { 
return number * 2; 
}); 
console.log(doubledNumbers); 

// Output: [2, 4, 6, 8, 10] 
let evenNumbers = numbers.filter(function(number) { return number % 2 == 0; }); console.log(evenNumbers); // Output: [2, 4]
```

So Map is for u to create new Array. But filter is to create array with some kind of conditions.