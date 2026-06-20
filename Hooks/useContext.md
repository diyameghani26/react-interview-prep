# useContext Hook

## Definition

`useContext` is a React Hook that allows components to access shared data without passing props manually through every level of the component tree.

It is commonly used to avoid prop drilling.

---

## Why use useContext?

* To share data between components.
* To avoid prop drilling.
* To manage global data.
* To make state accessible throughout the application.
* To simplify component communication.

---

## When to Use useContext?

Use `useContext` when:

* Multiple components need the same data.
* You want to avoid passing props through many levels.
* You need global state like theme, user, or language settings.
* Data needs to be shared across different parts of the application.

---

## Syntax

```jsx
const value = useContext(Context);
```

---

## Parameters

* `Context` → The context object created using `createContext()`.
* `value` → The data provided by the Context Provider.

---

## Creating Context

```jsx
import { createContext } from "react";

const UserContext = createContext();
```

---

## Providing Context

```jsx
<UserContext.Provider value="Diya">
  <App />
</UserContext.Provider>
```

---

## Consuming Context

```jsx
import { useContext } from "react";

function Profile() {
  const user = useContext(UserContext);

  return <h1>{user}</h1>;
}
```

---

## Complete Example

```jsx
import {
  createContext,
  useContext,
} from "react";

const UserContext = createContext();

function Profile() {
  const user = useContext(UserContext);

  return <h1>{user}</h1>;
}

function App() {
  return (
    <UserContext.Provider value="Diya">
      <Profile />
    </UserContext.Provider>
  );
}
```

---

## How useContext Works

1. Create a Context.
2. Wrap components with a Provider.
3. Pass data through the Provider.
4. Access data using useContext.
5. Components receive the shared value.

Flow:

Create Context → Provider → Value → useContext → Access Data

---

## Common Use Cases

### Theme Management

```jsx
const theme = useContext(ThemeContext);
```

### Authentication

```jsx
const user = useContext(AuthContext);
```

### Language Switching

```jsx
const language = useContext(LanguageContext);
```

### Global Settings

```jsx
const settings = useContext(SettingsContext);
```

---

## Important Points

* useContext helps share data globally.
* It eliminates prop drilling.
* Components automatically receive updated values.
* Works together with Context API.
* Suitable for small to medium global state.

---

## Prop Drilling Problem

Without Context:

```txt
App
 ↓
Parent
 ↓
Child
 ↓
GrandChild
```

Props must be passed through every component.

With Context:

```txt
Provider
 ↓
Any Component
```

Data can be accessed directly.

---

## useContext vs Props

| useContext            | Props                            |
| --------------------- | -------------------------------- |
| Shares data globally  | Passes data parent to child      |
| Avoids prop drilling  | Can cause prop drilling          |
| Used for shared state | Used for component communication |

---

## useContext vs Redux

| useContext            | Redux              |
| --------------------- | ------------------ |
| Built into React      | External library   |
| Small to medium state | Large applications |
| Easy setup            | More configuration |
| Simpler API           | Advanced features  |

---

## Interview Questions

### What is useContext?

useContext is a React Hook used to access shared data from a Context without passing props manually.

### What problem does useContext solve?

It solves prop drilling.

### What is prop drilling?

Passing props through multiple levels of components just to reach a deeply nested component.

### Does useContext replace Redux?

Not completely. useContext is suitable for small to medium state management, while Redux is better for large applications.

### Can useContext trigger re-renders?

Yes. Components using the context re-render when the context value changes.

### When should you use useContext?

When multiple components need access to the same shared data.

---

