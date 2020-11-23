# Custom Hooks

## Review, Research, and Discussion

* What does a component’s lifecycle refer to?

Components are created (mounted on the DOM), grow by updating, and then die (unmount on DOM).

* Why do you sometimes need to “wrap” functions in useCallback when called from within useEffect

to use async and await

* Why are functional components preferred over class components?
  * Functional component are much easier to read and test because they are plain JavaScript functions without state or lifecycle-hooks.
  * It has less code which makes it more readable.

* What is wrong with the following code?

for loop affect the useEffect

## Document the following Vocabulary Terms

* **state hook**: are completely independent of each other, so you can have as many state objects as you want.
* **effect hook**: adds the ability to perform side effects from a function component.
* **reducer hook**:  An alternative to useState . Accepts a reducer of type (state, action) => newState 

## Preparation Materials

### Custom Hooks

#### So How Do We Use Hooks
The easiest way to describe Hooks is to show side-by-side examples of a class component that needs to have access to state and lifecycle methods, and another example where we achieve the same thing with a functional component.

#### The Benefits of Using Hooks
Hooks have a lot of benefit to us as developers, and they are going to change the way we write components for the better.

#### Five Important Rules for Hooks
* Never call Hooks from inside a loop, condition or nested function
* Hooks should sit at the top-level of your component
* Only call Hooks from React functional components
* Never call a Hook from a regular function
* Hooks can call other Hooks

#### React Hooks with Async-Await
We cannot use 'async' keyword with 'useEffect' callback method. It will result in race conditions.

### useReducer
An alternative to useState. Accepts a reducer of type (state, action) => newState, and returns the current state paired with a dispatch method. (If you’re familiar with Redux, you already know how this works.)

```js
const initialState = {count: 0};

function reducer(state, action) {
  switch (action.type) {
    case 'increment':
      return {count: state.count + 1};
    case 'decrement':
      return {count: state.count - 1};
    default:
      throw new Error();
  }
}

function Counter() {
  const [state, dispatch] = useReducer(reducer, initialState);
  return (
    <>
      Count: {state.count}
      <button onClick={() => dispatch({type: 'decrement'})}>-</button>
      <button onClick={() => dispatch({type: 'increment'})}>+</button>
    </>
  );
}
```

### Building Your Own Hooks
Building your own Hooks lets you extract component logic into reusable functions.

```js
import React, { useState, useEffect } from 'react';

function FriendStatus(props) {
  const [isOnline, setIsOnline] = useState(null);
  useEffect(() => {
    function handleStatusChange(status) {
      setIsOnline(status.isOnline);
    }
    ChatAPI.subscribeToFriendStatus(props.friend.id, handleStatusChange);
    return () => {
      ChatAPI.unsubscribeFromFriendStatus(props.friend.id, handleStatusChange);
    };
  });

  if (isOnline === null) {
    return 'Loading...';
  }
  return isOnline ? 'Online' : 'Offline';
}
```

Now let’s say that our chat application also has a contact list, and we want to render names of online users with a green color. We could copy and paste similar logic above into our FriendListItem component but it wouldn’t be ideal:

```js
import React, { useState, useEffect } from 'react';

function FriendListItem(props) {
  const [isOnline, setIsOnline] = useState(null);
  useEffect(() => {
    function handleStatusChange(status) {
      setIsOnline(status.isOnline);
    }
    ChatAPI.subscribeToFriendStatus(props.friend.id, handleStatusChange);
    return () => {
      ChatAPI.unsubscribeFromFriendStatus(props.friend.id, handleStatusChange);
    };
  });

  return (
    <li style={{ color: isOnline ? 'green' : 'black' }}>
      {props.friend.name}
    </li>
  );
}
```

#### Extracting a Custom Hook
A custom Hook is a JavaScript function whose name starts with ”use” and that may call other Hooks. For example, useFriendStatus below is our first custom Hook:

```js
import { useState, useEffect } from 'react';

function useFriendStatus(friendID) {
  const [isOnline, setIsOnline] = useState(null);

  useEffect(() => {
    function handleStatusChange(status) {
      setIsOnline(status.isOnline);
    }

    ChatAPI.subscribeToFriendStatus(friendID, handleStatusChange);
    return () => {
      ChatAPI.unsubscribeFromFriendStatus(friendID, handleStatusChange);
    };
  });

  return isOnline;
}
```

#### Using a Custom Hook
Now that we’ve extracted this logic to a useFriendStatus hook, we can just use it:

```js
function FriendStatus(props) {
  const isOnline = useFriendStatus(props.friend.id);

  if (isOnline === null) {
    return 'Loading...';
  }
  return isOnline ? 'Online' : 'Offline';
}
```

```js
function FriendListItem(props) {
  const isOnline = useFriendStatus(props.friend.id);

  return (
    <li style={{ color: isOnline ? 'green' : 'black' }}>
      {props.friend.name}
    </li>
  );
}
```