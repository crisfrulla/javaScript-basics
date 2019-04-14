# JavaScript Basics

## Class Curriculum
* [Basic](#basic)
* [Operators](#operators)
* [Control Flow](#control-flow)
* [Objects](#objects)
* [Arrays](#arrays)
* [Functions](#functions)
* [ES6](#es6)

---

## Basics

### Variables
```javascript
let name = 'John';
```

### Constants
```javascript
const dateOfBirth = '01/01/1900'
```

### Primitive Types

#### Value Types
```javascript
let name = 'John'; // String Literal
let age = 20; // Number Literal
let isAproved = false //Boolean Literal
let firstName = undefined;
let selectedColor = null;
```

### Dynamic Typing
```javascript
typeof varName
```

### Reference Types

#### Objects
```javascript
let person = {
  name:'John',
  age:30
};
// Dot Notation
person.name = 'Paul'

// Bracket Notation
person['name'] = 'Luke';
```

#### Array
```javascript
let selectedColors =['red', 'blue'];
selectedColors[0];
selectedColors[2] = 'green';
selectedColors.length // 3
```

#### Function
```javascript
// Performing a task
function greet(name, lastName) {
  console.log('Hello ' + name + ' ' + lastName);
}
greet('John', 'Smith');

//Calculating a value
function square(number) {
  return number * number;
}
square(2);
```

---

## Operators

### Arithmetic Operators
```javascript
let x = 10;
let y = 5;

console.log(x + y);
console.log(x - y);
console.log(x * y);
console.log(x / y);
console.log(x % y);
console.log(x ** y);

// Increment (++)
console.log(x++);
console.log(++x);

// Decrement (--)
console.log(x--);
console.log(--x);
```

### Assignment Operators
```javascript
let x = 10;

x++;
x = x + 1; // Same

x += 5; // Increment of 5 
```

### Comparison Operators
```javascript
let x = 10;

console.log(x > 0); // true
console.log(x >= 0); // true
console.log(x < 0); // false
console.log(x <= 0); // true

// Equality
console.log(x === 0); // true
console.log(x !== 0); // false
```

### Equality Operators
```javascript
// Strict Equality (Type + Value)
console.log(1 === 1); // true
console.log('1' === 1); // false

// Lose Equality
console.log(1 == 1); // true
console.log('1' == 1); // true
console.log(true == 1); // true
```

### Ternary Operator
```javascript
let points = 110;
let type = points > 100 ? 'gold' : 'silver'; // gold
```

### Logical Operators
```javascript
// Logical AND (&&)
let highIncome = true;
let goodCreditScore = true;
let eligibleForLoad = highIncome && goodCreditScore // true

//Logical )R (||)
let highIncome = false;
let goodCreditScore = true;
let eligibleForLoad = highIncome || goodCreditScore // true

// NOT (!)
let applicationRefused = !elegibleForLoan; // false
```

### Logical Operators with Non-booleans
```javascript
// Falsy (false)
// undefined
// null
// 0
// false
// ''
// NaN

// Anything that is not Falsy -> Truthy

let userColor = undefined;
let defaultColor = 'blue';
let currentColor = userColor || defaultColor;
```

### Bitwise Operators
```javascript
// 1 = 00000001
// 2 = 00000010
// 3 = 00000011
// R = 00000000

console.log(1 | 2); // Bitwise OR
console.log(1 & 2); // Bitwise AND

//Read, Write, Execute
// 00000100
// 00000110
// 00000111
```

### Operators Precedence
```javascript
let x = (2 + 3) * 4;
```

---

## Control Flow

### If...else
```javascript
let hour = 10;

if (hour >= 6 && hour < 12)
  console.log('Good Morning');
else if (hour >= 12 && hour < 18)
  console.log('Good Afternoon');
else
  console.log('Good Night');
```

### Switch...case
```javascript
let role;
switch (role) {
  case 'guest': 
    console.log('Guest User');
    break;

  case 'moderator':
    console.log('Moderator User');
    break;

  default:
    console.log('Unknown User');
}
```

### Loops

#### For
```javascript
for (let i = 0; i < 5; i++ ) {
  console.log('Hello World');
}
```

#### While
```javascript
let i = 0;
while (i <= 5) {
  console.log('Hello World');
  i++
}
```

#### Do...while
```javascript
let i = 0;
do {
  console.log('Hello World');
  i++
} while (i <= 5);
```

#### For...in
```javascript
// Use for iterate over an object
const person = {
  name: 'John',
  age: 20
}
for (let key in persone)
  console.log(key, person[key]);

const colors = ['red', 'green', 'blue'];
for (let index in colors)
  console.log(index, colors[index])
```

#### For...of
```javascript
// Use for iterate over an array
const colors = ['red', 'green', 'blue'];
for (let color of colors)
  console.log(color);
```

---

## Objects

### Basic Object
```javascript
// Object-oriented Programming (OOP)

let circle = {
  radius: 1,
  location: {
    x: 1,
    y: 1
  },
  isVisible: true,
  draw: function() {
    console.log('draw');
  }
};

circle.draw(); // Method
```

### Factory Functions
```javascript
// Camel Notation: oneTwoThree

// Factory Function
function createCircle(radius) {
  return {
    radius: radius,
    draw: function() {
      console.log('draw');
    }
  };
}

// Short Syntax
function createCircle(radius) {
  return {
    radius,
    draw() {
      console.log('draw');
    }
  };
}

let circle1 = createCircle(10);
let circle2 = createCircle(20);
```

### Constructor Functions
```javascript
// Pascal Notation: OneTwoThree

function Circle(radius) {
  this.radius = radius;
  this.draw = function() {
    console.log('draw');
  }
}

let circle = new Circle(10);
```

### Dynamic Nature of Objects
```javascript
let circle = {
  radius: 1
};

circle.color = 'yellow';
circle.draw = function() {};

delete circle.color;
delete circle.draw;
```

### Constructor Property
```javascript
new Object(); // let x = {};
new String(); // '', "", ``
new Boolean(); // true, false
new Number(); // 1, 2, 3, ...
```

### Value vs Reference Types
```javascript
// Primitive Type
let x = 10;
let y = x;

x = 20;

// Reference Type
let x = { value: 10 };
let y = x;

x.value = 20;

let number = { value: 10 };
function increase(obj) {
  obj.value++;
}
increase(obj);
```

### Enumerating Properties of an Object
```javascript
let circle = {
  radius: 1,
  draw() {
    console.log('draw');
  }
}

for (let key in circle)
  console.log(key, circle[key]);

for (let key of Object.key(circle))
  console.log(key);
```

### Cloning an Object
```javascript
let circle = {
  radius: 1,
  draw() {
    console.log('draw');
  }
}

// let another = {};
// for (let key in circle)
//   another[key] = circle[key];

// let another = Object.assign({
//   color: 'yellow'
// }, circle);

// Spread operator
let another = { ...circle };
```

### Math Object
```javascript
Math.random()

Math.round(1.9)

Math.max(1,2,3,4,5)

Math.min(1,2,3,4,5)
```

### String Object
```javascript
// String primitive
let message = 'This is my first message';

// String object
let message = new String('hi');

message.includes('my') // true
message.startWith('This') // true
message.endWith('e') // true
message.indexOf('my') // 8
message.replace('first', 'second') // This is my second message
message.trim()
```

### Template Literals
```javascript
let message = 'This is my\n first message';

let message = `
  This is my
  first message
  `;

let name = 'John';
let message = `
  Hi ${name}

  Thank you for joining my mailing list.

  Regards,
  Paul
`;
```

### Date Object
```javascript
let now = new Date();
let date1 = new Date('May 11 2018 09:30');
let date2 = new Date(2018, 4, 11, 9, 30);
```

---

## Arrays

### Adding Elements
```javascript
const numbers = [3, 4];

// End
numbers.push(5,6);

// Beginning
numbers.unshift(1,2);

// Middle
numbers.spice(2, 0, 'a', 'b');
```

### Finding Elements (Primitives)
```javascript
const numbers = [1, 2, 3, 4];

number.indexOf();
number.lastIndexOf(1);
numbers.includes(1);
```

### Finding Elements (Reference Types)
```javascript
const courses = [
  { id: 1, name: 'a'},
  { id: 2, name: 'b'},
];

// Callback function
courses.find(function(course) {
  return course.name === 'a';
});
```

### Arrow Functions
```javascript
// Callback function
let course = courses.find(function(course) {
  return course.name === 'a';
});

// Arrow function
let course = courses.find(course => course.name === 'a');
```

### Removing Elements
```javascript
const numbers = [1, 2, 3, 4];

// End
const last = numbers.pop();

// Beginning
const first = numbers.shift();

// Middle
numbers.spice(2, 1);
```

### Emptying an Array
```javascript
let numbers = [1, 2, 3, 4];

// Solution 1
numbers = [];

// Solution 2
numbers.length = 0;

// Solution 3
numbers.splice(0, numbers.length);

// Solution 4
while (numbers.length > 0)
  numner.pop();
```

### Combining and Slicing Arrays
```javascript
const first = [1, 2, 3];
const second = [4, 5, 6];

const combined = first.concat(second);

const slice = combined.slice(2, 4);
```

### The Spread Operator
```javascript
const first = [1, 2, 3];
const second = [4, 5, 6];

const combined = [...first, 'a', ...second, 'b'];

const copy = [...combined];
```

### Iterating an Array
```javascript
const numbers = [1, 2, 3];

numbers.forEach((number, index) => console.log(number));
```

### Joining Arrays

```javascript
const numbers = [1, 2, 3];
const joined = numbers.join('-');
```

### Sorting Arrays
```javascript
const numbers = [3, 2, 1];
numbers.sort();
numbers.reverse();

const courses = [
  { id: 1, name: 'Node JS'},
  { id: 2, name: 'Ruby on Rails'}
];
numbers.sort(function(a,b) {
  if (a.name < b.name) return -1;
  if (a.name > b.name) return 1;
  return 0;
});
```

### Testing the Elements of an Array
```javascript
const numbers = [1, 2, 3];

const allPositive = numbers.every(function(value) {
  return value >= 0;
});

const atLeastOnePositive = numbers.some(function(value) {
  return value >= 0;
});
```

### Filtering an Array
```javascript
const numbers = [1, 2, -5, 3];
const filtered = numbers.filter(n => n >= 0);
```

### Mapping an Array
```javascript
const numbers = [1, 2, -5, 3];

const filtered = numbers.filter(n => n >= 0);

const items = filtered.map(n => '<li>' + n + '</li>');

const html = '<ul>' + items.join('') + '</ul>';
```

### Reducing an Array
```javascript
const numbers = [1, 2, 3, 4];

// let sum = 0;
// for (let n of numbers)
//   sum += n;

let sum = numbers.reduce((accumulator, currentValue) => {
  return accumulator + currentValue;
}, 0);
```

---

## Functions

### Function Declarations vs Expressions
```javascript
//Function Declarations
function walk() {
  console.log('walk')
}

// Anonymous Function Expressions
let run = function() {
  console.log('run')
};

let move = run;

run();
move();
```

### Hoisting
```javascript
// Javascript engine moves all Function Declarations at the top so you can call function that are defined before their definition.

walk();

function walk() {
  console.log('walk')
}
```

### Arguments
```javascript
function sum(a, b) {
  return a + b;
}
console.log(sum(1, 2, 3, 4));

function sum() {
  let total = 0;
  for (let value of arguments)
    total += value;
  return total;
}
console.log(sum(1, 2, 3, 4, 10));
```

### The Rest Operator
```javascript
function sum(...args) {
 return args.reduce((a, b) => a + b);
}

console.log(sum(1, 2, 3, 4, 10));
```

```javascript
function sum(discount, ...prices) {
 const total = prices.reduce((a, b) => a + b);
 return total * (1 - discount);
}

console.log(sum(0.1, 2, 3, 4, 10));
```

### Default Parameters
```javascript
function interest(principal, rate = 3.5, years = 5) {
  return principal * rate / 100 * years;
}

console.log(interest(10000, 3.5, 5));
```

### Getters and Setters
```javascript
const person = {
  firstName: 'Paul',
  lastName: 'Smith'
  get fullName() {
    return `${person.firstName} ${person.lastName}`;
  },
  set fullName(value) {
    const parts = value.spilt(' ');
    this.firstName = parts[0];
    this.lastName = parts[1];
  }
}

person.fullName = 'John Doe';

console.log(person.fullName);
```

### Try and Catch
```javascript
const person = {
  firstName: 'Paul',
  lastName: 'Smith',
  set fullName(value) {
    if (typeof value !== 'string')
      throw new Error('Value is not a string');

    const parts = value.spilt(' ');
    if (parts.length !== 2)
      throw new Error('Enter a first and last name.');

    this.firstName = parts[0];
    this.lastName = parts[1];
  }
}

try {
  person.fullName = null;
}
catch (e) {
  alert(e);
}

console.log(person);
```

### Local vs Global Scope
```javascript
const color = 'red';

function start( {
  const message = 'hi';
  const color = 'blue';
  console.log(color)
})

function stop( {
  const message = 'bye';
})

start();
```

### Let vs Var
```javascript
function start() {
  for (let i = 0; i < 5; i++)
    console.log(i);
  
  console.log(i);
}

function start() {
  for (var i = 0; i < 5; i++)
    console.log(i);
  
  console.log(i);
}
```

### The this Keyword
```javascript
// function -> global(window)
function video() {
  consol.log(this);
}
video();

// method -> obj
function Video(title) {
  this.title = title;
  console.log(this);
}
const v = new Video('a'); // {}

const video = {
  title: 'a',
  tag: ['1', '2', '3'];
  showTag() {
    this.tags.forEach(function(tag) {
      console.log(this.title, tag);
    }, this);
  }
};
video.showTags();
```

### Changing this
```javascript
function playVideo(a, b) {
  console.log(this);
}
playVideo.call({ name: 'Paul' }, 1, 2);
playVideo.apply({ name: 'Paul' }, [1, 2]);
playVideo.bind({ name: 'Paul' })();

playVideo();

const video = {
  title: 'a',
  tag: ['1', '2', '3'];
  showTag() {
    this.tags.forEach(tag => {
      console.log(this.title, tag);
    });
  }
};
video.showTags();
```

---

## ES6

### Objects
```javascript
const person = {
  name: 'Paul',
  walk() {},
  talk() {}
}
person.talk();
```

### Binding this
```javascript
const person = {
  name: 'Paul',
  walk() {
    console.log(this);
  }
}

person.talk();

const walk = person.walk.bind(person);
walk();
```

### Arrow Functions
```javascript
const square = function(number) {
  return number * number;
};

const square = (number) => number * number;

square(5);
```

```javascript
const jobs = [
  { id: 1, isActive: true },
  { id: 2, isActive: true },
  { id: 3, isActive: false }
];

const activeJob = job.filter((job) => job.isActive);
```

### Array.map Method
```javascript
const colors = ['red', 'blue', 'green'];
const items = color.map((color) => `<li>${color}</li>`);
```

### Object Destructuring
```javascript
const address = {
  street: '',
  city: '',
  country: ''
};

const { street: st, city, country } = address;
```

### Spread Operator
```javascript
// Array
const first = [1, 2, 3];
const second = [4, 5, 6];

const combined = [...first, 'a', ...second, 'b'];

const clone = [...combined];

// Object
const first = { name: 'Paul'};
const second = { job: 'Designer'};

const combined = {...first, ...second, location: 'Sydney'};

const clone = {...combined};
```

### Classes
```javascript
const person = {
  name: 'Paul',
  walk() {
    console.log('walk');
  }
};

class Person {
  construtor(name) {
    this.name = name;
  }

  walk() {
    console.log('walk');
  }
};

const person = new Person('Paul');
```

### Inheritance
```javascript
class Person {
  construtor(name) {
    this.name = name;
  }

  walk() {
    console.log('walk');
  }
}

class Teacher extends Person {
  constructor(name, degree) {
    super(name);
    this.degree = degree;
  }

  teach() {
    console.log('teach');
  }
}

const teacher = new Teacher('Paul', 'Art');
```

### Modules
```javascript
// file1.js
export class Person {
  construtor(name) {
    this.name = name;
  }

  walk() {
    console.log('walk');
  }
}
//

// file2.js
import { Person } from './file1';

export class Teacher extends Person {
  constructor(name, degree) {
    super(name);
    this.degree = degree;
  }

  teach() {
    console.log('teach');
  }
}
//

// file3.js
import { Teacher } from './file2';

const teacher = new Teacher('Paul', 'Art');
teacher.teach();
//
```

### Named and Default Exports
```javascript
// file3.js
import Teacher, { promote } from './file2';

const teacher = new Teacher('Paul', 'Art');
teacher.teach();
//

// file2.js
import { Person } from './file1';

export function promote() {};

export default class Teacher extends Person {
  constructor(name, degree) {
    super(name);
    this.degree = degree;
  }

  teach() {
    console.log('teach');
  }
}
//

```

---


### 

```javascript
```