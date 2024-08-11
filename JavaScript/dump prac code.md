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
# Reduce Method
```JS
//REDUCE METHOD

let str = ["one", "two", "three", "four", "five", "six"];
let addStr = str.reduce((allstr, strval) => allstr + " " + strval, "");
console.log(addStr);

// console.log(addNum);
let num = [1, 2, 3, 4, 5, 6];
let addNum = num.reduce((all, val) => {
  console.log(`Total: ${all}, Current Value: ${val}`);
  return all + val; // Return the updated accumulator
}, 0);

console.log(`Final Sum: ${addNum}`);

// Example 3
const words = [
  "apple",
  "banana",
  "orange",
  "banana",
  "apple",
  "orange",
  "apple",
  "grape",
];

const wordFrequency = words.reduce((frequencyMap, word) => {
  frequencyMap[word] = (frequencyMap[word] || 0) + 1;
  return frequencyMap;
}, {});

console.log(wordFrequency);
console.log("Jai shree Ram");
```
# Map
```JS
let map = new Map();

map.set("name", "Abhishek");
map.set("age", 19);
map.set("gender", "Male");
console.log(map);
for (let [key, value] of map) {
  console.log(key, ":", value);
}

// Map

let newMap = new Map([
  ["a", 1],
  ["b", 2],
  ["c", 3],
]);
// newMap.set()

console.log(newMap);
console.log(newMap.get("a"));
console.log(newMap.size);
newMap.delete("b");
console.log(newMap.size);
```
# SET
```JS
const initialValues = [1, 2, 3, 4, 1, 4, 5, 6];
const mySet = new Set(initialValues);
mySet.add("apple");
mySet.add("banana");
mySet.add("apple");
mySet.add("mango");
mySet.add("apple");
mySet.add("apple");
console.log(mySet);

console.log(mySet.has("apple"));
console.log(mySet.has("Abhishek"));
mySet.delete("apple");
console.log(mySet);
// mySet.clear();
console.log(mySet);

for (let item of mySet) {
  console.log(item);
}
```
