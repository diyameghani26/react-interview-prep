# Props

## Definition

Props (short for Properties) are used to pass data from a parent component to a child component.

Props make components reusable and dynamic.

---

## Why use Props?

* To pass data between components.
* To make components reusable.
* To create dynamic UIs.
* To share information from parent to child.
* To customize component behavior.

---

## When to Use Props?

Use Props when:

* A parent component needs to send data to a child component.
* Components need different data.
* You want reusable components.
* You want dynamic content.

---

## Syntax

### Parent Component

```jsx id="p1gxv7"
<Profile name="Lumi" age={21} />
```

### Child Component

```jsx id="n7q4mx"
function Profile(props) {
  return <h1>{props.name}</h1>;
}
```

---

## How Props Work

1. Parent component passes data.
2. Child component receives data through props.
3. Child component uses the received data.
4. UI updates when parent sends new props.

Flow:

Parent Component → Props → Child Component → UI

---

## Example 1: Passing a Single Prop

### Parent Component

```jsx id="j8a4fn"
function App() {
  return <Profile name="Lumi" />;
}
```

### Child Component

```jsx id="7xv5mc"
function Profile(props) {
  return <h1>{props.name}</h1>;
}
```

Output:

```txt id="g7h6vy"
Lumi
```

---

## Example 2: Passing Multiple Props

### Parent Component

```jsx id="f3km8w"
function App() {
  return (
    <Profile
      name="Lumi"
      age={21}
      city="Bhopal"
    />
  );
}
```

### Child Component

```jsx id="s4m4op"
function Profile(props) {
  return (
    <>
      <h1>{props.name}</h1>
      <p>{props.age}</p>
      <p>{props.city}</p>
    </>
  );
}
```

---

## Destructuring Props

Instead of:

```jsx id="m2wztf"
function Profile(props) {
  return <h1>{props.name}</h1>;
}
```

Use:

```jsx id="3x6t9w"
function Profile({ name }) {
  return <h1>{name}</h1>;
}
```

This is cleaner and commonly used.

---

## Passing Objects as Props

```jsx id="o8eq4v"
const user = {
  name: "Lumi",
  age: 21,
};

<Profile user={user} />;
```

```jsx id="7vdvsz"
function Profile({ user }) {
  return <h1>{user.name}</h1>;
}
```

---

## Passing Arrays as Props

```jsx id="sydd1r"
const skills = [
  "React",
  "JavaScript",
  "CSS",
];

<Skills skills={skills} />;
```

---

## Passing Functions as Props

### Parent Component

```jsx id="fnt8r0"
function App() {
  const greet = () => {
    alert("Hello");
  };

  return (
    <Button onClick={greet} />
  );
}
```

### Child Component

```jsx id="mtr66v"
function Button({ onClick }) {
  return (
    <button onClick={onClick}>
      Click
    </button>
  );
}
```

---

## Props are Read-Only

Props cannot be modified by the child component.

Wrong:

```jsx id="svd85d"
props.name = "Diya";
```

Correct:

```jsx id="38zuh5"
return <h1>{props.name}</h1>;
```

Props should be treated as immutable.

---

## Props vs State

| Props                       | State                         |
| --------------------------- | ----------------------------- |
| Passed from parent          | Managed inside component      |
| Read-only                   | Can be updated                |
| Used for communication      | Used for local data           |
| Cannot be modified directly | Updated using setter function |

---

## Parent to Child Communication

Props allow communication from:

```txt id="fvvq6k"
Parent
   ↓
Child
```

Data flows in one direction.

This is called:

### One-Way Data Flow

React follows one-way data flow where data moves from parent to child.

---

## Common Use Cases

### Passing User Data

```jsx id="3u6r3f"
<User name="Lumi" />
```

### Passing Product Information

```jsx id="t3zd7o"
<Product title="Laptop" />
```

### Passing Event Handlers

```jsx id="aj6e8o"
<Button onClick={handleClick} />
```

### Reusable Components

```jsx id="o11txe"
<Card title="React" />
<Card title="JavaScript" />
```

---

## Important Points

* Props stand for Properties.
* Props are used to pass data from parent to child.
* Props are read-only.
* Props help create reusable components.
* React follows one-way data flow.
* Props can contain values, objects, arrays, and functions.

---

## Common Misconceptions

### Can a Child Modify Props?

No.

Props are immutable and should not be modified.

### Are Props and State the Same?

No.

Props are received from parents, while state is managed inside the component.

### Can Functions be Passed as Props?

Yes.

Functions are commonly passed as props for event handling.

---

## Interview Questions

### What are Props in React?

Props are inputs passed from a parent component to a child component.

### Why do we use Props?

To pass data and make components reusable.

### Are Props mutable?

No. Props are read-only and cannot be modified by child components.

### What is One-Way Data Flow?

Data moves from parent components to child components through props.

### Can we pass functions as Props?

Yes. Functions can be passed for handling events and communication.

### What is the difference between Props and State?

Props are passed from parents and are read-only, while state is managed inside the component and can be updated.

### Can Props contain objects and arrays?

Yes. Props can contain any JavaScript value.

---

## One-Line Interview Answer

Props are read-only inputs used to pass data from a parent component to a child component in React.
