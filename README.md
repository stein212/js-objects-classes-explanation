# Javascript Objects and Classes

## Overview

-   What are objects and why do we use them
-   Classes and how they make development clearer
    -   Data structure integrity
    -   Reusability
    -   Extensibility
-   Mini Exercise

---

## What are objects and why do we use them

> Objects in JavaScript, just as in many other programming languages, can be compared to objects in real life. The concept of objects in JavaScript can be understood with real life, tangible objects. - [Mozilla Developer Network](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Working_with_Objects)

Think of objects as a dictionary; as in a words with their definition

![image of dictionary](./assets/dictionary.png)

As you can see, a dictionary contains a bunch of words with their definition.

Javascript objects also operate in a similar fashion with keys and values

```js
// We create a new Object and assign it to myDog
let myDog = new Object()

// Now imagining it as a dictionary, we can assign 'words' with their 'definition' or more accurately, assign properties with their value

// set the property 'name' on 'myDog' to be 'cat'
myDog.name = 'cat'
// set the property 'color' on 'myDog' to be 'brown'
myDog.color = 'brown'
// set the property 'age' on 'myDog' to be '5'
myDog.age = 5
```

Where did the property come from? It is created on the spot when we defined it. So prior to `myDog.name = 'cat';`, `name` does not exist.

[![Node my dog example](./assets/node-myDog-example.gif)](./assets/node-myDog-example.mp4)

```js
// We can do the same thing with square brackets
let myDog = new Object()
myDog['name'] = 'cat'
myDog['color'] = 'brown'
myDog['age'] = 5
```

So from this, you can see that there a 2 ways to access / set the property of an object: using the `.` or `[]` operators.

```js
// We can also use the object literal which is preferred
let myDog = {}
myDog.name = 'cat'
myDog.color = 'brown'
myDog.age = 5

// OR all at once

let myDog = {
    name: 'cat',
    color: 'brown',
    age: 5,
}

// We can still add on to myDog
myDog.favoriteFood = 'bone'
```

[//]: # 'Throughout the examples, show the actual code in action along with its current state, probably use vscode debugger to show it'

Throughout these examples, you can see that I am using objects in javascript to kind of define what my dog is. That is the idea behind javascript objects, which is to mimic real world features in.

### A Todo list in code

Imagine that we need to model how a todo list works with javascript. How might we do something like that?

From our understanding in todo lists, we know that it basically boils down to a list of tasks that are either 'Done' or 'Not Done'

Let's make a simple todo object

```js
let todo = {}
todo.name = 'Make a todo list in javascript'
todo.done = false

// {
//     name: 'Make a todo list in javascript',
//     isDone: false
// }
```

As you can see, our object is modelling how a todo in real life might look like. It contains the name of the todo, along with the state of the todo (isDone)

Now this is just 1 todo, we have to make a list of them so.

```js
// Make a list
let todoList = []

// Make our first todo
let todo1 = {}
todo1.name = 'Task 1'
todo1.isDone = false

// Add it to the list
todoList.push(todo1)

// Make our second todo
let todo2 = {
    name: 'Task 2',
    isDone: true,
}

// Add it to the list
todoList.push(todo2)

// Create our third todo and add it directly to the list
todoList.push({
    name: 'Task 3',
    isDone: true,
})

// [
//   { name: 'Task 1', isDone: false },
//   { name: 'Task 2', isDone: true },
//   { name: 'Task 3', isDone: true }
// ]
```

From this example, you see that we can also directly create and pass objects to functions.

In fact if we wanted to we could have just created the whole list directly and skip all the `.push()` functions

```js
let todoList = [
    { name: 'Task 1', isDone: false },
    { name: 'Task 2', isDone: true },
    { name: 'Task 3', isDone: true },
]
```

---
