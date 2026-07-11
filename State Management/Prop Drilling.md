# Prop Drilling

## Definition

**Prop Drilling** is the process of passing data from a parent component to a deeply nested child component through multiple intermediate components, even if those intermediate components do not use the data.

---

## Why does Prop Drilling happen?

Prop Drilling happens because React allows data to flow only from **parent to child** using Props. When a deeply nested component needs data, every intermediate component must pass that data down.

---

## When does Prop Drilling become a problem?

It becomes a problem when:

- The component tree is deeply nested.
- Many components pass the same props.
- Intermediate components don't use the props.
- The code becomes difficult to read and maintain.

---

## Example

### Without Prop Drilling

```jsx
<App />
```

### With Prop Drilling

```jsx
function App() {
  const user = "Diya";

  return <Parent user={user} />;
}

function Parent({ user }) {
  return <Child user={user} />;
}

function Child({ user }) {
  return <GrandChild user={user} />;
}

function GrandChild({ user }) {
  return <h2>Hello, {user}</h2>;
}
```

Here, `Parent` and `Child` don't use the `user` prop—they only pass it to `GrandChild`.

---

## How Prop Drilling Works

1. Parent has the data.
2. Parent passes the data to the child.
3. Child passes it to the next child.
4. This continues until the required component receives the data.

Flow:

```
App
 ↓
Parent
 ↓
Child
 ↓
GrandChild
```

---

## Problems with Prop Drilling

- Increases unnecessary prop passing.
- Makes code harder to maintain.
- Reduces readability.
- Becomes difficult in large applications.

---

## How to Avoid Prop Drilling?

Common solutions include:

- Context API
- Redux
- Redux Toolkit
- Zustand

These allow components to access shared data directly without passing props through every level.

---

## Advantages

- Simple for small applications.
- Easy to understand in shallow component trees.

---

## Disadvantages

- Too much prop passing.
- Difficult to maintain.
- Poor scalability.
- Makes components tightly connected.

---

## Important Points

- Prop Drilling is not a React feature.
- It is a common problem in React applications.
- It occurs because data is passed through multiple components using Props.
- Context API and state management libraries help solve it.

---

## Common Interview Mistakes

❌ **Prop Drilling is a React Hook.**

✅ Wrong.

It is a problem that occurs when passing props through multiple component levels.

---

❌ **Prop Drilling is always bad.**

✅ Wrong.

For small applications, it is completely acceptable. It becomes an issue mainly in large or deeply nested applications.

---

## Interview Questions

### What is Prop Drilling?

Prop Drilling is the process of passing props through multiple intermediate components to reach a deeply nested child component.

### Why is Prop Drilling a problem?

Because it increases unnecessary prop passing and makes the code harder to maintain.

### How can you avoid Prop Drilling?

Using Context API, Redux, Redux Toolkit, or Zustand.

### Does every application suffer from Prop Drilling?

No. It mainly becomes a problem in large or deeply nested component trees.

---

## One-Line Interview Answer

Prop Drilling is the process of passing props through multiple intermediate components to a deeply nested child, making the code harder to maintain and often solved using Context API or state management libraries.