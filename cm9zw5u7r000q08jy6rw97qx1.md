---
title: "[TypeScript] What is as const"
datePublished: Sun Apr 27 2025 16:56:27 GMT+0000 (Coordinated Universal Time)
cuid: cm9zw5u7r000q08jy6rw97qx1
slug: typescript-what-is-as-const
tags: typescript, as-const, literal-type

---

When working with TypeScript, you might often see the phrase `as const`. It may seem confusing at first, but once you understand it, it becomes a powerful tool to increase your code’s safety and accuracy.

# What is `as const`?

`as const` is a syntax in TypeScript that locks a value into its literal type.

> What is Literal Type?
> 
> A literal type in TypeScript means using a specific value as a type. Noramlly, types are broad, like `string`, `number`, or `boolean`, but a literal type restricts a variable to exactly one value.

Normally, when you declare a variable, TypeScript infers a broad type based on the value. For example:

```typescript
const color = "red";
```

Here, `color` is inferred as `string`, meaning you can assign any string to it later.

But if you use `as const`:

```typescript
const color = "red" as const;
```

The type of `color` becomes `”red”`, fixed and unchangeable.

# Why use `as const`

* To create immutable values
    
* To make type inference more precise with literal types
    
* To prevent modifications to objects or arrays
    

For example, with an object:

```typescript
const user = {
    name: "Alice",
    age: 30
} as const;
```

Here, `user.name` is fixed as `’Alice’` and `user.age` is fixed as 30. Both value and type are locked.

## Summary

* `as const` locks a value to its literal type.
    
* It prevents the value from being changed, making your code safer.
    
* You can use it with arrays, objects, strings, and more.