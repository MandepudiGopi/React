# React
- React is a JavaScript library for building user interfaces.

- React is used to build single page applications.

- React allows us to create reusable UI components.

## React Introduction

### What is React?

- React is a JavaScript library created by Facebook.

- React is a tool for building UI components.

### How does React Work?
- Instead of manipulating the browser's DOM directly, React creates a virtual DOM in memory, where it does all the necessary manipulating, before making the changes in the browser DOM.

> React only changes what needs to be changed!

- React finds out what changes have been made, and changes only what needs to be changed.

- You will learn the various aspects of how React does this in the rest of this tutorial.

### React.JS History
- Current version of React.JS is V16.8.6 (March 2019).

- Initial Release to the Public (V0.3.0) was in July 2013.

- React.JS was first used in 2011 for Facebook's Newsfeed feature.

- Facebook Software Engineer, Jordan Walke, created it.

- The create-react-app version 2.0 package was released in October 2018.

- Create-react-app version 2.0 supports Babel 7, webpack 4, and Jest23

### Setting up a React Environment.

- If you have NPM and Node.js installed, you can create a React application by first installing the create-react-app.

> If you've already created the create-react-app you can skip this section.

- Install create-react-app by running this command in your terminal:

> C:\Users\Your Name>npm install -g create-react-app

- Then you are able to create a React application, let's create one called myfirstreact.

- Run this command to create a React application named myfirstreact:

> C:\Users\Your Name>npx create-react-app myfirstreact

- The create-react-app will set up everything you need to run a React application.

> C:\Users\Your Name>cd myfirstreact

- Run this command to run the React application myfirstreact:

> C:\Users\Your Name\myfirstreact>npm start

- A new browser window will pop up with your newly created React App! If not, open your browser and type localhost:3000 in the address bar.

##### The result:

![the results](https://www.w3schools.com/REACT/screenshot_myfirstreact.png)

### Modify the React Application

- So far so good, but how do I change the content?

- Look in the myfirstreact directory, and you will find a src folder. Inside the src folder there is a file called App.js, open it and it will look like this:

#### /myfirstreact/src/App.js:

import React, { Component } from 'react';

import logo from './logo.svg';

import './App.css';

class App extends Component {

  render() {
  
    return (
    
      <div className="App">
      
        <header className="App-header">
        
          <img src={logo} className="App-logo" alt="logo" />
          
          <p>
          
            Edit <code>src/App.js</code> and save to reload.
            
          </p>
          
          <a
          
            className="App-link"
            
            href="https://reactjs.org"
            
            target="_blank"
            
            rel="noopener noreferrer"
            
          >
          
            Learn React
            
          </a>
          
        </header>
        
      </div>
      
    );
    
  }
  
}


export default App;



- Try changing the HTML content and save the file.

- Example
- Replace all the content inside the <div className="App"> with a <h1> element.

- See the changes in the browser when you click Save.

import React, { Component } from 'react';

class App extends Component {

  render() {
  
    return (
    
      <div className="App">
      
        <h1>Hello World!</h1>
        
      </div>
      
    );
    
  }
  
}


export default App;

![hello](https://www.w3schools.com/REACT/screenshot_helloworld.png)


### React Components

- Components are like functions that return HTML elements.

#### Create a Class Component

- When creating a React component, the component's name must start with an upper case letter.

- The component has to include the extends React.Component statement, this statement creates an inheritance to React.Component, and gives your component access to React.Component's functions.


- The component also requires a render() method, this method returns HTML.

##### Example
- Create a Class component called Car

class Car extends React.Component {

  render() {
  
    return <h2>Hi, I am a Car!</h2>;
    
  }
  
}

- Now your React application has a component called Car, which returns a <h2> element.

> To use this component in your application, use similar syntax as normal HTML: <Car />

- Display the Car component in the "root" element:

> ReactDOM.render(<Car />, document.getElementById('root'));

### Create a Function Component

- Here is the same example as above, but created using a Function component instead.

- A Function component also returns HTML, and behaves pretty much the same way as a Class component, but Class components have some additions, and will be preferred in this tutorial.

#### Example

- Create a Function component called Car

function Car() {

  return <h2>Hi, I am also a Car!</h2>;
  
}


- Once again your React application has a Car component.

- Refer to the Car component as normal HTML (except in React, components must start with an upper case letter):

### Component Constructor

- If there is a constructor() function in your component, this function will be called when the component gets initiated.

- The constructor function is where you initiate the component's properties.

- In React, component properties should be kept in an object called state.

- You will learn more about state later in this tutorial.

- The constructor function is also where you honor the inheritance of the parent component by including the super() statement, which executes the parent component's constructor function, and your component has access to all the functions of the parent component (React.Component).

#### Example

- Create a constructor function in the Car component, and add a color property:


class Car extends React.Component {

  constructor() {
  
    super();
    
    this.state = {color: "red"};
    
  }
  
  render() {
  
    return <h2>I am a Car!</h2>;
    
  }
  
}

> Use the color property in the render() function:

### Example
class Car extends React.Component {

  constructor() {
  
    super();
    
    this.state = {color: "red"};
    
  }
  
  render() {
  
    return <h2>I am a {this.state.color} Car!</h2>;
    
  }
  
  }
  
  
###  Props

- Another way of handling component properties is by using props.

- Props are like function arguments, and you send them into the component as attributes.

- You will learn more about props in the next chapter.


### Example

- Use an attribute to pass a color to the Car component, and use it in the render() function:

class Car extends React.Component {

  render() {
  
    return <h2>I am a {this.props.color} Car!</h2>;
    
  }
  
}


ReactDOM.render(<Car color="red"/>, document.getElementById('root'));
 
 


### Components in Components

- We can refer to components inside other components:

#### Example

- Use the Car component inside the Garage component:

class Car extends React.Component {

  render() {
  
    return <h2>I am a Car!</h2>;
    
  }
  
}


class Garage extends React.Component {

  render() {
  
    return (
    
      <div>
      
      <h1>Who lives in my Garage?</h1>
      
      <Car />
      
      </div>
      
    );
    
  }
  
}

ReactDOM.render(<Garage />, document.getElementById('root'));

### Components in Files

- React is all about re-using code, and it can be smart to insert some of your components in separate files.

- To do that, create a new file with a .js file extension and put the code inside it:

> Note that the file must start by importing React (as before), and it has to end with the statement export default Car;.


### Example

- This is the new file, we named it "App.js":

import React from 'react';

import ReactDOM from 'react-dom';


class Car extends React.Component {

  render() {
  
    return <h2>Hi, I am a Car!</h2>;
    
   
}

}


export default Car;


- To be able to use the Car component, you have to import the file in your application.


#### Example

- Now we import the "App.js" file in the application, and we can use the Car component as if it was created here.

import React from 'react';

import ReactDOM from 'react-dom';

import Car from './App.js';

ReactDOM.render(<Car />, document.getElementById('root'));
