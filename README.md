## Top interview topics 

🟢 STRONG TOPICS

JavaScript

Q: Difference between var, let, and const?
A: var is function-scoped and can be redeclared, which often leads to bugs. let and const are block-scoped — let allows reassignment while const doesn't allow the value to be changed after declaration. I default to const wherever possible and use let only when the value needs to change, which is modern JavaScript best practice.

Q: What is a closure?
A: A closure is when a function remembers variables from its outer scope even after that outer function has finished executing. we use this pattern often, like in custom hooks where we need to preserve state between renders.

Q: Difference between == and ===?
A: == checks value only and does type coercion, while === checks both value and type. I always use === to avoid unexpected bugs from type conversion.

Q: What are map, filter, and reduce?
A: map transforms each element and returns a new array, filter returns elements matching a condition, and reduce accumulates array values into a single result. 

Q: What is the difference between Promises and async/await?
A: "Promises represent an eventual completion of an async operation using .then() and .catch(). async/await is syntactic sugar over Promises that makes asynchronous code look synchronous and easier to read.


HTML5

Q: What are semantic elements? Give examples.
A: "Semantic elements clearly describe their meaning to the browser and screen readers — like header, nav, main, section, article, and footer — instead of using generic divs everywhere. this makes  better accessibility and SEO."

Q: Difference between div and section?
A: div is a generic container with no semantic meaning, while section represents a thematically grouped piece of content. 

Q: What's the purpose of the alt attribute?
A: It provides alternate text for images — important for accessibility (screen readers) and SEO, and it shows if the image fails to load.


Tailwind CSS

Q: What is Tailwind CSS and how is it different from traditional CSS?
A: "Tailwind is a utility-first CSS framework where you style elements directly in HTML/JSX using predefined classes like flex, p-4, text-center — instead of writing separate CSS files. It speeds up development a lot.

Q: How do you handle responsiveness in Tailwind?
A: Using breakpoint prefixes like sm:, md:, lg: 

Q: What is JIT mode in Tailwind?
A: "Just-In-Time mode generates styles on-demand as you write classes, instead of generating the entire stylesheet upfront — making builds faster and CSS files smaller."


REST API

Q: What is a REST API?
A: REST API is an architectural style for building web services that uses standard HTTP methods — GET, POST, PUT, DELETE — to perform operations on resources, usually exchanging data in JSON format"


Q: Difference between GET and POST?
A: GET retrieves data and doesn't change anything on the server parameters are visible in the URL. POST sends data to the server to create or update a resource, and the data is sent in the request body.


Redux

Q: What is Redux and why is it used?
A: "Redux is a state management library that stores your entire app's state in a single centralized store, making it predictable and easier to debug across components that don't share a direct parent-child relationship."

Q: Redux vs Context API — when would you use which?
A: "Context API is good for simple, low-frequency state like theme or auth status. Redux is better for complex, frequently-updated state shared across many components — like a shopping cart. 

Q: What is Redux Toolkit?
A: It's the official, simplified way to write Redux logic — it reduces boilerplate using createSlice and configureStore.


🟡 LEARNING TOPICS (be honest, show direction — don't bluff)

Next.js0

Q: What is Next.js and why use it over React?
A: In plain React, the browser downloads a blank HTML page and JavaScript builds the content on the client side — that's CSR. Next.js supports SSR, where the HTML is fully rendered on the server before being sent to the browser, so the user sees content immediately and search engines can crawl it properly. This improves both performance and SEO compared to plain client-side rendered React.

Q: What is SSR vs SSG?
A: "SSR renders the page on the server for every request, which is useful for frequently changing data. SSG pre-renders pages at build time, which is faster and great for content that doesn't change often, like blogs. "

Q: What is file-based routing?
A: "In Next.js, the file structure inside the app or pages folder automatically becomes your routes — so you don't need to manually configure a router like in React Router."


TypeScript

Q: What is TypeScript?
A: TypeScript is a superset of JavaScript — meaning all valid JavaScript is valid TypeScript too — but it adds static typing. This lets me define the expected type of a variable, like let age: number, and the editor catches type mismatches immediately while I'm writing code, instead of the error only showing up later when the app runs. It makes the code more predictable, especially in larger projects.

Q: What's the difference between type and interface?
A: "Both define the shape of an object, but interfaces can be extended and merged, while types are more flexible for unions and primitives. This is an area I'm still building practical experience in."


Node.js

Q: What is Node.js?
A: "Node.js is a JavaScript runtime built on Chrome's V8 engine that lets you run JavaScript outside the browser — typically used for building backend servers."

Q: What is npm?
A: "npm is Node's package manager, used to install and manage third-party libraries.for example, installing React, Tailwind, Firebase SDK, and other dependencies."



MERN Stack

Q: What does MERN stand for?
A: "MongoDB, Express.js, React, and Node.js — a full JavaScript stack for building web apps, where React handles the frontend and the other three handle the backend, database, and server."




Bootstrap

Q: What is Bootstrap and how is it different from Tailwind?
A: Bootstrap is a component-based CSS framework with pre-built UI components like navbars and cards, using a 12-column grid system. Tailwind, which is my primary tool, is utility-first — you compose custom designs from small utility classes instead of pre-styled components.


Material UI

Q: What is Material UI?
A: Material UI (MUI) is a React component library based on Google's Material Design — it provides ready-made, customizable components like buttons, modals, and forms. 





