# useEffect Hook

## Definition

`useEffect` is a React Hook that allows you to perform side effects in functional components.

A side effect is any operation that interacts with something outside the component rendering process, such as API calls, timers, event listeners, or DOM updates.

---

## Why use useEffect?

* To fetch data from APIs.
* To run code after a component renders.
* To manage timers and intervals.
* To add and remove event listeners.
* To synchronize the UI with external systems.

---

## When to Use useEffect?

Use `useEffect` when:

* Fetching data from a server.
* Running code after render.
* Working with browser APIs.
* Setting up subscriptions.
* Managing side effects.

---

## Syntax

```jsx
useEffect(() => {
  // side effect code
}, [dependencies]);
```

---

## How useEffect Works

1. Component renders.
2. React updates the DOM.
3. useEffect runs after the render is completed.

Flow:

Render → DOM Update → useEffect Runs

---

## Dependency Array

### 1. No Dependency Array

```jsx
useEffect(() => {
  console.log("Runs after every render");
});
```

Runs after every render.

---

### 2. Empty Dependency Array

```jsx
useEffect(() => {
  console.log("Runs once");
}, []);
```

Runs only once when the component mounts.

---

### 3. With Dependencies

```jsx
useEffect(() => {
  console.log("Count changed");
}, [count]);
```

Runs whenever `count` changes.

---

## Example

```jsx
import { useEffect } from "react";

function App() {
  useEffect(() => {
    console.log("Component Mounted");
  }, []);

  return <h1>Hello React</h1>;
}
```

---

## Cleanup Function

Used to clean up resources when a component unmounts.

```jsx
useEffect(() => {
  const timer = setInterval(() => {
    console.log("Running...");
  }, 1000);

  return () => {
    clearInterval(timer);
  };
}, []);
```

---

## Why Cleanup is Important?

* Prevents memory leaks.
* Removes event listeners.
* Clears timers.
* Stops unnecessary background work.

---

## Common Use Cases

### API Fetching

```jsx
useEffect(() => {
  fetchData();
}, []);
```

### Event Listeners

```jsx
useEffect(() => {
  window.addEventListener("resize", handleResize);

  return () => {
    window.removeEventListener("resize", handleResize);
  };
}, []);
```

### Timers

```jsx
useEffect(() => {
  const timer = setTimeout(() => {
    console.log("Hello");
  }, 1000);

  return () => clearTimeout(timer);
}, []);
```

---

## Important Points

* useEffect runs after rendering.
* It handles side effects.
* Cleanup function runs before unmounting.
* Dependency array controls when the effect runs.
* Multiple useEffects can be used in one component.

---

## Interview Questions

### What is useEffect?

useEffect is a React Hook used to perform side effects in functional components.

### What is a side effect?

Any operation outside the rendering process such as API calls, timers, subscriptions, and event listeners.

### When does useEffect run?

After the component renders and the DOM is updated.

### What is the purpose of the dependency array?

It controls when the effect should re-run.

### What is a cleanup function?

A function returned from useEffect that cleans resources before unmounting or before the effect runs again.

### Can we use multiple useEffects?

Yes. A component can contain multiple useEffect Hooks.

---

## One-Line Interview Answer

useEffect is a React Hook that allows functional components to perform side effects after rendering and manage cleanup when necessary.
