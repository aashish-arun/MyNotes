
[[Reactsheet]]

##
## ES6 (ECMAScript 6)
ECMAScript was created to standardize JavaScript, and ES6 is the 6th version of ECMAScript, it was published in 2015, and is also known as ECMAScript 2015.
### Why Should I Learn ES6?
React uses ES6, and should be familiar with some of the its new features like
- Classes
- Arrow Functions
- Variables (let, const, var)
- Array Methods like .map()
- Destructuring
- Modules
- Ternary Operator
- Spread Operator

---
### ES6: Classes
A class is a type of function, but instead of using the keyword `function` to initiate it, we use the keyword `class`, and the properties are assigned inside a `constructor()` method.
###### `Example of a simple class constructor with an object called "mycar" based on the Car class:`
```jsx
class Car {
	constructor(name) {
		this.brand = name;
	}
}

const myCar = new Car("Ford"); // Creates an object based on Car class
```

```Note
Standard naming convention for classes in javascript is PascalCase
The constructor function is called automatically when the object is initialized.
```
 
### Method in Classes
We can use our own methods inside a class:
###### `Example of a method named "present" which is inside the Car class:`
```jsx
class Car {
	constructor(name) {
	    this.brand = name;
	}
  
	present() {
		return 'I have a ' + this.brand;
	}
}

const myCar = new Car("Ford"); // Creates an object based on Car class
myCar.present();
```

```Note
We can call the method by referring to the object's method name followed by parentheses (parameters would go inside the parentheses).
```

### Class Inheritance
A class created with a class inheritance inherits all the methods from the other class. We use `extends` keyword to create class inheritance.
###### `Example of a class named "Model" which will inherit the methods from the "Car" class:`
```jsx
class Car {
	constructor(name) {
		this.brand = name;
	}
	present() {
	return 'I have a' + this.brand;
	}
}

class Model extends Car {
	constructor(name, model) {}
		super(name); // `super()` method refers to the parent class.
		this.model = model
	}
	show() {
      return this.present() + ', it is a ' + this.model;
    }
}

const myCar = new Model("Ford", "Mustang"); // Creates an object based on Model class that inherts from Car class
myCar.show();
```

```Note
By calling the `super()` method in the constructor method, we call the parent's constructor method and gets access to the parent's properties and methods.
```

---
### ES6: Arrow Functions
It allow us to write shorter function syntax. 
###### `Example of before arrow:`
```jsx
hello = function() {  
	return "Hello World!";  
}
```
###### `Example of with arrow function:`
```jsx
hello = () => {  
  return "Hello World!";  
}
```

If the function has only one statement, and the statement returns a value, you can remove the brackets _and_ the `return` keyword:
###### `Example of arrow function when it return a value by default:`
```jsx
hello = () => "Hello World!";
```

If you have parameters, you pass them inside the parentheses:
###### `Example of arrow function with parameters:`
```jsx
hello = (val) => "Hello " + val;
```

If you have only one parameter, you can skip the parentheses as well:
###### `Example of arrow function with parameters without parentheses:`
```jsx
hello = val => "Hello " + val;
```

### What About `this`?
The handling of `this` is also different in arrow functions compared to regular functions.

In short, with arrow functions there is no binding of `this`.

In regular functions the `this` keyword represented the object that called the function, which could be the window, the document, a button or whatever.

With arrow functions, the `this` keyword _always_ represents the object that defined the arrow function.

Let us take a look at two examples to understand the difference.
Both examples call a method twice, first when the page loads, and once again when the user clicks a button.

The first example uses a regular function, and the second example uses an arrow function.

###### `Example of a regular function:`
```jsx
class Header {
  constructor() {
    this.color = "Red";
  }

//Regular function:
  changeColor = function() {
    document.getElementById("demo").innerHTML += this; // this represents the object that called the function
  }
}

const myheader = new Header();

//The window object calls the function:
window.addEventListener("load", myheader.changeColor);

//A button object calls the function:
document.getElementById("btn").addEventListener("click", myheader.changeColor);
```

###### `Example of an arrow function:`
```jsx
class Header {
  constructor() {
    this.color = "Red";
  }

//Arrow function:
  changeColor = () => {
    document.getElementById("demo").innerHTML += this; // this represents the Header object no matter who called the function
  }
}

const myheader = new Header();


//The window object calls the function:
window.addEventListener("load", myheader.changeColor);

//A button object calls the function:
document.getElementById("btn").addEventListener("click", myheader.changeColor);
```

The result shows that the first example returns two different objects (window and button), and the second example returns the Header object twice.

Hence depending on the use choice which one you want to use.

---
### ES6: Variables
Before ES6, we only had one way to defining `var` keyword and if you didn't define them, they would be assigned to the global object. Unless you were in strict mode, then you would get an error if your variables were undefined.

Now, with ES6, there are three ways of defining your variables as: `var`, `let`, and `const`.
###### `Example of var:`
```jsx
var x = 5.6;
```

###### `Example of let:`
```jsx
let x = 5.6;
```

###### `Example of const:`
```jsx
const x = 5.6;
```

| Define as          | `var`                                                                                                                                                                                                                                                                        | `let`                                                                                                              | `const`                                                                                       |
| ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------- |
| **Scope**          | Function<br><br>Defined `var` outside of a function, it belongs to the global scope.<br><br>Defined `var` inside of a function, it belongs to that function.<br><br>Defined `var` inside of a block, i.e. a for loop, the variable is still available outside of that block. | Block<br><br>Defined `let` inside of a block, i.e. a for loop, the variable is only available inside of that loop. | Block<br><br>`const` is a variable that once it has been created, its value can never change. |
| **Hoisted**        | ✅ (initialized as `undefined`)                                                                                                                                                                                                                                               | ✅ (but not initialized)                                                                                            | ✅ (but not initialized)                                                                       |
| **Can reassign?**  | ✅ Yes                                                                                                                                                                                                                                                                        | ✅ Yes                                                                                                              | ❌ No                                                                                          |
| **Can redeclare?** | ✅ Yes                                                                                                                                                                                                                                                                        | ❌ No                                                                                                               | ❌ No                                                                                          |
| Use case           |                                                                                                                                                                                                                                                                              |                                                                                                                    |                                                                                               |

---
### ES6: Array Methods
Out of the many JavaScript array methods, the most useful in React is the `.map()` array method. 
### `.map()` method
The `.map()` method allows you to run a function on each item in the array, returning a new array as the result. In React, `map()` can be used to generate lists.

###### `Example of .map():`
```jsx
const myArray = ['apple', 'banana', 'orange'];

const myList = myArray.map((item) => <p>{item}</p>)
```


### ES6: Destructuring
It is an easier way to get specific items from a list or properties from a object.

### Destructuring Arrays
Returns an item in a list as an another array.
###### `Example without using destructing (i.e. before ES6) :`
```jsx
const vehicles = ['mustang', 'f-150', 'expedition'];

// Before ES6
const car = vehicles[0];
const truck = vehicles[1];
const suv = vehicles[2];
```

###### `Example using destructing :`
```jsx
const vehicles = ['mustang', 'f-150', 'expedition'];

const [car, truck, suv] = vehicles;
```

###### `Example using destructing but not needing all the items in the list :`
```jsx
const vehicles = ['mustang', 'f-150', 'expedition'];

const [car,, suv] = vehicles;
```

###### `Example using destructing in a function when it returns an array :`
```jsx
function calculate(a, b) {
  const add = a + b;
  const subtract = a - b;
  const multiply = a * b;
  const divide = a / b;

  return [add, subtract, multiply, divide];
}

const [add, subtract, multiply, divide] = calculate(4, 7);
```

```Note
When destructuring arrays, the order that variables are declared is important.
```
### Destructuring Objects
Returns an property in an object as an another array.
###### `Example without using destructing (i.e. before ES6) :`
```jsx
const vehicleOne = {
  brand: 'Ford',
  model: 'Mustang',
  type: 'car',
  year: 2021, 
  color: 'red'
}

myVehicle(vehicleOne);

// Before ES6
function myVehicle(vehicle) {
  const message = 'My ' + vehicle.type + ' is a ' + vehicle.color + ' ' + vehicle.brand + ' ' + vehicle.model + '.';
}
```

###### `Example using destructing :`
```jsx
const vehicleOne = {
  brand: 'Ford',
  model: 'Mustang',
  type: 'car',
  year: 2021, 
  color: 'red'
}

myVehicle(vehicleOne);

function myVehicle({type, color, brand, model}) {
  const message = 'My ' + type + ' is a ' + color + ' ' + brand + ' ' + model + '.';
}
```

```Note
The object properties do not have to be declared in a specific order.
```

###### `Example using destructing in a nested object by referencing the nested object then using a colon and curly braces to again destructure the items needed from the nested object:`
```jsx
const vehicleOne = {
  brand: 'Ford',
  model: 'Mustang',
  type: 'car',
  year: 2021, 
  color: 'red',
  registration: {
    city: 'Houston',
    state: 'Texas',
    country: 'USA'
  }
}

myVehicle(vehicleOne)

function myVehicle({ model, registration: { state } }) {
  const message = 'My ' + model + ' is registered in ' + state + '.';
}
```


---
### ES6: Spread Operator (`...`)
This operator allows us to quickly copy all or part of an existing array or object into another array or object. It is often used in combination with destructuring.

###### `Example of assigning the first and second items from `numbers` to variables and put the rest in an array:`
```jsx
const numbers = [1, 2, 3, 4, 5, 6];

const [one, two, ...rest] = numbers;
```

###### `Example of assigning the first and second items from `numbers` to variables and put the rest in an array:`
```jsx
const numbers = [1, 2, 3, 4, 5, 6];

const [one, two, ...rest] = numbers;
```

---
### ES6: Modules


---
### ES6: Ternary Operator
This is a simplified conditional operator which functions similar to `if` / `else`.

#### `Syntax`
```jsx
condition ? <expression if true> : <expression if false>
```

###### `Example of using if/else to authenticate  (i.e. before ES6) :`
```jsx
if (authenticated) {
  renderApp();
} else {
  renderLogin();
}
```

###### `Example of using ternary (i.e. after ES6) :`
```jsx
authenticated ? renderApp() : renderLogin();
```


## Render HTML
Goal is (i.e. build) to render HTML in a web page. To render HTML to a web page it uses a function called createRoot() and its method render()

### The createRoot Function

The `createRoot()` function takes one argument, an HTML element.

The purpose of the function is to define the HTML element where a React component should be displayed.

### The render Method

The `render()` method is then called to define the React component that should be rendered.

But render where?

## JavaScript XML (JSX)
JSX stands for JavaScript XML. It allows us to write and add HTML in react.

### Coding JSX
It allows us to write HTML elements in JavaScript and place them in the DOM without any `createElement()`  and/or `appendChild()` methods. It converts HTML tags into react elements.

```Note
You are not required to use JSX, but JSX makes it easier to write React applications.
```

### Expressions in JSX

### One Top Level Element
The HTML code must be wrapped in _ONE_ top level element. You can put everything inside a div (`<div></div>`) or fragment  (`<></>`).

###### `Example of wrapping two paragraphs inside one DIV element:`
```jsx
const myElement = (
  <div>
    <p>I am a paragraph.</p>
    <p>I am a paragraph too.</p>
  </div>
);
```

```Note
JSX will throw an error if the HTML is not correct, or if the HTML misses a parent element.
```

###### `Example of wrapping two paragraphs inside a fragment:`
```jsx
const myElement = (
  <>
    <p>I am a paragraph.</p>
    <p>I am a paragraph too.</p>
  </>
);
```

### Elements Must be Closed

## Components
Components are independent and reusable bits of code. They serve the same purpose as JavaScript functions, but work in isolation and return HTML. They are of two types class and function component

```Note
In older React code bases, you may find Class components primarily used. It is now suggested to use Function components along with Hooks, which were added in React 16.8. There is an optional section on Class components for your reference.
```

### Create Your First Component

```Note
Component MUST start with an upper case letter.
```
#### Class Component

A class component must include the `extends React.Component` statement and requires a `render()` method. 

This `extends React.Component` statement creates an inheritance to React.Component, and gives your component access to React.Component's functions.

The `render()` method returns HTML.
###### `Example of a class component called Car:
```jsx
class Car extends React.Component {
  render() {
    return <h2>Hi, I am a Car!</h2>;
  }
}
```

###### `Example of a fucntion component called Car:
```jsx
function Car() {
  return <h2>Hi, I am a Car!</h2>;
}
```

---
## Conditionals

1. Using if
2. Using &&
3. Using tertary