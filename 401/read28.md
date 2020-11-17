# Component Composition

## Review, Research, and Discussion

* Can a parent component access the state of a child component? 

Yes.

* What can be passed along in a prop variable?

prop variables have a 100-character maximum limit.


* How can a child component “know” the state of another component?

From the parent compenent.

## Document the following Vocabulary Terms

* **component props**: A component with a render prop takes a function that returns a React element and calls it instead of implementing its own render logic.

* **component state**: State is managed within the component (similar to variables declared within a function).

* **application state**: Is simply the state at which an application resides with regards to where in a program is being executed and the memory that is stored for the application.


## Preparation Materials

### react basics recap

* The Component Lifecycle
![ex](https://cdn-media-1.freecodecamp.org/images/1*U13Mlxz_ktcajaeJCyYkwg.png)

* Higher-Order Components

* React State and setState()

* React Context

### React’s props.children

props.children on components that represent ‘generic boxes’ and that ‘don’t know their children ahead of time’.

#### Example

```js
const Picture = (props) => {
  return (
    <div>
      <img src={props.src}/>
      {props.children}
    </div>
  )
}
```

### Composition vs Inheritance

#### Containment

Some components don’t know their children ahead of time. This is especially common for components like Sidebar or Dialog that represent generic “boxes”.

#### Specialization

Sometimes we think about components as being “special cases” of other components. For example, we might say that a WelcomeDialog is a special case of Dialog.

#### Inheritance

At Facebook, they use React in thousands of components, and they haven’t found any use cases where they would recommend creating component inheritance hierarchies.

Props and composition give you all the flexibility you need to customize a component’s look and behavior in an explicit and safe way. Remember that components may accept arbitrary props, including primitive values, React elements, or functions.