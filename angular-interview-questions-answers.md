Here are Angular interview questions and answers starting from number 1:

### 1. **What is Angular?**
   **Answer:** Angular is a platform and framework for building single-page client applications using HTML and TypeScript. It is developed and maintained by Google and is a complete rewrite of AngularJS. Angular applications are structured into modules, components, services, and other entities that work together to create a web application.

### 2. **What are Angular modules?**
   **Answer:** Angular modules are containers for different parts of your application. They help organize an application into cohesive blocks of functionality. Every Angular application has at least one module, the root module, which is typically named `AppModule`. Modules can contain components, services, directives, pipes, and other Angular features.

### 3. **What is a component in Angular?**
   **Answer:** A component is a fundamental building block of an Angular application. It consists of three key elements:
   - **A TypeScript class** that contains data and logic.
   - **An HTML template** that defines the view.
   - **A CSS selector** that specifies how the component is used in HTML.

### 4. **What is data binding in Angular?**
   **Answer:** Data binding is the synchronization of data between the model (business logic) and the view (UI). Angular supports several types of data binding:
   - **Interpolation:** `{{ expression }}` - One-way data binding from the component to the view.
   - **Property Binding:** `[property]="expression"` - One-way data binding from the component to an element's property.
   - **Event Binding:** `(event)="handler"` - One-way data binding from the view to the component.
   - **Two-way Binding:** `[(ngModel)]="property"` - Two-way data binding where changes in the view are reflected in the component and vice versa.

### 5. **What are directives in Angular?**
   **Answer:** Directives are classes that add behavior to elements in your Angular applications. Angular has three types of directives:
   - **Components:** Directives with a template.
   - **Structural directives:** Change the DOM layout by adding and removing DOM elements (e.g., `*ngIf`, `*ngFor`).
   - **Attribute directives:** Change the appearance or behavior of an element, component, or another directive (e.g., `ngClass`, `ngStyle`).

### 6. **Explain Angular services and dependency injection.**
   **Answer:** Services in Angular are used to encapsulate and share logic across multiple components. They are typically used for data retrieval, business logic, and other utilities. Angular's dependency injection (DI) system allows you to inject services into components and other services, promoting modularity and testability.

### 7. **What is Angular CLI and how is it used?**
   **Answer:** Angular CLI (Command Line Interface) is a tool that helps to automate the development workflow of Angular applications. It provides commands to create, build, serve, and test Angular projects. The CLI also simplifies the setup and configuration of new Angular projects.

### 8. **What are Angular pipes?**
   **Answer:** Pipes in Angular are used to transform data before displaying it in the view. They can be used for formatting dates, numbers, and other data types. Angular provides several built-in pipes, such as `DatePipe`, `CurrencyPipe`, and `UpperCasePipe`, and you can also create custom pipes.

### 9. **What is routing in Angular?**
   **Answer:** Angular's routing system enables navigation between different views or pages in a single-page application (SPA). The `RouterModule` is used to define routes and associate them with components. When a user navigates to a specific URL, the router renders the corresponding component.

### 10. **What is the difference between `ngIf` and `*ngIf`?**
   **Answer:** `ngIf` is a directive used to conditionally include or exclude elements from the DOM. When using `*ngIf`, the asterisk (`*`) is a shorthand that tells Angular to treat the directive as a structural directive. This means Angular will add or remove elements based on the condition.

Certainly! Here are more Angular interview questions and answers starting from number 11:

### 11. **What is the purpose of `ngFor` directive?**
   **Answer:** The `ngFor` directive in Angular is used to iterate over a collection (such as an array) and render a template for each item in the collection. It is a structural directive, which means it can add or remove elements from the DOM based on the iteration. The syntax is: `*ngFor="let item of items"`.

### 12. **What is the difference between `@Component` and `@Directive` in Angular?**
   **Answer:** 
   - `@Component` is a decorator that marks a class as an Angular component and provides configuration metadata, such as the selector, template, and style properties. Components have a view (HTML template) associated with them.
   - `@Directive` is a decorator that marks a class as a directive. Directives are used to add behavior to existing elements. Unlike components, directives do not have their own view.

### 13. **Explain Angular lifecycle hooks.**
   **Answer:** Angular provides lifecycle hooks that give you the opportunity to tap into key moments of a component's life:
   - **`ngOnChanges`:** Called before `ngOnInit` and whenever one or more data-bound input properties change.
   - **`ngOnInit`:** Called once, after the first `ngOnChanges`.
   - **`ngDoCheck`:** Detect and act upon changes that Angular can't or won't detect on its own.
   - **`ngAfterContentInit`:** Called after Angular has fully initialized all content of the directive/component.
   - **`ngAfterContentChecked`:** Called after every check of the content.
   - **`ngAfterViewInit`:** Called after Angular initializes the component's views and child views.
   - **`ngAfterViewChecked`:** Called after every check of the component's views and child views.
   - **`ngOnDestroy`:** Cleanup just before Angular destroys the directive/component.

### 14. **What are Angular forms and how do they differ?**
   **Answer:** Angular provides two approaches to handling user input through forms:
   - **Template-driven forms:** Simple forms using Angular directives and attributes in the template. They are easier to use but less flexible.
   - **Reactive forms:** More powerful and scalable, allowing for more complex validation and dynamic forms. They are defined using the `FormGroup` and `FormControl` classes in the component's TypeScript file.

### 15. **What is `ViewChild` and `ContentChild` in Angular?**
   **Answer:** 
   - **`@ViewChild`:** Used to access a child component, directive, or DOM element from within the parent component's class. It is typically used for direct DOM manipulation or interacting with child components.
   - **`@ContentChild`:** Used to access content projected into a component (using `<ng-content>`). It allows you to query content that has been passed from a parent component.

### 16. **What is Angular's change detection mechanism?**
   **Answer:** Angular's change detection mechanism is responsible for updating the view whenever the data in the model changes. Angular uses a `zone.js` library to track asynchronous operations and then trigger change detection automatically. This ensures that the view stays in sync with the model. The change detection can be optimized using `OnPush` strategy, which limits the checks to specific scenarios, like changes to input properties or events.

### 17. **What is lazy loading in Angular?**
   **Answer:** Lazy loading in Angular is a technique to load modules on demand instead of loading all modules at once when the application starts. It improves the application's load time and performance. Lazy loading is usually configured in the `AppRoutingModule` using the `loadChildren` property.

### 18. **What is Angular Universal?**
   **Answer:** Angular Universal is a technology that allows Angular applications to be rendered on the server side. This server-side rendering (SSR) improves the performance of the application, especially on slow networks, and makes the application more SEO-friendly by serving a fully rendered page to the search engine bots.

### 19. **What is Angular Ivy?**
   **Answer:** Angular Ivy is the new rendering engine introduced in Angular 9. It is designed to be smaller, faster, and easier to use compared to the previous View Engine. Ivy enables several improvements, such as better debugging, smaller bundle sizes, and more efficient change detection.

### 20. **What is AOT compilation in Angular?**
   **Answer:** Ahead-of-Time (AOT) compilation in Angular is the process of compiling your Angular application and its templates during the build process, before the browser downloads and runs the code. AOT improves performance by reducing the amount of JavaScript to be parsed and by detecting template errors earlier in the development process.

### Angular Interview Questions and Answers (21-30)

#### 21. **What is Change Detection in Angular?**
   - **Answer:** Change detection in Angular is the process by which the framework determines whether the state of the application has changed and updates the view accordingly. Angular uses two types of change detection strategies:
     1. **Default:** The change detection runs for every component in the component tree.
     2. **OnPush:** The change detection runs only when the component’s input properties change, making it more performant for large applications.

#### 22. **Explain the concept of AOT compilation in Angular.**
   - **Answer:** AOT (Ahead-of-Time) compilation is a process where the Angular compiler converts the Angular HTML and TypeScript code into efficient JavaScript code before the browser downloads and runs it. This process leads to faster rendering, smaller Angular framework download sizes, and detects template errors earlier.

#### 23. **What is the difference between `ngOnInit()` and a constructor in Angular?**
   - **Answer:** The `constructor` is a TypeScript feature used for initializing class members and dependency injection. `ngOnInit()` is an Angular lifecycle hook that is called after Angular has initialized the component's data-bound properties. Unlike the constructor, `ngOnInit()` is a better place for initialization logic that depends on Angular bindings.

#### 24. **What is the purpose of Angular Services?**
   - **Answer:** Services in Angular are used to encapsulate reusable logic or functionalities that can be shared across different components. They help keep the code modular, maintainable, and testable. Common use cases for services include fetching data from APIs, logging, and utility functions.

#### 25. **What is Dependency Injection (DI) in Angular?**
   - **Answer:** Dependency Injection (DI) is a design pattern used in Angular to pass dependencies (services or objects) into a class. Angular's DI system allows services to be injected into components, services, and other services, making it easier to manage dependencies and enhancing code reusability.

#### 26. **Explain the use of `@Input()` and `@Output()` in Angular.**
   - **Answer:** 
     - **`@Input()`** is a decorator that allows data to be passed from a parent component to a child component. It is used to bind a property in the child component to a property in the parent component.
     - **`@Output()`** is a decorator that allows a child component to emit events to the parent component. It is used to create custom events that a parent component can listen to and respond to.

#### 27. **What is a `Subject` in Angular, and how is it different from `Observable`?**
   - **Answer:** A `Subject` is a special type of `Observable` that allows values to be multicasted to multiple observers. Unlike a regular `Observable`, which is unicast and only emits to one subscriber, a `Subject` can emit values to many subscribers at once. `Subjects` are often used in Angular to share data between components.

#### 28. **What are Angular Pipes, and how are they used?**
   - **Answer:** Pipes in Angular are a way to transform data in the template before displaying it to the user. Angular provides several built-in pipes, such as `DatePipe`, `CurrencyPipe`, and `UpperCasePipe`. Custom pipes can also be created to handle specific transformations.

#### 29. **How does Angular handle forms, and what are the differences between Template-driven and Reactive forms?**
   - **Answer:** Angular provides two ways to handle forms:
     1. **Template-driven forms:** These are forms where logic is defined using Angular directives in the template (e.g., `ngModel`). They are easier to work with but less scalable for complex forms.
     2. **Reactive forms:** These forms are more flexible and scalable, where the form model is defined in the component class using `FormControl` and `FormGroup`. Reactive forms are better suited for dynamic and complex form requirements.

#### 30. **What is `ng-content` in Angular?**
   - **Answer:** `ng-content` is a directive used to project content from a parent component into a child component. It allows the parent component to pass HTML content to the child component and enables the child component to display that content at a specific location within its template.

---

Here are more Angular interview questions and answers starting from number 31:

### 31. What is Angular CLI, and what are its benefits?
**Answer:**  
Angular CLI (Command Line Interface) is a powerful tool that provides a command-line interface for creating, building, and maintaining Angular applications. It helps in streamlining the development process by automating repetitive tasks, ensuring consistency across projects, and enforcing best practices.

**Benefits of Angular CLI:**
- **Project Initialization:** Quickly set up a new Angular project with best practices and a predefined structure using `ng new`.
- **Code Generation:** Generate components, services, modules, pipes, directives, etc., using commands like `ng generate`.
- **Development Server:** Easily start a development server with live-reloading using `ng serve`.
- **Building and Bundling:** Efficiently build the project for different environments (e.g., development, production) with commands like `ng build`.
- **Testing:** Run unit tests and end-to-end tests with `ng test` and `ng e2e`.
- **Linting:** Enforce coding standards using `ng lint`.
- **Updates:** Keep Angular dependencies up to date with `ng update`.

### 32. What are Angular Directives? Explain the types.
**Answer:**  
Angular Directives are special markers in the DOM that tell Angular to do something with a DOM element or its children. They are used to manipulate the DOM and add dynamic behavior to elements.

**Types of Directives:**
1. **Structural Directives:** 
   - Change the structure of the DOM by adding or removing elements.
   - Examples: `*ngIf`, `*ngFor`, `*ngSwitch`.

2. **Attribute Directives:** 
   - Change the appearance or behavior of an element, component, or another directive.
   - Examples: `ngClass`, `ngStyle`, `ngModel`.

3. **Custom Directives:** 
   - Developers can create custom directives to encapsulate common DOM manipulation or behavior.
   - Example: A directive that changes the background color of an element on hover.

### 33. What is Dependency Injection in Angular?
**Answer:**  
Dependency Injection (DI) is a design pattern used in Angular to implement IoC (Inversion of Control). It allows dependencies (such as services) to be injected into a component or service, rather than being created by the component or service itself.

**Advantages of DI in Angular:**
- **Decoupling:** Promotes loose coupling between components and their dependencies.
- **Testability:** Makes it easier to mock dependencies during unit testing.
- **Reusability:** Allows services to be reused across different parts of the application.
- **Configuration:** Services can be configured and swapped easily without changing the components that use them.

### 34. How does Angular handle forms, and what are the two types of forms in Angular?
**Answer:**  
Angular provides a robust way to handle forms, which are essential in collecting and validating user input. Angular supports two types of forms:

1. **Template-Driven Forms:**
   - Built using directives and bindings in the template.
   - Simple and suitable for basic forms.
   - Uses Angular directives like `ngModel` for two-way data binding.
   - Validation is defined in the template.

   ```html
   <form #form="ngForm" (ngSubmit)="onSubmit(form)">
     <input name="username" ngModel required>
     <button type="submit">Submit</button>
   </form>
   ```

2. **Reactive Forms:**
   - Built programmatically in the component class.
   - More powerful and suitable for complex forms.
   - Uses `FormGroup`, `FormControl`, and `FormArray` for managing form state.
   - Validation logic is defined in the component class.

   ```typescript
   import { FormGroup, FormControl } from '@angular/forms';

   this.myForm = new FormGroup({
     username: new FormControl(''),
   });
   ```

### 35. What is Lazy Loading in Angular?
**Answer:**  
Lazy Loading in Angular is a technique used to load feature modules asynchronously when the user navigates to a route that requires them. It helps in reducing the initial load time of the application by loading only the necessary modules at the start and deferring the loading of other modules until they are needed.

**Implementation:**
- Define routes with the `loadChildren` property to specify the path to the module.
- Use Angular's built-in router to handle lazy loading.

```typescript
const routes: Routes = [
  {
    path: 'feature',
    loadChildren: () => import('./feature/feature.module').then(m => m.FeatureModule)
  }
];
```

### 36. What are Angular Modules, and how are they used?
**Answer:**  
Angular Modules (`@NgModule`) are containers that group related components, directives, pipes, and services together. They help in organizing the application into cohesive blocks of functionality.

**Key Features of Angular Modules:**
- **Root Module:** The main module that bootstraps the Angular application (usually `AppModule`).
- **Feature Modules:** Modules that focus on specific areas of the application (e.g., `UserModule`, `AdminModule`).
- **Shared Module:** A module containing shared components, directives, and pipes that are used across multiple modules.
- **Core Module:** A module that contains singleton services and is imported only once in the root module.

```typescript
@NgModule({
  declarations: [AppComponent, HeaderComponent, FooterComponent],
  imports: [BrowserModule, AppRoutingModule],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule {}
```

### 37. What is Change Detection in Angular, and how does it work?
**Answer:**  
Change Detection in Angular is a mechanism that tracks changes in the state of components and updates the DOM accordingly. Angular uses a change detection mechanism to ensure that the view is always synchronized with the model.

**How it works:**
- Angular creates a tree of components, each associated with a change detector.
- When a change occurs (e.g., user input, HTTP request, timer), Angular runs the change detection cycle to update the DOM.
- Angular can use two strategies for change detection:
  - **Default:** Checks every component for changes.
  - **OnPush:** Checks only components with changed inputs.

### 38. What are Angular Pipes, and how do you create a custom pipe?
**Answer:**  
Angular Pipes are functions that transform data in templates. They take input data, transform it, and return the transformed data to the template. Pipes are used for formatting, filtering, or manipulating data.

**Built-in Pipes:**
- `DatePipe`, `CurrencyPipe`, `UpperCasePipe`, `LowerCasePipe`, etc.

**Creating a Custom Pipe:**
1. Create a new class and implement the `PipeTransform` interface.
2. Decorate the class with the `@Pipe` decorator, specifying the pipe name.
3. Implement the `transform()` method, which will contain the transformation logic.

```typescript
import { Pipe, PipeTransform } from '@angular/core';

@Pipe({
  name: 'customPipe'
})
export class CustomPipe implements PipeTransform {
  transform(value: string): string {
    return value.toUpperCase();
  }
}
```

### 39. What is Angular Universal, and why is it used?
**Answer:**  
Angular Universal is a technology that allows Angular applications to be rendered on the server-side, providing server-side rendering (SSR). It generates static HTML on the server, which is sent to the client, enhancing performance and SEO.

**Benefits of Angular Universal:**
- **Faster Initial Load:** Since the HTML is pre-rendered on the server, the application appears faster to the user.
- **Improved SEO:** Search engines can index the content more easily because the content is available in the initial HTML response.
- **Better Performance on Slow Networks:** Reduces the time to first paint (TTFP) by sending pre-rendered HTML to the client.

### 40. What are Angular Animations, and how are they implemented?
**Answer:**  
Angular Animations allow developers to create complex animations within Angular applications. Angular provides a powerful API for defining and triggering animations.

**How to implement Angular Animations:**
1. Import the `BrowserAnimationsModule` in the `AppModule`.
2. Define animations in the component using the `@Component` decorator or in a separate file.
3. Use Angular's animation DSL to define states, transitions, triggers, and keyframes.

```typescript
import { trigger, state, style, transition, animate } from '@angular/animations';

@Component({
  selector: 'app-animate',
  templateUrl: './animate.component.html',
  styleUrls: ['./animate.component.css'],
  animations: [
    trigger('openClose', [
      state('open', style({ height: '200px', opacity: 1 })),
      state('closed', style({ height: '100px', opacity: 0.5 })),
      transition('open <=> closed', [animate('0.5s')]),
    ])
  ]
})
export class AnimateComponent {
  isOpen = true;

  toggle() {
    this.isOpen = !this.isOpen;
  }
}
```

### Angular Interview Questions and Answers (Starting from 41)

---

**41. What is the purpose of `ng-content` in Angular?**

`ng-content` is used to project content into Angular components. It allows you to create components that can receive HTML content from the parent component and project it into the child component. This is useful when creating reusable components like modals, tabs, or cards, where you want the ability to customize the content.

```html
<!-- Parent Component -->
<app-card>
  <h1>Title</h1>
  <p>Description goes here.</p>
</app-card>

<!-- Child Component -->
<div class="card">
  <ng-content></ng-content>
</div>
```

---

**42. What is Angular's Dependency Injection (DI) system?**

Angular's Dependency Injection (DI) system is a design pattern used to implement inversion of control for resolving dependencies. DI allows you to inject services or dependencies into a component, directive, or service, rather than hard-coding them into the component. This makes the code more modular, testable, and maintainable.

```typescript
@Injectable({
  providedIn: 'root',
})
export class MyService {
  constructor() {}
}

@Component({
  selector: 'app-my-component',
  templateUrl: './my-component.component.html',
})
export class MyComponent {
  constructor(private myService: MyService) {}
}
```

---

**43. How do you create a custom directive in Angular?**

A custom directive in Angular is created using the `@Directive` decorator. Directives are used to add behavior to elements in the DOM. There are two types of directives: structural directives and attribute directives.

```typescript
import { Directive, ElementRef, Renderer2, HostListener } from '@angular/core';

@Directive({
  selector: '[appHighlight]',
})
export class HighlightDirective {
  constructor(private el: ElementRef, private renderer: Renderer2) {}

  @HostListener('mouseenter') onMouseEnter() {
    this.renderer.setStyle(this.el.nativeElement, 'backgroundColor', 'yellow');
  }

  @HostListener('mouseleave') onMouseLeave() {
    this.renderer.removeStyle(this.el.nativeElement, 'backgroundColor');
  }
}
```

---

**44. What are Angular lifecycle hooks?**

Angular lifecycle hooks are methods that are invoked at specific stages of a component's lifecycle. They allow you to perform custom logic during the creation, update, and destruction of components.

Some commonly used lifecycle hooks include:

- `ngOnInit()`: Called once, after the component's first display.
- `ngOnChanges()`: Called when any data-bound property of a directive changes.
- `ngOnDestroy()`: Called just before the component is destroyed.
- `ngAfterViewInit()`: Called after the view and child views have been initialized.

---

**45. What is the difference between `@ViewChild()` and `@ContentChild()`?**

- `@ViewChild()`: This decorator is used to access a child component, directive, or DOM element from the view (template) of the current component. It is used to manipulate the DOM or get access to the underlying element/component after the view has been initialized.

- `@ContentChild()`: This decorator is used to access projected content (i.e., content that is passed from a parent component) within a child component. It is used to interact with elements or components that are passed into the component's content projection.

---

**46. What is the Angular Router, and how does it work?**

The Angular Router is a powerful tool that enables navigation between different views or pages in an Angular application. It maps URLs to components, allowing users to navigate through the app by changing the URL.

The Angular Router works by configuring routes in the `RouterModule` and associating them with components. When the user navigates to a particular route, the router loads the associated component.

```typescript
const routes: Routes = [
  { path: '', component: HomeComponent },
  { path: 'about', component: AboutComponent },
  { path: '**', component: NotFoundComponent },
];

@NgModule({
  imports: [RouterModule.forRoot(routes)],
  exports: [RouterModule],
})
export class AppRoutingModule {}
```

---

**47. How can you implement lazy loading in Angular?**

Lazy loading is a technique in Angular that allows you to load modules only when they are needed, rather than loading them upfront. This can significantly improve the initial load time of your application.

To implement lazy loading:

1. Create a module for the feature you want to lazy load.
2. Use the `loadChildren` property in the route configuration.

```typescript
const routes: Routes = [
  {
    path: 'feature',
    loadChildren: () =>
      import('./feature/feature.module').then((m) => m.FeatureModule),
  },
];
```

---

**48. What is an Angular service, and how do you create one?**

An Angular service is a class that encapsulates business logic, data, or both and can be shared across components. Services are typically used to perform tasks like HTTP requests, data manipulation, or shared state management.

You can create a service using the Angular CLI:

```bash
ng generate service my-service
```

This command generates a service file with a basic structure:

```typescript
import { Injectable } from '@angular/core';

@Injectable({
  providedIn: 'root',
})
export class MyService {
  constructor() {}
}
```

---

**49. What is Angular's `HttpClientModule`, and how do you use it?**

`HttpClientModule` is a module in Angular that provides a simplified API for making HTTP requests to a backend server. It is built on top of the browser's native `fetch` API and is used for tasks like getting data, posting data, and handling responses.

To use `HttpClientModule`:

1. Import `HttpClientModule` into your `AppModule`.
2. Inject `HttpClient` into your service or component.

```typescript
import { HttpClient } from '@angular/common/http';
import { Injectable } from '@angular/core';

@Injectable({
  providedIn: 'root',
})
export class DataService {
  constructor(private http: HttpClient) {}

  getData() {
    return this.http.get('https://api.example.com/data');
  }
}
```

---

**50. What are Angular pipes, and how do you create a custom pipe?**

Angular pipes are a way to transform data in templates. They take in a value and return a formatted value. Angular provides several built-in pipes like `date`, `uppercase`, and `currency`. You can also create custom pipes.

To create a custom pipe:

1. Use the `@Pipe` decorator.
2. Implement the `PipeTransform` interface.

```typescript
import { Pipe, PipeTransform } from '@angular/core';

@Pipe({
  name: 'capitalize',
})
export class CapitalizePipe implements PipeTransform {
  transform(value: string): string {
    return value.charAt(0).toUpperCase() + value.slice(1);
  }
}
```

Use the custom pipe in your template:

```html
<p>{{ 'hello world' | capitalize }}</p>
```

---

Let me know if you need more questions or further explanations on any of these topics!

### Angular Interview Questions and Answers (Starting from 51)

---

**51. What is the purpose of the `Renderer2` service in Angular?**

`Renderer2` is a service in Angular that provides a way to manipulate the DOM in a platform-agnostic way. This is particularly useful for web workers, server-side rendering, or any environment where direct access to the DOM is not possible or recommended.

The `Renderer2` service provides methods to create elements, set attributes, listen to events, and more, without directly interacting with the DOM API.

```typescript
import { Component, Renderer2 } from '@angular/core';

@Component({
  selector: 'app-example',
  template: '<div>Example</div>',
})
export class ExampleComponent {
  constructor(private renderer: Renderer2) {}

  ngOnInit() {
    const div = this.renderer.createElement('div');
    this.renderer.setStyle(div, 'color', 'blue');
    const text = this.renderer.createText('Hello, world!');
    this.renderer.appendChild(div, text);
    this.renderer.appendChild(document.body, div);
  }
}
```

---

**52. How does Angular handle two-way data binding?**

Angular uses a combination of property binding and event binding to implement two-way data binding. This is achieved using the `[(ngModel)]` directive, which binds the input element to a component property and listens for changes to update the model.

```html
<input [(ngModel)]="name" placeholder="Enter your name">
<p>Your name is: {{ name }}</p>
```

In this example, when the user types into the input field, the `name` property in the component is automatically updated, and the updated value is reflected in the paragraph.

---

**53. What is the difference between `NgModel` and `FormControl` in Angular?**

- `NgModel`: It is used for template-driven forms and provides a way to bind form controls in the template to data in the component. It is easy to use and requires minimal configuration, but it offers less control over form validation and state management.

- `FormControl`: It is part of Angular's reactive forms and provides more control over form state and validation. `FormControl` allows you to define form controls programmatically and manage their validation and state directly in the component.

```typescript
// Using FormControl in a reactive form
import { FormControl } from '@angular/forms';

export class MyComponent {
  name = new FormControl('');
}
```

```html
<!-- Template for FormControl -->
<input [formControl]="name" placeholder="Enter your name">
```

---

**54. How do you implement route guards in Angular?**

Route guards are used to control access to certain routes based on specific conditions, such as authentication or permissions. Angular provides several types of route guards: `CanActivate`, `CanActivateChild`, `CanDeactivate`, `Resolve`, and `CanLoad`.

To implement a route guard:

1. Create a service that implements the `CanActivate` interface.
2. Implement the `canActivate` method to return `true` or `false` based on your conditions.

```typescript
import { Injectable } from '@angular/core';
import { CanActivate, Router } from '@angular/router';

@Injectable({
  providedIn: 'root',
})
export class AuthGuard implements CanActivate {
  constructor(private router: Router) {}

  canActivate(): boolean {
    const isAuthenticated = // check authentication logic;
    if (isAuthenticated) {
      return true;
    } else {
      this.router.navigate(['/login']);
      return false;
    }
  }
}
```

```typescript
// Apply the guard to a route
const routes: Routes = [
  { path: 'dashboard', component: DashboardComponent, canActivate: [AuthGuard] },
];
```

---

**55. What are Angular animations, and how do you implement them?**

Angular animations are used to create motion and visual effects in Angular applications. The `@angular/animations` package provides a way to define animations in a declarative manner.

To implement animations:

1. Import the `BrowserAnimationsModule` into your `AppModule`.
2. Define animations using the `trigger`, `state`, `style`, `animate`, and `transition` functions.

```typescript
import { trigger, state, style, transition, animate } from '@angular/animations';

@Component({
  selector: 'app-example',
  template: '<div [@fadeInOut]></div>',
  animations: [
    trigger('fadeInOut', [
      state('void', style({ opacity: 0 })),
      transition(':enter, :leave', [
        animate(3000)
      ]),
    ]),
  ],
})
export class ExampleComponent {}
```

In this example, the `fadeInOut` animation is triggered when the element enters or leaves the DOM.

---

**56. What is the purpose of `ng-template` in Angular?**

`ng-template` is an Angular directive used to define a template that is not rendered by default but can be instantiated and rendered later using structural directives like `*ngIf`, `*ngFor`, or the `ngTemplateOutlet` directive. It is commonly used for reusable templates, content projection, and dynamic component rendering.

```html
<ng-template #myTemplate>
  <p>This is a reusable template.</p>
</ng-template>

<div *ngIf="show" [ngTemplateOutlet]="myTemplate"></div>
```

In this example, the content inside `ng-template` will only be rendered when the condition in `*ngIf` is true.

---

**57. How do you handle errors globally in Angular?**

Angular provides the `ErrorHandler` class for global error handling. You can create a custom error handler by extending the `ErrorHandler` class and overriding the `handleError` method.

```typescript
import { ErrorHandler, Injectable } from '@angular/core';

@Injectable({
  providedIn: 'root',
})
export class GlobalErrorHandler implements ErrorHandler {
  handleError(error: any): void {
    // Handle the error here (e.g., log it, show a notification)
    console.error('An error occurred:', error);
  }
}
```

To use this global error handler, provide it in the `AppModule`:

```typescript
@NgModule({
  providers: [{ provide: ErrorHandler, useClass: GlobalErrorHandler }],
})
export class AppModule {}
```

---

**58. What is the role of `ngZone` in Angular?**

`ngZone` is a service in Angular that helps manage and control the change detection mechanism. It allows you to run code inside or outside of Angular's zone, which can help improve performance by reducing unnecessary change detection cycles.

Common use cases for `ngZone` include running heavy computations or third-party code outside Angular's zone to prevent excessive change detection.

```typescript
import { Component, NgZone } from '@angular/core';

@Component({
  selector: 'app-example',
  template: '<p>{{ counter }}</p>',
})
export class ExampleComponent {
  counter = 0;

  constructor(private ngZone: NgZone) {
    this.ngZone.runOutsideAngular(() => {
      setInterval(() => {
        this.counter++;
        // Explicitly trigger change detection if needed
        this.ngZone.run(() => {});
      }, 1000);
    });
  }
}
```

---

**59. What are Angular directives, and what are the types?**

Angular directives are special markers in the DOM that tell Angular to attach a specific behavior to the element or modify its appearance, behavior, or layout.

There are three types of directives in Angular:

1. **Component Directives**: These are directives with a template. They create reusable views with associated behavior. Components are the most common type of directive.

2. **Structural Directives**: These directives change the DOM layout by adding or removing elements. Examples include `*ngIf`, `*ngFor`, and `*ngSwitch`.

3. **Attribute Directives**: These directives change the appearance or behavior of an element, component, or another directive. Examples include `ngClass`, `ngStyle`, and custom attribute directives.

---

**60. How can you share data between sibling components in Angular?**

To share data between sibling components (components that do not have a direct parent-child relationship), you can use a shared service. The service acts as a mediator and stores the data that needs to be shared. Both components can inject the service and access the shared data.

1. Create a shared service.
2. Inject the service into both sibling components.
3. Use the service to get or set shared data.

```typescript
// Shared service
@Injectable({
  providedIn: 'root',
})
export class SharedService {
  private data = new BehaviorSubject<string>('default data');
  sharedData = this.data.asObservable();

  setData(data: string) {
    this.data.next(data);
  }
}

// Sibling Component 1
@Component({
  selector: 'app-sibling1',
  template: '<button (click)="sendData()">Send Data</button>',
})
export class Sibling1Component {
  constructor(private sharedService: SharedService) {}

  sendData() {
    this.sharedService.setData('Data from Sibling 1');
  }
}

// Sibling Component 2
@Component({
  selector: 'app-sibling2',
  template: '<p>{{ data }}</p>',
})
export class Sibling2Component implements OnInit {
  data: string;

  constructor(private sharedService: SharedService) {}

  ngOnInit() {
    this.sharedService.sharedData.subscribe((data) => {
      this.data = data;
    });
  }
}
```

---

Let me know if you need more questions or further clarifications on any of these topics!

### Angular Interview Questions and Answers (Starting from 61)

---

**61. What is the purpose of `ng-content` in Angular?**

`ng-content` is used for content projection in Angular, allowing you to pass and display content within a component from outside the component. It acts as a placeholder for the projected content, enabling developers to create reusable components with customizable content.

```typescript
// Parent Component
@Component({
  selector: 'app-parent',
  template: `<app-child><p>Projected Content</p></app-child>`,
})
export class ParentComponent {}

// Child Component
@Component({
  selector: 'app-child',
  template: `<div><ng-content></ng-content></div>`,
})
export class ChildComponent {}
```

In this example, the `<p>Projected Content</p>` inside the `app-child` component is projected into the `ng-content` placeholder.

---

**62. How do you optimize Angular applications for better performance?**

Optimizing Angular applications involves several strategies, including:

1. **OnPush Change Detection**: Use `OnPush` strategy to reduce unnecessary change detection cycles.
   
   ```typescript
   @Component({
     selector: 'app-optimized',
     changeDetection: ChangeDetectionStrategy.OnPush,
     template: `<p>{{ data }}</p>`,
   })
   export class OptimizedComponent {
     @Input() data: string;
   }
   ```

2. **Lazy Loading Modules**: Load modules only when needed to reduce the initial bundle size.
   
   ```typescript
   const routes: Routes = [
     { path: 'feature', loadChildren: () => import('./feature/feature.module').then(m => m.FeatureModule) },
   ];
   ```

3. **Tree Shaking**: Ensure that unused code is removed during the build process by using Angular's AOT (Ahead-of-Time) compilation.

4. **Use Pure Pipes**: Pure pipes only execute when their inputs change, reducing unnecessary calculations.

5. **Avoid Memory Leaks**: Use `ngOnDestroy` to clean up subscriptions and avoid memory leaks.

---

**63. What are Angular lifecycle hooks, and why are they important?**

Angular lifecycle hooks are methods that allow you to tap into different stages of a component's lifecycle, such as initialization, changes, and destruction. They are important for managing component behavior, such as fetching data, cleaning up resources, or handling input changes.

Key lifecycle hooks include:

1. **ngOnInit**: Called once after the component is initialized. Commonly used for fetching data.

2. **ngOnChanges**: Called whenever input properties change. Useful for reacting to changes in input values.

3. **ngDoCheck**: Called during every change detection run. Allows custom change detection logic.

4. **ngOnDestroy**: Called just before the component is destroyed. Used for cleanup tasks, such as unsubscribing from Observables.

```typescript
@Component({
  selector: 'app-lifecycle',
  template: '<p>Lifecycle Hook Example</p>',
})
export class LifecycleComponent implements OnInit, OnDestroy {
  ngOnInit() {
    console.log('Component Initialized');
  }

  ngOnDestroy() {
    console.log('Component Destroyed');
  }
}
```

---

**64. What is a `HostBinding` and how is it used in Angular?**

`HostBinding` is a decorator in Angular that allows you to bind properties or attributes of the host element (the element on which the directive or component is applied) to a property in the directive or component class.

```typescript
@Directive({
  selector: '[appHighlight]',
})
export class HighlightDirective {
  @HostBinding('style.backgroundColor') backgroundColor: string;

  constructor() {
    this.backgroundColor = 'yellow';
  }
}
```

In this example, the `@HostBinding` decorator binds the `backgroundColor` style of the host element to the `backgroundColor` property in the directive, highlighting the element with a yellow background.

---

**65. What is the `async` pipe and how does it work in Angular?**

The `async` pipe is a built-in Angular pipe that subscribes to an Observable or a Promise and returns the latest value emitted by the Observable or resolved by the Promise. It automatically handles subscription and unsubscription, making it ideal for working with asynchronous data in templates.

```typescript
@Component({
  selector: 'app-async-pipe',
  template: `<p>{{ observableData$ | async }}</p>`,
})
export class AsyncPipeComponent {
  observableData$ = of('Hello, World!');
}
```

In this example, the `async` pipe subscribes to the `observableData$` Observable and displays its emitted value in the template.

---

**66. How does Angular handle forms? Explain template-driven and reactive forms.**

Angular provides two approaches for building forms:

1. **Template-driven forms**: These forms are defined directly in the template using directives like `ngModel`, `ngForm`, and `ngModelGroup`. They are easier to set up but offer less control over validation and form state.

   ```html
   <form #form="ngForm">
     <input [(ngModel)]="name" name="name" required>
     <button type="submit" [disabled]="form.invalid">Submit</button>
   </form>
   ```

2. **Reactive forms**: These forms are defined and managed in the component class using `FormControl`, `FormGroup`, and `FormBuilder`. They provide more control over form validation, state, and dynamic form creation.

   ```typescript
   this.form = this.fb.group({
     name: ['', Validators.required],
   });
   ```

   ```html
   <form [formGroup]="form">
     <input formControlName="name">
     <button type="submit" [disabled]="form.invalid">Submit</button>
   </form>
   ```

---

**67. What is the `Injector` in Angular, and how does it work?**

The `Injector` in Angular is a core service that is responsible for creating and injecting dependencies into components, directives, pipes, and services. The injector maintains a container of providers and can instantiate services based on the provided configuration.

When a class is decorated with `@Injectable`, Angular's dependency injection system knows how to create instances of that class and inject them where needed.

```typescript
@Injectable({
  providedIn: 'root',
})
export class MyService {
  constructor() {}
}

@Component({
  selector: 'app-example',
  template: `<p>Example Component</p>`,
})
export class ExampleComponent {
  constructor(private myService: MyService) {}
}
```

In this example, `MyService` is injected into `ExampleComponent` through the constructor.

---

**68. What is the difference between `@Injectable` and `@Inject` in Angular?**

- **`@Injectable`**: This decorator is used to define a service that can be injected into other classes. It indicates that the class is eligible for dependency injection.

- **`@Inject`**: This decorator is used to specify the exact dependency to inject when Angular cannot infer the dependency type. It is useful when injecting dependencies that require tokens or when the type cannot be determined automatically.

```typescript
@Injectable({
  providedIn: 'root',
})
export class MyService {
  constructor() {}
}

@Component({
  selector: 'app-example',
  template: `<p>Example Component</p>`,
})
export class ExampleComponent {
  constructor(@Inject(MyService) private service) {}
}
```

In this example, `@Inject` is used to specify that `MyService` should be injected into the component.

---

**69. What are Angular zones and how do they work?**

Angular zones, managed by the `Zone.js` library, are a mechanism to track asynchronous operations and automatically trigger change detection when these operations complete. Zones wrap asynchronous events like promises, setTimeout, or HTTP requests, ensuring that Angular knows when to update the view.

Zones are particularly useful for managing change detection efficiently and for tracking the execution context of asynchronous operations.

```typescript
import { Component, NgZone } from '@angular/core';

@Component({
  selector: 'app-zone-example',
  template: '<p>{{ counter }}</p>',
})
export class ZoneExampleComponent {
  counter = 0;

  constructor(private ngZone: NgZone) {
    this.ngZone.runOutsideAngular(() => {
      setInterval(() => {
        this.counter++;
        this.ngZone.run(() => {}); // Run inside Angular zone to trigger change detection
      }, 1000);
    });
  }
}
```

---

**70. What is the purpose of Angular's `ViewEncapsulation`, and what are its modes?**

`ViewEncapsulation` is an Angular mechanism that controls how styles are encapsulated and applied to components. Angular provides three modes of view encapsulation:

1. **Emulated** (default): Emulates Shadow DOM by adding unique attributes to component elements. Styles are scoped to the component but not to the entire document.

2. **Shadow DOM**: Uses native Shadow DOM to encapsulate styles, providing true style isolation. Only supported in browsers with Shadow DOM support.

3. **None**: No style encapsulation. Styles are applied globally to the entire document.

```typescript
@Component({
  selector: 'app-encapsulation',
  template: `<p>Encapsulation Example</p>`,
  styles: ['p { color: red; }'],
  encapsulation: ViewEncapsulation.Emulated, // Default
})
export class EncapsulationComponent {}
```

In this example, the paragraph's styles will only apply to elements within the component due to the `Emulated` view encapsulation.

---

Let me know if you need more questions or further clarifications on these topics!

### Angular Interview Questions and Answers (Starting from 71)

---

**71. What are Angular directives, and how do they differ from components?**

Angular directives are special classes that extend or modify the behavior of elements in the DOM. There are three types of directives:

1. **Components**: Directives with a template. They are the most common type of directive and represent a view in Angular.
   
   ```typescript
   @Component({
     selector: 'app-example',
     template: '<p>Component Example</p>',
   })
   export class ExampleComponent {}
   ```

2. **Attribute Directives**: Modify the behavior or appearance of an existing element, component, or directive. An example is `ngClass`.

   ```typescript
   @Directive({
     selector: '[appHighlight]',
   })
   export class HighlightDirective {
     constructor(private el: ElementRef) {
       el.nativeElement.style.backgroundColor = 'yellow';
     }
   }
   ```

3. **Structural Directives**: Modify the DOM structure by adding or removing elements. Examples include `ngIf` and `ngFor`.

   ```typescript
   <div *ngIf="condition">This will display if the condition is true.</div>
   ```

**Components** are a specialized form of directives with their own template, styles, and encapsulation. In contrast, **attribute** and **structural directives** do not have templates and are used to enhance existing elements.

---

**72. What is Angular Universal, and why is it important?**

Angular Universal is a technology that allows Angular applications to be rendered on the server side. It provides server-side rendering (SSR) capabilities, which improves performance and search engine optimization (SEO) for Angular applications.

**Benefits of Angular Universal:**

1. **Faster Initial Load**: Server-side rendering delivers the fully rendered page to the client, leading to a faster initial load.

2. **Improved SEO**: Search engines can better index the server-rendered content, improving the website's SEO.

3. **Better Performance on Low-end Devices**: Since the heavy lifting is done on the server, the client device can render the content more efficiently.

To implement Angular Universal:

1. Install the `@nguniversal/express-engine` package.
   
   ```bash
   ng add @nguniversal/express-engine
   ```

2. Generate the Universal project files and configurations.

3. Build and run the server-side application.

---

**73. What is lazy loading, and how is it implemented in Angular?**

Lazy loading is an optimization technique where modules or components are loaded on-demand rather than at the initial application load. In Angular, lazy loading is primarily used to load feature modules only when the user navigates to a route that requires them.

**Implementation:**

1. Create a feature module (e.g., `FeatureModule`).
   
   ```typescript
   @NgModule({
     declarations: [FeatureComponent],
     imports: [CommonModule],
   })
   export class FeatureModule {}
   ```

2. Use the `loadChildren` method in the router configuration to define a route for lazy loading.
   
   ```typescript
   const routes: Routes = [
     {
       path: 'feature',
       loadChildren: () => import('./feature/feature.module').then(m => m.FeatureModule),
     },
   ];
   ```

When the user navigates to the `/feature` route, Angular will load the `FeatureModule` on demand.

---

**74. What are resolvers in Angular, and how do they work?**

Resolvers in Angular are used to perform data fetching before a route is activated. They ensure that necessary data is available before the component is rendered. Resolvers are typically used to fetch data from a server or perform any asynchronous task required by the component.

**Implementation:**

1. Create a resolver service implementing the `Resolve` interface.

   ```typescript
   @Injectable({
     providedIn: 'root',
   })
   export class DataResolver implements Resolve<any> {
     constructor(private dataService: DataService) {}

     resolve(route: ActivatedRouteSnapshot, state: RouterStateSnapshot): Observable<any> {
       return this.dataService.getData();
     }
   }
   ```

2. Add the resolver to the route configuration.

   ```typescript
   const routes: Routes = [
     {
       path: 'data',
       component: DataComponent,
       resolve: { data: DataResolver },
     },
   ];
   ```

3. Access the resolved data in the component.

   ```typescript
   export class DataComponent implements OnInit {
     constructor(private route: ActivatedRoute) {}

     ngOnInit() {
       this.route.data.subscribe((data: { data: any }) => {
         console.log(data.data);
       });
     }
   }
   ```

---

**75. How does Angular handle errors, and what is the `ErrorHandler` class?**

Angular provides a global mechanism to handle errors using the `ErrorHandler` class. The `ErrorHandler` class can be extended to create custom error-handling logic that applies throughout the application.

**Implementation:**

1. Create a custom error handler by extending the `ErrorHandler` class.

   ```typescript
   @Injectable()
   export class GlobalErrorHandler extends ErrorHandler {
     handleError(error: any): void {
       // Custom error handling logic
       console.error('An error occurred:', error);
       super.handleError(error);
     }
   }
   ```

2. Provide the custom error handler in the application module.

   ```typescript
   @NgModule({
     providers: [{ provide: ErrorHandler, useClass: GlobalErrorHandler }],
   })
   export class AppModule {}
   ```

Now, any error that occurs in the application will be handled by the `GlobalErrorHandler`, where you can log the error, display notifications, or send the error to a server.

---

**76. What is Angular Material, and how is it used in Angular applications?**

Angular Material is a UI component library for Angular, following the Material Design guidelines by Google. It provides a collection of reusable and accessible components such as buttons, forms, navigation, and layout components.

**Implementation:**

1. Install Angular Material and add it to your project.

   ```bash
   ng add @angular/material
   ```

2. Import the required modules in your Angular module.

   ```typescript
   import { MatButtonModule } from '@angular/material/button';
   import { MatInputModule } from '@angular/material/input';

   @NgModule({
     imports: [MatButtonModule, MatInputModule],
   })
   export class AppModule {}
   ```

3. Use Angular Material components in your templates.

   ```html
   <button mat-button>Click me</button>
   <mat-form-field>
     <input matInput placeholder="Enter your name">
   </mat-form-field>
   ```

Angular Material simplifies the development of responsive, consistent, and visually appealing user interfaces in Angular applications.

---

**77. What is the purpose of the `Renderer2` class in Angular?**

The `Renderer2` class in Angular is an abstraction used to manipulate DOM elements in a way that is compatible across different platforms (e.g., web, native mobile). It provides a safe way to perform DOM manipulations like setting styles, attributes, or listening to events.

**Key Methods:**

- `setStyle`: Applies a CSS style to an element.
- `removeStyle`: Removes a CSS style from an element.
- `addClass`: Adds a class to an element.
- `removeClass`: Removes a class from an element.
- `setAttribute`: Sets an attribute on an element.
- `removeAttribute`: Removes an attribute from an element.
- `listen`: Adds an event listener to an element.

**Example:**

```typescript
import { Component, Renderer2, ElementRef } from '@angular/core';

@Component({
  selector: 'app-renderer-example',
  template: `<button (click)="changeColor()">Change Color</button>`,
})
export class RendererExampleComponent {
  constructor(private renderer: Renderer2, private el: ElementRef) {}

  changeColor() {
    this.renderer.setStyle(this.el.nativeElement, 'color', 'red');
  }
}
```

Using `Renderer2` ensures that the code is compatible with different rendering environments, like server-side rendering with Angular Universal.

---

**78. How do you implement routing guards in Angular?**

Routing guards in Angular are services that control navigation to and from routes based on certain conditions. There are several types of guards:

1. **CanActivate**: Prevents unauthorized access to a route.
2. **CanDeactivate**: Prevents navigation away from a route under certain conditions.
3. **CanActivateChild**: Applies to child routes, similar to `CanActivate`.
4. **Resolve**: Pre-fetches data before a route is activated.
5. **CanLoad**: Prevents loading lazy-loaded modules under certain conditions.

**Example: Implementing `CanActivate` Guard:**

1. Create a guard service implementing the `CanActivate` interface.

   ```typescript
   @Injectable({
     providedIn: 'root',
   })
   export class AuthGuard implements CanActivate {
     constructor(private authService: AuthService, private router: Router) {}

     canActivate(route: ActivatedRouteSnapshot, state: RouterStateSnapshot): boolean {
       if (this.authService.isLoggedIn()) {
         return true;
       } else {
         this.router.navigate(['login']);
         return false;
       }
     }
   }
   ```

2. Apply the guard to a route.

   ```typescript
   const routes: Routes = [
     {
       path: 'dashboard',
       component: DashboardComponent,
       canActivate: [AuthGuard],
     },
   ];
   ```

---
### Angular Interview Questions and Answers (Starting from 79)

---

**79. What are Angular modules, and how do they help in organizing an application?**

Angular modules, often referred to as `NgModules`, are containers that group related components, directives, pipes, and services together. They help organize an Angular application by allowing developers to structure the application into cohesive blocks of functionality.

**Key Points:**

1. **Root Module**: Every Angular application has at least one module, the root module (usually `AppModule`), which bootstraps the application.

   ```typescript
   @NgModule({
     declarations: [AppComponent],
     imports: [BrowserModule, FormsModule],
     bootstrap: [AppComponent],
   })
   export class AppModule {}
   ```

2. **Feature Modules**: These modules are created to encapsulate different features of an application. For example, a `UserModule` might manage everything related to user management.

   ```typescript
   @NgModule({
     declarations: [UserComponent],
     imports: [CommonModule],
     exports: [UserComponent],
   })
   export class UserModule {}
   ```

3. **Shared Modules**: These contain common components, directives, and pipes used across multiple modules. Shared modules help avoid code duplication.

   ```typescript
   @NgModule({
     declarations: [SharedComponent],
     imports: [CommonModule],
     exports: [SharedComponent, CommonModule],
   })
   export class SharedModule {}
   ```

4. **Core Modules**: The core module is typically used to provide services that should be instantiated only once, such as singletons.

   ```typescript
   @NgModule({
     providers: [AuthService],
   })
   export class CoreModule {}
   ```

Modules help in structuring large applications by separating functionality into different modules, promoting code reusability, maintainability, and easy testing.

---

**80. What is Ahead-of-Time (AOT) Compilation in Angular, and what are its benefits?**

Ahead-of-Time (AOT) Compilation is a process in Angular where the Angular compiler converts the Angular HTML and TypeScript code into efficient JavaScript code during the build phase, before the browser downloads and runs the code.

**Benefits of AOT Compilation:**

1. **Faster Rendering**: The browser downloads a pre-compiled version of the application, which renders immediately without needing to compile the code at runtime.

2. **Smaller Angular Framework**: AOT reduces the size of the Angular framework, as it does not need to include the compiler.

3. **Fewer HTTP Requests**: AOT inlines external HTML and CSS files within the application’s JavaScript, reducing the number of HTTP requests.

4. **Earlier Detection of Template Errors**: AOT detects and reports template binding errors during the build process, rather than at runtime.

5. **Better Security**: AOT compilation compiles templates into JavaScript and removes HTML templates, reducing the chances of injection attacks.

To enable AOT in an Angular project:

```bash
ng build --aot
```

AOT compilation is recommended for production builds to improve performance and security.

---

**81. What is the difference between Angular's `ngOnInit` and constructor?**

In Angular, both the `constructor` and `ngOnInit` methods are used for initialization, but they serve different purposes.

1. **Constructor**:
   - The `constructor` is a default TypeScript method used to initialize class members and inject dependencies.
   - It is called when the component is instantiated.
   - It should not contain any Angular logic, such as interacting with services or DOM elements, because at this point, the component's inputs and outputs are not yet available.

   ```typescript
   constructor(private service: SomeService) {
     // Constructor logic here (like initializing variables)
   }
   ```

2. **ngOnInit**:
   - `ngOnInit` is a lifecycle hook provided by Angular.
   - It is called after the constructor, and after Angular has initialized the component's input properties.
   - It is the preferred place to write initialization logic, such as fetching data from a service, that depends on the component's input properties.

   ```typescript
   ngOnInit(): void {
     // Angular initialization logic here (like making API calls)
   }
   ```

**Summary**: Use the `constructor` for dependency injection and simple initialization, and `ngOnInit` for complex initialization and Angular-specific tasks.

---

**82. What are pipes in Angular, and how do you create a custom pipe?**

Pipes in Angular are used to transform data in the template. They are similar to filters in other frameworks. Angular provides built-in pipes like `DatePipe`, `UpperCasePipe`, `LowerCasePipe`, etc., and also allows the creation of custom pipes.

**Creating a Custom Pipe:**

1. Generate a pipe using the Angular CLI:

   ```bash
   ng generate pipe custom
   ```

2. Implement the custom pipe logic.

   ```typescript
   @Pipe({
     name: 'customPipe',
   })
   export class CustomPipe implements PipeTransform {
     transform(value: string): string {
       // Custom transformation logic
       return value.toUpperCase();
     }
   }
   ```

3. Use the custom pipe in the template.

   ```html
   <p>{{ 'hello world' | customPipe }}</p>
   ```

   The output would be: `HELLO WORLD`.

**Pipes can be classified into:**

1. **Pure Pipes**: These pipes are stateless, meaning they depend only on their input value and return the same output for the same input.
2. **Impure Pipes**: These pipes can detect changes in mutable objects and perform transformations even when the reference hasn’t changed.

By default, Angular pipes are pure, and if you want to create an impure pipe, you can set `pure: false` in the `@Pipe` decorator.

---

**83. What is Angular's `ngOnChanges` lifecycle hook?**

`ngOnChanges` is a lifecycle hook in Angular that is called before `ngOnInit` and whenever one or more input properties of a component or directive change.

**Key Points:**

- `ngOnChanges` receives an object `SimpleChanges` which contains the current and previous values of the changed properties.
- It is particularly useful when a component depends on the changes of its input properties to perform certain tasks.

**Example:**

```typescript
@Component({
  selector: 'app-example',
  template: `<p>{{data}}</p>`,
})
export class ExampleComponent implements OnChanges {
  @Input() data: string;

  ngOnChanges(changes: SimpleChanges) {
    if (changes['data']) {
      console.log('Previous:', changes['data'].previousValue);
      console.log('Current:', changes['data'].currentValue);
    }
  }
}
```

Whenever the `data` input changes, `ngOnChanges` is triggered, and you can react to the change accordingly.

---

**84. How does Angular's `ng-content` work, and what is content projection?**

`ng-content` is an Angular directive used for content projection, allowing you to insert and display external content within a component's template.

**Content Projection:**

Content projection is a pattern in Angular that allows you to pass content from a parent component to a child component and display it in predefined spots within the child's template.

**Basic Example:**

1. In the child component's template, use `ng-content`.

   ```html
   <div class="card">
     <ng-content></ng-content>
   </div>
   ```

2. In the parent component, pass content to the child component.

   ```html
   <app-child>
     <p>This content is projected into the child component.</p>
   </app-child>
   ```

3. The child component will display the content passed by the parent.

**Multi-slot Content Projection:**

Angular also supports projecting content into multiple slots using selectors.

```html
<!-- child component -->
<div class="header">
  <ng-content select="[header]"></ng-content>
</div>
<div class="body">
  <ng-content select="[body]"></ng-content>
</div>
```

```html
<!-- parent component -->
<app-child>
  <h1 header>Header Content</h1>
  <p body>Body Content</p>
</app-child>
```

This approach allows for more flexible component designs, making it easy to customize content.

---

**85. What is Angular's `trackBy` function, and why is it important in `ngFor`?**

The `trackBy` function in Angular is used in conjunction with the `ngFor` directive to improve performance by helping Angular identify items in a list that have changed.

**Why is it important?**

- By default, Angular re-renders the entire list when items are added or removed.
- Using `trackBy`, Angular can keep track of items by a unique identifier (like an ID) and only re-render the items that have changed, instead of the entire list.

**Example:**

```typescript
@Component({
  selector: 'app-list',
  template: `
    <ul>
      <li *ngFor="let item of items; trackBy: trackById">{{ item.name }}</li>
    </ul>
  `,
})
export class ListComponent {
  items = [
    { id: 1, name: 'Item 1' },
    { id: 2, name: 'Item 2' },
  ];

  trackById(index: number, item: any): number {
    return item.id;
  }
}
```

In this example, Angular uses the `id` of each item to track changes. If an item is added, removed, or modified, only the affected items are re-rendered.

### Angular Interview Questions and Answers (Starting from 86)

---

**86. What is Angular Universal, and how does it benefit Angular applications?**

Angular Universal is a technology that enables server-side rendering (SSR) for Angular applications. It allows Angular applications to be rendered on the server, generating static HTML before sending it to the client.

**Benefits of Angular Universal:**

1. **Improved SEO**: Search engines can crawl the fully rendered HTML, making it easier to index and improve search rankings.

2. **Faster Initial Load**: Users see a fully rendered page faster, as the content is generated on the server and sent directly to the browser, reducing the time to first paint.

3. **Better Performance on Slow Connections**: Since the server sends a fully rendered page, users on slower networks experience better performance as the browser doesn't need to render the page client-side initially.

4. **Social Media Sharing**: When sharing links on social media, Angular Universal ensures that the correct metadata is included in the static HTML, improving how shared content appears.

**How to Implement Angular Universal:**

1. **Add Angular Universal to Your Project:**

   ```bash
   ng add @nguniversal/express-engine
   ```

2. **Build the Application:**

   ```bash
   npm run build:ssr
   ```

3. **Serve the Application:**

   ```bash
   npm run serve:ssr
   ```

This will start the server and render your Angular application on the server before sending it to the client.

---

**87. What is Angular's `Injector` and how does dependency injection work?**

Angular's `Injector` is a key part of Angular's dependency injection (DI) system. It is responsible for creating and managing the instances of services and other dependencies that a component or service may require.

**Dependency Injection in Angular:**

1. **Providers**: Services are registered with Angular’s dependency injection system using providers. These can be specified at different levels such as component, module, or root.

   ```typescript
   @Injectable({
     providedIn: 'root',
   })
   export class MyService {}
   ```

2. **Injecting Dependencies**: Dependencies are injected into components or services via the constructor.

   ```typescript
   constructor(private myService: MyService) {}
   ```

3. **Hierarchical Injectors**: Angular has a hierarchical DI system, meaning there can be multiple injectors. The root injector provides dependencies to the entire application, but you can also have child injectors at the component or module level, which can override services provided by parent injectors.

4. **Injector Class**: The `Injector` class allows manual retrieval of a service instance.

   ```typescript
   constructor(private injector: Injector) {
     const service = this.injector.get(MyService);
   }
   ```

Angular’s DI system promotes loose coupling and enhances testability by allowing easy mocking or replacing of dependencies.

---

**88. How does Angular handle HTTP requests, and what is `HttpClientModule`?**

Angular provides the `HttpClientModule` to handle HTTP requests. It is a part of the `@angular/common/http` package and is the recommended way to make HTTP requests in Angular applications.

**Using `HttpClientModule`:**

1. **Import the Module**: First, import `HttpClientModule` in your application module.

   ```typescript
   import { HttpClientModule } from '@angular/common/http';

   @NgModule({
     imports: [HttpClientModule],
   })
   export class AppModule {}
   ```

2. **Inject `HttpClient` in a Service**:

   ```typescript
   import { HttpClient } from '@angular/common/http';

   @Injectable({
     providedIn: 'root',
   })
   export class DataService {
     constructor(private http: HttpClient) {}

     getData() {
       return this.http.get('https://api.example.com/data');
     }
   }
   ```

3. **Making HTTP Requests**:
   - **GET Request**: Fetch data from the server.
   - **POST Request**: Send data to the server.
   - **PUT/PATCH Request**: Update data on the server.
   - **DELETE Request**: Delete data from the server.

   ```typescript
   this.http.get('https://api.example.com/data').subscribe((data) => {
     console.log(data);
   });
   ```

4. **Handling Errors**: Use the `catchError` operator to handle HTTP errors.

   ```typescript
   this.http.get('https://api.example.com/data').pipe(
     catchError((error: HttpErrorResponse) => {
       return throwError(() => new Error(error.message));
     })
   );
   ```

5. **Interceptors**: Angular allows you to create interceptors to modify HTTP requests and responses globally, such as adding authentication tokens or handling errors.

---

**89. What is Angular's Router, and how do you define routes in Angular?**

Angular's Router is a powerful feature that allows for navigation between views or components based on the application's state or URL. It enables single-page application (SPA) functionality.

**Defining Routes in Angular:**

1. **Import the RouterModule**:

   ```typescript
   import { RouterModule, Routes } from '@angular/router';
   import { NgModule } from '@angular/core';
   import { HomeComponent } from './home/home.component';
   import { AboutComponent } from './about/about.component';

   const routes: Routes = [
     { path: '', component: HomeComponent },
     { path: 'about', component: AboutComponent },
   ];

   @NgModule({
     imports: [RouterModule.forRoot(routes)],
     exports: [RouterModule],
   })
   export class AppRoutingModule {}
   ```

2. **Configure the Router**: Define the routes and their corresponding components.

   - **Path**: The URL path that triggers the route.
   - **Component**: The component to be displayed when the route is activated.
   - **Redirects**: You can set up redirects if needed.

   ```typescript
   const routes: Routes = [
     { path: '', redirectTo: '/home', pathMatch: 'full' },
     { path: 'home', component: HomeComponent },
     { path: 'about', component: AboutComponent },
   ];
   ```

3. **Router Outlet**: In your template, use the `<router-outlet></router-outlet>` directive to specify where the routed component should be displayed.

   ```html
   <nav>
     <a routerLink="/home">Home</a>
     <a routerLink="/about">About</a>
   </nav>

   <router-outlet></router-outlet>
   ```

4. **Navigation**: You can navigate programmatically using the `Router` service.

   ```typescript
   constructor(private router: Router) {}

   navigateToAbout() {
     this.router.navigate(['/about']);
   }
   ```

5. **Route Guards**: Angular provides route guards to control access to certain routes based on conditions like authentication.

The Router enables building scalable and maintainable SPAs with clean, intuitive navigation patterns.

---

**90. How does Angular handle forms, and what is the difference between Template-Driven and Reactive Forms?**

Angular provides two ways to handle forms: Template-Driven Forms and Reactive Forms. Both approaches are built on the same underlying API but differ in how the form model is defined and managed.

**Template-Driven Forms:**

1. **Declarative Approach**: The form structure and logic are primarily defined in the template using directives like `ngModel`.

2. **Simple to Use**: Template-Driven Forms are easy to use for simple forms and are more suitable for simpler, smaller applications.

3. **Two-Way Data Binding**: The `ngModel` directive is used for two-way data binding between the form input and the model.

4. **Validation**: Validators are applied directly in the template.

   ```html
   <form #form="ngForm">
     <input type="text" name="name" [(ngModel)]="name" required />
     <div *ngIf="form.controls.name?.invalid">Name is required</div>
   </form>
   ```

**Reactive Forms:**

1. **Programmatic Approach**: The form structure and logic are defined in the component using `FormGroup` and `FormControl`.

2. **More Control**: Reactive Forms offer more control and flexibility, making them suitable for complex and dynamic forms.

3. **Explicit Data Binding**: Form controls are explicitly linked to the model using `FormControl`.

4. **Validation**: Validators are applied directly in the component.

   ```typescript
   this.form = new FormGroup({
     name: new FormControl('', Validators.required),
   });
   ```

   ```html
   <form [formGroup]="form">
     <input type="text" formControlName="name" />
     <div *ngIf="form.get('name').invalid">Name is required</div>
   </form>
   ```

**Key Differences:**

- **Template-Driven Forms** are simple and easy to use but offer less control and flexibility.
- **Reactive Forms** provide more control, better scalability, and are more testable, making them the preferred choice for complex forms.

Angular's form handling features, including built-in validation, custom validators, and form controls, enable the creation of robust, user-friendly forms.

### Angular Interview Questions and Answers (Starting from 91)

---

**91. What are Angular Pipes, and how do you create a custom pipe?**

Angular Pipes are a way to transform data in your templates. They take in data as input and return a transformed version of that data. Angular provides several built-in pipes, such as `DatePipe`, `UpperCasePipe`, `LowerCasePipe`, and `CurrencyPipe`. Additionally, you can create custom pipes to suit specific needs.

**Creating a Custom Pipe:**

1. **Generate the Pipe**:

   You can generate a custom pipe using the Angular CLI:

   ```bash
   ng generate pipe customPipe
   ```

2. **Implement the Pipe**:

   Implement the `transform` method in the generated pipe class. This method will define how the input is transformed.

   ```typescript
   import { Pipe, PipeTransform } from '@angular/core';

   @Pipe({
     name: 'customPipe',
   })
   export class CustomPipe implements PipeTransform {
     transform(value: string, ...args: any[]): string {
       return value.toUpperCase(); // Example: Converts the input to uppercase
     }
   }
   ```

3. **Use the Pipe in a Template**:

   Once created, you can use the custom pipe in your templates like any other pipe.

   ```html
   <p>{{ 'hello world' | customPipe }}</p> <!-- Output: HELLO WORLD -->
   ```

**Built-In Pipes**:

Angular comes with a variety of built-in pipes, including:

- **DatePipe**: Formats dates.
- **UpperCasePipe**: Converts text to uppercase.
- **LowerCasePipe**: Converts text to lowercase.
- **CurrencyPipe**: Formats numbers as currency.

---

**92. What are Angular Directives, and what is the difference between structural and attribute directives?**

Angular Directives are special markers in the DOM that tell Angular to perform certain actions or behaviors on DOM elements.

**Types of Directives:**

1. **Structural Directives**:

   Structural directives change the structure of the DOM by adding or removing elements. They typically have an asterisk (`*`) prefix.

   Examples:
   - **`ngIf`**: Conditionally includes or excludes an element.
   - **`ngFor`**: Repeats an element for each item in a list.
   - **`ngSwitch`**: Switches between alternative views.

   ```html
   <div *ngIf="isVisible">Visible Content</div>
   <ul>
     <li *ngFor="let item of items">{{ item }}</li>
   </ul>
   ```

2. **Attribute Directives**:

   Attribute directives change the appearance or behavior of an element, component, or another directive. They do not change the structure of the DOM.

   Examples:
   - **`ngClass`**: Adds or removes a set of CSS classes.
   - **`ngStyle`**: Adds or removes a set of styles.

   ```html
   <div [ngClass]="{'active': isActive}">Content</div>
   <div [ngStyle]="{'color': isActive ? 'blue' : 'red'}">Styled Content</div>
   ```

**Difference Between Structural and Attribute Directives**:

- **Structural Directives**: Modify the DOM structure by adding, removing, or manipulating elements. Examples: `*ngIf`, `*ngFor`.
- **Attribute Directives**: Modify the appearance or behavior of an element without altering the DOM structure. Examples: `ngClass`, `ngStyle`.

---

**93. What is Angular Change Detection, and how does it work?**

Angular's Change Detection mechanism is responsible for detecting when data in your application changes and updating the view accordingly. This is one of Angular's core features that ensures the UI is always in sync with the application's state.

**How Change Detection Works:**

1. **Zones**:
   - Angular relies on a library called Zone.js to manage and detect asynchronous operations like HTTP requests, setTimeout, or user interactions. When such an operation occurs, Angular is notified, triggering the change detection process.

2. **Change Detection Cycle**:
   - During a change detection cycle, Angular checks every component in the component tree to see if the data-bound properties have changed. If a change is detected, Angular re-renders the affected components.

3. **Default Change Detection Strategy**:
   - Angular's default change detection strategy is called "CheckAlways." It checks every component on every change detection cycle, ensuring that all changes are captured.

4. **OnPush Change Detection Strategy**:
   - You can optimize performance by using the `OnPush` strategy. With this strategy, Angular only checks a component when its input properties change, or when an event occurs within the component.

   ```typescript
   @Component({
     selector: 'app-my-component',
     changeDetection: ChangeDetectionStrategy.OnPush,
     template: `...`,
   })
   export class MyComponent {}
   ```

**Optimizing Change Detection**:

- **Use `OnPush` strategy for components that rely heavily on immutable data or have a large number of elements.**
- **Minimize the number of change detection cycles by avoiding unnecessary bindings or heavy computations in templates.**

---

**94. What is a Singleton Service in Angular, and how do you create one?**

A Singleton Service in Angular is a service that is instantiated only once during the entire lifetime of the application. All components and other services that inject this service receive the same instance.

**Creating a Singleton Service:**

1. **Using `providedIn: 'root'`**:

   The easiest way to create a Singleton Service is to use the `providedIn` metadata in the `@Injectable` decorator with the value `'root'`.

   ```typescript
   @Injectable({
     providedIn: 'root',
   })
   export class SingletonService {
     // Service logic here
   }
   ```

   By using `providedIn: 'root'`, the service is registered at the root level, making it a singleton across the application.

2. **Providing the Service in a Module**:

   Alternatively, you can provide the service in the `providers` array of the `@NgModule` decorator in the application's root module (typically `AppModule`).

   ```typescript
   @NgModule({
     providers: [SingletonService],
   })
   export class AppModule {}
   ```

**Advantages of Singleton Services**:

- **Shared State**: A Singleton Service allows components to share data and state across the application.
- **Centralized Logic**: Centralize logic that needs to be used across multiple components, reducing code duplication.
- **Efficiency**: Only one instance of the service is created, reducing memory overhead.

---

**95. What is Angular's `Renderer2`, and when would you use it?**

Angular's `Renderer2` is a service that allows you to manipulate the DOM in a platform-agnostic way. Instead of directly accessing the DOM via `document` or `element`, Angular recommends using `Renderer2` to ensure compatibility with different rendering environments, such as server-side rendering.

**Using `Renderer2`:**

1. **Inject `Renderer2`**:

   Inject `Renderer2` into your component or directive constructor.

   ```typescript
   import { Renderer2, ElementRef } from '@angular/core';

   constructor(private renderer: Renderer2, private el: ElementRef) {}
   ```

2. **Manipulate DOM Elements**:

   Use `Renderer2` methods to interact with DOM elements.

   - **Set a Style**:

     ```typescript
     this.renderer.setStyle(this.el.nativeElement, 'color', 'blue');
     ```

   - **Add or Remove Classes**:

     ```typescript
     this.renderer.addClass(this.el.nativeElement, 'active');
     this.renderer.removeClass(this.el.nativeElement, 'inactive');
     ```

   - **Set an Attribute**:

     ```typescript
     this.renderer.setAttribute(this.el.nativeElement, 'role', 'button');
     ```

   - **Create and Append Elements**:

     ```typescript
     const newElement = this.renderer.createElement('span');
     this.renderer.appendChild(this.el.nativeElement, newElement);
     ```

**When to Use `Renderer2`:**

- **Compatibility**: Use `Renderer2` when you need to ensure that your code works across different platforms (e.g., web browsers, server-side rendering).
- **Security**: By using `Renderer2`, you avoid direct DOM manipulation, which can be safer and prevent certain types of security vulnerabilities.
- **Flexibility**: `Renderer2` abstracts away direct DOM access, making your code more testable and easier to maintain.

---

### Angular Interview Questions and Answers (Starting from 96)

---

**96. What are Angular Animations, and how do you implement them?**

Angular Animations provide a way to create rich, interactive animations in your Angular applications. They are based on the Web Animations API and allow for complex, reusable animations triggered by state changes.

**Implementing Angular Animations:**

1. **Import the Animations Module**:

   First, import the `BrowserAnimationsModule` in your `AppModule`.

   ```typescript
   import { BrowserAnimationsModule } from '@angular/platform-browser/animations';

   @NgModule({
     imports: [BrowserAnimationsModule],
   })
   export class AppModule {}
   ```

2. **Define an Animation**:

   Use the `trigger`, `state`, `style`, `animate`, and `transition` functions to define your animation in the component.

   ```typescript
   import { trigger, state, style, animate, transition } from '@angular/animations';

   @Component({
     selector: 'app-animate',
     templateUrl: './animate.component.html',
     animations: [
       trigger('openClose', [
         state('open', style({
           height: '200px',
           opacity: 1,
           backgroundColor: 'yellow'
         })),
         state('closed', style({
           height: '100px',
           opacity: 0.5,
           backgroundColor: 'green'
         })),
         transition('open => closed', [
           animate('0.5s')
         ]),
         transition('closed => open', [
           animate('0.5s')
         ]),
       ]),
     ],
   })
   export class AnimateComponent {
     isOpen = true;

     toggle() {
       this.isOpen = !this.isOpen;
     }
   }
   ```

3. **Use the Animation in the Template**:

   Bind the animation trigger to a DOM element in the template.

   ```html
   <div [@openClose]="isOpen ? 'open' : 'closed'">
     Click the button to toggle the animation.
   </div>
   <button (click)="toggle()">Toggle</button>
   ```

**Advantages of Angular Animations**:

- **Rich Interactivity**: Easily add animations to enhance the user experience.
- **Reusable**: Define animations once and reuse them across multiple components.
- **Declarative**: Define animations declaratively in the component’s metadata, making them easy to understand and maintain.

---

**97. How does Angular handle Dependency Injection, and what is its significance?**

Dependency Injection (DI) in Angular is a design pattern used to implement IoC (Inversion of Control). It allows the Angular framework to inject dependencies (like services) into components, services, or other classes.

**How Angular DI Works:**

1. **Providers**:
   - A provider is an instruction to the Angular DI system on how to obtain a value for a dependency.
   - Providers are usually defined in the `@Injectable` decorator, in the `providers` array of a module, or at the component level.

   ```typescript
   @Injectable({
     providedIn: 'root',
   })
   export class MyService {
     // Service logic
   }
   ```

2. **Injectors**:
   - Angular uses an injector to keep track of dependency instances and provide them when required.
   - Each Angular application has a root injector that is responsible for providing dependencies at the root level.

3. **Constructor Injection**:
   - The most common way to inject dependencies is through the constructor of a class.

   ```typescript
   import { Component } from '@angular/core';
   import { MyService } from './my-service';

   @Component({
     selector: 'app-my-component',
     templateUrl: './my-component.component.html',
   })
   export class MyComponent {
     constructor(private myService: MyService) {
       // Now myService is available to use within this component
     }
   }
   ```

**Significance of DI in Angular**:

- **Loose Coupling**: DI promotes loose coupling between components and services, making the code easier to maintain and test.
- **Scalability**: DI enables you to scale your application by easily managing dependencies and their lifecycles.
- **Modularity**: By injecting dependencies, different parts of the application can be developed and tested independently.

---

**98. What is an Angular Service Worker, and how does it contribute to building Progressive Web Apps (PWAs)?**

Angular Service Workers are a key feature in building Progressive Web Apps (PWAs). A Service Worker is a script that runs in the background, separate from the web page, and can intercept and handle network requests, manage caching, and enable offline functionality.

**How Angular Service Workers Contribute to PWAs**:

1. **Offline Support**:
   - Service Workers cache resources (HTML, CSS, JS, etc.) during the initial visit, enabling the app to work offline or in low-network conditions.

2. **Push Notifications**:
   - Service Workers can listen for push notifications from the server and display them even when the application is not running.

3. **Background Sync**:
   - Service Workers can synchronize data in the background, ensuring that the app's data is up-to-date when connectivity is restored.

4. **Improved Performance**:
   - By caching assets and serving them from the cache, Service Workers can significantly improve the performance of the app, leading to faster load times.

**Setting Up Angular Service Workers**:

1. **Install the Service Worker Package**:

   ```bash
   ng add @angular/pwa --project *project-name*
   ```

2. **Configure the `ngsw-config.json`**:
   - The `ngsw-config.json` file is where you configure the caching strategies, assets, and data groups.

3. **Build and Serve the Application**:
   - Build the application with service worker support and deploy it to a server.

   ```bash
   ng build --prod
   ```

**Advantages**:

- **Offline Capabilities**: Ensures the app works even when there is no network connection.
- **Improved User Experience**: Faster load times and the ability to function offline enhance the user experience.
- **Engagement**: Push notifications keep users engaged, even when they are not actively using the app.

---

**99. What is Angular Universal, and why would you use it?**

Angular Universal is a technology that allows Angular applications to be rendered on the server-side rather than on the client-side. This server-side rendering (SSR) approach can improve the performance and SEO of Angular applications.

**Why Use Angular Universal?**

1. **Improved Performance**:
   - SSR can reduce the initial load time of the application, especially on slower networks or less powerful devices, by delivering pre-rendered HTML to the client.

2. **Better SEO**:
   - Search engines can crawl and index server-rendered HTML more effectively, improving the visibility of your application in search results.

3. **Faster First Contentful Paint (FCP)**:
   - By rendering content on the server and sending it to the client as HTML, the time it takes for users to see the first meaningful content is reduced.

**Setting Up Angular Universal**:

1. **Install Angular Universal**:

   ```bash
   ng add @nguniversal/express-engine --clientProject *project-name*
   ```

2. **Update the App Server**:

   Angular Universal will create a server file (`server.ts`) that handles the SSR process.

3. **Build and Serve**:

   Use the Angular CLI to build the Universal app and serve it using a Node.js server.

   ```bash
   npm run build:ssr
   npm run serve:ssr
   ```

**Use Cases**:

- **Public-Facing Websites**: Websites that require SEO optimization, like blogs or e-commerce sites, benefit significantly from SSR.
- **Performance-Critical Applications**: Applications that need to load quickly, especially on mobile or in areas with poor network coverage, should consider Angular Universal.

---

**100. What is the `ng-container` directive in Angular, and when should you use it?**

The `ng-container` directive is an Angular element that acts as a container without rendering any additional DOM elements. It is often used to group elements in templates when structural directives need to be applied to multiple elements.

**Using `ng-container`**:

1. **Avoid Unnecessary DOM Elements**:

   Unlike `div`, `span`, or other HTML elements, `ng-container` does not add any extra nodes to the DOM. It’s purely a structural directive that helps with template organization.

   ```html
   <ng-container *ngIf="isLoggedIn">
     <p>Welcome back, user!</p>
     <button>Logout</button>
   </ng-container>
   ```

2. **Grouping Multiple Elements**:

   You can group multiple elements under a single structural directive without adding extra HTML tags to the DOM.

   ```html
   <ng-container *ngFor="let item of items">
     <div>{{ item.name }}</div>
     <span>{{ item.price }}</span>
   </ng-container>
   ```

**Advantages**:

- **Cleaner DOM**: Keeps the DOM structure clean and minimal by avoiding unnecessary wrapper elements.
- **Flexible Template Structure**: Provides more flexibility in applying structural directives across multiple elements without altering the DOM.

---

### Angular Interview Questions and Answers (Starting from 101)

---

**101. What are Angular Template Variables, and how do they work?**

Angular Template Variables are references to DOM elements or Angular components within a template. They allow you to access properties and methods of elements or components directly in the template.

**Using Template Variables:**

1. **Basic Usage**:

   Template variables are defined using the `#` symbol followed by the variable name.

   ```html
   <input #myInput type="text">
   <button (click)="logValue(myInput.value)">Log Input Value</button>
   ```

   In this example, `myInput` is a template variable that references the `input` element. The `logValue()` method can then access the value of the input directly.

2. **Accessing Components**:

   Template variables can also reference Angular components.

   ```html
   <app-child-component #childComp></app-child-component>
   <button (click)="childComp.someMethod()">Call Child Method</button>
   ```

   Here, `childComp` is a template variable that gives you access to the `app-child-component`, allowing you to call methods or access properties of the child component.

**Advantages**:

- **Simplified Access**: Template variables provide a straightforward way to access elements and components without needing to use Angular's `ViewChild` decorator.
- **Improved Template Interactivity**: They allow for more dynamic and interactive templates by enabling direct access to DOM elements and component properties.

---

**102. How do you handle form validation in Angular using Reactive Forms?**

In Angular, form validation can be managed using either Template-Driven Forms or Reactive Forms. Reactive Forms are more powerful and provide a more structured way of managing form controls and their validation.

**Handling Form Validation with Reactive Forms:**

1. **Set Up the Form Group**:

   First, create a `FormGroup` with `FormControl` instances and define the validators.

   ```typescript
   import { FormGroup, FormControl, Validators } from '@angular/forms';

   this.myForm = new FormGroup({
     username: new FormControl('', [Validators.required, Validators.minLength(4)]),
     email: new FormControl('', [Validators.required, Validators.email]),
     password: new FormControl('', [Validators.required, Validators.minLength(8)]),
   });
   ```

2. **Access Form Controls in the Template**:

   Bind the form group to the template and display validation messages.

   ```html
   <form [formGroup]="myForm" (ngSubmit)="onSubmit()">
     <label for="username">Username</label>
     <input id="username" formControlName="username">
     <div *ngIf="myForm.get('username').invalid && myForm.get('username').touched">
       Username is required and must be at least 4 characters long.
     </div>

     <label for="email">Email</label>
     <input id="email" formControlName="email">
     <div *ngIf="myForm.get('email').invalid && myForm.get('email').touched">
       Please enter a valid email.
     </div>

     <label for="password">Password</label>
     <input id="password" type="password" formControlName="password">
     <div *ngIf="myForm.get('password').invalid && myForm.get('password').touched">
       Password is required and must be at least 8 characters long.
     </div>

     <button type="submit" [disabled]="myForm.invalid">Submit</button>
   </form>
   ```

3. **Form Submission**:

   Handle form submission by accessing the form’s value and checking its validity.

   ```typescript
   onSubmit() {
     if (this.myForm.valid) {
       console.log('Form Submitted', this.myForm.value);
     } else {
       console.log('Form is invalid');
     }
   }
   ```

**Advantages of Reactive Forms**:

- **More Control**: Reactive Forms provide better control over form behavior and validation logic.
- **Easier Testing**: They are easier to test due to their more predictable and explicit structure.
- **Scalability**: Reactive Forms are well-suited for complex forms that require dynamic validation rules or conditional form fields.

---

**103. What is Angular's `ViewEncapsulation`, and what are the different types available?**

Angular’s `ViewEncapsulation` defines how styles defined in a component affect the DOM and how the component’s styles are isolated from the rest of the application.

**Types of View Encapsulation**:

1. **Emulated (Default)**:
   - Emulated encapsulation is the default in Angular. It uses attribute selectors to scope styles to a specific component.
   - Angular adds a unique attribute to each component’s host element and adjusts the CSS selectors accordingly.

   ```typescript
   @Component({
     selector: 'app-example',
     templateUrl: './example.component.html',
     styleUrls: ['./example.component.css'],
     encapsulation: ViewEncapsulation.Emulated,
   })
   ```

   ```css
   /* This style applies only to elements within the component */
   .example-class {
     color: blue;
   }
   ```

2. **None**:
   - No encapsulation means that styles defined in a component can affect the entire application, as if they were global styles.

   ```typescript
   @Component({
     selector: 'app-example',
     templateUrl: './example.component.html',
     styleUrls: ['./example.component.css'],
     encapsulation: ViewEncapsulation.None,
   })
   ```

   ```css
   /* This style can affect any element in the application */
   .example-class {
     color: blue;
   }
   ```

3. **Shadow DOM**:
   - Shadow DOM encapsulation uses the browser’s native Shadow DOM API to provide true style encapsulation.
   - Styles are scoped to the component and do not leak out, and global styles cannot affect the component’s styles.

   ```typescript
   @Component({
     selector: 'app-example',
     templateUrl: './example.component.html',
     styleUrls: ['./example.component.css'],
     encapsulation: ViewEncapsulation.ShadowDom,
   })
   ```

   ```css
   /* This style is fully encapsulated within the component */
   .example-class {
     color: blue;
   }
   ```

**Advantages of View Encapsulation**:

- **Style Isolation**: Prevents styles from leaking into other parts of the application.
- **Customization**: Allows developers to choose the appropriate level of encapsulation for their needs, balancing style isolation with global styling when needed.

---

**104. What is an Angular Pipe, and how do you create a custom pipe?**

Angular Pipes are a way to transform data in templates. They can be used to format, filter, or manipulate data before displaying it in the UI.

**Creating a Custom Pipe**:

1. **Generate a Pipe**:

   Use Angular CLI to generate a pipe.

   ```bash
   ng generate pipe customPipe
   ```

2. **Implement the Pipe Logic**:

   Implement the `transform` method in the generated pipe class. This method takes the input value and any optional parameters and returns the transformed value.

   ```typescript
   import { Pipe, PipeTransform } from '@angular/core';

   @Pipe({
     name: 'customPipe'
   })
   export class CustomPipe implements PipeTransform {
     transform(value: string, arg1: string, arg2: string): string {
       return `${arg1} ${value} ${arg2}`;
     }
   }
   ```

3. **Use the Pipe in a Template**:

   Apply the custom pipe in the template.

   ```html
   <p>{{ 'Angular' | customPipe:'Hello':'!' }}</p>
   ```

   Output: `Hello Angular !`

**Advantages of Angular Pipes**:

- **Code Reusability**: Pipes allow you to reuse common transformations throughout your application.
- **Simplified Templates**: They help keep templates clean and readable by moving transformation logic to pipes.
- **Customizable**: You can create custom pipes tailored to your specific needs, beyond the built-in ones like `date`, `currency`, `uppercase`, etc.

---

**105. What are Angular Lifecycle Hooks, and why are they important?**

Angular Lifecycle Hooks are special methods that Angular calls at specific moments in the lifecycle of a component or directive. These hooks allow developers to tap into the component lifecycle and perform actions like initializing data, cleaning up resources, or responding to changes in input properties.

**Common Angular Lifecycle Hooks**:

1. **ngOnInit**:
   - Called once after the component’s data-bound properties have been initialized. Ideal for initializing component state or fetching data.

   ```typescript
   ngOnInit() {
     console.log('Component initialized');
   }
   ```

2. **ngOnChanges**:
   - Called whenever an input-bound property changes. It receives a `SimpleChanges` object containing the current and previous values of the changed properties.

   ```typescript
   ngOnChanges(changes: SimpleChanges) {
     console.log('Input properties changed', changes);
   }
   ```

3. **ngDoCheck**:
   - Called during every change detection run, giving developers a chance to implement custom change detection logic.

   ```typescript
   ngDoCheck() {
     console.log('Custom change detection');
   }
   ```

4. **ngOnDestroy**:
   - Called just before the component is destroyed. It's a good place to clean up resources like subscriptions or event listeners.

   ```typescript
   ngOnDestroy() {
     console.log('Component destroyed');
   }
   ```

5. **ngAfterViewInit**:
   - Called after Angular initializes the component's view and child views.


### Angular Interview Questions and Answers (Starting from 106)

---

**106. What is Angular's `ContentChild` and `ContentChildren` decorators, and how do they differ from `ViewChild` and `ViewChildren`?**

In Angular, `ContentChild` and `ContentChildren` are decorators used to query and get references to projected content within a component, while `ViewChild` and `ViewChildren` are used to query and get references to elements within the component's own view.

**`ContentChild` and `ContentChildren`**:

- **Content Projection**: These decorators are used to access elements or components that are projected into a component using the `<ng-content>` directive.

- **Usage Example**:

  ```typescript
  @Component({
    selector: 'app-parent',
    template: `
      <ng-content></ng-content>
    `,
  })
  export class ParentComponent {
    @ContentChild('projectedContent', { static: false }) contentChild: ElementRef;

    ngAfterContentInit() {
      console.log(this.contentChild.nativeElement.textContent);
    }
  }
  ```

  ```html
  <app-parent>
    <p #projectedContent>Projected Content</p>
  </app-parent>
  ```

  In this example, the `#projectedContent` is accessed using the `@ContentChild` decorator in the `ParentComponent`.

- **Difference**:

  - `ContentChild`: Selects a single projected element or component.
  - `ContentChildren`: Selects multiple projected elements or components.

**`ViewChild` and `ViewChildren`**:

- **Component's Own Template**: These decorators are used to access elements or components that are declared within the component's own template.

- **Usage Example**:

  ```typescript
  @Component({
    selector: 'app-parent',
    template: `
      <p #viewChildContent>View Child Content</p>
    `,
  })
  export class ParentComponent {
    @ViewChild('viewChildContent', { static: false }) viewChild: ElementRef;

    ngAfterViewInit() {
      console.log(this.viewChild.nativeElement.textContent);
    }
  }
  ```

  In this example, the `#viewChildContent` is accessed using the `@ViewChild` decorator.

- **Difference**:

  - `ViewChild`: Selects a single element or component within the component's view.
  - `ViewChildren`: Selects multiple elements or components within the component's view.

**Summary**:
- Use `ContentChild` and `ContentChildren` for projected content (content passed into the component via `<ng-content>`).
- Use `ViewChild` and `ViewChildren` for elements or components within the component's own template.

---

**107. What is Angular's `Renderer2`, and when would you use it?**

Angular's `Renderer2` is a service that allows you to interact with the DOM in a way that is platform-agnostic, meaning it can work across different platforms like server-side rendering, web workers, or native mobile.

**When to Use `Renderer2`**:

1. **Platform Independence**:
   - Direct DOM manipulation using native methods like `document.createElement` or `element.style` ties your code to a specific platform. `Renderer2` provides an abstraction layer, ensuring your code remains compatible with multiple platforms.

2. **Security**:
   - Angular's `Renderer2` helps prevent security issues like XSS attacks by safely interacting with the DOM.

**Basic Usage Example**:

```typescript
import { Component, ElementRef, Renderer2 } from '@angular/core';

@Component({
  selector: 'app-example',
  template: `<button (click)="changeColor()">Change Color</button>`,
})
export class ExampleComponent {
  constructor(private el: ElementRef, private renderer: Renderer2) {}

  changeColor() {
    const button = this.el.nativeElement.querySelector('button');
    this.renderer.setStyle(button, 'color', 'blue');
  }
}
```

In this example, the `Renderer2` service is used to change the color of a button element. By using `Renderer2`, this code remains platform-agnostic and secure.

**Commonly Used Methods in `Renderer2`**:
- `setStyle`: Adds or updates an inline style on an element.
- `removeStyle`: Removes an inline style from an element.
- `setAttribute`: Sets an attribute on an element.
- `removeAttribute`: Removes an attribute from an element.
- `addClass`: Adds a CSS class to an element.
- `removeClass`: Removes a CSS class from an element.
- `appendChild`: Appends a child element to a parent element.
- `createElement`: Creates a new element.

**Advantages**:
- **Platform Agnostic**: Works across various environments, ensuring broader compatibility.
- **Security**: Prevents security vulnerabilities that may arise from direct DOM manipulation.

---

**108. What are Angular Animations, and how do you implement them?**

Angular Animations provide a way to animate the transitions and changes of DOM elements in a structured and declarative manner. They are built on top of the Web Animations API, allowing for complex animation sequences.

**Basic Steps to Implement Angular Animations**:

1. **Import the Necessary Modules**:

   First, import the `BrowserAnimationsModule` in your main module.

   ```typescript
   import { BrowserAnimationsModule } from '@angular/platform-browser/animations';

   @NgModule({
     imports: [BrowserAnimationsModule],
     // other configurations
   })
   export class AppModule {}
   ```

2. **Define the Animations**:

   In the component, import Angular's animation functions and define your animation.

   ```typescript
   import { trigger, state, style, transition, animate } from '@angular/animations';

   @Component({
     selector: 'app-example',
     templateUrl: './example.component.html',
     styleUrls: ['./example.component.css'],
     animations: [
       trigger('fadeInOut', [
         state('void', style({ opacity: 0 })),
         transition('void <=> *', [
           animate(3000)
         ]),
       ]),
     ],
   })
   export class ExampleComponent {}
   ```

3. **Apply the Animation to the Template**:

   Use the defined animation in your template by binding it to an element.

   ```html
   <div *ngIf="isVisible" [@fadeInOut]>
     This element will fade in and out
   </div>
   <button (click)="isVisible = !isVisible">Toggle Visibility</button>
   ```

   In this example, the element will fade in when it appears and fade out when it disappears.

**Core Concepts**:

- **Triggers**: A named set of states and transitions. Triggers are defined in the component’s metadata.
- **States**: Define different styles for different conditions.
- **Transitions**: Define how to switch from one state to another.
- **Animate**: Defines the timing and duration of the transition between states.

**Example of a Complex Animation**:

```typescript
trigger('openClose', [
  state('open', style({
    height: '200px',
    opacity: 1,
    backgroundColor: 'yellow'
  })),
  state('closed', style({
    height: '100px',
    opacity: 0.5,
    backgroundColor: 'green'
  })),
  transition('open => closed', [
    animate('1s')
  ]),
  transition('closed => open', [
    animate('0.5s')
  ]),
])
```

**Advantages of Angular Animations**:

- **Declarative Syntax**: Angular provides a clear and structured way to define animations, making your code easier to read and maintain.
- **Integration**: Animations are integrated directly into the Angular component model, allowing you to animate elements and respond to their lifecycle.
- **Advanced Capabilities**: Supports complex animation sequences, including keyframes, parallel animations, and more.

---

**109. What is the Angular `HttpInterceptor`, and how do you use it?**

Angular `HttpInterceptor` is a powerful feature that allows you to intercept and modify HTTP requests and responses. This is especially useful for adding authentication tokens, handling errors globally, logging, or modifying headers.

**How to Implement an `HttpInterceptor`**:

1. **Create an Interceptor Service**:

   Implement the `HttpInterceptor` interface in a service.

   ```typescript
   import { Injectable } from '@angular/core';
   import { HttpInterceptor, HttpRequest, HttpHandler, HttpEvent } from '@angular/common/http';
   import { Observable } from 'rxjs';

   @Injectable()
   export class AuthInterceptor implements HttpInterceptor {
     intercept(req: HttpRequest<any>, next: HttpHandler): Observable<HttpEvent<any>> {
       const authToken = 'YourAuthTokenHere';
       const clonedRequest = req.clone({
         headers: req.headers.set('Authorization', `Bearer ${authToken}`)
       });

       return next.handle(clonedRequest);
     }
   }
   ```

2. **Provide the Interceptor**:

   Register the interceptor in the `providers` array of your module.

   ```typescript
   import { HTTP_INTERCEPTORS } from '@angular/common/http';

   @NgModule({
     providers: [
       { provide: HTTP_INTERCEPTORS, useClass: AuthInterceptor, multi: true }
     ],
   })
   export class AppModule {}
   ```

   Setting `multi: true` allows you to use multiple interceptors in your application.

**Use Cases for `HttpInterceptor`**:

1. **Adding Authentication Tokens**:
   - Interceptors are often used to automatically attach authentication tokens to every outgoing HTTP request.

2. **Global Error Handling**:
   - You can use interceptors to handle HTTP errors globally.


### Angular Interview Questions and Answers (Starting from 110)

---

**110. What is Angular's `RendererFactory2`, and how does it relate to `Renderer2`?**

`RendererFactory2` is a service in Angular that is used to create instances of `Renderer2`. It provides an abstraction for DOM manipulation, allowing you to create custom renderers or use Angular's default DOM renderer (`Renderer2`).

**Relationship to `Renderer2`**:
- `RendererFactory2` is used to obtain an instance of `Renderer2`.
- While `Renderer2` provides methods to manipulate the DOM (e.g., adding/removing elements, classes, styles), `RendererFactory2` is responsible for creating these instances, especially useful when you need different renderers for different platforms or scenarios.

**Basic Usage Example**:

```typescript
import { RendererFactory2, Renderer2 } from '@angular/core';

@Component({
  selector: 'app-example',
  template: `<p>Hello World</p>`,
})
export class ExampleComponent {
  private renderer: Renderer2;

  constructor(private rendererFactory: RendererFactory2) {
    this.renderer = rendererFactory.createRenderer(null, null);
  }

  changeTextColor() {
    const paragraph = document.querySelector('p');
    this.renderer.setStyle(paragraph, 'color', 'blue');
  }
}
```

In this example, `RendererFactory2` creates an instance of `Renderer2`, which is then used to change the text color of a paragraph element.

**Use Cases**:
- **Custom Renderers**: When building cross-platform applications (e.g., web and native mobile), you may need different renderers for different platforms.
- **Testing**: In unit tests, `RendererFactory2` allows you to mock or stub out rendering logic, making tests more predictable.

---

**111. What is Angular's `TestBed`, and how do you use it in unit testing?**

`TestBed` is the primary API in Angular for writing unit tests for Angular components, services, and other elements. It allows you to create a testing environment where you can configure modules, inject dependencies, and create components in isolation from the rest of the application.

**How to Use `TestBed`**:

1. **Configure the Testing Module**:
   - `TestBed.configureTestingModule()` is used to set up the testing module by declaring components, importing modules, and providing services.

   ```typescript
   beforeEach(() => {
     TestBed.configureTestingModule({
       declarations: [MyComponent],
       imports: [FormsModule],
       providers: [MyService],
     }).compileComponents();
   });
   ```

2. **Create a Component**:
   - You can create an instance of a component by using `TestBed.createComponent()`.

   ```typescript
   it('should create the component', () => {
     const fixture = TestBed.createComponent(MyComponent);
     const component = fixture.componentInstance;
     expect(component).toBeTruthy();
   });
   ```

3. **Inject Services**:
   - `TestBed.inject()` is used to retrieve instances of services for testing.

   ```typescript
   it('should use MyService', () => {
     const service = TestBed.inject(MyService);
     expect(service).toBeTruthy();
   });
   ```

**Example of a Simple Test**:

```typescript
import { TestBed } from '@angular/core/testing';
import { MyComponent } from './my-component.component';
import { MyService } from './my-service.service';

describe('MyComponent', () => {
  beforeEach(() => {
    TestBed.configureTestingModule({
      declarations: [MyComponent],
      providers: [MyService],
    }).compileComponents();
  });

  it('should create the component', () => {
    const fixture = TestBed.createComponent(MyComponent);
    const component = fixture.componentInstance;
    expect(component).toBeTruthy();
  });

  it('should have the correct title', () => {
    const fixture = TestBed.createComponent(MyComponent);
    fixture.detectChanges();
    const compiled = fixture.nativeElement;
    expect(compiled.querySelector('h1').textContent).toContain('MyComponent Title');
  });
});
```

**Advantages**:
- **Isolation**: `TestBed` allows you to isolate and test components and services in a controlled environment.
- **Dependency Injection**: You can easily inject and mock dependencies, making it easier to test components and services in isolation.
- **Comprehensive**: `TestBed` can handle components, services, directives, pipes, and more, providing a full suite of testing capabilities.

---

**112. What is Angular's `ng-template`, and how is it different from `ng-container`?**

`ng-template` is an Angular directive that allows you to define a template that isn't rendered by default. It's often used for structural directives like `ngIf`, `ngFor`, and `ngSwitch`, or when you need to create reusable templates.

**Key Characteristics of `ng-template`**:
- **Not Rendered by Default**: The content inside `ng-template` is not rendered until it is explicitly instantiated.
- **Usage with Structural Directives**: `ng-template` is commonly used with structural directives like `*ngIf` and `*ngFor` to define the template for those directives.

**Basic Usage Example**:

```html
<ng-template #myTemplate>
  <p>This is a template!</p>
</ng-template>

<button (click)="showTemplate = !showTemplate">Toggle Template</button>
<div *ngIf="showTemplate; else myTemplate">
  <p>Template is shown!</p>
</div>
```

In this example, the content inside the `ng-template` is only rendered when the `else` condition of `*ngIf` is met.

**Difference Between `ng-template` and `ng-container`**:
- **`ng-template`**: Defines a template that is not rendered by default. It can be instantiated multiple times by directives like `ngFor`.
- **`ng-container`**: Acts as a grouping element that does not add any additional DOM element. It's used to apply structural directives without adding an extra wrapper element.

**Usage Example of `ng-container`**:

```html
<ng-container *ngIf="condition">
  <p>This content is conditionally rendered without an extra wrapper.</p>
</ng-container>
```

**Summary**:
- Use `ng-template` to define templates that can be rendered conditionally or reused in different parts of your application.
- Use `ng-container` to apply structural directives without adding extra elements to the DOM.

---

**113. What is Angular's `@HostListener` decorator, and how do you use it?**

The `@HostListener` decorator in Angular is used to listen to events on the host element of a directive or component. It allows you to handle events in a clean and declarative manner, without the need to manually add event listeners.

**Basic Usage Example**:

```typescript
import { Directive, HostListener } from '@angular/core';

@Directive({
  selector: '[appClickListener]',
})
export class ClickListenerDirective {
  @HostListener('click', ['$event'])
  handleClick(event: Event) {
    console.log('Element clicked:', event);
  }
}
```

In this example, the `@HostListener` decorator listens for the `click` event on the host element (the element to which the directive is applied). When the element is clicked, the `handleClick` method is called.

**Advantages**:
- **Declarative**: `@HostListener` provides a clean, declarative way to handle events directly within your directives or components.
- **No Manual Event Binding**: Eliminates the need to manually add or remove event listeners, reducing potential memory leaks.
- **Event Argument**: You can pass the event object or other event-specific arguments to the handler method by specifying them in the decorator.

**Advanced Example**:

```typescript
import { Component, HostListener } from '@angular/core';

@Component({
  selector: 'app-example',
  template: `<p>Resize the window and check the console.</p>`,
})
export class ExampleComponent {
  @HostListener('window:resize', ['$event'])
  onResize(event: Event) {
    console.log('Window resized:', event);
  }
}
```

In this example, the `@HostListener` decorator is used to listen to the `resize` event on the `window` object, allowing you to react to window resizing.

**Common Use Cases**:
- Handling user interactions such as clicks, hovers, or key presses.
- Responding to window events like `resize` or `scroll`.
- Managing custom events on the host element.

---

**114. What is Angular's `@Optional` decorator, and how is it used in dependency injection?**

The `@Optional` decorator in Angular is used in dependency injection to specify that a dependency is optional. If the dependency is not provided, Angular will inject `null` instead of throwing an error.

**Basic Usage Example**:

```typescript
import { Component, Optional } from '@angular/core';
import { MyService } from './my-service.service';

@Component({
  selector: 'app-example',
  template: `<p>Check the console for service status.</p>`,
})
export class ExampleComponent {
  constructor(@Optional() private myService: MyService) {
    if (myService) {
      console.log('MyService is available.');
    } else {
      console.log('MyService is not provided.');
    }
  }
}
```

In this example, `MyService` is marked as optional using the `@Optional` decorator. If `MyService` is not provided in the module, the component will log that the service is not available instead of throwing an error.


