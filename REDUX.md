# REDUX

We will have project directory structure as:

```
./src
    ./store
        index.js
    App.js
    index.js
```

In root index.js we will not change anything so wherever I say index.js file it means the file inside store directory

# 
In App.js we will have the Components to be displayed to the user.

We will have a counter which we can increment or decrement by one or custom given value

Let's import useDispatch and useSelector from react-redux module

```js
import {useSelector, useDispatch} from "react-redux"
```


#
For now lets leave the App.js for a moment and work on store/index.js

Let's import createStore which ```holds our complete state of tree of our app```

```js
import { createStore } from "redux"
```

Let's create a arrow function (reducer handler) which has state and action as parameters. 

- State parameter holds all the variables given to it in an object format, so we can assign it a Initial value. 
- Action parameter receives the value to it with which we can do some function

```js
const reducerfn = (state = {counter : 0}, action) => {

}
```

We can Switch between action types based on requirements and perform some functionality over it. 

```js
switch(action.type){
    case "inc": return { counter: state.counter + 1 }
    default   : return state //remember to return the same state if no other case satisfies
}
```

Each action has two important objects:

1. action.type
1. action.payload

- type specifies the type of action
- payload contains some data which might be needed to take action based on the payload information

```A payload maybe defined as a tiny data carried out during data transfer```

```js
case "incByNum" : return { counter: state.counter + action.payload }
```

We can now create the Store variable so that we can have a manager of the state and export it

```js
export default const store = createStore(reducerfn)
```

Final code for store/index looks like this:

```js
import { createStore } from "redux";


const reducerfn = (state = { counter: 10 }, action) => {
    switch(action.type){
        case "inc": return { counter: state.counter + 1 }
        case "incByNum": return { counter: state.counter + action.payload }

        default: return state
    }
}


const store = createStore(reducerfn)

export default store
```

#
Now Back to App.js to design the component part,

We can create a counter variable and assign it to useSelector function which has a arrow function like this,

```js
const counter = useSelector((state) => state.counter)
```

The useSelector simply accesses the store component and returns the counter component from it and assigns it to the counter constant

Define and Assign a constant to useDispatch() function:

```js
const dispatch = useDispatch()
```

The useDispatch() returns the redux store

#

Now we need to create function to dispatch the action and use this function on some events.

The dispatch function is called inside the function. The dispatch function contains the action objects like type and payload: 

```js
const increment = () => {
    dispatch({ type: "inc" })
}

const incrementByNumber = () => {
    dispatch({ type: "incByNum", payload: someVariableName })
}
```

And finally we can call these function on some events like this,

```html
<button onClick={ increment } >ADD</button>
```