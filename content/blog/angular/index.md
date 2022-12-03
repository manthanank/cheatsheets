---
title: Angular
date: "2022-11-28"
description: "Complete Angular Guide."
tags: ["angular"]
---

## Installation

```jsx
npm install -g @angular/cli
```

### Check version

```jsx
ng version
```

## Generating new application

```jsx
ng new app-name
```

## Run the application

```jsx
ng serve
ng serve --open
ng serve -o
```

## Data binding

- One way binding
- Two ways binding

## Life Cycle Hooks

- ngOnChanges
- ngOnInit
- ngOnDestroy
- ngDoCheck
- ngAfterViewInit
- ngAfterViewChecked
- ngAfterContentInit
- ngAfterContentChecked

## ngOnChanges

Runs after an input/output binding has been changed.

## ngOnInit

Runs after a component has been initialized. Input bindings are ready.

## ngDoCheck

Allows developers to perform custom actions during change detection.

## ngAfterContentInit

Runs after the content of a component has been initialized.

## ngAfterContentChecked

Runs after every check of a component's content.

## ngAfterViewInit

Runs after the view of a component has been initialized.

## ngAfterViewChecked

Runs after every check of a component's view.

## ngOnDestroy

Runs before a component is destroyed.

## Directives

## Forms

- Template Driven Form
- Reactive Form

### Attribute Directives

- ngClass
- ngStyle
- ngModel

### Structural Directives

- ngIf
- ngFor
- ngSwitch
- ngSwitchCase
- ngSwitchDefault

## Pipes

- Date Pipe
- Uppercase Pipe
- Lowercase Pipe
- Currency Pipe
- Percent Pipe

## Decorators

- Input
- Output
- HostListener
- contentChil & contentChildren
- viewChild & viewChildren
