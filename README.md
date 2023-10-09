# How to install React Router
```console
npm install react-router-dom
```

That's it.


# How to use React-router
===============================================
* First we need to import react-router component(ofcurse after installing router)
* Some of router's components are :
1. BrowserRouter 
2. Routes
3. Route
4. Link

```jsx
import {BrowserRouter, Routes, Route, Link} from react-router-dom;
```

> I saw many ways of using Router. This is the easiest way I know.

<br>


* Now, create a component that will handle the `routing`. 
* **Note that** <ins>this is the main section</ins> of `react-routing`.

```jsx
import {BrowserRouter, Routes, Route, Link} from "react";

//main routing function component
const LinkHandling = ()=>{
  return(
    <BrowserRoute> // requires "BrowserRoute" component
      <Routes> //used to include multiple route tag, requires "Routes" component
        <Route path="/" element=<Home/> />  //if the path in the browser is "/" what component should we render?
        <Route path="/contact" element=<ContactPage/> />
        <Route path="/AboutUs" element=<AboutPage/> />
      </Roues>
    </BrowserRoute>
  )
}

//Now just render Router Function Component 
const root = ReactDOM.createRoot(document.getElementById('root'));

root.render(
  <React.StrictMode> 
    <LinkHandling /> 
  </React.StrictMode>
);


```

> You can also avoid creating the component and just create routing in the `render` section.

<br>
<br>

# React Router <Link>
==============================================================

The routing, 
* Its a JSX element.
* If you want to go one page from another page in react using React Routing,
* Then, `<Link>The text people want to see </Link>` is a proper way.
* Instead of using `<a> </a>`, the `<Link />` tag needs to be used. 
* In <Link /> tag, `L` must needs to be uppercase.
* Requirements: It requires `Link` components from `react-router-dom` 

```jsx
<Link path="/contactpage">Some Path </Link>
```


# Faced an issue

```console
npx create-react-app my-app
```
no longer works

<br>
<br>

### now I have to install react environment using something called `vite` 

```console
npm install vite@latest
```
> Problem is that the `react router` no longer works with those syntax somehow.
> If I install react with vite then this routing works
> And ofcurse I have to install react-router-dom using npm

```javascript
import * as React from "react";
import * as ReactDOM from "react-dom/client";
import {
  createBrowserRouter,
  RouterProvider,
} from "react-router-dom";
import "./index.css";

const router = createBrowserRouter([
  {
    path: "/",
    element: <div>Hello world!</div>,
  },
]);

ReactDOM.createRoot(document.getElementById("root")).render(
  <React.StrictMode>
    <RouterProvider router={router} />
  </React.StrictMode>
);
```
