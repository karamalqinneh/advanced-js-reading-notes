# useState Hook

Hooks are JavaScript functions, but they impose two additional rules:

- Only call Hooks at the top level. Don’t call Hooks inside loops, conditions, or nested functions.
- Only call Hooks from React function components. Don’t call Hooks from regular JavaScript functions.

## useState

`const [state, updateState] = useState("initial value")`

The useState hook is a special function that takes the initial state as an argument and returns an array of two entries.We can also pass a function as an argument if the initial state has to be computed. And the value returned by the function will be used as the initial state.
useState and setState both are asynchronous. They do not update the state immediately but have queues that are used to update the state object. This is done to improve the performance of the rendering of React components. Even though they are asynchronous, the useState and setState functions do not return promises.
