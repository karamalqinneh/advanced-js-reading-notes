# useReducer

`const [state, dispatch] = useReducer(reducer, initialArg, init);`

An alternative to useState. Accepts a reducer of type (state, action) => newState, and returns the current state paired with a dispatch method. (If you’re familiar with Redux, you already know how this works.)

useReducer is usually preferable to useState when you have complex state logic that involves multiple sub-values or when the next state depends on the previous one. useReducer also lets you optimize performance for components that trigger deep updates because you can pass dispatch down instead of callbacks.

## How does the useReducer Hook work?

The useReducer Hook is used to store and update states, just like the useState Hook. It accepts a reducer function as its first parameter and the initial state as the second.

useReducer returns an array that holds the current state value and a dispatch function to which you can pass an action and later invoke it. While this is similar to the pattern Redux uses, there are a few differences.

For example, the useReducer function is tightly coupled to a specific reducer. We dispatch action objects to that reducer only, whereas in Redux, the dispatch function sends the action object to the store. At the time of dispatch, the components don’t need to know which reducer will process the action.

For those who may be unfamiliar with Redux, we’ll explore this concept a bit further. There are three main building blocks in Redux:

A store: An immutable object that holds the application’s state data A reducer: A function that returns some state data, triggered by an action type An action: An object that tells the reducer how to change the state. It must contain a type property and can contain an optional payload property

## Code Example

```
import {useReducer} from "react"

  const initialState = (
    <>
      <Form
        getFormData={getFormDataHandler}
        dispatch={(action) => {
          dispatch(action);
        }}
      ></Form>
      <div style={{ display: "flex" }}>
        <History
          getHistoryData={renderedData == null ? [] : renderedData}
        ></History>
        <Results getResultsData={resultsData}></Results>
      </div>
    </>
  );


function Example() {

  const [state, dispatch] = useReducer(reducer, initialState);

  const reducer = (state, action) => {
    switch (action.type) {
      case "HOME":
        return initialState;
      case "HISTORY":
        return (
          <History getHistoryData={renderedData == null ? [] : renderedData} />
        );
      case "SUPPORT":
        return <h1>Support will be available soon</h1>;

      default:
        return initialState;
    }
  };

    return (
        <div>
        {state}
        </div>
    )
}



```
