# Personal notes from learning React

## Day 1(Lesson 1 - 16) (1 hour): Lets go! Learn React :)
## Troubleshoot: 
- Email: ste.grider@gmail.com
- Twitter: @sg_in_sf
- Github: github.com/stephengrider

## General React notes: 
- React is a JS library
- Components: snippets of code that produces HTML
  - Multiple Components: Nest them to make complex applications
- React / React DOM: React starting to diverge into two libraries
  - React DOM library: functionality to render on the DOM.
  - React library: functionality to create/ manage components.
- Transpilation: Code is transpiled when served to the web.
  - JSX: simplifies code! This gets transpiled into React code.
    - JSX tag calls createElement. Component name is component class, but JSX turns it into component instance. i.e. <App /> (self closing tag) : this creates an App component instance. 
- Code structure: 1 Component per JS file. This is the standard. 
  - "container" is the root node of the React App. 
  - npm install --save <package>: save <package> to package.json file. 


## ES6 notes:
- ES6 modules: Normally, files cant refer to variables in other files.
- Importing React: Even if React is installed in dependencies, it still needs to be imported i.e. import the module React to get access in the file. 
```
import React from 'react'
```
- Exploring modules: explicitly declare connections between JS files. 
```
export default <Component>
```
  - When importing javascript files (that we write), need to provide a path to the file we're trying to import. Not necessary for libraries, since there can't be conflicting names for libraries.

Error:  Invalid component element. Instead of passing a component class, make sure to instantiate it by passing it to React.createElement.
- When we create a component, we create a class of the component. 
- Make sure to pass instance of class to DOM. i.e. render(App)

Classes (Creating components with ES6 classes)
- extends React.Component
- Define method on class called render(). Every class based component needs this render() method. 
State 
- Use Class Components

## Code from day 1 (index.js)

```
import React from 'react'; //go find react library and assign to variable React
import ReactDOM from 'react-dom'
// Transpiler gives this file access to react.

import SearchBar from './components/search_bar'
//allows requests to Youtube.
const API_KEY = 'AIzaSyC8p4Tmi7_ZTVxBLW0MlpiiZgr95MaTCbI'; //API key to Youtube api.


// Create a new component. This component should produce some html

//const : ES6 syntax. Const makes App non-reassignable. Never changed.
//var is kind of the same, declares variable
// Anonymous functions is javascript:
// var flyToTheMoon = function() {
//   alert("Zoom! Zoom! Zoom!");
// }
// Call function by flyToTheMoon()

//Const App creates a class, not the instance! Instance creation: <App />
const App = function() {
  return (
    <div>
      <SearchBar />
    </div>);
  //JSX syntax: what looks like html but behind the scenes javascript.
  //  JSX gets transpiled to Javascript.
  //  JSX makes code more legible.
  // This is the same as React.createElement("div", null, "Hi!");
}

//ES6 syntax for function():
// const App = () => {
//   return <div>Hi!</div>;
// }


// Make sure this component's generated HTML is put on the page (in the DOM).
ReactDOM.render(<App />, document.querySelector('.container')); //need to make sure to import ReactDOM
//Pass instance of App: <App /> (same as <App> </App>)

// document.querySelector('.container') : need to tell where to mount the app on
// the DOM.

```

## Day 2(Lesson 16 - ...) (1 hour)

Event handler
- function run when event occurs
- pass event handler to element to handle the event
- in JSX, wrap JS with curly braces
- All browser events that get triggered by native elements, when handled by the event handler, it is called with an event 
 object. Describes context / information on the event that occured. 
 - Watch for 'Change' input. Change is a protected react defined property. Search up in react docs

React State:
- A plain javascript object that is used to record and react to user events. Each class based object we fine 
has its own state object. Whenever the state is changed, the object and all its children re-render. 
- Need to initialize state. 
- All js classes have function 'constructor', which gets called upon initialization. 
- update state with this.setState.

Controlled field / form element:  
- a form element i.e. input, whose value is set by the state
- i.e. value = {this.state.term}. The value is set by the state! The value changes only 
  when the state changes.
- Saves the change made from the event.

Downward dataflow: most parent object fetches data. 

## Day 3

- ES6 syntax (syntactic sugar when key and value have the same name): this.setState({videos: videos}) --> just do this.setState({videos});

props
- passing props: 
  - Child accessing state of parent. Pass the data through the JSX. Pass by defining property on JSX tag
  - i.e. videos = {this.state.videos}, videos is the 'props object'
  - Each time the app re renders, VideoList will get the new list of videos as well
  - with functional component, the props object arrives as an argument to the function. 
  - class components access by this.props
  - ES6 syntax: const video = props.video is the same as having {video} as argument to functional component. Basically says take 
  the property video, and make the reference to the property.
 
  
  
When we render items of the same type, react assumes we are rendering a list.
- logic is built to optimize rendering a list. 

Creating video-detail:
- ES6 syntax: adding thing to string: 
  - `....../${thing_to_add}` : use backticks!
  
  Handling null props:
  - 
  
Day 4: Lecture 29 onwards
  
Video Selection: 
- Adding selected video to App state
  
Current flow of App: 
- Initialization of app: search is performed, setting state of App Component (video and selected video) through the 
  callback function provided. Setting state re renders the component. i.e VideoDetail and VideoList is re-rendered 
  with the newly searched video.
    
Passing function as property of JSX (i.e. passing through props)
- <VideoList 
    onVideoSelect={selectedVideo => this.setState({selectedVideo})} //Function that sets the video. 
    videos={this.state.videos} />

Passing callbacks (functions) from parent to child components. 
- can be confusing where it is called and see where it is coming from!
- can be called by a child to go to the parent. 

React wrap up:
- Functional vs class components: functional for simple properties and static JSX. Super lightweight, super fast. 
- State: this.state in constructor function to initialize state. When we change state, component instantly re-renders, 
  along with all the children.
- import: relative path for our own files, name of library for library 
- callbacks: passing functions/callbacks to edit parent state. 

Component level state: 
- Each component have their own state. Localized changes. Not the same in redux. 
  
