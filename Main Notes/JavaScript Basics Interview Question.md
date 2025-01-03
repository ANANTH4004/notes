#### 🗓️ Date: 2025-01-03 | 🏷️ Tags: [[Interview]] 
---
 
1 Primitive Types: 
	1. string
	2. Boolean
	3. number
	4. BigInt
	5. undefined - *Represents a variable that has been declared but not assigned a value*.
	6. null - *Represents the intentional absence of value.*

---
**7.Symbol** 
```
		// Define a symbol for the unique user ID
const userId = Symbol('userId');

// Create user objects
let user1 = {
  name: 'Alice',
  email: 'alice@example.com',
  [userId]: 101 // Use symbol as a key for unique ID
};

let user2 = {
  name: 'Bob',
  email: 'bob@example.com',
  [userId]: 102 // Each user has a unique symbol-based ID
};

// Access the user ID
console.log(user1[userId]); // 101
console.log(user2[userId]); // 102

// Symbols are not enumerable
console.log(Object.keys(user1)); // ['name', 'email']
console.log(JSON.stringify(user1)); // {"name":"Alice","email":"alice@example.com"}

// Iterate over user properties
for (let key in user1) {
  console.log(key); // Logs only 'name' and 'email'
}

```
---
## Non Primitive
	1. Array
	2. Object
---
## Hoisting
 - variable and function declarations are moved on the top.
 - *variable declared with **let** and **const** are also hoisted but are placed in a **temporal dead zone (TDZ)** from the start of the block until their declaration is encountered. **throws Reference ERROR***
---
## logical operator --> 
- ( || ) --> return the first true value 
- ( && ) --> return the second value always if true or return the falsy value
---
## isNaN(): 
- isNaN() function converts the given value to a Number type, and then equates to NaN.
```
isNaN("Hello") // Returns true 
isNaN(345) // Returns false 
isNaN('1') // Returns false, since '1' is converted to Number type which results in 0 ( a number) 
isNaN(true) // Returns false, since true converted to Number type results in 1 ( a number) 
isNaN(false) // Returns false 
isNaN(undefined) // Returns true
isNaN(null) // false
```

---
