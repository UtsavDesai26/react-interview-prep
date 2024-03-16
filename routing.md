![UtsavDesai26](https://github.com/UtsavDesai26/react-interview-prep/assets/80502799/07f8817f-f0e1-4ce6-8f54-20e133465292)

# Implementing Routing using React Router

Routing is an essential aspect of building single-page applications (SPAs) with ReactJS. It allows users to navigate between different views or pages without the need for a full page reload. React Router is a popular library used for managing routing in React applications.

## Getting Started with React Router

To begin using React Router in your application, you'll first need to install it via npm or yarn:

```bash
npm install react-router-dom
```

or

```bash
yarn add react-router-dom
```

Once installed, you can import the necessary components from React Router to start defining your application's routes.

## Basic Usage

In React Router, routes are defined using the `<Route>` component, which is typically wrapped within a `<BrowserRouter>` component. Here's a basic example of how you can set up routing in your React application:

```jsx
// Import necessary components from react-router-dom
import { BrowserRouter as Router, Route, Switch } from 'react-router-dom';

// Import your components/pages
import Home from './components/Home';
import About from './components/About';
import Contact from './components/Contact';

// Define your routes within the Router component
function App() {
  return (
    <Router>
      <Switch>
        <Route exact path="/" component={Home} />
        <Route path="/about" component={About} />
        <Route path="/contact" component={Contact} />
      </Switch>
    </Router>
  );
}

export default App;
```

In the above example:

- We imported the necessary components from `react-router-dom`.
- We defined routes for three different paths: `/`, `/about`, and `/contact`.
- Each route maps to a specific component (`Home`, `About`, `Contact`).
- The `<Switch>` component ensures that only one route is rendered at a time.

## Route Parameters

React Router allows you to define dynamic routes using parameters. These parameters can be accessed within your components to fetch data or perform other actions based on the URL.

```jsx
<Route path="/users/:userId" component={UserDetail} />
```

In the above route definition, `:userId` is a route parameter that can be accessed within the `UserDetail` component via `props.match.params.userId`.

## Navigation

To navigate between different routes in your application, you can use the `<Link>` component provided by React Router.

```jsx
import { Link } from 'react-router-dom';

function Navigation() {
  return (
    <nav>
      <ul>
        <li><Link to="/">Home</Link></li>
        <li><Link to="/about">About</Link></li>
        <li><Link to="/contact">Contact</Link></li>
      </ul>
    </nav>
  );
}
```

By using `<Link>` components, you can create navigation menus and links that seamlessly transition between different views without reloading the page.

## Nested Routes

React Router supports nested routes, allowing you to define routes within components to create more complex navigation structures.

```jsx
<Route path="/products" component={Products}>
  <Route path="/products/:productId" component={ProductDetail} />
</Route>
```

In the above example, when the URL matches `/products`, the `Products` component will be rendered. If the URL matches `/products/:productId`, the `ProductDetail` component will be rendered within the `Products` component.

## Conclusion

React Router provides a powerful and flexible way to handle routing in React applications. By defining routes, handling parameters, and utilizing navigation components, you can create seamless and dynamic user experiences in your React projects.

👉 [Advanced Routing Techniques](advancedrouting.md)

This concludes our overview of implementing routing using React Router. Experiment with different features and explore the documentation to unlock the full potential of routing in your React applications. Happy coding!

----

[![Github Badge](http://img.shields.io/badge/-Github-black?style=flat-square&logo=github&link=https://github.com/UtsavSoftrefineTech)](https://github.com/UtsavSoftrefineTech)
[![Linkedin Badge](https://img.shields.io/badge/-LinkedIn-blue?style=flat-square&logo=Linkedin&logoColor=white&link=https://www.linkedin.com/in/utsavdesai26/)](https://www.linkedin.com/in/utsavdesai26/)
[![Hackerrank Badge](https://img.shields.io/badge/-Hackerrank-2EC866?style=flat-square&logo=HackerRank&logoColor=white&link=https://www.hackerrank.com/profile/UtsavDesai26)](https://www.hackerrank.com/profile/UtsavDesai26)
[![Stackoverflow Badge](https://img.shields.io/badge/-Stack%20overflow-FE7A16?style=flat-square&logo=stack-overflow&logoColor=white&link=https://stackoverflow.com/users/22878781/utsav-desai)](https://stackoverflow.com/users/22878781/utsav-desai)
[![Gmail Badge](https://img.shields.io/badge/-Gmail-d14836?style=flat-square&logo=Gmail&logoColor=white&link=mailto:desaiutsav26@gmail.com)](mailto:desaiutsav26@gmail.com)
[![Leetcode Badge](https://img.shields.io/badge/-Leetcode-FFA116?style=flat-square&logo=leetcode&logoColor=white&link=https://leetcode.com/desaiutsav26/)](https://leetcode.com/desaiutsav26/)
[![Medium Badge](https://img.shields.io/badge/-Medium-black?style=flat-square&logo=medium&link=https://medium.com/@utsavdesai26)](https://medium.com/@utsavdesai26)
