# Redux - Combined Reducers

## Review, Research, and Discussion

* Why choose Redux instead of the Context API for global state?

with a more complex state which has high-frequency updates, the React Context won't be a good solution. Because, the React Context will trigger a re-render on each update, and optimizing it manually can be really tough. And there, a solution like Redux is much easier to implement.


* What is the purpose of a reducer?

Determines changes to an application's state.

* What does an action contain?

JavaScript object that has a type field

* Why do we need to copy the state in a reducer?

It's only for read that why

## Document the following Vocabulary Terms

* immutable state: sometimes you can mutate the state in a view or in an action by mistake. To reduce chances of this happening we can make state mutations explicit by using and immutable data structure.
* time travel in redux:  ability to move back and forth among the previous states of an application and view the results in real time. 
* action creator: JavaScript object that has a type field
* reducer: function that determines changes to an application's state.
* dispatch:  The only way to update the state is to call store.dispatch()

## Preparation Materials

### combineReducers
The most common state shape for a Redux app is a plain Javascript object containing "slices" of domain-specific data at each top-level key. Similarly, the most common approach to writing reducer logic for that state shape is to have "slice reducer" functions, each with the same (state, action) signature, and each responsible for managing all updates to that specific slice of state. Multiple slice reducers can respond to the same action, independently update their own slice as needed, and the updated slices are combined into the new state object.

#### State Shape
There are two ways to define the initial shape and contents of your store's state. First, the createStore function can take preloadedState as its second argument. This is primarily intended for initializing the store with state that was previously persisted elsewhere, such as the browser's localStorage. The other way is for the root reducer to return the initial state value when the state argument is undefined. These two approaches are described in more detail in Initializing State, but there are some additional concerns to be aware of when using combineReducers.

```js
// reducers.js
export default theDefaultReducer = (state = 0, action) => state

export const firstNamedReducer = (state = 1, action) => state

export const secondNamedReducer = (state = 2, action) => state

// rootReducer.js
import { combineReducers, createStore } from 'redux'

import theDefaultReducer, {
  firstNamedReducer,
  secondNamedReducer
} from './reducers'

// Use ES6 object literal shorthand syntax to define the object shape
const rootReducer = combineReducers({
  theDefaultReducer,
  firstNamedReducer,
  secondNamedReducer
})

const store = createStore(rootReducer)
console.log(store.getState())
// {theDefaultReducer : 0, firstNamedReducer : 1, secondNamedReducer : 2}
```

A better usage might look like:

```js
import { combineReducers, createStore } from 'redux'

// Rename the default import to whatever name we want. We can also rename a named import.
import defaultState, {
  firstNamedReducer,
  secondNamedReducer as secondState
} from './reducers'

const rootReducer = combineReducers({
  defaultState, // key name same as the carefully renamed default export
  firstState: firstNamedReducer, // specific key name instead of the variable name
  secondState // key name same as the carefully renamed named export
})

const reducerInitializedStore = createStore(rootReducer)
console.log(reducerInitializedStore.getState())
// {defaultState : 0, firstState : 1, secondState : 2}

```