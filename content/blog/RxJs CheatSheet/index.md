---
title: RxJs Cheatsheet
date: "2024-03-25"
description: "Complete RxJs Guide."
tags: ["rxjs"]
---

Here is a complete RxJs cheatsheet that covers everything you need to know about RxJs. You can use this cheatsheet as a quick reference guide for RxJs development.

## Table of Contents

- [RxJs Basics](#rxjs-basics)
- [RxJs Operators](#rxjs-operators)
- [RxJs Subjects](#rxjs-subjects)
- [RxJs Subscription](#rxjs-subscription)
- [RxJs Error Handling](#rxjs-error-handling)
- [RxJs Utility Functions](#rxjs-utility-functions)

## RxJs Basics

### Install RxJs

```bash
npm install rxjs
```

### Import RxJs

```typescript
import { Observable } from 'rxjs';
```

### Create Observable

```typescript
const observable = new Observable(subscriber => {
  subscriber.next(1);
  subscriber.next(2);
  subscriber.next(3);
  subscriber.complete();
});
```

### Subscribe to Observable

```typescript
observable.subscribe({
  next(x) { console.log('got value ' + x); },
  error(err) { console.error('something wrong occurred: ' + err); },
  complete() { console.log('done'); }
});
```

## RxJs Operators

### Map Operator

```typescript
import { map } from 'rxjs/operators';
import { of } from 'rxjs';

const source = of(1, 2, 3, 4, 5);

const example = source.pipe(
  map(val => val + 10)
);

example.subscribe(val => console.log(val));
```

### Filter Operator

```typescript
import { filter } from 'rxjs/operators';
import { of } from 'rxjs';

const source = of(1, 2, 3, 4, 5);

const example = source.pipe(
  filter(val => val % 2 === 0)
);

example.subscribe(val => console.log(val));
```

### Merge Operator

```typescript
import { merge } from 'rxjs';
import { of } from 'rxjs';

const source1 = of(1, 2, 3);
const source2 = of(4, 5, 6);

const example = merge(source1, source2);

example.subscribe(val => console.log(val));
```

## RxJs Subjects

### Create Subject

```typescript
import { Subject } from 'rxjs';

const subject = new Subject<number>();
```

### Subscribe to Subject

```typescript
subject.subscribe({
  next: (v) => console.log(`observerA: ${v}`)
});
```

### Emit Value

```typescript
subject.next(1);
subject.next(2);
```

## RxJs Subscription

### Create Subscription

```typescript
import { interval } from 'rxjs';

const observable = interval(1000);

const subscription = observable.subscribe(x => console.log(x));
```

### Unsubscribe Subscription

```typescript
subscription.unsubscribe();
```

## RxJs Error Handling

### Catch Error

```typescript
import { catchError } from 'rxjs/operators';
import { of } from 'rxjs';

const source = of('a', 1, 'b', 2, 'c');

const example = source.pipe(
  map(val => val.toUpperCase()),
  catchError(error => of('error'))
);

example.subscribe(val => console.log(val));
```

## RxJs Utility Functions

### Tap Operator

```typescript
import { tap } from 'rxjs/operators';
import { of } from 'rxjs';

const source = of(1, 2, 3, 4, 5);

const example = source.pipe(
  tap(val => console.log(`BEFORE MAP: ${val}`)),
  map(val => val + 10),
  tap(val => console.log(`AFTER MAP: ${val}`))
);

example.subscribe(val => console.log(val));
```

### Delay Operator

```typescript
import { delay } from 'rxjs/operators';
import { of } from 'rxjs';

const source = of(1, 2, 3, 4, 5);

const example = source.pipe(
  delay(1000)
);

example.subscribe(val => console.log(val));
```

### Retry Operator

```typescript
import { retry } from 'rxjs/operators';
import { of } from 'rxjs';

const source = of('a', 1, 'b', 2, 'c');

const example = source.pipe(
  map(val => val.toUpperCase()),
  retry(1)
);

example.subscribe(val => console.log(val));
```

### DebounceTime Operator

```typescript
import { debounceTime } from 'rxjs/operators';
import { of } from 'rxjs';

const source = of(1, 2, 3, 4, 5);

const example = source.pipe(
  debounceTime(1000)
);

example.subscribe(val => console.log(val));
```

### Take Operator

```typescript
import { take } from 'rxjs/operators';
import { of } from 'rxjs';

const source = of(1, 2, 3, 4, 5);

const example = source.pipe(
  take(3)
);

example.subscribe(val => console.log(val));
```

### Skip Operator

```typescript
import { skip } from 'rxjs/operators';
import { of } from 'rxjs';

const source = of(1, 2, 3, 4, 5);

const example = source.pipe(
  skip(2)
);

example.subscribe(val => console.log(val));
```

### TakeUntil Operator

```typescript
import { takeUntil } from 'rxjs/operators';
import { interval, timer } from 'rxjs';

const source = interval(1000);

const example = source.pipe(
  takeUntil(timer(5000))
);

example.subscribe(val => console.log(val));
```

### MergeMap Operator

```typescript
import { mergeMap } from 'rxjs/operators';
import { of } from 'rxjs';

const source = of('Hello', 'RxJS!');
const example = source.pipe(
  mergeMap(val => of(`${val} World!`))
);

example.subscribe(val => console.log(val));
```

### ConcatMap Operator

```typescript
import { concatMap } from 'rxjs/operators';
import { of } from 'rxjs';

const source = of('Hello', 'RxJS!');

const example = source.pipe(
  concatMap(val => of(`${val} World!`))
);

example.subscribe(val => console.log(val));
```

### SwitchMap Operator

```typescript
import { switchMap } from 'rxjs/operators';
import { of } from 'rxjs';

const source = of('Hello', 'RxJS!');
const example = source.pipe(
  switchMap(val => of(`${val} World!`))
);

example.subscribe(val => console.log(val));
```

### CombineLatest Operator

```typescript
import { combineLatest } from 'rxjs';
import { of } from 'rxjs';

const source1 = of('Hello');

const source2 = of('World!');

const example = combineLatest(source1, source2);

example.subscribe(val => console.log(val));
```

### ForkJoin Operator

```typescript
import { forkJoin, of } from 'rxjs';

const source1 = of('Hello');

const source2 = of('World!');
const example = forkJoin(source1, source2);

example.subscribe(val => console.log(val));
```

### Zip Operator

```typescript
import { zip, of } from 'rxjs';

const source1 = of('Hello');

const source2 = of('World!');

const example = zip(source1, source2);

example.subscribe(val => console.log(val));
```

## Conclusion

This cheatsheet covers all the essential RxJs concepts and operators that you need to know to work with RxJs. You can use this cheatsheet as a quick reference guide for RxJs development.
