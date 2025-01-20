Link: [[TypeScript]]

# Primitive Types: [[JavaScript Basics]]

---
# [Generic functions:](https://www.typescriptlang.org/docs/handbook/2/functions.html#generic-functions)
```
function firstElement<Type>(arr: Type[]): Type | undefined {
return arr[0];
}
```
---
# Interface: 
---
# Unknown:
- the `unknown` type represent the any value. *but it is not safer because it's not legal to do anything with an unknown value*
```
function f1(a: any) {
  a.b(); // OK
}
function f2(a: unknown) {
  a.b();
'a' is of type 'unknown'.
}
```
---
# **never**
- some function nerver return any value;
- it is intented to *throw any error or exit the application.*
- 