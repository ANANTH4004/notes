#### 🗓️ Date: 16-12-2024 | 🏷️ Tags: [[Rxjs]] | Link: [Error operator](https://rxjs.dev/guide/operators#error-handling-operators)
---
### **catchError**
 *catch the error on the observable to be handled by returning a new observable or throwing an error.*
 

---
## **Retry**

- **What It Does**: Retries a failed observable a specific number of times before throwing the error.
    
- **Use Case**: Automatically retry failed operations (e.g., network requests) a fixed number of times.
- **Explanation**: If an error occurs, the observable will retry twice before emitting the error.

---

## **RetryWhen**

- **What It Does**: Retries a failed observable based on a custom condition or strategy defined by a notifier observable.
    
- **Use Case**: When you need **custom retry logic** (e.g., wait time between retries or retry only for specific errors).
- **Explanation**: The retry logic waits for 2 seconds before attempting again, using the `timer` operator.
---

### **Key Differences**

|Feature|**Retry**|**RetryWhen**|
|---|---|---|
|**Logic**|Retries a fixed number of times.|Retries based on a **notifier observable**.|
|**Flexibility**|Simple, fixed retry count.|Customizable with dynamic logic.|
|**Use Case**|Fixed retry attempts.|Conditional retries (e.g., delays or filters).|