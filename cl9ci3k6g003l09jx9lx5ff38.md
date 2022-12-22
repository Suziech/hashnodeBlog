# [TypeScript] Basics

## TypeScript 
- It is a type safe language. it exists for : 


1. having less bugs 🐞
2. minimising runtime error ⌛️
3. more productive ⌚️

### what is `runtime`?

> **Definition**

> Runtime is a system used primarily in software development to describe the period of time during which a program is running.

[SP//] : https://www.stackpath.com/edge-academy/what-is-runtime/ "What is runtime?"

### ok, then, what is `runtime error`?
> Runtime error refers to an error that takes place while executing a program. To put it simply, an error that happens while the code runs.

### JavaScript doesn't support strongly typed or static typing as typed below.

```
[1,2,3] + true
// result 1,2,3true
```

### What is Typescript compiled to?

 - JavaScript Code. TypeScript needed to be translated to JavaScript to be run.

### Typescript can infer it sometimes
> We don't have to specify a type for our variables in Typescript since TypeScript can infer.

### How do we set the type of a variable explicitly in TS?

```
const x : string = "hi"
```

### how to declare as an array
```
let a : number[] = [1];
let b : string[] = "i1";
let c : boolean[] = [true];
``` 

###  