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

