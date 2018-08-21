---
layout: post
title:  "Week-05 day-02 React State"
date:   2018-08-21 20:40:20 +0800
categories: JSA React
---

## virtual DOM
###trandition DOM:

  - when change some elements, DOM will remove them then render the new ones, it's not effiencent and very slow.
  
  - so have to chenge the propertie of elements, and DOM won't rerender.

###virtual DOM:

  react have 2 layers: Virtual DOM, Real DOM
  
  change JSX -> render whole things into virtual DOM -> create everything (in the memory) -> check changes -> move only the changes into real DOM


## JSX
[Introducing JSX](https://reactjs.org/docs/introducing-jsx.html)

JSX looks like this: ```const element = <h1>Hello, world!</h1>;```



## state 
```
class Clock extends React.Component {
  constructor(props) {
    super(props);
    this.state = {date: new Date()};
  }

  render() {
    return (
      <div>
        <h1>Hello, world!</h1>
        <h2>It is {this.state.date.toLocaleTimeString()}.</h2>
      </div>
    );
  }
}

ReactDOM.render(
  <Clock />,
  document.getElementById('root')
);
```

### Using State Correctly
There are three things you should know about setState().

Do Not Modify State Directly
For example, this will not re-render a component:

```
// Wrong
this.state.comment = 'Hello';
Instead, use setState():

// Correct
this.setState({comment: 'Hello'});
```
The only place where you can assign this.state is the constructor.

### State Updates May Be Asynchronous
React may batch multiple setState() calls into a single update for performance.

Because this.props and this.state may be updated asynchronously, you should not rely on their values for calculating the next state.

For example, this code may fail to update the counter:

```
// Wrong
this.setState({
  counter: this.state.counter + this.props.increment,
});
```
To fix it, use a second form of setState() that accepts a function rather than an object. That function will receive the previous state as the first argument, and the props at the time the update is applied as the second argument:

```
// Correct
this.setState((prevState, props) => ({
  counter: prevState.counter + props.increment
}));
```
We used an arrow function above, but it also works with regular functions:

```
// Correct
this.setState(function(prevState, props) {
  return {
    counter: prevState.counter + props.increment
  };
});
```

### State Updates are Merged
When you call setState(), React merges the object you provide into the current state.

For example, your state may contain several independent variables:

```
  constructor(props) {
    super(props);
    this.state = {
      posts: [],
      comments: []
    };
  }
```
Then you can update them independently with separate setState() calls:

```
  componentDidMount() {
    fetchPosts().then(response => {
      this.setState({
        posts: response.posts
      });
    });

    fetchComments().then(response => {
      this.setState({
        comments: response.comments
      });
    });
  }
```
The merging is shallow, so this.setState({comments}) leaves this.state.posts intact, but completely replaces this.state.comments.

### The Data Flows Down
Neither parent nor child components can know if a certain component is stateful or stateless, and they shouldn’t care whether it is defined as a function or a class.

This is why state is often called local or encapsulated. It is not accessible to any component other than the one that owns and sets it.

## Functional and Class Components
The simplest way to define a component is to write a JavaScript function:

```
// functional or stateless
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}
```

You can also use an ES6 class to define a component:

```
// class or stateful
class Welcome extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}
```

## props
Props are Read-Only



## render
###Rendering an Element into the DOM
Let’s say there is a <div> somewhere in your HTML file: ```<div id="root"></div>```

We call this a “root” DOM node because everything inside it will be managed by React DOM.

Applications built with just React usually have a single root DOM node. If you are integrating React into an existing app, you may have as many isolated root DOM nodes as you like.

To render a React element into a root DOM node, pass both to ReactDOM.render():

```
const element = <h1>Hello, world</h1>;
ReactDOM.render(element, document.getElementById('root'));
```
###React Only Updates What’s Necessary
React DOM compares the element and its children to the previous one, and only applies the DOM updates necessary to bring the DOM to the desired state.

## lifecyclehook
```
componentDidMount() {

}
```
The **componentDidMount()** hook runs after the component output has been rendered to the DOM.

```
componentWillUnmount() {

}
```
The component will be stopped when the **componentWillUnmount()** lifecycle hook is called.

## CORS

[CORS](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS) Cross-Origin Resource Sharing

![](https://mdn.mozillademos.org/files/14295/CORS_principle.png)

cause by the backend server.

if want to solve this, in the backend should set the 

```
Access-Control-Allow-Origin: * // * means any url, but you can filter some
```

## install react without create-react-app
npm init -> get package.json

npm i react --save -> add dependencies
npm i babel-core --save-dev -> add development dependencies

npm run lint -- --init

## props.children
the text in the ```<>'text here'</>``` has the default name -> children. so you can use props.children to access it.

## handle events
For example, the HTML:

```
<button onclick="activateLasers()">
  Activate Lasers
</button>
```
is slightly different in React:

```
<button onClick={activateLasers}>
  Activate Lasers
</button>
```

Another difference is that you cannot return false to prevent default behavior in React. You must call preventDefault explicitly. For example, with plain HTML, to prevent the default link behavior of opening a new page, you can write:

```
<a href="#" onclick="console.log('The link was clicked.'); return false">
  Click me
</a>
```
In React, this could instead be:

```
function ActionLink() {
  function handleClick(e) {
    e.preventDefault();
    console.log('The link was clicked.');
  }

  return (
    <a href="#" onClick={handleClick}>
      Click me
    </a>
  );
}
```
Here, e is a synthetic event. 

When using React you should generally not need to call addEventListener to add listeners to a DOM element after it is created. Instead, just provide a listener when the element is initially rendered.

## without bind()
