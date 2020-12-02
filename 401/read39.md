# Redux - Additional Topics

## Review, Research, and Discussion

* What’s the best practice for “pre-loading” data into the store (on application start) in a Redux application?

using useEffect.

* When using a thunk/async action that dispatches the actual action, which do you export from your reducer?

the async function.

## Document the following Vocabulary Terms

* middleware: provides a third-party extension point between dispatching an action
* thunk: middleware allows you to write action creators that return a function instead of an action.

## Preparation Materials

### Redux Toolkit

It easier to write good Redux applications and speeds up development, by baking in our recommended best practices, providing good default behaviors, catching mistakes, and allowing you to write simpler code.

Redux Toolkit is beneficial to all Redux users regardless of skill level or experience. It can be added at the start of a new project, or used as part of an incremental migration in an existing project.

### What's Included#

* A configureStore() function with simplified configuration options. It can automatically combine your slice reducers, adds whatever Redux middleware you supply, includes redux-thunk by default, and enables use of the Redux DevTools Extension.
* A createReducer() utility that lets you supply a lookup table of action types to case reducer functions, rather than writing switch statements. In addition, it automatically uses the immer library to let you write simpler immutable updates with normal mutative code, like state.todos[3].completed = true.
* A createAction() utility that returns an action creator function for the given action type string. The function itself has toString() defined, so that it can be used in place of the type constant.
* A createSlice() function that accepts a set of reducer functions, a slice name, and an initial state value, and automatically generates a slice reducer with corresponding action creators and action types.
* The createSelector utility from the Reselect library, re-exported for ease of use.* 

we can replace the plain Redux createStore function with RTK's configureStore. This will automatically set up the Redux DevTools Extension for us.

The changes here are simple. We update src/index.js to import configureStore instead of createStore, and replace the function call. Remember that configureStore takes an options object as a parameter with named fields, so instead of passing rootReducer directly as the first parameter, we pass it as an object field named reducer:

```js
import React from "react";
import { render } from "react-dom";
-import { createStore } from "redux";
+import { configureStore } from "@reduxjs/toolkit";
import { Provider } from "react-redux";
import App from "./components/App";
import rootReducer from "./reducers";

- const store = createStore(rootReducer);
+ const store = configureStore({
+   reducer: rootReducer,
+});
```