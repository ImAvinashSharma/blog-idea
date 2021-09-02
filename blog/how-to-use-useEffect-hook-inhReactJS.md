---
title: "How to use useEffect Hook in ReactJS"
date: 2021-09-02
summary: "The next hook which is useEffect this, Article is going to be an introduction to useEffect. We will take a look at a few examples and dive deeper into the details of the useEffect hook."
author: "Avinash Sharma"
image: "/static/images/backend/og.png"
---
# How to use useEffect Hook in React.js

The next hook which is `useEffect` this, Article is going to be an introduction to useEffect.

We will take a look at a few examples and dive deeper into the details of the useEffect hook.

Understanding the motivation for useEffect, If you've been working with class components you would have performed side-effects in your components

for example updating the Dom fetching data
from an API endpoint and setting up

subscriptions or timers since the render

the method would be too early to perform

side-effects you had to make use of the

life cycle methods for example consider

updating the document title to the

current counter value on initial render

Do you want to set the document title to

clicked zero times so this code goes in

component did mount which is executed

only once in the component lifecycle we

then would have a button to increment

the count state value but when count

value increments we also need to update

the document title again and for that we

add the same piece of code in component

did update lifecycle hook this lifecycle

the method is called anytime the component

updates and is perfect for updating the

document title now let's consider

another side effect let's go with a

timer on component did mount we set up a

timer to log to the console the string

```js
componentDidMount() {
    document.title = `You clicked ${this.state.count} times`;
  }
  componentDidUpdate() {
    document.title = `You clicked ${this.state.count} times`;
  }
```





hello every 5 seconds we can clear this

timer when the component is being

removed from the DOM and we do that in

the component will unmount lifecycle

method so our component code is complete

and everything works as expected

but you start to wonder if it can be

better here's the first thing to observe

to update the document title we are

writing the same code twice once in

component did bound and once in

component did update exact same code but

twice

the second thing to observe is how the

code is together or split apart the code

related to the timer set interval and

the clear intervals which is related are put

into different code blocks that there's

different lifecycle methods the code to

update the Dom and set an interval which

are completely unrelated are put

together wouldn't it be nice to not

repeat code and at the same time group

together only the related code well that

is well the effect hook comes into

picture the effect hook lets you perform

side effects in functional components

while addressing the problems we just

discussed it is a close replacement for

component did mount component did update

and component will unmount that's right

three lifecycle methods can be handled

by the useEffect hook now that we know

why the useEffect hook was introduced

and what it does the next step is to

learn how to use it

so in the next video let's start by

understanding how we can use the effect

hook to set the document title on

initial vendor of the component as well

as subsequent renders when the component

updates


```js
import React, { useState, useEffect } from 'react';

function Example() {
  const [count, setCount] = useState(0);

  // Similar to componentDidMount and componentDidUpdate:
  useEffect(() => {
    // Update the document title using the browser API
    document.title = `You clicked ${count} times`;
  });

  return (
    <div>
      <h1>You clicked {count} times</h1
      >
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}
```
