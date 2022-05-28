# Redux

State management is one of the most important topics in modern web applications.

Redux is a state management library that allows you to manage app level state and gives you the ability to elevate your applications as well as improving your general understanding of building JavaScript UIs.

Redux provides a solid, stable, and mature solution to managing state in your React application.

It helps you write applications that behave consistently.

Redux takes away some of the hassles faced with state management in large applications. You may also have a lot of data changing in your application over time. Redux helps solve these kinds of problems.

If you want to update the state of your Redux application , you need to let Redux know about that with an action then send the action to the reducers.

Reducers are the most important concept in Redux. So, what’s the deal with the Reducer. In more technical terms, a reducer is also called a reducing function.

## Integrating Redux with a UI framework

Using Redux with any UI layer requires the same consistent set of steps:

- Create a Redux store
- Subscribe to updates
- Inside the subscription callback:
  - Get the current store state
  - Extract the data needed by this piece of UI
  - Update the UI with the data
- If necessary, render the UI with initial state
- Respond to UI inputs by dispatching Redux actions

The process of subscribing to the store, checking for updated data, and triggering a re-render can be made more generic and reusable. A UI binding library like React Redux handles the store interaction logic, so you don't have to write that code yourself.
