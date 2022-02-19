## Event Loop

Basically to understand how JS executes in simple plain words you’ll have to imagine two main blocks they are called call stack and callback queue. And there is a supporting block (lets agree to call it a supporting block) and that depends on the runtime environment ex: in chrome the runtime environment is called V8 engine and the supporting block is called WEBAPIs.

The call stack is how the interpreter usually stacks the code to execute it, first called first interpreted. Also JS by default is synchronously interpreted and sometimes you just don’t want that, such as when you are sending XHR requests or consuming API data there is usually some delay in the response from the server and that might cause unintentional errors such as the delay in the app or Blocking to avoid this firstly the call back queue was introduced which only executes when the call stack is completely empty.

The call back queue solved too many issues but still there are some and to completely solve this the asynchronous functions were introduced, which are functions that only gets popped of the call stack when they are completely finished.

The following figure illustrates how the event loop works in the V8 engines:

![Event Loop illustration](./assets/eventLoop.jpg)
