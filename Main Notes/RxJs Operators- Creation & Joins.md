Tags: [[Rxjs]] 
---
Operators are **functions**. 
	1. Pipeable operator --> map, tab, catchError
	2. Creation Operator --> of, from

>Higher order Observables:

Observable most commonly emit values like **string, numbers**. but sometimes they emit an observable itself **Observable of observable**.

# [Creation Operator](https://rxjs.dev/guide/operators#creation-operators-1):
- **from** -->  create observable from an **Array**.
- **fromEvent** -->  create observable that emits event.
- **interval** --> emit sequence of number in specified interval.
	- `const numbers = interval(1000).pipe(take(4))`
	- `numbers.subscribe(data => log(data))`
- **of** --> Converts the arguments to an observable sequence.
- **range** --> emits number in a given range 
	- `range(1,100)`
- **throwError** -->  as name suggests

# [Join Creation Operator](https://rxjs.dev/guide/operators#join-creation-operators)
- **combineLatest** : combine multiple observable to create a new observable which value is calculated from the latest value of each observable.
- **concat**: crate an new observable which sequentially emits all values from the first given Observable and then moves on to the next.
- **forkjoin** -> get the list of observables as an input and emit value after all the provided observable complete.
- **merge** --> combine all the observable.
- **partition** --> split the source observable into 2 stream. which satisfy the condition and not.(we need to give a arrow function)
- **race** --> return the fastest one. like a race first one wins.
- **Zip** --> Combines multiple Observables to create an Observable whose values are calculated from the values, in order, of each of its input Observables.
```
import { of, zip, map } from 'rxjs';

const age$ = of(27, 25, 29);
const name$ = of('Foo', 'Bar', 'Beer');
const isDev$ = of(true, true, false);

zip(age$, name$, isDev$).pipe(
  map(([age, name, isDev]) => ({ age, name, isDev }))
)
.subscribe(x => console.log(x));

// Outputs
// { age: 27, name: 'Foo', isDev: true }
// { age: 25, name: 'Bar', isDev: true }
// { age: 29, name: 'Beer', isDev: false }
```

