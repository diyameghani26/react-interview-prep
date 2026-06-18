# UseState Hook

## Definition

`useState` is a React Hook that allows functional components to store and update data (state). When the state changes, React automatically re-renders the component with the updated value.

## Why use useState?

* To store dynamic data inside a component.
* To make the UI interactive.
* To update the screen when data changes.
* To manage values such as counters, forms, toggles, and user input.

## When to Use useState?

Use `useState` when:

* A value needs to change over time.
* User actions update the UI.
* You need to store form input values.
* You need to manage toggle states (open/close, show/hide).
* You need to keep track of counters, likes, or selected items.

## Example Use Cases

* Counter Application
* Dark/Light Theme Toggle
* Login Form Inputs
* Modal Open/Close State
* Like Button Counter


## Syntax

```jsx
const [state, setState] = useState(initialValue);
```

### Parameters

* `state` → Current state value.
* `setState` → Function used to update the state.
* `initialValue` → Initial value of the state.

---

## Example

```jsx
import { useState } from "react";

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <h2>{count}</h2>

      <button onClick={() => setCount(count + 1)}>
        Increment
      </button>
    </div>
  );
}
```

---

## How useState Works

1. React creates a state variable with the initial value.
2. The component renders.
3. When `setState` is called, React updates the state.
4. React re-renders the component.
5. The UI shows the updated value.

Flow:

User Action → setState() → State Updated → Re-render → UI Updated

---

## Common Use Cases

### Counter

```jsx
const [count, setCount] = useState(0);
```

### Toggle

```jsx
const [isOpen, setIsOpen] = useState(false);
```

### Form Input

```jsx
const [name, setName] = useState("");
```

### Theme Switcher

```jsx
const [darkMode, setDarkMode] = useState(false);
```

---

## Important Points

* State updates are asynchronous because React batches and schedules state changes for better performance instead of updating the state immediately when setState is called.

Batching is a React optimization technique where multiple state updates are grouped together and processed in a single re-render to improve performance.

* Updating state causes a re-render.
* Never update state directly.
* Always use the setter function.
* Each component has its own independent state.

Wrong:

```jsx
count = count + 1;
```

Correct:

```jsx
setCount(count + 1);
```

---


### Why was useState introduced?

Before Hooks, state could only be managed in class components. useState brought state management to functional components.

### Does useState cause re-rendering?

Yes. Whenever the state changes, React re-renders the component.

### Can useState store objects and arrays?

Yes.

```jsx
const [user, setUser] = useState({
  name: "Diya",
  age: 21,
});
```

### What happens when setState is called?

React updates the state and schedules a re-render of the component.

### Difference Between State and Props?

| State                         | Props                       |
| ----------------------------- | --------------------------- |
| Managed inside component      | Passed from parent          |
| Can change                    | Read-only                   |
| Updated using setter function | Cannot be modified by child |

---


## Interview One-Liner

useState is a React Hook that allows functional components to manage local state and trigger re-renders when the state changes.
