Here is the full list of 60 React interview questions:

- [1. What is React?](#1-what-is-react)
- [2. **What is `useMemo`?**](#2-what-is-usememo)
- [3. **What are the features of React?**](#3-what-are-the-features-of-react)
- [4. **What is JSX?**](#4-what-is-jsx)
- [5. **What is DOM?**](#5-what-is-dom)
- [6. **What is Virtual DOM?**](#6-what-is-virtual-dom)
- [7. **What is the component lifecycle of a React class component?**](#7-what-is-the-component-lifecycle-of-a-react-class-component)
- [8. **What are fragments in React?**](#8-what-are-fragments-in-react)
- [9. **What are props in React?**](#9-what-are-props-in-react)
- [10. **What are synthetic events in React?**](#10-what-are-synthetic-events-in-react)
- [11. **What are the differences between `package.json` and `package-lock.json`?**](#11-what-are-the-differences-between-packagejson-and-package-lockjson)
- [12. **What are the differences between client-side and server-side rendering?**](#12-what-are-the-differences-between-client-side-and-server-side-rendering)
- [13. **What is state in React.js?**](#13-what-is-state-in-reactjs)
- [14. **What are props?**](#14-what-are-props)
- [15. **What are the differences between State and Props in React?**](#15-what-are-the-differences-between-state-and-props-in-react)
- [16. **What is props drilling?**](#16-what-is-props-drilling)
- [17. **What are the disadvantages of props drilling and how can we avoid it?**](#17-what-are-the-disadvantages-of-props-drilling-and-how-can-we-avoid-it)
- [18. **What are Pure Components in React?**](#18-what-are-pure-components-in-react)
- [19. **What are Refs in React?**](#19-what-are-refs-in-react)
- [20. **What is meant by forward ref?**](#20-what-is-meant-by-forward-ref)
- [21. **What are Error Boundaries?**](#21-what-are-error-boundaries)
- [22. **What are Higher Order Components (HOCs) in React?**](#22-what-are-higher-order-components-hocs-in-react)
- [23. **What are the differences between controlled and uncontrolled components?**](#23-what-are-the-differences-between-controlled-and-uncontrolled-components)
- [24. **What is `useCallback`?**](#24-what-is-usecallback)
- [25. **What are the differences between `useMemo` and `useCallback`?**](#25-what-are-the-differences-between-usememo-and-usecallback)
- [26. **What are keys in React?**](#26-what-are-keys-in-react)
- [27. **What is Lazy Loading in React?**](#27-what-is-lazy-loading-in-react)
- [28. **What is Suspense in React?**](#28-what-is-suspense-in-react)
- [29. **What are custom hooks?**](#29-what-are-custom-hooks)
- [30. **What is `useReducer` hook?**](#30-what-is-usereducer-hook)
- [31. **What are Portals in React?**](#31-what-are-portals-in-react)
- [32. **What is context in React?**](#32-what-is-context-in-react)
- [33. **Practical question: Give an example of context API usage.**](#33-practical-question-give-an-example-of-context-api-usage)
- [34. **What is the purpose of a callback function as an argument of `setState()`?**](#34-what-is-the-purpose-of-a-callback-function-as-an-argument-of-setstate)
- [35. **Practical question: Create a custom hook for an increment/decrement counter.**](#35-practical-question-create-a-custom-hook-for-an-incrementdecrement-counter)
- [36. **Which lifecycle hooks in class components are replaced with `useEffect` in functional components?**](#36-which-lifecycle-hooks-in-class-components-are-replaced-with-useeffect-in-functional-components)
- [37. **What is Strict Mode in React?**](#37-what-is-strict-mode-in-react)
- [38. **What are the different ways to pass data from a child component to a parent component in React?**](#38-what-are-the-different-ways-to-pass-data-from-a-child-component-to-a-parent-component-in-react)
- [39. **Practical question: How to send data from child to parent using callback functions?**](#39-practical-question-how-to-send-data-from-child-to-parent-using-callback-functions)
- [40. **Practical question: How to send data from a child component to a parent using `useRef`?**](#40-practical-question-how-to-send-data-from-a-child-component-to-a-parent-using-useref)
- [41. **How do you optimize your React application?**](#41-how-do-you-optimize-your-react-application)
- [42. **How would you consume a RESTful JSON API in React.js?**](#42-how-would-you-consume-a-restful-json-api-in-reactjs)
- [43. **Different design patterns used in React?**](#43-different-design-patterns-used-in-react)
- [44. **Context API vs Redux**](#44-context-api-vs-redux)
- [45. **Prop Types in React (How to apply validation on props in React)?**](#45-prop-types-in-react-how-to-apply-validation-on-props-in-react)
- [46. **What are React Mixins?**](#46-what-are-react-mixins)
- [47. **What are the different hooks you have used?**](#47-what-are-the-different-hooks-you-have-used)
- [48. **What are Render Props in React?**](#48-what-are-render-props-in-react)
- [49. **What are the different types of exports and imports?**](#49-what-are-the-different-types-of-exports-and-imports)
- [50. **What are the differences between `createElement` vs `cloneElement` in React?**](#50-what-are-the-differences-between-createelement-vs-cloneelement-in-react)
- [51. **When to use `useState` and `useReducer`?**](#51-when-to-use-usestate-and-usereducer)
- [52. **What is `flushSync` in React?**](#52-what-is-flushsync-in-react)
- [53. **What are protected routes in React?**](#53-what-are-protected-routes-in-react)
- [54. **What is React Router's context menu?**](#54-what-is-react-routers-context-menu)
- [55. **What are the lifecycle methods in Redux?**](#55-what-are-the-lifecycle-methods-in-redux)
- [56. **What is the use of store in Redux?**](#56-what-is-the-use-of-store-in-redux)
- [57. **What is `useCallback` hook? How to implement it?**](#57-what-is-usecallback-hook-how-to-implement-it)
- [58. **What is `React.memo` and `useMemo`? Please explain it.**](#58-what-is-reactmemo-and-usememo-please-explain-it)
- [59. **What is state management in React? Why use a state management library?**](#59-what-is-state-management-in-react-why-use-a-state-management-library)
- [60. **Why use React over Angular? What are the advantages and disadvantages of these JavaScript frameworks?**](#60-why-use-react-over-angular-what-are-the-advantages-and-disadvantages-of-these-javascript-frameworks)

Here are the answers to the React interview questions:

#### <a id="q1"></a>1. What is React?
   - **Answer:** React is a popular JavaScript library developed by Facebook for building user interfaces, particularly single-page applications. It allows developers to create reusable UI components and manage the view layer efficiently. React uses a declarative approach to build interactive UIs, and its virtual DOM enhances performance by minimizing direct manipulation of the actual DOM.

#### <a id="q2"></a>2. **What is `useMemo`?**
   - **Answer:** `useMemo` is a React Hook that allows you to memoize the result of a computation. It only recomputes the memoized value when one of the dependencies has changed. This is useful for optimizing performance, particularly for expensive calculations or to prevent unnecessary re-renders of components. The syntax is `const memoizedValue = useMemo(() => computeValue(a, b), [a, b]);`.

#### <a id="q3"></a>3. **What are the features of React?**
   - **Answer:** React has several key features:
     - **Component-Based Architecture:** React allows you to build encapsulated components that manage their own state and can be composed to create complex UIs.
     - **Virtual DOM:** React uses a virtual representation of the DOM to optimize updates and improve performance.
     - **Unidirectional Data Flow:** Data flows in one direction, making it easier to understand and debug applications.
     - **JSX:** React uses JSX, a syntax extension that allows HTML to be written within JavaScript, making the code more readable and easier to write.
     - **Declarative UI:** React makes it easier to build dynamic user interfaces by allowing developers to describe the UI in terms of its current state.

#### <a id="q4"></a>4. **What is JSX?**
   - **Answer:** JSX stands for JavaScript XML. It is a syntax extension for JavaScript that allows you to write HTML-like code within JavaScript files. JSX is syntactic sugar for `React.createElement` and makes it easier to create and manage the structure of React components. While it looks similar to HTML, JSX allows you to use JavaScript expressions within it.

#### <a id="q5"></a>5. **What is DOM?**
   - **Answer:** The DOM (Document Object Model) is a programming interface for web documents. It represents the structure of an HTML or XML document as a tree of objects, allowing scripts to dynamically access and update the content, structure, and style of the document. The DOM provides a way for JavaScript to interact with and manipulate web pages.

#### <a id="q6"></a>6. **What is Virtual DOM?**
   - **Answer:** The Virtual DOM is a lightweight, in-memory representation of the actual DOM. React maintains this virtual DOM to optimize updates to the real DOM. When the state of a React component changes, React creates a new Virtual DOM tree, compares it with the previous one (a process known as "reconciliation"), and updates only the parts of the real DOM that have changed, leading to better performance.

#### <a id="q7"></a>7. **What is the component lifecycle of a React class component?**
- **Answer:** The lifecycle of a React class component can be divided into three main phases:
     - **Mounting:** When the component is created and inserted into the DOM. Methods include `constructor()`, `componentDidMount()`, and `render()`.
     - **Updating:** When the component is being re-rendered due to changes in props or state. Methods include `componentDidUpdate()`, `shouldComponentUpdate()`, and `render()`.
     - **Unmounting:** When the component is being removed from the DOM. The primary method here is `componentWillUnmount()`.
     - **Error Handling:** There’s also an error handling phase with methods like `componentDidCatch()` to catch errors during rendering.

#### <a id="q8"></a>8. **What are fragments in React?**
- **Answer:** Fragments in React allow you to group multiple elements without adding extra nodes to the DOM. This is useful when a component needs to return multiple elements but you don’t want to wrap them in an additional `div` or other container element. You can use fragments with the `<React.Fragment>` tag or shorthand syntax `<></>`.

#### <a id="q9"></a>9. **What are props in React?**
- **Answer:** Props (short for properties) are inputs to a React component. They are passed from parent to child components and are immutable within the child component. Props allow you to pass data, event handlers, or other information to components, enabling them to be dynamic and reusable. They are accessed in the child component using `this.props` (in class components) or directly through the argument (in functional components).

#### <a id="q10"></a>10. **What are synthetic events in React?**
- **Answer:** Synthetic events are React's cross-browser wrapper around the browser's native event system. They are designed to work identically across all browsers, ensuring consistent behavior and performance. Synthetic events have the same interface as native events, including methods like `stopPropagation()` and `preventDefault()`, but they also add some React-specific optimizations, such as automatic event pooling.

#### <a id="q11"></a>11. **What are the differences between `package.json` and `package-lock.json`?**
- **Answer:** 
      - **`package.json`:** This file contains metadata about the project and its dependencies. It lists the packages your project depends on, scripts you can run, versioning information, and other configurations.
      - **`package-lock.json`:** This file is automatically generated and ensures that dependencies are installed in the exact versions specified. It locks the versions of all installed packages and their dependencies, ensuring consistent installs across different environments.

#### <a id="q12"></a>12. **What are the differences between client-side and server-side rendering?**
- **Answer:**
      - **Client-Side Rendering (CSR):** In CSR, the browser downloads a minimal HTML page and JavaScript files, which then render the full content in the browser. CSR can provide a faster initial page load but may suffer from SEO challenges since content is rendered after the page is loaded.
      - **Server-Side Rendering (SSR):** In SSR, the HTML is fully rendered on the server and sent to the browser. This results in faster initial content display and better SEO because the content is available immediately upon loading. However, it may result in slower interactivity as the JavaScript takes longer to load.

#### <a id="q13"></a>13. **What is state in React.js?**
- **Answer:** State in React.js refers to an object that holds data that may change over the lifecycle of a component. State is managed within the component (in class components, using `this.setState`; in functional components, using the `useState` Hook). When the state changes, React re-renders the component to reflect the updated data.

#### <a id="q14"></a>14. **What are props?**
- **Answer:** Props (short for properties) are inputs passed from a parent component to a child component in React. They allow data and event handlers to be passed between components, making the component dynamic and reusable. Props are read-only and cannot be modified by the receiving component.

#### <a id="q15"></a>15. **What are the differences between State and Props in React?**
- **Answer:**
      - **State:** 
        - Managed within the component.
        - Can change over time, triggering a re-render.
        - Used for storing data that changes within the component.
      - **Props:**
        - Passed to the component from a parent.
        - Immutable within the receiving component.
        - Used for passing data and functions to child components.

#### <a id="q16"></a>16. **What is props drilling?**
- **Answer:** Props drilling refers to the process of passing data from a parent component down through multiple levels of nested child components, even if intermediate components don't need the data. This can make the code more difficult to maintain and understand.

#### <a id="q17"></a>17. **What are the disadvantages of props drilling and how can we avoid it?**
- **Answer:** 
      - **Disadvantages:**
        - Makes the code harder to manage and understand.
        - Can lead to unnecessary re-renders of intermediate components.
        - Increases coupling between components.
      - **Avoiding Props Drilling:** 
        - Use **React Context API** to share data between components without drilling.
        - Implement **state management libraries** like Redux or Zustand.
        - Utilize custom Hooks to encapsulate shared logic.

#### <a id="q18"></a>18. **What are Pure Components in React?**
- **Answer:** A Pure Component in React is a class component that implements the `shouldComponentUpdate` lifecycle method with a shallow comparison of props and state. If the new props and state are identical to the previous ones, the component does not re-render, improving performance by avoiding unnecessary updates. Functional components can achieve similar behavior using `React.memo`.

#### <a id="q19"></a>19. **What are Refs in React?**
- **Answer:** Refs (short for references) provide a way to access DOM nodes or React elements directly within a component. Refs can be used to focus an input, select text, or trigger animations. In class components, refs are created using `React.createRef()` and accessed via `this.myRef`. In functional components, the `useRef` Hook is used.

#### <a id="q20"></a>20. **What is meant by forward ref?**
- **Answer:** Forward ref is a technique in React that allows a parent component to pass a ref to a child component. This is useful when the parent needs to access the child’s DOM node or element directly. `React.forwardRef` is used to achieve this, allowing the parent component to interact with the child’s DOM element or another child component's ref.

#### <a id="q21"></a>21. **What are Error Boundaries?**
- **Answer:** Error boundaries are React components that catch JavaScript errors anywhere in their child component tree, log those errors, and display a fallback UI instead of the component tree that crashed. Error boundaries are created using the `componentDidCatch` lifecycle method or by wrapping components in a static `getDerivedStateFromError` method. They do not catch errors in event handlers, asynchronous code, or server-side rendering.

#### <a id="q22"></a>22. **What are Higher Order Components (HOCs) in React?**
- **Answer:** A Higher Order Component (HOC) is a pattern in React where a function takes a component as an argument and returns a new component. HOCs are used to add additional functionality to existing components, such as injecting props, adding state, or handling logic, without modifying the original component. They are often used for code reuse, logic encapsulation, and cross-cutting concerns.

#### <a id="q23"></a>23. **What are the differences between controlled and uncontrolled components?**
- **Answer:**
      - **Controlled Components:** 
        - The component’s state is controlled by React.
        - The form data is handled by the React state, and any input value changes are managed through event handlers.
        - Typically used when you need to interact with or validate the form data.
      - **Uncontrolled Components:**
        - The form data is handled by the DOM itself.
        - Refs are used to access the values, instead of relying on React state.
        - Simpler to implement but offers less control over the form inputs.

#### <a id="q24"></a>24. **What is `useCallback`?**
- **Answer:** `useCallback` is a React Hook that returns a memoized version of a callback function. It only recreates the function if one of its dependencies has changed. This is particularly useful for optimizing performance in components that rely on functions as props, ensuring the function reference remains stable between renders, preventing unnecessary re-renders of child components.

#### <a id="q25"></a>25. **What are the differences between `useMemo` and `useCallback`?**
- **Answer:**
      - **useMemo:** Memoizes the result of a computation and returns the memoized value. Used for optimizing expensive calculations.
      - **useCallback:** Memoizes a function reference, preventing unnecessary recreation of the function between renders. Used for optimizing functions passed as props or dependencies.
      - **Key Difference:** `useMemo` returns a value, while `useCallback` returns a function.

#### <a id="q26"></a>26. **What are keys in React?**
- **Answer:** Keys are special attributes in React used to identify elements in a list. They help React optimize rendering by tracking which items have changed, been added, or removed. Each key must be unique among siblings and should be stable across renders. Using keys effectively helps React perform efficient updates to the DOM.

#### <a id="q27"></a>27. **What is Lazy Loading in React?**
- **Answer:** Lazy loading in React refers to the technique of loading components asynchronously when they are needed, rather than loading all components upfront. React's `React.lazy` and `Suspense` components are used to implement lazy loading, improving the performance of the application by reducing the initial load time and splitting the code into smaller, manageable chunks.

#### <a id="q28"></a>28. **What is Suspense in React?**
- **Answer:** Suspense is a React component that allows you to handle loading states for components that are being lazy-loaded or are waiting for asynchronous data to resolve. When used with `React.lazy` for code-splitting or with concurrent features, Suspense can display a fallback UI (like a loading spinner) while the component is being loaded or data is being fetched.

#### <a id="q29"></a>29. **What are custom hooks?**
- **Answer:** Custom Hooks in React are functions that allow you to encapsulate and reuse stateful logic. They are built using existing hooks (like `useState`, `useEffect`, etc.) and follow the same rules as regular hooks. Custom hooks help in abstracting away complex logic, making components cleaner and more reusable.

#### <a id="q30"></a>30. **What is `useReducer` hook?**
- **Answer:** `useReducer` is a React Hook that is used for managing complex state logic in a component. It is an alternative to `useState` and is particularly useful when the state logic involves multiple sub-values or when the next state depends on the previous one. `useReducer` accepts a reducer function and an initial state, returning the current state and a dispatch function to trigger state updates based on actions.

#### <a id="q31"></a>31. **What are Portals in React?**
- **Answer:** Portals in React provide a way to render a child component into a different part of the DOM tree that is outside the parent component's hierarchy. This is useful for scenarios like modals, tooltips, or dropdowns where you need to visually break out of the parent container. Portals are created using `ReactDOM.createPortal(child, container)`.

#### <a id="q32"></a>32. **What is context in React?**
- **Answer:** Context in React is a feature that allows you to pass data through the component tree without having to pass props down manually at every level. It is designed for situations where some data (such as user authentication, theme, or language) needs to be accessible by many components at different nesting levels. Context is created using `React.createContext()` and consumed via `Context.Provider` and `Context.Consumer` or the `useContext` hook.

#### <a id="q33"></a>33. **Practical question: Give an example of context API usage.**
- **Answer:**
      ```javascript
      import React, { createContext, useContext, useState } from 'react';

      // Create a context
      const ThemeContext = createContext();

      // Provider component
      const ThemeProvider = ({ children }) => {
        const [theme, setTheme] = useState('light');
        return (
          <ThemeContext.Provider value={{ theme, setTheme }}>
            {children}
          </ThemeContext.Provider>
        );
      };

      // Consumer component using useContext
      const ThemedComponent = () => {
        const { theme, setTheme } = useContext(ThemeContext);
        return (
          <div style={{ background: theme === 'light' ? '#fff' : '#333', color: theme === 'light' ? '#000' : '#fff' }}>
            <p>The current theme is {theme}</p>
            <button onClick={() => setTheme(theme === 'light' ? 'dark' : 'light')}>Toggle Theme</button>
          </div>
        );
      };

      // App component
      const App = () => (
        <ThemeProvider>
          <ThemedComponent />
        </ThemeProvider>
      );

      export default App;
      ```

#### <a id="q34"></a>34. **What is the purpose of a callback function as an argument of `setState()`?**
- **Answer:** The callback function passed as an argument to `setState()` is executed after the state has been updated and the component has re-rendered. This is useful when you need to perform some action or trigger another update immediately after the state change has taken effect, ensuring that the state has been fully updated before executing further code.

#### <a id="q35"></a>35. **Practical question: Create a custom hook for an increment/decrement counter.**
- **Answer:**
      ```javascript
      import { useState } from 'react';

      const useCounter = (initialValue = 0) => {
        const [count, setCount] = useState(initialValue);

        const increment = () => setCount(count + 1);
        const decrement = () => setCount(count - 1);
        const reset = () => setCount(initialValue);

        return { count, increment, decrement, reset };
      };

      export default useCounter;
      ```

#### <a id="q36"></a>36. **Which lifecycle hooks in class components are replaced with `useEffect` in functional components?**
- **Answer:** The `useEffect` hook can replace several lifecycle methods in class components:
      - **`componentDidMount`** (executed when the component mounts).
      - **`componentDidUpdate`** (executed when the component updates).
      - **`componentWillUnmount`** (executed when the component unmounts, using the cleanup function inside `useEffect`).

#### <a id="q37"></a>37. **What is Strict Mode in React?**
- **Answer:** Strict Mode is a feature in React that helps identify potential problems in an application by running additional checks and warnings for its descendants. It helps in detecting side effects, deprecated APIs, and other issues during the development phase. Strict Mode is activated by wrapping a part of the component tree with `<React.StrictMode>`.

#### <a id="q38"></a>38. **What are the different ways to pass data from a child component to a parent component in React?**
- **Answer:**
      - **Using Callback Functions:** The parent component passes a function as a prop to the child, which the child calls with the data to send it back to the parent.
      - **Using Context API:** The child component can update context values, which the parent can observe.
      - **Using Refs:** The parent can pass a ref to the child, and the child can use it to expose its internal state or methods to the parent.
      - **Custom Event Emitters:** Although not native to React, custom event systems can be implemented to communicate between components.

#### <a id="q39"></a>39. **Practical question: How to send data from child to parent using callback functions?**
- **Answer:**
      ```javascript
      const ParentComponent = () => {
        const handleData = (data) => {
          console.log("Data from child:", data);
        };

        return <ChildComponent sendData={handleData} />;
      };

      const ChildComponent = ({ sendData }) => {
        const handleClick = () => {
          sendData("Hello from Child");
        };

        return <button onClick={handleClick}>Send Data to Parent</button>;
      };
      ```

#### <a id="q40"></a>40. **Practical question: How to send data from a child component to a parent using `useRef`?**
- **Answer:**
      ```javascript
      import React, { useRef, useEffect } from 'react';

      const ParentComponent = () => {
        const childRef = useRef();

        useEffect(() => {
          if (childRef.current) {
            console.log("Data from child:", childRef.current.getData());
          }
        }, []);

        return <ChildComponent ref={childRef} />;
      };

      const ChildComponent = React.forwardRef((props, ref) => {
        const getData = () => {
          return "Hello from Child";
        };

        React.useImperativeHandle(ref, () => ({
          getData,
        }));

        return <div>Child Component</div>;
      });

      export default ParentComponent;
      ```

#### <a id="q41"></a>41. **How do you optimize your React application?**
- **Answer:** Optimizing a React application can be achieved through several techniques:
      - **Code Splitting:** Use dynamic imports and lazy loading to split your code into smaller bundles.
      - **Memoization:** Utilize `React.memo`, `useMemo`, and `useCallback` to prevent unnecessary re-renders.
      - **Avoid Inline Functions:** Define functions outside of render methods to avoid creating new instances on every render.
      - **Use `useEffect` Wisely:** Limit side effects by setting appropriate dependency arrays in `useEffect`.
      - **Optimize Component Rendering:** Break down large components into smaller, more manageable components and use `React.PureComponent` or `React.memo`.
      - **Avoid Unnecessary State Updates:** Ensure that state changes only when necessary to reduce re-renders.
      - **Use Production Build:** Make sure to build the app for production with `npm run build`, which optimizes the code and reduces bundle size.

#### <a id="q42"></a>42. **How would you consume a RESTful JSON API in React.js?**
- **Answer:** To consume a RESTful JSON API in React:
      1. Use the `fetch` API or libraries like Axios to make HTTP requests.
      2. Handle the response by parsing the JSON data.
      3. Update the component state with the fetched data.
      4. Use `useEffect` to fetch data on component mount or when dependencies change.
      Example:
      ```javascript
      import React, { useState, useEffect } from 'react';

      const MyComponent = () => {
        const [data, setData] = useState([]);

        useEffect(() => {
          fetch('https://api.example.com/data')
            .then(response => response.json())
            .then(data => setData(data))
            .catch(error => console.error('Error fetching data:', error));
        }, []);

        return (
          <div>
            {data.map(item => (
              <div key={item.id}>{item.name}</div>
            ))}
          </div>
        );
      };

      export default MyComponent;
      ```

#### <a id="q43"></a>43. **Different design patterns used in React?**
- **Answer:**
      - **Container/Presentational Pattern:** Separates logic (container components) from UI (presentational components).
      - **Higher-Order Components (HOC):** A function that takes a component and returns a new component with added behavior.
      - **Render Props:** A technique where a component’s prop is a function that returns a React element.
      - **Custom Hooks:** Encapsulate and reuse stateful logic across components.
      - **Controlled/Uncontrolled Components:** Pattern for handling form elements.
      - **Compound Components:** Allow components to communicate with each other while staying flexible.
      - **State Lifting:** Moving shared state to a common ancestor to manage it in one place.

#### <a id="q44"></a>44. **Context API vs Redux**
- **Answer:**
      - **Context API:**
        - Built-in feature in React for passing data through the component tree.
        - Best suited for simple state management or when data needs to be accessed by many components.
        - Easier to set up but lacks middleware support, making it less suitable for complex state management.
      - **Redux:**
        - A standalone library for managing application state.
        - More powerful and scalable, with features like middleware, DevTools, and time-travel debugging.
        - Better suited for large applications with complex state requirements but requires more setup and boilerplate.

#### <a id="q45"></a>45. **Prop Types in React (How to apply validation on props in React)?**
- **Answer:** PropTypes are used to validate the types of props passed to a component. React has a built-in `PropTypes` library that you can use to define and validate props.
      Example:
      ```javascript
      import PropTypes from 'prop-types';

      const MyComponent = ({ name, age }) => (
        <div>
          <p>Name: {name}</p>
          <p>Age: {age}</p>
        </div>
      );

      MyComponent.propTypes = {
        name: PropTypes.string.isRequired,
        age: PropTypes.number,
      };

      MyComponent.defaultProps = {
        age: 18,
      };
      ```

#### <a id="q46"></a>46. **What are React Mixins?**
- **Answer:** Mixins are a way to share behavior between components in React. They allow you to add shared functionality across multiple components. However, React Mixins are mostly considered an anti-pattern and have been deprecated in favor of HOCs and custom hooks due to issues with component complexity and collision of method names.

#### <a id="q47"></a>47. **What are the different hooks you have used?**
- **Answer:** Commonly used hooks in React include:
      - **`useState`:** Manages state in functional components.
      - **`useEffect`:** Handles side effects like data fetching, subscriptions, or manual DOM changes.
      - **`useContext`:** Accesses data from a React Context.
      - **`useReducer`:** Manages complex state logic.
      - **`useRef`:** Creates mutable object references that persist across renders.
      - **`useMemo`:** Memoizes expensive calculations.
      - **`useCallback`:** Memoizes callback functions.
      - **`useLayoutEffect`:** Similar to `useEffect`, but fires synchronously after all DOM mutations.
      - **`useImperativeHandle`:** Customizes the instance value that is exposed to parent components when using `ref`.
      - **`useDebugValue`:** Displays a label in React DevTools for custom hooks.

#### <a id="q48"></a>48. **What are Render Props in React?**
- **Answer:** Render props refer to a technique for sharing code between components using a prop whose value is a function. A component with a render prop takes a function that returns a React element and calls it instead of implementing its own render logic.
      Example:
      ```javascript
      const DataFetcher = ({ render }) => {
        const [data, setData] = useState(null);

        useEffect(() => {
          fetch('https://api.example.com/data')
            .then(response => response.json())
            .then(data => setData(data));
        }, []);

        return render(data);
      };

      const MyComponent = () => (
        <DataFetcher render={(data) => (
          <div>{data ? data.name : 'Loading...'}</div>
        )} />
      );
      ```

#### <a id="q49"></a>49. **What are the different types of exports and imports?**
- **Answer:**
      - **Named Exports/Imports:**
        - Multiple exports per module, must be imported using the same name.
        - Example:
          ```javascript
          // file.js
          export const a = 10;
          export const b = 20;

          // anotherFile.js
          import { a, b } from './file';
          ```
      - **Default Exports/Imports:**
        - Only one default export per module, can be imported with any name.
        - Example:
          ```javascript
          // file.js
          const a = 10;
          export default a;

          // anotherFile.js
          import myValue from './file'; // Can be imported with any name
          ```
      - **Namespace Imports:**
        - Imports everything as an object.
        - Example:
          ```javascript
          import * as myModule from './file';
          ```

#### <a id="q50"></a>50. **What are the differences between `createElement` vs `cloneElement` in React?**
- **Answer:**
      - **`React.createElement`:** Used to create a new React element. It’s typically used by JSX under the hood to create elements. This function takes in a component type, props, and children as arguments and returns a React element.
      - **`React.cloneElement`:** Used to clone an existing React element and add or override its props and children. This is useful when you want to add props to children passed down from a parent component without altering the original component.
      - **Key Difference:** `createElement` generates a new element, whereas `cloneElement` creates a copy of an existing element with the option to modify its properties.

#### <a id="q51"></a>51. **When to use `useState` and `useReducer`?**
- **Answer:**
      - **`useState`:** Use `useState` when you have simple state management needs, such as toggling a boolean, updating a string, or maintaining a counter. It is straightforward to implement and is ideal for handling small, isolated pieces of state.
      - **`useReducer`:** Use `useReducer` when your state logic is complex or involves multiple sub-values that need to be managed together. It is also useful when the next state depends on the previous state or when state transitions involve more complex operations, similar to managing state with Redux.

#### <a id="q52"></a>52. **What is `flushSync` in React?**
- **Answer:** `flushSync` is a React function introduced to force React to flush all updates inside the provided callback synchronously. This ensures that changes are committed immediately instead of waiting for React to batch updates, which is useful in cases where you need to guarantee that the UI updates before performing another action, such as measuring the DOM.
    - Example:
      ```javascript
      import { flushSync } from 'react-dom';

      flushSync(() => {
        setState(newValue);
      });
      // You can safely read the updated DOM here
      ```

#### <a id="q53"></a>53. **What are protected routes in React?**
- **Answer:** Protected routes are routes that are accessible only to authenticated users. They are implemented by wrapping the route component in a conditional check that redirects unauthorized users to a login page or another route.
      - Example:
      ```javascript
      import { Redirect, Route } from 'react-router-dom';

      const ProtectedRoute = ({ component: Component, ...rest }) => (
        <Route
          {...rest}
          render={(props) =>
            isAuthenticated ? <Component {...props} /> : <Redirect to="/login" />
          }
        />
      );
      ```

#### <a id="q54"></a>54. **What is React Router's context menu?**
- **Answer:** React Router does not have a built-in context menu feature. However, you can create a custom context menu in your application and control its behavior using React Router by handling route changes, conditional rendering, and interactions.

#### <a id="q55"></a>55. **What are the lifecycle methods in Redux?**
- **Answer:** Redux doesn't have lifecycle methods like React components do, but there are key actions and middleware in the Redux flow:
      - **Action Dispatching:** Initiates a state change.
      - **Reducers:** Determine how the state should change in response to an action.
      - **Middleware:** Handles side effects, such as async operations.
      - **Store Subscription:** Allows components to listen for state changes.
      - **Re-rendering:** React components re-render based on the new state.

#### <a id="q56"></a>56. **What is the use of store in Redux?**
- **Answer:** The Redux store holds the entire state tree of your application. It serves as the single source of truth for the app's state, and the only way to change the state is by dispatching actions to the store. The store also allows components to subscribe to state changes.

#### <a id="q57"></a>57. **What is `useCallback` hook? How to implement it?**
- **Answer:** `useCallback` is a React hook that memoizes a callback function, preventing it from being recreated on every render unless its dependencies change. It is useful when passing callbacks to child components to avoid unnecessary re-renders.
      - Example:
      ```javascript
      const memoizedCallback = useCallback(() => {
        doSomething(a, b);
      }, [a, b]);
      ```

#### <a id="q58"></a>58. **What is `React.memo` and `useMemo`? Please explain it.**
- **Answer:**
      - **`React.memo`:** A higher-order component that wraps a functional component and memoizes its output, preventing unnecessary re-renders when props haven’t changed.
        - Example:
        ```javascript
        const MyComponent = React.memo((props) => {
          // render logic
        });
        ```
      - **`useMemo`:** A hook that memoizes a value, recomputing it only when its dependencies change. It’s used to optimize performance for expensive calculations.
        - Example:
        ```javascript
        const memoizedValue = useMemo(() => computeExpensiveValue(a, b), [a, b]);
        ```

#### <a id="q59"></a>59. **What is state management in React? Why use a state management library?**
- **Answer:** State management in React involves managing the state (data) that drives the UI. As an application grows, managing state across multiple components can become complex. A state management library (like Redux or MobX) helps by providing a centralized store for all the state, making it easier to manage, debug, and scale the application.

#### <a id="q60"></a>60. **Why use React over Angular? What are the advantages and disadvantages of these JavaScript frameworks?**
  - **Answer:**
      - **Advantages of React:**
        - **Flexibility:** React is a library, not a full framework, allowing more flexibility in how it is used.
        - **Component-Based Architecture:** Promotes reusable components, making it easier to maintain and scale applications.
        - **Virtual DOM:** Enhances performance by minimizing direct DOM manipulation.
        - **Ecosystem:** Rich ecosystem with many third-party libraries and tools.
      - **Disadvantages of React:**
        - **Learning Curve:** Requires understanding JSX, component lifecycle, and state management.
        - **Fragmented Ecosystem:** Since React focuses on UI, developers need to choose other libraries for routing, state management, etc.
      - **Advantages of Angular:**
        - **Complete Framework:** Angular provides everything needed out of the box, including routing, form validation, and state management.
        - **Two-Way Data Binding:** Synchronizes data between the model and view automatically.
        - **TypeScript:** Built with TypeScript, providing static typing and better tooling.
      - **Disadvantages of Angular:**
        - **Complexity:** Angular is a full-fledged framework, which can be more complex and rigid.
        - **Performance:** The use of two-way data binding can lead to performance issues in large applications.
        - **Steep Learning Curve:** Angular's extensive feature set and conventions require a significant learning investment.
