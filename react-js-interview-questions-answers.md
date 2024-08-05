Sure, here are some React.js interview questions and answers:

### Beginner Questions

1. **What is React?**
    - **Answer**: React is a JavaScript library for building user interfaces, specifically for single-page applications where data is dynamically changed without needing to reload the page. It allows developers to create large web applications that can update and render efficiently in response to data changes.

2. **What are the main features of React?**
    - **Answer**: The main features of React include:
      - **Virtual DOM**: React creates a virtual representation of the actual DOM to improve performance by minimizing direct DOM manipulations.
      - **JSX**: JSX is a syntax extension that allows HTML-like code to be written within JavaScript files.
      - **Components**: React encourages a component-based architecture, where the UI is broken down into reusable pieces.
      - **One-way Data Binding**: Data flows in one direction, making it easier to understand and debug.

3. **What is JSX?**
    - **Answer**: JSX stands for JavaScript XML. It is a syntax extension for JavaScript that looks similar to XML or HTML and is used to describe what the UI should look like. JSX makes it easier to write and add HTML in React.

4. **What are components in React?**
    - **Answer**: Components are the building blocks of a React application. They can be thought of as custom, reusable HTML elements that can be nested, managed, and handled independently. Components can be functional (stateless) or class-based (stateful).

5. **What is the difference between a functional component and a class component in React?**
    - **Answer**: 
      - **Functional Component**: A simple JavaScript function that takes props as an argument and returns React elements. With the introduction of hooks, functional components can now manage state and side effects.
      - **Class Component**: A more complex component that can hold and manage its own state and lifecycle methods. It is defined using an ES6 class that extends `React.Component`.

6. **What is the virtual DOM, and how does it work?**
    - **Answer**: The virtual DOM is a lightweight in-memory representation of the actual DOM. When the state of an object changes, React first updates the virtual DOM, then compares it with the previous virtual DOM using a process called "diffing." The minimal number of changes needed to update the real DOM are then applied, improving performance.

7. **What are props in React?**
    - **Answer**: Props (short for properties) are read-only attributes passed from a parent component to a child component. They allow data to flow from one component to another and are used to configure a component or pass data and event handlers.

8. **What is state in React?**
    - **Answer**: State is a built-in React object used to contain data or information about the component. Unlike props, state is mutable and managed within the component. State changes can trigger re-renders of the component.

9. **What are hooks in React?**
    - **Answer**: Hooks are special functions that let you use state and other React features in functional components. Some common hooks include `useState` for managing state, `useEffect` for side effects, and `useContext` for context API usage.

10. **What is the purpose of the `useState` hook?**
    - **Answer**: The `useState` hook is used to add state to functional components. It returns a stateful value and a function to update it. The initial state is passed as an argument to `useState`:
      ```javascript
      const [count, setCount] = useState(0);
      ```

### Intermediate Questions

11. **What is the `useEffect` hook, and how does it work?**
    - **Answer**: The `useEffect` hook allows you to perform side effects in functional components, such as data fetching, subscriptions, or manually changing the DOM. It takes a function as an argument that contains the side effect code and an optional array of dependencies:
      ```javascript
      useEffect(() => {
        // side effect code
      }, [dependencies]);
      ```

12. **What is the Context API in React?**
    - **Answer**: The Context API is a way to pass data through the component tree without having to pass props down manually at every level. It is used to manage global state in a React application:
      ```javascript
      const MyContext = React.createContext();
      ```

13. **How do you optimize performance in a React application?**
    - **Answer**: Performance in a React application can be optimized using several techniques, including:
      - **Using Pure Components**: React's `PureComponent` automatically implements a `shouldComponentUpdate` method to reduce unnecessary renders.
      - **Memoization**: Using `React.memo` for functional components and `useMemo` or `useCallback` hooks to memoize expensive calculations and prevent unnecessary re-renders.
      - **Code Splitting**: Dynamically importing components with React.lazy and Suspense to reduce initial load time.
      - **Virtualization**: Using libraries like react-window or react-virtualized to efficiently render large lists.

14. **What is React Router, and how do you use it?**
    - **Answer**: React Router is a standard library for routing in React applications. It enables navigation between different components, URL parameters, and nested routes. It is used by wrapping the application in a `Router` component and defining routes with `Route` components:
      ```javascript
      <Router>
        <Route path="/home" component={Home} />
        <Route path="/about" component={About} />
      </Router>
      ```

15. **What are higher-order components (HOCs) in React?**
    - **Answer**: Higher-order components (HOCs) are functions that take a component and return a new component with additional props or behavior. HOCs are used to share logic and functionalities between components:
      ```javascript
      const withLogging = WrappedComponent => {
        return props => {
          console.log("Component rendered with props:", props);
          return <WrappedComponent {...props} />;
        };
      };
      ```

16. **Explain the concept of "lifting state up" in React.**
    - **Answer**: "Lifting state up" refers to moving state to the closest common ancestor of components that need to share that state. This practice ensures that the state is managed in a single place and can be passed down as props to child components.

17. **What is the `useReducer` hook, and when would you use it?**
    - **Answer**: The `useReducer` hook is an alternative to `useState` for managing complex state logic. It is particularly useful when the state has multiple sub-values or when the next state depends on the previous state. It takes a reducer function and an initial state:
      ```javascript
      const [state, dispatch] = useReducer(reducer, initialState);
      ```

18. **What is the difference between controlled and uncontrolled components in React?**
    - **Answer**: 
      - **Controlled Components**: Components that get their state from props and inform their parent components of state changes via callbacks. The parent component manages the state.
      - **Uncontrolled Components**: Components that manage their own state internally using refs. The state is not controlled by the parent component.

19. **What is the significance of keys in React?**
    - **Answer**: Keys are unique identifiers used by React to identify which items have changed, been added, or removed in a list of elements. They help React optimize rendering by efficiently updating only the changed elements. Keys should be stable, predictable, and unique.

20. **How do you handle forms in React?**
    - **Answer**: Forms in React can be handled using controlled components, where form data is managed by the component's state, or uncontrolled components, where form data is managed by the DOM itself. Controlled components involve setting up state for each form field and updating it via event handlers:
      ```javascript
      const [value, setValue] = useState("");

      const handleChange = (event) => {
        setValue(event.target.value);
      };

      return <input type="text" value={value} onChange={handleChange} />;
      ```

### Advanced Questions

21. **What is the React Fiber architecture?**
    - **Answer**: React Fiber is a reimplementation of React's core algorithm for rendering and reconciliation. It improves the ability to interrupt and prioritize updates, handle animations, layout, and gestures better, and enhance the performance of complex applications.

22. **How does React handle reconciliation?**
    - **Answer**: React uses a diffing algorithm to compare the current virtual DOM with the previous one to determine the minimum number of changes needed to update the real DOM. This process, called reconciliation, helps optimize updates and maintain high performance.

Sure, here are more React.js interview questions and answers starting from number 24:

24. **What is the `useImperativeHandle` hook, and when would you use it?**
    - **Answer**: The `useImperativeHandle` hook customizes the instance value that is exposed when using `ref` in a parent component. It allows you to control child component instances and expose imperative methods to the parent:
      ```javascript
      const Child = React.forwardRef((props, ref) => {
        useImperativeHandle(ref, () => ({
          focus: () => {
            inputRef.current.focus();
          }
        }));
        const inputRef = useRef();
        return <input ref={inputRef} />;
      });

      const Parent = () => {
        const childRef = useRef();
        return (
          <div>
            <Child ref={childRef} />
            <button onClick={() => childRef.current.focus()}>Focus Input</button>
          </div>
        );
      };
      ```

25. **What is `React.memo`, and how does it work?**
    - **Answer**: `React.memo` is a higher-order component that memoizes the rendered output of a functional component. It prevents unnecessary re-renders by comparing the current props with the previous props and re-renders the component only if the props have changed:
      ```javascript
      const MyComponent = React.memo(({ value }) => {
        console.log("Rendering MyComponent");
        return <div>{value}</div>;
      });

      const Parent = () => {
        const [count, setCount] = useState(0);
        return (
          <div>
            <MyComponent value="Hello" />
            <button onClick={() => setCount(count + 1)}>Increment</button>
          </div>
        );
      };
      ```

26. **What is the `useCallback` hook, and when would you use it?**
    - **Answer**: The `useCallback` hook returns a memoized version of a callback function that only changes if one of the dependencies has changed. It is used to optimize performance by preventing the recreation of functions on every render:
      ```javascript
      const Parent = () => {
        const [count, setCount] = useState(0);
        const handleClick = useCallback(() => {
          console.log("Button clicked");
        }, []);
        return (
          <div>
            <button onClick={handleClick}>Click Me</button>
            <button onClick={() => setCount(count + 1)}>Increment</button>
          </div>
        );
      };
      ```

27. **What is the `useMemo` hook, and how does it differ from `useCallback`?**
    - **Answer**: The `useMemo` hook returns a memoized value, whereas `useCallback` returns a memoized function. `useMemo` is used to optimize expensive calculations by caching the result and recomputing it only when the dependencies change:
      ```javascript
      const Parent = () => {
        const [count, setCount] = useState(0);
        const memoizedValue = useMemo(() => {
          return count * 2;
        }, [count]);
        return (
          <div>
            <p>{memoizedValue}</p>
            <button onClick={() => setCount(count + 1)}>Increment</button>
          </div>
        );
      };
      ```

28. **What is server-side rendering (SSR) in React, and how does it differ from client-side rendering (CSR)?**
    - **Answer**: Server-side rendering (SSR) involves rendering React components on the server and sending the fully rendered HTML to the client. This approach improves performance and SEO. Client-side rendering (CSR) involves rendering components directly in the browser using JavaScript, which can be slower for initial load but provides a more interactive experience once loaded.

29. **How do you implement SSR in a React application?**
    - **Answer**: SSR can be implemented in a React application using frameworks like Next.js, which provide built-in support for SSR. You can also use libraries like ReactDOMServer to manually render components to HTML on the server:
      ```javascript
      import ReactDOMServer from 'react-dom/server';
      import App from './App';

      const express = require('express');
      const app = express();

      app.get('*', (req, res) => {
        const html = ReactDOMServer.renderToString(<App />);
        res.send(`
          <!DOCTYPE html>
          <html>
            <head>
              <title>My App</title>
            </head>
            <body>
              <div id="root">${html}</div>
              <script src="/bundle.js"></script>
            </body>
          </html>
        `);
      });

      app.listen(3000, () => {
        console.log('Server is listening on port 3000');
      });
      ```

30. **What is hydration in the context of SSR?**
    - **Answer**: Hydration is the process of attaching event listeners to the already-rendered HTML markup sent from the server during SSR. React reuses the server-rendered HTML and only adds the necessary event listeners and state to make the app fully interactive:
      ```javascript
      import ReactDOM from 'react-dom';
      import App from './App';

      ReactDOM.hydrate(<App />, document.getElementById('root'));
      ```

31. **What is React Suspense, and how does it work?**
    - **Answer**: React Suspense is a feature that allows you to display a fallback component while waiting for some asynchronous operation, such as data fetching or code splitting. It is used with `React.lazy` for lazy loading components:
      ```javascript
      const LazyComponent = React.lazy(() => import('./LazyComponent'));

      const Parent = () => (
        <Suspense fallback={<div>Loading...</div>}>
          <LazyComponent />
        </Suspense>
      );
      ```

32. **What are error boundaries in React?**
    - **Answer**: Error boundaries are components that catch JavaScript errors in their child component tree, log those errors, and display a fallback UI instead of crashing the entire application. Error boundaries are created using class components that implement `componentDidCatch` and `getDerivedStateFromError` lifecycle methods:
      ```javascript
      class ErrorBoundary extends React.Component {
        constructor(props) {
          super(props);
          this.state = { hasError: false };
        }

        static getDerivedStateFromError(error) {
          return { hasError: true };
        }

        componentDidCatch(error, info) {
          // Log error
        }

        render() {
          if (this.state.hasError) {
            return <h1>Something went wrong.</h1>;
          }

          return this.props.children;
        }
      }
      ```

33. **How do you handle state management in a React application?**
    - **Answer**: State management in a React application can be handled using various methods, including:
      - **Local state**: Managed within individual components using `useState` or `useReducer`.
      - **Context API**: For managing global state and providing it to deeply nested components.
      - **State management libraries**: Such as Redux, MobX, or Zustand, for more complex state management needs.

34. **What is Redux, and how does it work with React?**
    - **Answer**: Redux is a predictable state container for JavaScript applications. It centralizes the application's state in a single store and uses actions and reducers to manage state changes. React components can connect to the Redux store using the `react-redux` library:
      ```javascript
      import { createStore } from 'redux';
      import { Provider, useSelector, useDispatch } from 'react-redux';

      const initialState = { count: 0 };

      const reducer = (state = initialState, action) => {
        switch (action.type) {
          case 'INCREMENT':
            return { ...state, count: state.count + 1 };
          default:
            return state;
        }
      };

      const store = createStore(reducer);

      const App = () => (
        <Provider store={store}>
          <Counter />
        </Provider>
      );

      const Counter = () => {
        const count = useSelector(state => state.count);
        const dispatch = useDispatch();
        return (
          <div>
            <p>{count}</p>
            <button onClick={() => dispatch({ type: 'INCREMENT' })}>Increment</button>
          </div>
        );
      };
      ```

Sure, here are more React.js interview questions and answers starting from number 36:

### Advanced Questions

36. **What are custom hooks in React, and how do you create one?**
    - **Answer**: Custom hooks are functions that start with "use" and allow you to encapsulate and reuse stateful logic. They can call other hooks and can be used to abstract away repeated logic. Here's an example of a custom hook for fetching data:
      ```javascript
      const useFetch = (url) => {
        const [data, setData] = useState(null);
        const [loading, setLoading] = useState(true);
        const [error, setError] = useState(null);

        useEffect(() => {
          fetch(url)
            .then(response => {
              if (!response.ok) {
                throw new Error('Network response was not ok');
              }
              return response.json();
            })
            .then(data => {
              setData(data);
              setLoading(false);
            })
            .catch(error => {
              setError(error);
              setLoading(false);
            });
        }, [url]);

        return { data, loading, error };
      };
      ```

37. **How do you handle side effects in a React component?**
    - **Answer**: Side effects in React components are handled using the `useEffect` hook. This hook allows you to perform side effects in functional components, such as data fetching, subscriptions, or manually changing the DOM. The effect runs after every render by default, but you can control when it runs by specifying dependencies:
      ```javascript
      useEffect(() => {
        // Perform side effect
        return () => {
          // Cleanup side effect
        };
      }, [dependencies]);
      ```

38. **What is the difference between the `useEffect` and `useLayoutEffect` hooks?**
    - **Answer**: Both `useEffect` and `useLayoutEffect` hooks are used for side effects in functional components. The difference lies in when they are executed:
      - **`useEffect`**: Runs after the render is committed to the screen. It is non-blocking and allows the browser to paint before running the effect.
      - **`useLayoutEffect`**: Runs synchronously after all DOM mutations but before the browser has a chance to paint. It is useful for reading layout from the DOM and synchronously re-rendering.

39. **What is `React.lazy`, and how do you use it?**
    - **Answer**: `React.lazy` is a function that enables you to render a dynamic import as a regular component. It allows you to split your code into smaller chunks and load them on demand, improving the performance of your application. `React.lazy` is used in conjunction with `Suspense` to handle the loading state:
      ```javascript
      const LazyComponent = React.lazy(() => import('./LazyComponent'));

      const App = () => (
        <Suspense fallback={<div>Loading...</div>}>
          <LazyComponent />
        </Suspense>
      );
      ```

40. **What is the Context API, and how do you use it in React?**
    - **Answer**: The Context API is a way to pass data through the component tree without having to pass props down manually at every level. It is used to manage global state that needs to be accessed by multiple components. You create a context using `React.createContext`, provide the context value using a `Provider` component, and consume the context value using the `useContext` hook:
      ```javascript
      const MyContext = React.createContext();

      const MyProvider = ({ children }) => {
        const [value, setValue] = useState("Hello, World!");
        return (
          <MyContext.Provider value={{ value, setValue }}>
            {children}
          </MyContext.Provider>
        );
      };

      const MyComponent = () => {
        const { value } = useContext(MyContext);
        return <div>{value}</div>;
      };
      ```

41. **What is the difference between `Component` and `PureComponent` in React?**
    - **Answer**: `Component` and `PureComponent` are both base classes for creating class components in React. The main difference is how they handle `shouldComponentUpdate`:
      - **`Component`**: Always re-renders by default unless you define `shouldComponentUpdate` to optimize performance.
      - **`PureComponent`**: Implements a shallow comparison for `props` and `state` in `shouldComponentUpdate` to determine if the component should re-render, optimizing performance automatically for pure components.

42. **How do you optimize a React application for performance?**
    - **Answer**: There are several ways to optimize a React application for performance:
      - **Use `React.memo`**: To memoize functional components and prevent unnecessary re-renders.
      - **Use `useCallback` and `useMemo`**: To memoize functions and values respectively, avoiding unnecessary recalculations.
      - **Code splitting**: Using `React.lazy` and `Suspense` to split code and load it on demand.
      - **Virtualization**: Using libraries like `react-window` or `react-virtualized` to efficiently render large lists.
      - **Avoid anonymous functions in render**: Define functions outside the render method to prevent re-creation on every render.
      - **Optimize rendering lists**: Use keys properly and avoid index as keys if the list order can change.
      - **Use production build**: Ensure the application is running the optimized production build by running `npm run build`.

43. **What are higher-order components (HOCs) in React, and how do you create one?**
    - **Answer**: Higher-order components (HOCs) are functions that take a component and return a new component with additional props or behavior. They are used to share common logic across multiple components. HOCs are not part of the React API but are a pattern that emerges from React's compositional nature:
      ```javascript
      const withLogging = WrappedComponent => {
        return props => {
          console.log("Component rendered with props:", props);
          return <WrappedComponent {...props} />;
        };
      };

      const MyComponent = props => <div>{props.message}</div>;
      const MyComponentWithLogging = withLogging(MyComponent);
      ```

44. **What is the difference between `React.Component` and `React.PureComponent`?**
    - **Answer**: Both `React.Component` and `React.PureComponent` are base classes for creating class components, but they handle updates differently:
      - **`React.Component`**: By default, re-renders every time `setState` is called.
      - **`React.PureComponent`**: Implements `shouldComponentUpdate` with a shallow prop and state comparison to avoid unnecessary re-renders. This can improve performance for components that don't need to re-render on every state or prop change.

45. **How do you use the `useContext` hook in React?**
    - **Answer**: The `useContext` hook is used to access the value of a context in functional components. It simplifies consuming context values without needing to use a `Consumer` component:
      ```javascript
      const MyContext = React.createContext();

      const MyComponent = () => {
        const value = useContext(MyContext);
        return <div>{value}</div>;
      };

      const App = () => (
        <MyContext.Provider value="Hello, World!">
          <MyComponent />
        </MyContext.Provider>
      );
      ```

46. **What is the `useRef` hook, and how is it used?**
    - **Answer**: The `useRef` hook returns a mutable ref object whose `.current` property is initialized to the passed argument (initial value). It persists across renders and can be used to access DOM elements or store mutable values:
      ```javascript
      const MyComponent = () => {
        const inputRef = useRef();

        const focusInput = () => {
          inputRef.current.focus();
        };

        return (
          <div>
            <input ref={inputRef} />
            <button onClick={focusInput}>Focus Input</button>
          </div>
        );
      };
      ```

47. **How do you implement error boundaries in React?**
    - **Answer**: Error boundaries are implemented using class components that define `componentDidCatch` and `getDerivedStateFromError` lifecycle methods. They catch JavaScript errors in their child component tree, log those errors, and display a fallback UI:
      ```javascript
      class ErrorBoundary extends React.Component {
        constructor(props) {
          super(props);
          this.state = { hasError: false };
        }

        static getDerivedStateFromError(error) {
          return { hasError: true };
        }

        componentDidCatch(error, errorInfo) {
          // Log error to an error reporting service
        }

        render() {
          if (this.state.hasError) {
            return <h1>Something went wrong.</h1>;
          }

          return this.props.children;
        }
      }
      ```

Sure, here are more React.js interview questions and answers starting from number 48:

48. **What is the difference between `useState` and `useReducer` hooks?**
    - **Answer**: Both `useState` and `useReducer` are hooks for managing state in functional components, but they are used in different scenarios:
      - **`useState`**: Suitable for simple state management with a single state variable.
      - **`useReducer`**: Suitable for complex state logic involving multiple state variables or when the next state depends on the previous state. It takes a reducer function and an initial state:
        ```javascript
        const initialState = { count: 0 };

        function reducer(state, action) {
          switch (action.type) {
            case 'increment':
              return { count: state.count + 1 };
            case 'decrement':
              return { count: state.count - 1 };
            default:
              throw new Error();
          }
        }

        const Counter = () => {
          const [state, dispatch] = useReducer(reducer, initialState);
          return (
            <div>
              <p>{state.count}</p>
              <button onClick={() => dispatch({ type: 'increment' })}>Increment</button>
              <button onClick={() => dispatch({ type: 'decrement' })}>Decrement</button>
            </div>
          );
        };
        ```

49. **How do you handle forms in React?**
    - **Answer**: Forms in React are handled using controlled components where the form data is handled by the React component's state. You can use the `useState` hook to manage form input values and handle form submission:
      ```javascript
      const MyForm = () => {
        const [formData, setFormData] = useState({ name: '', email: '' });

        const handleChange = (e) => {
          const { name, value } = e.target;
          setFormData((prevFormData) => ({
            ...prevFormData,
            [name]: value,
          }));
        };

        const handleSubmit = (e) => {
          e.preventDefault();
          console.log('Form submitted:', formData);
        };

        return (
          <form onSubmit={handleSubmit}>
            <input
              type="text"
              name="name"
              value={formData.name}
              onChange={handleChange}
            />
            <input
              type="email"
              name="email"
              value={formData.email}
              onChange={handleChange}
            />
            <button type="submit">Submit</button>
          </form>
        );
      };
      ```

50. **What are React portals, and how do you use them?**
    - **Answer**: React portals provide a way to render children into a DOM node that exists outside the DOM hierarchy of the parent component. They are useful for rendering components like modals, tooltips, or dropdowns:
      ```javascript
      import ReactDOM from 'react-dom';

      const Modal = ({ isOpen, children }) => {
        if (!isOpen) return null;
        return ReactDOM.createPortal(
          <div className="modal">{children}</div>,
          document.getElementById('modal-root')
        );
      };

      const App = () => {
        const [isOpen, setIsOpen] = useState(false);

        return (
          <div>
            <button onClick={() => setIsOpen(true)}>Open Modal</button>
            <Modal isOpen={isOpen}>
              <h1>Modal Content</h1>
              <button onClick={() => setIsOpen(false)}>Close Modal</button>
            </Modal>
          </div>
        );
      };
      ```

51. **What is the `useDebugValue` hook, and how do you use it?**
    - **Answer**: The `useDebugValue` hook is used to display a label for custom hooks in React DevTools. It helps to debug custom hooks by providing a custom label:
      ```javascript
      const useCustomHook = (value) => {
        useDebugValue(value ? 'Enabled' : 'Disabled');
        // Custom hook logic
      };

      const MyComponent = () => {
        const customValue = useCustomHook(true);
        return <div>{customValue}</div>;
      };
      ```

52. **How do you create a context with a default value in React?**
    - **Answer**: A context with a default value is created by passing the default value to `React.createContext`. This default value will be used if a component consuming the context does not have a matching `Provider` above it in the tree:
      ```javascript
      const MyContext = React.createContext('default value');

      const MyComponent = () => {
        const value = useContext(MyContext);
        return <div>{value}</div>;
      };

      const App = () => (
        <MyComponent />
      );
      ```

53. **How do you manage state in a React application with complex state transitions?**
    - **Answer**: For managing complex state transitions, `useReducer` is preferred over `useState`. `useReducer` provides a more predictable and testable way to handle state transitions using actions and a reducer function:
      ```javascript
      const initialState = { count: 0 };

      function reducer(state, action) {
        switch (action.type) {
          case 'increment':
            return { count: state.count + 1 };
          case 'decrement':
            return { count: state.count - 1 };
          default:
            throw new Error();
        }
      }

      const Counter = () => {
        const [state, dispatch] = useReducer(reducer, initialState);
        return (
          <div>
            <p>{state.count}</p>
            <button onClick={() => dispatch({ type: 'increment' })}>Increment</button>
            <button onClick={() => dispatch({ type: 'decrement' })}>Decrement</button>
          </div>
        );
      };
      ```

54. **What are controlled and uncontrolled components in React?**
    - **Answer**: 
      - **Controlled components**: Form inputs that derive their value from React state. The state is updated via event handlers, making the input a "controlled" element:
        ```javascript
        const MyComponent = () => {
          const [value, setValue] = useState('');

          const handleChange = (e) => {
            setValue(e.target.value);
          };

          return (
            <input type="text" value={value} onChange={handleChange} />
          );
        };
        ```
      - **Uncontrolled components**: Form inputs that store their own state internally. You can access the input value using refs:
        ```javascript
        const MyComponent = () => {
          const inputRef = useRef();

          const handleSubmit = (e) => {
            e.preventDefault();
            console.log(inputRef.current.value);
          };

          return (
            <form onSubmit={handleSubmit}>
              <input type="text" ref={inputRef} />
              <button type="submit">Submit</button>
            </form>
          );
        };
        ```

55. **What is the `useImperativeHandle` hook, and when would you use it?**
    - **Answer**: The `useImperativeHandle` hook customizes the instance value that is exposed when using `ref` in a parent component. It allows you to control child component instances and expose imperative methods to the parent:
      ```javascript
      const Child = React.forwardRef((props, ref) => {
        useImperativeHandle(ref, () => ({
          focus: () => {
            inputRef.current.focus();
          }
        }));
        const inputRef = useRef();
        return <input ref={inputRef} />;
      });

      const Parent = () => {
        const childRef = useRef();
        return (
          <div>
            <Child ref={childRef} />
            <button onClick={() => childRef.current.focus()}>Focus Input</button>
          </div>
        );
      };
      ```

56. **How do you handle routing in a React application?**
    - **Answer**: Routing in a React application is typically handled using a library like React Router. React Router provides components like `BrowserRouter`, `Route`, `Switch`, and `Link` to define and manage routes:
      ```javascript
      import { BrowserRouter as Router, Route, Switch, Link } from 'react-router-dom';

      const Home = () => <h2>Home</h2>;
      const About = () => <h2>About</h2>;

      const App = () => (
        <Router>
          <nav>
            <ul>
              <li><Link to="/">Home</Link></li>
              <li><Link to="/about">About</Link></li>
            </ul>
          </nav>
          <Switch>
            <Route exact path="/" component={Home} />
            <Route path="/about" component={About} />
          </Switch>
        </Router>
      );
      ```

Sure, here are more React.js interview questions and answers starting from number 57:

### Advanced Questions (Continued)

57. **How do you optimize React component rendering?**
    - **Answer**: There are several strategies to optimize React component rendering:
      - **Use `React.memo`**: To prevent unnecessary re-renders by memoizing functional components.
      - **Use `useCallback` and `useMemo`**: To memoize functions and values, preventing them from being recreated on every render.
      - **Avoid anonymous functions in render**: Define functions outside the render method.
      - **Use keys properly in lists**: Ensure unique and stable keys for list items.
      - **Code splitting**: Split code into smaller bundles and load them on demand using `React.lazy` and `Suspense`.
      - **Virtualization**: Render only the visible portion of large lists using libraries like `react-window` or `react-virtualized`.
      - **Avoid unnecessary state updates**: Ensure state updates only when necessary.

58. **What are React Fragments and how are they useful?**
    - **Answer**: React Fragments allow you to group multiple elements without adding extra nodes to the DOM. This is useful for returning multiple elements from a component without wrapping them in a parent element:
      ```javascript
      const MyComponent = () => (
        <React.Fragment>
          <h1>Title</h1>
          <p>Content</p>
        </React.Fragment>
      );
      // Short syntax
      const MyComponent = () => (
        <>
          <h1>Title</h1>
          <p>Content</p>
        </>
      );
      ```

59. **What is the difference between `useEffect` and `useLayoutEffect`?**
    - **Answer**: Both `useEffect` and `useLayoutEffect` are hooks for performing side effects in functional components, but they run at different times:
      - **`useEffect`**: Runs after the render is committed to the screen. It's asynchronous and non-blocking, which means it does not block the browser paint.
      - **`useLayoutEffect`**: Runs synchronously after all DOM mutations but before the browser has a chance to paint. It's useful for reading layout from the DOM and synchronously re-rendering.

60. **How do you manage global state in a React application?**
    - **Answer**: Global state in a React application can be managed using several approaches:
      - **Context API**: Using `React.createContext` and `useContext` to share state across components.
      - **State management libraries**: Using libraries like Redux, MobX, Zustand, or Recoil for more complex state management needs.
      - **Custom hooks**: Creating custom hooks to encapsulate global state logic.

61. **What are render props in React?**
    - **Answer**: Render props is a technique for sharing code between React components using a prop whose value is a function. This function returns a React element:
      ```javascript
      const MyComponent = ({ render }) => (
        <div>
          {render()}
        </div>
      );

      const App = () => (
        <MyComponent render={() => <h1>Hello, World!</h1>} />
      );
      ```

62. **How do you handle conditional rendering in React?**
    - **Answer**: Conditional rendering in React can be handled using JavaScript conditional operators:
      - **Using if-else**:
        ```javascript
        const MyComponent = ({ isLoggedIn }) => {
          if (isLoggedIn) {
            return <h1>Welcome back!</h1>;
          } else {
            return <h1>Please sign up.</h1>;
          }
        };
        ```
      - **Using ternary operator**:
        ```javascript
        const MyComponent = ({ isLoggedIn }) => (
          isLoggedIn ? <h1>Welcome back!</h1> : <h1>Please sign up.</h1>
        );
        ```
      - **Using logical && operator**:
        ```javascript
        const MyComponent = ({ showWarning }) => (
          <>
            {showWarning && <h1>Warning!</h1>}
          </>
        );
        ```

63. **How do you handle errors in a React component?**
    - **Answer**: Errors in React components can be handled using error boundaries. Error boundaries are React components that catch JavaScript errors in their child component tree, log those errors, and display a fallback UI:
      ```javascript
      class ErrorBoundary extends React.Component {
        constructor(props) {
          super(props);
          this.state = { hasError: false };
        }

        static getDerivedStateFromError(error) {
          return { hasError: true };
        }

        componentDidCatch(error, errorInfo) {
          // Log the error
        }

        render() {
          if (this.state.hasError) {
            return <h1>Something went wrong.</h1>;
          }

          return this.props.children;
        }
      }
      ```

64. **What are synthetic events in React?**
    - **Answer**: Synthetic events are React's cross-browser wrapper around the browser's native events. They work identically across all browsers and provide a consistent interface for handling events. Synthetic events are optimized for performance and are pooled, meaning the event object is reused across multiple events to reduce memory overhead.

65. **How do you handle side effects in a React component?**
    - **Answer**: Side effects in React components are handled using the `useEffect` hook. This hook allows you to perform side effects like data fetching, subscriptions, and manually changing the DOM. The `useEffect` hook runs after every render by default, but you can control when it runs by specifying dependencies:
      ```javascript
      useEffect(() => {
        // Perform side effect
        return () => {
          // Cleanup side effect
        };
      }, [dependencies]);
      ```

66. **What is reconciliation in React?**
    - **Answer**: Reconciliation is the process through which React updates the DOM to match the virtual DOM. React uses a diffing algorithm to compare the previous and current virtual DOM trees and determines the minimum number of changes required to update the actual DOM. This process optimizes performance by only updating parts of the DOM that have changed.

67. **How do you handle asynchronous operations in React?**
    - **Answer**: Asynchronous operations in React can be handled using:
      - **`useEffect` hook**: For side effects like data fetching. You can use async/await within `useEffect`:
        ```javascript
        useEffect(() => {
          const fetchData = async () => {
            const response = await fetch('/api/data');
            const data = await response.json();
            setData(data);
          };
          fetchData();
        }, []);
        ```
      - **Libraries like `axios` or `fetch`**: For making HTTP requests.

68. **How do you use React's Profiler API?**
    - **Answer**: React's Profiler API is used to measure the performance of React applications. It can be used to identify performance bottlenecks and optimize rendering performance. You wrap components with the `Profiler` component and provide an `onRender` callback:
      ```javascript
      const onRenderCallback = (
        id, // the "id" prop of the Profiler tree that has just committed
        phase, // either "mount" (if the tree just mounted) or "update" (if it re-rendered)
        actualDuration, // time spent rendering the committed update
        baseDuration, // estimated time to render the entire subtree without memoization
        startTime, // when React began rendering this update
        commitTime, // when React committed this update
        interactions // the Set of interactions belonging to this update
      ) => {
        console.log({ id, phase, actualDuration, baseDuration, startTime, commitTime, interactions });
      };

      const App = () => (
        <Profiler id="App" onRender={onRenderCallback}>
          <MyComponent />
        </Profiler>
      );
      ```

69. **What is the difference between `React.createElement` and JSX?**
    - **Answer**: `React.createElement` is a function that creates a React element object, while JSX is a syntax extension that allows you to write HTML-like code within JavaScript. JSX is syntactic sugar for `React.createElement` calls. The following two examples are equivalent:
      ```javascript
      const element = React.createElement('div', { className: 'my-class' }, 'Hello, World!');
      ```
      ```jsx
      const element = <div className="my-class">Hello, World!</div>;
      ```

70. **How do you handle user input in React?**
    - **Answer**: User input in React is typically handled using controlled components. The form input values are stored in the component's state and updated via event handlers:
      ```javascript
      const MyComponent = () => {
        const [value, setValue] = useState('');

        const handleChange = (e) => {
          setValue(e.target.value);
        };

        return (
          <input type="text" value={value} onChange={handleChange} />
        );
      };
      ```

Sure, here are more React.js interview questions and answers starting from number 71:

### Advanced Questions (Continued)

71. **How do you implement server-side rendering (SSR) in a React application?**
    - **Answer**: Server-side rendering (SSR) in a React application can be implemented using frameworks like Next.js. SSR allows the server to pre-render the initial HTML of the page, improving performance and SEO. Here's a simple example using Next.js:
      ```javascript
      // pages/index.js
      const Home = ({ data }) => (
        <div>
          <h1>Server-Side Rendered Data</h1>
          <p>{data.message}</p>
        </div>
      );

      export async function getServerSideProps() {
        // Fetch data from an API or perform other server-side logic
        const res = await fetch('https://api.example.com/data');
        const data = await res.json();

        return { props: { data } };
      }

      export default Home;
      ```

72. **What is the purpose of `React.StrictMode`?**
    - **Answer**: `React.StrictMode` is a wrapper component that helps to identify potential problems in an application. It activates additional checks and warnings for its descendants. It's useful during development to highlight issues that might not be immediately apparent:
      ```javascript
      const App = () => (
        <React.StrictMode>
          <MyComponent />
        </React.StrictMode>
      );
      ```

73. **How do you handle CSS in React applications?**
    - **Answer**: CSS in React applications can be handled in several ways:
      - **CSS Modules**: Scoped CSS to the component, preventing global namespace collisions.
        ```javascript
        import styles from './MyComponent.module.css';

        const MyComponent = () => (
          <div className={styles.myClass}>
            My styled component
          </div>
        );
        ```
      - **Styled-components**: A library for writing CSS in JS using tagged template literals.
        ```javascript
        import styled from 'styled-components';

        const Button = styled.button`
          background: palevioletred;
          color: white;
        `;

        const MyComponent = () => <Button>Click me</Button>;
        ```
      - **Inline styles**: Using the `style` attribute directly on elements.
        ```javascript
        const MyComponent = () => (
          <div style={{ color: 'blue', fontSize: '20px' }}>
            Inline styled component
          </div>
        );
        ```
      - **CSS-in-JS libraries**: Using libraries like Emotion or JSS.

74. **What is React.lazy and how do you use it?**
    - **Answer**: `React.lazy` is a function that lets you load a component dynamically via code splitting. It allows components to be loaded only when they are needed, reducing the initial load time. It works with `React.Suspense` to show a fallback while the component is loading:
      ```javascript
      const OtherComponent = React.lazy(() => import('./OtherComponent'));

      const MyComponent = () => (
        <React.Suspense fallback={<div>Loading...</div>}>
          <OtherComponent />
        </React.Suspense>
      );
      ```

75. **How do you test React components?**
    - **Answer**: React components can be tested using various tools and libraries:
      - **Jest**: A JavaScript testing framework for writing and running tests.
      - **React Testing Library**: A library for testing React components with a focus on accessibility and user interactions.
        ```javascript
        import { render, screen } from '@testing-library/react';
        import MyComponent from './MyComponent';

        test('renders component', () => {
          render(<MyComponent />);
          const linkElement = screen.getByText(/MyComponent/i);
          expect(linkElement).toBeInTheDocument();
        });
        ```
      - **Enzyme**: A testing utility for React that allows shallow rendering, full DOM rendering, and static rendering.

76. **What are Higher-Order Components (HOCs) in React?**
    - **Answer**: Higher-Order Components (HOCs) are functions that take a component and return a new component. They are used to add additional functionality to existing components without modifying them directly:
      ```javascript
      const withLogging = (WrappedComponent) => {
        return (props) => {
          console.log('Component props:', props);
          return <WrappedComponent {...props} />;
        };
      };

      const MyComponent = (props) => <div>{props.text}</div>;

      const EnhancedComponent = withLogging(MyComponent);
      ```

77. **How do you manage side effects in a large React application?**
    - **Answer**: Side effects in large React applications can be managed using:
      - **useEffect**: For side effects within functional components.
      - **Redux Thunk**: For managing side effects in a Redux-based application.
      - **Redux Saga**: For managing more complex side effects using generator functions.

78. **What is the Context API and how do you use it?**
    - **Answer**: The Context API is a way to pass data through the component tree without having to pass props down manually at every level. It is useful for global state management:
      ```javascript
      const MyContext = React.createContext();

      const MyProvider = ({ children }) => {
        const [state, setState] = useState('Hello, World!');

        return (
          <MyContext.Provider value={{ state, setState }}>
            {children}
          </MyContext.Provider>
        );
      };

      const MyComponent = () => {
        const { state } = useContext(MyContext);
        return <div>{state}</div>;
      };

      const App = () => (
        <MyProvider>
          <MyComponent />
        </MyProvider>
      );
      ```

79. **What is the `useRef` hook and how do you use it?**
    - **Answer**: The `useRef` hook returns a mutable ref object whose `.current` property is initialized to the passed argument. It is used to persist values across renders without causing re-renders and to access DOM elements directly:
      ```javascript
      const MyComponent = () => {
        const inputRef = useRef(null);

        const focusInput = () => {
          inputRef.current.focus();
        };

        return (
          <div>
            <input ref={inputRef} type="text" />
            <button onClick={focusInput}>Focus Input</button>
          </div>
        );
      };
      ```

80. **How do you implement internationalization (i18n) in a React application?**
    - **Answer**: Internationalization (i18n) in a React application can be implemented using libraries like `react-i18next`. It provides components and hooks to translate text and manage language resources:
      ```javascript
      import { useTranslation } from 'react-i18next';

      const MyComponent = () => {
        const { t, i18n } = useTranslation();

        const changeLanguage = (language) => {
          i18n.changeLanguage(language);
        };

        return (
          <div>
            <p>{t('Welcome')}</p>
            <button onClick={() => changeLanguage('en')}>English</button>
            <button onClick={() => changeLanguage('fr')}>French</button>
          </div>
        );
      };
      ```

81. **What is the difference between `React.Component` and `React.PureComponent`?**
    - **Answer**: `React.Component` is the base class for creating class components. `React.PureComponent` is a subclass of `React.Component` that implements `shouldComponentUpdate` with a shallow prop and state comparison. This means `React.PureComponent` automatically prevents re-renders if the props and state have not changed shallowly.

82. **How do you handle authentication in a React application?**
    - **Answer**: Authentication in a React application can be handled using several approaches:
      - **Client-side authentication**: Storing tokens in local storage or cookies and checking for their presence.
      - **Server-side authentication**: Using frameworks like Next.js to handle authentication on the server.
      - **Third-party services**: Using services like Firebase Authentication or Auth0.

      Example using JWT tokens:
      ```javascript
      const login = async (username, password) => {
        const response = await fetch('/api/login', {
          method: 'POST',
          headers: { 'Content-Type': 'application/json' },
          body: JSON.stringify({ username, password }),
        });

        const data = await response.json();
        localStorage.setItem('token', data.token);
      };

      const isAuthenticated = () => {
        const token = localStorage.getItem('token');
        return !!token;
      };
      ```

83. **How do you implement lazy loading of images in React?**
    - **Answer**: Lazy loading of images in React can be implemented using the `loading` attribute on the `img` tag or using libraries like `react-lazyload`:
      ```javascript
      // Using the loading attribute
      const MyComponent = () => (
        <img src="image.jpg" alt="Lazy Loaded" loading="lazy" />
      );

      // Using react-lazyload
      import LazyLoad from 'react-lazyload';

      const MyComponent = () => (
        <LazyLoad height={200} offset={100}>
          <img src="image.jpg" alt="Lazy Loaded" />
        </LazyLoad>
      );
      ```

Sure, here are more React.js interview questions and answers starting from number 84:

### Advanced Questions (Continued)

84. **What are React hooks and why were they introduced?**
    - **Answer**: React hooks are functions that let you use state and other React features in functional components. They were introduced in React 16.8 to simplify code, reduce the need for class components, and share logic across components. The primary hooks include `useState`, `useEffect`, `useContext`, `useReducer`, and `useRef`. Hooks address issues like complex lifecycle methods, reuse of stateful logic, and bloated component hierarchies.

85. **What is `useReducer` and when would you use it?**
    - **Answer**: `useReducer` is a hook that is used for state management in situations where `useState` becomes unwieldy. It's an alternative to `useState` for managing more complex state logic, particularly when the state has multiple sub-values or when the next state depends on the previous one:
      ```javascript
      const initialState = { count: 0 };

      function reducer(state, action) {
        switch (action.type) {
          case 'increment':
            return { count: state.count + 1 };
          case 'decrement':
            return { count: state.count - 1 };
          default:
            throw new Error();
        }
      }

      const Counter = () => {
        const [state, dispatch] = useReducer(reducer, initialState);

        return (
          <div>
            <p>Count: {state.count}</p>
            <button onClick={() => dispatch({ type: 'increment' })}>+</button>
            <button onClick={() => dispatch({ type: 'decrement' })}>-</button>
          </div>
        );
      };
      ```

86. **What is `useMemo` and how do you use it?**
    - **Answer**: `useMemo` is a hook that memoizes a computed value, recomputing it only when its dependencies change. It's used to optimize performance by preventing expensive calculations on every render:
      ```javascript
      const MyComponent = ({ items }) => {
        const expensiveCalculation = (items) => {
          // Some expensive calculation
          return items.reduce((a, b) => a + b, 0);
        };

        const total = useMemo(() => expensiveCalculation(items), [items]);

        return <div>Total: {total}</div>;
      };
      ```

87. **What are custom hooks and how do you create one?**
    - **Answer**: Custom hooks are functions that encapsulate reusable logic using React hooks. They allow you to extract and share logic between components without duplicating code:
      ```javascript
      const useFetch = (url) => {
        const [data, setData] = useState(null);
        const [loading, setLoading] = useState(true);

        useEffect(() => {
          fetch(url)
            .then((response) => response.json())
            .then((data) => {
              setData(data);
              setLoading(false);
            });
        }, [url]);

        return { data, loading };
      };

      const MyComponent = () => {
        const { data, loading } = useFetch('https://api.example.com/data');

        if (loading) return <div>Loading...</div>;

        return <div>Data: {JSON.stringify(data)}</div>;
      };
      ```

88. **What are render props and how do you use them?**
    - **Answer**: Render props is a pattern for sharing code between React components using a prop whose value is a function. This function returns a React element, allowing you to render dynamic content:
      ```javascript
      const DataProvider = ({ render }) => {
        const [data, setData] = useState(null);

        useEffect(() => {
          fetch('https://api.example.com/data')
            .then((response) => response.json())
            .then((data) => setData(data));
        }, []);

        return render(data);
      };

      const MyComponent = () => (
        <DataProvider render={(data) => <div>Data: {JSON.stringify(data)}</div>} />
      );
      ```

89. **How do you manage forms in React?**
    - **Answer**: Forms in React can be managed using controlled components, uncontrolled components, or libraries like Formik and React Hook Form:
      - **Controlled Components**: Form inputs are controlled by React state.
        ```javascript
        const MyForm = () => {
          const [value, setValue] = useState('');

          const handleChange = (e) => {
            setValue(e.target.value);
          };

          const handleSubmit = (e) => {
            e.preventDefault();
            console.log(value);
          };

          return (
            <form onSubmit={handleSubmit}>
              <input type="text" value={value} onChange={handleChange} />
              <button type="submit">Submit</button>
            </form>
          );
        };
        ```
      - **Uncontrolled Components**: Using refs to access form values.
        ```javascript
        const MyForm = () => {
          const inputRef = useRef(null);

          const handleSubmit = (e) => {
            e.preventDefault();
            console.log(inputRef.current.value);
          };

          return (
            <form onSubmit={handleSubmit}>
              <input type="text" ref={inputRef} />
              <button type="submit">Submit</button>
            </form>
          );
        };
        ```

90. **How do you optimize performance in a React application?**
    - **Answer**: Performance in a React application can be optimized using various techniques:
      - **Code splitting**: Using `React.lazy` and `Suspense` to load components on demand.
      - **Memoization**: Using `React.memo`, `useMemo`, and `useCallback` to prevent unnecessary re-renders.
      - **Virtualization**: Using libraries like `react-window` or `react-virtualized` for rendering large lists efficiently.
      - **Avoid anonymous functions in render**: Define functions outside the render method.
      - **Use production build**: Ensure the app is running in production mode for optimizations.
      - **Optimize images and assets**: Use optimized images and static assets.
      - **Avoid unnecessary state updates**: Ensure state updates only when necessary.

91. **What are the limitations of React?**
    - **Answer**: While React is powerful, it has some limitations:
      - **Learning curve**: Requires learning JSX, state management, and new JavaScript concepts.
      - **Boilerplate code**: Can require a lot of boilerplate, especially for larger applications.
      - **JSX complexity**: Mixing HTML and JavaScript in JSX can be challenging for some developers.
      - **Performance issues**: Improper use of state and props can lead to performance issues.
      - **SEO limitations**: Without SSR, React applications can have SEO limitations since content is rendered on the client side.

92. **What are controlled and uncontrolled components in React?**
    - **Answer**: Controlled and uncontrolled components are two ways of handling form inputs in React:
      - **Controlled Components**: Form inputs are controlled by React state, with the value being set through props and changes being handled by event handlers.
        ```javascript
        const MyForm = () => {
          const [value, setValue] = useState('');

          const handleChange = (e) => {
            setValue(e.target.value);
          };

          return (
            <input type="text" value={value} onChange={handleChange} />
          );
        };
        ```
      - **Uncontrolled Components**: Form inputs manage their own state internally, and refs are used to access their current values.
        ```javascript
        const MyForm = () => {
          const inputRef = useRef(null);

          const handleSubmit = (e) => {
            e.preventDefault();
            console.log(inputRef.current.value);
          };

          return (
            <form onSubmit={handleSubmit}>
              <input type="text" ref={inputRef} />
              <button type="submit">Submit</button>
            </form>
          );
        };
        ```

93. **How do you handle side effects in functional components?**
    - **Answer**: Side effects in functional components are handled using the `useEffect` hook. It allows you to perform side effects after rendering and to clean up after the component unmounts or when dependencies change:
      ```javascript
      useEffect(() => {
        // Perform side effect
        const fetchData = async () => {
          const response = await fetch('/api/data');
          const data = await response.json();
          setData(data);
        };
        fetchData();

        // Cleanup side effect
        return () => {
          // Cleanup code
        };
      }, [dependencies]);
      ```

94. **What is reconciliation and how does React handle it?**
    - **Answer**: Reconciliation is the process by which React updates the DOM to match the virtual DOM. React uses a diffing algorithm to compare the previous and current virtual DOM trees and determine the minimum number of changes required to update the actual DOM. This process optimizes performance by only updating parts of the DOM that have changed.

95. **What is the use of `React.PureComponent`?**
    - **Answer**: `React.PureComponent` is a base class for creating class components that implements `shouldComponentUpdate` with a shallow prop and state comparison. This prevents unnecessary re-renders if the props and state have not changed shallowly. It is useful for optimizing performance in components where re-rendering is expensive.

Sure, here are more React.js interview questions and answers starting from number 96:

96. **How do you create a higher-order component (HOC) in React?**
    - **Answer**: A higher-order component (HOC) is a function that takes a component and returns a new component with added functionality. It is used for code reuse, logic, and bootstrap abstraction:
      ```javascript
      const withExtraProps = (WrappedComponent) => {
        return (props) => {
          const newProps = { extraProp: 'This is an extra prop!' };
          return <WrappedComponent {...props} {...newProps} />;
        };
      };

      const MyComponent = (props) => (
        <div>
          <p>{props.extraProp}</p>
          <p>{props.otherProp}</p>
        </div>
      );

      const EnhancedComponent = withExtraProps(MyComponent);
      ```

97. **What is React Fiber and why was it introduced?**
    - **Answer**: React Fiber is a complete rewrite of React's reconciliation algorithm. It was introduced in React 16 to improve the performance and flexibility of React applications. Fiber allows React to break down rendering work into smaller chunks and spread it out over multiple frames. This enables React to pause and resume work, prioritize updates, and handle animations and layout updates more efficiently.

98. **What is the use of `React.Fragment` and how do you use it?**
    - **Answer**: `React.Fragment` allows you to group multiple elements without adding extra nodes to the DOM. It helps in avoiding unnecessary wrapper elements:
      ```javascript
      const MyComponent = () => (
        <React.Fragment>
          <h1>Title</h1>
          <p>Description</p>
        </React.Fragment>
      );

      // Short syntax
      const MyComponent = () => (
        <>
          <h1>Title</h1>
          <p>Description</p>
        </>
      );
      ```

99. **What are controlled components in React?**
    - **Answer**: Controlled components are form elements whose values are controlled by React state. The value is set via props, and changes are handled by event handlers:
      ```javascript
      const MyForm = () => {
        const [value, setValue] = useState('');

        const handleChange = (e) => {
          setValue(e.target.value);
        };

        return (
          <input type="text" value={value} onChange={handleChange} />
        );
      };
      ```

100. **What are uncontrolled components in React?**
    - **Answer**: Uncontrolled components are form elements that manage their own state internally. Refs are used to access their current values:
      ```javascript
      const MyForm = () => {
        const inputRef = useRef(null);

        const handleSubmit = (e) => {
          e.preventDefault();
          console.log(inputRef.current.value);
        };

        return (
          <form onSubmit={handleSubmit}>
            <input type="text" ref={inputRef} />
            <button type="submit">Submit</button>
          </form>
        );
      };
      ```

101. **What is the difference between `useEffect` and `useLayoutEffect`?**
    - **Answer**: Both `useEffect` and `useLayoutEffect` are hooks for performing side effects in functional components, but they have different timing:
      - **useEffect**: Runs after the render is committed to the screen. It's suitable for most side effects like data fetching, subscriptions, or manually changing the DOM.
        ```javascript
        useEffect(() => {
          // Side effect logic
        }, [dependencies]);
        ```
      - **useLayoutEffect**: Runs synchronously after all DOM mutations but before the browser has painted. It is useful for reading layout from the DOM and synchronously re-rendering.
        ```javascript
        useLayoutEffect(() => {
          // Synchronous side effect logic
        }, [dependencies]);
        ```

102. **What is the `useImperativeHandle` hook and when would you use it?**
    - **Answer**: `useImperativeHandle` is a hook that allows you to customize the instance value that is exposed when using `ref` in parent components. It is used to control imperative methods of a child component from a parent component:
      ```javascript
      const MyComponent = React.forwardRef((props, ref) => {
        useImperativeHandle(ref, () => ({
          customMethod() {
            console.log('Custom method called');
          }
        }));

        return <div>My Component</div>;
      });

      const ParentComponent = () => {
        const ref = useRef(null);

        const handleClick = () => {
          ref.current.customMethod();
        };

        return (
          <div>
            <MyComponent ref={ref} />
            <button onClick={handleClick}>Call Custom Method</button>
          </div>
        );
      };
      ```

103. **What are Portals in React and how do you use them?**
    - **Answer**: Portals provide a way to render children into a DOM node that exists outside the hierarchy of the parent component. They are useful for rendering components like modals or tooltips that need to break out of the parent component's overflow or z-index:
      ```javascript
      const modalRoot = document.getElementById('modal-root');

      class Modal extends React.Component {
        constructor(props) {
          super(props);
          this.el = document.createElement('div');
        }

        componentDidMount() {
          modalRoot.appendChild(this.el);
        }

        componentWillUnmount() {
          modalRoot.removeChild(this.el);
        }

        render() {
          return ReactDOM.createPortal(this.props.children, this.el);
        }
      }

      const App = () => (
        <div>
          <h1>My App</h1>
          <Modal>
            <div>My Modal</div>
          </Modal>
        </div>
      );
      ```

104. **What is the `useCallback` hook and how do you use it?**
    - **Answer**: `useCallback` is a hook that returns a memoized version of the callback function that only changes if one of the dependencies has changed. It is useful for preventing unnecessary re-renders and optimizing performance:
      ```javascript
      const MyComponent = () => {
        const [count, setCount] = useState(0);

        const increment = useCallback(() => {
          setCount((prevCount) => prevCount + 1);
        }, []);

        return (
          <div>
            <p>Count: {count}</p>
            <button onClick={increment}>Increment</button>
          </div>
        );
      };
      ```

105. **What is React Concurrent Mode and what are its benefits?**
    - **Answer**: React Concurrent Mode is an experimental feature that allows React to work on multiple tasks simultaneously and prioritize tasks based on their importance. Benefits include:
      - **Improved responsiveness**: Prioritizes urgent updates (e.g., user input) over less urgent ones (e.g., network responses).
      - **Interruptible rendering**: Allows React to pause rendering work and resume it later.
      - **Concurrent rendering**: Enables React to render components concurrently.

106. **How do you handle error boundaries in React?**
    - **Answer**: Error boundaries are React components that catch JavaScript errors anywhere in their child component tree, log those errors, and display a fallback UI instead of the component tree that crashed. They are created using class components with the `componentDidCatch` lifecycle method:
      ```javascript
      class ErrorBoundary extends React.Component {
        constructor(props) {
          super(props);
          this.state = { hasError: false };
        }

        static getDerivedStateFromError(error) {
          return { hasError: true };
        }

        componentDidCatch(error, errorInfo) {
          // Log error
          console.error(error, errorInfo);
        }

        render() {
          if (this.state.hasError) {
            return <h1>Something went wrong.</h1>;
          }

          return this.props.children;
        }
      }

      const App = () => (
        <ErrorBoundary>
          <MyComponent />
        </ErrorBoundary>
      );
      ```

107. **What is the difference between `useState` and `useReducer`?**
    - **Answer**: Both `useState` and `useReducer` are hooks for managing state in functional components, but they have different use cases:
      - **useState**: Simple state management with a state variable and a function to update it. Best for simple state with a single value.
        ```javascript
        const [count, setCount] = useState(0);
        ```
      - **useReducer**: Complex state management with a state variable, a dispatch function, and a reducer function. Best for complex state logic involving multiple sub-values or when the next state depends on the previous one.
        ```javascript
        const [state, dispatch] = useReducer(reducer, initialState);
        ```
