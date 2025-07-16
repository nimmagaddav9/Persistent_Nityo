## 45 minutes interview with Persistent

## 1. Tell me about yourself

I am a **Senior Full Stack Engineer** with 12+ years of experience building .com websites for various organizations using **HTML5**, **CSS3**, **JavaScript**, **React.js**, and **Redux**.

For the past 2 years, I’ve been part of the **React migration team** at United Airlines, where we converted .NET pages to React on united.com.  
The frontend uses **React** with in-house **ATMOS** component libraries used company-wide.

I worked on several user-facing **security features**, including:

- Forgot password / Forgot MileagePlus number
- Security questions and sign-in features
- Miles-Pooling
- United Club pass management
- Recent Activity and dashboard updates
- KTN (Known Traveler Number)
- Accessibility (WCAG) improvements

To handle asynchronous flows, I used **Redux-Saga** for API calls, data fetching, and impure actions.

**Recent initiatives** include:

- **Miles-Pooling** (travel rewards point sharing)
- **TSA Precheck integration**
- **Under18 account restrictions**
- **Account security and management** updates

**Previous experience:**

- **Visa Inc. – Accelerator Team**  
  Remediated MBDA modules like Application Management, Portfolio Management, Analytics, Recurring Billing, and Virtual Terminal for clients like Wells Fargo and Bank of America.

- **Capital Group – DAVIS Project**  
  Built data visualizations using **Highcharts** in React and integrated with **AEM**.  
  Also worked on **Creative Workbench**, a writing tool for publishing articles.

- **Cerner Corporation**  
  Developed forms for **medical examinations**.

- **Office Depot**  
  Worked on **Black Friday reporting** tools.

- **Satinos Technologies**  
  Built a **tax portal** and **school website** (Schoomin) for **Vignan Schools**.

---

## 2. HTML

### Q: What is a Web Worker? Why would you use it?

**A:** A **Web Worker** allows JavaScript to run in a **background thread**, separate from the main UI thread.

This is useful for handling **heavy computations or blocking logic**—such as image processing, long loops, or polling APIs—**without freezing the UI**.  
It keeps the page responsive and improves user experience when doing non-UI intensive work in the background.

## 🚀 2. HTML Page Optimization – What are the best practices?

**Q: How do you optimize an HTML page for performance?**

**A: Key strategies:**

- Minify HTML, CSS, JS
- Defer non-critical JS with `defer` or `async`
- Lazy-load images (`loading="lazy"`) and use compressed formats like WebP
- Use semantic HTML for better rendering and accessibility
- Reduce HTTP requests (combine files, use sprites/icons)
- Preload key resources with `<link rel="preload">`
- Use caching headers and versioning for assets
- Avoid inline styles/scripts unless necessary
- Optimize critical rendering path: inline critical CSS, defer the rest
- Use a CDN for static assets
- Compress responses (gzip, Brotli)

---

**Q: What's the difference between `async` and `defer`?**

- **`async`**: Loads and executes the script _as soon as it’s available_. Doesn’t wait for HTML parsing.
- **`defer`**: Loads script in parallel, but executes _after_ HTML is parsed. Safer for DOM-dependent scripts.

---

## 🧩 3. Semantic Elements in HTML

**Q: What are semantic elements in HTML and why are they important?**

**A:** Semantic elements clearly describe their meaning to both the browser and developer. This improves:

- Accessibility (screen readers)
- SEO (search engines prioritize semantic structure)
- Maintainability (code clarity)

**Examples:**

- `<header>`, `<footer>`
- `<main>`, `<section>`, `<article>`
- `<nav>`, `<aside>`
- `<figure>`, `<figcaption>`

---

**Q: What's the difference between `<section>` and `<div>`?**

- `<section>` is semantic—it represents a standalone block of related content with a heading.
- `<div>` is purely structural—no inherent meaning.

---

**Q: When should you use `<article>` vs `<section>`?**

- Use `<article>` for independent, self-contained content (blog post, comment, news article).
- Use `<section>` to group related content under a heading that forms part of a larger document.

## 3. CSS

### Q: What is Responsive Web Design?

**A:** Responsive Web Design (RWD) is a design approach where the layout and elements of a web page adapt fluidly to different screen sizes and devices.  
It uses techniques like **flexible grids**, **media queries**, and **relative units** (%, `em`, `rem`, `vw`, `vh`) to ensure content looks good on desktops, tablets, and phones.

---

### Q: What are the different `position` values in CSS?

**A:** The `position` property determines how an element is placed in the document. Key values include:

- `static` – default, element follows normal document flow
- `relative` – positioned relative to its normal position
- `absolute` – positioned relative to the nearest positioned ancestor
- `fixed` – positioned relative to the viewport, stays in place during scroll
- `sticky` – toggles between `relative` and `fixed` depending on scroll position

---

### Q: What is `z-index` in CSS?

**A:** `z-index` controls the **stacking order** of positioned elements (those with `position` other than `static`).  
Higher `z-index` values appear in front of lower ones. It only works on **positioned** elements.

Example:

```css
.element {
  position: absolute;
  z-index: 10;
}
```

### Q: What's Flex?

**A:** Flexbox (`display: flex`) is a CSS layout model that makes it easier to align and distribute space among elements inside a container.

Key concepts:

- **Main axis** (horizontal by default) and **cross axis** (vertical)
- Automatically adjusts item sizes based on available space
- Helps with both **horizontal and vertical alignment**

**Common properties:**

**On the container:**

- `display: flex`
- `flex-direction`: row | column
- `justify-content`: flex-start | center | space-between | space-around
- `align-items`: stretch | center | flex-start | flex-end

**On the children:**

- `flex`: shorthand for `flex-grow`, `flex-shrink`, and `flex-basis`
- `align-self`: overrides container’s `align-items` for individual items

**Example:**

```css
.container {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
```

### Q: What are Media Types in CSS?

**A:** Media types specify the type of device or medium a stylesheet is targeting. They allow developers to apply styles conditionally based on how the content is being accessed.

**Common media types:**

- `screen` – for computer screens, tablets, smartphones
- `print` – for printed documents or print preview
- `speech` – for screen readers (used in accessibility)
  Media types are often combined with media features (like width, resolution) using media queries to create responsive designs.
  **Example:**

```css
@media screen and (max-width: 768px) {
  body {
    font-size: 16px;
  }
}
```

### Q: What’s the difference between SCSS and CSS?

| Feature          | CSS                            | SCSS (Sassy CSS)               |
| ---------------- | ------------------------------ | ------------------------------ |
| Variables        | Not supported (in classic CSS) | Supported using `$variable`    |
| Nesting          | Not supported                  | Fully supported                |
| Mixins/Functions | Not available                  | Supported for reuse            |
| Code Reusability | Limited                        | High                           |
| Syntax           | Plain styling rules            | CSS-compatible with extensions |
| Compilation      | No compilation needed          | Must be compiled to CSS        |

**Summary:**  
SCSS is a preprocessor that extends CSS by adding powerful features like variables, nesting, mixins, and functions. It helps write cleaner, more maintainable styles—especially in large or component-based codebases.

## 4. JavaScript

## Closure

A **closure** occurs when an **inner function** retains access to variables defined in its **outer function**, even after the outer function has finished executing.

In simpler terms:

> If any inner function holds on to outer function's data, that's a closure.

---

### Example:

```html
<script>
  function fun_one() {
    var x = 10;
    var y = 20;
    return () => {
      console.log(x);
      console.log(y);
    };
  }

  console.dir(fun_one());
  // Output in console:
  // 0: Closure (fun_one) { x: 10, y: 20 }
</script>
```

## What is the Event Loop?

The **Event Loop** is the mechanism in JavaScript that enables **non-blocking, asynchronous behavior**, even though JavaScript runs in a **single thread**.

It coordinates execution between:

- **Call Stack** – where functions are executed
- **Web APIs** – like `setTimeout`, `fetch`, DOM events, etc.
- **Callback Queue** – holds messages (callbacks) ready to be pushed onto the call stack
- **Microtask Queue** – used for promises and other microtasks

---

### How It Works:

1. JavaScript runs the first line and puts functions on the **call stack**.
2. When an async operation (like `setTimeout`) is called, it's handed off to the **Web API** environment.
3. Once the operation completes, its callback is pushed into the **callback queue**.
4. The **event loop** checks if the call stack is empty.
5. If empty, it moves the next function from the queue into the call stack and executes it.

---

### Example:

```js
console.log("Start");

setTimeout(() => {
  console.log("Timeout");
}, 0);

Promise.resolve().then(() => {
  console.log("Promise");
});

console.log("End");
```

### Summary

The **Event Loop** allows JavaScript to handle **asynchronous tasks** without blocking the **main thread**.  
This ensures the UI stays responsive and code execution remains efficient, even when handling time-consuming operations like API calls, timers, or user events.

---

### Q: Output of `isNaN('1')`

````js
isNaN('1'); // returns false

### Why?

The string `'1'` is **coerced into a number** before the `isNaN` check.
Since `Number('1')` results in the valid number `1`, it is **not** NaN.

So:

```js
isNaN('1')   // → false
isNaN('abc') // → true
````

### Output for the following code:

```js
x = 23;
let x;

function anotherRandomFunc() {
  message = "Hello"; // bad pratice
}

anotherRandomFunc();
```

### Summary

The code will throw a **ReferenceError** at `x = 23;` due to the **Temporal Dead Zone (TDZ)**.

If the TDZ error did not occur, calling `anotherRandomFunc()` would create a global variable `message`.

## Temporal Dead Zone (TDZ)

The **Temporal Dead Zone** is the time between entering a scope and the moment a variable declared with `let` or `const` is initialized.  
Accessing the variable during this period results in a **ReferenceError**.

Example:

```js
console.log(a); // ReferenceError: Cannot access 'a' before initialization
let a = 10;
```

TDZ helps catch errors by preventing access to variables before their declaration.

---

## Higher-Order Functions (HOFs) in JavaScript

A **Higher-Order Function** is a function that either:

- Takes one or more functions as arguments, or
- Returns a function as its result

They allow functions to be composed, reused, and abstracted.

**Common examples:**

- `Array.prototype.map`
- `Array.prototype.filter`
- `Array.prototype.reduce`
- `setTimeout`

### Q: What’s a Generator Function? (`function* genFunc(){}`)

A **Generator Function** is a special kind of function in JavaScript that can **pause** and **resume** its execution.

- Defined using the `function*` syntax (note the asterisk `*`)
- Uses the `yield` keyword to pause execution and send values out
- Calling a generator returns an **iterator** object with a `.next()` method
- Each `.next()` call resumes execution until the next `yield` or return

---

### Example:

```js
function* genFunc() {
  yield 1;
  yield 2;
  return 3;
}

const gen = genFunc();

console.log(gen.next()); // { value: 1, done: false }
console.log(gen.next()); // { value: 2, done: false }
console.log(gen.next()); // { value: 3, done: true }
```

### Use Cases

- Lazy evaluation (generate values on demand)
- Implementing iterators
- Managing asynchronous flows (with `async`/`await`)
- State machines

### Difference Between Promises and Observables in JavaScript

| Feature        | Promises                                      | Observables                                               |
| -------------- | --------------------------------------------- | --------------------------------------------------------- |
| Values emitted | Single value (resolved or rejected)           | Multiple values over time                                 |
| Lazy?          | Yes                                           | Yes                                                       |
| Cancelable?    | No                                            | Yes                                                       |
| Operators      | Limited (`then`, `catch`, `finally`)          | Rich set of operators (`map`, `filter`, `debounce`, etc.) |
| Execution      | Starts immediately when created               | Execution starts on subscription                          |
| Use cases      | Single async operations (e.g., HTTP requests) | Streams, events, real-time data, user input               |

---

**Summary:**

- Use **Promises** for one-time async operations that resolve or reject once.
- Use **Observables** (e.g., with RxJS) for handling streams of data over time, allowing cancellation and complex operations.

## 5. NodeJS

### Types of Subjects in RxJS

In RxJS, a **Subject** is both an **Observable** and an **Observer**. It can multicast to many observers.

There are several types of Subjects:

- **Subject**  
  The basic form. Starts empty and emits values to subscribers from the point of subscription onward.

- **BehaviorSubject**  
  Requires an initial value and **emits the latest value** to new subscribers immediately upon subscription.

- **ReplaySubject**  
  Records a specified number of previous emissions and replays them to new subscribers.

- **AsyncSubject**  
  Emits only the **last value** (and only when the Observable completes).

---

### Summary:

| Subject Type    | Emits to New Subscribers                        |
| --------------- | ----------------------------------------------- |
| Subject         | Values emitted after subscription               |
| BehaviorSubject | Most recent value immediately upon subscription |
| ReplaySubject   | Specified number of previous values             |
| AsyncSubject    | Last value only after completion                |

## Pros and Cons of Node.js

### Pros

- **Fast and efficient**  
  Built on Chrome’s V8 engine, Node.js executes JavaScript very quickly.

- **Non-blocking, event-driven architecture**  
  Handles many concurrent connections with minimal overhead.

- **Single language (JavaScript) for frontend and backend**  
  Simplifies development and allows code reuse.

- **Large ecosystem**  
  Vast npm repository with thousands of libraries and tools.

- **Scalable**  
  Suitable for microservices and real-time applications (chat, streaming).

- **Active community and corporate support**  
  Constant improvements and plenty of learning resources.

---

### Cons

- **Single-threaded limitations**  
  CPU-intensive tasks can block the event loop and degrade performance.

- **Callback hell** (less common now with async/await)  
  Complex asynchronous code can become hard to manage.

- **Maturity**  
  Some libraries and tools are less mature compared to older backend platforms.

- **Not ideal for heavy computation**  
  Better suited for I/O-bound applications rather than CPU-bound.

- **API instability**  
  Some APIs have changed frequently in early versions (less so now).

---

**Summary:**  
Node.js excels at building fast, scalable I/O-heavy applications but requires care when handling CPU-intensive workloads.

## Streams in Node.js

**Streams** are objects that let you read data from a source or write data to a destination **in chunks**, rather than all at once.  
This makes streams efficient for handling large files, network communications, or any I/O operation.

---

### Types of Streams

- **Readable**: streams you can read data from (e.g., `fs.createReadStream`)
- **Writable**: streams you can write data to (e.g., `fs.createWriteStream`)
- **Duplex**: streams that are both readable and writable (e.g., TCP sockets)
- **Transform**: duplex streams that can modify or transform the data as it is written and read (e.g., compression)

---

### Benefits

- Handle large data efficiently without buffering entire content in memory
- Support **backpressure** to control the flow of data
- Allow piping data from one stream to another, simplifying data processing

---

### Example

```js
const fs = require("fs");

const readable = fs.createReadStream("input.txt");
const writable = fs.createWriteStream("output.txt");

readable.pipe(writable);
```

This reads `input.txt` chunk by chunk and writes it to `output.txt` without loading the entire file into memory.

---

### Summary

Streams are core to Node.js for efficient I/O operations, enabling scalable and performant applications.

## `fork()` Function in Node.js

The `fork()` function is a special case of `child_process.spawn()` used to create a new Node.js process. It is mainly used to run another JavaScript file as a separate process.

---

### Key Features

- Creates a new Node.js instance with its own event loop and memory.
- Enables inter-process communication (IPC) between parent and child using messaging.
- Useful for CPU-intensive tasks or running separate modules without blocking the main process.

---

### Usage Example

```js
const { fork } = require("child_process");

const child = fork("child.js");

child.on("message", (msg) => {
  console.log("Message from child:", msg);
});

child.send({ hello: "world" });
```

## Security Implementation in Node.js

### Key Practices

- **Input Validation & Sanitization**  
  Prevent injection attacks (SQL, NoSQL, command injection) by validating and sanitizing all user inputs.

- **Use HTTPS**  
  Always serve over HTTPS to encrypt data in transit.

- **Manage Secrets Safely**  
  Store API keys, tokens, and passwords securely using environment variables or secret management tools.

- **Authentication & Authorization**  
  Implement robust auth using JWT, OAuth, or sessions. Limit access based on roles and permissions.

- **Avoid Vulnerable Dependencies**  
  Regularly audit and update npm packages. Use tools like `npm audit` or `Snyk`.

- **Prevent Cross-Site Scripting (XSS)**  
  Escape user-generated content before rendering on client.

- **Prevent Cross-Site Request Forgery (CSRF)**  
  Use CSRF tokens to validate requests.

- **Secure Headers**  
  Use modules like `helmet` to set HTTP headers (Content Security Policy, X-Frame-Options, etc.).

- **Rate Limiting and Throttling**  
  Protect APIs from brute force or denial-of-service attacks.

- **Error Handling**  
  Avoid leaking sensitive info in error messages.

---

### Tools & Libraries

- `helmet` — sets security-related HTTP headers
- `express-validator` — input validation
- `bcrypt` — secure password hashing
- `jsonwebtoken` — JWT auth
- `cors` — enable and configure CORS securely

---

### Summary

Security in Node.js requires a multi-layered approach: validate inputs, protect data in transit, manage dependencies, enforce strict auth, and configure secure headers.

## Clustering in Node.js

Node.js runs on a single thread by default, which limits CPU core utilization.  
**Clustering** allows you to create multiple child processes (workers) that share the same server port and run in parallel, leveraging multi-core systems.

---

### How Clustering Works

- The main process (master) spawns multiple worker processes.
- Each worker runs its own event loop and handles incoming requests.
- Workers share the same server port, allowing load distribution.
- If a worker crashes, the master can restart it for resilience.

---

### Basic Example

```js
const cluster = require("cluster");
const http = require("http");
const numCPUs = require("os").cpus().length;

if (cluster.isMaster) {
  console.log(`Master ${process.pid} is running`);

  // Fork workers
  for (let i = 0; i < numCPUs; i++) {
    cluster.fork();
  }

  cluster.on("exit", (worker, code, signal) => {
    console.log(`Worker ${worker.process.pid} died. Restarting...`);
    cluster.fork();
  });
} else {
  // Workers can share the TCP connection
  http
    .createServer((req, res) => {
      res.writeHead(200);
      res.end(`Hello from worker ${process.pid}`);
    })
    .listen(8000);

  console.log(`Worker ${process.pid} started`);
}
```

### Benefits

- Improves performance by utilizing all CPU cores.
- Increases application reliability through worker restarts.
- Enables horizontal scaling on a single machine.

---

### Summary

Clustering is a simple way to scale Node.js applications vertically by forking worker processes that handle requests concurrently.

## 6. Angular

### Dependency Injection (DI) in Angular

Dependency Injection (DI) is a design pattern Angular uses to supply components or services with the dependencies they need.

Instead of creating dependencies inside a class, Angular injects them from an external source, making the code more modular, testable, and maintainable.

---

### How DI Works in Angular

- Angular has an **injector** that maintains a container of dependencies (services).
- Components declare dependencies in their constructor.
- Angular resolves and provides those dependencies automatically at runtime.

---

### Example

```ts
import { Injectable } from "@angular/core";

@Injectable({
  providedIn: "root",
})
export class ApiService {
  getData() {
    return "data";
  }
}

@Component({
  selector: "app-example",
  template: "{{ data }}",
})
export class ExampleComponent {
  data: string;

  constructor(private apiService: ApiService) {
    this.data = this.apiService.getData();
  }
}
```

Here, `ApiService` is injected into `ExampleComponent` via the constructor.

---

### Benefits of DI

- Promotes loose coupling between classes
- Easier unit testing by injecting mocks/stubs
- Centralizes dependency management
- Enables reusable and maintainable code

---

### Providers

- Services are registered with **providers** in modules, components, or via `providedIn: 'root'`.
- Providers define how and where dependencies are created.

---

### Summary

Angular’s DI system simplifies the management of service instances, improves testability, and promotes clean, modular architecture.

## Eager vs Lazy Loading

### Eager Loading

- Loads all components, modules, or resources **upfront** when the application starts.
- Ensures everything is available immediately but can increase initial load time.
- Common in small apps or for critical modules that must be ready instantly.

### Lazy Loading

- Loads components or modules **on demand**, only when needed.
- Reduces initial load time and improves performance, especially for large apps.
- Often used with route-based code splitting in frameworks like Angular or React.

---

### Summary

- **Eager Loading** prioritizes availability at startup, possibly at the cost of slower initial loads.
- **Lazy Loading** optimizes load time by deferring non-essential resources until required, improving user experience.

## Types of Route Guards in Angular

Route guards control navigation and access to routes in an Angular application.

### 1. CanActivate

- Checks if a route can be **activated**.
- Used to prevent unauthorized access to routes.

### 2. CanActivateChild

- Checks if **child routes** of a route can be activated.
- Useful when protecting a group of child routes.

### 3. CanDeactivate

- Checks if a route can be **exited** or deactivated.
- Commonly used to warn users about unsaved changes before leaving a page.

### 4. Resolve

- Pre-fetches data **before** activating the route.
- Ensures components have necessary data when they load.

### 5. CanLoad

- Prevents **lazy-loaded modules** from loading unless certain conditions are met.
- Useful for blocking access to entire feature modules.

---

### Summary

Angular’s route guards help manage access control, data loading, and user flow, improving security and user experience.

### What is `CanLoad` used for?

`CanLoad` is a route guard in Angular that prevents **lazy-loaded modules** from being loaded unless certain conditions are met.

---

### Key points:

- Runs **before** the module is loaded.
- Stops unauthorized users from downloading entire feature modules.
- Useful for improving app performance and security by blocking access early.

---

### Example use case:

Prevent loading an admin module unless the user has admin privileges.

```ts
export class AuthGuard implements CanLoad {
  constructor(private authService: AuthService, private router: Router) {}

  canLoad(route: Route): boolean {
    if (this.authService.isAdmin()) {
      return true;
    } else {
      this.router.navigate(["/not-authorized"]);
      return false;
    }
  }
}
```

### What do Providers mean in the context of Angular services?

In Angular, **providers** tell the dependency injection system **how to create and deliver a service** instance.

---

### Key points:

- A provider defines **where** and **how** Angular should create an instance of a service.
- Services need to be registered with providers to be injectable.
- Providers can be registered at different levels:
  - **Root level** (application-wide singleton)
  - **Module level** (scoped to a module)
  - **Component level** (scoped to component and its children)

---

### Common ways to register providers:

- Using `providedIn` metadata in `@Injectable` decorator:
  ```ts
  @Injectable({
    providedIn: "root",
  })
  export class MyService {}
  ```
  This makes the service available app-wide as a singleton.

---

### Adding `providers` array in an NgModule or component:

```ts
@NgModule({
  providers: [MyService],
})
export class SomeModule {}
```

### Summary

Providers configure Angular’s Dependency Injection (DI) system to know **how** and **where** to create service instances,  
controlling their **scope** (application-wide, module-level, or component-level) and **lifecycle**.

## HTTP Interceptors in Angular

### What is an HTTP Interceptor?

An **HTTP Interceptor** is a special service in Angular that sits between your application and the backend.  
It lets you **intercept, modify, or log** outgoing HTTP requests and incoming responses.

---

### Common Use Cases

- Add authentication tokens (e.g., JWT) to headers
- Log or handle errors globally
- Show and hide loading indicators
- Modify requests or responses
- Retry failed requests

---

### Example: Adding an Authorization Header

```ts
@Injectable()
export class AuthInterceptor implements HttpInterceptor {
  constructor(private authService: AuthService) {}

  intercept(
    req: HttpRequest<any>,
    next: HttpHandler
  ): Observable<HttpEvent<any>> {
    const token = this.authService.getToken();

    const cloned = req.clone({
      setHeaders: {
        Authorization: `Bearer ${token}`,
      },
    });

    return next.handle(cloned);
  }
}
```

### Summary

HTTP Interceptors in Angular are powerful for centralizing cross-cutting concerns like authentication, error handling, and logging, making your HTTP code cleaner and more maintainable.

## 7. React

### What is Redux?

**Redux** is a predictable state management library used in JavaScript applications, commonly with React.

It centralizes the application state into a **single store**, making state changes predictable and easier to debug.

---

### Core Concepts

- **Store**: The single source of truth that holds the app state.
- **Action**: A plain JavaScript object that describes what happened.
- **Reducer**: A pure function that takes the current state and an action, and returns the new state.
- **Dispatch**: Sends an action to the store to trigger a state change.
- **Selector**: Extracts specific data from the store.

---

### Example Flow

1. Component dispatches an action
2. Redux passes the action to the reducer
3. Reducer returns a new state
4. UI re-renders with the updated state

---

### Benefits

- Predictable state updates
- Centralized debugging (e.g. with Redux DevTools)
- Easier testing and maintenance
- Works well for medium to large applications

---

### Summary

Redux helps manage and centralize state in large React apps by enforcing a unidirectional data flow and clear separation between data and UI logic.

### What is Immutability?

**Immutability** means that an object’s state **cannot be changed after it’s created**.  
Instead of modifying the original object or array, you create and return a **new copy** with the updated values.

---

### Why It Matters in React/Redux

- Ensures **predictable state updates**
- Makes **time-travel debugging** possible
- Avoids unintended side effects
- Helps React detect changes (via shallow comparison)

---

### Example (Wrong: Mutating)

```js
const state = { count: 1 };
state.count = 2; // ❌ mutation
```

### Summary

Immutability is a key principle in React and Redux that ensures state changes are **predictable**, **traceable**, and **efficient**.

### What are React Hooks?

React Hooks are built-in functions that let you use state and other React features in functional components—without writing a class.

**Common hooks:**

- `useState` – manage local state
- `useEffect` – handle side effects
- `useContext` – access context
- `useRef` – reference DOM or store mutable values
- `useMemo`, `useCallback` – performance optimizations

**Rules:** Only call hooks at the top level, inside function components or custom hooks.

### What is React Router?

**React Router** is a standard library for routing in React.  
It enables navigation between different components (pages) in a single-page application (SPA) without reloading the page.

---

### Key Features

- Declarative routing using components like `<Route>`, `<Link>`, and `<Navigate>`
- Nested routes for complex layouts
- Dynamic route matching (e.g., `/users/:id`)
- Programmatic navigation using `useNavigate()`
- Route protection with wrappers or conditions

---

### Basic Example

```jsx
import { BrowserRouter, Routes, Route, Link } from "react-router-dom";

function App() {
  return (
    <BrowserRouter>
      <nav>
        <Link to="/">Home</Link> | <Link to="/about">About</Link>
      </nav>
      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/about" element={<About />} />
      </Routes>
    </BrowserRouter>
  );
}
```

### Summary

React Router enables client-side routing in React apps—keeping the UI in sync with the URL without full page reloads.

## 8. AEM

### AEM Design Patterns

AEM (Adobe Experience Manager) design patterns are reusable best practices and structures for building scalable, maintainable AEM applications.

---

### Common AEM Design Patterns

- **Component-Based Architecture**  
  Build modular, reusable components that encapsulate both content and logic.

- **Sling Models**  
  Use Sling Models to map Sling resources to Java objects, making backend logic cleaner and easier to maintain.

- **HTL (Sightly) Templates**  
  Use HTL for secure, HTML-centric templating that separates markup from business logic.

- **Use of Client Libraries**  
  Manage CSS and JavaScript dependencies via clientlibs to optimize delivery and caching.

- **Dispatcher Caching**  
  Configure dispatcher caching rules to improve performance and scalability.

- **Content Fragment and Experience Fragment**  
  Leverage fragments to reuse content across pages and channels.

- **Event Handling with Observers**  
  Use event handlers and observers for asynchronous processing and decoupling.

- **Service Layer Design**  
  Implement service layers to encapsulate business logic, separate from component code.

---

### Summary

Following AEM design patterns leads to modular, maintainable, and performant AEM projects by leveraging componentization, proper templating, caching, and clean backend logic.

## AEM Connectors

**AEM Connectors** are integrations between Adobe Experience Manager and other Adobe or third-party systems to extend AEM’s capabilities and enable seamless workflows.

---

### Common AEM Connectors

- **Adobe Marketing Cloud**  
  Integrates AEM with Adobe Analytics, Adobe Target, and Adobe Campaign for unified marketing automation and personalization.

- **Adobe Asset Link**  
  Connects AEM Assets with Adobe Creative Cloud apps (Photoshop, Illustrator) to streamline asset management and editing.

- **Adobe Commerce (Magento)**  
  Syncs content between AEM and Magento to deliver rich shopping experiences with CMS-managed content.

- **Salesforce Connector**  
  Integrates AEM with Salesforce CRM for personalized customer experiences using CRM data.

- **Social Media Connectors**  
  Enable publishing and syndication of content to platforms like Facebook, Twitter, and LinkedIn.

- **DAM Connectors**  
  Sync third-party Digital Asset Management (DAM) systems with AEM Assets.

---

### Benefits of AEM Connectors

- Streamline workflows between marketing, creative, commerce, and sales teams
- Enable personalized, data-driven experiences
- Reduce manual data synchronization
- Enhance asset management and delivery

---

### Summary

AEM Connectors enable powerful integrations that extend AEM’s core features, making it a central hub for digital experience management.

## OSGi Lifecycle

OSGi (Open Services Gateway initiative) defines a dynamic module system for Java that manages the lifecycle of bundles (modules) at runtime.

---

### OSGi Bundle Lifecycle States

1. **Installed**  
   The bundle has been successfully installed but is not yet resolved.

2. **Resolved**  
   All dependencies are resolved; the bundle is ready to be started.

3. **Starting**  
   The bundle is in the process of starting. Its `BundleActivator.start()` method is called.

4. **Active**  
   The bundle is running and its services are available.

5. **Stopping**  
   The bundle is stopping. Its `BundleActivator.stop()` method is called.

6. **Uninstalled**  
   The bundle has been removed and is no longer available.

---

### Lifecycle Transitions

- Install → Resolve → Start → Active
- Active → Stop → Resolved
- Resolved → Uninstall → Uninstalled

---

### Summary

The OSGi lifecycle allows modular Java applications like AEM to dynamically install, start, stop, update, and uninstall components without restarting the entire system.

## Advantages of OSGi

- **Modularity**  
  Enables breaking applications into reusable, loosely coupled bundles (modules).

- **Dynamic Updates**  
  Supports installing, updating, and uninstalling bundles at runtime without restarting the application.

- **Versioning**  
  Allows multiple versions of the same bundle or library to coexist.

- **Service-Oriented**  
  Promotes service registration and discovery, enabling dynamic binding between components.

- **Improved Maintainability**  
  Smaller, focused bundles are easier to develop, test, and maintain.

- **Resource Isolation**  
  Bundles have their own classloaders, preventing class conflicts.

- **Scalability**  
  Suitable for large, complex applications that require modular architecture.

- **Used in Enterprise Platforms**  
  Foundation for systems like Adobe Experience Manager (AEM) and Eclipse.

---

### Summary

OSGi provides a flexible, modular framework that enhances application maintainability, scalability, and dynamic behavior.
