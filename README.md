# modern-js-es6-es7-es8
This document will teach you the most modern features of JavaScript, also known as ES6, ES7, ES8

## Template Literals
Strings historically in JS has been a second class citizen, haven't got much love in comparisson with other programming languages. Let's take an example:

#### The good old days:
```javascript
let firstName = 'John';
let lastName = 'Doe';

const fullName = firstName + ' ' + lastName;

console.log(fullName); // Output: John Doe
```

So this gets very long and very ugly, but template literals allow us to use back ticks and pass in our values.

#### Modern JavaScript:
```javascript
let firstName = 'John';
let lastName = 'Doe';
let numOne = 17;
let numTwo = 30;

const fullName = `${firstName} ${lastName} ${numOne + numTwo}`;

console.log(fullName); // Output: John Doe 47
```

Multiline string, example

#### The good old days:
```javascript
const helloWorld = 'Hello \n' + 'world!';

console.log(helloWorld); 
/*Output:
Hello
world!
*/
```

#### Modern JavaScript:
```javascript
let hello = 'Hello';
let world = 'world!';

const greeting = `${hello}
${world}`;

console.log(greeting);
/*Output:
Hello
world!
*/
```

## Destructuring Objects
One of the coolest additions to the JS programming language has been destructuring objects, So let's take the example bellow:

```javascript
const myAddress = {
    firstName: 'John',
    lastName: 'Doe',
    city: 'Boston',
    state: 'Massachusetts',
    zipCode: '83301'
}

const {firstName, lastName} = myAddress;

console.log(`${firstName} ${lastName}`); // Output: John Doe
```

Let's say we want to reassign the value here and take this a little bit further:

```javascript
const myAddress = {
    firstName: 'John',
    lastName: 'Doe',
    city: 'Boston',
    state: 'Massachusetts',
    zipCode: '83301'
}

const {firstName: fn, lastName: ln} = myAddress;

console.log(`${fn} ${ln}`); // Output: John Doe
```

## Destructuring Arrays
Destructuring arrays has been another great feature that has been added to JS and is very similar to how we distructed objects above, so let's take an example.

```javascript
let aboutMe = ['John', 'Doe', 'USA'];

// let's transform the above, into something like this:

let [firstName, lastName] = ['John', 'Doe', 'USA'];

console.log(firstName, lastName); // Output: John Doe

// let's say we want to overwrite the value
lastName = 'Bush';

console.log(firstName, lastName); // Output: John Bush
```

## Object Literal
If you have noticed modern JS has put a special importance on writing less code, while still being readable and maintainable. Object Literal is nor difference here.

```javascript
function addressFunc (city, state) {
    const newAddress = {newCity: city, newState: state};

    console.log(newAddress);
}
addressFunc('New Jersey', 'New York'); // Output: {newCity: "New Jersey", newState: "New York"}
```
However object literals give us the ability to, if these keys are the same as the values that they are passing it, we don't have to actually set it, it's going to make the assumptons it self.

```javascript
function addressFunc (city, state) {
    const newAddress = {city, state};

    console.log(newAddress);
}
addressFunc('New Jersey', 'New York'); // Output: {newCity: "New Jersey", newState: "New York"}
```
Object literals is an excellent way for us not to have to write duplicate code, that doesn't help in explaining it, but allows us to write less code while still being very descriptive.