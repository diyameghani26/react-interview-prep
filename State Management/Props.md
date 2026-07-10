# Props

## Definition

Props (short for **Properties**) are read-only values passed from a parent component to a child component. They allow components to share data and make components reusable.

---

## Why use Props?

- To pass data from parent to child.
- To make components reusable.
- To customize component behavior.
- To share information between components.

---

## When to Use Props?

Use Props when:

- A parent component needs to send data to a child component.
- You want to reuse the same component with different data.
- You need to pass functions or event handlers to child components.

Examples:

- User Details
- Product Cards
- Profile Cards
- Buttons
- Blog Posts

---

## Syntax

### Parent Component

```jsx
<Profile name="Diya" age={20} />
```

### Child Component

```jsx
function Profile(props) {
  return (
    <>
      <h2>{props.name}</h2>
      <p>{props.age}</p>
    </>
  );
}
```

---

## Example

```jsx
function Student(props) {
  return <h2>Hello, {props.name}</h2>;
}

function App() {
  return <Student name="Diya" />;
}
```

Output:

```
Hello, Diya
```

---

## How Props Work

1. Parent component passes data.
2. Child component receives the data.
3. Child component displays or uses the data.
4. If the parent sends new props, the child re-renders.

Flow:

```
Parent Component
        ↓
      Props
        ↓
Child Component
        ↓
Display Data
```

---

## Characteristics of Props

- Props are read-only.
- Passed from parent to child.
- Make components reusable.
- Can store any JavaScript value.
- Updating props causes the child component to re-render.

---

## Advantages

- Makes components reusable.
- Improves code organization.
- Enables parent-child communication.
- Makes UI dynamic.

---

## Important Points

- Props are immutable.
- They are passed from parent to child.
- Child components cannot modify props.
- Props can contain strings, numbers, arrays, objects, functions, and JSX.

---

## Common Interview Mistakes

❌ **Props can be modified inside the child component.**

✅ Wrong.

Props are read-only and cannot be modified by the child component.

---

❌ **Props and State are the same.**

✅ Wrong.

Props are passed by the parent, while State is managed within the component.

---

## Interview Questions

### What are Props in React?

Props are read-only values passed from a parent component to a child component.

### Why do we use Props?

To pass data between components and make components reusable.

### Can a child component modify Props?

No. Props are read-only.

### Can Props store functions?

Yes. Functions can be passed as props.

### Do Props trigger re-rendering?

Yes. If the parent passes new props, the child component re-renders.

---

## One-Line Interview Answer

Props are read-only values passed from a parent component to a child component, allowing data sharing and component reusability.