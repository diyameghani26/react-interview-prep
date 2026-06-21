# Virtual DOM

## Definition

The Virtual DOM (VDOM) is a lightweight JavaScript representation of the Real DOM.

React uses the Virtual DOM to efficiently update the UI by comparing changes before updating the actual DOM.

---

## Why use Virtual DOM?

* To improve application performance.
* To minimize direct manipulation of the Real DOM.
* To make UI updates faster.
* To reduce unnecessary DOM operations.
* To provide a smoother user experience.

---

## When is Virtual DOM Used?

Virtual DOM is used whenever:

* State changes.
* Props change.
* A component re-renders.
* React needs to update the UI.

---

## What is Real DOM?

The Real DOM is the actual DOM structure rendered by the browser.

Example:

```html
<div>
  <h1>Hello React</h1>
</div>
```

The browser creates and manages this DOM.

---

## What is Virtual DOM?

The Virtual DOM is a JavaScript object that represents the Real DOM.

Example:

```jsx
<div>
  <h1>Hello React</h1>
</div>
```

React converts this into a lightweight JavaScript object internally.

---

## How Virtual DOM Works

1. Component renders.
2. React creates a Virtual DOM tree.
3. State or props change.
4. React creates a new Virtual DOM tree.
5. React compares the old and new Virtual DOM.
6. React identifies the changed parts.
7. Only the necessary updates are applied to the Real DOM.

Flow:

Render → Virtual DOM Created → State Change → New Virtual DOM → Compare → Update Real DOM

---

## Example

Initial UI:

```jsx
<h1>Count: 0</h1>
```

After State Update:

```jsx
<h1>Count: 1</h1>
```

React compares:

```txt
Old Virtual DOM
Count: 0

New Virtual DOM
Count: 1
```

React notices only the text changed and updates only that part of the Real DOM.

---

## Diffing Algorithm

React uses a Diffing Algorithm to compare:

* Old Virtual DOM
* New Virtual DOM

The algorithm finds the differences and updates only the changed elements.

Example:

Before:

```jsx
<h1>Hello</h1>
```

After:

```jsx
<h1>Hello Lumi</h1>
```

React updates only the text instead of re-rendering the entire page.

---

## Reconciliation

The process of comparing the old Virtual DOM with the new Virtual DOM and updating the Real DOM is called Reconciliation.

Flow:

Old Virtual DOM
↓
New Virtual DOM
↓
Diffing
↓
Reconciliation
↓
Update Real DOM

---

## Real DOM vs Virtual DOM

| Real DOM                            | Virtual DOM                      |
| ----------------------------------- | -------------------------------- |
| Actual browser DOM                  | JavaScript representation of DOM |
| Slower updates                      | Faster updates                   |
| Direct manipulation                 | Indirect manipulation            |
| Expensive operations                | Lightweight operations           |
| Updates entire structure more often | Updates only changed parts       |

---

## Advantages of Virtual DOM

### Faster Rendering

React updates only the changed elements.

### Better Performance

Reduces expensive DOM operations.

### Efficient Updates

Uses diffing to identify changes.

### Improved User Experience

Results in smoother UI interactions.

### Cross-Platform Support

Works efficiently with React Native and React DOM.

---

## Important Points

* Virtual DOM is not the actual browser DOM.
* It is a lightweight JavaScript copy of the DOM.
* React compares Virtual DOM trees using diffing.
* React updates only changed elements.
* Virtual DOM improves rendering performance.
* Reconciliation is the process of syncing Virtual DOM with Real DOM.

---

## Common Misconceptions

### Does React update the entire DOM?

No.

React updates only the changed parts of the DOM.

### Is Virtual DOM faster than Real DOM?

Not exactly.

Manipulating the Virtual DOM is faster because it reduces expensive Real DOM operations.

### Is Virtual DOM a browser feature?

No.

It is a React concept implemented in JavaScript.

---

## Interview Questions

### What is Virtual DOM?

Virtual DOM is a lightweight JavaScript representation of the Real DOM used by React to optimize UI updates.

### Why does React use Virtual DOM?

To improve performance by minimizing direct manipulation of the Real DOM.

### What happens when state changes?

React creates a new Virtual DOM, compares it with the previous Virtual DOM, and updates only the changed parts of the Real DOM.

### What is Diffing?

Diffing is the process of comparing the old Virtual DOM and the new Virtual DOM to find changes.

### What is Reconciliation?

Reconciliation is the process of updating the Real DOM based on the differences found during diffing.

### Is Virtual DOM the same as Real DOM?

No. Virtual DOM is a lightweight JavaScript representation, while Real DOM is the actual DOM rendered by the browser.

### Does Virtual DOM improve performance?

Yes. It reduces expensive DOM operations and makes UI updates more efficient.

---

## One-Line Interview Answer

Virtual DOM is a lightweight JavaScript representation of the Real DOM that React uses to efficiently update only the changed parts of the UI.
