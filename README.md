# Objects

## Lesson Objectives

To Understand...

- JS Objects
- Destructuring Objects
- JSON Objects
  - JSON Strings

## Intro

### JS Objects

***Objects* are one of the fundamental data types in JavaScript**. They are used to store and manipulate collections of **data and functions**. An object in JavaScript is defined using a set of key-value pairs, where the key is a string and **the value can be any valid JavaScript data type**, including other `objects`. **Objects** in JavaScript can be created using `object literals`, `constructors`, or the `Object.create()` method.

```js
let person = {
  name: "Jane",
  age: 30,
  address: {
    street: "123 Fake St",
    city: "New York",
    state: "NY"
  },
  sayHello: function() {
      console.log("Hello, my name is " + this.name)
  }
}

console.log(person.name) // Jane
console.log(person.address.city)// New York

// I won't work in JSON
person.sayHello() // Hello, my name is Jane
```

### Destructuring Objects

`Destructuring` in JavaScript is a way to **extract values from objects and arrays into separate variables**. This can make code more concise and readable, especially when working with complex data structures.

To destructure an `object`, we use the curly braces `{}` syntax to specify the variables we want to extract from the `object`, followed by the `object` we want to destructure. **The variables are assigned the values of the corresponding object properties**.

```js
let { name, age } = person;
console.log(name);       // Jane
console.log(age);        // 25

```

We can also destructure nested objects and provide default values for variables that may not exist in the object.

```js
let person = { name: "Jane", age: 25, address: { city: "New York" } };
let { name, age, address: { city = "unknown" } } = person;
console.log(name);       // Jane
console.log(age);        // 25
console.log(city);       // New York
```

### JSON Objects

`JSON`, which stands for `JavaScript Object Notation`, is a lightweight data format used for storing and exchanging **data**. It's designed to be easily read and written by both humans and machines.

Think of JSON like a language that computers can understand. It uses a simple syntax to represent data in a structured way, much like a list of items with their corresponding attributes. For example, a JSON object might represent a person and include attributes such as their name, age, and address.

JSON is often used to exchange data between web servers and clients because it's easy to parse and can be used with many different programming languages. When data is exchanged between two systems using JSON, the data is first converted into a JSON format on one end, then sent across the network, and finally converted back into its original format on the receiving end.

Overall, JSON is a convenient way to store and exchange data, and its simplicity makes it a popular choice for many different applications.

#### JSON Strings

`JSON strings` are **just like regular strings of text**, but they follow a specific format that makes them easy for computers to understand.

Imagine that you're writing a letter to a friend, but instead of writing it in English, you write it in a code that only you and your friend understand. This is similar to how `JSON strings` work. They are written in a code that can be read and understood by computer programs.

`JSON strings` are made up of key-value pairs that represent data. For example, you might have a `JSON string` that represents a `person` and includes `keys` like `name`, `age`, and `address`, with corresponding values for each key, like a `JS Object`.

To create a `JSON string`, *you simply need to follow the correct format*. Each `key-value pair` is separated by a comma, and the entire string is enclosed in curly braces.

```json
// Looks an awful lot like a JS Object 🧐
{
  "name": "Jane",
  "age": 30,
  // notice the quotes on the keys in JSON
  "address": {
    "street": "123 Fake St",
    "city": "New York",
    "state": "NY"
  }
  // we also can't store functions in strings
}
```

> Purely *data* not *functionality*

`JSON strings` are often used for *exchanging data between different systems*, such as between a web server and a client. Because the format is **well-defined and easy to parse**, `JSON strings` can be quickly and easily converted into usable data within a program.

In JavaScript, we can use `JSON Strings` with the built-in `JSON` object.

`JSON` has two main functions

- `JSON.stringify()`
- `JSON.parse()`

`JSON.parse()` allows us to `parse` a `JSON string` into a `JS object` with all the benefits such as *dot notation* and *modification*.

`JSON.stringify()` allows us to turn a `JS object` into a `JSON string`.

When we convert a `JS object` into a `JSON String` we can store this *stringified* object in things like the user's browser where we can normally only store `strings`.


```js
//////////////////////////////////////////////////////
// Declare an Oject in JS
const person = {name: "Jane", age: 25}
// works on JS Object
person.name 
// {name: "Jane", age: 25}.name

//////////////////////////////////////////////////////
// convert a JS object into a JSON String
// Just a normal string '{"name": "Jane", "age": 25}'
// We can convert the userRecord `object` to a 
// string for sending somewhere, whether that 
// is the users browser or a database
const personString = JSON.stringify(person)

// .name doesn't work on strings
personString.name 
// '{"name": "Jane", "age": 25}'.name

//////////////////////////////////////////////////////
// convert a JSON string back into a JS Object
// JS Object {name: "Jane", age: 25}
const personObject = JSON.parse(personString) 

// works again as it's now a JS Object again
personObject.name 
// {name: "Jane", age: 25}.name
```

We can then read such information with `JSON.parse()` when the user returns to the page to say, for example, *restore a saved shopping cart* for them, or to save and restore preferences like dark mode or theme when the page loads.

## Resources

### W3 Schools

- [JavaScript Objects](https://www.w3schools.com/js/js_objects.asp)
- [JavaScript JSON](https://www.w3schools.com/js/js_json.asp)
- [Window localStorage (browser only)](https://www.w3schools.com/jsref/prop_win_localstorage.asp)
> For some reason, this is in React, not JS
- [React ES6 Spread Operator](https://www.w3schools.com/react/react_es6_spread.asp) 

### MDN Docs

- [Spread syntax (...)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax)
- [JSON](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON)
- [Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)
- [Window: localStorage property](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage)