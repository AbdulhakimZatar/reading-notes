# Context API

## Review, Research, and Discussion
* Describe use cases for useMemo() and useReducer()

useMemo() it allows you to apply memoization to any value type (not just functions).

useReducer() to use in order to reset the calculator to a default state of zero when clearing it out.

* Why do custom hooks need the use prefix?

so react can know it's custom hook

* What do custom hooks usually do?

We can decide what it takes as arguments, and what, if anything, it should return. In other words, it's just like a normal function.

## Document the following Vocabulary Terms
* **reducer**: Basic Reducer Structure: Overview of how reducer functions work with Redux state.

## Preparation Materials

### Context
Context is designed to share data that can be considered “global” for a tree of React components, such as the current authenticated user, theme, or preferred language.

#### Before You Use Context
Context is primarily used when some data needs to be accessible by many components at different nesting levels. Apply it sparingly because it makes component reuse more difficult.

If you only want to avoid passing some props through many levels, component composition is often a simpler solution than context.

```js
const MyContext = React.createContext(defaultValue);

```
Creates a Context object. When React renders a component that subscribes to this Context object it will read the current context value from the closest matching Provider above it in the tree.

The defaultValue argument is only used when a component does not have a matching Provider above it in the tree. This can be helpful for testing components in isolation without wrapping them. Note: passing undefined as a Provider value does not cause consuming components to use defaultValue.

