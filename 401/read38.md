# Redux - Asynchronous Actions

## Review, Research, and Discussion

* How granular should your reducers be?

should only depend on their state and action arguments

* Pro or Con – multiple reducers can “fire” when a commonly named action is dispatched

  * No need to create action for each reducer.
  * Waste of time.

* Name a strategy for preventing the above

Using switch

## Document the following Vocabulary Terms

* store: brings together the state,
* combined reducers: helper function turns an object whose values are different reducing functions into a single reducing function you can pass to createStore

## Preparation Materials

### Async Logic and Data Fetching
By itself, a Redux store doesn't know anything about async logic. It only knows how to synchronously dispatch actions, update the state by calling the root reducer function, and notify the UI that something has changed. Any asynchronicity has to happen outside the store.

#### Some common kinds of side effects are things like

* Logging a value to the console
* Saving a file
* Setting an async timer
* Making an AJAX HTTP request
* Modifying some state that exists outside of a function, or mutating arguments to a function
* Generating random numbers or unique random IDs (such as Math. random() or Date.now())

#### Using Middleware to Enable Async Logic

Let's look at a couple examples of how middleware can enable us to write some kind of async logic that interacts with the Redux store.

One possibility is writing a middleware that looks for specific action types, and runs async logic when it sees those actions, like these examples:

```js
import { client } from '../api/client'

const delayedActionMiddleware = storeAPI => next => action => {
  if (action.type === 'todos/todoAdded') {
    setTimeout(() => {
      // Delay this action by one second
      next(action)
    }, 1000)
    return
  }

  return next(action)
}

const fetchTodosMiddleware = storeAPI => next => action => {
  if (action.type === 'todos/fetchTodos') {
    // Make an API call to fetch todos from the server
    client.get('todos').then(todos => {
      // Dispatch an action with the todos we received
      dispatch({ type: 'todos/todosLoaded', payload: todos })
    })
  }

  return next(action)
}
```

#### Redux Async Data Flow
![ex](https://redux.js.org/assets/images/ReduxAsyncDataFlowDiagram-d97ff38a0f4da0f327163170ccc13e80.gif)

### Redux Thunk

Thunk is a programming concept where a function is used to delay the evaluation/calculation of an operation.



