---
layout: post
title:      "Props & State"
date:       2020-12-14 07:24:59 +0000
permalink:  props_and_state
---


Props:

What are props and why are they used? Props are properties that are used for passing data from a parent component to a child component. Props are used to show content and to react to user interaction.  

```
class Parent extends React.Component {

        //to set a prop, call the child component within the Parent componemt and set the properties
		//name is the name of the prop while "Lorena" is the value of the prop
		 
            <Child name="Lorena" />
			<Child name="Nancy" />
			<Child name="Alice" />
}
```

To consume the prop information an argument to is set to the Child component with the argument of props

```
const Child = (props) => {
     console.log(props)
          return (
		     <div>
	  		<p>{props.name}</p>
			 </div>
		 
		 )
}
```

To view the props with the console you can console.log(props) within the component and see that there are 3 objects that display keys and values that have been assigned.

The steps within the child component are:

1. Child component will look at the props object
2. The props object will see that there is a name property listed and take that property name and stick it in the p element.


State:

State is a JavaScript object that contains data that is relevant to a singular component.  State can be used in class components and functional components but....in order to use state in a functional component hooks are required.

When should state be used and how is it used?

State is a object in React where values of properties are stored that belong to the specific component.

Example:

```
class ExampleOne extends React.Component {
     constructor(props) {
		 super(props);
		 
		 this.state = { 
		   person: " Lorena"
		 };
		 }
		 
		 render() {
		  return (
			<div>
			<h1>Hello, my name is {this.state.name}</h1>
			
			//Output:  Hello, my name is Lorena
			
			</div>
			)
		 }
}
```


1. State must be initialized when a component is created
2. State can only be updated using the function 'setState'

Example of how to change the state

```
class ExampleTwo extends React.Component {
     constructor(props) {
		 super(props);
		 
		 this.state = { 
		   person: " Lorena"
		 };
		 }
		 
		 changeName = () => {
		  this.setState( {name: "Bart} )
		 }
		 
		 render() {
		  return (
			<div>
			 <p>
          Hi I'm {this.state.name}
        </p>
        <button
          type="button"
          onClick={this.changeName}
        >Change name</button>
        >
			
			</div>
			)
		 }
}


//Output: Hi I'm Bart
```

So what's the difference between state and props?

State can be changed while props is just a way of passing data.












