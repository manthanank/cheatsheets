---
title: Angular
date: "2022-12-22"
description: "Complete Angular Guide."
tags: ["angular"]
---

**Angular** is a platform and framework for building single-page client applications using HTML and TypeScript. Angular is written in TypeScript. It implements core and optional functionality as a set of TypeScript libraries that you import into your applications.

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

## Introduction to components

Component is the main building block of an Angular Application.

### The Components consists of three main building blocks

**Template** - Defines the layout and content of the View. Without the template,  there is nothing for Angular to render to the DOM.

**Class** - Class provides the data & logic to the View. It contains the JavaScript code associated with Template (View).

**MetaData** - Metadata Provides additional information about the component to the Angular. Angular uses this information to process the class. We use the @Component decorator to provide the Metadata to the Component.

### Important Component metadata properties

**Selector** - 

**Providers** - 

**Directives** - 

**styles/styleUrls** - 

**template/templateUrl** - 

## Creating the Component

The creation of the Angular component requires you to follow these steps :

**Create the Component file** -

**Import the required external Classes/Functions** -

```typescript
import { Component } from '@angular/core';
```

**Create the Component class and export it** -

```typescript
export class TestComponent {
  title = 'test';
}
```

**Add @Component decorator** -

```typescript
@Component({
})
export class TestComponent {
  title = 'app';
}
```

**Add metadata to @Component decorator** -

```typescript
@Component({
  selector: 'app-root',
  templateUrl: './test.component.html',
  styleUrls: ['./test.component.css']
})
```

**Create the Template** -

```html
<h1>
    Welcome to {{title}}!
</h1>
```

**Create the CSS Styles** -

**Register the Component in Angular Module** -

```typescript
import { TestComponent } from './app.component';
```

```typescript
@NgModule({ 
  declarations: [ TestComponent ]
})
```

```typescript
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
 
import { AppComponent } from './app.component';
 
@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

### Creating the inline Template & StyleUrls

```typescript
import { Component } from '@angular/core';
 
@Component({
  selector: 'app-root',
  template: '<h1> {{title}} works </h1>',
  styles: ['h1 { font-weight: bold; }']
})
export class AppComponent {
  title = 'app';
}
```

## Data binding

### 1. One way binding

### a. From Component to View

**Interpolation** - 

**Property binding** - 

class binding

ClassName Property binding

Set the Class attribute with class binding

ngClass directive

style binding

Style Binding

ngStyle directive

attribute binding

### b. From View to Component

**Event binding** - 

### 2. Two ways binding

**ngModel** -

## Angular Directives

### Structural DIrectives -

**ngFor** -

```html
<tr *ngFor="let customer of customers;">
    <td>{{customer.customerNo}}</td>
    <td>{{customer.name}}</td>
    <td>{{customer.address}}</td>
    <td>{{customer.city}}</td>
    <td>{{customer.state}}</td>
</tr>
```

**ngSwitch** -

```html
<div [ngSwitch]="Switch_Expression"> 
    <div *ngSwitchCase="MatchExpression1”> First Template</div>
    <div *ngSwitchCase="MatchExpression2">Second template</div> 
    <div *ngSwitchCase="MatchExpression3">Third Template</div> 
    <div *ngSwitchCase="MatchExpression4">Third Template</div> 
    <div *ngSwitchDefault?>Default Template</div>
</div>
```

**ngIf** -

```html
<div *ngIf="condition"> 
    This is shown if condition is true
</div>
```

### Attribute Diretives

**ngModel** -

```html

```

**ngClass** -

```html
<div [ngClass]="'first second'">...</div>
```

**ngStyle** -

```html
<div [ngStyle]="{'color': 'blue', 'font-size': '24px', 'font-weight': 'bold'}">
    some text
</div>
```

### Custom Directives


## Life Cycle Hooks

ngOnChanges

```ts

```

ngOnInit

```ts

```

ngOnDestroy

```ts

```

ngDoCheck

```ts

```

ngAfterViewInit

```ts

```

ngAfterViewChecked

```ts

```

ngAfterContentInit

```ts

```

ngAfterContentChecked

```ts

```

## Forms

Template Driven Form

```ts

```

Reactive Form

```ts

```

## Directives

### Attribute Directives

ngClass

```ts

```

ngStyle

```ts

```

ngModel

```ts

```

### Structural Directives

ngIf

```ts

```

ngFor

```ts

```

ngSwitch

```ts

```

ngSwitchCase

```ts

```

ngSwitchDefault

```ts

```

## Pipes

Date Pipe

```ts

```

Uppercase Pipe

```ts

```

Lowercase Pipe

```ts

```

Currency Pipe

```ts

```

Percent Pipe

```ts

```

## Decorators

Input

```ts

```

Output

```ts

```

HostListener

```ts

```

contentChil & contentChildren

```ts

```

viewChild & viewChildren

```ts

```
