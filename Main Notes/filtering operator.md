#### 🗓️ Date: 16-12-2024 | 🏷️ Tags: [[Rxjs]]
---
#### **audit** & **auditTime**

- ignore the source value specified by the inner observable.
```
import { fromEvent, audit, interval } from 'rxjs';

const clicks = fromEvent(document, 'click');
const result = clicks.pipe(audit(ev => interval(1000)));
result.subscribe(x => console.log(x));
```

- ignore the source value by given time milliseconds *auditTime(50)*
---
> [!flashcard]- **debounce**
>Emits a notification from the source Observable only after a particular time span determined by another Observable has passed without another source emission.

---

#### **debounceTime**

```
import { fromEvent, debounceTime } from 'rxjs';

const clicks = fromEvent(document, 'click');
const result = clicks.pipe(debounceTime(1000));
result.subscribe(x => console.log(x));
```

---
1. **Skip** -> ![[Pasted image 20241223125516.png]]

2. **skipLast**![[Pasted image 20241223125559.png]]

3. **skipUntil** ![[Pasted image 20241223125649.png]]
4. **skipWhile** ![[Pasted image 20241223125748.png]]


---
## Throttle vs ThrottleTime

### **Throttle**

- **Definition**: Emits a value, then ignores others until a **secondary observable** completes.
- **Use Case**: When you need **custom throttling logic** (e.g., dynamic delays or external triggers).
- **Example**:
    `throttle(() => interval(2000))`
    - Emits one value every 2 seconds using the secondary observable.
    
### **ThrottleTime**

- **Definition**: Emits a value, then ignores others for a **fixed time period**.
- **Use Case**: When you need simple, **time-based throttling**.
- **Example**:    
    `throttleTime(2000)`
    - Emits one value every 2 seconds using a fixed duration.
### **Key Differences**

|Feature|**Throttle**|**ThrottleTime**|
|---|---|---|
|**Logic**|Uses a secondary observable.|Uses a fixed time duration.|
|**Use Case**|Dynamic/custom delays.|Consistent time-based throttling.|
|**Complexity**|More flexible but requires logic.|Simple and easy to use.|

---

#### **distinct**
- get the unique values form the source observable.

	1.**distinctUntilChnaged** -> compare previous and next value.
	2.**distinctUntilKeyChanged** -> compare prev and next value only but based on specified key.

| Feature              | `distinctUntilChanged`                                      | `distinctUntilKeyChanged`                              |
| -------------------- | ----------------------------------------------------------- | ------------------------------------------------------ |
| **Comparison**       | Compares entire values (or based on a custom function).     | Compares the value of a specific key in objects.       |
| **Use Case**         | Works with primitives or objects (with custom comparison).  | Specifically designed for objects with a target key.   |
| **Default Behavior** | Deep comparison for primitives; objects require a function. | Compares by key directly without requiring a function. |
| **Customization**    | Optional custom comparator for flexible use cases.          | Sim                                                    |

---
#### **filter**
- like array.prototype.filter method.
---

#### **first**, **last**, **single**, **elementAt**, **sample**, 

---

