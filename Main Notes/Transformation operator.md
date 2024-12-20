[[Rxjs]]
# [Transformation operator](https://rxjs.dev/guide/operators#transformation-operators):

- **concatMap** --> Maps each value emitted by the source Observable to an inner Observable using a provided mapping function (`project` function).
				- ![[Pasted image 20241220120402.png]]
- **concatMapTo** --> Maps every value emitted by the source Observable to the same inner Observable, **ignoring the source value**.
---

- **exaustMap** --> inner observable complete aagra varaikkum Source Observable emit panra values aa ignore pannitum
- *Ignores new values from the source observable while the current inner observable is still active. Only subscribes to a new inner observable if the current one has completed.*
- 
```
import { fromEvent, exhaustMap, interval, take } from 'rxjs';
const clicks = fromEvent(document, 'click');
const result = clicks.pipe(
  exhaustMap(() => interval(1000).pipe(take(5)))
);
result.subscribe(x => console.log(x));
```
---

- **buffer** --> buffer the input until the notification emit the value.
		![[Pasted image 20241220115041.png]]

---

- **bufferCount** --> 
			- ![[Pasted image 20241220115510.png]]

---
###### **GroupBy**
 *group the source observable based on the condition we gave.*
 ```
 import { of, groupBy, mergeMap, reduce } from 'rxjs';
of(
  { id: 1, name: 'JavaScript' },
  { id: 2, name: 'Parcel' },
  { id: 2, name: 'webpack' },
  { id: 1, name: 'TypeScript' },
  { id: 3, name: 'TSLint' }
).pipe(
  groupBy(p => p.id),
  mergeMap(group$ => group$.pipe(reduce((acc, cur) => [...acc, cur], [])))
)
.subscribe(p => console.log(p));

// displays:
// [{ id: 1, name: 'JavaScript' }, { id: 1, name: 'TypeScript'}]
// [{ id: 2, name: 'Parcel' }, { id: 2, name: 'webpack'}]
// [{ id: 3, name: 'TSLint' }]
```

---
##### **map**
- like the array.map method

---
##### **mergeMap**
- merge the value as they comes in.(combine outer and inner observable)
		- ![[Pasted image 20241220174642.png]]
---

#### **pairwise**
makes a pair of emitted data.

![[Pasted image 20241220175949.png]]

---
#### **pluck**

Maps each source value to its nested property.
![[Pasted image 20241220180824.png]]


---

#### **scan**

like *reduce* method but emit the current accumulation state after each update

![[Pasted image 20241220181108.png]]


---

#### **switchMap**

*Cancels the previous inner observable and switches to the new inner observable whenever a new value is emitted by the source observable.*

![[Pasted image 20241220181724.png]]


---

#### **window**

like buffer only but *each windows are a observable*

![[Pasted image 20241220182523.png]]

---
