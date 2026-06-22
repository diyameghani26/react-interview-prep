# JSX (JavaScript XML)

## Definition

JSX (JavaScript XML) is a syntax extension for JavaScript that allows developers to write HTML-like code inside JavaScript.

It makes React code easier to read and write.

---

## Why use JSX?

* Makes UI code more readable.
* Allows writing HTML-like syntax in JavaScript.
* Improves developer experience.
* Makes component creation easier.
* Helps React describe UI structure.

---

## When to Use JSX?

Use JSX when:

* Creating React components.
* Designing user interfaces.
* Rendering dynamic content.
* Building reusable UI elements.

---

## Syntax

```jsx
const element = <h1>Hello React</h1>;
```

---

## JSX Example

```jsx
function App() {
  return (
    <h1>Hello React</h1>
  );
}
```

---

## JSX vs JavaScript

Without JSX:

```jsx
const element = React.createElement(
  "h1",
  null,
  "Hello React"
);
```

With JSX:

```jsx
const element = <h1>Hello React</h1>;
```

JSX is easier to read and write.

---

## How JSX Works

React does not understand JSX directly.

Before execution, Babel converts JSX into regular JavaScript.

JSX:

```jsx
<h1>Hello React</h1>
```

Converted by Babel:

```jsx
React.createElement(
  "h1",
  null,
  "Hello React"
);
```

Flow:

JSX → Babel → React.createElement() → Virtual DOM → Real DOM

---

## Embedding JavaScript in JSX

Use curly braces `{}` to write JavaScript inside JSX.

Example:

```jsx
const name = "Lumi";

function App() {
  return <h1>Hello {name}</h1>;
}
```

Output:

```txt
Hello Lumi
```

---

## JSX Expressions

Valid:

```jsx
<h1>{2 + 2}</h1>
```

```jsx
<h1>{user.name}</h1>
```

```jsx
<h1>{isLoggedIn ? "Welcome" : "Login"}</h1>
```

---

## JSX Attributes

Similar to HTML attributes.

Example:

```jsx
<img src="image.jpg" alt="Image" />
```

---

## className instead of class

HTML:

```html
<div class="container"></div>
```

JSX:

```jsx
<div className="container"></div>
```

React uses `className` because `class` is a reserved JavaScript keyword.

---

## Self-Closing Tags

JSX requires self-closing tags.

Correct:

```jsx
<img src="image.jpg" />
```

```jsx
<input />
```

Wrong:

```jsx
<img src="image.jpg">
```

---

## Returning Multiple Elements

JSX must return a single parent element.

Wrong:

```jsx
return (
  <h1>Hello</h1>
  <p>React</p>
);
```

Correct:

```jsx
return (
  <div>
    <h1>Hello</h1>
    <p>React</p>
  </div>
);
```

Or:

```jsx
return (
  <>
    <h1>Hello</h1>
    <p>React</p>
  </>
);
```

---

## React Fragments

Fragments allow grouping elements without adding extra DOM nodes.

Example:

```jsx
<>
  <h1>Hello</h1>
  <p>React</p>
</>
```

---

## Common Use Cases

### Rendering Text

```jsx
<h1>Hello World</h1>
```

### Rendering Variables

```jsx
<h1>{name}</h1>
```

### Conditional Rendering

```jsx
<h1>
  {isLoggedIn
    ? "Welcome"
    : "Login"}
</h1>
```

### Rendering Lists

```jsx
{
  users.map(user => (
    <li key={user.id}>
      {user.name}
    </li>
  ))
}
```

---

## Important Points

* JSX is not HTML.
* JSX is a syntax extension for JavaScript.
* Babel converts JSX into JavaScript.
* JavaScript expressions use curly braces `{}`.
* JSX must return a single parent element.
* JSX improves readability and maintainability.

---

## JSX vs HTML

 JSX                       | HTML                           
 ------------------------- | ------------------------------ 
 Uses className            | Uses class                     
 Uses camelCase attributes | Uses lowercase attributes      
 Written inside JavaScript | Written in HTML files          
 Converted by Babel        | Directly understood by browser 

---

## Common Misconceptions

### Is JSX HTML?

No.

JSX looks like HTML but is actually JavaScript syntax.

### Can browsers understand JSX?

No.

Babel converts JSX into JavaScript before execution.

### Is JSX required in React?

No.

React can be written using `React.createElement()`, but JSX makes development easier.

---

## Interview Questions

### What is JSX?

JSX is a syntax extension for JavaScript that allows developers to write HTML-like code inside React.

### Is JSX HTML?

No. JSX looks like HTML but is converted into JavaScript.

### Why do we use JSX?

To make React code more readable and easier to write.

### What is Babel?

Babel is a JavaScript compiler that converts JSX into regular JavaScript.

### Why do we use className instead of class?

Because `class` is a reserved keyword in JavaScript.

### Can we write JavaScript inside JSX?

Yes. JavaScript expressions can be written inside curly braces `{}`.

### Why must JSX return a single parent element?

Because JSX expressions must return a single JavaScript object.

---

## One-Line Interview Answer

JSX is a JavaScript syntax extension that allows developers to write HTML-like code in React, which is later converted into JavaScript by Babel.
