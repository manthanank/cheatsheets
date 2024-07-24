---
title: NgRx Cheatsheet
date: "2024-03-25"
description: "Complete NgRx Guide."
tags: ["ngrx"]
---

Here is a complete NgRx cheatsheet that covers everything you need to know about NgRx. You can use this cheatsheet as a quick reference guide for NgRx development.

## Table of Contents

- [NgRx Basics](#ngrx-basics)
- [NgRx Actions](#ngrx-actions)
- [NgRx Reducers](#ngrx-reducers)
- [NgRx Effects](#ngrx-effects)
- [NgRx Selectors](#ngrx-selectors)
- [NgRx Entity](#ngrx-entity)
- [NgRx Router Store](#ngrx-router-store)
- [NgRx Schematics](#ngrx-schematics)

## NgRx Basics

### Install NgRx

```bash
npm install @ngrx/store @ngrx/effects @ngrx/entity @ngrx/router-store
```

### Setup NgRx Store

```typescript
import { StoreModule } from '@ngrx/store';
import { reducers } from './reducers';

@NgModule({
  imports: [
    StoreModule.forRoot(reducers)
  ]
})
export class AppModule { }
```

### Create Action

```typescript
import { createAction, props } from '@ngrx/store';

export const increment = createAction('[Counter Component] Increment');
export const decrement = createAction('[Counter Component] Decrement');
export const reset = createAction('[Counter Component] Reset');
```

### Create Reducer

```typescript
import { createReducer, on } from '@ngrx/store';
import { increment, decrement, reset } from './counter.actions';

export const initialState = 0;

export const counterReducer = createReducer(
  initialState,
  on(increment, state => state + 1),
  on(decrement, state => state - 1),
  on(reset, state => 0)
);
```

### Create Effect

```typescript
import { Injectable } from '@angular/core';
import { Actions, ofType, createEffect } from '@ngrx/effects';
import { map } from 'rxjs/operators';

@Injectable()
export class CounterEffects {

  loadMovies$ = createEffect(() => this.actions$.pipe(
    ofType('[Counter Component] Increment'),
    map(() => ({ type: '[Counter API] Increment Success' }))
  ));

  constructor(private actions$: Actions) {}
}
```

### Create Selector

```typescript
import { createSelector } from '@ngrx/store';

export const selectFeature = state => state.feature;

export const selectFeatureCount = createSelector(
  selectFeature,
  (state: any) => state.count
);
```

## NgRx Actions

### Create Action with Payload

```typescript
import { createAction, props } from '@ngrx/store';

export const addTodo = createAction(
  '[Todo Component] Add Todo',
  props<{ text: string }>()
);
```

### Create Action with Multiple Payloads

```typescript
import { createAction, props } from '@ngrx/store';

export const updateTodo = createAction(
  '[Todo Component] Update Todo',
  props<{ id: number, text: string }>()
);
```

### Create Action with Optional Payload

```typescript
import { createAction, props } from '@ngrx/store';

export const deleteTodo = createAction(
  '[Todo Component] Delete Todo',
  props<{ id: number }>()
);
```

## NgRx Reducers

### Create Reducer with Multiple Actions

```typescript
import { createReducer, on } from '@ngrx/store';
import { addTodo, updateTodo, deleteTodo } from './todo.actions';

export const initialState = [];

export const todoReducer = createReducer(
  initialState,
  on(addTodo, (state, { text }) => [...state, { text }]),
  on(updateTodo, (state, { id, text }) => state.map(todo => todo.id === id ? { ...todo, text } : todo),
  on(deleteTodo, (state, { id }) => state.filter(todo => todo.id !== id))
);
```

### Create Reducer with Entity Adapter

```typescript
import { createEntityAdapter, EntityState } from '@ngrx/entity';
import { Todo } from './todo.model';

export interface TodoState extends EntityState<Todo> {}

export const todoAdapter = createEntityAdapter<Todo>();

export const initialState: TodoState = todoAdapter.getInitialState();
```

## NgRx Effects

### Create Effect with API Call

```typescript
import { Injectable } from '@angular/core';
import { Actions, ofType, createEffect } from '@ngrx/effects';
import { map, mergeMap, catchError } from 'rxjs/operators';
import { of } from 'rxjs';
import { TodoService } from './todo.service';

@Injectable()
export class TodoEffects {

  loadTodos$ = createEffect(() => this.actions$.pipe(
    ofType('[Todo Component] Load Todos'),
    mergeMap(() => this.todoService.getTodos()
      .pipe(
        map(todos => ({ type: '[Todo API] Load Todos Success', todos })),
        catchError(() => of({ type: '[Todo API] Load Todos Failure' }))
      )
    )
  ));

  constructor(
    private actions$: Actions,
    private todoService: TodoService
  ) {}
}
```

### Create Effect with Navigation

```typescript
import { Injectable } from '@angular/core';
import { Actions, ofType, createEffect } from '@ngrx/effects';
import { tap } from 'rxjs/operators';
import { Router } from '@angular/router';

@Injectable()
export class RouterEffects {

  navigate$ = createEffect(() => this.actions$.pipe(
    ofType('[Router Component] Navigate'),
    tap(() => this.router.navigate(['/home']))
  ));

  constructor(
    private actions$: Actions,
    private router: Router
  ) {}
}
```

## NgRx Selectors

### Create Selector with Multiple Features

```typescript
import { createSelector } from '@ngrx/store';
import { selectFeature1, selectFeature2 } from './feature.selectors';

export const selectFeature1Count = createSelector(
  selectFeature1,
  (state: any) => state.count
);

export const selectFeature2Count = createSelector(
  selectFeature2,
  (state: any) => state.count
);
```

### Create Selector with Memoization

```typescript
import { createSelector } from '@ngrx/store';

export const selectFeature = state => state.feature;

export const selectFeatureCount = createSelector(
  selectFeature,
  (state: any) => state.count
);
```

### Create Selector with Props

```typescript
import { createSelector } from '@ngrx/store';

export const selectFeature = state => state.feature;

export const selectFeatureById = createSelector(
  selectFeature,
  (state: any, props: { id: number }) => state.find(item => item.id === props.id)
);
```

## NgRx Entity

### Create Entity Adapter

```typescript
import { createEntityAdapter, EntityState } from '@ngrx/entity';
import { Todo } from './todo.model';

export interface TodoState extends EntityState<Todo> {}

export const todoAdapter = createEntityAdapter<Todo>();

export const initialState: TodoState = todoAdapter.getInitialState();
```

### Add Entity to Reducer

```typescript
import { createReducer } from '@ngrx/store';
import { todoAdapter, initialState } from './todo.adapter';

export const todoReducer = createReducer(
  initialState,
  on(TodoActions.addTodo, (state, { todo }) => todoAdapter.addOne(todo, state)),
  on(TodoActions.updateTodo, (state, { update }) => todoAdapter.updateOne(update, state)),
  on(TodoActions.deleteTodo, (state, { id }) => todoAdapter.removeOne(id, state))
);
```

### Select Entity from Store

```typescript
import { createFeatureSelector, createSelector } from '@ngrx/store';
import { todoAdapter, TodoState } from './todo.adapter';

export const selectTodoState = createFeatureSelector<TodoState>('todos');

export const {
  selectIds,
  selectEntities,
  selectAll,
  selectTotal,
} = todoAdapter.getSelectors(selectTodoState);
```

## NgRx Router Store

### Setup Router Store

```typescript
import { StoreRouterConnectingModule } from '@ngrx/router-store';

@NgModule({
  imports: [
    StoreRouterConnectingModule.forRoot()
  ]
})
export class AppModule { }
```

### Select Router State

```typescript
import { RouterReducerState } from '@ngrx/router-store';

export const selectRouter = createFeatureSelector<RouterReducerState>('router');
```

### Dispatch Router Action

```typescript
import { Router } from '@angular/router';
import { go } from '@ngrx/router-store';

this.store.dispatch(go({ path: ['/home'] }));
```

## NgRx Schematics

### Generate NgRx Store

```bash
ng generate store State --root --statePath store --module app.module.ts
```

### Generate NgRx Actions

```bash
ng generate action Counter --group --flat false
```

### Generate NgRx Reducer

```bash
ng generate reducer counter --reducers index.ts
```

### Generate NgRx Effect

```bash
ng generate effect counter --root --module app.module.ts
```

### Generate NgRx Entity

```bash
ng generate entity todo --module app.module.ts
```

### Generate NgRx Selector

```bash
ng generate selector counter --module app.module.ts
```

### Generate NgRx Feature

```bash
ng generate feature counter --module app.module.ts
```

### Generate NgRx Facade

```bash
ng generate facade counter --module app.module.ts
```

### Generate NgRx Guard

```bash
ng generate guard auth --module app.module.ts
```

### Generate NgRx Resolver

```bash
ng generate resolver user --module app.module.ts
```

### Generate NgRx Component

```bash
ng generate component counter --module app.module.ts
```

### Generate NgRx Service

```bash
ng generate service counter --module app.module.ts
```

### Generate NgRx Pipe

```bash
ng generate pipe capitalize --module app.module.ts
```

### Generate NgRx Directive

```bash
ng generate directive highlight --module app.module.ts
```

### Generate NgRx Module

```bash
ng generate module counter --module app.module.ts
```

### Generate NgRx Class

```bash
ng generate class user --module app.module.ts
```

### Generate NgRx Interface

```bash
ng generate interface user --module app.module.ts
```

### Generate NgRx Enum

```bash
ng generate enum status --module app.module.ts
```

### Generate NgRx Typedef

```bash
ng generate typedef user --module app.module.ts
```

## Conclusion

This NgRx cheatsheet covers all the essential concepts of NgRx. You can use this cheatsheet as a quick reference guide for NgRx development. If you have any questions or feedback, feel free to reach out to me. Happy coding! 🚀
