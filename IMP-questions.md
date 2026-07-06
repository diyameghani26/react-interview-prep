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

7. What are Custom Hooks and when would you use them?

Answer: Custom Hooks are JavaScript functions that start with use and allow you to reuse stateful logic across multiple React components. They can use other React Hooks like useState, useEffect, and useContext internally. Custom Hooks help keep code clean, reusable, and easier to maintain by avoiding duplicate logic. They are commonly used when the same functionality, such as data fetching, form handling, authentication, or window resizing, is needed in multiple components.

8. How does React implement lazy loading and code splitting?

Answer: React implements lazy loading and code splitting to improve application performance by loading only the code that is needed. Code splitting breaks the application into smaller JavaScript bundles instead of one large bundle. Lazy loading loads these bundles only when a component is required, using React.lazy() and Suspense. This reduces the initial load time, improves performance, and provides a better user experience, especially in large applications.

9. What is useLayoutEffect and how is it different from useEffect?

Answer: useLayoutEffect is a React Hook that runs synchronously after the DOM has been updated but before the browser paints the screen. It is mainly used when you need to measure or modify the DOM before the user sees it, such as calculating element sizes or preventing visual flickering. In contrast, useEffect runs after the browser has painted the updated UI, making it suitable for tasks like API calls, event listeners, and timers. Since useLayoutEffect blocks the browser from painting until it finishes, it should only be used when necessary.

10. How does React support Concurrent Rendering?

Answer: Concurrent Rendering is a feature introduced in React 18 that allows React to prepare multiple versions of the UI and prioritize important updates. Instead of blocking the entire application while rendering, React can pause, resume, or interrupt rendering to handle high-priority tasks first, such as user interactions. This makes applications more responsive and provides a smoother user experience, especially when rendering large or complex components.

11. What is Server-Side Rendering (SSR) in React?

Answer: Server-Side Rendering (SSR) is a rendering technique where React generates the HTML on the server and sends the fully rendered page to the browser. This allows users to see the page content immediately without waiting for JavaScript to load. SSR improves the initial page load time, enhances SEO because search engines can easily crawl the content, and provides a better user experience on slower networks. Frameworks like Next.js use SSR to build fast and SEO-friendly React applications.

12. What is Lifting State Up in React?

Answer: Lifting State Up is the process of moving state from a child component to its closest common parent component so that multiple child components can share and access the same data. Instead of each child maintaining its own separate state, the parent manages the state and passes it down to the children through props. This ensures a single source of truth, keeps data synchronized across components, and makes state management easier.

13. What is Prop Drilling in React and how can you avoid it?

Answer: Prop Drilling is the process of passing data from a parent component to a deeply nested child component through multiple intermediate components, even if those intermediate components don't use the data. This can make the code difficult to read, maintain, and manage. To avoid prop drilling, React provides the Context API, which allows data to be shared directly with any component in the component tree without passing props manually through every level. For larger applications, state management libraries like Redux or Zustand can also be used.

14. What is Suspense in React?

Answer: Suspense is a React component that lets you display a fallback UI, such as a loading spinner or loading message, while waiting for a component or data to load. It is commonly used with React.lazy() for lazy loading components. Instead of showing a blank screen, Suspense displays the fallback content until the requested component is ready, providing a smoother and better user experience.