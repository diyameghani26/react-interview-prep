1. Explain the React Reconciliation Algorithm.

Answer: The React Reconciliation Algorithm is the process React uses to efficiently update the UI when a component's state or props change. Instead of updating the entire Real DOM, React creates a new Virtual DOM, compares it with the previous Virtual DOM using a process called Diffing, and identifies only the parts that have changed. It then updates only those changed elements in the Real DOM, which improves performance and makes React applications faster and more efficient.


2. What are Controlled vs. Uncontrolled Components?

Answer: In React, Controlled Components are form elements whose values are managed by React State using the useState Hook. Every time the user types, the state is updated, and the UI re-renders, giving React full control over the input. This approach is commonly used for form validation, dynamic forms, and real-time input handling.

On the other hand, Uncontrolled Components are form elements whose values are managed by the DOM itself instead of React State. React accesses the input value using a Ref (useRef), usually when the form is submitted. Uncontrolled components are simpler and may be preferred for basic forms or file inputs where continuous state updates are unnecessary.

3. How does React handle Context and why use it?

Answer: React handles shared data using the Context API, which allows data to be passed directly to any component in the component tree without manually passing props at every level. First, a Context is created using createContext(), then a Provider supplies the data, and any child component can access it using the useContext Hook. Context is mainly used to avoid prop drilling and to manage global data such as user information, themes, language settings, and authentication state.

4. What are the common performance optimization techniques in React?

Answer: React provides several techniques to improve application performance by reducing unnecessary rendering and computations. Common optimization techniques include using 
**React.memo** to prevent unnecessary component re-renders,**useMemo** to memoize expensive calculated values, and **useCallback** to memoize functions passed to child components. 
Other techniques include lazy loading and code splitting to load components only when needed, using proper keys while rendering lists, avoiding unnecessary state updates, and optimizing large lists with virtualization. These techniques help make React applications faster and more efficient.

5. How does memoization work in React (React.memo, useMemo)?

Answer: Memoization is an optimization technique used to avoid unnecessary computations and re-renders by storing previously computed results. In React, React.memo memoizes a component and prevents it from re-rendering if its props haven't changed. useMemo memoizes the result of an expensive calculation and recomputes it only when its dependencies change. Using memoization can improve performance, especially in large applications, but it should be used only when needed because unnecessary memoization can add complexity.

6. How does React handle batching of state updates?

Answer: React improves performance by batching multiple state updates into a single re-render. Instead of re-rendering the component after every setState call, React groups multiple state updates together and updates the UI only once. This reduces unnecessary renders and makes the application faster. In modern React (React 18+), automatic batching works for event handlers, promises, setTimeout, and other asynchronous operations as well.