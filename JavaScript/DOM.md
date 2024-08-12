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
