Day 1: Lets go! Learn React :)

Lesson 6 notes: 
- React is a JS library
- Components: snippets of code that produces HTML
- Multiple Components: Nest them to make complex applications

Lesson 8 notes: 
- ES6 modules: other files cant refer to variables in other files.
-   Even if React is installed in dependencies, still need to import React i.e. import the module and get access in the file.
- React / React DOM: React starting to diverge into two libraries
-   React DOM library: functionality to render on the DOM.
-   React library: functionality to create/ manage components.

Error:  Invalid component element. Instead of passing a component class, make sure to instantiate it by passing it to React.createElement.
- When we create a component, we create a class of the component. 
- Make sure to pass instance of class to DOM. i.e. render(App)

JSX: JSX tag calls createElement. Component name is component class, but JSX turns it into component instance.
- i.e. <App /> (self closing tag) : this creates an App component instance. 

"container" is the root node of the React App. 

1 Component per file!
const: variables that dont change

npm install --save <package>: save <package> to package.json file. 

Exploring modules
- explicitly declare connections between JS files. 
- export default <Component>
- When importing javascript files (that we write), need file reference to file we're trying to import. Not necessary for libraries, since
  there can't be conflicting names for libraries. 
Classes

State 
