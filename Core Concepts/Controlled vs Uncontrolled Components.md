# Controlled vs Uncontrolled Components

## Definition

A **Controlled Component** is a component whose form data is controlled by React using **State**.

An **Uncontrolled Component** is a component whose form data is managed by the **DOM itself** using **Refs**.

---

## Why use Controlled Components?

* To have full control over form data.
* To validate user input.
* To update the UI instantly.
* To keep form values in React State.
* To easily handle form submissions.

---

## Why use Uncontrolled Components?

* For simple forms.
* When React doesn't need to manage every input change.
* To improve performance in large forms.
* When working with third-party libraries.
* To directly access DOM values.

---

## When to Use Controlled Components?

Use Controlled Components when:

* Form validation is required.
* Input values need to update the UI.
* Data needs to be stored in React State.
* Building dynamic forms.
* You need predictable data flow.

---

## When to Use Uncontrolled Components?

Use Uncontrolled Components when:

* The form is simple.
* Validation is not required.
* You only need the value on form submission.
* You want less React state management.

---

## Controlled Component Syntax

```jsx
const [name, setName] = useState("");
```

```jsx
<input
  type="text"
  value={name}
  onChange={(e) => setName(e.target.value)}
/>
```

---

## Uncontrolled Component Syntax

```jsx
const inputRef = useRef();
```

```jsx
<input
  type="text"
  ref={inputRef}
/>
```

---

## Example 1: Controlled Component

```jsx
import { useState } from "react";

function App() {
  const [name, setName] = useState("");

  return (
    <>
      <input
        type="text"
        value={name}
        onChange={(e) =>
          setName(e.target.value)
        }
      />

      <h2>{name}</h2>
    </>
  );
}
```

Whenever the user types:

* State updates.
* Component re-renders.
* UI updates instantly.

---

## Example 2: Uncontrolled Component

```jsx
import { useRef } from "react";

function App() {
  const inputRef = useRef();

  const handleSubmit = () => {
    alert(inputRef.current.value);
  };

  return (
    <>
      <input
        type="text"
        ref={inputRef}
      />

      <button onClick={handleSubmit}>
        Submit
      </button>
    </>
  );
}
```

Here, React does not store the input value.

The value is accessed directly from the DOM.

---

## How Controlled Components Work

1. User types into the input.
2. `onChange` event fires.
3. State updates.
4. Component re-renders.
5. Updated value appears in the UI.

Flow:

User Input → onChange → State Update → Re-render → Updated UI

---

## How Uncontrolled Components Work

1. User types into the input.
2. Browser stores the value.
3. React does not re-render.
4. Value is accessed using `ref.current.value`.

Flow:

User Input → DOM Stores Value → useRef → Access Value

---

## Controlled vs Uncontrolled Components

| Controlled Component       | Uncontrolled Component    |
| -------------------------- | ------------------------- |
| Uses `useState`            | Uses `useRef`             |
| React controls input       | DOM controls input        |
| Re-renders on every change | No re-render while typing |
| Easier validation          | Limited validation        |
| Best for dynamic forms     | Best for simple forms     |

---

## Advantages of Controlled Components

* Easy validation.
* Predictable data flow.
* Better debugging.
* Real-time UI updates.
* Easy to manage form data.

---

## Advantages of Uncontrolled Components

* Less code.
* Better performance for simple forms.
* Fewer re-renders.
* Easy to integrate with non-React libraries.

---

## Common Use Cases

### Controlled Login Form

```jsx
const [email, setEmail] = useState("");
```

### Controlled Search Bar

```jsx
const [search, setSearch] = useState("");
```

### Uncontrolled File Input

```jsx
const fileRef = useRef();
```

### Simple Contact Form

```jsx
const nameRef = useRef();
```

---

## Important Points

* Controlled Components use **State**.
* Uncontrolled Components use **Refs**.
* Controlled Components re-render on every input change.
* Uncontrolled Components do not re-render while typing.
* Controlled Components are preferred in most React applications.
* File inputs are usually uncontrolled.

---

## Common Misconceptions

### Are Controlled Components always better?

No.

They are preferred for most applications, but Uncontrolled Components are useful for simple forms and file inputs.

### Can Uncontrolled Components use State?

No.

They mainly rely on the DOM and `useRef`.

### Which is more common in React projects?

Controlled Components are more commonly used because they provide better control over form data.

---

## Interview Questions

### What is a Controlled Component?

A Controlled Component is a form element whose value is controlled by React State.

### What is an Uncontrolled Component?

An Uncontrolled Component is a form element whose value is managed by the DOM and accessed using `useRef`.

### What is the main difference between Controlled and Uncontrolled Components?

Controlled Components use React State, while Uncontrolled Components use the DOM with Refs.

### Which is better: Controlled or Uncontrolled Components?

Controlled Components are generally preferred because they provide better control, validation, and predictable data flow.

### Why are file inputs usually uncontrolled?

Because browsers manage file input values, and React cannot directly control them.

### Can we use useRef in Controlled Components?

Yes, but `useRef` is generally used for DOM access, while `useState` manages input values.

---

## One-Line Interview Answer

Controlled Components use React State to manage form data, while Uncontrolled Components rely on the DOM and `useRef` to manage form values.
