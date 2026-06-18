# useMemo Hook

## Definition

`useMemo` is a React Hook that stores a calculated value and reuses it until its dependencies change.

It helps improve performance by avoiding unnecessary recalculations.

---

## Why use useMemo?

* To improve application performance.
* To avoid expensive calculations on every render.
* To cache computed values.
* To reduce unnecessary work during re-renders.
* To optimize large applications.

---

## When to Use useMemo?

Use `useMemo` when:

* A calculation is expensive.
* The result doesn't need to be recalculated on every render.
* You want to optimize performance.
* You are working with large datasets.
* You need to prevent unnecessary computations.

---

## Syntax

```jsx
const memoizedValue = useMemo(() => {
  return calculation();
}, [dependencies]);
```

---

## Parameters

* `callback function` → Function that returns the value to be memoized.
* `dependencies` → Array of values that determine when the calculation should run again.

---

## Example 1: Basic Calculation

```jsx
import { useMemo } from "react";

function App() {
  const number = 5;

  const squaredNumber = useMemo(() => {
    return number * number;
  }, [number]);

  return <h1>{squaredNumber}</h1>;
}
```

---

## Example 2: Expensive Calculation

```jsx
import { useMemo, useState } from "react";

function App() {
  const [count, setCount] = useState(0);

  const expensiveValue = useMemo(() => {
    console.log("Calculating...");
    
    let result = 0;
    
    for (let i = 0; i < 1000000000; i++) {
      result += i;
    }

    return result;
  }, []);

  return (
    <>
      <h1>{count}</h1>

      <button onClick={() => setCount(count + 1)}>
        Increment
      </button>

      <p>{expensiveValue}</p>
    </>
  );
}
```

Even if the component re-renders, the expensive calculation runs only once because the dependency array is empty.

---

## How useMemo Works

1. React executes the calculation.
2. The result is stored in memory.
3. On re-render, React checks dependencies.
4. If dependencies have not changed, React returns the stored value.
5. If dependencies change, React recalculates the value.

Flow:

Calculate Value → Store Result → Re-render → Check Dependencies → Reuse or Recalculate

---

## Common Use Cases

### Expensive Calculations

```jsx
const total = useMemo(() => {
  return calculateTotal(items);
}, [items]);
```

### Filtering Large Lists

```jsx
const filteredUsers = useMemo(() => {
  return users.filter(user =>
    user.name.includes(searchTerm)
  );
}, [users, searchTerm]);
```

### Sorting Data

```jsx
const sortedProducts = useMemo(() => {
  return [...products].sort();
}, [products]);
```

### Derived State

```jsx
const fullName = useMemo(() => {
  return firstName + " " + lastName;
}, [firstName, lastName]);
```

---

## Important Points

* useMemo memoizes values.
* It improves performance.
* It recalculates only when dependencies change.
* It stores the result of a calculation.
* It should be used only when optimization is needed.
* Overusing useMemo can make code harder to read.

---

## useMemo vs useState

| useMemo                               | useState                        |
| ------------------------------------- | ------------------------------- |
| Stores calculated values              | Stores component state          |
| Used for optimization                 | Used for managing UI state      |
| Recalculates when dependencies change | Updates through setter function |
| Improves performance                  | Triggers UI updates             |

---

## useMemo vs useRef

| useMemo                               | useRef                                    |
| ------------------------------------- | ----------------------------------------- |
| Stores calculated values              | Stores mutable values                     |
| Recalculates when dependencies change | Never recalculates automatically          |
| Used for optimization                 | Used for DOM access and value persistence |
| Returns a value                       | Returns a ref object                      |

---

## Interview Questions

### What is useMemo?

useMemo is a React Hook that memoizes a calculated value and recalculates it only when dependencies change.

### Why use useMemo?

To improve performance by avoiding unnecessary calculations during re-renders.

### Does useMemo prevent re-renders?

No. It prevents unnecessary recalculations, not re-renders.

### What is memoization?

Memoization is an optimization technique where the result of a calculation is stored and reused instead of being recalculated.

### When should you use useMemo?

When calculations are expensive and performance optimization is needed.

### Can useMemo improve performance?

Yes. It can reduce unnecessary computations and improve application performance.

### Should useMemo be used everywhere?

No. It should only be used when there is a real performance benefit.

---

## One-Line Interview Answer

useMemo is a React Hook that caches a calculated value and recalculates it only when its dependencies change.
