#### 🗓️ Date: 2025-01-03 | 🏷️ Tags: [[JavaScript]]
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
