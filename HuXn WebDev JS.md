<h2> START DATE: 15th July 2024</h2>

### basics
```JS
//log --> console.log (shortcut)

let name = "Abhishek";
let whatDoYouWannaBecomeInYourLife = "Programmer";
let gender = "male";
let twitterHandle = "araj5434";

console.log(
  `Hi, my name is ${name}. I want to be a ${whatDoYouWannaBecomeInYourLife} and I am a ${gender}. My Twitter handle is @${twitterHandle}`
);

console.log(name);
console.log(whatDoYouWannaBecomeInYourLife);
console.log(gender);
console.log(twitterHandle);
```

## number primitive type

```JS
/*SHORTCUT KEY
Alt+ ↑ / ↓ = Move line up/down. You can move the line using the arrows without having to erase
Shift+Alt + ↓ / ↑ = Copy line up/down. This will copy the line as many times as you press the arrow. 
Ctrl+Shift+K = Delete line. This will delete the whole line instantly. 
Multi-cursor and selection
Alt+Click = Insert cursor. You can insert the cursor on as many lines at once and write the same thing at the same time on all lines
CTRL+D = Multi-select an element. When you need to change the H3 tags to the H4 tags (all of them) in a file, what will you do? You have to select one H3 tag and use the shortcut. This will find every H3 tag and give you an active cursor for further action.
Ctrl+U = Undo last cursor operation.
Shift+Alt+I = Insert cursor at end of each line selected
Ctrl+L = Select current line. It selects the current line like you would do it with the mouse when wanting to copy and paste something. 

[CTRL SHIFT K] ==> DELETE LINE OF CODE
[ALT SHIFT ARROW] => COPY SAME CODE
*/

//Primitive type #1. Number
/*
let num = 10;
let numfloat = 10.001;
console.log(num);

console.log(typeof numfloat);
console.log(typeof num);
*/

// 1. Create Variable name (firstFavNum) & store your favorite number.
// 2. Create Variable name (secondFavNum) & store your second fav number.
// 3. Add (firstFavNum & secondFavNumber).
// 4. Subtract (firstFavNum & secondFavNumber).
// 5. Multiply (firstFavNum & secondFavNumber).
// 6. Divided (firstFavNum & secondFavNumber).
// 7. Check (firstFavNum Mod secondFavNumber)
// 8. Check the power of (firstFavNum)

let firstFavNum = 20;
let secondFavNum = 10;

let sum = firstFavNum + secondFavNum;
let sub = firstFavNum - secondFavNum;
let multiply = firstFavNum * secondFavNum;
let divide = firstFavNum / secondFavNum;
let mod = firstFavNum % secondFavNum;
let power = firstFavNum ** 2;

console.log(sum);
console.log(sub);
console.log(multiply);
console.log(divide);
console.log(mod);
console.log(power);
```

### Falsy and boolean type

```JS
//Boolean type true || false

let isTrue = true;
console.log(isTrue);
console.log(typeof isTrue);

let num = 10;
console.log(num + undefined); //NaN

/*
falsy value:
--> false
--> null
--> undefined
--> 0
--> -0
--> NaN
--> '',"",``,(empty quotes)
*/

/*
Difference between null and undefined
--> Null is set by the programmer
--> undefined is set by the compiler
*/
```

#### Small problem
```JS

// 1. Create Variable name (isJsProgrammingLanguage) & store true as a value.
// 2. Create variable name (isJsHard) & store false as a value.
// 3. Create variable name (favNumb) & store your favorite number inside.
// 4. Now Add favNumber with the value of undefined.

let isJsProgrammingLanguage = true;
let isJsHard = false;
let favNumb = 5;
console.log(favNumb + undefined); //NaN
console.log(favNumb * isJsHard); //0
console.log(favNumb + isJsProgrammingLanguage); //6
```

## Relational operators
```JS
/* Comparison Operators

--> Relational Operators
    > Greater than
    < Less than
    >= Greater than or equal to
    <= Less than or equal to

--> Equality Operators
    === strict equality (type + value)
    !== strict non-equlaity operators (type + value)
    == loose equality operator (value)
    != loose not equality operator (value)
*/
```
### exercise
```JS
// 1. Create variable name (firstFavNumb) & store your favorite number.
// 2. Create variable name (secondFavNumb) & store second fav Number.
// 3. Check (firstFavNumb is greater then secondFavNumb)
// 4. Check (firstFavNumb is less then secondFavNumb)
// 5. Check (firstFavNumb is greater then & equal to secondFavNumb)
// 6. Check (firstFavNumb is less then & equal to secondFavNumb)
// 7. Check (firstFavNumb is equal to secondFavNumb) using strict equality operator.
// 8. Check (firstFavNumb is equal to secondFavNumb) using loose equality operator.
// 9. Check (firstFavNumb is not equal to secondFavNumb) using strict non-equality operator.
// 10. Check is (firstFavNumb is not equal to secondFavNumb) using loose non-equality operator.

let firstFavNumb = 10;
let secondFavNumb = 5;

console.log(firstFavNumb > secondFavNumb); // true
console.log(firstFavNumb < secondFavNumb); // false
console.log(firstFavNumb >= secondFavNumb); // true
console.log(firstFavNumb <= secondFavNumb); // false
console.log(firstFavNumb === secondFavNumb); // false
console.log(firstFavNumb == secondFavNumb); // false
console.log(firstFavNumb !== secondFavNumb); // true
console.log(firstFavNumb != secondFavNumb); // true
```

## String Type

```JS
let firstName = "Abhishek";
let secondName = "Raj";

// Concatenation using '+' operator
let fullName = firstName + " " + secondName;
console.log(fullName);

// Concatenation using concat
let fullNameConcat = firstName.concat(" ", secondName);
console.log(fullNameConcat);

//Concate through append
/*
    let fullNameAppend = "";
    fullNameAppend += firstName;
    fullNameAppend += " ";
    fullNameAppend += secondName;
    console.log(fullNameAppend);
    */

// firstName += " Appending val";
// console.log(firstName);

// Length
console.log(fullName.length);

// Cases

console.log(firstName.toLowerCase());
console.log(firstName.toUpperCase());

//Slice
console.log(firstName.slice(0, 4));

//Split and Join
console.log(firstName.split("").join(""));

// Includes
console.log(firstName.includes("Abhi"));
console.log(firstName.includes("m"));

//Trim
console.log(" Abhishek".trim());

//Multi line string
let multiLineString = `
Hello,
This is a multi-line
string.
`;

console.log(multiLineString);

let testFirstName = "Abhishek";
let testSecondName = "Kumar";
let fullTestName = `${testFirstName} ${testSecondName} something`;
console.log(fullTestName);
```

### exercise
```JS
// 1. Create variable name (favActorFirstName) & store your fav Actor name.
let favActorFirstName = "Virat";
// 2. Create variable name (favActorLastName) & store the last name of (FA).
let favActorLastName = "Kohli";
// 3. Create variable name (fullName) & concatenate (favActorFirstName, favActorLastName)
let fullNameFavActor = favActorFirstName.concat(" ", favActorLastName);
console.log(fullNameFavActor);
// 4. Create variable name (uppercase) & CAPITALIZE your fav actor name.
let uppercase = fullNameFavActor.toUpperCase();
console.log(uppercase);
// 5. Create a variable name (message) & store `My favorite Actor Is (favActorName) & say something about your fav actor` name should be in UPPERCASE.
let message = `My favorite Actor is ${uppercase} and he is very humble personality`;
console.log(message);
// 6. Now append this message to the (message variable) `his best show is Silicon Valley`.
let updatedMessage = (message += " " + `his best show is Silicon Valley`);

// 7. Now Log your Message.
console.log(updatedMessage);
console.log(message);
```
## Converting String to Number
```JS
//TYPECASTING / conversion

let money = "50";
let money2 = "40";

//Convert string to number

console.log(typeof money);
money = parseInt(money); //1st way of conversion
console.log(money);
console.log(typeof money);

let money3 = +money2; // Second way of conversion
console.log(`Type of money 2 is:  ${typeof money2}`);
console.log(`Type of money 3 is:  ${typeof money3}`);

console.log(
  `This is the 3rd way of converting string into number: just use ${Number(
    money
  )} and then see it's type is ${typeof Number(money)}`
); // 3rd way of conversion

```
## Converting Number to String
```JS
// Convert number to string

let money = 50;
money = money.toString(); //1st way
console.log(money);
console.log(typeof money);

let money2 = 50;

money2 = String(money2); //2nd way

console.log(money2);
console.log(typeof money2);

```

## Converting String to Float or decimal

```JS

//Convert string to decimal

let strMoney = "50.5";
money = parseFloat(strMoney); //1st way
console.log(money);
console.log(typeof money);

let strMoney2 = "50.5";

money2 = Number(strMoney2); //2nd way

console.log(money2);
console.log(typeof money2);
```

## Control Flow
### if else
```JS
//Syntax
/*
if (condition) {...}
else if (condition) {...}
else {...}
*/

let password = 8;

if (password === 8) {
  console.log("Welcome");
} else if (password <= 8) {
  console.log("Password is too short");
} else if (password >= 8) {
  console.log("Too Long Password");
  console.log("Password should be 8 characters");
} else {
  console.log("Please provide a password.");
}

```

### switch statement
```JS
//Syntax
/*
Switch (condition){
case condition:
  action
  break;
default:
  action
}
//Examples
let x = 0;
let bulb;
switch (x) {
  case 0:
    bulb = "Off";
    console.log(bulb);
    break;
  case 1:
    bulb = "On";
    console.log(bulb);
    break;
  default:
    bulb = "Invalid input";
    console.log(bulb);
}
//Example 2
let day = "Monday";
switch (day.toLowerCase()) {
  case "monday":
    console.log("Today is Monday");
    break;
  case "tuesday":
    console.log("Today is Tuesday");
    break;
  case "wednesday":
    console.log("Today is Wednesday");
    break;
  case "thursday":
    console.log("Today is Thursday");
    break;
  case "friday":
    console.log("Today is Friday");
    break;
  case "saturday":
    console.log("Today is saturday");
    break;
  case "sunday":
    console.log("Today is sunday");
    break;
  default:
    console.log("Invalid day");
}
```

### For loop
```JS
//Syntax:
//for (initialization; condition; increment/decrement) {}
/*
Using variable in the console.log
Method 1: console.log("Hello Raj" + " " + i);
Method 2: console.log('Hello Raj',i)\
*/

for (let i = 1; i <= 1000; i = i + 1) {
  console.log("My name is Raj", i);
}

//Nested Loop
for (let i = 1; i <= 5; i++) {
  console.log("----- Outer Loop -----", i);
  //nested Loop
  for (let j = 1; j <= 5; j++) {
    console.log("---------Inner Loop ---------", j);
  }
}
```
### While loop
```JS
//Syntax
/*
while (condition) {
code
}
*/
//Example

let i = 1;
while (i <= 5) {
  console.log("My name is Raj", i);
  i++;
}
//Example 2
let i = 10;
let j = 1;
while (i < 110) {
  console.log("My name is Abhishek", "The value of i is:", i, "and j is:", j);
  i++;
  j++;
}
```
### Do while loop
```JS
let i = 1;
do {
  console.log("My name is Abhishek", i);
  i++;
} while (i <= 5);
```
### Loop through an array
```JS
let arr = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
for (let i = 0; i < arr.length; i++) {
  console.log("Element at index", i, "is", arr[i]);
}
for (let element of arr) {
  console.log("Element is", element);
}
```

### Break and Continue
/*
1. Break: It will stop the loop execution and move to the next statement.
2. Continue: It will skip the current iteration and move to the next iteration.
*/

// Example
let i = 1;
while (i <= 10) {
  if (i === 5) {
    break;
  }
  console.log("My name is Abhishek", i);
  i++;
}

let i = 1;
while (i <= 10) {
if (i === 5) {
  continue;
}
console.log("My name is Abhishek", i);
i++;
}

## Logical operators

### Logical && (AND) Operator
&& (AND) - It will return true if both the conditions are true.
Example:
```JS
const a = true;
const b = false;
const c = 4;

console.log(a && b);
console.log(c > 2 && a > 0); //true
```

### Logical || (OR)
|| (OR) - It will return true if any one of the conditions is true
```JS
const a = true;
const b = false;
const c = 4;

console.log(a || b);
```
### ! (NOT)
! (NOT) - It will return true if the condition is false and vice versa
```JS
const a = true;
 const b = false;
 const c = 4;

 console.log(!a);
 console.log(!b);
 console.log(!c); //false
```
### XOR (exclusive OR)
XOR (exclusive OR) - It will return true if exactly one of the conditions is true
```JS
 // Example:
  const a = true;
  const b = false;
  const c = 4;

  console.log(a ^ b); //true
  console.log(c > 2 ^ a > 0); //true
```
### Ternary Operator
Ternary operator - It is a shorthand for if-else statements.
Syntax: condition ? true : false;
```JS
const a = 10;
  const b = 5;

  const result = a > b ? "a is greater than b" : "b is greater than a";
  console.log(result); //a is greater than b
```

## Array
```JS

const mixedArr = ["string", ["otherarray"], 123, true];
for (i in mixedArr) {
  console.log(mixedArr[i]);
}
```
### Array Methods
| Method     |                                      Description                                       |
| ---------- | :------------------------------------------------------------------------------------: |
| concat()   |                     joins two or more arrays and returns a result                      |
| includes() |                    checks if an array contains a specified element                     |
| push()     |    aads a new element to the end of an array and returns the new length of an array    |
| unshift()  | adds a new element to the beginning of an array and returns the new length of an array |
| pop()      |          removes the last element of an array and returns the removed element          |
| shift()    |         removes the first element of an array and returns the removed element          |
| sort()     |          sorts the elements alphabetically in strings and in ascending order           |
| slice()    |                 selects the part of an array and returns the new array                 |
| splice()   |             removes or replaces existing elements and/or adds new elements             |

**PUSH AND POP METHOD**
-- push used to add element in the end
-- Pop used to remove element from the end of the array. We don't need to provide any parameter to this method

```JS
const fruits = ["Apple", "Mango", "Carrot", "Pineapple"];
console.log(fruits);

fruits.push("Banana");
console.log(fruits);
fruits.pop();
console.log(fruits);
```
**SHIFT UNSHIFT METHOD**
Shift --> Used to remove element from the beginning of an array
Unshif --> Used to add element from the beginning of an array

```JS
const fruits = ["Apple", "Mango", "Carrot", "Pineapple"];
console.log(fruits);

fruits.shift();//remove element in the zero index of the array
console.log(fruits);

fruits.unshift("Orange"); // Add element in the zero index of the array
console.log(fruits);
```

**CONCAT METHOD**
Used to add 2 arrays into one
```JS
const fruits = ["Apple", "Mango", "Carrot", "Pineapple"];
const moreFruits = ["strawberries", "grapefruit"];

const totalFruits = fruits.concat(moreFruits);
console.log(totalFruits);
```
**INCLUDES AND JOIN METHOD**

--> Includes method gives the result in boolean values
--> It validates if the String provided as a part of parameter is in the array or not

--> Join used to make array an string with the delimeter provided in the parameter of the method

```JS
const pl = ["JavaScript", "Golang", "Python", "PHP"];
const numbers = [3, 5, 2, 4, 1];

console.log(pl.includes("Golang")); // Give boolean result as true or false
console.log(pl.join(", ")); // Used to make array to string with a separator

const joins = pl.join(", ");
console.log(typeof joins); //String
```

**SORT REVERSE AND SLICE**
--> Sort used to make the array in order
--> Slice used to slice the array and output the part of it

```JS
const pl = ["JavaScript", "Golang", "Python", "PHP"];
const numbers = [3, 5, 2, 4, 1];

console.log(pl.reverse());
console.log(pl.slice(0, 2));
console.log(numbers.sort());
```

**OBJECT IN JS**
```JS
//OBJECTS
//Syntax
// const objectName = {
// key: value,
// key: value,
// ...
// };

const person = {
  name: "John",
  age: 30,
  city: "New York",
  isMarried: true,
};

const userdetail = {
  user_id: "cdp-2026",
  email: "araj@zetaglobal.com",
  properties: {
    has_active_email: true,
    has_active_phone: false,
    address: {
      street: "123 Main St",
      city: "New York",
      state: "NY",
      zip: "10001",
    },
  },
  contacts: [
    {
      type: "phone",
      contact_value: "234567890",
      status: "active",
    },
    {
      type: "email",
      contact_value: "john@example.com",
      status: "inactive",
    },
  ],
};
//accessing object value

console.log(person.name); //John

console.log(person.age); //30
console.log(person.city); //New York
console.log(person.isMarried); //true

console.log(userdetail["properties"]["address"]["street"]); //123 Main St)

console.log(userdetail.contacts[0].contact_value); //234567890

const arr = [];
console.log(typeof arr); //Object

delete userdetail.email; // Used to delete a property from object
console.log(userdetail);
```

## Functions

A function is a block of code that performs a specific task.
Function makes the code reusable. You can declare it once and use it multiple times.
Function makes the program easier as each small task is divided into a function.
Function increases readability.
DRY - Don't Repeat Yourself
function name(parameterIfAny) {...}

```JS
function sayHello(name) {
  console.log(`Hello ${name}`);
}
// sayHello("Abhishek");

function add(x, y) {
  return x + y;
}
```

### Call Back Function
When we provide function as an argument to other function that function is known as call back function
```Example
function func1(callFunc) {
  name = "Abhishek";
  console.log("This is the execution of function 1");
  callFunc();
}

func1(function () {
  console.log(name);
  console.log(
    `This is the execution of call back function which retrieves data from func1 name var whose value is ${name}`
  );
});
```
Certainly! Here's a detailed note on JSON for your Markdown file:


# JSON (JavaScript Object Notation) Notes

JSON (JavaScript Object Notation) is a lightweight data interchange format that is easy for humans to read and write, and easy for machines to parse and generate. JSON is used primarily to transmit data between a server and web application as text.

## Basic Structure

JSON is built on two structures:
1. A collection of name/value pairs (often realized as an object, hash table, dictionary, or associative array).
2. An ordered list of values (often realized as an array, vector, list, or sequence).

Here is an example of a JSON object:

```json
{
  "name": "Abhishek",
  "work": "BSA",
  "age": 25,
  "email": "araj@zetaglobal.com",
  "hobbies": ["Reading", "Coding"],
  "address": {
    "street": "123 Main St",
    "city": "New York",
    "state": "NY"
  }
}
```

## Working with JSON in JavaScript

### Parsing JSON

To convert a JSON string into a JavaScript object, use `JSON.parse()`.

```javascript
let jsonObjet = `{
  "name": "Abhishek",
  "work": "BSA",
  "age": 25,
  "email": "araj@zetaglobal.com",
  "hobbies": ["Reading", "Coding"],
  "address": {
    "street": "123 Main St",
    "city": "New York",
    "state": "NY"
  }
}`;

let jsonParsed = JSON.parse(jsonObjet);
```

### Checking Data Types

After parsing, you can check the type of the data:

```javascript
console.log(typeof jsonObjet); // string
console.log(typeof jsonParsed); // object
```

### Accessing Data

You can access properties of the parsed object using dot notation or bracket notation.

```javascript
console.log(jsonParsed); // Outputs the entire object
console.log(jsonParsed.address); // Outputs the address object
```

### Stringifying JSON

To convert a JavaScript object into a JSON string, use `JSON.stringify()`.

```javascript
console.log(JSON.stringify(jsonParsed)); // Converts the JavaScript object back to a JSON string
console.log(JSON.stringify(jsonObjet)); // This will still be a string, since jsonObjet is already a JSON string
```

## Important Points to Remember

- JSON keys must be strings wrapped in double quotes.
- JSON values can be strings, numbers, objects, arrays, booleans, or null.
- JSON is commonly used for asynchronous browser/server communication (AJAX).

Certainly! Here's a detailed note on Global and Local Variables in JavaScript for your Markdown file:


# Global and Local Variables in JavaScript

In JavaScript, variables can be declared globally or locally, and understanding the scope of these variables is crucial for writing predictable and maintainable code.

## Global Variables

Global variables are declared outside any function. They have global scope, which means they can be accessed and modified from anywhere in the code.

### Example of Global Variable

```javascript
var value = 5;

function showCallFunc(fc) {
  fc(value);
  console.log(value); // Accesses the global variable
}

showCallFunc(function (value) {
  console.log(value * 2); // Uses the global variable
  value = value * 2; // This reassigns the local parameter 'value', not the global variable
  console.log(value); // Outputs the modified local variable
});

console.log(value); // Outputs the global variable, which remains unchanged
```

Output:
```
10
10
5
5
```

## Local Variables

Local variables are declared within a function (or a block, if using `let` or `const`). They have local scope, which means they can only be accessed within that function or block.

### Example of Local Variable

```javascript
var value = 5;

function showCallFunc(fc) {
  fc(value);
  console.log(value); // Accesses the global variable
}

showCallFunc(function (newVar) {
  newVar = 2; // This is a local variable within the anonymous function
  console.log(newVar * 2); // Outputs 4
  value = value * 2; // Modifies the global variable
  console.log(value); // Outputs the modified global variable
});

console.log(typeof newVar); // Outputs 'undefined' since 'newVar' is local to the function
console.log(value); // Outputs the modified global variable
```

Output:
```
4
10
undefined
10
```

## Key Points to Remember

1. **Global Scope:**
   - Variables declared outside any function are in the global scope.
   - They can be accessed and modified from anywhere in the code.

2. **Local Scope:**
   - Variables declared inside a function are in the local scope.
   - They can only be accessed and modified within that function.

3. **Parameter Variables:**
   - Parameters of a function are also local to that function.
   - Modifying a parameter inside a function does not affect the global variable.

4. **Variable Shadowing:**
   - A local variable can shadow a global variable if they share the same name.
   - Inside the local scope, the local variable takes precedence.

### Example of Variable Shadowing

```javascript
var value = 5;

function showCallFunc(fc) {
  var value = 10; // This 'value' shadows the global 'value'
  fc(value);
  console.log(value); // Outputs the local 'value'
}

showCallFunc(function (value) {
  console.log(value * 2); // Uses the local 'value' from showCallFunc
  value = value * 2;
  console.log(value);
});

console.log(value); // Outputs the global 'value'
```

Output:
```
20
20
10
5
```

# JavaScript Date Operations

JavaScript provides the `Date` object to work with dates and times. Here, we will cover some basic date operations and common pitfalls.

## Creating a Date Object

You can create a `Date` object using the `Date` constructor. There are several ways to create a `Date` object:

### Example

```javascript
const currentDate = new Date(2024, 2, 24, 12, 30, 0, 0);
console.log(currentDate); // Outputs: Sun Mar 24 2024 12:30:00 GMT+0000 (Coordinated Universal Time)
```

The parameters for the `Date` constructor are:
- `year` (required)
- `month` (0-11, where 0 = January and 11 = December)
- `day` (1-31, default is 1)
- `hours` (0-23, default is 0)
- `minutes` (0-59, default is 0)
- `seconds` (0-59, default is 0)
- `milliseconds` (0-999, default is 0)

### Important Note on Months

In JavaScript, months are zero-based. This means:
- January is 0
- February is 1
- March is 2
- ... 
- December is 11

## Getting the Current Date and Time

You can get the current date and time by creating a new `Date` object without any arguments:

```javascript
const date = new Date();
console.log(date); // Outputs the current date and time
```

## Extracting Year and Month

You can extract the year, month, and other parts of the date using various methods:

### Example

```javascript
const date = new Date();
const year = date.getFullYear();
const month = date.getMonth();

console.log(`Year: ${year}`); // Outputs the current year
console.log(`Month: ${month}`); // Outputs the current month (zero-based)
```

### Correcting Month Output

Since the `getMonth()` method returns a zero-based value, you might want to add 1 to get the human-readable month number.

```javascript
console.log(`Month: ${month + 1}`); // Outputs the current month in a human-readable format
```

## Common Date Methods

- `getFullYear()`: Returns the year (e.g., 2024).
- `getMonth()`: Returns the month (0-11).
- `getDate()`: Returns the day of the month (1-31).
- `getHours()`: Returns the hour (0-23).
- `getMinutes()`: Returns the minutes (0-59).
- `getSeconds()`: Returns the seconds (0-59).
- `getMilliseconds()`: Returns the milliseconds (0-999).

### Example

```javascript
const date = new Date();
console.log(`Current Date and Time: ${date}`);
console.log(`Year: ${date.getFullYear()}`);
console.log(`Month: ${date.getMonth() + 1}`); // Adjust for zero-based month
console.log(`Day: ${date.getDate()}`);
console.log(`Hours: ${date.getHours()}`);
console.log(`Minutes: ${date.getMinutes()}`);
console.log(`Seconds: ${date.getSeconds()}`);
console.log(`Milliseconds: ${date.getMilliseconds()}`);
```

## Setting Date and Time

You can also set different parts of the date and time using various methods:

- `setFullYear(year)`: Sets the year.
- `setMonth(month)`: Sets the month (0-11).
- `setDate(day)`: Sets the day of the month (1-31).
- `setHours(hours)`: Sets the hour (0-23).
- `setMinutes(minutes)`: Sets the minutes (0-59).
- `setSeconds(seconds)`: Sets the seconds (0-59).
- `setMilliseconds(milliseconds)`: Sets the milliseconds (0-999).

### Example

```javascript
const date = new Date();
date.setFullYear(2025);
date.setMonth(0); // January
date.setDate(15);
date.setHours(10);
date.setMinutes(30);
date.setSeconds(45);
date.setMilliseconds(500);

console.log(date); // Outputs: Wed Jan 15 2025 10:30:45 GMT+0000 (Coordinated Universal Time)
```

# Date Formatting in JavaScript

JavaScript provides several methods for formatting dates and times, allowing for flexible and locale-sensitive representations.

## Creating a Date Object

First, create a `Date` object to work with:

```javascript
const date = new Date();
console.log(date); // Outputs the current date and time
```

## Formatting Methods

### `toDateString()`

Returns the date portion of the `Date` object as a human-readable string.

```javascript
console.log(date.toDateString()); // Outputs: Mon Jul 29 2024
```

### `toISOString()`

Returns the date and time in ISO 8601 format, which is commonly used in web APIs.

```javascript
console.log(date.toISOString()); // Outputs: 2024-07-29T12:30:00.000Z
```

### `toLocaleString()`

Returns a string with a language-sensitive representation of the date and time.

```javascript
console.log(date.toLocaleString()); // Outputs: 7/29/2024, 12:30:00 PM (format may vary based on locale)
```

### `toUTCString()`

Returns the date and time in UTC (Coordinated Universal Time) format.

```javascript
let utcDate = date.toUTCString();
console.log(utcDate); // Outputs: Mon, 29 Jul 2024 12:30:00 GMT
```

## Manipulating Dates

You can modify the `Date` object using various setter methods. For example, to set the date to the next day:

### Example: Incrementing the Date

```javascript
date.setDate(date.getDate() + 1);
console.log(date); // Outputs the date incremented by one day
```

### Common Formatting Methods

- `toDateString()`: Converts the date portion to a readable string.
- `toTimeString()`: Converts the time portion to a readable string.
- `toISOString()`: Converts the date to ISO 8601 format.
- `toLocaleDateString()`: Converts the date portion to a locale-specific string.
- `toLocaleTimeString()`: Converts the time portion to a locale-specific string.
- `toLocaleString()`: Converts the date and time to a locale-specific string.
- `toUTCString()`: Converts the date to a UTC string.

## Example of Using Various Methods

```javascript
const date = new Date();

console.log("toDateString:", date.toDateString()); // Outputs: Mon Jul 29 2024
console.log("toISOString:", date.toISOString()); // Outputs: 2024-07-29T12:30:00.000Z
console.log("toLocaleString:", date.toLocaleString()); // Outputs: 7/29/2024, 12:30:00 PM
console.log("toUTCString:", date.toUTCString()); // Outputs: Mon, 29 Jul 2024 12:30:00 GMT

// Incrementing the date by one day
date.setDate(date.getDate() + 1);
console.log("Incremented Date:", date.toDateString()); // Outputs the incremented date
```

## Custom Formatting

For custom date formats, you can manually construct the desired format using date methods.

### Example

```javascript
const customDate = new Date();

const year = customDate.getFullYear();
const month = String(customDate.getMonth() + 1).padStart(2, '0'); // Adjust for zero-based month
const day = String(customDate.getDate()).padStart(2, '0');

console.log(`Custom Format: ${year}-${month}-${day}`); // Outputs: 2024-07-29
```

# `setInterval`, `setTimeout`, and `clearInterval`

### `setTimeout`

**Purpose:**  
`setTimeout` is used to execute a function once after a specified number of milliseconds.

**Syntax:**
```javascript
let timeoutId = setTimeout(function, delay, arg1, arg2, ...);
```

- **`function`**: The function to be executed.
- **`delay`**: The time in milliseconds to wait before executing the function.
- **`arg1, arg2, ...`**: Optional arguments to pass to the function when executed.

**Use Cases:**

- Delaying the execution of a piece of code.
- Executing a function once after a delay.
- Scheduling a function to run after a particular event.

**Example:**
```javascript
function greet() {
    console.log('Hello, world!');
}

// Call greet() after 2000 milliseconds (2 seconds)
let timeoutId = setTimeout(greet, 2000);
```

**Canceling a Timeout:**

You can cancel a timeout before it executes using `clearTimeout`.

```javascript
clearTimeout(timeoutId);
```

**Example:**
```javascript
let timeoutId = setTimeout(greet, 2000);

// Cancel the timeout before it executes
clearTimeout(timeoutId);
```

### `setInterval`

**Purpose:**  
`setInterval` is used to repeatedly execute a function at a specified interval (in milliseconds).

**Syntax:**
```javascript
let intervalId = setInterval(function, delay, arg1, arg2, ...);
```

- **`function`**: The function to be executed.
- **`delay`**: The time in milliseconds between executions of the function.
- **`arg1, arg2, ...`**: Optional arguments to pass to the function each time it is executed.

**Use Cases:**

- Creating animations or updates that need to occur repeatedly.
- Polling for data at regular intervals.
- Implementing timers or clocks.

**Example:**
```javascript
function logTime() {
    console.log(new Date().toLocaleTimeString());
}

// Log the current time every second
let intervalId = setInterval(logTime, 1000);
```

**Canceling an Interval:**

You can stop an interval using `clearInterval`.

```javascript
clearInterval(intervalId);
```

**Example:**
```javascript
let count = 0;

function incrementCounter() {
    count++;
    console.log(count);

    if (count >= 5) {
        clearInterval(intervalId);
    }
}

// Increment the counter every second and stop after 5 increments
let intervalId = setInterval(incrementCounter, 1000);
```

### `clearInterval`

**Purpose:**  
`clearInterval` stops a timer that was previously established by calling `setInterval`.

**Syntax:**
```javascript
clearInterval(intervalId);
```

- **`intervalId`**: The identifier of the interval you want to cancel, as returned by `setInterval`.

**Use Cases:**

- Stopping repeated actions once a condition is met.
- Preventing unnecessary executions of code after it is no longer needed.

**Example:**
```javascript
let intervalId = setInterval(() => console.log('Repeating'), 1000);

// Stop the interval after 5 seconds
setTimeout(() => clearInterval(intervalId), 5000);
```

### Summary

- **`setTimeout`** is for running a function once after a delay.
- **`setInterval`** is for running a function repeatedly at set intervals.
- **`clearTimeout`** and **`clearInterval`** are used to cancel scheduled actions.

Additional Examples:
```JS
setTimeout(() => {
  console.log("Hello World! I am testing setTimeout function");
  console.log(`######################################################`);
}, 1000);

let count = 0;

let intervalId = setInterval(() => {
  console.log("This is Abhishek Testing setInterval function");

  count++;
  if (count > 5) {
    clearInterval(intervalId); // Use clearInterval to stop the interval
  }
}, 1000);


//using setTimeout for clearinterval

const intervalId2 = setInterval(function(){
  console.log(`This function is being executed at the interval`)
},1000)

setTimeout(function(){
  clearInterval(intervalId2) // Using setTimeout to stop the interval
}, 5000)
```
