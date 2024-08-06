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
