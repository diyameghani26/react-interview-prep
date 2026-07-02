1. Explain the React Reconciliation Algorithm.

Answer: The React Reconciliation Algorithm is the process React uses to efficiently update the UI when a component's state or props change. Instead of updating the entire Real DOM, React creates a new Virtual DOM, compares it with the previous Virtual DOM using a process called Diffing, and identifies only the parts that have changed. It then updates only those changed elements in the Real DOM, which improves performance and makes React applications faster and more efficient.


2. What are Controlled vs. Uncontrolled Components?

Answer: In React, Controlled Components are form elements whose values are managed by React State using the useState Hook. Every time the user types, the state is updated, and the UI re-renders, giving React full control over the input. This approach is commonly used for form validation, dynamic forms, and real-time input handling.

On the other hand, Uncontrolled Components are form elements whose values are managed by the DOM itself instead of React State. React accesses the input value using a Ref (useRef), usually when the form is submitted. Uncontrolled components are simpler and may be preferred for basic forms or file inputs where continuous state updates are unnecessary.