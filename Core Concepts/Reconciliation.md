# Reconciliation

## Definition

Reconciliation is the process React uses to compare the old Virtual DOM with the new Virtual DOM and update only the changed parts of the Real DOM.

It helps React efficiently update the UI without re-rendering the entire page.

---

## Why use Reconciliation?

* To improve performance.
* To reduce unnecessary DOM updates.
* To make UI updates efficient.
* To minimize expensive Real DOM operations.
* To provide a faster user experience.

---

## When is Reconciliation Used?

Reconciliation happens whenever:

* State changes.
* Props change.
* A component re-renders.
* React needs to update the UI.

---

## How Reconciliation Works

1. Component renders.
2. React creates a Virtual DOM tree.
3. State or props change.
4. React creates a new Virtual DOM tree.
5. React compares the old and new Virtual DOM trees.
6. React finds the differences.
7. React updates only the changed parts of the Real DOM.

Flow:

Old Virtual DOM → New Virtual DOM → Diffing → Reconciliation → Update Real DOM

---

## Example

Initial UI:

```jsx
<h1>Hello</h1>
```

Updated UI:

```jsx
<h1>Hello Lumi</h1>
```

React compares:

```txt
Old Virtual DOM
<h1>Hello</h1>

New Virtual DOM
<h1>Hello Lumi</h1>
```

React updates only the text node instead of rebuilding the entire DOM.

---

## What is Diffing?

Diffing is the process of comparing:

* Old Virtual DOM
* New Virtual DOM

React uses a Diffing Algorithm to identify changes between them.

Reconciliation uses the results of Diffing to update the Real DOM.

---

## Reconciliation Rules

### Rule 1: Different Element Types

Before:

```jsx
<h1>Hello</h1>
```

After:

```jsx
<p>Hello</p>
```

React removes the old element and creates a new one.

---

### Rule 2: Same Element Type

Before:

```jsx
<h1 className="title">
  Hello
</h1>
```

After:

```jsx
<h1 className="heading">
  Hello
</h1>
```

React updates only the changed attribute.

---

### Rule 3: Updating Children

Before:

```jsx
<ul>
  <li>A</li>
  <li>B</li>
</ul>
```

After:

```jsx
<ul>
  <li>A</li>
  <li>B</li>
  <li>C</li>
</ul>
```

React adds only the new child element.

---

## Role of Keys in Reconciliation

Keys help React identify list items efficiently.

Example:

```jsx
{
  users.map(user => (
    <li key={user.id}>
      {user.name}
    </li>
  ))
}
```

Without keys, React may perform unnecessary updates.

With keys, React can track elements correctly.

---

## Why Keys are Important?

* Improve performance.
* Help React identify elements.
* Reduce unnecessary re-renders.
* Make list updates efficient.

---

## Reconciliation vs Diffing

| Reconciliation                  | Diffing                        |
| ------------------------------- | ------------------------------ |
| Complete process of updating UI | Process of finding differences |
| Uses diffing internally         | Compares Virtual DOM trees     |
| Updates Real DOM                | Finds changes                  |
| Higher-level concept            | Part of reconciliation         |

---

## Virtual DOM vs Reconciliation

| Virtual DOM                      | Reconciliation          |
| -------------------------------- | ----------------------- |
| JavaScript representation of DOM | Process of updating DOM |
| Stores UI structure              | Updates UI efficiently  |
| Used for comparison              | Uses comparison results |
| Lightweight copy of DOM          | Update mechanism        |

---

## Advantages of Reconciliation

### Faster Updates

Only changed elements are updated.

### Better Performance

Reduces expensive DOM operations.

### Efficient Rendering

Avoids unnecessary updates.

### Improved User Experience

Creates smoother interactions.

---

## Important Points

* Reconciliation compares old and new Virtual DOM trees.
* React uses a Diffing Algorithm during reconciliation.
* Only changed elements are updated.
* Keys improve reconciliation performance.
* Reconciliation helps React update the UI efficiently.

---

## Common Misconceptions

### Does React re-render the entire DOM?

No.

React updates only the parts that changed.

### Is Reconciliation the same as Virtual DOM?

No.

Virtual DOM is a data structure, while Reconciliation is the process of updating the UI.

### Are Keys only used to remove warnings?

No.

Keys help React optimize reconciliation and improve performance.

---

## Interview Questions

### What is Reconciliation?

Reconciliation is the process React uses to compare Virtual DOM trees and update only the changed parts of the Real DOM.

### What is the purpose of Reconciliation?

To efficiently update the UI while minimizing DOM operations.

### What is Diffing?

Diffing is the process of comparing old and new Virtual DOM trees to find changes.

### Why are Keys important in Reconciliation?

Keys help React identify list items and perform efficient updates.

### Does Reconciliation improve performance?

Yes. It reduces unnecessary DOM updates and improves rendering efficiency.

### What happens when state changes?

React creates a new Virtual DOM, compares it with the previous Virtual DOM, and updates only the changed parts of the Real DOM.

### What is the relationship between Diffing and Reconciliation?

Diffing finds the changes, and Reconciliation uses those changes to update the Real DOM.

---

## One-Line Interview Answer

Reconciliation is the process React uses to compare old and new Virtual DOM trees and efficiently update only the changed parts of the Real DOM.

