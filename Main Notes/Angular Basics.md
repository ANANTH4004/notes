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