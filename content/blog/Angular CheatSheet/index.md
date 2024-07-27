---
title: Angular Cheatsheet
date: "2024-07-25"
description: "Complete Angular Guide."
---

Here is a complete Angular cheatsheet that covers everything you need to know about Angular. You can use this cheatsheet as a quick reference guide for Angular development.

## Angular CLI

### Install Angular CLI

```bash
npm install -g @angular/cli
```

### Create New Angular Project

```bash
ng new my-app
```

### Run Angular Project

```bash
cd my-app
ng serve --open
```

### Generate Angular Component

```bash
ng generate component my-component
```

### Generate Angular Directive

```bash
ng generate directive my-directive
```

### Generate Angular Pipe

```bash
ng generate pipe my-pipe
```

### Generate Angular Service

```bash
ng generate service my-service
```

### Generate Angular Module

```bash
ng generate module my-module
```

### Generate Angular Class

```bash
ng generate class my-class
```

### Generate Angular Interface

```bash
ng generate interface my-interface
```

### Generate Angular Enum

```bash
ng generate enum my-enum
```

### Generate Angular Guard

```bash
ng generate guard my-guard
```

### Generate Angular Resolver

```bash
ng generate resolver my-resolver
```

### Generate Angular Library

```bash
ng generate library my-library
```

### Build Angular Project

```bash
ng build
```

### Test Angular Project

```bash
ng test
```

### Lint Angular Project

```bash
ng lint
```

### Analyze Angular Project

```bash
ng analyze
```

### Update Angular CLI

```bash
ng update @angular/cli
```

## Angular Components

### Create Angular Component

```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'app-my-component',
  templateUrl: './my-component.component.html',
  styleUrls: ['./my-component.component.css']
})

export class MyComponent {
  title = 'My Component';
}
```

### Use Angular Component

```html
<h1>{{ title }}</h1>
```

### Angular Component Lifecycle Hooks

- `ngOnChanges`: Called after a bound input property changes.
- `ngOnInit`: Called once the component is initialized.
- `ngDoCheck`: Called during every change detection run.
- `ngAfterContentInit`: Called after content (ng-content) has been projected into the view.
- `ngAfterContentChecked`: Called every time the projected content has been checked.
- `ngAfterViewInit`: Called after the component's view (and child views) has been initialized.
- `ngAfterViewChecked`: Called every time the view (and child views) have been checked.
- `ngOnDestroy`: Called once the component is about to be destroyed.

## Angular Directives

### Create Angular Directive

```typescript
import { Directive, ElementRef } from '@angular/core';

@Directive({
  selector: '[appMyDirective]'
})

export class MyDirective {
  constructor(private el: ElementRef) {
    el.nativeElement.style.color = 'red';
  }
}
```

### Use Angular Directive

```html
<p appMyDirective>My Directive</p>
```

## Angular Pipes

### Create Angular Pipe

```typescript
import { Pipe, PipeTransform } from '@angular/core';

@Pipe({
  name: 'myPipe'
})

export class MyPipe implements PipeTransform {
  transform(value: string): string {
    return value.toUpperCase();
  }
}
```

### Use Angular Pipe

```html
<p>{{ 'my pipe' | myPipe }}</p>
```

## Angular Services

### Create Angular Service

```typescript
import { Injectable } from '@angular/core';

@Injectable({
  providedIn: 'root'
})

export class MyService {
  title = 'My Service';
}
```

### Use Angular Service

```typescript
import { Component } from '@angular/core';
import { MyService } from './my-service.service';

@Component({
  selector: 'app-my-component',
  template: '<h1>{{ title }}</h1>'
})

export class MyComponent {
  title: string;

  constructor
    (private myService: MyService) {
        this.title = myService.title;
    }
}
```

## Angular Routing

### Configure Angular Router

```typescript
import { RouterModule, Routes } from '@angular/router';

const routes: Routes = [];

@NgModule({
  imports: [RouterModule.forRoot(routes)],
  exports: [RouterModule]
})

export class AppRoutingModule {}
```

### Define Angular Routes

```typescript
import { Routes } from '@angular/router';
import { MyComponent } from './my-component.component';

const routes: Routes = [
    {
        path: 'my-component',
        component: MyComponent
    }
];

@NgModule({
  imports: [RouterModule.forRoot(routes)],
  exports: [RouterModule]
})

export class AppRoutingModule {}
```

### Use Angular Router Outlet

```html
<router-outlet></router-outlet>
```

### Use Angular Router Link

```html
<a routerLink="/my-component">My Component</a>
```

## Angular Forms

### Create Angular Form

```typescript
import { Component } from '@angular/core';
import { FormBuilder, FormGroup } from '@angular/forms';

@Component({
  selector: 'app-my-component',
  templateUrl: './my-component.component.html'
})

export class MyComponent {
  form: FormGroup;

  constructor(private fb: FormBuilder) {
    this.form = this.fb.group({
      name: ''
    });
  }
}
```

### Use Angular Form

```html
<form [formGroup]="form">
  <input formControlName="name">
</form>
```

## Angular Http Client

### Import Angular Http Client Module

```typescript
import { HttpClientModule } from '@angular/common/http';

@NgModule({
  imports: [HttpClientModule]
})

export class AppModule {}
```

### Create Angular Http Client Service

```typescript
import { Injectable } from '@angular/core';
import { HttpClient } from '@angular/common/http';

@Injectable({
  providedIn: 'root'
})

export class MyService {
  constructor(private http: HttpClient) {}
}
```

### Use Angular Http Client Service

```typescript
import { Component } from '@angular/core';
import { MyService } from './my-service.service';

@Component({
  selector: 'app-my-component',
  template: '<h1>{{ data }}</h1>'
})

export class MyComponent {
  data: any;

  constructor(private myService: MyService) {
    myService.getData().subscribe((res) => {
      this.data = res;
    });
  }
}
```

## Angular RxJS

### Import Angular RxJS Operators

```typescript
import { map, filter, switchMap } from 'rxjs/operators';
```

### Use Angular RxJS Operators

```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'app-my-component',
  template: '<h1>{{ data }}</h1>'
})

export class MyComponent {
  data: any;

  constructor(private http: HttpClient) {
    http.get('https://api.com/data')
      .pipe(
        map((res) => res.data),
        filter((data) => data.length > 0),
        switchMap((data) => http.get('https://api.com/data/' + data[0].id))
      )
      .subscribe((res) => {
        this.data = res;
      });
  }
}
```

## Angular Testing

### Create Angular Test

```typescript
import { TestBed, ComponentFixture } from '@angular/core/testing';
import { MyComponent } from './my-component.component';

describe('MyComponent', () => {
  let fixture: ComponentFixture<MyComponent>;
  let component: MyComponent;

  beforeEach(() => {
    TestBed.configureTestingModule({
      declarations: [MyComponent]
    });

    fixture = TestBed.createComponent(MyComponent);
    component = fixture.componentInstance;
  });

  it('should create', () => {
    expect(component).toBeTruthy();
  });
});
```

### Run Angular Tests

```bash
ng test
```

## Angular Deployment

Visit the [Angular Deployment](https://angular.dev/tools/cli/deployment) guide for more information on deploying Angular applications.

## Conclusion

This is a complete Angular cheatsheet that covers everything you need to know about Angular. You can use this cheatsheet as a quick reference guide for Angular development. Happy coding!
