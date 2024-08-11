# `Array.prototype.map()`

The `map` method creates a new array populated with the results of calling a provided function on every element in the calling array.

#### Syntax

```javascript
let newArray = array.map((element, index, array) => {
    // return new element for newArray
});
```

- **`element`**: The current element being processed in the array.
- **`index`**: The index of the current element being processed (optional).
- **`array`**: The array `map` was called upon (optional).

#### Use Case

Use `map` when you want to transform each element of an array into a new element. It's often used for creating a new array that has the same length as the original array but with modified elements.

#### Example

```javascript
let numbers = [1, 2, 3, 4];
let doubled = numbers.map(number => number * 2);

console.log(doubled);
// Output: [2, 4, 6, 8]
```

In this example, each number in the array is doubled, resulting in a new array with doubled values.

# `Array.prototype.filter()`

The `filter` method creates a new array with all elements that pass the test implemented by the provided function.

#### Syntax

```javascript
let newArray = array.filter((element, index, array) => {
    // return true to keep the element, false otherwise
});
```

- **`element`**: The current element being processed in the array.
- **`index`**: The index of the current element being processed (optional).
- **`array`**: The array `filter` was called upon (optional).

#### Use Case

Use `filter` when you want to create a new array that contains only the elements of the original array that meet certain conditions or criteria.

#### Example

```javascript
let numbers = [1, 2, 3, 4, 5];
let evenNumbers = numbers.filter(number => number % 2 === 0);

console.log(evenNumbers);
// Output: [2, 4]

let numbers = [10, 20, 30, 15, 60];
const multiply10 = numbers.map((number) => number * 10);
const map15Plus = numbers.filter((number) => number > 15);
console.log(`MAP function: ${multiply10}`);
console.log(`Filter function: ${map15Plus}`);
```

In this example, the `filter` method is used to extract only the even numbers from the original array.

# `Array.prototype.find()`

The `find` method returns the value of the first element in the array that satisfies the provided testing function. If no elements satisfy the testing function, `undefined` is returned.

#### Syntax

```javascript
let foundElement = array.find((element, index, array) => {
    // return true if element is found, false otherwise
});
```

- **`element`**: The current element being processed in the array.
- **`index`**: The index of the current element being processed (optional).
- **`array`**: The array `find` was called upon (optional).

#### Use Case

Use `find` when you need to retrieve the first element that meets a specific condition or criteria.

#### Example

```javascript
let numbers = [5, 12, 8, 130, 44];
let found = numbers.find(number => number > 10);

console.log(found);
// Output: 12
```

In this example, `find` is used to locate the first number in the array that is greater than 10.

### Summary

- **`map`**: Transforms each element of an array and returns a new array of the same length with the transformed elements.
- **`filter`**: Returns a new array containing only the elements that pass a specified test.
- **`find`**: Returns the first element in an array that satisfies a provided testing function.

# `Array.prototype.reduce()`

The `reduce` method applies a function against an accumulator and each element in the array (from left to right) to reduce it to a single value.

**Syntax:**

```javascript
array.reduce((accumulator, currentValue, index, array) => {
    // Return updated accumulator
}, initialValue);
```

**Example:**

```javascript
let numbers = [1, 2, 3, 4];
let sum = numbers.reduce((acc, num) => acc + num, 0);
console.log(sum); // Output: 10
```

# `Array.prototype.some()`

The `some` method tests whether at least one element in the array passes the test implemented by the provided function. It returns a Boolean value.

**Example:**

```javascript
let numbers = [1, 2, 3, 4];
let hasEven = numbers.some(number => number % 2 === 0);
console.log(hasEven); // Output: true
```

# `Array.prototype.every()`

The `every` method tests whether all elements in the array pass the test implemented by the provided function. It returns a Boolean value.

**Example:**

```javascript
let numbers = [2, 4, 6];
let allEven = numbers.every(number => number % 2 === 0);
console.log(allEven); // Output: true
```

# `Array.prototype.concat()`

The `concat` method is used to merge two or more arrays. This method does not change the existing arrays but returns a new array.

**Example:**

```javascript
let array1 = [1, 2];
let array2 = [3, 4];
let mergedArray = array1.concat(array2);
console.log(mergedArray); // Output: [1, 2, 3, 4]
```

# `Array.prototype.slice()`

The `slice` method returns a shallow copy of a portion of an array into a new array object selected from `start` to `end` (end not included).

**Example:**

```javascript
let numbers = [1, 2, 3, 4, 5];
let sliced = numbers.slice(1, 3);
console.log(sliced); // Output: [2, 3]
```

# `Array.prototype.splice()`

The `splice` method changes the contents of an array by removing or replacing existing elements and/or adding new elements in place.

**Example:**

```javascript
let numbers = [1, 2, 3, 4, 5];
numbers.splice(2, 1, 9); // Removes 1 element at index 2, adds 9
console.log(numbers); // Output: [1, 2, 9, 4, 5]
```

# `Array.prototype.sort()`

The `sort` method sorts the elements of an array in place and returns the sorted array.

**Example:**

```javascript
let numbers = [4, 2, 5, 1, 3];
numbers.sort((a, b) => a - b); // Ascending order
console.log(numbers); // Output: [1, 2, 3, 4, 5]
```

# `Array.prototype.join()`

The `join` method joins all elements of an array into a string and returns this string.

**Example:**

```javascript
let words = ['Hello', 'world'];
let sentence = words.join(' ');
console.log(sentence); // Output: "Hello world"
```

