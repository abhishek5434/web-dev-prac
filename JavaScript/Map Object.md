# Map
### Overview of `Map`

A `Map` is a collection of key-value pairs where both keys and values can be of any data type. It is similar to an object, but it provides more functionality and is often more suitable for certain use cases.

### Key Characteristics of `Map`

- **Key Flexibility**: Unlike objects, keys in a `Map` can be of any type, including objects, functions, and primitive values.
- **Insertion Order**: Iterating over a `Map` follows the insertion order of the elements.
- **Size Property**: The size of a `Map` can be easily retrieved using the `size` property.
- **Iterable**: `Map` is iterable, allowing it to be looped through directly with `for...of`.

### Creating a `Map`

```javascript
let map = new Map();
```

### Methods of `Map`

#### 1. `map.set(key, value)`

Adds or updates an element with the specified key and value to the `Map`.

**Example:**

```javascript
let map = new Map();
map.set('name', 'Alice');
map.set('age', 30);

console.log(map); // Map(2) { 'name' => 'Alice', 'age' => 30 }
```

#### 2. `map.get(key)`

Returns the value associated with the specified key. If the key does not exist, `undefined` is returned.

**Example:**

```javascript
console.log(map.get('name')); // Output: Alice
console.log(map.get('height')); // Output: undefined
```

#### 3. `map.has(key)`

Returns a boolean indicating whether the `Map` contains an element with the specified key.

**Example:**

```javascript
console.log(map.has('age')); // Output: true
console.log(map.has('height')); // Output: false
```

#### 4. `map.delete(key)`

Removes the specified element from the `Map` by key. Returns `true` if an element was successfully removed, otherwise `false`.

**Example:**

```javascript
map.delete('age');
console.log(map.has('age')); // Output: false
```

#### 5. `map.clear()`

Removes all elements from the `Map`.

**Example:**

```javascript
map.clear();
console.log(map.size); // Output: 0
```

#### 6. `map.size`

Returns the number of key-value pairs in the `Map`.

**Example:**

```javascript
let map = new Map([['a', 1], ['b', 2]]);
console.log(map.size); // Output: 2
```

### Iterating Over a `Map`

You can iterate over a `Map` using several methods:

#### Using `for...of`

```javascript
let map = new Map([['a', 1], ['b', 2], ['c', 3]]);

for (let [key, value] of map) {
    console.log(`${key}: ${value}`);
}
// Output:
// a: 1
// b: 2
// c: 3
```

#### Using `map.forEach()`

```javascript
map.forEach((value, key) => {
    console.log(`${key}: ${value}`);
});
// Output:
// a: 1
// b: 2
// c: 3
```

#### Iterating Keys and Values Separately

- **Keys**: `map.keys()`
- **Values**: `map.values()`
- **Entries**: `map.entries()`

```javascript
for (let key of map.keys()) {
    console.log(key); // Output: a b c
}

for (let value of map.values()) {
    console.log(value); // Output: 1 2 3
}

for (let [key, value] of map.entries()) {
    console.log(`${key}: ${value}`);
}
// Output:
// a: 1
// b: 2
// c: 3
```

### Use Cases for `Map`

- **Complex Key Types**: When you need keys other than strings, such as objects or functions.
- **Preserved Order**: When you need to maintain the order of elements as they are added.
- **Efficiency**: Operations on `Map` (such as insertion, deletion, and retrieval) generally have better performance characteristics than similar operations on objects.

