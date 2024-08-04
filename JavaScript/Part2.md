# Template Literals

**Overview:**  
Template literals allow for enhanced string handling, including multiline strings, interpolation, and embedded expressions. They are enclosed in backticks (`` ` ``).

**Features:**

1. **Multiline Strings:**
   - Write strings over multiple lines without escape characters.
   ```javascript
   const text = `This is a string
   spanning multiple lines.`;
   ```

2. **String Interpolation:**
   - Embed variables and expressions using `${}`.
   ```javascript
   const name = "Abhishek";
   const greeting = `Hello, ${name}!`;
   ```

3. **Embedded Expressions:**
   - Include any JavaScript expression inside `${}`.
   ```javascript
   const a = 5, b = 10;
   const result = `The sum is ${a + b}.`;
   ```

4. **Tagged Templates:**
   - Use functions to process template literals for custom behavior.
   ```javascript
   function tag(strings, ...values) {
     return strings.reduce((acc, str, i) => `${acc}${str}<strong>${values[i] || ''}</strong>`, '');
   }
   const message = tag`Name: ${name}, Age: ${30}`;
   ```

**Benefits:**  
- Improved readability and ease of string manipulation.
- Simplified handling of dynamic content and multiline text.

These features make template literals a powerful tool for working with strings in JavaScript.

# Arrow Function

**Overview:**  
Arrow functions are a shorthand way to write functions in JavaScript, introduced in ES6 (ECMAScript 2015). They are particularly useful for non-method functions.

**Syntax:**

```javascript
// Basic syntax
const functionName = (parameters) => expression;

// With multiple parameters
const add = (a, b) => a + b;

// With no parameters
const greet = () => console.log("Hello!");

// With a block body (for multiple statements)
const multiply = (a, b) => {
  const result = a * b;
  return result;
};
```

### Key Features

1. **Concise Syntax:**
   - Arrow functions have a shorter syntax compared to traditional function expressions.

2. **Implicit Return:**
   - If the function body consists of a single expression, it is returned implicitly without needing a `return` statement.

   ```javascript
   const square = (x) => x * x; // Implicit return
   ```

3. **Lexical `this`:**
   - Arrow functions do not have their own `this` context. They inherit `this` from the surrounding lexical context, making them ideal for use in methods where the `this` value is inherited.

   ```javascript
   function Counter() {
     this.count = 0;
     setInterval(() => {
       this.count++;
       console.log(this.count);
     }, 1000);
   }
   const counter = new Counter(); // Correctly increments count
   ```

4. **No `arguments` Object:**
   - Arrow functions do not have their own `arguments` object. If you need to access function arguments, you should use rest parameters or use a traditional function.

   ```javascript
   const sum = (...args) => args.reduce((a, b) => a + b, 0);
   ```

### When to Use Arrow Functions

- **For Callbacks:**
  - Arrow functions are great for short, simple functions and callbacks.

  ```javascript
  const numbers = [1, 2, 3, 4];
  const squares = numbers.map(n => n * n);
  ```

- **When Using Lexical `this`:**
  - Use arrow functions to avoid the common pitfalls of `this` in regular functions, especially in event handlers or within methods.

### When Not to Use Arrow Functions

- **For Methods in Classes/Objects:**
  - Arrow functions should not be used as methods in an object or class because they do not have their own `this`.

  ```javascript
  const obj = {
    name: "Test",
    sayName: () => console.log(this.name) // Incorrect: 'this' does not refer to 'obj'
  };
  ```

- **When You Need `arguments`:**
  - If you need access to the `arguments` object, use a regular function.

### Summary

- **Arrow functions** provide a concise syntax and solve common issues with `this` binding.
- Ideal for use in callbacks and functional programming patterns.
- Avoid using them as methods in classes or objects where a dynamic `this` is required.

Enhanced object literals in JavaScript, introduced with ES6 (ECMAScript 2015), provide a more concise and readable syntax for defining object properties and methods. They include several features that streamline the process of working with objects. Here's a summary of the key features of enhanced object literals:

# Enhanced Object Literals

**Overview:**  
Enhanced object literals make it easier to create objects by providing shorthand syntax for common patterns.

### Key Features

1. **Property Shorthand:**
   - You can omit the colon and value if the property name matches the variable name.

   ```javascript
   const name = "Abhishek";
   const age = 25;

   const person = { name, age };

   console.log(person); // { name: "Abhishek", age: 25 }
   ```

2. **Method Shorthand:**
   - Define methods in objects without using the `function` keyword.

   ```javascript
   const person = {
     name: "Abhishek",
     greet() {
       console.log(`Hello, my name is ${this.name}`);
     }
   };

   person.greet(); // Hello, my name is Abhishek
   ```

3. **Computed Property Names:**
   - Use expressions inside square brackets `[]` to define dynamic property names.

   ```javascript
   const propName = "dynamicProp";
   const obj = {
     [propName]: "value"
   };

   console.log(obj); // { dynamicProp: "value" }
   ```

4. **Concise Method Definitions:**
   - Use concise syntax for defining methods within objects, which improves readability.

   ```javascript
   const mathOperations = {
     add(a, b) {
       return a + b;
     },
     subtract(a, b) {
       return a - b;
     }
   };

   console.log(mathOperations.add(5, 3)); // 8
   ```

5. **Prototype Definitions:**
   - Objects can include a `__proto__` property to set the prototype directly.

   ```javascript
   const proto = {
     greet() {
       console.log("Hello from proto!");
     }
   };

   const obj = {
     __proto__: proto,
     customMethod() {
       console.log("This is a custom method.");
     }
   };

   obj.greet(); // Hello from proto!
   ```

### Summary

- **Property Shorthand:** Simplifies object creation by reducing redundancy.
- **Method Shorthand:** Provides a cleaner syntax for defining object methods.
- **Computed Property Names:** Allows dynamic property creation using expressions.
- **Prototype Definitions:** Easily set the prototype of an object with `__proto__`.

Enhanced object literals are useful for creating objects more efficiently and making the code easier to read and maintain. They help to reduce boilerplate code and provide a modern syntax for object-oriented programming in JavaScript.

# Default value in function
```JS
const printName = (name = "Abhishek") => `Hello ${name}`;
console.log(printName("Rajesh"));

function multiply(a, b = 1) {
  return a * b;
}

console.log(multiply(5, 2));
```
Here are concise notes on the spread operator (`...`) in JavaScript, which is a versatile feature introduced in ES6 (ECMAScript 2015) for expanding iterables and objects.

# Spread Operator

**Overview:**  
The spread operator (`...`) allows an iterable (like an array or string) or an object to be expanded in places where zero or more elements/values are expected. It can be used for function arguments, array literals, and object literals.

### Key Uses

1. **Expanding Arrays:**
   - The spread operator can expand elements of an iterable (like an array) into individual elements.

   ```javascript
   const numbers = [1, 2, 3];
   const newNumbers = [...numbers, 4, 5];

   console.log(newNumbers); // [1, 2, 3, 4, 5]
   ```

2. **Copying Arrays:**
   - Create a shallow copy of an array quickly and easily.

   ```javascript
   const originalArray = [1, 2, 3];
   const copiedArray = [...originalArray];

   console.log(copiedArray); // [1, 2, 3]
   ```

3. **Merging Arrays:**
   - Combine multiple arrays into one.

   ```javascript
   const array1 = [1, 2, 3];
   const array2 = [4, 5, 6];
   const mergedArray = [...array1, ...array2];

   console.log(mergedArray); // [1, 2, 3, 4, 5, 6]
   ```

4. **Spreading in Function Calls:**
   - Pass elements of an array as arguments to a function.

   ```javascript
   const numbers = [1, 2, 3];
   const sum = (a, b, c) => a + b + c;

   console.log(sum(...numbers)); // 6
   ```

5. **Copying Objects:**
   - Create a shallow copy of an object.

   ```javascript
   const originalObject = { a: 1, b: 2 };
   const copiedObject = { ...originalObject };

   console.log(copiedObject); // { a: 1, b: 2 }
   ```

6. **Merging Objects:**
   - Combine multiple objects into one.

   ```javascript
   const obj1 = { a: 1, b: 2 };
   const obj2 = { c: 3, d: 4 };
   const mergedObject = { ...obj1, ...obj2 };

   console.log(mergedObject); // { a: 1, b: 2, c: 3, d: 4 }
   ```

7. **Overriding Properties:**
   - Properties in objects can be overridden when using the spread operator.

   ```javascript
   const obj1 = { a: 1, b: 2 };
   const obj2 = { b: 3, c: 4 };
   const combinedObject = { ...obj1, ...obj2 };

   console.log(combinedObject); // { a: 1, b: 3, c: 4 }
   ```

### Summary

- **Arrays:** Use the spread operator to copy, merge, or expand arrays.
- **Objects:** Use it to copy or merge objects, with latter properties overriding former ones.
- **Function Arguments:** Spread array elements into individual function arguments.
- **Shallow Copies:** The spread operator creates shallow copies, meaning nested objects or arrays are not duplicated.

# Rest Parameter

**Overview:**  
The Rest Parameter (`...`) allows you to represent an indefinite number of arguments as an array in a function. It provides a clean and efficient way to handle functions that can receive varying numbers of arguments.

### Syntax

```javascript
function functionName(param1, param2, ...rest) {
  // Function body
}
```

- `...rest` is the rest parameter, which will collect all remaining arguments into an array named `rest`.

### Key Features

1. **Collecting Arguments:**
   - The rest parameter gathers all the remaining arguments passed to a function into an array.

   ```javascript
   function logArguments(...args) {
     console.log(args);
   }

   logArguments(1, 2, 3, 4); // Output: [1, 2, 3, 4]
   ```

2. **Flexible Argument Handling:**
   - It allows you to handle a variable number of arguments without using the `arguments` object.

   ```javascript
   function sum(...numbers) {
     return numbers.reduce((total, num) => total + num, 0);
   }

   console.log(sum(1, 2, 3)); // Output: 6
   console.log(sum(10, 20)); // Output: 30
   ```

3. **Combining with Named Parameters:**
   - You can combine rest parameters with named parameters, but the rest parameter must be the last in the function definition.

   ```javascript
   function concatenate(separator, ...strings) {
     return strings.join(separator);
   }

   console.log(concatenate(", ", "a", "b", "c")); // Output: "a, b, c"
   ```

4. **Difference from the `arguments` Object:**
   - The `arguments` object is not a true array but an array-like object, whereas the rest parameter is a real array.
   - The rest parameter does not include named parameters, whereas the `arguments` object includes all passed arguments.

   ```javascript
   function showArguments(...args) {
     console.log(args instanceof Array); // true
     console.log(args);
   }

   showArguments("apple", "banana", "cherry"); // Output: ["apple", "banana", "cherry"]
   ```

5. **Using with Arrow Functions:**
   - Arrow functions do not have their own `arguments` object, making rest parameters especially useful.

   ```javascript
   const multiply = (...nums) => nums.reduce((product, num) => product * num, 1);

   console.log(multiply(2, 3, 4)); // Output: 24
   ```

### Summary

- **Collects Excess Arguments:** Rest parameters gather any number of arguments into an array, allowing functions to handle an indefinite number of inputs.
- **Flexible and Clean:** They provide a cleaner alternative to the `arguments` object and work well with other ES6 features.
- **Must Be Last:** The rest parameter must be the last parameter in the function definition.

### Examples
```JS

function sum(...numbers) {
  let sum = 0;
  for (let number of numbers) {
    sum += number;
  }
  return sum;
}

console.log(sum(1, 2, 3, 4, 5)); // Output: 15


function sumArray(...numbers) {
  sumVal = numbers.reduce(
    (accumulator, currentValue) => accumulator + currentValue,
    0
  );
  console.log(sumVal);
}

// Example usage

sumArray(1, 2, 3, 4, 5);

console.log(totalSum); // Output: 15

function restTest(...params) {
  for (let index = 0; index < params.length; index++) {
    console.log(params[index]);
  }
}

restTest("Take", "unlimited", "value", "in", "the", "params");

function sum(...nums) {
  let summation = nums.reduce((a, b) => a + b, 0);
  console.log(summation);
}

sum(20, 50, 75, 25, 30);
```
Here are concise notes on array destructuring in JavaScript, a feature that allows you to unpack values from arrays into distinct variables.

# Destructuring
## Array Destructuring

**Overview:**  
Array destructuring in JavaScript allows you to extract values from arrays and assign them to variables in a single, concise statement. This syntax makes it easy to work with data stored in arrays.

### Syntax

```javascript
const [var1, var2, ...rest] = array;
```

- **`var1`, `var2`**: Variables to which the array elements are assigned.
- **`rest`**: Collects the remaining elements into an array.

### Key Features

1. **Basic Destructuring:**
   - Assign values from an array to variables based on their position.

   ```javascript
   const fruits = ["apple", "banana", "cherry"];
   const [first, second, third] = fruits;

   console.log(first); // Output: "apple"
   console.log(second); // Output: "banana"
   console.log(third); // Output: "cherry"
   ```

2. **Skipping Elements:**
   - Skip elements by leaving empty slots.

   ```javascript
   const numbers = [1, 2, 3, 4, 5];
   const [first, , third] = numbers;

   console.log(first); // Output: 1
   console.log(third); // Output: 3
   ```

3. **Default Values:**
   - Assign default values to variables if the array does not have enough elements.

   ```javascript
   const colors = ["red"];
   const [primary, secondary = "blue"] = colors;

   console.log(primary); // Output: "red"
   console.log(secondary); // Output: "blue"
   ```

4. **Rest Parameter:**
   - Collect remaining elements into a new array.

   ```javascript
   const scores = [10, 20, 30, 40];
   const [first, second, ...rest] = scores;

   console.log(first); // Output: 10
   console.log(second); // Output: 20
   console.log(rest); // Output: [30, 40]
   ```

5. **Swapping Variables:**
   - Use destructuring to swap values between variables.

   ```javascript
   let a = 1;
   let b = 2;

   [a, b] = [b, a];

   console.log(a); // Output: 2
   console.log(b); // Output: 1
   ```

6. **Destructuring with Functions:**
   - Easily pass and return arrays in functions.

   ```javascript
   function getCoordinates() {
     return [10, 20];
   }

   const [x, y] = getCoordinates();

   console.log(x); // Output: 10
   console.log(y); // Output: 20
   ```

### Summary

- **Concise and Readable:** Array destructuring provides a cleaner and more readable way to extract values from arrays.
- **Default Values:** Supports default values for handling undefined elements.
- **Rest Parameter:** Use the rest parameter to gather the remaining elements into an array.
- **Versatile:** Useful for swapping variables, handling function returns, and managing multiple variables efficiently.

## Object Destructuring

**Overview:**  
Object destructuring in JavaScript lets you unpack properties from objects and assign them to variables in a concise and readable manner. This syntax is useful for extracting data from complex objects.

### Syntax

```javascript
const { property1, property2 } = object;
```

- **`property1`, `property2`**: The names of the properties you want to extract.
- **`object`**: The object from which properties are being extracted.

### Key Features

1. **Basic Destructuring:**
   - Extract multiple properties from an object.

   ```javascript
   const person = { name: "Abhishek", age: 25, city: "New York" };
   const { name, age, city } = person;

   console.log(name); // Output: "Abhishek"
   console.log(age);  // Output: 25
   console.log(city); // Output: "New York"
   ```

2. **Default Values:**
   - Assign default values to variables if the property is `undefined`.

   ```javascript
   const person = { name: "Abhishek" };
   const { name, age = 30 } = person;

   console.log(name); // Output: "Abhishek"
   console.log(age);  // Output: 30
   ```

3. **Renaming Variables:**
   - Use a colon (`:`) to rename variables while destructuring.

   ```javascript
   const person = { name: "Abhishek", age: 25 };
   const { name: fullName, age: years } = person;

   console.log(fullName); // Output: "Abhishek"
   console.log(years);    // Output: 25
   ```

4. **Nested Destructuring:**
   - Extract properties from nested objects.

   ```javascript
   const user = {
     name: "Abhishek",
     address: {
       city: "New York",
       zip: 10001
     }
   };
   const {
     name,
     address: { city, zip }
   } = user;

   console.log(name); // Output: "Abhishek"
   console.log(city); // Output: "New York"
   console.log(zip);  // Output: 10001
   ```

5. **Rest Properties:**
   - Collect the remaining properties into a new object.

   ```javascript
   const person = { name: "Abhishek", age: 25, city: "New York" };
   const { name, ...rest } = person;

   console.log(name); // Output: "Abhishek"
   console.log(rest); // Output: { age: 25, city: "New York" }
   ```

6. **Function Parameters:**
   - Use destructuring to extract properties from objects passed as function parameters.

   ```javascript
   function displayPerson({ name, age }) {
     console.log(`Name: ${name}, Age: ${age}`);
   }

   const person = { name: "Abhishek", age: 25 };
   displayPerson(person); // Output: "Name: Abhishek, Age: 25"
   ```

### Summary

- **Concise Syntax:** Object destructuring provides a clean and concise way to extract object properties.
- **Default Values:** Supports default values for undefined properties.
- **Renaming and Nesting:** Allows renaming of variables and extraction from nested structures.
- **Flexible:** Works well with function parameters, enhancing code readability and maintainability.

## Nested Destructuring
```JS
const songs = [
  { name: "lucky you", singer: "Joyner", duration: 4.34 },
  { name: "Just Like you", singer: "NF", duration: 3.23 },
  { name: "Humble Singer", singer: "Kendrick Lamar", duration: 2.33 },
  { name: "Old Town Road", singer: "Lil Nas X", duration: 1.43 },
];

const [, { singer: singer2 }, { singer: singer3 }, { singer: singer4 }] = songs;
// console.log("Singer1: ", singer1);
console.log("Singer2: ", singer2);
console.log("Singer3: ", singer3);
console.log("Singer4: ", singer4);

console.log(typeof songs);
console.log(Array.isArray(songs));
```
## Mix destructuring
Robust Example of destructuring
```JS
const data = {
  user: {
    id: 123,
    name: "John Doe",
    age: 30,
    email: "john.doe@example.com",
    address: {
      city: "New York",
      country: "USA",
    },
    hobbies: ["Reading", "Painting", "Cooking"],
    scores: {
      math: 95,
      science: 88,
      history: 75,
    },
  },
  products: [
    { id: 1, name: "Laptop", price: 1000 },
    { id: 2, name: "Phone", price: 800 },
    { id: 3, name: "Tablet", price: 500 },
  ],
  settings: {
    darkMode: true,
    notifications: {
      email: true,
      sms: false,
      push: true,
    },
    language: "English",
  },
};

// Extracting data using object destructuring
const {
  user: {
    name,
    age,
    address: { city, country },
    hobbies,
    scores: { math, science, history },
    email,
  },
  products: [product1, product2, product3],
  settings: {
    darkMode,
    notifications: {
      email: emailNotifications,
      sms: smsNotifications,
      push: pushNotifications,
    },
    language,
  },
} = data;

// Logging the extracted data using template literals
console.log(`Name: ${name}`);
console.log(`Age: ${age}`);
console.log(`Address: ${city}, ${country}`);
console.log(`Hobbies: ${hobbies.join(", ")}`);
console.log(`Math Score: ${math}`);
console.log(`Science Score: ${science}`);
console.log(`History Score: ${history}`);
console.log(`Product 1: ${product1.name} - $${product1.price}`);
console.log(`Product 2: ${product2.name} - $${product2.price}`);
console.log(`Product 3: ${product3.name} - $${product3.price}`);
console.log(`Dark Mode: ${darkMode}`);
console.log(`Email Notifications: ${emailNotifications}`);
console.log(`SMS Notifications: ${smsNotifications}`);
console.log(`Push Notifications: ${pushNotifications}`);
console.log(`Language: ${language}`);
```
Certainly! Here are more concise notes on the ternary operator while retaining the essential information:

# Ternary Operator Overview

The ternary operator, also known as the conditional operator, provides a shorthand way to write `if-else` statements in JavaScript. It is especially useful for simple conditional expressions.

### Syntax

```javascript
condition ? expressionIfTrue : expressionIfFalse;
```

- **`condition`**: Evaluates to `true` or `false`.
- **`expressionIfTrue`**: Executed if `condition` is `true`.
- **`expressionIfFalse`**: Executed if `condition` is `false`.

### Example Usage

#### Basic Example

```javascript
let age = 18;
let canVote = age >= 18 ? 'Yes' : 'No';
console.log(canVote); // Output: 'Yes'
```

This example assigns `'Yes'` to `canVote` if `age` is 18 or more, otherwise `'No'`.

#### Conditional Assignment

```javascript
let number = 5;
let type = number % 2 === 0 ? 'even' : 'odd';
console.log(type); // Output: 'odd'
```

Assigns `'even'` or `'odd'` based on whether `number` is divisible by 2.

#### Nested Ternary Operator

```javascript
let score = 85;
let grade = score >= 90 ? 'A' :
            score >= 80 ? 'B' :
            score >= 70 ? 'C' :
            score >= 60 ? 'D' : 'F';
console.log(grade); // Output: 'B'
```

Assigns a letter grade based on the `score`.

### Usage Tips

- **Conciseness**: Best for short, simple conditions.
- **Readability**: Use parentheses for clarity when mixed with other operations:

  ```javascript
  let x = (a + b) > (c + d) ? 'greater' : 'less or equal';
  ```

- **Avoid Overuse**: For complex conditions, prefer `if-else` statements.

# For Loop versions in JS

### 1. Traditional `for` Loop

The most basic form, used for simple iteration over a range.

**Syntax:**

```javascript
for (initialization; condition; increment) {
    // Code to be executed
}
```

**Example:**

```javascript
for (let i = 0; i < 5; i++) {
    console.log(i);
}
// Output: 0 1 2 3 4
```

**Use Case:** Ideal for situations where you need to iterate a specific number of times or need precise control over the iteration process.

### 2. `for...in` Loop

Used to iterate over the enumerable properties of an object.

**Syntax:**

```javascript
for (let key in object) {
    // Code to be executed
}
```

**Example:**

```javascript
const object = { a: 1, b: 2, c: 3 };
for (let key in object) {
    if (object.hasOwnProperty(key)) {
        console.log(key, object[key]);
    }
}
// Output: a 1 b 2 c 3
```
```JS
let person = {
  name: "Abhishek",
  age: 26,
  city: "Bangalore",
};

for (let keys in person) {
  console.log(keys, ": ", person[keys]);
}

console.log("###########################################");
list = ["one", "two", "three", "four"];
for (let numbers in list) {
  console.log(numbers);
}

const object = { a: 1, b: 2, c: 3 };

for (let [key, value] of Object.entries(object)) {
  console.log(key, value);
}

for (let keys in object) {
  console.log(`${keys}: ${object[keys]}`);
}
```

**Use Case:** Best for iterating over object properties. Use `hasOwnProperty` to ensure you’re iterating over the object’s own properties.

### 3. `for...of` Loop

Used to iterate over iterable objects like arrays, strings, maps, sets, etc.

**Syntax:**

```javascript
for (let element of iterable) {
    // Code to be executed
}
```

**Example:**

```javascript
const array = ['apple', 'banana', 'cherry'];
for (let fruit of array) {
    console.log(fruit);
}
// Output: apple banana cherry
```

**Use Case:** Ideal for iterating over arrays or any iterable object without needing to deal with indices.

### 4. `forEach` Method

A method available on arrays that executes a provided function once for each array element.

**Syntax:**

```javascript
array.forEach((element, index, array) => {
    // Code to be executed
});
```

**Example:**

```javascript
const array = ['apple', 'banana', 'cherry'];
array.forEach((fruit, index) => {
    console.log(index, fruit);
});
// Output: 0 apple 1 banana 2 cherry
```

**Use Case:** Good for performing an action on each element of an array without modifying the array itself. Note that `forEach` cannot be broken out of like a `for` loop.

### 5. `for await...of` Loop

Used for iterating over asynchronous iterable objects, such as streams or async generators.

**Syntax:**

```javascript
for await (let item of asyncIterable) {
    // Code to be executed
}
```

**Example:**

```javascript
async function* asyncGenerator() {
    yield Promise.resolve(1);
    yield Promise.resolve(2);
    yield Promise.resolve(3);
}

(async () => {
    for await (let num of asyncGenerator()) {
        console.log(num);
    }
})();
// Output: 1 2 3
```

**Use Case:** Useful for handling asynchronous data streams or iterating over results from asynchronous operations.

### Considerations

- **Choosing the Right Loop:** Use the loop type that best fits the data structure and operations you're working with. `for...of` is more modern and generally preferred for array-like iterations, while `for...in` is useful for objects.
- **Performance:** While performance differences are usually negligible, traditional `for` loops can be more performant in cases where tight control is needed.
- **Readability:** Always consider readability and maintainability. Simpler loops like `for...of` and `forEach` often result in cleaner code.

## When to use what for loop:

Guide for choosing right for loop

### 1. **Traditional `for` Loop**

**Use When:**

- You need precise control over the iteration process, such as specific start, stop, and step values.
- You're working with indexes directly, such as modifying elements at specific positions in an array.
- You need to break out of the loop early or skip certain iterations using `break` and `continue`.

**Example:**

```javascript
for (let i = 0; i < array.length; i++) {
    if (array[i] === target) {
        console.log('Found target');
        break;
    }
}
```

### 2. **`for...in` Loop**

**Use When:**

- You need to iterate over an object's enumerable properties.
- You're dealing with non-array objects where you want to access keys and values.

**Avoid When:**

- Iterating over arrays, as `for...in` iterates over all enumerable properties, which can lead to unexpected results with arrays.

**Example:**

```javascript
const object = { name: 'Alice', age: 25 };
for (let key in object) {
    if (object.hasOwnProperty(key)) {
        console.log(key, object[key]);
    }
}
```

### 3. **`for...of` Loop**

**Use When:**

- Iterating over arrays, strings, maps, sets, or any iterable object.
- You want a simple and clean syntax for accessing elements directly without dealing with indices.
- You're working with collections that don't need modification by index.

**Example:**

```javascript
const fruits = ['apple', 'banana', 'cherry'];
for (let fruit of fruits) {
    console.log(fruit);
}
```

### 4. **`forEach` Method**

**Use When:**

- You need to perform an operation on each element of an array.
- You're focused on readability and simplicity, especially when dealing with arrays.

**Limitations:**

- Cannot use `break`, `continue`, or `return` to exit early.
- Primarily used for side effects rather than transforming data.

**Example:**

```javascript
const numbers = [1, 2, 3, 4];
numbers.forEach(number => {
    console.log(number * 2);
});
```

### 5. **`for await...of` Loop**

**Use When:**

- Iterating over asynchronous data, such as streams or results from async functions.
- You need to handle promises in a sequential manner.

**Example:**

```javascript
async function* asyncGenerator() {
    yield Promise.resolve(1);
    yield Promise.resolve(2);
    yield Promise.resolve(3);
}

(async () => {
    for await (let num of asyncGenerator()) {
        console.log(num);
    }
})();
```

### Summary

- **Use `for` loop** when you need complete control over the loop's iteration variables.
- **Use `for...in`** for iterating over object properties, but avoid it for arrays.
- **Use `for...of`** for iterating over arrays and other iterables with clean, readable syntax.
- **Use `forEach`** for array operations where exiting the loop early isn't needed, focusing on readability.
- **Use `for await...of`** for handling asynchronous iterables in a clear and sequential way.
