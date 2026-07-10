createRoot()

Definition

createRoot() is a React API introduced in React 18 that is used to create a root for rendering a React application.

It replaces the older ReactDOM.render() method and enables modern React features like Concurrent Rendering.

Why use createRoot()?
To render a React application.
To use React 18 features.
To improve rendering performance.
To replace the deprecated ReactDOM.render() method.
When to Use createRoot()?

Use createRoot():

When starting a React application.
In the application's entry file (main.jsx or index.js).
When using React 18 or later.
Syntax
import { createRoot } from "react-dom/client";

const root = createRoot(document.getElementById("root"));

root.render(<App />);
Parameters
document.getElementById("root") → The DOM element where the React app will be mounted.
Example
import { createRoot } from "react-dom/client";
import App from "./App";

const root = createRoot(
  document.getElementById("root")
);

root.render(<App />);
How createRoot() Works
React finds the root DOM element.
It creates a React Root.
The App component is rendered inside that root.
React manages all future UI updates.

Flow:

HTML Root Element
        ↓
createRoot()
        ↓
React Root Created
        ↓
root.render(<App />)
        ↓
UI Rendered
createRoot() vs ReactDOM.render()
createRoot()	ReactDOM.render()
Introduced in React 18	Used before React 18
Supports Concurrent Rendering	Does not support Concurrent Rendering
Recommended	Deprecated
Uses root.render()	Uses ReactDOM.render()
Advantages
Supports React 18 features.
Better rendering performance.
Enables Concurrent Rendering.
Future-proof API.
Important Points
Introduced in React 18.
Replaces ReactDOM.render().
Used only once in the application's entry file.
Creates the root of the React application.
Required for using React 18 features.
Common Interview Mistakes

❌ createRoot() is used inside every component.

✅ Wrong.

It is used only once, usually in main.jsx or index.js.

❌ ReactDOM.render() is still recommended.

✅ Wrong.

ReactDOM.render() is deprecated in React 18. Use createRoot() instead.

Interview Questions
What is createRoot()?

createRoot() is a React 18 API used to create the root of a React application and render components into the DOM.

Why was createRoot() introduced?

It was introduced to replace ReactDOM.render() and support modern React features like Concurrent Rendering.

Where is createRoot() used?

It is used in the application's entry file (main.jsx or index.js).

Can createRoot() be called multiple times?

Generally, it is called once for the main application root.