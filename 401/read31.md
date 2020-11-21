# Hooks API

## Review, Research, and Discussion
* Why do we not need more .html pages in a multi-page React app?

Using jsx we can use html in js files

* If we wanted a component to show up on every page, where would we put it and why?
  * Outside the ```<BrowserRouter/>```
  * Inside the ```<BrowserRouter />```, outside a ```<Route />```
  * Inside a ```<Route />```

  Inside the ```<BrowserRouter />```, because this is the browers what see.


* What does props.children contain?

contain what inside the compenent ```<test> <children/> </test>```

## Document the following Vocabulary Terms
* **Composition**: composition allows you to build more complex functionality by combining small and focused functions.


* **Children / Child Components**: Children allow you to pass components as data to other components, just like any other prop you use. The special thing about children is that React provides support through its ReactElement API and JSX. XML children translate perfectly to React children!

* **Hash Routing**:  is using the anchor part of the URL to simulate different content.
* **Link Routing**:  technique in which each router shares the knowledge of its neighborhood with every other router in the internetwork.

## Preparation Materials

### Hooks
We know that components and top-down data flow help us organize a large UI into small, independent, reusable pieces. However, we often can’t break complex components down any further because the logic is stateful and can’t be extracted to a function or another component. Sometimes that’s what people mean when they say React doesn’t let them “separate concerns.”

* Huge components that are hard to refactor and test.
* Duplicated logic between different components and lifecycle methods.
* Complex patterns like render props and higher-order components.

#### Do Hooks Make React Bloated?
Before we look at Hooks in detail, you might be worried that we’re just adding more concepts to React with Hooks. That’s a fair criticism. I think that while there is definitely going to be a short-term cognitive cost to learning them, the end result will be the opposite.

#### So What About Classes?
Custom Hooks are, in our opinion, the most appealing part of the Hooks proposal. But in order for custom Hooks to work, React needs to provide functions with a way to declare state and side effects. And that’s exactly what built-in Hooks like useState and useEffect let us do.

#### Using the State Hook
```js
import React, { useState } from 'react';

function Example() {
  // Declare a new state variable, which we'll call "count"
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}
```

#### Declaring multiple state variables
```js
function ExampleWithManyStates() {
  // Declare multiple state variables!
  const [age, setAge] = useState(42);
  const [fruit, setFruit] = useState('banana');
  const [todos, setTodos] = useState([{ text: 'Learn Hooks' }]);
  // ...
}
```
#### Effect Hook
You’ve likely performed data fetching, subscriptions, or manually changing the DOM from React components before. We call these operations “side effects” (or “effects” for short) because they can affect other components and can’t be done during rendering.

```js
import React, { useState, useEffect } from 'react';

function Example() {
  const [count, setCount] = useState(0);

  // Similar to componentDidMount and componentDidUpdate:
  useEffect(() => {
    // Update the document title using the browser API
    document.title = `You clicked ${count} times`;
  });

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}
```
