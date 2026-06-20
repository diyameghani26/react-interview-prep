# Custom Hooks

## Definition

A Custom Hook is a JavaScript function that uses one or more React Hooks and allows you to reuse stateful logic across multiple components.

Custom Hooks always start with the word `use`.

---

## Why use Custom Hooks?

* To reuse logic between components.
* To keep components clean and readable.
* To avoid code duplication.
* To separate business logic from UI.
* To improve code maintainability.

---

## When to Use Custom Hooks?

Use Custom Hooks when:

* The same logic is used in multiple components.
* Components become too large.
* You want cleaner and more reusable code.
* You need to share stateful behavior.

---

## Syntax

```jsx
function useCustomHook() {
  // Hook logic

  return value;
}
```

---

## Naming Rule

Custom Hooks must start with `use`.

✅ Correct

```jsx
function useCounter() {}
```

❌ Wrong

```jsx
function counter() {}
```

---

## Example 1: Custom Counter Hook

### useCounter.js

```jsx
import { useState } from "react";

function useCounter() {
  const [count, setCount] = useState(0);

  const increment = () => {
    setCount(count + 1);
  };

  const decrement = () => {
    setCount(count - 1);
  };

  return {
    count,
    increment,
    decrement,
  };
}

export default useCounter;
```

### App.jsx

```jsx
import useCounter from "./useCounter";

function App() {
  const {
    count,
    increment,
    decrement,
  } = useCounter();

  return (
    <>
      <h1>{count}</h1>

      <button onClick={increment}>
        +
      </button>

      <button onClick={decrement}>
        -
      </button>
    </>
  );
}
```

---

## Example 2: Custom Window Width Hook

### useWindowWidth.js

```jsx
import {
  useState,
  useEffect,
} from "react";

function useWindowWidth() {
  const [width, setWidth] = useState(
    window.innerWidth
  );

  useEffect(() => {
    const handleResize = () => {
      setWidth(window.innerWidth);
    };

    window.addEventListener(
      "resize",
      handleResize
    );

    return () => {
      window.removeEventListener(
        "resize",
        handleResize
      );
    };
  }, []);

  return width;
}

export default useWindowWidth;
```

### App.jsx

```jsx
const width = useWindowWidth();

return <h1>{width}</h1>;
```

---

## How Custom Hooks Work

1. Create a function starting with `use`.
2. Use React Hooks inside it.
3. Return values or functions.
4. Import the custom hook into components.
5. Reuse the same logic anywhere.

Flow:

Create Hook → Add Logic → Return Values → Import Hook → Reuse Logic

---

## Common Use Cases

### Form Handling

```jsx
const form = useForm();
```

### API Calls

```jsx
const data = useFetch(url);
```

### Authentication

```jsx
const auth = useAuth();
```

### Theme Management

```jsx
const theme = useTheme();
```

### Window Size Tracking

```jsx
const width = useWindowWidth();
```

---

## Important Points

* Custom Hooks are reusable functions.
* They can use other React Hooks.
* They help avoid duplicate code.
* They keep components clean.
* They must start with `use`.
* Every component using a Custom Hook gets its own state.

---

## Custom Hook vs Normal Function

| Custom Hook                   | Normal Function                    |
| ----------------------------- | ---------------------------------- |
| Can use React Hooks           | Cannot use React Hooks             |
| Starts with `use`             | No naming rule                     |
| Used for reusable React logic | Used for general JavaScript logic  |
| Can manage state              | Cannot directly manage React state |

---

## Interview Questions

### What is a Custom Hook?

A Custom Hook is a reusable JavaScript function that uses React Hooks to share stateful logic between components.

### Why do we use Custom Hooks?

To reuse logic, avoid duplication, and keep components clean.

### Can Custom Hooks use other Hooks?

Yes. They can use any React Hook such as useState, useEffect, useRef, etc.

### Why must Custom Hooks start with "use"?

React uses this naming convention to identify Hooks and enforce Hook rules.

### Do Custom Hooks share state between components?

No. Each component gets its own separate state.

### Can we create multiple Custom Hooks?

Yes. Applications can contain many Custom Hooks for different purposes.

---

## One-Line Interview Answer

Custom Hooks are reusable functions that use React Hooks to share stateful logic between components.
