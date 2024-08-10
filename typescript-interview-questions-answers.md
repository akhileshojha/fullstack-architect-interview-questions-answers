Here are TypeScript interview questions and answers, starting from number 1:

### 1. **What is TypeScript, and how is it different from JavaScript?**

**Answer:**
TypeScript is a statically typed superset of JavaScript developed by Microsoft. It adds optional static types to the language, enabling developers to catch errors at compile time rather than runtime. The primary differences between TypeScript and JavaScript are:
- **Static Typing:** TypeScript supports static typing, meaning types are checked at compile time, whereas JavaScript is dynamically typed.
- **Compile-time Checking:** TypeScript code is transpiled into JavaScript, allowing developers to catch errors before code execution.
- **Features:** TypeScript introduces features like interfaces, generics, and decorators, which are not available in standard JavaScript.

### 2. **What are some advantages of using TypeScript in a project?**

**Answer:**
- **Early Error Detection:** TypeScript’s static type checking allows for catching errors during development, reducing bugs in production.
- **Improved IDE Support:** TypeScript provides better tooling and IDE support, such as IntelliSense, which enhances developer productivity.
- **Code Readability:** Strong typing and interfaces make the code more predictable and easier to understand, especially in large codebases.
- **Maintainability:** TypeScript’s features like interfaces and generics improve code organization and maintainability.
- **Interoperability:** TypeScript is fully compatible with JavaScript, allowing developers to gradually adopt TypeScript in existing JavaScript projects.

### 3. **Explain the concept of "interfaces" in TypeScript.**

**Answer:**
An interface in TypeScript is a contract that defines the shape of an object. It specifies what properties and methods an object should have, without providing the actual implementation. Interfaces help in ensuring that objects follow a specific structure, which is particularly useful in large codebases where consistent object shapes are critical.

```typescript
interface User {
  id: number;
  name: string;
  email: string;
  isAdmin?: boolean; // Optional property
}

const user: User = {
  id: 1,
  name: "John Doe",
  email: "john@example.com",
};
```

In the above example, the `User` interface defines that an object of type `User` must have `id`, `name`, and `email` properties, with `isAdmin` being optional.

### 4. **What are "Type Aliases" in TypeScript? How do they differ from interfaces?**

**Answer:**
Type Aliases in TypeScript allow you to create a new name for an existing type or a union of types. They are similar to interfaces but with some key differences:
- **Type Aliases:** Can represent any type, including primitives, unions, tuples, and function types.
- **Interfaces:** Primarily used to define the structure of objects and are more flexible when it comes to extending or merging interfaces.

```typescript
type ID = number | string;

type User = {
  id: ID;
  name: string;
  email: string;
};

const user: User = {
  id: 1,
  name: "John Doe",
  email: "john@example.com",
};
```

In this example, `ID` is a type alias that can be either a `number` or a `string`.

### 5. **What is "type inference" in TypeScript?**

**Answer:**
Type inference is a feature in TypeScript where the compiler automatically infers the type of a variable based on the value assigned to it. This means developers don't always need to explicitly define types.

```typescript
let name = "John"; // TypeScript infers 'name' to be of type 'string'
```

In this example, TypeScript infers the type of the variable `name` as `string` based on the assigned value. If you try to assign a non-string value to `name` later, TypeScript will raise an error.

### 6. **How does TypeScript handle null and undefined types?**

**Answer:**
In TypeScript, `null` and `undefined` are treated as distinct types. By default, `null` and `undefined` are assignable to all types, which can lead to potential runtime errors. However, with the introduction of the `strictNullChecks` flag in TypeScript, these types are no longer assignable to other types unless explicitly specified.

```typescript
let value: string | null = "Hello";
value = null; // Allowed when 'strictNullChecks' is off

let anotherValue: string;
anotherValue = null; // Error when 'strictNullChecks' is on
```

Enabling `strictNullChecks` ensures that variables can only be assigned `null` or `undefined` if they explicitly include those types.

### 7. **What are "generics" in TypeScript, and why are they useful?**

**Answer:**
Generics in TypeScript are a way to create reusable components that can work with a variety of data types. They provide a mechanism for writing code that is flexible and type-safe.

```typescript
function identity<T>(arg: T): T {
  return arg;
}

let output1 = identity<string>("Hello"); // T is 'string'
let output2 = identity<number>(42); // T is 'number'
```

In this example, the `identity` function is a generic function that can accept arguments of any type, denoted by `T`. The type `T` is then inferred or explicitly provided when the function is called.

### 8. **What is the "unknown" type in TypeScript? How is it different from "any"?**

**Answer:**
The `unknown` type in TypeScript represents a value that could be of any type, similar to `any`. However, unlike `any`, you cannot perform operations on an `unknown` type without first narrowing it to a more specific type. This ensures better type safety compared to `any`.

```typescript
let value: unknown;
value = "Hello";
value = 42;

if (typeof value === "string") {
  console.log(value.toUpperCase()); // Safe because 'value' is narrowed to 'string'
}
```

Using `unknown` encourages developers to perform type checks before operating on a variable, reducing the risk of runtime errors.

### 9. **What are "decorators" in TypeScript?**

**Answer:**
Decorators in TypeScript are special declarations that can be attached to classes, methods, properties, or parameters to modify their behavior. They are a form of metadata that can be applied to elements to change their runtime behavior.

```typescript
function Log(target: any, propertyName: string, descriptor: PropertyDescriptor) {
  const originalMethod = descriptor.value;

  descriptor.value = function (...args: any[]) {
    console.log(`Method ${propertyName} was called with args: ${JSON.stringify(args)}`);
    return originalMethod.apply(this, args);
  };
}

class Example {
  @Log
  greet(name: string) {
    return `Hello, ${name}`;
  }
}

const example = new Example();
example.greet("John"); // Logs: Method greet was called with args: ["John"]
```

In this example, the `@Log` decorator is applied to the `greet` method, and it logs information whenever the method is called.

### 10. **What is the "never" type in TypeScript, and when would you use it?**

**Answer:**
The `never` type in TypeScript represents values that never occur. It is used in situations where a function is expected to never return, such as when it always throws an error or has an infinite loop.

```typescript
function throwError(message: string): never {
  throw new Error(message);
}

function infiniteLoop(): never {
  while (true) {}
}
```

The `never` type is also useful in scenarios where you want to ensure that all possible cases in a union are handled, especially in exhaustive type checks with `switch` statements.

---

These questions should give you a strong foundation for preparing for TypeScript interviews. Let me know if you need more questions or further details on any specific topic!

Here are additional TypeScript interview questions and answers, starting from number 11:

### 11. **What is the purpose of `readonly` in TypeScript, and how do you use it?**

**Answer:**
The `readonly` modifier in TypeScript is used to make properties of an object immutable. Once a property is marked as `readonly`, it cannot be reassigned after the initial assignment.

```typescript
interface Person {
  readonly id: number;
  name: string;
}

const person: Person = {
  id: 1,
  name: "John Doe",
};

person.name = "Jane Doe"; // Allowed
person.id = 2; // Error: Cannot assign to 'id' because it is a read-only property.
```

In this example, the `id` property is marked as `readonly`, so any attempt to change its value after the object is created will result in a compilation error.

### 12. **Explain the concept of "type guards" in TypeScript.**

**Answer:**
Type guards in TypeScript are expressions that perform runtime checks to ensure that a variable is of a certain type. They allow you to narrow down the type within a conditional block, enabling safer access to the properties or methods of a specific type.

```typescript
function isString(value: unknown): value is string {
  return typeof value === "string";
}

function printLength(value: unknown) {
  if (isString(value)) {
    console.log(value.length); // Safe access to 'length' because 'value' is known to be a string
  } else {
    console.log("Not a string");
  }
}
```

In this example, `isString` is a custom type guard that checks if a value is of type `string`. Inside the `if` block, TypeScript knows that `value` is a `string`, so accessing its properties is safe.

### 13. **What is the "Partial" utility type in TypeScript, and when would you use it?**

**Answer:**
The `Partial` utility type in TypeScript constructs a type with all properties of a given type set to optional. It’s useful when you want to create a version of an existing type that allows for partial updates.

```typescript
interface User {
  id: number;
  name: string;
  email: string;
}

function updateUser(user: User, updates: Partial<User>): User {
  return { ...user, ...updates };
}

const user: User = { id: 1, name: "John Doe", email: "john@example.com" };
const updatedUser = updateUser(user, { name: "Jane Doe" }); // Only 'name' is updated
```

In this example, the `Partial<User>` type allows the `updateUser` function to accept an object with any combination of the `User` properties, all of which are optional.

### 14. **What are "Mapped Types" in TypeScript?**

**Answer:**
Mapped types in TypeScript allow you to create new types by transforming properties in an existing type. They are often used to create utility types like `Partial`, `Readonly`, or `Record`.

```typescript
type Optional<T> = {
  [P in keyof T]?: T[P];
};

interface User {
  id: number;
  name: string;
  email: string;
}

type OptionalUser = Optional<User>;
```

In this example, the `Optional` mapped type takes a type `T` and makes all of its properties optional. `OptionalUser` is now a type where `id`, `name`, and `email` are all optional.

### 15. **Explain the `Record` utility type in TypeScript.**

**Answer:**
The `Record` utility type in TypeScript is used to create an object type with a set of keys of type `K` and values of type `T`. It’s particularly useful for creating dictionaries or maps.

```typescript
type Roles = "admin" | "user" | "guest";
type Permissions = "read" | "write" | "delete";

const rolePermissions: Record<Roles, Permissions[]> = {
  admin: ["read", "write", "delete"],
  user: ["read"],
  guest: ["read"],
};
```

In this example, the `Record<Roles, Permissions[]>` type creates an object where the keys are of type `Roles` and the values are arrays of `Permissions`.

### 16. **How does TypeScript handle function overloading?**

**Answer:**
Function overloading in TypeScript allows you to define multiple signatures for a function, with different types or numbers of parameters. The implementation signature must handle all the defined overloads.

```typescript
function add(a: number, b: number): number;
function add(a: string, b: string): string;
function add(a: any, b: any): any {
  return a + b;
}

console.log(add(1, 2)); // 3
console.log(add("Hello, ", "World!")); // Hello, World!
```

In this example, the `add` function is overloaded to accept either two numbers or two strings. The implementation uses a generic type (`any`) to handle both cases.

### 17. **What is the "namespace" keyword in TypeScript, and how is it used?**

**Answer:**
Namespaces in TypeScript are a way to organize and encapsulate code under a common name, preventing naming conflicts in larger codebases. They can contain variables, functions, classes, and interfaces.

```typescript
namespace Utils {
  export function log(message: string) {
    console.log(message);
  }

  export class Logger {
    log(message: string) {
      console.log(message);
    }
  }
}

Utils.log("Hello, World!"); // Accessing function within namespace
const logger = new Utils.Logger();
logger.log("Logging a message"); // Accessing class within namespace
```

In this example, the `Utils` namespace contains a function and a class, both of which are accessible via the `Utils` namespace. The `export` keyword is used to make them available outside the namespace.

### 18. **What is the difference between `interface` and `type` in TypeScript? When would you use one over the other?**

**Answer:**
Both `interface` and `type` can be used to define object shapes in TypeScript, but there are some differences:
- **Interfaces**: Best used for defining object types, especially when you need to use features like `extends` or `implements`.
- **Type Aliases**: More versatile, can represent any type (including primitives, unions, and intersections), but cannot be reopened to add new properties.

Use `interface` when:
- You need to define the structure of an object.
- You want to take advantage of extending or implementing other interfaces.

Use `type` when:
- You need to define union or intersection types.
- You want to create a type alias for a more complex type.

### 19. **What is "Type Assertion" in TypeScript, and how do you use it?**

**Answer:**
Type assertion in TypeScript is a way to tell the compiler to treat a value as a specific type, overriding its inferred type. It is useful when you know more about the type of a value than TypeScript does.

```typescript
let someValue: unknown = "Hello, TypeScript!";
let stringLength: number = (someValue as string).length;
```

In this example, `someValue` is asserted to be of type `string` using `as string`, allowing you to safely access the `length` property.

### 20. **How does TypeScript support "module resolution," and what are the common module resolution strategies?**

**Answer:**
Module resolution in TypeScript refers to how the compiler determines the location of modules imported in a project. The two common strategies are:
- **Classic**: Used in earlier versions of TypeScript, where non-relative module imports are resolved based on the `baseUrl` or current working directory.
- **Node**: Mimics Node.js behavior, resolving modules based on `node_modules`, index files, and package.json files.

The module resolution strategy can be configured in the `tsconfig.json` file using the `moduleResolution` option.

```json
{
  "compilerOptions": {
    "moduleResolution": "node"
  }
}
```

In this example, the `node` module resolution strategy is used, which is common in projects using Node.js.

---

These additional questions should deepen your understanding of TypeScript. Let me know if you need more questions or further explanations!

Here are more TypeScript interview questions and answers, starting from number 21:

### 21. **What is the difference between `let`, `const`, and `var` in TypeScript?**

**Answer:**
- **`var`**: Declares a variable that is function-scoped or globally scoped if declared outside a function. Variables declared with `var` are hoisted to the top of their scope, meaning they can be accessed before their declaration, though they will be `undefined` until assigned a value.
  
- **`let`**: Declares a block-scoped variable, meaning it is only accessible within the block it is defined. Unlike `var`, `let` does not hoist the variable declaration, preventing it from being used before it’s declared.

- **`const`**: Declares a block-scoped, read-only named constant. The variable cannot be reassigned after its initial assignment, though its contents (like an object or array) can be modified.

```typescript
function example() {
  if (true) {
    var a = 1;
    let b = 2;
    const c = 3;
  }

  console.log(a); // Accessible, var is function-scoped
  console.log(b); // Error, let is block-scoped
  console.log(c); // Error, const is block-scoped
}
```

### 22. **What is the "unknown" type in TypeScript, and how is it different from "any"?**

**Answer:**
The `unknown` type in TypeScript is a safer alternative to `any`. While `any` allows you to perform any operation on it without type checking, `unknown` requires you to perform a type check or type assertion before you can perform operations on it. This reduces the risk of runtime errors.

```typescript
let value: unknown;

value = "Hello, TypeScript!";
value = 42;

if (typeof value === "string") {
  console.log(value.toUpperCase()); // Safe because 'value' is known to be a string
} else {
  console.log("Not a string");
}
```

Here, TypeScript enforces a type check before allowing operations on the `unknown` type, while `any` would bypass such checks.

### 23. **How do you create and use a tuple in TypeScript?**

**Answer:**
A tuple in TypeScript is an array with a fixed number of elements, where each element can have a different type. Tuples are useful when you want to group a fixed number of elements with different types.

```typescript
let person: [string, number];

person = ["John Doe", 30]; // Valid
person = [30, "John Doe"]; // Error: Type 'number' is not assignable to type 'string'

const [name, age] = person;
console.log(name); // "John Doe"
console.log(age); // 30
```

In this example, `person` is a tuple where the first element is a string and the second is a number. The order and types of elements in a tuple are strictly enforced.

### 24. **What is "type narrowing" in TypeScript? How is it achieved?**

**Answer:**
Type narrowing is the process of refining the type of a variable to a more specific type based on control flow, type guards, or type assertions. It allows you to safely perform operations on variables by narrowing their type from a union or broader type to a more specific one.

```typescript
function printId(id: number | string) {
  if (typeof id === "string") {
    console.log(id.toUpperCase()); // TypeScript knows 'id' is a string here
  } else {
    console.log(id); // TypeScript knows 'id' is a number here
  }
}

printId(101); // Output: 101
printId("ID101"); // Output: ID101
```

In this example, TypeScript narrows the type of `id` based on the `typeof` check, allowing the code to handle both `number` and `string` types appropriately.

### 25. **How does TypeScript handle asynchronous programming? What is the `async/await` syntax?**

**Answer:**
TypeScript handles asynchronous programming using the same constructs as JavaScript, such as promises, `async/await`, and callbacks. The `async/await` syntax is a modern way to write asynchronous code in a synchronous manner, making it easier to read and write.

- **`async`**: Marks a function as asynchronous, meaning it implicitly returns a promise.
- **`await`**: Pauses the execution of an `async` function, waiting for the resolution of a promise before proceeding.

```typescript
async function fetchData(): Promise<void> {
  try {
    const response = await fetch("https://api.example.com/data");
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error("Error fetching data:", error);
  }
}

fetchData();
```

In this example, `fetchData` is an asynchronous function that uses `await` to wait for the `fetch` and `json` operations to complete before logging the data.

### 26. **What are "index signatures" in TypeScript?**

**Answer:**
Index signatures in TypeScript allow you to define types for objects that can have an arbitrary number of properties, where the property names are not known in advance but the types of the properties are consistent.

```typescript
interface StringDictionary {
  [key: string]: string;
}

const dictionary: StringDictionary = {
  name: "John",
  occupation: "Developer",
  country: "USA",
};

console.log(dictionary["name"]); // "John"
```

In this example, `StringDictionary` is an interface that can have any number of properties with string keys and string values. This is useful for creating objects like dictionaries or maps where you don’t know all the property names upfront.

### 27. **What is "discriminated unions" in TypeScript, and how is it used?**

**Answer:**
Discriminated unions in TypeScript are a powerful pattern used to create types that can represent a value from multiple types. These unions are made up of several types that share a common property, which serves as a "discriminator" to determine which type is being used.

```typescript
interface Square {
  kind: "square";
  size: number;
}

interface Rectangle {
  kind: "rectangle";
  width: number;
  height: number;
}

interface Circle {
  kind: "circle";
  radius: number;
}

type Shape = Square | Rectangle | Circle;

function getArea(shape: Shape): number {
  switch (shape.kind) {
    case "square":
      return shape.size * shape.size;
    case "rectangle":
      return shape.width * shape.height;
    case "circle":
      return Math.PI * shape.radius ** 2;
  }
}

const square: Square = { kind: "square", size: 5 };
console.log(getArea(square)); // 25
```

In this example, `Shape` is a discriminated union that can be a `Square`, `Rectangle`, or `Circle`. The `kind` property is used to determine which shape type is being used, allowing TypeScript to narrow the type and access the relevant properties.

### 28. **How do you handle enums in TypeScript? What are the different types of enums?**

**Answer:**
Enums in TypeScript are a way of defining a set of named constants, making code more readable and maintaining consistent values. There are three types of enums in TypeScript:

1. **Numeric Enums**: The default, where each member has a numeric value.
2. **String Enums**: Where each member has a string value.
3. **Heterogeneous Enums**: A mix of string and numeric members (less common and generally discouraged).

```typescript
enum Direction {
  Up = 1,
  Down,
  Left,
  Right,
}

enum Status {
  Success = "SUCCESS",
  Failure = "FAILURE",
  Pending = "PENDING",
}

enum MixedEnum {
  No = 0,
  Yes = "YES",
}
```

In this example:
- `Direction` is a numeric enum where `Up` starts with 1 and the others increment automatically.
- `Status` is a string enum with custom string values.
- `MixedEnum` is a heterogeneous enum with both a number and a string.

Here are more TypeScript interview questions and answers, starting from number 29:

### 29. **What are decorators in TypeScript, and what are the types of decorators available?**

**Answer:**
Decorators in TypeScript are special annotations that can be attached to a class, method, accessor, property, or parameter. They allow you to modify or extend the behavior of these elements at runtime. Decorators are often used in frameworks like Angular to inject dependencies or modify class behavior.

Types of decorators in TypeScript:
1. **Class Decorators**: Applied to a class, allowing modification or replacement of the class constructor.
2. **Method Decorators**: Applied to a method, allowing modification of method behavior.
3. **Accessor Decorators**: Applied to a getter or setter, modifying access to a property.
4. **Property Decorators**: Applied to a class property, enabling modification of the property behavior or metadata.
5. **Parameter Decorators**: Applied to method parameters to modify or log their values.

Example of a Method Decorator:
```typescript
function Log(target: any, propertyName: string, descriptor: PropertyDescriptor) {
  const originalMethod = descriptor.value;

  descriptor.value = function (...args: any[]) {
    console.log(`Method ${propertyName} was called with args: ${JSON.stringify(args)}`);
    return originalMethod.apply(this, args);
  };
}

class Example {
  @Log
  greet(name: string) {
    return `Hello, ${name}`;
  }
}

const example = new Example();
example.greet("John"); // Logs: Method greet was called with args: ["John"]
```

### 30. **What is "strict null checks" in TypeScript, and how does it help in writing safer code?**

**Answer:**
`strictNullChecks` is a TypeScript compiler option that enforces stricter null and undefined checking. When enabled, variables cannot be assigned `null` or `undefined` unless they are explicitly defined to allow those types. This helps in preventing null reference errors and makes the code safer and more predictable.

When `strictNullChecks` is enabled:
- `null` and `undefined` must be explicitly handled or allowed in type definitions.
- Operations on potentially null or undefined variables require a check or type assertion.

Example:
```typescript
// With `strictNullChecks` enabled
function getLength(value: string | null): number {
  if (value === null) {
    return 0;
  }
  return value.length;
}

console.log(getLength("TypeScript")); // 10
console.log(getLength(null)); // 0
```

### 31. **How does TypeScript infer types when not explicitly provided?**

**Answer:**
TypeScript has a powerful type inference system that automatically infers the types of variables, function return types, and expressions based on the context. If a type is not explicitly declared, TypeScript will infer it from the assigned value or operation.

Example of type inference:
```typescript
let name = "John Doe"; // Inferred as string
let age = 30; // Inferred as number

function add(a: number, b: number) {
  return a + b; // Inferred as number
}

const result = add(5, 10); // result is inferred as number
```

In this example, TypeScript infers the types of `name` as `string`, `age` as `number`, and the return type of the `add` function as `number` based on the provided values.

### 32. **What is "ambient declaration" in TypeScript, and when would you use it?**

**Answer:**
Ambient declarations in TypeScript are used to declare the types of external libraries or global variables that are not part of your codebase but are used within your project. They are typically written in `.d.ts` files.

Ambient declarations help TypeScript understand the shape and types of external modules or global objects, enabling better type-checking and autocompletion.

Example of an ambient declaration:
```typescript
// ambient.d.ts
declare module "external-library" {
  export function doSomething(value: string): void;
}

declare var globalVar: number;
```

In this example, the ambient declaration tells TypeScript about an external library function `doSomething` and a global variable `globalVar`, enabling you to use them in your code without TypeScript throwing errors.

### 33. **What is a "generic constraint" in TypeScript, and how do you apply it?**

**Answer:**
Generic constraints in TypeScript allow you to restrict the types that can be passed to a generic type parameter. This is useful when you want to enforce that the type passed to a generic meets certain conditions, such as having specific properties or methods.

Example of generic constraint:
```typescript
interface Lengthwise {
  length: number;
}

function logLength<T extends Lengthwise>(value: T): void {
  console.log(value.length);
}

logLength("Hello, TypeScript!"); // 18
logLength([1, 2, 3]); // 3
logLength({ length: 10, name: "Object" }); // 10

// logLength(42); // Error: Argument of type '42' is not assignable to parameter of type 'Lengthwise'.
```

In this example, the generic function `logLength` uses the `T extends Lengthwise` constraint to ensure that any type passed to the function has a `length` property.

### 34. **What is "type compatibility" in TypeScript, and how does it work?**

**Answer:**
Type compatibility in TypeScript refers to the way TypeScript compares types to determine if one type can be assigned to another. TypeScript uses a structural type system, meaning that two types are compatible if their structures are compatible, regardless of their declared types.

Example of type compatibility:
```typescript
interface Person {
  name: string;
  age: number;
}

let p: Person = { name: "John Doe", age: 30 };

let x = { name: "Jane Doe", age: 25, location: "NYC" };
p = x; // Valid because 'x' has all the properties of 'Person'

function greet(person: Person) {
  console.log(`Hello, ${person.name}`);
}

greet(x); // Valid because 'x' is structurally compatible with 'Person'
```

In this example, the object `x` can be assigned to the variable `p` of type `Person` because it has all the required properties (`name` and `age`), making it structurally compatible.

### 35. **Explain the difference between "union types" and "intersection types" in TypeScript.**

**Answer:**
- **Union Types**: Represent a type that can be one of several types. A union type is denoted by the `|` symbol and allows a variable to hold a value of any of the specified types.

  Example:
  ```typescript
  function printId(id: number | string) {
    console.log(`ID: ${id}`);
  }

  printId(101); // Valid
  printId("A101"); // Valid
  ```

- **Intersection Types**: Represent a type that combines multiple types into one. An intersection type is denoted by the `&` symbol and requires that a value satisfies all the specified types.

  Example:
  ```typescript
  interface A {
    name: string;
  }

  interface B {
    age: number;
  }

  type Person = A & B;

  const person: Person = { name: "John Doe", age: 30 }; // Must have both 'name' and 'age'
  ```

In the first example, `id` can be either a `number` or a `string`, whereas in the second example, `person` must satisfy both `A` and `B` interfaces, having both `name` and `age` properties.

### 36. **What is "type aliasing" in TypeScript, and how do you use it?**

**Answer:**
Type aliasing in TypeScript allows you to create a new name (alias) for a type. This can be useful for simplifying complex types, improving code readability, or reusing types.

Example of type aliasing:
```typescript
type ID = string | number;

function printId(id: ID) {
  console.log(`ID: ${id}`);
}

type User = {
  id: ID;
  name: string;
  email: string;
};

const user: User = {
  id: 101,
  name: "John Doe",
  email: "john@example.com",
};

printId(user.id); // 101
```

In this example, `ID` is a type alias for `string | number`, and `User` is a type alias for an object type with specific properties. This makes the code more concise and easier to understand.

Here are more TypeScript interview questions and answers, starting from number 37:

### 37. **What is "type casting" in TypeScript, and how does it differ from "type assertion"?**

**Answer:**
Type casting and type assertion in TypeScript both allow you to override the inferred or existing type of a value, but "type assertion" is the more accurate term in TypeScript. Type assertion is used when you want to tell the TypeScript compiler to treat a value as a specific type.

There are two common ways to perform type assertion:

1. **Using the `as` keyword**:
   ```typescript
   let someValue: unknown = "Hello, TypeScript!";
   let strLength: number = (someValue as string).length;
   ```

2. **Using angle-bracket syntax**:
   ```typescript
   let someValue: unknown = "Hello, TypeScript!";
   let strLength: number = (<string>someValue).length;
   ```

In both cases, TypeScript will treat `someValue` as a `string`, allowing access to string methods like `.length`.

### 38. **What is a "type guard" in TypeScript, and how does it work?**

**Answer:**
A type guard in TypeScript is a technique used to narrow down the type of a variable within a conditional block. Type guards help TypeScript's type checker refine the types and provide better type safety within specific code branches.

Type guards can be implemented using various constructs:

1. **`typeof` operator**: Used to check primitive types like `string`, `number`, or `boolean`.
   ```typescript
   function printValue(value: string | number) {
     if (typeof value === "string") {
       console.log(`String value: ${value}`);
     } else {
       console.log(`Number value: ${value}`);
     }
   }
   ```

2. **`instanceof` operator**: Used to check if an object is an instance of a particular class.
   ```typescript
   class Dog {
     bark() {
       console.log("Woof!");
     }
   }

   class Cat {
     meow() {
       console.log("Meow!");
     }
   }

   function makeSound(animal: Dog | Cat) {
     if (animal instanceof Dog) {
       animal.bark();
     } else {
       animal.meow();
     }
   }
   ```

3. **Custom type guards**: Functions that return a boolean and have a type predicate in the return type.
   ```typescript
   function isString(value: unknown): value is string {
     return typeof value === "string";
   }

   function printValue(value: string | number) {
     if (isString(value)) {
       console.log(`String value: ${value}`);
     } else {
       console.log(`Number value: ${value}`);
     }
   }
   ```

### 39. **How do you handle asynchronous operations in TypeScript?**

**Answer:**
In TypeScript, asynchronous operations are typically handled using Promises, `async/await` syntax, or callback functions. TypeScript provides full support for these constructs, allowing you to write asynchronous code that is clean and easy to read.

1. **Using Promises**:
   ```typescript
   function fetchData(): Promise<string> {
     return new Promise((resolve, reject) => {
       setTimeout(() => {
         resolve("Data fetched");
       }, 1000);
     });
   }

   fetchData().then(data => console.log(data)).catch(error => console.error(error));
   ```

2. **Using `async/await`**:
   ```typescript
   async function fetchData(): Promise<string> {
     return new Promise((resolve, reject) => {
       setTimeout(() => {
         resolve("Data fetched");
       }, 1000);
     });
   }

   async function getData() {
     try {
       const data = await fetchData();
       console.log(data);
     } catch (error) {
       console.error(error);
     }
   }

   getData();
   ```

`async/await` is syntactic sugar over Promises, making the code look synchronous while still being asynchronous.

### 40. **What is the difference between `readonly` and `const` in TypeScript?**

**Answer:**
Both `readonly` and `const` are used to create immutability in TypeScript, but they are used in different contexts:

- **`const`**: Used for variables, ensuring that the variable cannot be reassigned after its initial assignment. However, the contents of objects or arrays declared with `const` can still be modified.
  ```typescript
  const x = 10;
  x = 20; // Error: Assignment to constant variable.

  const arr = [1, 2, 3];
  arr.push(4); // Valid, array contents can be modified.
  ```

- **`readonly`**: Used for properties of classes or interfaces, making sure that the property cannot be reassigned after the object is constructed. This does not prevent modification of the contents of the object or array.
  ```typescript
  class Person {
    readonly name: string;

    constructor(name: string) {
      this.name = name;
    }
  }

  const person = new Person("John");
  person.name = "Doe"; // Error: Cannot assign to 'name' because it is a read-only property.
  ```

In summary, `const` applies to variables, preventing reassignment, while `readonly` applies to properties, preventing modification after initial assignment.

### 41. **What is "declaration merging" in TypeScript, and how does it work?**

**Answer:**
Declaration merging in TypeScript occurs when two or more declarations with the same name are merged into a single declaration. This is most commonly seen with interfaces, namespaces, and function overloads.

1. **Merging Interfaces**:
   ```typescript
   interface Person {
     name: string;
   }

   interface Person {
     age: number;
   }

   const person: Person = { name: "John", age: 30 }; // Merged Person interface includes both 'name' and 'age'.
   ```

   In this example, the `Person` interface is declared twice, but TypeScript merges them into a single interface with both properties `name` and `age`.

2. **Merging Namespaces**:
   ```typescript
   namespace Utility {
     export function log(message: string) {
       console.log(message);
     }
   }

   namespace Utility {
     export function error(message: string) {
       console.error(message);
     }
   }

   Utility.log("Hello"); // Valid
   Utility.error("Oops"); // Valid
   ```

   Here, the `Utility` namespace is declared twice, and TypeScript merges them, so it contains both the `log` and `error` functions.

3. **Merging Functions** (overloads):
   ```typescript
   function add(x: number, y: number): number;
   function add(x: string, y: string): string;
   function add(x: any, y: any): any {
     return x + y;
   }

   console.log(add(1, 2)); // 3
   console.log(add("Hello, ", "World!")); // "Hello, World!"
   ```

   In this case, TypeScript merges the overloaded function declarations, allowing the `add` function to handle both `number` and `string` arguments.

### 42. **What are "index types" and "index signatures" in TypeScript?**

**Answer:**
Index types and index signatures allow you to define types for objects with dynamic keys or properties.

1. **Index Types**: Used with `keyof` and `typeof` operators to create new types based on the keys of an object or an array.
   ```typescript
   interface Person {
     name: string;
     age: number;
   }

   type PersonKeys = keyof Person; // 'name' | 'age'

   function getValue(person: Person, key: PersonKeys) {
     return person[key];
   }

   const john: Person = { name: "John Doe", age: 30 };
   console.log(getValue(john, "name")); // "John Doe"
   ```

2. **Index Signatures**: Define a type for the keys and values of an object when you don't know the exact property names ahead of time.
   ```typescript
   interface Dictionary {
     [key: string]: string;
   }

   const dict: Dictionary = {
     firstName: "John",
     lastName: "Doe",
   };

   console.log(dict["firstName"]); // "John"
   ```

   In this example, the `Dictionary` interface defines an index signature, allowing any string key with a string value.

Here are more TypeScript interview questions and answers, starting from number 43:

### 43. **What is the purpose of `unknown` type in TypeScript, and how does it differ from `any`?**

**Answer:**
The `unknown` type in TypeScript is a safer alternative to `any` because it forces you to perform type checking before using the value. With `unknown`, you must perform some type of checking (such as `typeof` or `instanceof`) or a type assertion to narrow down the type before performing operations on the value. This helps prevent runtime errors and promotes safer code.

- **`any`**: Disables type checking entirely, allowing any operation on the variable without TypeScript issuing any type-related warnings.
  ```typescript
  let value: any = "Hello";
  value.toUpperCase(); // No error, but potentially unsafe.
  value.foo(); // No error, but `foo` might not exist on a string.
  ```

- **`unknown`**: Requires explicit type checks or assertions before you can operate on the value.
  ```typescript
  let value: unknown = "Hello";

  if (typeof value === "string") {
    value.toUpperCase(); // Valid
  } else {
    // TypeScript knows `value` is not a string here
  }
  
  (value as string).toUpperCase(); // Also valid with type assertion
  ```

Using `unknown` is safer than `any` because it encourages developers to write type-safe code.

### 44. **How can you create a "readonly" tuple in TypeScript?**

**Answer:**
In TypeScript, you can create a `readonly` tuple by using the `readonly` keyword before the tuple type. This ensures that once the tuple is created, its elements cannot be reassigned or modified.

```typescript
let readonlyTuple: readonly [number, string] = [1, "TypeScript"];

// readonlyTuple[0] = 42; // Error: Cannot assign to '0' because it is a read-only property.
```

The `readonly` modifier ensures that all elements in the tuple are immutable.

### 45. **What is `enum` in TypeScript, and how is it different from `const enum`?**

**Answer:**
`enum` in TypeScript is a way to define a collection of related values that can be numeric or string-based. Enums provide a convenient way to work with sets of constants and improve code readability.

- **Numeric Enums**:
  ```typescript
  enum Direction {
    Up,
    Down,
    Left,
    Right,
  }

  let move: Direction = Direction.Up;
  ```

- **String Enums**:
  ```typescript
  enum Direction {
    Up = "UP",
    Down = "DOWN",
    Left = "LEFT",
    Right = "RIGHT",
  }

  let move: Direction = Direction.Up;
  ```

**`const enum`** is a more optimized version of `enum` where the enum values are inlined by the TypeScript compiler. This means that no extra code is generated for the enum, and the resulting JavaScript is more efficient.

```typescript
const enum Direction {
  Up,
  Down,
  Left,
  Right,
}

let move: Direction = Direction.Up;
// This compiles to: let move = 0; // Instead of extra enum object code.
```

Use `const enum` when you want to eliminate the overhead of an enum object and don’t need features like reverse mapping.

### 46. **What is a "discriminated union" in TypeScript, and how is it useful?**

**Answer:**
A discriminated union (also known as a tagged union or algebraic data type) is a powerful pattern in TypeScript that combines union types with a literal type property that acts as a "discriminator." This property allows TypeScript to determine which type a value belongs to within a union, enabling more precise type narrowing.

```typescript
interface Circle {
  kind: "circle";
  radius: number;
}

interface Square {
  kind: "square";
  sideLength: number;
}

type Shape = Circle | Square;

function getArea(shape: Shape): number {
  switch (shape.kind) {
    case "circle":
      return Math.PI * shape.radius ** 2;
    case "square":
      return shape.sideLength ** 2;
  }
}

const myShape: Shape = { kind: "circle", radius: 10 };
console.log(getArea(myShape)); // Correctly narrows to 'Circle' type
```

In this example, the `kind` property serves as the discriminator, allowing TypeScript to accurately narrow the type of `shape` within the `switch` statement. Discriminated unions are particularly useful when working with complex types that have distinct properties based on a common discriminator.

### 47. **What are "mapped types" in TypeScript, and how do you use them?**

**Answer:**
Mapped types in TypeScript allow you to create new types by transforming the properties of an existing type. You can map over the keys of a type and apply transformations, such as making properties optional, readonly, or changing their types.

1. **Example of making all properties optional**:
   ```typescript
   type Person = {
     name: string;
     age: number;
   };

   type PartialPerson = {
     [K in keyof Person]?: Person[K];
   };

   // Built-in TypeScript utility type equivalent: Partial<Person>
   ```

2. **Example of making all properties readonly**:
   ```typescript
   type ReadonlyPerson = {
     [K in keyof Person]: Readonly<Person[K]>;
   };

   // Built-in TypeScript utility type equivalent: Readonly<Person>
   ```

3. **Example of changing the type of all properties**:
   ```typescript
   type StringifiedPerson = {
     [K in keyof Person]: string;
   };

   const person: StringifiedPerson = {
     name: "John",
     age: "30", // All properties are now strings
   };
   ```

Mapped types are especially useful when you need to transform types in a consistent way across many properties.

### 48. **What is a "utility type" in TypeScript, and can you give some examples?**

**Answer:**
Utility types in TypeScript are predefined types that provide common type transformations. They help make type declarations more concise and reusable. Some commonly used utility types include:

1. **`Partial<T>`**: Makes all properties of `T` optional.
   ```typescript
   interface Person {
     name: string;
     age: number;
   }

   const partialPerson: Partial<Person> = { name: "John" }; // 'age' is optional
   ```

2. **`Readonly<T>`**: Makes all properties of `T` readonly.
   ```typescript
   const readonlyPerson: Readonly<Person> = { name: "John", age: 30 };
   // readonlyPerson.age = 31; // Error: Cannot assign to 'age' because it is a read-only property.
   ```

3. **`Pick<T, K extends keyof T>`**: Creates a new type by picking a subset of properties from `T`.
   ```typescript
   const personName: Pick<Person, "name"> = { name: "John" };
   ```

4. **`Omit<T, K extends keyof T>`**: Creates a new type by omitting specific properties from `T`.
   ```typescript
   const personWithoutAge: Omit<Person, "age"> = { name: "John" };
   ```

5. **`Record<K extends keyof any, T>`**: Creates a type with a set of properties `K` of type `T`.
   ```typescript
   const nameAgeMap: Record<string, number> = { John: 30, Jane: 25 };
   ```

Utility types are very powerful and can be used to reduce boilerplate code when defining complex types.

### 49. **How can you ensure that an object adheres to a specific structure using TypeScript?**

**Answer:**
In TypeScript, you can ensure that an object adheres to a specific structure by defining an `interface` or a `type` and using that as the type annotation for the object.

1. **Using an `interface`**:
   ```typescript
   interface Person {
     name: string;
     age: number;
   }

   const person: Person = { name: "John", age: 30 }; // Valid
   ```

   If you try to assign an object that doesn’t conform to the `Person` interface, TypeScript will throw an error.

2. **Using a `type` alias**:
   ```typescript
   type Person = {
     name: string;
     age: number;
   };

   const person: Person = { name: "John", age: 30 }; // Valid
   ```

By using `interface` or `type`, you define the exact shape that an object must have, ensuring that all necessary properties are present and have the correct types.

Here are more TypeScript interview questions and answers, starting from number 50:

### 50. **What is "ambient declaration" in TypeScript, and when would you use it?**

**Answer:**
Ambient declarations in TypeScript are used to describe the shape of code that is external to the current project, such as a third-party library or global variables that TypeScript does not have any knowledge of. They allow you to include declarations of variables, functions, classes, etc., without providing their implementation. This is useful when integrating with JavaScript code or using external libraries without TypeScript definitions.

Ambient declarations are typically placed in `.d.ts` files and are used when you need to tell TypeScript about the types of objects or modules that exist in your environment but are not defined in your TypeScript code.

**Example of an ambient declaration for a global variable:**
```typescript
// ambient.d.ts
declare var myGlobalVar: string;

// main.ts
console.log(myGlobalVar.toUpperCase());
```

You would use ambient declarations to declare types for existing JavaScript code, global variables, or modules that TypeScript doesn't know about, ensuring TypeScript can correctly infer types and provide type checking.

### 51. **What are "type guards" in TypeScript, and how do they work?**

**Answer:**
Type guards in TypeScript are expressions that allow you to narrow down the type of a variable within a conditional block. They help TypeScript infer a more specific type when the type could be one of several possible types.

Type guards can be implemented using:

1. **`typeof` operator**: To check the type of a variable at runtime.
   ```typescript
   function padLeft(value: string, padding: string | number): string {
     if (typeof padding === "number") {
       return Array(padding + 1).join(" ") + value;
     }
     if (typeof padding === "string") {
       return padding + value;
     }
     throw new Error(`Expected string or number, got '${typeof padding}'.`);
   }
   ```

2. **`instanceof` operator**: To check if an object is an instance of a particular class.
   ```typescript
   class Cat {
     meow() {
       console.log("Meow!");
     }
   }

   class Dog {
     bark() {
       console.log("Woof!");
     }
   }

   function makeSound(animal: Cat | Dog) {
     if (animal instanceof Cat) {
       animal.meow(); // TypeScript knows it's a Cat
     } else {
       animal.bark(); // TypeScript knows it's a Dog
     }
   }
   ```

3. **Custom type guards**: Using a user-defined function that returns a boolean and has a type predicate.
   ```typescript
   function isString(value: any): value is string {
     return typeof value === "string";
   }

   function printLength(value: string | number) {
     if (isString(value)) {
       console.log(value.length); // TypeScript knows it's a string
     } else {
       console.log(value.toString().length); // TypeScript knows it's a number
     }
   }
   ```

Type guards enhance the type safety of your code by allowing TypeScript to better understand the possible types of values during execution.

### 52. **What is the difference between `interface` and `type` in TypeScript?**

**Answer:**
Both `interface` and `type` in TypeScript are used to define the shape of an object, but they have some key differences:

1. **Extensibility**:
   - **`interface`**: Can be extended using `extends` and can also extend other interfaces or classes. Interfaces are open-ended, meaning you can add more properties to them later (declaration merging).
     ```typescript
     interface Person {
       name: string;
     }

     interface Person {
       age: number;
     }

     // Now Person has both 'name' and 'age' properties
     ```

   - **`type`**: Cannot be extended in the same way as interfaces. If you need to extend a type, you would use intersections (`&` operator) or create a new type based on the original.
     ```typescript
     type Person = {
       name: string;
     };

     type Employee = Person & {
       age: number;
     };
     ```

2. **Usage**:
   - **`interface`**: Best for describing the shape of objects and defining contracts for classes. It's the preferred approach when working with object-oriented patterns.
   - **`type`**: More versatile and can represent not just objects, but also primitives, unions, intersections, and more complex types.

3. **Declaration merging**:
   - **`interface`**: Supports declaration merging, allowing multiple interface declarations with the same name to be merged into a single interface.
   - **`type`**: Does not support declaration merging.

4. **Aliases and complex types**:
   - **`interface`**: Cannot be used to define complex types such as union types or primitives.
   - **`type`**: Can be used to create complex types, including union types, intersection types, and more.

**Example**:
```typescript
// Using interface
interface Person {
  name: string;
  age: number;
}

// Using type
type PersonType = {
  name: string;
  age: number;
};
```

In practice, use `interface` when you want to define a contract for objects or classes, and use `type` when you need more flexibility, such as defining union or intersection types.

### 53. **What are "conditional types" in TypeScript, and how do you use them?**

**Answer:**
Conditional types in TypeScript are a powerful feature that allows you to define types based on a condition. They follow the format:

```typescript
T extends U ? X : Y
```

Here, if type `T` extends type `U`, then the resulting type is `X`, otherwise, it is `Y`.

**Example 1: Basic conditional type**
```typescript
type IsString<T> = T extends string ? true : false;

type Test1 = IsString<string>; // true
type Test2 = IsString<number>; // false
```

**Example 2: Inferring types within conditional types**
```typescript
type ElementType<T> = T extends (infer U)[] ? U : T;

type Test1 = ElementType<number[]>; // number
type Test2 = ElementType<string>;   // string
```

In this example, `ElementType` extracts the element type from an array. If the type `T` is an array, it returns the type of the elements; otherwise, it returns `T` itself.

**Example 3: Conditional types with union types**
```typescript
type ExcludeString<T> = T extends string ? never : T;

type Test1 = ExcludeString<string | number | boolean>; // number | boolean
```

Here, `ExcludeString` removes `string` from a union type.

Conditional types are useful for creating more flexible and reusable type utilities that can adapt based on the input types.

### 54. **How do you create a type-safe `factory function` in TypeScript?**

**Answer:**
A factory function is a function that returns an instance of a class or an object. In TypeScript, you can create a type-safe factory function by using generics and constraints.

**Example 1: Factory function for classes**
```typescript
class Dog {
  bark() {
    console.log("Woof!");
  }
}

class Cat {
  meow() {
    console.log("Meow!");
  }
}

type Constructor<T> = new (...args: any[]) => T;

function createInstance<T>(ctor: Constructor<T>): T {
  return new ctor();
}

const dog = createInstance(Dog); // TypeScript knows `dog` is of type `Dog`
dog.bark(); // Valid

const cat = createInstance(Cat); // TypeScript knows `cat` is of type `Cat`
cat.meow(); // Valid
```

In this example, `createInstance` is a factory function that takes a class constructor and returns an instance of that class. The function is generic, so it works with any class type.

**Example 2: Factory function for objects**
```typescript
type User = {
  name: string;
  age: number;
};

function createUser(name: string, age: number): User {
  return { name, age };
}

const user = createUser("John", 30); // TypeScript knows `user` is of type `User`
console.log(user.name); // Valid
```

Here, `createUser` is a factory function that creates an object of type `User`. The function is type-safe because it returns an object that adheres to the `User` type.

Factory functions are useful when you want to encapsulate object creation logic while ensuring that the resulting objects conform to a specific type.

Here are more TypeScript interview questions and answers, starting from number 55:

### 55. **What are "index types" in TypeScript, and how do they work?**

**Answer:**
Index types in TypeScript allow you to reference the types of properties in an object type using keys. They provide a way to work with the keys and values of an object type in a type-safe manner.

**Example 1: Using `keyof` and index access types**
```typescript
interface Person {
  name: string;
  age: number;
}

type PersonKeys = keyof Person; // "name" | "age"

type NameType = Person["name"]; // string
type AgeType = Person["age"]; // number
```

In this example, `keyof Person` creates a union type of all the keys in the `Person` interface, which is `"name" | "age"`. The index access type, `Person["name"]`, retrieves the type associated with the `name` property, which is `string`.

**Example 2: Using index types with generics**
```typescript
function getProperty<T, K extends keyof T>(obj: T, key: K): T[K] {
  return obj[key];
}

const person: Person = { name: "John", age: 30 };
const name = getProperty(person, "name"); // TypeScript infers that 'name' is of type 'string'
```

In this example, the `getProperty` function uses a generic constraint (`K extends keyof T`) to ensure that `key` is a valid property key of the object `obj`. The return type is then `T[K]`, representing the type of the value at the specified key.

Index types are particularly useful for creating flexible and type-safe utilities that operate on object properties.

### 56. **What is the "readonly" modifier in TypeScript, and how does it differ from `const`?**

**Answer:**
The `readonly` modifier in TypeScript is used to mark properties of an object as immutable, meaning their values cannot be changed after they are assigned.

**Key differences between `readonly` and `const`:**

1. **Usage Context**:
   - **`readonly`**: Used on properties within classes, interfaces, or types. It enforces immutability at the property level, meaning once a property is assigned a value, it cannot be reassigned.
   - **`const`**: Used for variables. It enforces immutability at the variable level, meaning the variable cannot be reassigned after its initial value is set.

2. **Mutability of the contents**:
   - **`readonly`**: While `readonly` prevents reassignment of the property, it does not make the contents of the object immutable. For example, you can still modify the contents of a `readonly` array.
   - **`const`**: Similarly, a `const` variable cannot be reassigned, but the contents of an object or array it refers to can still be modified.

**Example:**
```typescript
class Point {
  readonly x: number;
  readonly y: number;

  constructor(x: number, y: number) {
    this.x = x;
    this.y = y;
  }
}

const point = new Point(10, 20);
// point.x = 5; // Error: Cannot assign to 'x' because it is a read-only property

const arr: readonly number[] = [1, 2, 3];
// arr.push(4); // Error: Property 'push' does not exist on type 'readonly number[]'

const obj = { name: "John" } as const;
// obj.name = "Doe"; // Error: Cannot assign to 'name' because it is a read-only property
```

In this example, `readonly` is used to ensure that the properties `x` and `y` in the `Point` class cannot be changed after they are set in the constructor.

### 57. **What is the "Mapped Types" feature in TypeScript?**

**Answer:**
Mapped types in TypeScript allow you to create new types by transforming existing types. You can map over the properties of an existing type and create a new type with modified properties.

**Example 1: Creating a partial type**
```typescript
type Person = {
  name: string;
  age: number;
  address: string;
};

type PartialPerson = {
  [K in keyof Person]?: Person[K];
};

// Equivalent to:
type PartialPersonManual = {
  name?: string;
  age?: number;
  address?: string;
};
```

In this example, `PartialPerson` is a mapped type that makes all properties of `Person` optional. The `[K in keyof Person]` syntax iterates over each key in `Person` and makes it optional using the `?` modifier.

**Example 2: Readonly type**
```typescript
type ReadonlyPerson = {
  readonly [K in keyof Person]: Person[K];
};

// Equivalent to:
type ReadonlyPersonManual = {
  readonly name: string;
  readonly age: number;
  readonly address: string;
};
```

Here, `ReadonlyPerson` is a mapped type that makes all properties of `Person` read-only.

**Example 3: Mapping over union types**
```typescript
type Keys = "option1" | "option2" | "option3";
type Flags = { [K in Keys]: boolean };

// Equivalent to:
type FlagsManual = {
  option1: boolean;
  option2: boolean;
  option3: boolean;
};
```

In this example, `Flags` creates an object type where each key from the `Keys` union is mapped to a `boolean` type.

Mapped types are useful for creating utility types like `Partial`, `Readonly`, `Pick`, and `Record`, which are widely used in TypeScript to manipulate and transform types.

### 58. **What are "template literal types" in TypeScript, and how do they work?**

**Answer:**
Template literal types in TypeScript are a way to create new string types by combining other string types or literal values with a template literal syntax. They allow you to define types based on string patterns.

**Example 1: Basic template literal types**
```typescript
type Greeting = "Hello" | "Hi";
type Name = "John" | "Jane";

type PersonalizedGreeting = `${Greeting}, ${Name}!`;

// Equivalent to:
// type PersonalizedGreeting = "Hello, John!" | "Hello, Jane!" | "Hi, John!" | "Hi, Jane!";
```

In this example, `PersonalizedGreeting` is a type that represents all possible combinations of the greetings and names, creating a union of string literals.

**Example 2: Combining with other types**
```typescript
type ResponseCode = 200 | 404 | 500;
type StatusMessage = `Response: ${ResponseCode}`;

// Equivalent to:
// type StatusMessage = "Response: 200" | "Response: 404" | "Response: 500";
```

Here, `StatusMessage` is a template literal type that combines a string literal with a numeric union type to form different status messages.

**Example 3: Dynamic property keys**
```typescript
type Prefix = "get" | "set";
type Property = "Name" | "Age";

type MethodName = `${Prefix}${Property}`;

// Equivalent to:
// type MethodName = "getName" | "setName" | "getAge" | "setAge";
```

In this example, `MethodName` represents all possible combinations of prefixes and properties, commonly used to create method names in a type-safe way.

Template literal types are powerful for creating dynamic string-based types and are particularly useful when working with patterns, such as creating keys or messages in a type-safe manner.

### 59. **How does TypeScript's "as const" assertion work?**

**Answer:**
The `as const` assertion in TypeScript is used to create immutable values from objects, arrays, or literals. When you use `as const`, TypeScript infers the narrowest possible type for the value, making it a literal type or a tuple instead of a broader type like `string` or `number`.

**Example 1: Literal types with `as const`**
```typescript
const color = "blue" as const;
// TypeScript infers color as type "blue" (literal type)
```

Without `as const`, TypeScript would infer `color` as `string`, but with `as const`, it infers `color` as the literal type `"blue"`.

**Example 2: Immutable arrays and objects**
```typescript
const point = [10, 20] as const;
// TypeScript infers point as type readonly [10, 20]

const config = {
  environment: "production",
  port: 3000,
} as const;
// TypeScript infers config as:
// {
//   readonly environment: "production";
//   readonly port: 3000;
// }
```

In these examples, using `as const` makes the array `point` a tuple type, `[10, 20]`, and the object `config` an immutable object with literal types for its properties.

**Example 3: Using `as const` with unions**
```typescript
const directions = ["up", "down", "left", "right"] as const;
type Direction = typeof directions[number];
// Type Direction = "up" | "down" | "left" | "right";
```

Here, `as const` is used to create a tuple, and then `typeof directions[number]` extracts the union of all possible values in the tuple.

`as const` is particularly useful when you want to ensure that certain values remain constant and that TypeScript treats them as literal types, providing stronger type safety and preventing unintended modifications.

Here are more TypeScript interview questions and answers, starting from number 60:

### 60. **What are "conditional types" in TypeScript, and how do they work?**

**Answer:**
Conditional types in TypeScript allow you to create types that depend on a condition. They follow the syntax `T extends U ? X : Y`, where if type `T` extends type `U`, the type resolves to `X`; otherwise, it resolves to `Y`.

**Example 1: Basic conditional types**
```typescript
type IsString<T> = T extends string ? "Yes" : "No";

type A = IsString<string>; // "Yes"
type B = IsString<number>; // "No"
```

In this example, `IsString` is a conditional type that checks if the provided type `T` extends `string`. If it does, it returns `"Yes"`; otherwise, it returns `"No"`.

**Example 2: Inferring types within conditional types**
```typescript
type ElementType<T> = T extends (infer U)[] ? U : T;

type A = ElementType<string[]>; // string
type B = ElementType<number>; // number
```

Here, `ElementType` uses `infer` to extract the element type from an array. If `T` is an array type, `U` will be the element type; otherwise, it returns `T` as is.

**Example 3: Distributive conditional types**
```typescript
type Filter<T, U> = T extends U ? never : T;

type A = Filter<string | number | boolean, boolean>; // string | number
```

In this example, `Filter` removes any types from the union `T` that extend `U`. If `T` is a union type, the conditional type is applied to each member of the union, resulting in a new union.

Conditional types are powerful for creating complex type transformations and utilities, enabling more dynamic and flexible type definitions in TypeScript.

### 61. **How does TypeScript handle function overloads?**

**Answer:**
TypeScript supports function overloading, allowing you to define multiple signatures for a function. This enables a function to behave differently based on the types of its arguments.

**Key concepts:**

1. **Overload signatures**: These are the various signatures you define at the top of the function definition, specifying the different argument and return type combinations.
2. **Implementation signature**: This is the actual implementation of the function that handles all overloads. The implementation must be compatible with all overload signatures.

**Example:**
```typescript
function getLength(value: string): number;
function getLength(value: any[]): number;
function getLength(value: any): number {
  return value.length;
}

const length1 = getLength("hello"); // 5
const length2 = getLength([1, 2, 3]); // 3
```

In this example, `getLength` has two overload signatures—one for strings and one for arrays. The implementation signature is a general function that works for both cases, and TypeScript will use the appropriate signature based on the arguments provided.

**Important considerations**:

- The implementation signature should be broad enough to cover all overloads.
- The overload signatures should be listed before the implementation.
- Overloads should be as specific as possible, with more general signatures listed last.

Function overloads are useful when a function can operate on different types and you want to provide specific type information for each case.

### 62. **What is the purpose of "utility types" in TypeScript, and can you give examples?**

**Answer:**
Utility types in TypeScript are predefined types that help you transform or manipulate other types. They are built-in types provided by TypeScript to perform common type transformations, making your code more concise and expressive.

**Common utility types:**

1. **`Partial<T>`**: Makes all properties in `T` optional.
   ```typescript
   interface Person {
     name: string;
     age: number;
   }

   type PartialPerson = Partial<Person>;
   // Equivalent to:
   // type PartialPerson = {
   //   name?: string;
   //   age?: number;
   // }
   ```

2. **`Required<T>`**: Makes all properties in `T` required.
   ```typescript
   interface Person {
     name?: string;
     age?: number;
   }

   type RequiredPerson = Required<Person>;
   // Equivalent to:
   // type RequiredPerson = {
   //   name: string;
   //   age: number;
   // }
   ```

3. **`Readonly<T>`**: Makes all properties in `T` readonly.
   ```typescript
   interface Person {
     name: string;
     age: number;
   }

   type ReadonlyPerson = Readonly<Person>;
   // Equivalent to:
   // type ReadonlyPerson = {
   //   readonly name: string;
   //   readonly age: number;
   // }
   ```

4. **`Pick<T, K extends keyof T>`**: Creates a type by picking a subset of properties `K` from `T`.
   ```typescript
   interface Person {
     name: string;
     age: number;
     address: string;
   }

   type NameAndAge = Pick<Person, "name" and "age">;
   // Equivalent to:
   // type NameAndAge = {
   //   name: string;
   //   age: number;
   // }
   ```

5. **`Omit<T, K extends keyof any>`**: Creates a type by omitting a subset of properties `K` from `T`.
   ```typescript
   interface Person {
     name: string;
     age: number;
     address: string;
   }

   type PersonWithoutAddress = Omit<Person, "address">;
   // Equivalent to:
   // type PersonWithoutAddress = {
   //   name: string;
   //   age: number;
   // }
   ```

6. **`Record<K extends keyof any, T>`**: Creates a type with a set of properties `K`, all of type `T`.
   ```typescript
   type Roles = "admin" | "user" | "guest";
   type RolePermissions = Record<Roles, boolean>;
   // Equivalent to:
   // type RolePermissions = {
   //   admin: boolean;
   //   user: boolean;
   //   guest: boolean;
   // }
   ```

Utility types simplify common type manipulations, making code more maintainable and type-safe.

### 63. **What is the "never" type in TypeScript, and when is it used?**

**Answer:**
The `never` type in TypeScript represents a type that contains no values. It is used to indicate that a function never returns (e.g., it throws an error or enters an infinite loop) or when a type should not be possible.

**Example 1: Functions that never return**
```typescript
function throwError(message: string): never {
  throw new Error(message);
}

function infiniteLoop(): never {
  while (true) {}
}
```

In this example, `throwError` and `infiniteLoop` are functions that never successfully complete execution, so they are typed as `never`.

**Example 2: Exhaustiveness checking in `switch` statements**
```typescript
type Shape = "circle" | "square";

function getArea(shape: Shape): number {
  switch (shape) {
    case "circle":
      return Math.PI * 1 * 1;
    case "square":
      return 1 * 1;
    default:
      const _exhaustiveCheck: never = shape;
      throw new Error(`Unhandled shape: ${shape}`);
  }
}
```

Here, the `_exhaustiveCheck` variable is typed as `never`. If a new shape is added to the `Shape` union and not handled in the `switch` statement, TypeScript will raise an error, ensuring that all cases are covered.

The `never` type is essential for type safety, ensuring that unreachable code or unhandled cases are flagged by TypeScript.

### 64. **How does TypeScript's type inference work?**

**Answer:**
TypeScript's type inference automatically determines the types of variables, function return values, and other expressions without explicit type annotations. This helps reduce the need for verbose type annotations while maintaining type safety.

**Key points of type inference:**

1. **Variable inference**:
   ```typescript
   let num = 10; // TypeScript infers 'num' as 'number'
   let str = "hello"; // TypeScript infers 'str' as 'string'
   ```

2. **Function return type inference**:
   ```typescript
   function add(a: number, b: number) {
     return a + b; // TypeScript infers return type as 'number'
   }
   ```

3. **Contextual typing**:
   ```typescript
   const handler = (event: MouseEvent) => {
     console.log(event.clientX); // TypeScript infers 'event' as 'MouseEvent'
   };

   window.addEventListener("click", handler);
   ```

4. **Best common type**:
   ```typescript
   let arr = [1, "hello", true]; // TypeScript infers 'arr' as (number | string | boolean)[]
   ```

5. **Type inference with generics**:
   ```typescript
   function identity<T>(arg: T): T {
     return arg;
   }

   let output = identity("hello"); // TypeScript infers 'T' as 'string'
   ```

Type inference allows TypeScript to automatically determine types based on the values and context, reducing the need for explicit annotations while preserving type safety.
