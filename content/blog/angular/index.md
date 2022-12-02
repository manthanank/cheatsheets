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

1. One way binding

2. Two ways binding

## Life Cycle Hooks

1. ngOnChanges

2. ngOnInit

3. ngOnDestroy

4. ngDoCheck

5. ngAfterViewInit

6. ngAfterViewChecked

7. ngAfterContentInit

8. ngAfterContentChecked

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

1. Template Driven Form

2. Reactive Form

### Attribute Directives

1. ngClass

2. ngStyle

3. ngModel

### Structural Directives

1. ngIf

2. ngFor

3. ngSwitch

4. ngSwitchCase

5. ngSwitchDefault

## Pipes

1. Date Pipe

2. Uppercase Pipe

3. Lowercase Pipe

4. Currency Pipe

5. Percent Pipe

## Decorators

1. Input

2. Output

3. HostListener

4. contentChil & contentChildren

5. viewChild & viewChildren
