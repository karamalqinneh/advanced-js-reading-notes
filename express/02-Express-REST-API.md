# Express-REST-API

## Middleware

The request object is used to describe a request to a server. While the response object represents the HTTP response that an Express app sends when it gets an HTTP request.

Middleware is a function that execute after the server receives the request and before the controller action sends the response, but there are a few more things that are specific to middleware. The biggest thing is that middleware functions have access to the response (res) and request (req) variables and can modify them or use them as needed. Middleware functions also have a third parameter which is a next function. This function is important since it must be called from a middleware for the next middleware to be executed. If this function is not called then none of the other middleware including the controller action will be called.

1. Application-level middleware
2. Router-level middleware
3. Error-handling middleware
4. Built-in middleware
5. Third-party middleware
   1. Specifying a Service Type
   2. Invoking operations
   3. Encoding the Response
   4. Application Middleware

You can consider the route handlers as a middleware as they have access to both the req and res objects

### Application Middleware

### Routing Middleware

Routing middleware is middleware determining how an application responds to a client request to a particular endpoint

```
app.get('/', routingMiddleware[function])

```

Or you can use a more advanced Router-level middleware to handle this such as Router in Express.

### What can cause express to error with “Request headers sent twice, cannot start a second response”?

The error "Error: Can't set headers after they are sent." means that you're already in the Body or Finished state, but some function tried to set a header or statusCode. When you see this error, try to look for anything that tries to send a header after some of the body has already been written. For example, look for callbacks that are accidentally called twice, or any error that happens after the body is sent.

In other words there is another middleware (routeHandlerFunction) trying to edit the response after the first one has already sent a one.

# Resources

1. [How To Use And Write Express Middleware](https://blog.webdevsimplified.com/2019-12/express-middleware-in-depth/)
2. [Routing](https://expressjs.com/en/guide/routing.html)
3. [Error: Can't set headers after they are sent to the client](https://stackoverflow.com/questions/7042340/error-cant-set-headers-after-they-are-sent-to-the-client)
