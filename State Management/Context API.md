# Context API

## Definition

The **Context API** is a built-in React feature that allows data to be shared across multiple components without passing props manually through every level of the component tree.

It is commonly used to avoid **Prop Drilling**.

---

## Why use Context API?

- To avoid prop drilling.
- To share global data.
- To make code cleaner.
- To reduce unnecessary prop passing.
- To simplify state sharing.

---

## When to Use Context API?

Use Context API when:

- Multiple components need the same data.
- You want to avoid prop drilling.
- Managing global data like:
  - User Authentication
  - Theme (Dark/Light)
  - Language
  - User Profile
  - Application Settings

---

## How Context API Works

Context API has three main parts:

### 1. Create Context

Creates a Context object.

```jsx
import { createContext } from "react";

const UserContext = createContext();
```

---

### 2. Provider

Provides data to all child components.

```jsx
<UserContext.Provider value="Diya">
    <Home />
</UserContext.Provider>
```

---

### 3. Consumer

Consumes the data using `useContext()`.

```jsx
import { useContext } from "react";

const user = useContext(UserContext);
```

---

## Complete Example

### Create Context

```jsx
import { createContext } from "react";

export const UserContext = createContext();
```

---

### Provide Data

```jsx
import { UserContext } from "./UserContext";

function App() {
  return (
    <UserContext.Provider value="Diya">
      <Home />
    </UserContext.Provider>
  );
}
```

---

### Consume Data

```jsx
import { useContext } from "react";
import { UserContext } from "./UserContext";

function Home() {
  const user = useContext(UserContext);

  return <h2>Hello {user}</h2>;
}
```

---

## How Context API Works

1. Create a Context.
2. Wrap components with a Provider.
3. Pass data using the `value` prop.
4. Child components access the data using `useContext()`.

Flow:

```
createContext()
        ↓
Context.Provider
        ↓
value
        ↓
useContext()
        ↓
Access Data
```

---

## Context API vs Prop Drilling

| Context API | Prop Drilling |
|-------------|---------------|
| Shares data globally | Passes props manually |
| Avoids unnecessary prop passing | Requires passing props through multiple components |
| Cleaner code | More boilerplate |
| Better for shared state | Suitable for small component trees |

---

## Common Use Cases

- Authentication
- Theme Switching
- Language Selection
- User Profile
- Global Settings

---

## Advantages

- Eliminates prop drilling.
- Built into React.
- Easy to use.
- Makes code cleaner.
- Great for simple global state.

---

## Limitations

- Not ideal for very large or complex applications.
- Frequent updates may cause unnecessary re-renders.
- Redux or Zustand may be better for complex global state.

---

## Important Points

- Context API is built into React.
- It is mainly used for global state.
- It helps avoid prop drilling.
- It works with `createContext()`, `Provider`, and `useContext()`.
- It is not a complete replacement for Redux in every scenario.

---

## Common Interview Mistakes

❌ **Context API stores state.**

✅ Wrong.

Context API only shares data. The state is usually managed using `useState` or `useReducer` and then provided through Context.

---

❌ **Context API replaces Redux in every application.**

✅ Wrong.

Context API is great for simple global state, while Redux is better for large and complex applications.

---

## Interview Questions

### What is Context API?

Context API is a built-in React feature used to share data across components without prop drilling.

### Why do we use Context API?

To share global data and avoid passing props through multiple component levels.

### What are the three main parts of Context API?

- createContext()
- Provider
- useContext()

### Does Context API manage state?

No. It shares state. The state is usually managed using `useState` or `useReducer`.

### When should you use Context API?

When multiple components need access to the same data, such as authentication, themes, or language settings.

---

## One-Line Interview Answer

Context API is a built-in React feature that allows data to be shared across multiple components without prop drilling by using `createContext()`, `Provider`, and `useContext()`.