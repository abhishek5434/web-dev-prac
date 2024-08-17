# Basic Concepts

### Understanding the DOM Tree Structure

The Document Object Model (DOM) is a programming interface that represents an HTML or XML document as a tree structure. It allows programs and scripts to dynamically access and update the content, structure, and style of a document. The DOM represents the document as a hierarchical tree of nodes.

#### DOM Tree Structure

- **Document**: The root node of the DOM tree, representing the entire HTML document.
- **Element Nodes**: Nodes that correspond to HTML tags, such as `<div>`, `<p>`, and `<a>`. These nodes can have child nodes and attributes.
- **Text Nodes**: Nodes that contain the text content within an element. They are always leaf nodes (i.e., they do not have children).
- **Attribute Nodes**: Represent the attributes of an element, such as `class`, `id`, or `src`. Attributes provide additional information about elements but are not part of the main DOM tree hierarchy.

#### Example: HTML and DOM Representation

**HTML:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Sample Document</title>
</head>
<body>
  <h1>Hello, World!</h1>
  <p>This is a paragraph.</p>
</body>
</html>
```

**DOM Structure:**

```
Document
 └── html
     ├── head
     │   ├── meta
     │   └── title
     └── body
         ├── h1
         │   └── "Hello, World!"
         └── p
             └── "This is a paragraph."
```

### Node Types

Nodes are the basic units of the DOM. Each node has a type, which determines its role and properties within the DOM tree.

#### Common Node Types

1. **Element Node (`Node.ELEMENT_NODE`)**: 
   - Represents an HTML element.
   - Has a node type value of `1`.
   - Can contain attributes and child nodes.
   - Example: `<div>`, `<span>`.

2. **Text Node (`Node.TEXT_NODE`)**:
   - Represents the text content of an element.
   - Has a node type value of `3`.
   - Always a leaf node with no children.
   - Example: The text inside `<p>Hello</p>`.

3. **Attribute Node (`Node.ATTRIBUTE_NODE`)**:
   - Represents an attribute of an element.
   - Has a node type value of `2`.
   - Associated with an element but not directly part of the DOM tree.
   - Example: `class="highlight"`.

4. **Document Node (`Node.DOCUMENT_NODE`)**:
   - Represents the entire HTML or XML document.
   - Root of the DOM tree with a node type value of `9`.

5. **Comment Node (`Node.COMMENT_NODE`)**:
   - Represents a comment in the document.
   - Has a node type value of `8`.

**Examples:**
Get the head: ```console.log(document.head)```
Get Title: ```console.log(document.title)```
Get Body: ```console.log(document.body)```
Get URL of the page: ```console.log(document.documentURI)

### Selecting DOM Elements

Selecting elements from the DOM is essential for manipulating the content and structure of a web page. There are several methods for selecting elements, each suited for different use cases.

#### Selecting Elements by ID

- **`document.getElementById()`**: 
  - Selects a single element by its unique `id` attribute.
  - Returns the first element with the specified ID or `null` if no matching element is found.
  
  **Example:**

  ```html
  <h1 id="header">Welcome</h1>

  <script>
    let header = document.getElementById('header');
    console.log(header.textContent); // Output: "Welcome"
  </script>
  ```

#### Selecting Elements by Class or Tag

- **`document.getElementsByClassName()`**:
  - Selects all elements with the specified class name.
  - Returns an `HTMLCollection`, which is a live collection of elements.
  
  **Example:**

  ```html
  <p class="text">First paragraph.</p>
  <p class="text">Second paragraph.</p>

  <script>
    let paragraphs = document.getElementsByClassName('text');
    console.log(paragraphs.length); // Output: 2
  </script>
  ```

- **`document.getElementsByTagName()`**:
  - Selects all elements with the specified tag name.
  - Returns an `HTMLCollection`.

  **Example:**

  ```html
  <div>First div</div>
  <div>Second div</div>

  <script>
    let divs = document.getElementsByTagName('div');
    console.log(divs.length); // Output: 2
  </script>
  ```

#### Using Query Selectors

- **`document.querySelector()`**:
  - Selects the first element that matches a given CSS selector.
  - Returns the element or `null` if no match is found.

  **Example:**

  ```html
  <h1 class="title">Main Title</h1>

  <script>
    let title = document.querySelector('.title');
    console.log(title.textContent); // Output: "Main Title"
  </script>
  ```

- **`document.querySelectorAll()`**:
  - Selects all elements that match a given CSS selector.
  - Returns a `NodeList`, which is a static collection of elements.

  **Example:**

  ```html
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>

  <script>
    let items = document.querySelectorAll('li');
    items.forEach(item => console.log(item.textContent));
    // Output:
    // Item 1
    // Item 2
    // Item 3
  </script>
  ```
Additional Example:
```JS
const h1 = document.querySelector("h1");
h1.innerText = "Text Changed";
h1.innerHTML = "<em>Change HTML</em>"; // This will italicize the text
h1.innerHTML = "<del>HTML Heading changed</del>"; // This will strike out the heading text
```

# Understanding `innerText`, `innerHTML`, and `textContent` in JavaScript

#### 1. `innerText`
- **Description**: 
  - `innerText` represents the "rendered" text content of a node and its descendants. It takes into account the CSS styles, such as `display: none` or `visibility: hidden`, which means it will not return text that is hidden from the user.
- **Use Cases**: 
  - Useful when you want to retrieve or set the visible text as a user sees it.
- **Example**:
  ```javascript
  const element = document.getElementById('example');
  console.log(element.innerText); // Gets the visible text content of the element.
  element.innerText = 'New Text'; // Changes the visible text content.
  ```

#### 2. `innerHTML`
- **Description**: 
  - `innerHTML` allows you to get or set the HTML content inside an element. It includes any HTML tags within the element, and it is often used to insert dynamic content.
- **Use Cases**: 
  - Useful when you need to manipulate or inject HTML content directly.
- **Example**:
  ```javascript
  const element = document.getElementById('example');
  console.log(element.innerHTML); // Gets the HTML content of the element.
  element.innerHTML = '<strong>Bold Text</strong>'; // Sets new HTML content, replacing existing content.
  ```
- **Caution**:
  - Be careful when setting `innerHTML` with user-provided content, as it can lead to XSS (Cross-Site Scripting) attacks if not properly sanitized.

#### 3. `textContent`
- **Description**: 
  - `textContent` retrieves or sets the text content of a node and all its descendants, but it includes all text within the node, regardless of whether it is visible or not. It does not consider any CSS styling, and it returns the full text including hidden elements.
- **Use Cases**: 
  - Useful when you need to get or set the raw text without any HTML tags or consideration of styling.
- **Example**:
  ```javascript
  const element = document.getElementById('example');
  console.log(element.textContent); // Gets the text content of the element, including hidden text.
  element.textContent = 'Plain Text'; // Replaces the text content without inserting HTML.
  ```

#### Key Differences
- **`innerText` vs `textContent`**: 
  - `innerText` considers CSS styling and only returns visible text, while `textContent` retrieves all text, regardless of visibility.
- **`innerHTML` vs `textContent`**:
  - `innerHTML` returns or sets content as HTML, including tags, while `textContent` works purely with text, stripping out all HTML tags.

#### Summary
- Use `innerText` when you care about the text as it's displayed to the user.
- Use `innerHTML` when you need to work with HTML structures within an element.
- Use `textContent` when you need to retrieve or set the raw text content without any concern for HTML or CSS visibility.

---
Certainly! Here’s a detailed note on the `classList` method in JavaScript:

---

### Understanding the `classList` Method in JavaScript

The `classList` property is a convenient way to manipulate the classes of an HTML element. It provides methods to add, remove, toggle, and check classes on an element, which can be extremely useful for dynamically changing the appearance or behavior of elements in response to user actions or other events.

#### What is `classList`?

- **Description**: 
  - `classList` is a read-only property that returns a live `DOMTokenList` collection of the class attributes of the element. This collection allows you to easily manipulate the classes without having to work with the class attribute directly as a string.

- **Type**: 
  - The `classList` property returns a `DOMTokenList` object, which is an array-like object where each entry is a class name associated with the element.

# Common Methods of `classList`

1. **`add()`**
   - **Description**: Adds one or more classes to the element.
   - **Syntax**: `element.classList.add(class1, class2, ...)`
   - **Example**:
     ```javascript
     const element = document.getElementById('example');
     element.classList.add('active', 'highlight'); // Adds the classes 'active' and 'highlight' to the element.
     ```

2. **`remove()`**
   - **Description**: Removes one or more classes from the element.
   - **Syntax**: `element.classList.remove(class1, class2, ...)`
   - **Example**:
     ```javascript
     const element = document.getElementById('example');
     element.classList.remove('active', 'highlight'); // Removes the classes 'active' and 'highlight' from the element.
     ```

3. **`toggle()`**
   - **Description**: Toggles a class on the element. If the class is present, it removes it; if it’s not present, it adds it. Optionally, you can pass a second argument, a boolean, to explicitly add or remove the class.
   - **Syntax**: `element.classList.toggle(className, [force])`
   - **Example**:
     ```javascript
     const element = document.getElementById('example');
     element.classList.toggle('active'); // Toggles the 'active' class: adds it if not present, removes it if present.
     element.classList.toggle('active', true); // Ensures 'active' class is added.
     ```

4. **`contains()`**
   - **Description**: Checks if the element has a specific class.
   - **Syntax**: `element.classList.contains(className)`
   - **Returns**: `true` if the class is present, `false` otherwise.
   - **Example**:
     ```javascript
     const element = document.getElementById('example');
     if (element.classList.contains('active')) {
       console.log('Element has the "active" class.');
     }
     ```

5. **`replace()`**
   - **Description**: Replaces an existing class with a new class.
   - **Syntax**: `element.classList.replace(oldClass, newClass)`
   - **Example**:
     ```javascript
     const element = document.getElementById('example');
     element.classList.replace('old-class', 'new-class'); // Replaces 'old-class' with 'new-class'.
     ```

6. **`length`**
   - **Description**: This property gives the number of classes that the element has.
   - **Syntax**: `element.classList.length`
   - **Example**:
     ```javascript
     const element = document.getElementById('example');
     console.log(element.classList.length); // Outputs the number of classes on the element.
     ```

#### Benefits of Using `classList`

- **Ease of Use**: Manipulating classes via `classList` is more straightforward and less error-prone than managing class names as a single string.
- **Performance**: Using `classList` is more efficient, especially when dealing with multiple classes, compared to manually concatenating strings.
- **Safety**: It prevents accidental class name mistakes, like double spaces or missing spaces, which can happen when managing the class attribute as a string.

#### Example Usage
```javascript
const button = document.querySelector('button');

// Adding a class
button.classList.add('active');

// Removing a class
button.classList.remove('inactive');

// Toggling a class
button.classList.toggle('highlight');

// Checking if a class exists
if (button.classList.contains('highlight')) {
  console.log('Button is highlighted.');
}

// Replacing a class
button.classList.replace('highlight', 'dim');
```
# `Get attribute` & `Set attribute`
 Example:
 ```JS
// href
let href = document.querySelector("a").href;
const input = document.querySelector("input");

href = "www.google.com";
// console.log(href);
// console.log(input.value);
// console.log(input.type);

// getAttribute(attrName)
console.log(input.getAttribute("type"));
// setAttribute(attrName, value)
// console.log((input.value = "BYE"));
// console.log((input.placeholder = "provide pass"));

input.setAttribute("placeholder", "Password");
input.setAttribute("type", "password");
```
# Siblings

#### What are Siblings?

- **Siblings**:
  - Sibling elements are elements that have the same parent. For example, in a list (`<ul>`), each `<li>` is a sibling to the others because they share the same `<ul>` parent.

#### Key Properties and Methods for Working with Siblings

1. **`nextElementSibling`**
   - **Description**: 
     - This property returns the next sibling element that follows the current element in the DOM tree. If there is no next sibling, it returns `null`.
   - **Use Case**: 
     - Useful for moving to the next sibling element when you are processing or navigating elements in sequence.
   - **Syntax**:
     ```javascript
     let nextSibling = element.nextElementSibling;
     ```
   - **Example**:
     ```javascript
     let firstLi = document.querySelector("li");
     console.log(firstLi.nextElementSibling); // Logs the next <li> sibling after the first <li>
     ```

2. **`previousElementSibling`**
   - **Description**: 
     - This property returns the previous sibling element that precedes the current element in the DOM tree. If there is no previous sibling, it returns `null`.
   - **Use Case**: 
     - Useful for moving to the previous sibling element when you need to navigate backward in a sequence.
   - **Syntax**:
     ```javascript
     let prevSibling = element.previousElementSibling;
     ```
   - **Example**:
     ```javascript
     let fourthLi = document.querySelector(".fourth");
     console.log(fourthLi.previousElementSibling.innerText); // Logs the text of the sibling before the fourth <li>
     ```

3. **`parentElement` and `children`**
   - **Description**: 
     - While not directly related to sibling navigation, understanding how to access a parent element and its children is crucial. Siblings share the same parent, so you can often retrieve siblings by first getting the parent and then accessing its children.
   - **Example**:
     ```javascript
     let parent = firstLi.parentElement;
     let allSiblings = parent.children; // `allSiblings` is a collection of all sibling elements
     ```
   - **Use Case**: 
     - Useful when you want to work with all siblings at once or iterate over them.

#### Practical Examples

```javascript
// Select the first <li> element in a list
let firstLi = document.querySelector("li");

// Log the first <li> element
console.log(firstLi);

// Navigate to and log the next siblings
console.log(firstLi.nextElementSibling); // Logs the second <li> (next sibling)
console.log(firstLi.nextElementSibling.nextElementSibling); // Logs the third <li>

// Navigate to and log the previous sibling
let fourthLi = document.querySelector(".fourth");
console.log(fourthLi.previousElementSibling.innerText); // Logs the text of the third <li> (previous sibling)
```

#### Summary

- **`nextElementSibling`**: Use this to move to the next sibling in the DOM tree.
- **`previousElementSibling`**: Use this to move to the previous sibling in the DOM tree.
- **Parent-child relationship**: Often, you can retrieve all siblings by accessing the parent element and iterating through its children.

# Understanding the `style` Property in JavaScript

The `style` property in JavaScript allows you to manipulate the inline styles of an HTML element directly from your scripts. This is useful for dynamically changing the appearance of elements in response to user interactions, animations, or other events.

#### Key Concepts

1. **What is the `style` Property?**
   - **Description**: 
     - The `style` property is an object that contains the inline CSS styles applied to a particular HTML element. It allows you to get and set the CSS properties of an element directly.
   - **Inline Styles**: 
     - These are styles applied directly to an element using the `style` attribute in HTML, like `<div style="color: red;"></div>`.
   - **Syntax**:
     ```javascript
     element.style.propertyName = value;
     ```

2. **Setting Styles**
   - **Description**: 
     - You can set CSS properties directly by accessing them through the `style` object. The properties are written in camelCase (e.g., `backgroundColor` instead of `background-color`).
   - **Example**:
     ```javascript
     let div = document.querySelector("div");

     // Set the background color to blue
     div.style.backgroundColor = "blue";

     // Set the font size to 20 pixels
     div.style.fontSize = "20px";

     // Set the display to block
     div.style.display = "block";
     ```

3. **Getting Styles**
   - **Description**: 
     - You can retrieve the current value of a style property using the `style` object. However, this will only give you the inline styles, not those applied via external or internal CSS.
   - **Example**:
     ```javascript
     let div = document.querySelector("div");

     // Get the current background color
     console.log(div.style.backgroundColor); // Logs "blue" if set previously
     ```

4. **Removing Styles**
   - **Description**: 
     - To remove an inline style, set the property value to an empty string.
   - **Example**:
     ```javascript
     div.style.backgroundColor = ""; // Removes the background color style
     ```

5. **Handling Complex Styles**
   - **Hyphenated CSS Properties**: 
     - In JavaScript, hyphenated CSS properties are written in camelCase. For example:
     - `background-color` becomes `backgroundColor`.
     - `font-size` becomes `fontSize`.
   - **Example**:
     ```javascript
     let paragraph = document.querySelector("p");

     // Set multiple styles
     paragraph.style.marginTop = "10px";
     paragraph.style.borderBottom = "2px solid black";
     ```

6. **Using `cssText` for Multiple Styles**
   - **Description**: 
     - The `cssText` property allows you to set multiple CSS properties at once by assigning a complete string of CSS styles.
   - **Example**:
     ```javascript
     let div = document.querySelector("div");

     // Apply multiple styles at once
     div.style.cssText = "color: white; background-color: black; padding: 10px;";
     ```

7. **Limitations of the `style` Property**
   - **Inline Styles Only**: 
     - The `style` property only accesses and modifies inline styles. It does not affect styles applied via external or internal CSS files.
   - **Computed Styles**: 
     - To get the final, computed styles (including those from external stylesheets), you should use `getComputedStyle()`.

8. **Using `getComputedStyle()`**
   - **Description**: 
     - `getComputedStyle()` is a method that returns the computed style of an element, which includes all styles applied to the element (inline, internal, and external).
   - **Example**:
     ```javascript
     let computedStyle = getComputedStyle(div);

     // Get the computed background color
     console.log(computedStyle.backgroundColor); // Logs the final background color applied to the element
     ```

#### Practical Example

```javascript
// Select an element
let box = document.querySelector(".box");

// Set inline styles
box.style.width = "200px";
box.style.height = "200px";
box.style.backgroundColor = "green";

// Get the inline style
console.log(box.style.backgroundColor); // Logs "green"

// Remove the inline style
box.style.backgroundColor = "";

// Use cssText to set multiple styles
box.style.cssText = "border: 2px solid black; padding: 10px;";

// Get computed style
let computedStyle = getComputedStyle(box);
console.log(computedStyle.border); // Logs the final computed border style
```

# DOM Manipulation Methods: `createElement`, `append`, `prepend`, `insertAdjacentElement`, `removeChild`, `remove`, `insertBefore`

#### 1. **`document.createElement()`**

- **Description**: 
  - Creates a new HTML element specified by the tag name you provide.
- **Syntax**: 
  ```javascript
  let element = document.createElement('tagName');
  ```
- **Example**:
  ```javascript
  let newDiv = document.createElement('div');
  newDiv.textContent = 'Hello, World!';
  ```

#### 2. **`append()`**

- **Description**: 
  - Inserts a node or text string as the last child of a parent element. It can take multiple arguments.
  - It does not return the inserted node, and it allows for appending both DOM nodes and text content.
- **Syntax**: 
  ```javascript
  parentElement.append(childElement);
  ```
- **Example**:
  ```javascript
  let parent = document.getElementById('parent');
  let newDiv = document.createElement('div');
  newDiv.textContent = 'This is a new div';
  parent.append(newDiv);
  ```

#### 3. **`prepend()`**

- **Description**: 
  - Inserts a node or text string as the first child of a parent element. It can take multiple arguments.
  - Like `append()`, it allows for adding both elements and text.
- **Syntax**: 
  ```javascript
  parentElement.prepend(childElement);
  ```
- **Example**:
  ```javascript
  let parent = document.getElementById('parent');
  let newDiv = document.createElement('div');
  newDiv.textContent = 'This is a new div at the start';
  parent.prepend(newDiv);
  ```

#### 4. **`insertAdjacentElement()`**

- **Description**: 
  - Inserts a new element into the DOM at a specified position relative to an existing element.
- **Positions**:
  - `'beforebegin'`: Before the target element itself.
  - `'afterbegin'`: Just inside the target element, before its first child.
  - `'beforeend'`: Just inside the target element, after its last child.
  - `'afterend'`: After the target element itself.
- **Syntax**: 
  ```javascript
  targetElement.insertAdjacentElement(position, newElement);
  ```
- **Example**:
  ```javascript
  let referenceElement = document.getElementById('reference');
  let newDiv = document.createElement('div');
  newDiv.textContent = 'Inserted adjacent to reference element';
  referenceElement.insertAdjacentElement('afterend', newDiv);
  ```

#### 5. **`removeChild()`**

- **Description**: 
  - Removes a specified child node from the DOM. You must call this method on the parent node and pass in the child node to be removed.
- **Syntax**: 
  ```javascript
  parentElement.removeChild(childElement);
  ```
- **Example**:
  ```javascript
  let parent = document.getElementById('parent');
  let child = document.getElementById('child');
  parent.removeChild(child);
  ```

#### 6. **`remove()`**

- **Description**: 
  - Removes the element from the DOM. Unlike `removeChild()`, it is called directly on the element to be removed.
- **Syntax**: 
  ```javascript
  element.remove();
  ```
- **Example**:
  ```javascript
  let element = document.getElementById('elementToRemove');
  element.remove();
  ```

#### 7. **`insertBefore()`**

- **Description**: 
  - Inserts a new node before an existing child of a specified parent node. You specify both the new node and the reference node (the node before which the new node should be inserted).
- **Syntax**: 
  ```javascript
  parentElement.insertBefore(newElement, referenceElement);
  ```
- **Example**:
  ```javascript
  let parent = document.getElementById('parent');
  let newElement = document.createElement('div');
  newElement.textContent = 'Inserted before the reference element';
  let referenceElement = document.getElementById('referenceElement');
  parent.insertBefore(newElement, referenceElement);
  ```

### Summary

- **`createElement()`**: Creates a new HTML element.
- **`append()`**: Adds elements or text to the end of a parent element.
- **`prepend()`**: Adds elements or text to the beginning of a parent element.
- **`insertAdjacentElement()`**: Inserts an element relative to another element’s position.
- **`removeChild()`**: Removes a child element from its parent.
- **`remove()`**: Directly removes an element from the DOM.
- **`insertBefore()`**: Inserts a new element before a specified existing element within a parent.

# Adding Events in JavaScript

Events are actions or occurrences that happen in the browser, such as clicks, key presses, or page loads. In JavaScript, you can attach event handlers to elements so that when these events occur, specific functions (called event handlers or event listeners) are executed. Here's how you can add events to elements:

#### 1. **Using `addEventListener()`**

- **Description**:
  - The `addEventListener()` method is the most flexible and recommended way to add events to elements. It allows you to attach multiple event handlers to the same event type on the same element.

- **Syntax**:
  ```javascript
  element.addEventListener('eventType', eventHandler);
  ```
  - `eventType`: The type of the event (e.g., 'click', 'mouseover', 'keydown').
  - `eventHandler`: The function that should be executed when the event occurs.

- **Example**:
  ```javascript
  let button = document.getElementById('myButton');
  button.addEventListener('click', function() {
    alert('Button was clicked!');
  });
  ```

- **Removing Event Listeners**:
  - You can remove an event listener using `removeEventListener()`. This requires passing the same function reference that was used when adding the listener.
  - **Example**:
    ```javascript
    function handleClick() {
      alert('Button was clicked!');
    }
    button.addEventListener('click', handleClick);
    button.removeEventListener('click', handleClick); // Removes the event listener
    ```

#### 2. **Using Inline Event Handlers (HTML Attributes)**

- **Description**:
  - You can directly attach events in your HTML code using attributes like `onclick`, `onmouseover`, etc. However, this method is generally discouraged for larger projects because it mixes HTML and JavaScript and can make code harder to maintain.

- **Example**:
  ```html
  <button id="myButton" onclick="alert('Button was clicked!')">Click Me</button>
  ```

#### 3. **Using DOM Element Properties**

- **Description**:
  - You can also assign an event handler directly to a DOM element's property (like `onclick`, `onmouseover`, etc.). This method is simple but only allows one event handler per event type per element.

- **Syntax**:
  ```javascript
  element.eventType = eventHandler;
  ```
  - `eventType`: The event type, written as a property (e.g., `onclick`, `onmouseover`).
  - `eventHandler`: The function to execute when the event occurs.

- **Example**:
  ```javascript
  let button = document.getElementById('myButton');
  button.onclick = function() {
    alert('Button was clicked!');
  };
  ```

- **Note**:
  - Assigning an event handler this way will overwrite any existing event handler for the same event type on that element.

#### 4. **Event Object**

- **Description**:
  - When an event occurs, an event object is created and passed to the event handler. This object contains useful information about the event, such as the target element, the type of event, mouse coordinates, key presses, and more.

- **Example**:
  ```javascript
  button.addEventListener('click', function(event) {
    console.log('Clicked element:', event.target);
    console.log('Event type:', event.type);
  });
  ```

#### 5. **Event Delegation**

- **Description**:
  - Event delegation is a technique where a single event listener is added to a parent element, and it handles events for its child elements. This is useful when you have many child elements that need the same event handler or when child elements are dynamically added.

- **Example**:
  ```javascript
  let parent = document.getElementById('parentElement');
  parent.addEventListener('click', function(event) {
    if (event.target.matches('.child')) {
      alert('A child element was clicked!');
    }
  });
  ```

- **Advantages**:
  - Fewer event listeners need to be attached, improving performance.
  - Works well with dynamically added elements.

#### 6. **Preventing Default Behavior**

- **Description**:
  - Sometimes, you want to prevent the default behavior of an element (like a link navigating to a new page). You can do this using `event.preventDefault()`.

- **Example**:
  ```javascript
  let link = document.getElementById('myLink');
  link.addEventListener('click', function(event) {
    event.preventDefault(); // Prevents the link from following its href
    alert('Default action prevented!');
  });
  ```

#### 7. **Stopping Event Propagation**

- **Description**:
  - Events in JavaScript propagate, meaning they move from the target element up through the DOM tree (known as bubbling). You can stop this propagation using `event.stopPropagation()`.

- **Example**:
  ```javascript
  let child = document.getElementById('childElement');
  child.addEventListener('click', function(event) {
    event.stopPropagation(); // Stops the event from bubbling up to parent elements
    alert('Click event stopped at child element!');
  });
  ```

### Summary

- **`addEventListener()`**: The most flexible and recommended way to add event listeners to elements.
- **Inline Event Handlers**: Simple but not recommended for large projects.
- **Element Properties**: Another way to add events, but only one handler per event type.
- **Event Object**: Provides information about the event and allows you to control event behavior.
- **Event Delegation**: Efficient way to manage events for multiple child elements.
- **`preventDefault()`**: Prevents the default action associated with an event.
- **`stopPropagation()`**: Stops the event from bubbling up the DOM tree.

# Mouse Events in JavaScript

Mouse events are a core part of making web pages interactive. These events are triggered by actions involving the mouse, such as clicks, movements, and scrolls. JavaScript provides several built-in mouse events that you can use to respond to user actions.

#### Common Mouse Events

1. **`click`**
   - **Description**: Triggered when the user clicks on an element (typically with the left mouse button).
   - **Use Case**: Used to execute a function when an element is clicked.
   - **Example**:
     ```javascript
     const button = document.getElementById('myButton');
     button.addEventListener('click', function() {
       alert('Button clicked!');
     });
     ```

2. **`dblclick`**
   - **Description**: Triggered when the user double-clicks on an element.
   - **Use Case**: Used to trigger actions that should only happen after a double click.
   - **Example**:
     ```javascript
     const box = document.getElementById('myBox');
     box.addEventListener('dblclick', function() {
       alert('Box double-clicked!');
     });
     ```

3. **`mousedown`**
   - **Description**: Triggered when the user presses down on a mouse button.
   - **Use Case**: Useful for detecting the start of a click or drag operation.
   - **Example**:
     ```javascript
     const div = document.getElementById('myDiv');
     div.addEventListener('mousedown', function() {
       console.log('Mouse button pressed down on div');
     });
     ```

4. **`mouseup`**
   - **Description**: Triggered when the user releases a mouse button.
   - **Use Case**: Often used together with `mousedown` to detect a complete click or drag operation.
   - **Example**:
     ```javascript
     const div = document.getElementById('myDiv');
     div.addEventListener('mouseup', function() {
       console.log('Mouse button released on div');
     });
     ```

5. **`mousemove`**
   - **Description**: Triggered when the mouse pointer moves over an element.
   - **Use Case**: Useful for tracking the mouse's position, creating drag-and-drop interfaces, or custom cursor effects.
   - **Example**:
     ```javascript
     const div = document.getElementById('myDiv');
     div.addEventListener('mousemove', function(event) {
       console.log(`Mouse moved: X=${event.clientX}, Y=${event.clientY}`);
     });
     ```

6. **`mouseenter`**
   - **Description**: Triggered when the mouse pointer enters the boundaries of an element.
   - **Use Case**: Used for hover effects or when you want to detect when the mouse first enters an element.
   - **Example**:
     ```javascript
     const div = document.getElementById('myDiv');
     div.addEventListener('mouseenter', function() {
       div.style.backgroundColor = 'yellow';
     });
     ```

7. **`mouseleave`**
   - **Description**: Triggered when the mouse pointer leaves the boundaries of an element.
   - **Use Case**: Used to reset or remove hover effects.
   - **Example**:
     ```javascript
     const div = document.getElementById('myDiv');
     div.addEventListener('mouseleave', function() {
       div.style.backgroundColor = '';
     });
     ```

8. **`mouseover`**
   - **Description**: Similar to `mouseenter`, but `mouseover` also triggers when the mouse enters child elements.
   - **Use Case**: Often used for hover effects that need to include child elements.
   - **Example**:
     ```javascript
     const div = document.getElementById('myDiv');
     div.addEventListener('mouseover', function() {
       div.style.borderColor = 'red';
     });
     ```

9. **`mouseout`**
   - **Description**: Similar to `mouseleave`, but `mouseout` triggers when the mouse leaves the element or any of its children.
   - **Use Case**: Used to handle hover effects that involve both an element and its children.
   - **Example**:
     ```javascript
     const div = document.getElementById('myDiv');
     div.addEventListener('mouseout', function() {
       div.style.borderColor = '';
     });
     ```

10. **`contextmenu`**
    - **Description**: Triggered when the user right-clicks on an element, which typically opens the context menu.
    - **Use Case**: Can be used to customize the context menu or prevent it from appearing.
    - **Example**:
      ```javascript
      const div = document.getElementById('myDiv');
      div.addEventListener('contextmenu', function(event) {
        event.preventDefault(); // Prevent the default context menu from appearing
        alert('Custom context menu!');
      });
      ```

#### The Event Object

- **Description**: When a mouse event is triggered, an event object is passed to the event handler function. This object contains useful information about the event, such as:
  - `event.type`: The type of event (e.g., 'click').
  - `event.target`: The element that triggered the event.
  - `event.clientX`, `event.clientY`: The mouse pointer's coordinates relative to the viewport.
  - `event.button`: Indicates which mouse button was pressed (0 = left, 1 = middle, 2 = right).

- **Example**:
  ```javascript
  const div = document.getElementById('myDiv');
  div.addEventListener('click', function(event) {
    console.log('Clicked element:', event.target);
    console.log('Mouse position: X=' + event.clientX + ', Y=' + event.clientY);
  });
  ```

#### Event Propagation and Handling

- **Event Propagation**: Mouse events propagate through the DOM in three phases: capturing phase, target phase, and bubbling phase. By default, events bubble up from the target element to the root.

- **`stopPropagation()`**: Stops the event from propagating further up or down the DOM tree.
  - **Example**:
    ```javascript
    const button = document.getElementById('myButton');
    button.addEventListener('click', function(event) {
      event.stopPropagation(); // Prevents the event from reaching parent elements
      alert('Button clicked without bubbling');
    });
    ```

- **`preventDefault()`**: Prevents the default action associated with the event (e.g., preventing a link from being followed).
  - **Example**:
    ```javascript
    const link = document.getElementById('myLink');
    link.addEventListener('click', function(event) {
      event.preventDefault(); // Prevent the link from navigating
      alert('Link click prevented!');
    });
    ```

### Summary

- **Mouse Events**: Include events like `click`, `dblclick`, `mousedown`, `mouseup`, `mousemove`, `mouseenter`, `mouseleave`, `mouseover`, `mouseout`, and `contextmenu`.
- **Event Object**: Provides details about the event, including the type, target, and mouse position.
- **Event Handling**: You can control event propagation and default behavior using `stopPropagation()` and `preventDefault()`.
- **Use Cases**: Mouse events are used for interactivity, such as handling clicks, implementing drag-and-drop, or customizing context menus.
