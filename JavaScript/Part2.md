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
