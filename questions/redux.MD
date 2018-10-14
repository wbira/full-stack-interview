<h1 align="center">
    Redux Interview Questions & Answers
</h1>
<p align="center">
    <img src="https://github.com/monkey3310/full-stack-interview/blob/master/assets/redux.png" alt="Redux Interview Questions & Answers" width="200"/>
</p>

_Note: Keep in mind that many of these questions are open-ended and could lead to interesting discussions that tell you more about the person's capabilities than a straight answer would._

### 1. What is the concept of “single source of truth” in Redux? :star:

<details>
    <summary>
        Answer
    </summary>

The state of your whole application is stored in an object tree within a single store. That is, there are not multiple stores keeping chunks of the entire state of the web application. Having a single store also helps in debugging the app.

</details>

### 2. What are actions in Redux? :star:

<details>
    <summary>
        Answer
    </summary>

Actions are plain JavaScript objects that describe potential changes to the state. They can be thought of as the "intent" to do something. Here are a few example actions:

```js
{ type: 'ADD_TODO', text: 'Go to swimming pool' }
{ type: 'TOGGLE_TODO', index: 1 }
{ type: 'SET_VISIBILITY_FILTER', filter: 'SHOW_ALL' }
```

</details>

### 3. Can functions be an action? :star:

<details>
    <summary>
        Answer
    </summary>

Yes. Libraries like `redux-thunk` allow developers to use functions as actions.

See [redux-thunk](https://github.com/reduxjs/redux-thunk)

</details>

### 4. What are reducers in Redux? :star:

<details>
    <summary>
        Answer
    </summary>

Reducers are pure functions that take the previous state and an action, and return and object that represents the next state. Example:

```js
function handleAuth(state, action) {
    return {
        ...state,
        auth: action.payload
    });
}
```

</details>

### 5. What is `Store` in Redux? :star:

<details>
    <summary>
        Answer
    </summary>

Store is the object that holds the application state. It provides a few helper methods to access the state, dispatch actions and register listeners. The entire store is kept in a single JavaScript object.

Reducers are used to get a new state from an existing state. The new state becomes the store.

</details>

### 6. How is it different from MVC and Flux? :star:

<details>
    <summary>
        Answer
    </summary>

**MVC vs Redux**

- One of the main differences between MVC and Redux is that, while in MVC data can flow in a bidirectional manner, in Redux it strictly moves in one direction.
- In MVC, when applications became more complex, the Controller begins to feel the burden.
The Controller takes the huge responsibility of maintaining both the application state and the data. Also, the cascading updates makes the app really difficult to understand and debug. In the end, you have an application whose results are totally unpredictable.In Redux, this problem is mitigated, and eventually, predictable application state is achieved. When the data flow is unidirectional, changes in the application view layer will trigger an action in the data layer. These changes will then be reflected in the View. The View does not directly affect application data.
- It is often mentioned that an MVC based application has issues with scaling.
While an architecture may be partly responsible for scaling related limitations, it is not the only factor. There are many web applications that are developed using the MVC architecture and are proven to be scalable to meet customer demands.
Having said that, information is the most challenging aspect of a software when it comes to scaling. Redux tackles information scaling well, as it puts information first and foremost, above everything else.

See [redux-vs-mvc](https://blog.gisspan.com/2017/02/Redux-Vs-MVC,-Why-and-How.html)

**Flux vs Redux**

**Flux:** 
- Store contain state and change logic
- Multile stores
- Flat disconnected stores
- Singleton dispatcher
- React Component subscibe to stores
- State is mutated

**Redux:**
- Store and change logic are seperate
- Single store
- Single store with hierarchical reducers
- No dispatcher
- Container components utilize connect
- State is immutable

See [redux-vs-flux](https://www.educba.com/redux-vs-flux/)

</details>

### 7. Why the state is read-only? :star:

<details>
    <summary>
        Answer
    </summary>

Because it's [second of the Three Principles of Redux](https://redux.js.org/introduction/threeprinciples#state-is-read-only). But that's not really a good answer :slightly_smiling_face:.

The real answer is: read-only state makes it easier to track changes of state. Since changes happen only by applying actions to the store there are no race conditions to watch out for - no hidden mutations. Read-only state means that complex deep checks for changes can be replaced with simple shallow comparison, what will allow developers to reduce the complexity of applications.

</details>

### 8. What are action creators and how they differ from actions? :star:

<details>
    <summary>
        Answer
    </summary>

[Action creators](https://redux.js.org/basics/actions#action-creators) are functions that create actions. Since actions are just objects it's convenient to write functions that create them. For example:

```js
function addTodo(text) {
  return {
    type: 'ADD_TODO',
    payload: { text }
  };
}
```

In redux action creators do not dispatch actions - you must wrap them in `dispatch` calls.

```js
dispatch(addTodo('Pass full-stack interview at Google'));
```

</details>

### 9. What are middlewares in Redux?. :star:

<details>
    <summary>
        Answer
    </summary>

`Middleware` generally refers to software services that "glue together" separate features in existing software. For Redux, middleware provides a third-party extension point between dispatching an action and handing the action off to the reducer:

[ Action ] <-> [ Middleware ] <-> [ Dispatcher ]

Examples of middleware include logging, crash reporting, routing, handling asynchronous requests, etc.

Middleware is basically a function that accepts the store, which is expected to return a function that accepts the next function, which is expected to return a function which accepts an action.

Here is an example of logging Middleware:

```js
const loggingMiddleware = store => next => action => {
  // Our middleware
  console.log(`Redux Log:`, action);
  // call the next function
  next(action);
};
```

</details>

### 10. Why do reducer functions have to be pure? :star:

<details>
    <summary>
        Answer
    </summary>

Because it's [third of the Three Principles of Redux](https://redux.js.org/introduction/threeprinciples#changes-are-made-with-pure-functions) :slightly_smiling_face:.

A **pure** function is a function whose result only depends on it's arguments and which has no side effects. For example, pure reducer should work like this:

```js
(previousState, action) => newState;
```

Reducers have to be pure because pure functions are predictable making them easier to debug, test and refactor.

Having impure reducers would mean that application state depends not only on previous state and actions, but on something else. This breakes the **Single Source Of Truth** principle and increases the complexity of your app.

</details>
