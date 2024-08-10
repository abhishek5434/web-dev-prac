# Loop practice code
```JS
for (let i = 1; i <= 5; i++) {
  console.log(`Hello World! ${i}`);
}

For in loop

let person = {
  name: "Abhishek",
  age: 20,
  gender: "Male",
};
for (let key in person) {
  console.log(`${key} : ${person[key]}`);
}

let persons = ["Abhishek", "Raja", "Avinash", "Rakesh"];
for (let person of persons) {
  console.log(person);
}
for (let index in persons) {
  console.log(`${index}: ${persons[index]}`);
}
```
# For each examples
```JS
let colors = ["teal", "red", "green", "blue", "brown"];
colors.forEach((element) => {
  console.log(element);
});

const words = ["table", "bed", "furniture", "ekectricity"];
const capwords = words.forEach((word, index, arr) => {
  arr[index] = word[0].toUpperCase() + word.substring(1);
});

console.log(words);
// console.log(capwords);

let numbers = [1, 2, 3, 4, 5, 6];
let sum = 0;
const adder = (number) => (sum += number);
numbers.forEach(adder);
console.log(sum);
```
# MAP
```JS
const numbers = [1, 2, 3, 4, 5];
double = numbers.map((number) => number * 2);
console.log(numbers);
console.log(double);

let peoples = [
  { firstName: "John", lastName: "Doe" },
  { firstName: "Abhishek", lastName: "Raj" },
  { firstName: "Rakesh", lastName: "Ranjan" },
  { firstName: "Rajeev", lastName: "Ji" },
];

let names = peoples.map((person) => `${person.firstName} ${person.lastName}`);

console.log(names);
```
# Filter
```JS

let numbers = [10, 20, 30, 15, 60];
const multiply10 = numbers.map((number) => number * 10);
const map15Plus = numbers.filter((number) => number > 15);
console.log(`MAP function: ${multiply10}`);
console.log(`Filter function: ${map15Plus}`);

const computers = [
  { ram: 4, hdd: 100 },
  { ram: 8, hdd: 200 },
  { ram: 16, hdd: 300 },
  { ram: 32, hdd: 400 },
];

let filteredComp = computers.filter((computer) => computer.ram > 16);
let stringFy = JSON.stringify(filteredComp);
console.log(stringFy);
console.log(filteredComp);

const ages = [32, 33, 16, 15, 40];
function checkAdults(age) {
  return age >= 18;
}

const adults = ages.filter(checkAdults);
console.log(adults);
```
# FIND
```JS
let words = [
  "Hello",
  "High Standard",
  "Learning",
  "Advanced",
  "Programming",
  "Development",
  "JavaScript",
  "HTML",
  "CSS",
  "Bootstrap",
  "React",
  "number",
];

let filterWords = words.filter((word) => word.length > 6);
console.log(filterWords);
let findWords = words.find((word) => word.length > 6);
console.log(findWords);

let products = [
  { name: "Checkers", category: "Toys" },
  { name: "Harry Potter", category: "Books" },
  { name: "iPhone", category: "Electronics" },
  { name: "Learn PHP", category: "Books" },
];

let proBook = products.find((product) => product.category === "Books");
console.log(proBook);
```
