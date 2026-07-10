# Props vs State

## Definition

**Props** and **State** are both used to manage data in React, but they serve different purposes. **Props** are used to pass data from a parent component to a child component, while **State** is used to store and manage data within a component.

---

## Why Compare Props and State?

Understanding the difference helps you decide:

- When to pass data using Props.
- When to store data using State.
- How data flows in a React application.

---

## Props vs State

| Props | State |
|-------|-------|
| Passed from parent to child | Managed inside the component |
| Read-only (Immutable) | Can be updated (Mutable) |
| Used to pass data | Used to store and manage data |
| Cannot be modified by the child | Updated using the setter function |
| Makes components reusable | Makes components interactive |

---

## Example

### Using Props

```jsx
function User(props) {
  return <h2>{props.name}</h2>;
}

function App() {
  return <User name="Diya" />;
}
```

---

### Using State

```jsx
import { useState } from "react";

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <>
      <h2>{count}</h2>

      <button onClick={() => setCount(count + 1)}>
        Increment
      </button>
    </>
  );
}
```

---

## How They Work

### Props

```
Parent Component
        ↓
     Pass Props
        ↓
Child Component
        ↓
Uses the Data
```

### State

```
Component
     ↓
Stores State
     ↓
State Updates
     ↓
React Re-renders
```

---

## When to Use Props?

Use Props when:

- Passing data from parent to child.
- Reusing components.
- Passing event handlers.

---

## When to Use State?

Use State when:

- Data changes over time.
- Handling user interactions.
- Managing component-specific data.

---

## Advantages

### Props

- Makes components reusable.
- Enables parent-child communication.
- Keeps data flow predictable.

### State

- Makes components interactive.
- Automatically updates the UI.
- Stores dynamic data.

---

## Important Points

- Props are read-only.
- State can be updated.
- Props are received from the parent.
- State belongs to the component.
- Updating State causes a re-render.
- New Props from the parent also cause a re-render.

---

## Common Interview Mistakes

❌ **Props and State are the same.**

✅ Wrong.

Props are passed by the parent, while State is managed by the component itself.

---

❌ **Props can be modified inside a child component.**

✅ Wrong.

Props are immutable and cannot be modified by the child.

---

## Interview Questions

### What is the difference between Props and State?

Props are read-only values passed from a parent component, while State is managed within the component and can be updated.

### Which one is mutable?

State is mutable, while Props are immutable.

### Which one is used for parent-child communication?

Props.

### Which one triggers a re-render?

Both. Updating State or receiving new Props causes a component to re-render.

### Can a child component modify Props?

No. Props are read-only.

---

## One-Line Interview Answer

Props are read-only values passed from a parent component, while State is mutable data managed within a component that can change over time.