#### 🗓️ Date: 2025-01-03 | 🏷️ Tags: [[JavaScript]]

# LINK: [questions](https://www.interviewbit.com/javascript-interview-questions/#difference-between-exec-and-test-methods-in-javascript)
---
## Ways to create Objects in Javascript:
1. Using **Object Literals** --> let person = {name: "Anand", age: 23}
2. using **new Object()**
3. **Object constructor function** -> Sometimes we need to create many objects of the same **type**.
	- To create an **object type** we use an **object constructor function**.
	- `function Person(first, last, age, eye) { this.firstName = first;  this.lastName = last;  this.age = age;  this.eyeColor = eye; }`
4. Using `Object.assign()`
5. Using `Object.create()`
6. Using `Object.fromEntries()`
---
## Deep Copy
- create completely new and independent array or an Object, duplication all the nested objects. 
- Changes in the copied do not affect the original object.
- **JSON.parse(JSON.stringify(original))**
- **let copied = structuredClone(original)**
---
## Shallow Copy
- [*Object.assign()*](https://github.com/ANANTH4004/notes.git) method
- using *=* 
- using **spread operator (...object name)**
---
# [**Object** Method](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object#static_methods)
- *Object.assign()* --> used to shallow copy an object or assign one object to another.
> let source1 = {a: 10, b: 20}
> let source2 = {b: 40, c: 30}
> const target = Object.assign({}, source1, source2);
> // output: target: {a:10, b:40, c:30}

- *Object.keys()*
- *Object.values()*
- *Object.entries()*
- *Object.freeze()* --> Prevents adding, removing, or modifying properties of the object.
>const obj = { name: 'Alice' };
 Object.freeze(obj);
 obj.name = 'Bob'; // No effect
 console.log(obj.name); // Alice

- *Object.seal()* --> modification of the exsting propery is allowed but we can't delete or add new property.
- **Object.is(value1,value2)** -->  compare both value if they are same return true else false. Mostly used to compare NaN with NaN or -0 and +0 
> const value = NaN;
  console.log(value === NaN); // false
  console.log(Object.is(value, NaN)); // true

---

# Closure and lexical scope

**Lexical Scope** means **where a variable is declared in your code** determines where it can be accessed.

- Inner functions can access variables of their parent functions because they are written inside the parent function.
- Even if the parent function finishes running, the inner function still remembers the variables.
```
function outer() {
  const message = "Hello from outer!"; // Variable in outer function
  function inner() {
    console.log(message); // Accessing outer function's variable
  }
  inner(); // Calling the inner function
}
outer(); // Output: Hello from outer!
```

A **closure** happens when a function **remembers** the variables from its parent function, even after the parent function has finished executing.
#### **Key Idea of Closure**
- If you **return a function** from another function, the returned function keeps access to the variables in the parent function.
>function outerFunction() {
  let count = 0; // Variable in the outer function
  return function innerFunction() {
    count++; // Inner function changes the outer variable
    console.log(`Count is: ${count}`);
  };
}
const counter = outerFunction(); // outerFunction runs and returns innerFunction
counter(); // Count is: 1
counter(); // Count is: 2
counter(); // Count is: 3

---

# PROTOTYPE: #prototype

- Prototype is a javascript mechanism that enables *inheritance* by linking Objects. 
- It allows an object to inherit properties and methods from another object.
- **advantages --> Inheritance and Memory Efficiency**

---
# Function chaining.
- a pattern that allows calling multiple methods on the same object in a single statement.
- **ensure all the method that are chaning needs to return this**
```
class User {
  constructor(name, age) {
    this.name = name;
    this.age = age;
    this.errors = [];
  }

  validateName() {
    if (!this.name) {
      this.errors.push("Name is required.");
    }
    return this;
  }

  validateAge() {
    if (this.age < 18) {
      this.errors.push("Age must be 18 or older.");
    }
    return this;
  }

  getErrors() {
    return this.errors;
  }
}

const user = new User("", 16)
  .validateName()
  .validateAge()
  .getErrors();

console.log(user); // [ 'Name is required.', 'Age must be 18 or older.' ]
```

---
# Generator function:
- Generator function is a special type of function in javascript that *can be paused and resumed during its execution.* It allows us to yeild multiple values over time making it perfect for scenarios like iterating over a data or controlling async operation.
- Defined with **function**** 
- **yeild** statement is used to pause the function and return the value.Execution can resume from where it was paused.
- **Returns an Iterator:** A generator function returns an **iterator** object with a `next()` method. Each call to `next()` resumes the generator from where it was last paused.
```
function* generatorFunction() {
  yield "First value";
  yield "Second value";
  yield "Third value";
}
const generator = generatorFunction();
console.log(generator.next()); // { value: 'First value', done: false }
console.log(generator.next()); // { value: 'Second value', done: false }
console.log(generator.next()); // { value: 'Third value', done: false }
console.log(generator.next()); // { value: undefined, done: true }
```

---
# Immediately Invoked function:
- An Immediately Invoked Function ( known as IIFE and pronounced as IIFY) is a function that runs as soon as it is defined.
---
# Higher order function:
- function that operators on another function either taking them as a an arguments or returning them are called higher order function.
---
# Currying
- Currying is the process of transforming a function with multiple arguments into a series of functions, each taking one argument at a time.
```
function curriedAdd(a) {
  return function (b) {
    return function (c) {
      return a + b + c;
    };
  };
}

console.log(curriedAdd(1)(2)(3)); // 6
```
---
# Call
- its a method that invoke another method by specifying the owner Object.
```
function sayHello(){ 
	return "Hello " + this.name; }
	var obj = {name: "Sandy"}; 
	sayHello.call(obj); // Returns "Hello Sandy"
```

---
# Apply
-  The apply method is similar to the call() method. The only difference is that, call() method takes arguments separately whereas, apply() method takes arguments as an array.
```
function saySomething(message){
  return this.name + " is " + message;
}        
var person4 = {name:  "John"};
saySomething.apply(person4, ["awesome"]);
```
---
# Bind:
- This method returns a new function, where the value of **“this”** keyword will be bound to the owner object, which is provided as a parameter.
```
var bikeDetails = { 
		displayDetails: function(registrationNumber,brandName){
		return this.name+ " , "+ "bike details: "+ registrationNumber + " , " + brandName; } 
		} 
		var person1 = {name: "Vivek"}; var detailsOfPerson1 = bikeDetails.displayDetails.bind(person1, "TS0122", "Bullet"); // Binds the displayDetails function to the person1 object detailsOfPerson1(); //Returns Vivek, bike details: TS0122, Bullet
```

