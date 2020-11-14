# Component Based UI

## Review, Research, and Discussion

* Name 5 Javascript UI Frameworks (other than React)
Angular, jQuery, Bootstrap, Vue, Ember

* What’s the difference between a framework and a library?

## Document the following Vocabulary Terms

The technical difference between a framework and library lies in a term called inversion of control.

When you use a library, you are in charge of the flow of the application. You are choosing when and where to call the library. When you use a framework, the framework is in charge of the flow. It provides some places for you to plug in your code, but it calls the code you plugged in as needed.

## Preparation Materials

### React
is an open-source, front end, JavaScript library[3] for building user interfaces or UI components. 

The smallest React example looks like this:
```js
ReactDOM.render(
  <h1>Hello, world!</h1>,
  document.getElementById('root')
);
```

#### Rendering Elements

```js
const element = <h1>Hello, world</h1>;
ReactDOM.render(element, document.getElementById('root'));
```

#### Updating the Rendered Element

```js
function tick() {
  const element = (
    <div>
      <h1>Hello, world!</h1>
      <h2>It is {new Date().toLocaleTimeString()}.</h2>
    </div>
  );
  ReactDOM.render(element, document.getElementById('root'));
}

setInterval(tick, 1000);
```


### JSX

JSX may remind you of a template language, but it comes with the full power of JavaScript.

#### Why JSX?
React embraces the fact that rendering logic is inherently coupled with other UI logic: how events are handled, how the state changes over time, and how the data is prepared for display.

#### Embedding Expressions in JSX
```js 
const name = 'Josh Perez';
const element = <h1>Hello, {name}</h1>;

ReactDOM.render(
  element,
  document.getElementById('root')
);
```

#### JSX is an Expression Too
After compilation, JSX expressions become regular JavaScript function calls and evaluate to JavaScript objects.

