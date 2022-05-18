# React Cookies

Cookies are the data stored in the form of key-value pairs that are used to store information about the user on their computer by the websites that the users browse and use it to verify them.

## `<CookiesProvider />`

Set the user cookies

On the server, the `cookies` props must be set using `req.universalCookies` or `new Cookie(cookieHeader)`

## `useCookies([dependencies])`

Access and modify cookies using React hooks.

```jsx
const [cookies, setCookie, removeCookie] = useCookies(["cookie-name"]);
```

### `cookies`

Javascript object with all your cookies. The key is the cookie name.

### `setCookie(name, value, [options])`

Set a cookie value

- name (string): cookie name
- value (string|object): save the value and stringify the object if needed
- options (object): Support all the cookie options from RFC 6265
  - path (string): cookie path, use `/` as the path if you want your cookie to be accessible on all pages
  - expires (Date): absolute expiration date for the cookie
  - maxAge (number): relative max age of the cookie from when the client receives it in seconds
  - domain (string): domain for the cookie (sub.domain.com or .allsubdomains.com)
  - secure (boolean): Is only accessible through HTTPS?
  - httpOnly (boolean): Can only the server access the cookie? **Note: You cannot get or set httpOnly cookies from the browser, only the server.**
  - sameSite (boolean|none|lax|strict): Strict or Lax enforcement

### `removeCookie(name, [options])`

Remove a cookie

- name (string): cookie name
- options (object): Support all the cookie options from RFC 6265
  - path (string): cookie path, use `/` as the path if you want your cookie to be accessible on all pages
  - expires (Date): absolute expiration date for the cookie
  - maxAge (number): relative max age of the cookie from when the client receives it in seconds
  - domain (string): domain for the cookie (sub.domain.com or .allsubdomains.com)
  - secure (boolean): Is only accessible through HTTPS?
  - httpOnly (boolean): Can only the server access the cookie? **Note: You cannot get or set httpOnly cookies from the browser, only the server.**
  - sameSite (boolean|none|lax|strict): Strict or Lax enforcement

## `withCookies(Component)`

Give access to your cookies anywhere. Add the following props to your component:

- cookies: Cookies instance allowing you to get, set and remove cookies.
- allCookies: All your current cookies in an object.

Your original static properties will be hoisted on the returned component. You can also access the original component by using the `WrappedComponent` static property. Example:

```jsx
function MyComponent() {
  return null;
}
const NewComponent = withCookies(MyComponent);
NewComponent.WrappedComponent === MyComponent;
```

## Cookies

### `get(name, [options])`

Get a cookie value

- name (string): cookie name
- options (object):
  - doNotParse (boolean): do not convert the cookie into an object no matter what

### `getAll([options])`

Get all cookies

- options (object):
  - doNotParse (boolean): do not convert the cookie into an object no matter what

### `set(name, value, [options])`

### `remove(name, [options])`

## Simple Example with React hooks

```js
// Root.jsx
import React from "react";
import App from "./App";
import { CookiesProvider } from "react-cookie";

export default function Root() {
  return (
    <CookiesProvider>
      <App />
    </CookiesProvider>
  );
}
```

```js
// App.jsx
import React from "react";
import { useCookies } from "react-cookie";

import NameForm from "./NameForm";

function App() {
  const [cookies, setCookie] = useCookies(["name"]);

  function onChange(newName) {
    setCookie("name", newName, { path: "/" });
  }

  return (
    <div>
      <NameForm name={cookies.name} onChange={onChange} />
      {cookies.name && <h1>Hello {cookies.name}!</h1>}
    </div>
  );
}

export default App;
```
