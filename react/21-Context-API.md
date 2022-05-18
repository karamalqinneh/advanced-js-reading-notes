# Context API

## React Context

Context provides a way to pass data through the component tree without having to pass props down manually at every level.

In a typical React application, data is passed top-down (parent to child) via props, but such usage can be cumbersome for certain types of props (e.g. locale preference, UI theme) that are required by many components within an application. Context provides a way to share values like these between components without having to explicitly pass a prop through every level of the tree.

React.createContext() is all you need. It returns a consumer and a provider. Provider is a component that as it's names suggests provides the state to its children. It will hold the "store" and be the parent of all the components that might need that store. Consumer as it so happens is a component that consumes and uses the state.

### When to Use Context?

Context is designed to share data that can be considered “global” for a tree of React components, such as the current authenticated user, theme, or preferred language.

### Before You Use Context

Context is primarily used when some data needs to be accessible by many components at different nesting levels. Apply it sparingly because it makes component reuse more difficult.

## useContext Hook

useContext hook takes a context object (object returned by React.CreateContext) as an argument and returns the object passed via value prop of Context.Provider. The current context value is determined by the value prop of the nearest Context.Provider in the component tree in case a component has multiple ancestors dispatching data via Context.Provider.

It should be noted that a component which renders data passed via context API will always re-render when the context value changes. The code below is the functional component equivalent of context.Consumer.

`const myContext = React.useContext(context);`

You can now access the data passed as value attribute of context.Provider using myContext.
