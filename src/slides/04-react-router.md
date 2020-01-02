# Adding App Routs

---

## Why do we need Routes?

- Logical seperation between views/pages
- Deep linking
- View state managment
- Authorization

---

## Routes vs. State

Naive route management

```js
const { route } = this.state;

<Container>
    {switch(route) {
        case 'home': 
            return <Home />
        case 'login': 
            return <Login />
        case 'register': 
            return <Register />
        default:
            return <Home>
    }}
</Container>
```

---

## Working with React-Router

- Declarative
- Browser Routing support (routes in the URL)
- History support
- Path and matchers

---

## Basic Example

```js
import React from "react";
import {
  BrowserRouter as Router,
  Switch,
  Route,
  Link
} from "react-router-dom";
import { About, Users, Home } from "./routes"

export default function App() {
  return (
    <Router>
      <div>
        <Switch>
          <Route path="/about">
            <About />
          </Route>
          <Route path="/users">
            <Users />
          </Route>
          <Route path="/">
            <Home />
          </Route>
        </Switch>
      </div>
    </Router>
  );
}

```


---

## Components

- `Router` - A HoC that is a context provider
- `Switch` - A route matcher - searches through child `Route` for url match
- `Route` - A url matcher. First match is rendered. More specific are first

---

## Router

- HashRouter - uses hash (`#`) to seperate the the page route 

`http://mydomain.com/webapp/#/your/page`


- BrowserRouter - use regular slash (`/`) seperated paths - requires server side support

`http://mydomain.com/webapp/your/page`


---

## Route - rendering

A container component for a specific route that provides information about the route

`path`: the location to match for the route to be rendered
`component`: An optional component to be rendered if the location is matched
`render`: A function to render if the location is matched
`children`: Components to render if the location is matched

* `<Route component>` takes precedence over `<Route render>` so don’t use both in the same `<Route>`
  
---

## Route with Component

```js
mport React from "react";
import ReactDOM from "react-dom";
import { BrowserRouter as Router, Route } from "react-router-dom";

// All route props (match, location and history) are available to User
function User(props) {
  return <h1>Hello {props.match.params.username}!</h1>;
}

ReactDOM.render(
  <Router>
    <Route path="/user/:username" component={User} />
  </Router>,
  node
);
```

---

## Route with `render` function

```js
import React from "react";
import ReactDOM from "react-dom";
import { BrowserRouter as Router, Route } from "react-router-dom";

// convenient inline rendering
ReactDOM.render(
  <Router>
    <Route path="/home" render={() => <div>Home</div>} />
  </Router>,
  node
);

```
---

## Route with children

```js
import React from "react";
import ReactDOM from "react-dom";
import {
  BrowserRouter as Router,
  Link,
  Route
} from "react-router-dom";

function ListItemLink({ to, ...rest }) {
  return (
    <Route
      path={to}
      children={({ match }) => (
        <li className={match ? "active" : ""}>
          <Link to={to} {...rest} />
        </li>
      )}
    />
  );
}

ReactDOM.render(
  <Router>
    <ul>
      <ListItemLink to="/somewhere" />
      <ListItemLink to="/somewhere-else" />
    </ul>
  </Router>,
  node
);
```

---

## Other `Route` props

- `path`: string | string[]
- `exact`: boolean
- `strict`: boolean
- `location`: object
- `sensitive`: boolean

---

## URL Parameters

Adding `:param-name` to a route can be paresed as a url parameter

for the route `/user/:id` 

```js
<Route path="/:id" render={({ match }) => {
    const id = match.params.id;
    return (<div>The id is {id}</div>)
}} />

```

---

## History

- A history is a parameter (object) passed into a component wrapped by a `<Route />`.

- use it to navigate between routes

```js
const { history } = this.props;

//...
history.push('/new-location')
```

---

## withRouter

A HoC that adds route related parameters to a component




