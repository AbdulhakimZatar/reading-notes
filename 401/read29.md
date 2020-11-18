# Routing

## Review, Research, and Discussion

* Do child components have direct access to props/state from the parent?

It have access but not direct.

* When a component “wraps” another component, how does the child component’s output get rendered?
```html
<Main>
  <Content />
</Main>
```

A higher-order component (HOC) is an advanced technique in React for reusing component logic. HOCs are not part of the React API, per se. They are a pattern that emerges from React’s compositional nature.

* Can a component, such as <Content />, which is a child also be used as a standalone component elsewhere in the application?

Yes

## Document the following Vocabulary Terms

* **props.children**: components that represent ‘generic boxes’ and that don’t know their children ahead of time. 
* **composition**: composition allows you to build more complex functionality by combining small and focused functions.

## Preparation Materials

### React Router

The <Route> component is the main building block of React Router. Anywhere that you want to only render content based on the location’s pathname, you should use a <Route> element.

* Choosing our router
* Creating our routes
* Navigating between routes using links

#### Path 
A <Route> expects a path prop, which is a string that describes the pathname that the route matches — for example, <Route path='/roster'/> should match a pathname that begins with /roster 2. When the current location’s pathname is matched by the path, the route will render a React element. When the path does not match, the route will not render anything 3.

#### Creating our routes
<Route>s can be created anywhere inside of the router, but often it makes sense to render them in the same place. You can use the <Switch> component to group <Route>s. The <Switch> will iterate over its children elements (the routes) and only render the first one that matches the current pathname.

```js
<Switch>
  <Route exact path='/' component={Home}/>
  {/* both /roster and /roster/:number begin with /roster */}
  <Route path='/roster' component={Roster}/>
  <Route path='/schedule' component={Schedule}/>
</Switch>
```

#### What does the <Route> render?
* component 
* render 
* children 

#### Nested Routes
```js
function Roster() {
  return (
    <Switch>
      <Route exact path='/roster' component={FullRoster}/>
      <Route path='/roster/:number' component={Player}/>
    </Switch>
  );
}
```

#### Path Params
```js
{ number: '6' } // note that the captured value is a string


// an API that returns a player object
import PlayerAPI from './PlayerAPI'
function Player(props) {
  const player = PlayerAPI.get(
    parseInt(props.match.params.number, 10)
  )
  if (!player) {
    return <div>Sorry, but the player was not found</div>
  }
  return (
    <div>
      <h1>{player.name} (#{player.number})</h1>
      <h2>{player.position}</h2>
    </div>
  );
}
```