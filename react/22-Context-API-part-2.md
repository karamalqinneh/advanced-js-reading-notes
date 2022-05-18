# Context API

Context (Links to an external site.)
Context allows you to transfer data down the component tree without having to explicitly pass props at each level.

When to Use Context? (Links to an external site.)
Context is used to exchange information that is deemed “global” for a React component tree, such as the current authorized user, theme, or chosen language.When numerous components at various nesting levels need access to the same data, context is employed. It should be used with caution because it makes component reuse more difficult.

Context Update from a Nested Component (Links to an external site.)
It’s common to need to change the context from a component that’s deep down in the component tree. You can pass a function down the context in this scenario to allow consumers to update the context.

Consuming Multiple Contexts: (Links to an external site.)
React needs to create each context consumer a different node in the tree to maintain context re-rendering fast.

## How to use Context API?

- You might think to yourself: "Well, I'm convinced. How do I implement Context API in my app?" First, make sure you need it. Sometimes people use shared state across nested components instead of just passing it as props. And if you do need it you should follow these very few steps:

1. Create a folder under your app root named contexts (not required. just a convention)
1. Create a file named <your context name>Context.js, e.g. userContext.js
1. import and create a context like so:

```
import React, { createContext } from "react";
const UserContext = createContext();
```

4. Create a component that will wrap the provider named Provider e.g. UserProvider
   Example using React Hooks:

```
const UserProvider = ({ children }) => {
  const [name, setName] = useState("John Doe");
  const [age, setAge] = useState(1);
  const happyBirthday = () => setAge(age + 1);
  return (
    <UserContext.Provider value={{ name, age, happyBirthday }}>
      {children}
    </UserContext.Provider>
  );
};
```

5. Create a higher order component to consume the context named: with e.g. withUser
   Example using React Hooks:

```
const withUser = (Child) => (props) => (
  <UserContext.Consumer>
    {(context) => <Child {...props} {...context} />}
    {/* Another option is:  {context => <Child {...props} context={context}/>}*/}
  </UserContext.Consumer>
);
```

- The difference between the two options above is if you want the context to be a single nested property by this name, to explode it to its properties (which in my opinion is more convenient).

6. Finally export them

```
export { UserProvider, withUser };
```

7. And use them however you like
   For example:

```
ReactDOM.render(
  <UserProvider>
    <App />
  </UserProvider>,
  document.getElementById("root")
);
```

```
export default withUser(LoginForm);
```
