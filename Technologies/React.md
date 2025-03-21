## Classes
A class is a type of function, but instead of using the keyword `function` to initiate it, we use the keyword `class`, and the properties are assigned inside a `constructor()` method.
### Example
A simple class constructor with an object called "mycar" based on the Car class:

```jsx
class Car {
	constructor(name) {
		this.brand = name;
	}
}

const mycar = new Car("Ford"); // Creates an object based on Car class
```

```Note
Standard naming convention for classes in javascript is PascalCase
The constructor function is called automatically when the object is initialized.
```
 
## Method in Classes
We can use our own methods inside a class:
### Example
A method named "present" which is inside the Car class:

```jsx
class Car {
	constructor(name) {
	    this.brand = name;
	}
  
	present() {
		return 'I have a ' + this.brand;
	}
}

const mycar = new Car("Ford");
mycar.present();
```

```Note
We can call the method by referring to the object's method name followed by parentheses (parameters would go inside the parentheses).
```

---
## Class Inheritance
A class created with a class inheritance inherits all the methods from the other class. We use `extends` keyword to create class inheritance.

### Example
A class named "Model" which will inherit the methods from the "Car" class:

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
	constructor(name, model) {
	}
	super(name)
}
const mycar = new Car("Ford"); // Creates an object based on Car class
```


## Arrow Function

