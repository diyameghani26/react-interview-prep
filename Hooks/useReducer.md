# useReducer Hook

## Definition

`useReducer` is a React Hook used to manage complex state logic in a component.

It updates state by dispatching actions to a reducer function.

---

## Why use useReducer?

* To manage complex state.
* To handle multiple related state values.
* To make state updates predictable.
* To organize state logic in one place.
* To replace multiple useState hooks when state becomes difficult to manage.

---

## When to Use useReducer?

Use `useReducer` when:

* State logic becomes complex.
* Multiple state values depend on each other.
* State updates involve many conditions.
* You have large forms.
* You want Redux-like state management inside a component.

---

## Syntax

```jsx
const [state, dispatch] = useReducer(reducer, initialState);
```

---

## Parameters

* `reducer` → Function that decides how state should change.
* `initialState` → Initial state value.
* `state` → Current state.
* `dispatch` → Function used to send actions to the reducer.

---

## Basic Structure

```jsx
const initialState = { count: 0 };

function reducer(state, action) {
  switch (action.type) {
    case "increment":
      return { count: state.count + 1 };

    case "decrement":
      return { count: state.count - 1 };

    default:
      return state;
  }
}
```

---

## Example 1: Counter

```jsx
import { useReducer } from "react";

const initialState = { count: 0 };

function reducer(state, action) {
  switch (action.type) {
    case "increment":
      return { count: state.count + 1 };

    case "decrement":
      return { count: state.count - 1 };

    default:
      return state;
  }
}

function App() {
  const [state, dispatch] = useReducer(
    reducer,
    initialState
  );

  return (
    <>
      <h1>{state.count}</h1>

      <button
        onClick={() =>
          dispatch({ type: "increment" })
        }
      >
        +
      </button>

      <button
        onClick={() =>
          dispatch({ type: "decrement" })
        }
      >
        -
      </button>
    </>
  );
}
```

---

## How useReducer Works

1. React creates the initial state.
2. User dispatches an action.
3. Action goes to the reducer function.
4. Reducer decides how state should change.
5. New state is returned.
6. Component re-renders with updated state.

Flow:

State → Dispatch Action → Reducer → New State → Re-render

---

## Common Use Cases

### Counter Applications

```jsx
dispatch({ type: "increment" });
```

### Form Management

```jsx
dispatch({
  type: "updateName",
  payload: "Diya",
});
```

### Shopping Cart

```jsx
dispatch({
  type: "addToCart",
  payload: product,
});
```

### Authentication State

```jsx
dispatch({
  type: "login",
  payload: userData,
});
```

---

## Important Points

* useReducer is used for complex state management.
* State updates happen through dispatch actions.
* Reducer functions should be pure functions.
* Similar to Redux concepts.
* Makes state transitions predictable.
* Better than multiple useState hooks for large state logic.

---

## useReducer vs useState

| useReducer                    | useState                       |
| ----------------------------- | ------------------------------ |
| Used for complex state        | Used for simple state          |
| Uses reducer function         | Uses setter function           |
| Updates through dispatch      | Updates through setState       |
| Better for large applications | Better for small state changes |

---

## Reducer Function Rules

A reducer should:

✅ Return a new state

✅ Be a pure function

✅ Not modify existing state directly

Wrong:

```jsx
state.count++;
return state;
```

Correct:

```jsx
return {
  count: state.count + 1,
};
```

---

## Interview Questions

### What is useReducer?

useReducer is a React Hook used to manage complex state using a reducer function and dispatched actions.

### When should you use useReducer?

When state logic becomes complex or when multiple state values need to be managed together.

### What is a reducer?

A reducer is a function that receives the current state and an action and returns a new state.

### What is dispatch?

Dispatch is a function used to send actions to the reducer.

### How is useReducer different from useState?

useState is suitable for simple state, while useReducer is better for complex state logic.

### Is useReducer similar to Redux?

Yes. It follows the same reducer and action pattern as Redux.

### Does useReducer cause re-renders?

Yes. When state changes, React re-renders the component.

---

## One-Line Interview Answer

useReducer is a React Hook that manages complex state by using a reducer function and dispatching actions to update the state.
