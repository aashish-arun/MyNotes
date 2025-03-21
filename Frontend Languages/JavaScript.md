


## Variables
they are containers for storing data. they can be declared  in 4 ways:

###### `1. Automatically`
```js
x = 5;  
y = 6;  
z = x + y; // x, y, and z are undeclared variables. They are automatically declared when first used.
```

```Note
It is considered good programming practice to always declare variables before use.
```
###### `2. Using var`
```js
x = 5;  
y = 6;  
z = x + y; // x, y, and z are undeclared variables. They are automatically declared when first used.
```
###### `3.  Using let`
```js
x = 5;  
y = 6;  
z = x + y; // x, y, and z are undeclared variables. They are automatically declared when first used.
```
###### `4.  Using const
```js
x = 5;  
y = 6;  
z = x + y; // x, y, and z are undeclared variables. They are automatically declared when first used.
```

## When to Use var, let, or const?

---

## **this** Keyword

---
## Arrow Function
It allow us to write shorter function syntax. 
###### `Example of before arrow:`
```js
hello = function() {  
	return "Hello World!";  
}
```
###### `Example of with arrow function:`
```js
hello = () => {  
  return "Hello World!";  
}
```

If the function has only one statement, and the statement returns a value, you can remove the brackets _and_ the `return` keyword:
###### `Example of arrow function when it return a value by default:`
```js
hello = () => "Hello World!";
```

If you have parameters, you pass them inside the parentheses:
###### `Example of arrow function with parameters:`
```js
hello = (val) => "Hello " + val;
```

If you have only one parameter, you can skip the parentheses as well:
###### `Example of arrow function with parameters without parentheses:`
```js
hello = val => "Hello " + val;
```
---
## Classes
Classes are templates for JavaScript Objects. We use keyword `class` to create a class and always add a method named `constructor()` to initialize the properties of the object. We can also use other optional methods to define the behavior of the objects created from that class.
#### `Syntax`
```js
class ClassName {  
	constructor() { ... }  
	method_1() { ... }  
	method_2() { ... }  
	method_3() { ... }  
}
```
###### `Example of a class named Car with two initial properties named name and year:`
```js
class Car() {
	constructor(name, year) {
		this.name = name;
		this.year = year;
	}
}
```
### Using a Class
When you have a class, you can use the class to create objects:
###### `Example of two objects named myCar1 and myCar2 which is made using the Car class:`
```js
const myCar1 = new Car("Ford", 2014);
const myCar2 = new Car("Audi", 2019);
```
### Constructor Method
It is a special method that is used to initialize object's properties. It is executed automatically when a new object is created.

```Note
If you do not define a constructor method, JavaScript will add an empty constructor method.
```
### Class Methods
These are the methods that define the behavior of the objects created from the class. There is no limit to the number of methods that you can create in a class.
###### `Example of a class method named "age", that returns the Car age:`
```js
class Car() {
	constructor(name, year) {
		this.name = name;
		this.year = year;
	}
	age() {
		const date = new Date();
		return date.getFullYear() - this.year;
	}
}

const myCar = new Car("Ford", 2014);

document.getElementById("demo").innerHTML =  "My car is " + myCar.age() + " years old.";
```

###### `Example of a class method named "age", that returns the Car age while pasing parameters to it:`
```js
class Car() {
	constructor(name, year) {
		this.name = name;
		this.year = year;
	}
	age(year) {
		return year - this.year;
	}
}

const date = new Date();
let year = date.getFullYear();

const myCar = new Car("Ford", 2014);

document.getElementById("demo").innerHTML =  "My car is " + myCar.age(year) + " years old.";
```

---