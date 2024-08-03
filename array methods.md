# Array

1. Create array name (favSingers) Store 3 favorite singers.
2. log the first singer in that array.
3. Create array name (favNumbers) & store 4 fav Numbers.
4. Create array name (mixedArr) store ["string", ["otherarray"], 123, true]
5. Now Access each item in that array by using [] notation.

const favSingers = ["King", "Honey Singh", "Kaka"];
console.log(favSingers[0]);

## ARRAY METHODS

### `CONCAT()`

const favNumbers = [1, 2, 3, 4, 5];
const favNumbers2 = [6, 7, 8, 9, 10];
console.log(favNumbers.concat(favNumbers2));

### `JOIN()`

console.log(favNumbers.join(", "));

### `POP()`

console.log(favNumbers.pop()); // remove last element and return it

console.log(favNumbers);

### `SHIFT()`

console.log(favNumbers.shift()); // remove first element and return it

console.log(favNumbers);

### `UNSHIFT()`

console.log(favNumbers.unshift(0)); // add element at the beginning

console.log(favNumbers);

### `SPLICE()`

console.log(favNumbers.splice(2, 0, 6, 7)); // remove element from index 2 and add new elements

console.log(favNumbers);

### `REVERSE()`

console.log(favNumbers.reverse());

### `SORT()`

console.log(favNumbers.sort((a, b) => a - b)); // sort in ascending order

console.log(favNumbers);

### `forEach()`

favNumbers.forEach((number, index) => {
  console.log(`Number at index ${index} is ${number}`);
});

### `MAP()`

const doubledNumbers = favNumbers.map((number) => number * 2);

console.log(doubledNumbers);

### `FILTER()`

const evenNumbers = favNumbers.filter((number) => number % 2 === 0);

console.log(evenNumbers);

### `REDUCE()`

const sum = favNumbers.reduce(
  (accumulator, currentValue) => accumulator + currentValue,
  0
);
