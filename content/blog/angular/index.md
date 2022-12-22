---
title: Angular
date: "2022-12-22"
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

## Introduction to components

Component is the main building block of an Angular Application.

### The Components consists of three main building blocks

**Template** - Defines the layout and content of the View. Without the template,  there is nothing for Angular to render to the DOM.

**Class** - Class provides the data & logic to the View. It contains the JavaScript code associated with Template (View).

**MetaData** - Metadata Provides additional information about the component to the Angular. Angular uses this information to process the class. We use the @Component decorator to provide the Metadata to the Component.

### Important Component metadata properties

**Selector** - Selector specifies the simple CSS selector. The Angular looks for the CSS selector in the template and renders the component there.

**Providers** - The Providers are the Angular Services, that our component going to use. The Services provide service to the Components or to the other Services.

**Directives** - The directives that this component going to use are listed here.

**styles/styleUrls** - The CSS styles or style sheets, that this component needs. Here we can use either external stylesheet (using styleUrls) or inline styles (using Styles). The styles used here are specific to the component

**template/templateUrl** - The HTML template that defines our View. It tells Angular how to render the Component’s view. The templates can be inline (using a template) or we can use an external template (using a templateUrl). The Component can have only one template. You can either use inline template or external template and not both

## Creating the Component

The creation of the Angular component requires you to follow these steps :

**Create the Component file**

**Import the required external Classes/Functions**

```typescript
import { Component } from '@angular/core';
```

**Create the Component class and export it**

```typescript
export class TestComponent {
  title = 'test';
}
```

**Add @Component decorator**

```typescript
@Component({
})
export class TestComponent {
  title = 'app';
}
```

**Add metadata to @Component decorator**

```typescript
@Component({
  selector: 'app-root',
  templateUrl: './test.component.html',
  styleUrls: ['./test.component.css']
})
```

**Create the Template**

```html
<h1>
    Welcome to {{title}}!
</h1>
```

**Create the CSS Styles**

**Register the Component in Angular Module**

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

**ngModel**

## Angular Directive

### Attribute Diretives

### Structural DIrectives

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
