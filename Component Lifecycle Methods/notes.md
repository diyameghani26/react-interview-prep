# Component Lifecycle Methods

## Definition

The **Component Lifecycle** refers to the different stages a React component goes through from the time it is created until it is removed from the DOM. In Class Components, these stages are managed using **Lifecycle Methods**.

---

## Lifecycle Phases

1. Mounting
2. Updating
3. Unmounting

---

# 1. Mounting Phase

The Mounting phase occurs when a component is created and inserted into the DOM.

### Lifecycle Methods

### constructor()

- Called first when the component is created.
- Used to initialize state and bind methods.

```jsx
constructor(props) {
  super(props);
  this.state = {
    count: 0,
  };
}
```

---

### static getDerivedStateFromProps()

- Called before every render.
- Used to update state based on props.
- Rarely used.

---

### render()

- Returns the JSX.
- Required in every Class Component.

```jsx
render() {
  return <h1>Hello React</h1>;
}
```

---

### componentDidMount()

- Called after the component is added to the DOM.
- Used for:
  - API Calls
  - Event Listeners
  - Timers
  - Fetching Data

```jsx
componentDidMount() {
  console.log("Component Mounted");
}
```

---

# 2. Updating Phase

The Updating phase occurs whenever the component's state or props change.

### Lifecycle Methods

### static getDerivedStateFromProps()

Called before every update.

---

### shouldComponentUpdate()

- Decides whether the component should re-render.
- Returns `true` or `false`.
- Used for performance optimization.

```jsx
shouldComponentUpdate() {
  return true;
}
```

---

### render()

Re-renders the updated UI.

---

### getSnapshotBeforeUpdate()

Captures information from the DOM before it is updated.

Rarely used.

---

### componentDidUpdate()

Called after the component updates.

Used for:

- API calls after updates
- Comparing previous and current props/state
- Side effects

```jsx
componentDidUpdate(prevProps, prevState) {
  console.log("Updated");
}
```

---

# 3. Unmounting Phase

The Unmounting phase occurs when the component is removed from the DOM.

### Lifecycle Method

### componentWillUnmount()

Used to clean up resources like:

- Timers
- Event Listeners
- API Subscriptions

```jsx
componentWillUnmount() {
  console.log("Component Removed");
}
```

---

## Lifecycle Flow

```
Mounting
│
├── constructor()
├── getDerivedStateFromProps()
├── render()
└── componentDidMount()

↓

Updating
│
├── getDerivedStateFromProps()
├── shouldComponentUpdate()
├── render()
├── getSnapshotBeforeUpdate()
└── componentDidUpdate()

↓

Unmounting
│
└── componentWillUnmount()
```

---

## Lifecycle Methods vs Functional Components

| Class Component | Functional Component |
|-----------------|----------------------|
| componentDidMount() | useEffect(() => {}, []) |
| componentDidUpdate() | useEffect(() => {}, [dependency]) |
| componentWillUnmount() | Cleanup function inside useEffect |

Example:

```jsx
useEffect(() => {
  console.log("Mounted");

  return () => {
    console.log("Unmounted");
  };
}, []);
```

---

## Important Points

- Lifecycle methods are used only in Class Components.
- Functional Components use the `useEffect` Hook instead.
- There are three lifecycle phases:
  - Mounting
  - Updating
  - Unmounting
- `componentDidMount()` is commonly used for API calls.
- `componentWillUnmount()` is used for cleanup.

---

## Common Interview Questions

### What are the three phases of the React Component Lifecycle?

Mounting, Updating, and Unmounting.

### Which lifecycle method is used for API calls?

`componentDidMount()`.

### Which lifecycle method is used for cleanup?

`componentWillUnmount()`.

### Which Hook replaces lifecycle methods in Functional Components?

`useEffect`.

### Are lifecycle methods used in Functional Components?

No. Functional Components use Hooks like `useEffect`.

---

## One-Line Interview Answer

Component Lifecycle Methods are special methods in Class Components that run during the Mounting, Updating, and Unmounting phases of a component's life.

Note: Lifecycle methods are used in Class Components. In modern React, Functional Components use Hooks like useEffect to handle lifecycle behavior. This is a nice touch and shows interviewers you know both old and modern React.