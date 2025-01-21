---
share_link: https://share.note.sx/s47o0kmv#dx2vvhln9CVGWWwkjN6DdCRCN2ut6ba3W4L48eN3VO0
share_updated: 2025-01-20T15:10:26+05:30
---
#### 🗓️ Date: 2025-01-08 | 🏷️ Tags: [[Interview]]
---
 
# Intro:
- from angular 16 wee have something called as *standalone blocks* --> *standalone Component, standalone Directive, standalone pipes.*
	- **standalone: true**
- ![[Pasted image 20250108185428.png]]
- from angular 16 it self there is no **ngModules** we need to import component before using it in Root or other components
---
# Major changes in angular 17

![[Pasted image 20250109113507.png]]

- Angular added 2 new Lifecycle hooks **AfterRender() & AfterNextRender()**
- *integration with Bun.Js (package manager like npm, yarn, pnpm)*
- *.*ngFor, *ngIf changed* -> **@for @if @empty @else @else if, @switch, @case**
---
# Bun.js
- package manager. javascript runtime, test runner and all.
- npm install bun -g.
- ng new << app-name >> --package-manager=bun

---
# [Deferred loding with triggres](https://angular.dev/guide/templates/defer):
- used to load a components based on some conditions
- **read documentation its more clear**
- using *@if() with the the componenent is not the same because its called conditional loading the chunk for the specific conponent wont be there*
---
# DestroyRef:
- used with **takeUntilDestroy** operator insted on OnDestroy hook.
---
# @component Decorator changes:
 - **StyleUrls to styleUrl** only one scss file for a component.
 ---
# Signals: #signal
- *Signal is a wrapper around a value, which is capable of notifying intersted consumers when that value changes*
 ![[Pasted image 20250109161125.png]]
- **Writeable signals & readOnly Signals**
	1. **const count = signal(0)**
	2. To access counf variable use **count()**
	3. **Computed(() => return value)**
	4. **count.set(0)** to reset the value 
	5. **count.update((currentValue) =>  updatedValue)**
## patent to child communication using Signals

![[Pasted image 20250109183554.png]]

# Effects in Signals:
- effect is a block of code that get automatically triggered when the value of the signal chnages.
- *need to write the effect in the constructor*
- if we want to write the effect any where we need to include **run in context**.
---
# SimpleChanges in angular:
- when ever the @input() values changes we can see the previous value and current value using *SimpleChanges class*
- ![[Pasted image 20250109184314.png]]
---
# Angular 18:

- **toSignal()**
- **toObservable()**
- 