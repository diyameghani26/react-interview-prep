# Components in React

## Definition

A **Component** is a reusable, independent piece of UI in React.

Each component contains its own structure, logic, and behavior, making applications easier to build and maintain.

---

## Why use Components?

* To reuse code.
* To make the application modular.
* To improve readability.
* To simplify maintenance.
* To build scalable applications.

---

## When to Use Components?

Use Components when:

* You want to reuse the same UI.
* A UI section has its own functionality.
* Your application becomes large.
* You want cleaner and organized code.

---

## Syntax

```jsx
function ComponentName() {
  return (
    <h1>Hello React</h1>
  );
}
```

---

## Example 1: Simple Component

```jsx
function Welcome() {
  return <h1>Welcome to React</h1>;
}

export default Welcome;
```

Using the component:

```jsx
import Welcome from "./Welcome";

function App() {
  return <Welcome />;
}
```

Output:

```txt
Welcome to React
```

---

## Example 2: Reusable Component

```jsx
function Card() {
  return (
    <div>
      <h2>React Course</h2>
      <p>Learn React from scratch.</p>
    </div>
  );
}
```

Using multiple times:

```jsx
function App() {
  return (
    <>
      <Card />
      <Card />
      <Card />
    </>
  );
}
```

Instead of writing the same HTML three times, we reuse the component.

---

## Types of Components

### 1. Functional Component

A Functional Component is a JavaScript function that returns JSX.

Example:

```jsx
function Welcome() {
  return <h1>Hello React</h1>;
}
```

This is the most commonly used component type in modern React.

---

### 2. Class Component

A Class Component is created using JavaScript classes.

Example:

```jsx
import React, { Component } from "react";

class Welcome extends Component {
  render() {
    return <h1>Hello React</h1>;
  }
}

export default Welcome;
```

Class Components were used before Hooks were introduced.

Nowadays, Functional Components are preferred.

---

## How Components Work

1. Create a component.
2. Return JSX.
3. Import the component where needed.
4. Render the component.
5. React displays the UI.

Flow:

Create Component → Return JSX → Import → Render → Display UI

---

## Naming Rules

✅ Component names must start with a capital letter.

Correct:

```jsx
function Header() {}
```

Wrong:

```jsx
function header() {}
```

React treats lowercase names as HTML elements.

---

## Component Composition

Large applications are built by combining small components.

Example:

```txt
App
│
├── Navbar
├── Hero
├── Services
├── Testimonials
├── Footer
```

Each component has its own responsibility.

---

## Reusable Components

One component can be used multiple times.

Example:

```jsx
<Card />
<Card />
<Card />
```

This reduces duplicate code and improves maintainability.

---

## Components vs Functions

| Component                    | Normal Function                              |
| ---------------------------- | -------------------------------------------- |
| Returns JSX                  | Returns any JavaScript value                 |
| Used to build UI             | Used for general logic                       |
| Starts with a capital letter | No naming rule                               |
| Can use React Hooks          | Cannot use Hooks (unless it's a Custom Hook) |

---

## Functional Component vs Class Component

| Functional Component      | Class Component               |
| ------------------------- | ----------------------------- |
| JavaScript function       | JavaScript class              |
| Uses Hooks                | Uses lifecycle methods        |
| Less code                 | More boilerplate              |
| Easier to understand      | More complex                  |
| Preferred in modern React | Mostly used in older projects |

---

## Advantages of Components

### Reusability

Write once, use multiple times.

### Maintainability

Changes in one component automatically reflect everywhere it is used.

### Better Organization

Keeps code modular and easy to understand.

### Scalability

Makes large applications easier to manage.

### Easy Testing

Each component can be tested independently.

---

## Important Points

* Components are the building blocks of React applications.
* Components return JSX.
* Component names must start with a capital letter.
* Components are reusable.
* Functional Components are preferred in modern React.
* Components can receive Props and manage State.

---

## Common Misconceptions

### Is every JavaScript function a React Component?

No.

Only functions that return JSX and follow React's component rules are React Components.

### Can one component use another component?

Yes.

Components can be nested inside other components.

### Are Class Components still used?

Yes, but Functional Components are preferred in modern React because of Hooks.

---

## Interview Questions

### What is a Component in React?

A Component is a reusable and independent piece of UI that returns JSX.

### Why do we use Components?

To build reusable, modular, and maintainable user interfaces.

### What are the types of Components?

Functional Components and Class Components.

### Which Component type is preferred today?

Functional Components because they are simpler and support Hooks.

### Can Components be reused?

Yes. A single component can be rendered multiple times.

### Why should Component names start with a capital letter?

React uses capitalized names to identify custom components and lowercase names for HTML elements.

---

## One-Line Interview Answer

A React Component is a reusable and independent piece of UI that returns JSX and helps build modular, maintainable applications.
