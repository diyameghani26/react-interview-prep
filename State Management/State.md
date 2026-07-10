# State

## Definition

State is a built-in React object that stores data or information about a component. It represents data that can change over time, and whenever the state changes, React automatically updates the UI.

---

## Why use State?

- To store dynamic data.
- To update the UI automatically.
- To make components interactive.
- To handle user actions.
- To manage changing data.

---

## When to Use State?

Use State when:

- Data changes over time.
- User interactions update the UI.
- The component needs to remember values.
- The UI depends on changing data.

Examples:

- Counter
- Toggle Button
- Form Input
- Shopping Cart
- Like Button

---

## Syntax

```jsx
const [state, setState] = useState(initialValue);
```

---

## Parameters

- `state` → Current state value.
- `setState` → Function used to update the state.
- `initialValue` → Initial value of the state.

---

## Example

```jsx
import { useState } from "react";

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <>
      <h1>{count}</h1>

      <button onClick={() => setCount(count + 1)}>
        Increment
      </button>
    </>
  );
}
```

Whenever the button is clicked, the state changes and React automatically updates the UI.

---

## How State Works

1. React creates the state.
2. The component renders using the current state.
3. User performs an action.
4. State is updated using `setState`.
5. React re-renders the component.
6. Updated UI is displayed.

Flow:

```
Create State
      ↓
Render UI
      ↓
User Action
      ↓
Update State
      ↓
React Re-renders
      ↓
Updated UI
```

---

## Characteristics of State

- State is mutable (can change).
- State is local to a component.
- Updating state triggers a re-render.
- State should be updated using the setter function.
- State helps create dynamic user interfaces.

---

## Advantages

- Makes components interactive.
- Automatically updates the UI.
- Stores dynamic data.
- Easy to manage with Hooks.

---

## Important Points

- State stores dynamic data.
- Never update state directly.
- Always use the setter function.
- State changes trigger a re-render.
- Each component has its own state.

---

## Common Interview Mistakes

❌ **State can be changed directly.**

```jsx
count = count + 1;
```

✅ Wrong.

Always update state using the setter function.

```jsx
setCount(count + 1);
```

---

❌ **Changing state does not update the UI.**

✅ Wrong.

Whenever the state changes, React automatically re-renders the component.

---

## Interview Questions

### What is State in React?

State is a built-in React object that stores dynamic data and updates the UI whenever the data changes.

### Why do we use State?

To store and manage data that changes over time.

### How do you update State?

Using the setter function returned by `useState`.

### Does updating State re-render the component?

Yes. React automatically re-renders the component when the state changes.

### Can we update State directly?

No. Always use the setter function like `setState`.

---

## One-Line Interview Answer

State is a built-in React object that stores dynamic data, and whenever it changes, React automatically re-renders the component to update the UI.