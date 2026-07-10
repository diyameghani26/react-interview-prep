# Higher-Order Component (HOC)

## Definition

A **Higher-Order Component (HOC)** is an advanced React pattern used to reuse component logic. It is a function that takes a component as an argument and returns a new component with additional functionality or behavior.

---

## Why use HOC?

- To reuse component logic.
- To avoid code duplication.
- To separate business logic from UI.
- To add extra functionality without modifying the original component.

---

## When to Use HOC?

Use HOCs when:

- Multiple components share the same logic.
- You want to add authentication or authorization.
- You need logging or analytics.
- You want to fetch data before rendering a component.

---

## Syntax

```jsx
const EnhancedComponent = higherOrderComponent(Component);
```

---

## Example

```jsx
function withLogger(WrappedComponent) {
  return function EnhancedComponent(props) {
    console.log("Component Rendered");

    return <WrappedComponent {...props} />;
  };
}
```

Using the HOC:

```jsx
function Home() {
  return <h1>Home Page</h1>;
}

export default withLogger(Home);
```

Whenever the `Home` component renders, the message **"Component Rendered"** is logged before rendering the component.

---

## How HOC Works

1. Create a Higher-Order Component.
2. Pass a component to it.
3. The HOC returns a new enhanced component.
4. Render the enhanced component.

Flow:

```
Component
     ↓
Higher-Order Component
     ↓
Enhanced Component
     ↓
Rendered UI
```

---

## Common Use Cases

- Authentication
- Authorization
- Logging
- Data Fetching
- Analytics
- Permission Checking

---

## Advantages

- Promotes code reusability.
- Reduces duplicate code.
- Keeps components clean.
- Separates logic from UI.

---

## Important Points

- An HOC is a function, not a React Hook.
- It takes a component as input.
- It returns a new enhanced component.
- It does not modify the original component.
- Used to reuse component logic.

---

## Common Interview Mistakes

❌ **HOC is a React Hook.**

✅ Wrong.

An HOC is a JavaScript function that returns a new component.

---

❌ **HOCs modify the original component.**

✅ Wrong.

They wrap the original component and return a new enhanced component.

---

## Interview Questions

### What is a Higher-Order Component (HOC)?

A Higher-Order Component is a function that takes a component as an argument and returns a new component with additional functionality.

### Why do we use HOCs?

To reuse component logic and avoid code duplication.

### Is HOC a React Hook?

No. It is a design pattern used for component reuse.

### Can HOCs modify the original component?

No. They return a new enhanced component without changing the original one.

### What are common use cases of HOCs?

Authentication, authorization, logging, analytics, and data fetching.

---

## One-Line Interview Answer

A Higher-Order Component (HOC) is a function that takes a component and returns a new component with additional functionality, enabling code reuse and separation of concerns.