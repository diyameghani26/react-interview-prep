# useCallback Hook

## Definition

`useCallback` is a React Hook that memoizes a function and returns the same function reference unless its dependencies change.

It helps improve performance by preventing unnecessary function recreation.

---

## Why use useCallback?

* To optimize performance.
* To prevent unnecessary function creation.
* To avoid unnecessary child component re-renders.
* To maintain the same function reference between renders.
* To work efficiently with React.memo.

---

## When to Use useCallback?

Use `useCallback` when:

* Passing functions to child components.
* Working with React.memo.
* Preventing unnecessary re-renders.
* Optimizing large applications.
* Function recreation affects performance.

---

## Syntax

```jsx
const memoizedFunction = useCallback(() => {
  // function logic
}, [dependencies]);
```

---

## Parameters

* `callback function` → Function to be memoized.
* `dependencies` → Values that determine when the function should be recreated.

---

## Example 1: Basic Example

```jsx
import { useCallback } from "react";

function App() {
  const handleClick = useCallback(() => {
    console.log("Button Clicked");
  }, []);

  return <button onClick={handleClick}>Click Me</button>;
}
```

---

## Example 2: Preventing Child Re-renders

```jsx
import React, {
  useState,
  useCallback,
} from "react";

const Child = React.memo(({ onClick }) => {
  console.log("Child Rendered");

  return (
    <button onClick={onClick}>
      Click
    </button>
  );
});

function App() {
  const [count, setCount] = useState(0);

  const handleClick = useCallback(() => {
    console.log("Clicked");
  }, []);

  return (
    <>
      <h1>{count}</h1>

      <button
        onClick={() =>
          setCount(count + 1)
        }
      >
        Increment
      </button>

      <Child onClick={handleClick} />
    </>
  );
}
```

Without useCallback, a new function is created on every render.

With useCallback, the same function reference is reused.

---

## How useCallback Works

1. React creates the function.
2. Function reference is stored.
3. React checks dependencies during re-render.
4. If dependencies haven't changed, the same function is reused.
5. If dependencies change, a new function is created.

Flow:

Create Function → Store Reference → Re-render → Check Dependencies → Reuse or Recreate Function

---

## Common Use Cases

### Event Handlers

```jsx
const handleClick = useCallback(() => {
  console.log("Clicked");
}, []);
```

### React.memo Optimization

```jsx
const handleSubmit = useCallback(() => {
  submitForm();
}, []);
```

### Passing Functions to Children

```jsx
<Child onSave={handleSave} />
```

### Large Applications

```jsx
const fetchData = useCallback(() => {
  // fetch logic
}, []);
```

---

## Important Points

* useCallback memoizes functions.
* It improves performance.
* It prevents unnecessary function recreation.
* It is commonly used with React.memo.
* It recreates the function only when dependencies change.
* Overusing useCallback can make code harder to maintain.

---

## useCallback vs useMemo

| useCallback                    | useMemo                           |
| ------------------------------ | --------------------------------- |
| Memoizes functions             | Memoizes values                   |
| Returns a function             | Returns a value                   |
| Used for function optimization | Used for calculation optimization |
| Prevents function recreation   | Prevents value recalculation      |

---

## useCallback vs useRef

| useCallback                        | useRef                          |
| ---------------------------------- | ------------------------------- |
| Stores function reference          | Stores mutable values           |
| Used for optimization              | Used for value persistence      |
| Recreates when dependencies change | Does not recreate automatically |
| Returns a function                 | Returns a ref object            |

---

## Interview Questions

### What is useCallback?

useCallback is a React Hook that memoizes a function and returns the same function reference until dependencies change.

### Why use useCallback?

To prevent unnecessary function recreation and improve performance.

### Does useCallback prevent re-renders?

No. It prevents unnecessary function recreation, but not component re-renders directly.

### When should you use useCallback?

When passing functions to child components or optimizing performance.

### What is the difference between useCallback and useMemo?

useCallback memoizes functions, while useMemo memoizes values.

### Is useCallback always necessary?

No. It should only be used when there is a real performance benefit.

### Does useCallback improve performance?

Yes, especially when working with React.memo and large component trees.

---
