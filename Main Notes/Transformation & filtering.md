# [Transformation operator](https://rxjs.dev/guide/operators#transformation-operators):

- **concatMap** --> Maps each value emitted by the source Observable to an inner Observable using a provided mapping function (`project` function).
				- ![[Pasted image 20241220120402.png]]
- **concatMapTo** --> Maps every value emitted by the source Observable to the same inner Observable, **ignoring the source value**.
---

- **exaustMap** --> inner observable complete aagra varaikkum Source Observable emit panra values aa ignore pannitum
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
