1. The stack data structure is a sequential collection of elements that follows the principle of **Last In First Out (LIFO)**
2. The last element inserted into the stack is first element to be removed
3. A stack of plates. The last plate placed on top of the stack is also the first plateremoved from the stack.
4. Stack is an abstract data type. It is defined by its behavior rather than being a mathematical model
5. The Stack data structure supports two main operations
6. Push, which adds an element to the collection
7. Pop, which removes the most recently added element from the collection
**Stack Usage**
- Browser history tracking (back and forward buttons)
- Undo operation when typing
- Expression conversions
- Call stack in JavaScript runtime

```js
class Stack {
  constructor() {
    this.items = []
  }
  get size() {
    return this.items.length
  }
  pop() {
    if (this.items.length === 0) {
      return 'undefined'
    }
    return this.items.pop()
  }

  push(element) {
    this.items.push(element)
  }

  peek() {
    if (this.size == 0) {
      return 'undefined'
    }
    return this.items[this.size - 1]
  }
  
  clear() {
    this.items.length = 0
  }

  [Symbol.iterator]() {
    let index = this.items.length - 1
    return {
      next: () => {
        if (index >= 0) return { value: this.items[index--], done: false }
        else return { done: true }
      },
    }
  }
}

let stack = new Stack()
stack.push(1)
stack.push(2)
stack.push(3)
stack.push({ name: 'anand' })
console.log('poping', stack.pop())
for (let s of stack) {
  console.log(s)
}

```
