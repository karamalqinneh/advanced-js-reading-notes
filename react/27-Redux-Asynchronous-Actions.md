# Redux - Asynchronous Actions

## Redux Middleware and Side Effects​

It only knows how to synchronously dispatch actions, update the state by calling the root reducer function, and notify the UI that something has changed. Earlier, we said that Redux reducers must never contain «side effects». However, any real app will need to do these kinds of things somewhere. Redux middleware were designed to enable writing logic that has side effects.

## Using the Redux Thunk Middleware​

Redux already has an official version of that "async function middleware", called the Redux "Thunk" middleware. The thunk middleware allows us to write functions that get dispatch and getState as arguments. The thunk functions can have any async logic we want inside, and that logic can dispatch actions and read the store state as needed.

The Redux thunk middleware is available on NPM as a package called redux-thunk.

## Using Middleware to Enable Async Logic

the next examples will show how middleware can enable us to write some kind of async logic that interacts with the Redux store.
One possibility is writing a middleware that looks for specific action types, and runs async logic when it sees those actions, like these examples:

```
import { client } from '../api/client'

const delayedActionMiddleware = storeAPI => next => action => {
  if (action.type === 'todos/todoAdded') {
    setTimeout(() => {
      // Delay this action by one second
      next(action)
    }, 1000)
    return
  }

  return next(action)
}

const fetchTodosMiddleware = storeAPI => next => action => {
  if (action.type === 'todos/fetchTodos') {
    // Make an API call to fetch todos from the server
    client.get('todos').then(todos => {
      // Dispatch an action with the todos we received
      storeAPI.dispatch({ type: 'todos/todosLoaded', payload: todos })
    })
  }

  return next(action)
}
```

## Writing an Async Function Middleware

Here's what that middleware might look like:

Example async function middleware

```
const asyncFunctionMiddleware = storeAPI => next => action => {
  // If the "action" is actually a function instead...
  if (typeof action === 'function') {
    // then call the function and pass `dispatch` and `getState` as arguments
    return action(storeAPI.dispatch, storeAPI.getState)
  }

  // Otherwise, it's a normal action - send it onwards
  return next(action)
}
```

And then we could use that middleware like this:

```
const middlewareEnhancer = applyMiddleware(asyncFunctionMiddleware)
const store = createStore(rootReducer, middlewareEnhancer)

// Write a function that has `dispatch` and `getState` as arguments
const fetchSomeData = (dispatch, getState) => {
  // Make an async HTTP request
  client.get('todos').then(todos => {
    // Dispatch an action with the todos we received
    dispatch({ type: 'todos/todosLoaded', payload: todos })
    // Check the updated store state after dispatching
    const allTodos = getState().todos
    console.log('Number of todos after loading: ', allTodos.length)
  })
}
```

// Pass the _function_ we wrote to `dispatch`
store.dispatch(fetchSomeData)
// logs: 'Number of todos after loading: ###'

## Redux Async Data Flow

Just like with a normal action, we first need to handle a user event in the application, such as a click on a button. Then, we call dispatch(), and pass in
something, whether it be a plain action object, a function, or some other value that a middleware can look for.
Once that dispatched value reaches a middleware, it can make an async call, and then dispatch a real action object when the async call completes.
When we add async logic to a Redux app, we add an extra step where middleware can run logic like AJAX requests, then dispatch actions.
