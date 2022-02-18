## Event Loop

Basically to understand how JS executes in simple plain words you’ll have to imagine two main blocks they are called call stack and callback queue. And there is a supporting block (lets agree to call it a supporting block) and that depends on the runtime environment ex: in chrome the runtime environment is called V8 engine and the supporting block is called WEBAPIs.

The call stack is how the interpreter usually stacks the code to execute it, first called first interpreted. Also JS by default is synchronously interpreted and sometimes you just don’t want that, such as when you are sending XHR requests or consuming API data there is usually some delay in the response from the server and that might cause unintentional errors
