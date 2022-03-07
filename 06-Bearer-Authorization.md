# Bearer Authorization

JWT stands for JSON Web Token an it's an open standard which means that every body can use it. It's used to secuerly transfer infromation between any two bodies. JWT is digitally signed which means that the data can't be altered.

The most important aspect of JWT is that it's so compact that you can send it via URL, POST Requests, HTTP Headers, etc. Therefore fast transmission is one of it's main properties.

JWT is also self-contained this means that the token itself contains all the information about the user which leads to not querying the database more than once.

Why to use JWT?

1. authentatction: This is the most common scenario for using JWT. Once the user is logged in, each subsequent request will include the JWT, allowing the user to access routes, services, and resources that are permitted with that token. Single Sign On is a feature that widely uses JWT nowadays, because of its small overhead and its ability to be easily used across different domains.

2. information exchange: JSON Web Tokens are a good way of securely transmitting information between parties. Because JWTs can be signed—for example, using public/private key pairs—you can be sure the senders are who they say they are. Additionally, as the signature is calculated using the header and the payload, you can also verify that the content hasn't been tampered with.

JWT structure

1. Header: is a JSON object that has two props the first one is alg (algorithim) that tells JWT in which algortithim it was encoded and the second one is typ and its simply type of the token (JWT)

2. Payload: is a JSON object that contains claims (claims are user details or additional meta data)

3. Signture: contais base64 Header and base64 payload with secret

### How do JSON Web Tokens work?

In authentication, when the user successfully logs in using their credentials, a JSON Web Token will be returned. Since tokens are credentials, great care must be taken to prevent security issues. In general, you should not keep tokens longer than required. Whenever the user wants to access a protected route or resource, the user agent should send the JWT, typically in the Authorization header using the Bearer schema. The content of the header should look like the following: `Authorization: Bearer` This can be, in certain cases, a stateless authorization mechanism. The server's protected routes will check for a valid JWT in the Authorization header, and if it's present, the user will be allowed to access protected resources. If the JWT contains the necessary data, the need to query the database for certain operations may be reduced, though this may not always be the case.
