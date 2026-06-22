# State

## Definition

State is a built-in React object used to store and manage data that can change over time.

When state changes, React automatically re-renders the component to update the UI.

---

## Why use State?

* To store dynamic data.
* To update the UI automatically.
* To manage user interactions.
* To handle changing values.
* To make applications interactive.

---

## When to Use State?

Use State when:

* Data changes over time.
* User interactions update the UI.
* Input fields need to store values.
* API data needs to be displayed.
* Component data must be managed locally.

---

## Syntax

```jsx
const [state, setState] = useState(initialValue);
```

---

## Parameters

* `state` → Current state value.
* `setState` → Function used to update state.
* `initialValue` → Initial state value.

---

## Example 1: Counter

```jsx
import { useState } from "react";

function App() {
  const [count, setCount] = useState(0);

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
    </>
  );
}
```

---

## Example 2: Input Field

```jsx
import { useState } from "react";

function App() {
  const [name, setName] = useState("");

  return (
    <>
      <input
        value={name}
        onChange={(e) =>
          setName(e.target.value)
        }
      />

      <h1>{name}</h1>
    </>
  );
}
```

---

## How State Works

1. React creates state with an initial value.
2. Component renders.
3. User interaction occurs.
4. State updates using setState.
5. React re-renders the component.
6. Updated UI is displayed.

Flow:

Create State → Render UI → Update State → Re-render → Updated UI

---

## State is Mutable Through setState

Wrong:

```jsx
count = count + 1;
```

Correct:

```jsx
setCount(count + 1);
```

React must be informed about state changes through the setter function.

---

## State Updates are Asynchronous

```jsx
setCount(count + 1);

console.log(count);
```

Output may still show the old value because React schedules state updates and processes them later.

---

## Functional Updates

When the new state depends on the previous state:

```jsx
setCount(prevCount => prevCount + 1);
```

Recommended approach for counters and repeated updates.

---

## Local State

State belongs to the component where it is created.

Example:

```jsx
function Counter() {
  const [count, setCount] =
    useState(0);
}
```

Other components cannot directly access this state.

---

## State vs Variables

Normal Variable:

```jsx
let count = 0;

count++;
```

React will NOT re-render.

State:

```jsx
const [count, setCount] =
  useState(0);

setCount(count + 1);
```

React WILL re-render.

---

## State vs Props

| State                    | Props                      |
| ------------------------ | -------------------------- |
| Managed inside component | Passed from parent         |
| Can be updated           | Read-only                  |
| Dynamic data             | External data              |
| Uses setter function     | Cannot be changed by child |

---

## Common Use Cases

### Counter

```jsx
const [count, setCount] =
  useState(0);
```

### Form Inputs

```jsx
const [name, setName] =
  useState("");
```

### Toggle UI

```jsx
const [isOpen, setIsOpen] =
  useState(false);
```

### API Data

```jsx
const [users, setUsers] =
  useState([]);
```

### Loading State

```jsx
const [loading, setLoading] =
  useState(true);
```

---

## Lifting State Up

Sometimes multiple components need the same state.

In such cases, move the state to their closest common parent component.

Example:

```txt
Parent
 ├── Child A
 └── Child B
```

State is stored in Parent and passed down through props.

This is called:

### Lifting State Up

---

## Important Points

* State stores dynamic data.
* Updating state triggers re-rendering.
* State is local to a component.
* State updates are asynchronous.
* Use setter functions to update state.
* State makes React applications interactive.

---

## Common Misconceptions

### Does changing a normal variable re-render React?

No.

Only state updates trigger re-renders.

### Can state be modified directly?

No.

Always use the setter function.

### Is state shared between components?

No.

Each component has its own state unless it is lifted up or shared through Context.

---

## Interview Questions

### What is State in React?

State is a built-in object used to store and manage dynamic data in a component.

### Why do we use State?

To store changing data and update the UI automatically.

### What happens when State changes?

React re-renders the component and updates the UI.

### What is the difference between State and Props?

State is managed inside a component and can be updated, while Props are passed from parent components and are read-only.

### Why are state updates asynchronous?

React batches updates to improve performance and avoid unnecessary re-renders.

### What is Lifting State Up?

Moving state to a common parent component so multiple child components can access it.

### Can we modify state directly?

No. State should always be updated using the setter function.

---

## One-Line Interview Answer

State is a React feature used to store dynamic data, and updating state automatically re-renders the component to update the UI.
