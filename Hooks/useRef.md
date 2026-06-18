# useRef Hook

## Definition

`useRef` is a React Hook used to store values and access DOM elements without re-rendering the component.

---

## Why use useRef?

* To access DOM elements directly.
* To store values between renders.
* To avoid unnecessary re-renders.
* To keep track of previous values.
* To store timer or interval IDs.

---

## When to Use useRef?

Use `useRef` when:

* You need direct access to a DOM element.
* You want to focus an input field.
* You need to store values without re-rendering.
* You want to track previous state values.
* You need to store timers or intervals.

---

## Syntax

```jsx
const ref = useRef(initialValue);
```

---

## Parameters

* `ref` → Reference object.
* `initialValue` → Initial value stored in the ref.

---

## Accessing the Value

```jsx
ref.current
```

`current` contains the actual value stored inside the ref.

---

## Example 1: Storing a Value

```jsx
import { useRef } from "react";

function Counter() {
  const countRef = useRef(0);

  const increment = () => {
    countRef.current++;
    console.log(countRef.current);
  };

  return <button onClick={increment}>Increment</button>;
}
```

---

## Example 2: Accessing DOM Elements

```jsx
import { useRef } from "react";

function App() {
  const inputRef = useRef();

  const focusInput = () => {
    inputRef.current.focus();
  };

  return (
    <>
      <input ref={inputRef} />
      <button onClick={focusInput}>
        Focus Input
      </button>
    </>
  );
}
```

---

## How useRef Works

1. React creates a ref object.
2. The object remains the same across renders.
3. Updating `ref.current` does not trigger a re-render.
4. The value persists between renders.

Flow:

Create Ref → Store Value → Update current → No Re-render

---

## Common Use Cases

### Input Focus

```jsx
const inputRef = useRef();
```

### Previous Value Tracking

```jsx
const prevCount = useRef();
```

### Timer IDs

```jsx
const timerRef = useRef();
```

### DOM Manipulation

```jsx
inputRef.current.focus();
```

---

## Important Points

* useRef persists values across renders.
* Updating `ref.current` does not trigger a re-render.
* Ref values are mutable.
* Commonly used for DOM access.
* The ref object remains the same throughout the component lifecycle.

---

## useRef vs useState

| useRef                  | useState            |
| ----------------------- | ------------------- |
| Does not re-render      | Causes re-render    |
| Stores mutable values   | Stores UI state     |
| Accessed using current  | Accessed directly   |
| Used for DOM references | Used for UI updates |

---

## Interview Questions

### What is useRef?

useRef is a React Hook used to store mutable values and access DOM elements without causing re-renders.

### Does useRef trigger re-rendering?

No. Updating `ref.current` does not trigger a component re-render.

### What is ref.current?

It is the property that stores the actual value of the ref.

### Why use useRef instead of useState?

Because useRef can store values without causing re-renders, making it more efficient for non-UI data.

### Can useRef access DOM elements?

Yes. It is commonly used to directly access and manipulate DOM elements.

### Does useRef persist between renders?

Yes. The same ref object persists throughout the component lifecycle.

---
