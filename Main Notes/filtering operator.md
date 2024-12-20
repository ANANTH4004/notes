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


to check commit message