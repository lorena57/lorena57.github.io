---
layout: post
title:      "Stateful and Stateless"
date:       2020-11-21 05:50:29 +0000
permalink:  stateful_and_stateless
---


So what's the difference?  

Stateful components has a state while stateless doesn't.  Stateful components keep track of changing data while stateless components typically render the same thing.  

Stateful components allow you to use `this.state` within the component as well as react hooks and lifecycle methods while stateless components don't allow you to.  

So when should you use a stateful component versus a stateless component?

If you intend of using dynamic data it it recommended that a stateful component is used so that you can share properties with the children components.  But.....if you don't need to to have a state then stateless is that way to go.

Example of Stateful component
```
import React, {Component} from 'react';

class Ideas extends Component {
	constructor() {
super()
this.state = {
ideas: []
}
}

render() {
	return (
		<div>
			<h1>I'm a stateful component</h1>
		</div>
)
}
}
```

Example of a stateless component
```
import React from 'react';

const Idea = () => {
	return (
		<div>
			<h1>I'm a stateless component</h1>
		</div>
)
}
```

