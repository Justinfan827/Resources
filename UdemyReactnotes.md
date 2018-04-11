# Personal notes from learning React

## Day 1(Lesson 1 - 16) (1 hour): Lets go! Learn React :)

# General React notes: 
- React is a JS library
- Components: snippets of code that produces HTML
  - Multiple Components: Nest them to make complex applications

#ES6 modules: Normally, files cant refer to variables in other files.
- Importing React: Even if React is installed in dependencies, it still needs to be imported i.e. import the module React to get access in the file. 
'''
import React from 'react'
'''
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
  there can't be conflicting names for libraries. I.e. NEED TO USE RELATIVE PATH. 
 
Classes (Creating components with ES6 classes)
- extends React.Component
- Define method on class called render(). Every class based component needs this render() method. 
State 
- Use Class Components

Event handler: 
- 
