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
