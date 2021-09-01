---
title: "How to use useState Hook in ReactJS"
date: 2021-03-29
summary: "How to use useState Hook in ReactJS"
author: "avinash sharma"
image: "/static/images/backend/og.png"
---

# How to use useState Hook in React.js

Hooks were introduced in React version 16.8. In order to replace the `this.state` in Class component.

## Steps of Using useState Hook

### Step 1

We need to import the Hook from react

```js
import { useState } from "react"
```
### Step 2

declare a const variable and assign the useState function as follow 

```js
// conventional way to use sate 
const [state, setState = useState(InitialState);
```
### Step 3

How to set state and use state, The useState Hook returne's two parameters one to set the state and the other to get the state value.

```js
import React, { useState } from 'react';

function Example() {
  // Declare a new state variable, which we'll call "name"
  const [name, setName] = useState("");

  return (
    <div>
      {name&&<p>You {Name}</p>)
      <label for="name">name:</label>
      <input type="text" id="name" name="name" value={name}
        onChange={()=>setName(e.target.value)}/>
    </div>
  );
}
```
Traditional ways of using state, This method is a bit tricky use a the beginning, Becouse it has the key word `this` that make thing complex

```js
class Example extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      name: ""
    };
  }

  render() {
    return (
      <div>
        {name&&<p>You {Name}</p>)
        <label for="name">name:</label>
        <input type="text" id="name" name="name" value={this.state.name}
        onChange={()=>this.setState({name:e.target.value})}/>
      </div>
    );
  }
}
```
