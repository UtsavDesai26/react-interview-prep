![UtsavDesai26](https://github.com/UtsavDesai26/react-interview-prep/assets/80502799/07f8817f-f0e1-4ce6-8f54-20e133465292)

# Understand React Hooks with Examples

## 1. `useState`

The `useState` hook is fundamental for adding state to functional components. It returns an array with the current state value and a function that lets you update it.

### Example:

```jsx
import React, { useState } from "react";

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>Click me</button>
    </div>
  );
}
```

## 2. `useEffect`

`useEffect` enables performing side effects in functional components. It runs after every render and is useful for data fetching, subscriptions, or manually changing the DOM.

### Example:

```jsx
import React, { useState, useEffect } from "react";

function Example() {
  const [count, setCount] = useState(0);

  useEffect(() => {
    document.title = `You clicked ${count} times`;
  });

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>Click me</button>
    </div>
  );
}
```

## 3. `useContext`

`useContext` provides access to the React context API within functional components. It allows components to subscribe to context changes.

### Example:

```jsx
import React, { useContext } from "react";
import ThemeContext from "./ThemeContext";

function ThemedButton() {
  const theme = useContext(ThemeContext);

  return (
    <button style={{ background: theme.background, color: theme.foreground }}>
      Themed Button
    </button>
  );
}
```

## 4. `useReducer`

`useReducer` is a hook that is usually preferable to `useState` when you have complex state logic. It takes a reducer function and returns the current state, dispatch function, and an optional initial action.

### Example:

```jsx
import React, { useReducer } from "react";

const initialState = { count: 0 };

function reducer(state, action) {
  switch (action.type) {
    case "increment":
      return { count: state.count + 1 };
    case "decrement":
      return { count: state.count - 1 };
    default:
      throw new Error();
  }
}

function Counter() {
  const [state, dispatch] = useReducer(reducer, initialState);

  return (
    <div>
      Count: {state.count}
      <button onClick={() => dispatch({ type: "increment" })}>+</button>
      <button onClick={() => dispatch({ type: "decrement" })}>-</button>
    </div>
  );
}
```

## 5. `useCallback` and `useMemo`

`useCallback` memoizes functions to optimize performance, while `useMemo` memoizes values. These are crucial for preventing unnecessary re-renders.

### Example:

```jsx
import React, { useState, useCallback, useMemo } from "react";

function MyComponent({ data }) {
  const [count, setCount] = useState(0);

  const handleClick = useCallback(() => {
    setCount(count + 1);
  }, [count]);

  const doubledCount = useMemo(() => {
    return count * 2;
  }, [count]);

  return (
    <div>
      <button onClick={handleClick}>Click me</button>
      <p>Count: {count}</p>
      <p>Doubled Count: {doubledCount}</p>
    </div>
  );
}
```

## 6. `useRef`

`useRef` provides a way to persist values across renders without causing re-renders. It is often used for accessing and interacting with the DOM.

### Example:

```jsx
import React, { useRef } from "react";

function TextInputWithFocusButton() {
  const inputEl = useRef(null);
  const focusInput = () => {
    inputEl.current.focus();
  };

  return (
    <div>
      <input ref={inputEl} type="text" />
      <button onClick={focusInput}>Focus Input</button>
    </div>
  );
}
```

## 7. Additional Hooks

### - `useImperativeHandle`

`useImperativeHandle` customizes the instance value that is exposed when using `React.forwardRef`. It can be useful for hiding certain properties from the parent components.

### - `useLayoutEffect`

`useLayoutEffect` is similar to `useEffect`, but it fires synchronously after all DOM mutations. Use it when you need to read or manipulate the layout before the browser paints.

### - `useDebugValue`

`useDebugValue` is used to display a label for custom hooks in React DevTools. It can be helpful for debugging custom hooks.

### - `useId`

`useId` generates a unique identifier that can be used for associating elements and labels in your application. It's particularly useful for managing accessibility and ensuring the uniqueness of elements.

### - `useDeferredValue`

`useDeferredValue` is used for deferring the update of a value in concurrent mode. It allows prioritizing rendering of critical components while deferring less critical updates, enhancing the responsiveness and performance of your application.

### - `useInsertionEffect`

`useInsertionEffect` is similar to `useEffect`, but it triggers only on initial insertion into the DOM. It's useful for executing side effects that should only occur once during component initialization.

### - `useOptimistic`

`useOptimistic` is a hook used in optimistic UI rendering scenarios. It allows you to update the UI optimistically while waiting for confirmation from the server, providing a smoother user experience.

### - `useSyncExternalStore`

`useSyncExternalStore` synchronizes the state of a React component with an external data store, such as local storage or a global state management solution. It ensures consistency between the component state and the external data source.

### - `useTransition`

`useTransition` enables smoother transitions between different UI states or components. It allows you to coordinate changes to the UI in a way that avoids jarring transitions and enhances the overall user experience.

These additional hooks expand the capabilities of React and offer solutions to common challenges encountered in frontend development. Incorporate them into your projects as needed to optimize performance, enhance user experience, and streamline development workflows.

## Conclusion

Mastering React Hooks provides a robust foundation for building scalable and maintainable React applications. By understanding and leveraging the power of each hook, developers can create efficient and expressive functional components. Experiment with these hooks in your projects and tailor them to your specific needs to unlock the full potential of React development.

---

[![Github Badge](http://img.shields.io/badge/-Github-black?style=flat-square&logo=github&link=https://github.com/UtsavSoftrefineTech)](https://github.com/UtsavSoftrefineTech)
[![Linkedin Badge](https://img.shields.io/badge/-LinkedIn-blue?style=flat-square&logo=Linkedin&logoColor=white&link=https://www.linkedin.com/in/utsavdesai26/)](https://www.linkedin.com/in/utsavdesai26/)
[![Stackoverflow Badge](https://img.shields.io/badge/-Stack%20overflow-FE7A16?style=flat-square&logo=stack-overflow&logoColor=white&link=https://stackoverflow.com/users/22878781/utsav-desai)](https://stackoverflow.com/users/22878781/utsav-desai)
[![Gmail Badge](https://img.shields.io/badge/-Gmail-d14836?style=flat-square&logo=Gmail&logoColor=white&link=mailto:desaiutsav26@gmail.com)](mailto:desaiutsav26@gmail.com)
[![Medium Badge](https://img.shields.io/badge/-Medium-black?style=flat-square&logo=medium&link=https://medium.com/@utsavdesai26)](https://medium.com/@utsavdesai26)
