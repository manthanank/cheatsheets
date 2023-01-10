---
title: RxJS
date: "2023-01-10"
description: "Complete RxJS Guide."
tags: ["rxjs"]
---

## Installation

```bash
npm install rxjs
```

## Importing

```typescript
'rxjs' - for example: import { of } from 'rxjs';

'rxjs/operators' - for example: import { map } from 'rxjs/operators';

'rxjs/ajax' - for example: import { ajax } from 'rxjs/ajax';

'rxjs/fetch' - for example: import { fromFetch } from 'rxjs/fetch';

'rxjs/webSocket' - for example: import { webSocket } from 'rxjs/webSocket';

'rxjs/testing' - for example: import { TestScheduler } from 'rxjs/testing';
```

## Observables

```typescript
import { Observable } from 'rxjs';

const observable = new Observable((subscriber) => {
  subscriber.next(1);
  subscriber.next(2);
  subscriber.next(3);
  setTimeout(() => {
    subscriber.next(4);
    subscriber.complete();
  }, 1000);
});
```

```typescript
import { Observable } from 'rxjs';

const observable = new Observable((subscriber) => {
  subscriber.next(1);
  subscriber.next(2);
  subscriber.next(3);
  setTimeout(() => {
    subscriber.next(4);
    subscriber.complete();
  }, 1000);
});

console.log('just before subscribe');
observable.subscribe({
  next(x) {
    console.log('got value ' + x);
  },
  error(err) {
    console.error('something wrong occurred: ' + err);
  },
  complete() {
    console.log('done');
  },
});
console.log('just after subscribe');
```

## Observer

```typescript
const observer = {
  next: x => console.log('Observer got a next value: ' + x),
  error: err => console.error('Observer got an error: ' + err),
  complete: () => console.log('Observer got a complete notification'),
};
```

```typescript
observable.subscribe(observer);
```

## Operators

**1. Combination** -

combineAll

```typescript

```

combineLatest

```typescript

```

concat

```typescript
import { of, concat } from 'rxjs';

concat(
  of(1, 2, 3),
  // subscribed after first completes 
  of(4, 5, 6), 
  // subscribed after second completes
  of(7, 8, 9)
)
// log: 1, 2, 3, 4, 5, 6, 7, 8, 9
.subscribe(console.log);
```

concatAll

```typescript

```

endWith

```typescript

```

forkJoin

```typescript

```

merge

```typescript
// RxJS v6+
import { mapTo } from 'rxjs/operators';
import { interval, merge } from 'rxjs';

//emit every 2.5 seconds
const first = interval(2500);
//emit every 2 seconds
const second = interval(2000);
//emit every 1.5 seconds
const third = interval(1500);
//emit every 1 second
const fourth = interval(1000);

//emit outputs from one observable
const example = merge(
  first.pipe(mapTo('FIRST!')),
  second.pipe(mapTo('SECOND!')),
  third.pipe(mapTo('THIRD')),
  fourth.pipe(mapTo('FOURTH'))
);
//output: "FOURTH", "THIRD", "SECOND!", "FOURTH", "FIRST!", "THIRD", "FOURTH"
const subscribe = example.subscribe(val => console.log(val));
```

mergeAll

```typescript

```

pairwise

```typescript

```

race

```typescript

```

startWith

```typescript
// RxJS v6+
import { startWith } from 'rxjs/operators';
import { of } from 'rxjs';

//emit (1,2,3)
const source = of(1, 2, 3);
//start with 0
const example = source.pipe(startWith(0));
//output: 0,1,2,3
const subscribe = example.subscribe(val => console.log(val));
```

**2. Conditional** -

defaultIfEmpty

```typescript

```

every

```typescript

```

iif

```typescript

```

sequenceequal

```typescript

```

**3. Creation** -

ajax

```typescript

```

create

```typescript

```

defer

```typescript

```

empty

```typescript

```

from

```typescript
// RxJS v6+
import { from } from 'rxjs';

//emit array as a sequence of values
const arraySource = from([1, 2, 3, 4, 5]);
//output: 1,2,3,4,5
const subscribe = arraySource.subscribe(val => console.log(val));
```

fromEvent

```typescript

```

generate

```typescript

```

interval

```typescript

```

of

```typescript
// RxJS v6+
import { of } from 'rxjs';
//emits any number of provided values in sequence
const source = of(1, 2, 3, 4, 5);
//output: 1,2,3,4,5
const subscribe = source.subscribe(val => console.log(val));
```

range

```typescript

```

throw

```typescript

```

timer

```typescript

```

**4. Error Handling** -

catch/catchError

```typescript

```

retry

```typescript

```

retryWhen

```typescript

```

**5. Multicasting** -

publish

```typescript

```

multicast

```typescript

```

share

```typescript

```

shareReplay

```typescript

```

**6. Filtering** -

audit

```typescript

```

auditTime

```typescript

```

debounce

```typescript

```

debounceTime

```typescript

```

distinct

```typescript

```

distinctUntilChanged

```typescript

```

distinctUntilKeyChanged

```typescript

```

filter

```typescript

```

find

```typescript

```

first

```typescript

```

ignoreElements

```typescript

```

last

```typescript

```

sample

```typescript

```

single

```typescript

```

skip

```typescript

```

skipUntil

```typescript

```

skipWhile

```typescript

```

take

```typescript

```

takeLast

```typescript

```

takeUntil

```typescript

```

takeWhile

```typescript

```

throttle

```typescript

```

throttleTime

```typescript

```

**7. Transformation** -

buffer

```typescript

```

bufferCount

```typescript

```

bufferTime

```typescript

```

bufferToggle

```typescript

```

bufferWhen

```typescript

```

concatMap

```typescript

```

concatMapTo

```typescript

```

exhaustMap

```typescript

```

expand

```typescript

```

groupby

```typescript

```

map

```typescript
// RxJS v6+
import { from } from 'rxjs';
import { map } from 'rxjs/operators';

//emit (1,2,3,4,5)
const source = from([1, 2, 3, 4, 5]);
//add 10 to each value
const example = source.pipe(map(val => val + 10));
//output: 11,12,13,14,15
const subscribe = example.subscribe(val => console.log(val));
```

mapTo

```typescript

```

mergeMap/flatMap

```typescript

```

mergeScan

```typescript

```

partition

```typescript

```

pluck

```typescript

```

reduce

```typescript

```

scan

```typescript

```

switchMap

```typescript
// RxJS v6+
import { from } from 'rxjs';
import { map } from 'rxjs/operators';

//emit (1,2,3,4,5)
const source = from([1, 2, 3, 4, 5]);
//add 10 to each value
const example = source.pipe(map(val => val + 10));
//output: 11,12,13,14,15
const subscribe = example.subscribe(val => console.log(val));
```

swicthMapTo

```typescript

```

toArray

```typescript

```

window

```typescript

```

windowCount

```typescript

```

windowTime

```typescript

```

windowToggle

```typescript

```

windowWhen

```typescript

```

**8. Utility** -

tap / do

```typescript
// RxJS v6+
import { of } from 'rxjs';
import { tap, map } from 'rxjs/operators';

const source = of(1, 2, 3, 4, 5);
// transparently log values from source with 'tap'
const example = source.pipe(
  tap(val => console.log(`BEFORE MAP: ${val}`)),
  map(val => val + 10),
  tap(val => console.log(`AFTER MAP: ${val}`))
);

//'tap' does not transform values
//output: 11...12...13...14...15
const subscribe = example.subscribe(val => console.log(val));
```

deplay

deplayWhen

dematerialize

finalize / finally

let

repeat

repeatWhen

timeInterval

timeout

timeoutWith

toPromise

## Subscription

```typescript
import { interval } from 'rxjs';

const observable = interval(1000);
const subscription = observable.subscribe(x => console.log(x));
// Later:
// This cancels the ongoing Observable execution which
// was started by calling subscribe with an Observer.
subscription.unsubscribe();
```

```typescript
import { interval } from 'rxjs';

const observable1 = interval(400);
const observable2 = interval(300);

const subscription = observable1.subscribe(x => console.log('first: ' + x));
const childSubscription = observable2.subscribe(x => console.log('second: ' + x));

subscription.add(childSubscription);

setTimeout(() => {
  // Unsubscribes BOTH subscription and childSubscription
  subscription.unsubscribe();
}, 1000);
```

## Subjects

**1. AsyncSubject** -

```typescript

```

**2. BehaviorSubject** -

```typescript

```

**3. ReplaySubject** -

```typescript

```

**4. Subject** -

```typescript

```

## Scheduler

```typescript
import { Observable, observeOn, asyncScheduler } from 'rxjs';

const observable = new Observable((observer) => {
  observer.next(1);
  observer.next(2);
  observer.next(3);
  observer.complete();
}).pipe(
  observeOn(asyncScheduler)
);

console.log('just before subscribe');
observable.subscribe({
  next(x) {
    console.log('got value ' + x);
  },
  error(err) {
    console.error('something wrong occurred: ' + err);
  },
  complete() {
    console.log('done');
  },
});
console.log('just after subscribe');
```
