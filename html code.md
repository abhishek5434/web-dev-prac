# web-development-code
It has all the codes of which are being used in the udemy course.

![image](https://github.com/abhishek5434/web-development-code/assets/86175919/ecdee888-e192-4478-89ad-e157a4c558ec)


## HTML: Hyper Text Markup Language.
-	Hyper Text is mainly hyperlink which redirects us to another page.
-	Markup Language is HTML tags.
 
### The Heading Elements:
-	We only have h1 to h6 heading tag.
-	Don’t have more than h1.
-	We should have all the header.
- Example
```HTML
<h1> Hello World </h1>
```
```txt
- < or > -- It is called angle bracket.
- <h1>-- It is called opening tag.
- </h1> -- It is called closing tag.
```
- You can go to developer.mozilla.org for the documentation of the html elements.
    
### The Paragraph Element
```HTML
<p> This is a paragraph </p>
```
-	We can use www.lipsum.com to get the random paragraph and you can copy paste from there to use in your website. It can look like a real written text.

### Void element
- ``` <hr /> ```
- It gives a horizontal line.
- This can also be written as
```HTML
<hr>
```

### BR Tag
- Break tag
- This can also be written as:
```HTML
<br>
<br />
```

### Unordered List
-	We need to put the items in this as well.
-	This can be used using the <ul> tag </ul>

```HTML
<ul>
<li>Milk</li>
<li>Eggs</li>
<li>Flour</li>
</ul>
```

### Ordered List
 	
-	The ordered list can be written between <ol>
```HTML
<ol>
  <li>Milk</li>
  <li>Eggs</li>
  <li>Flour</li>
</ol>
```

-	Ol in the code refers to ordered list and li refers to line items
Example:
```HTML
<ul>
<li>A</li>
<li>B
    <ol>
        <li>B1</li>
        <li>B2
            <ul>
                <li>B2a
                    <ul>
                        <li>B2aa</li>
                        <li>B2ab</li>
                    </ul>
                </li>
                <li>B2b</li>
                <li>B2c</li>
            </ul>
        </li>
        <li>B3
            <ol>
                <li>B31</li>
                <li>B32</li>
            </ol>
    </ol>
</li>
<li>C</li>
</ul>
```
### HTML attributes

The common form of writing an HTML attributes is : ``` <tag attribute=vale>Content</tag> ```

### Anchor tag
- This tag helps to embbed hyperlink into the webpage.
- The format of writing this is ```<a href = "http://www.google.com"> This is a link of Google </a>```
- In the format you can see the anchor tag starts with ```<a href=``` then takes the link and after the link we close the bracket and then we provide the content which will show in the website and after the content we close the anchor bracket.
- We can also review this website for more HTMl attributes: https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/accesskey
- **Example of anchor tag and attribute:**

```HTML
<ol start="3">
    <li><a href="https://chat.openai.com/">ChatGpt</a></li>
    <li><a href="www.theanalyticsexplorer.com"> The analytics exlorer</a></li>
    <li><a href="https://github.com/">Gith hub</a></li>
    <li><a href="www.claude.ai">Claude</a></li>
    <li><a href="www.geeksforgeeks.com">geeksforgeeks</a></li>
</ol>
```

Result:
<ol start="3">
    <li><a href="https://chat.openai.com/">ChatGpt</a></li>
    <li><a href="www.theanalyticsexplorer.com"> The analytics exlorer</a></li>
    <li><a href="https://github.com/">Gith hub</a></li>
    <li><a href="www.claude.ai">Claude</a></li>
    <li><a href="www.geeksforgeeks.com">geeksforgeeks</a></li>
</ol>

### Image element
- It does not have closing tag and hence it is also a void element
- This is the simple form of code: ```<img src="url" />```
- We can pick the random image from picsum.photos url
- Do use the alt attribute in this img tag since it can help the user who wants to listen the website via reader
- Here is one example:
```HTML
<img src="https://picsum.photos/200" alt="This is just an example" />
```
**Result:**

<img src="https://picsum.photos/200" alt="This is just an example"/>

Simple project using all the above concepts:

```HTML
<h1>It's my birthday today !</h1>
<h2>On the 1st July</h2>
<img src="https://gifocard.com/en/b/03/a/happy-birthday.gif.pagespeed.ce.EFmm7_XCG_.gif" alt="This is birthday cake"/>
<h3>What to bring:</h3>
<ul>
    <li>Baloons</li>
    <li>Cake</li>
    <li>A gift</li>
</ul>

<h3>This is where you need to go</h3>
<a href="https://maps.app.goo.gl/rLruqpyaKND2s5oG7">Google map link</a>
```
Result:
<h1>It's my birthday today !</h1>
<h2>On the 1st July</h2>
<img src="https://gifocard.com/en/b/03/a/happy-birthday.gif.pagespeed.ce.EFmm7_XCG_.gif" alt="This is birthday cake"/>
<h3>What to bring:</h3>
<ul>
    <li>Baloons</li>
    <li>Cake</li>
    <li>A gift</li>
</ul>

<h3>This is where you need to go</h3>
<a href="https://maps.app.goo.gl/rLruqpyaKND2s5oG7">Google map link</a>

### Relative and Absolute path
**Absolute path**
- An absolute path provides the full and exact location of a file or directory from the root directory.
- Example: ```C:\Users\User\Documents\example.txt```

**Relative path**
- A relative path specifies the location of a file or directory in relation to the current working directory.
- It does not start from the root directory; instead, it assumes a starting point and provides a path from that point.
- Relative paths are often more convenient for specifying locations within the same project or directory structure.
- Example 1 showing picking file from the same directory: ```./documents/example.txt```
- Example 2 showing picking file from the different directory: ```../images/picture.jpg```

We can link an url inside a picture like this:
```HTML
<a href="./public/about.html"> <img src="../../Pic with victor.png" alt="My picture with Victor"/></a>
```
### The HTML Boilerplate

```HTML
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Your Page Title</title>
    <!-- Add your additional meta tags, stylesheets, or scripts here -->
</head>

<body>
    <!-- Your content goes here -->
    <h1>Hello, World!</h1>

    <!-- Add your HTML content, such as paragraphs, images, links, etc. -->

    <!-- Add your scripts or additional content at the end of the body if needed -->

</body>

</html>
```

**Created a portfolio website with just the basic HTML code:** https://abhishek5434.github.io/portfolio-html/

# b tag in the html
- It is used to bold the word within any tag
```HTML
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Learning</title>
  </head>
  <body>
    <p>
      Lorem ipsum dolor
      <b>these words will be in bold since it is in b tag</b> sit amet.
    </p>
  </body>
</html>
```
# i tag
Used to italic the word
```HTML
<p>
      Lorem ipsum dolor
      <i>these words will be in italic since it is in i tag</i> sit amet.
    </p>
```
You're absolutely right, I apologize for the mistake in the previous explanation. Here's the corrected information:

# Superscript (sup):
  - Use the `<sup>` tag to make text appear slightly above the line. 
  - This is often used for footnotes or references.
  - Example: Here's the formula for water `H<sup>2</sup>O`.

# Subscript (sub):
  - Use the `<sub>` tag to display text slightly below the line.
  - Subscripts are common in mathematical expressions or chemical formulas.
  - Example: The speed of light is denoted by c<sub>e</sub>.

```HTML
<p>
   CO<sub>2</sub> is called carbon dioxide gas.
   2<sup>2</sup> is equal to 4.
</p>
```

In HTML, forms allow users to interact with your web page by providing information. They act like containers for various input elements where users can enter data. Here's a breakdown with an example:

# Form Element (`<form>`)

This is the foundation for creating a form. It defines the starting and ending points of your form. 

* **Example:**

```html
<form>
  </form>
```

**Input Elements**

Within the `<form>` tags, you place different input elements to collect user data. Here are some common types:

* **Text Input (`<input type="text">`):** This creates a one-line text field where users can type information like names, addresses, etc.

* **Password Input (`<input type="password">`):** Similar to text input, but characters are masked with dots or asterisks for password security.

* **Email Input (`<input type="email">`):** This specifies that the input should be an email address and often triggers keyboard validation for email format.

* **Radio Buttons (`<input type="radio">`):** Used to create a group of options where only one can be selected at a time.

* **Checkboxes (`<input type="checkbox">`):** Allow users to select multiple options from a set.

* **Submit Button (`<input type="submit">`):** This button triggers the form submission process when clicked.

**Example with Useful Inputs:**

```html
<form>
  <label for="name">Name:</label>
  <input type="text" id="name" name="name" required><br>

  <label for="email">Email:</label>
  <input type="email" id="email" name="email" required><br>

  <label for="message">Message:</label>
  <textarea id="message" name="message" rows="5" required></textarea><br>

  <input type="submit" value="Send Message">
</form>
```

This code creates a form with:

* Labels for each input field to guide users.
* Required text and email input fields for user information.
* A large text area for detailed messages.
* A submit button to send the form data.

**Good example of form:**
```HTML
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Learning</title>
  </head>
  <body>
    <form>
        <label for="fname">First name:</label>
        <input type="text" id="fname" name="fname" placeholder="Give First Name"><br><br>
        <label for="lname">Last name:</label>
        <input type="text" id="lname" name="lname" placeholder="Give Last Name"><br><br>
        <input type="submit" value="Submit">
      </form>
  </body>
</html>
```
To Only Select one option from the options
- You need to add name attribute with the same value for the radio options you want to select one
```HTML
<input name= "gender" type="radio">Male
<input name= "gender" type="radio">Female
<input name= "gender" type="radio">Undefined
```

`CTRL + D` : To get more cursor
![image](https://github.com/abhishek5434/web-development-code/assets/86175919/85ec27c9-2ef5-4724-877b-f222fc712819)

# ID vs Class
-> Use id when we need to give style to a unique element. Hence id is unique per element
-> Use class when we have same css for elements
```HTML
<!DOCTYPE html>
<html>
  <head>
    <style>
      .button1 {
        background-color: green;
        color: white;
        padding: 10px;
      }

      .button2 {
        background-color: blue;
        color: white;
        padding: 10px;
      }
    </style>
  </head>
  <body>
    <button class="button1">Click me</button>
    <button class="button1">Submit</button>
    <button class="button2">Another button</button>
    <button class="button2">One Another button</button>
  </body>
</html>
```
