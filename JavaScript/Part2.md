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
