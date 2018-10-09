# modern-js-es6-es7-es8
This document will teach you the most modern features of JavaScript, also known as ES6, ES7, ES8

## Template Literals
Strings historically in JS has been a second class citizen, haven't got much love in comparison with other programming languages. Let's take an example:

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
Destructuring arrays has been another great feature that has been added to JS and is very similar to how we destructed objects above, so let's take an example.

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
However object literals give us the ability to, if these keys are the same as the values that they are passing it, we don't have to actually set it, it's going to make the assumptions it self.

```javascript
function addressFunc (city, state) {
    const newAddress = {city, state};

    console.log(newAddress);
}
addressFunc('New Jersey', 'New York'); // Output: {newCity: "New Jersey", newState: "New York"}
```
Object literals is an excellent way for us not to have to write duplicate code, that doesn't help in explaining it, but allows us to write less code while still being very descriptive.

## Spread Operator
This is another great addition to JS, one you can use almost on daily basis at work. Let's take it in an example.

```javascript
let arrayOne = [1,2,3,4,5,6,7];
let arrayTwo = [...arrayOne];

console.log(arrayTwo); // Output: [1, 2, 3, 4, 5, 6, 7]
```
Actually it's unwrapping the values of `arrayOne` into `arrayTwo`. All the new values are added to `arrayTwo`, also it's not passing it by reference, is it instantiating new array in this instance.

## Rest Operator
Rest Operator although is not used widely as Spread Operator, is somewhat similar and just as valuable to worth mentioning. It gives the ability to get the arguments out of our function and it's used in a case when we don't know how many inputs are going to be used. Let's take it in an example.
```javascript
function add(...nums) {
    //now when we access nums we'll get an array of the input values
    console.log(nums);
}
add(8, 12, 32, 41, 51); // Output: [8, 12, 32, 41, 51]
```
When you're going to write a function and you don't know how many values are gonna be inputted you just know it's going to be some sort of value but you don't want to necessarily just pass an array for various reasons you may want to consider the rest operator.

## Arrow Functions
Arrow functions are a great way to eliminate some of the unnecessary boilerplate of callback functions and comes with a lot of functionality, with some key points you don't know exists.
```javascript
function add(...nums) {
    let total = nums.reduce( (x, y) => x + y);
    
    console.log(total);
}
add(8, 12, 32, 41, 51); // Output: 144
```

## Default Params
Default parameters are another new concept, but it's around in other programming languages for quite some time and it provides us a lot of value. Let's take it in an example.

```javascript
function add(numArray = []) {
    let total = 0;
    numArray.forEach( (element) => {
        total =+ element
    });
    
    console.log(total);
}
add(); // Output: 144
```
So if we never pass an array when calling the function, we would've get a error. Because `numArray` will be undefined, but if we use optional parameters and add to the parameter `numArray = []`, because sometimes maybe when we call it, can be that it doesn't matter, sometimes it can be just an empty array.

## Includes
The `includes()` method determines whether an array includes certain element, returning `true` or `false`.
```javascript
var arrayOne = [1, 2, 3];

console.log(arrayOne.includes(2)); // Output: true
```

## Let & Const
So `let` is a stricter version of `var` and which it uses block scope, so in our case:
```javascript
if (false) {
    let example = true;
}

console.log(example); // Output: ReferenceError: example is not defined
```
So although `var` for instance will not throw an error, but instead will return as `null`, because `var` is using hoisting, `let` does not and neither does `const`.

So `const` as you may guessed it stands for constant, but it may not work the same way that you would expect.
```javascript
const example = 5;

console.log(example); // Output: 5
```
For `const` you can't actually reset the value, because are read-only properties, these are things that have been set and you don't plan on changing.

But there's one catch when using arrays, so for instance we have an empty array and we want to push a value:

```javascript
const example = [];
example.push(5);
console.log(example); // Output: [5]
```
That above example, goes the same for objects.

However if we wanted to change the value from an array to something else:
```javascript
const example = [];
example = 3;
console.log(example); // Output: SyntaxError: unknown: "example" is read-only
```

## Import & Export
The `import` statement is used to import bindings which are exported by another module, while `export` statement is used when creating JS modules to export functions, objects, or primitive values from the module so they can be used by other programs with the `import` statement.

Source `example.js`
```javascript
export const data = [1, 2, 3];
```
Source `app.js`
```javascript
import { data } from './example.js';
let updatedData = data;
data.push(4);
console.log(data); // Output [1, 2, 3, 4]
```