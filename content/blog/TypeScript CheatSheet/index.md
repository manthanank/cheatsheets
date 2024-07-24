---
title: TypeScript Cheatsheet
date: "2024-03-25"
description: "Complete TypeScript Guide."
tags: ["typescript"]
---

Here is a complete TypeScript cheatsheet that covers everything you need to know about TypeScript. You can use this cheatsheet as a quick reference guide for TypeScript development.

## Table of Contents

- [TypeScript Basics](#typescript-basics)
- [TypeScript Types](#typescript-types)
- [TypeScript Functions](#typescript-functions)
- [TypeScript Classes](#typescript-classes)
- [TypeScript Interfaces](#typescript-interfaces)
- [TypeScript Generics](#typescript-generics)
- [TypeScript Enums](#typescript-enums)
- [TypeScript Decorators](#typescript-decorators)
- [TypeScript Modules](#typescript-modules)
- [TypeScript Namespaces](#typescript-namespaces)

## TypeScript Basics

### Install TypeScript

```bash
npm install -g typescript
```

### Compile TypeScript File

```bash
tsc filename.ts
```

### Run TypeScript File

```bash
node filename.js
```

### TypeScript Comments

```typescript
// Single Line Comment

/*
Multi Line Comment
*/
```

## TypeScript Types

### TypeScript Basic Types

```typescript
let isDone: boolean = false;
let decimal: number = 6;
let color: string = "blue";
let list: number[] = [1, 2, 3];
let fruits: Array<string> = ["Apple", "Banana"];
let x: [string, number] = ["hello", 10];
let notSure: any = 4;
let u: undefined = undefined;
let n: null = null;
```

### TypeScript Type Assertion

```typescript
let someValue: any = "this is a string";
let strLength: number = (someValue as string).length;
```

### TypeScript Type Inference

```typescript
let a = 10; // number
let b = "Hello"; // string
let c = true; // boolean
```

## TypeScript Functions

### TypeScript Function

```typescript
function add(x: number, y: number): number {
  return x + y;
}
```

### TypeScript Optional Parameters

```typescript
function buildName(firstName: string, lastName?: string): string {
  if (lastName) return firstName + " " + lastName;
  else return firstName;
}
```

### TypeScript Default Parameters

```typescript
function calculateDiscount(price: number, discount: number = 0.10): number {
  return price - price * discount;
}
```

## TypeScript Classes

### TypeScript Class

```typescript
class Person {
  name: string;
  constructor(name: string) {
    this.name = name;
  }
  greet() {
    return "Hello, " + this.name;
  }
}
```

### TypeScript Inheritance

```typescript
class Employee extends Person {
  empCode: number;
  constructor(name: string, empCode: number) {
    super(name);
    this.empCode = empCode;
  }
  getSalary() {
    return "Salary is 10000";
  }
}
```

### TypeScript Access Modifiers

```typescript
class Employee {
  private empCode: number;
  protected empName: string;
  public empDept: string;
}
```

## TypeScript Interfaces

### TypeScript Interface

```typescript
interface Person {
  name: string;
  age: number;
}
```

### TypeScript Interface Methods

```typescript
interface Person {
  name: string;
  age: number;
  greet(): string;
}
```

### TypeScript Interface Optional Properties

```typescript
interface Person {
  name: string;
  age?: number;
}
```

## TypeScript Generics

### TypeScript Generics Function

```typescript
function identity<T>(arg: T): T {
  return arg;
}
```

### TypeScript Generics Interface

```typescript
interface GenericIdentityFn<T> {
  (arg: T): T;
}
```

### TypeScript Generics Class

```typescript
class GenericNumber<T> {
  zeroValue: T;
  add: (x: T, y: T) => T;
}
```

## TypeScript Enums

### TypeScript Enum

```typescript
enum Direction {
  Up = 1,
  Down,
  Left,
  Right,
}
```

### TypeScript Reverse Enum

```typescript
enum Direction {
  Up,
  Down,
  Left,
  Right,
}

let direction: string = Direction[2];
console.log(direction); // Down
```

## TypeScript Decorators

### TypeScript Decorator

```typescript
function log(target: any, key: string) {
  console.log(key + " was called");
}

class Calculator {
  @log
  add(x: number, y: number): number {
    return x + y;
  }
}
```

### TypeScript Decorator Factory

```typescript
function log(): MethodDecorator {
  return function (target: any, key: string) {
    console.log(key + " was called");
  };
}

class Calculator {
  @log()
  add(x: number, y: number): number {
    return x + y;
  }
}
```

## TypeScript Modules

### TypeScript Module Export

```typescript
export function add(x: number, y: number): number {
  return x + y;
}

export const PI = 3.14;
```

### TypeScript Module Import

```typescript
import { add, PI } from "./math";

console.log(add(10, 20));
console.log(PI);
```

## TypeScript Namespaces

### TypeScript Namespace

```typescript
namespace Math {
  export function add(x: number, y: number): number {
    return x + y;
  }
}
```

### TypeScript Namespace Import

```typescript
/// <reference path="math.ts" />

console.log(Math.add(10, 20));
```

## Conclusion

This TypeScript cheatsheet covers all the essential TypeScript concepts that you need to know. You can use this cheatsheet as a quick reference guide for TypeScript development. Happy coding!
