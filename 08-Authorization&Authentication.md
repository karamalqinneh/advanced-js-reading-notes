## Review, Research, and Discussion

### What header(s) are used in authentication and authorization?

The Authentication Header.

### What is safe to put into a JWT?

The best practice is to use the userame as in case of any attacks no sensitive data would be leaked.

### How are JWTs validated?

JWTs are signed so they can't be modified in transit. When an authorization server issues a token, it signs it using a key. When the client receives the ID token, the client validates the signature using a key as well

## Terms :

- RBAC: (Role-Based Access control) is a method of modifying resources based on the roles of individual users within a website or web application.

- User Roles: Permissions given to the users.

- JWT Token : json web token is an encoded data (used to transfer data between two bodies and authentication) the server generates it once the user sign in(sign up) and it stored in the user's browser which will be used for the user's accessability on the website.

## Preview

1. Which 3 things had you heard about previously and now have better clarity on?

- Tokens, authentication + autherazation and ACL.

2. Which 3 things are you hoping to learn more about in the upcoming lecture/demo?

- More layers of secuerity of the JWT.

3. What are you most excited about trying to implement or see how it works?

- How to use the token to personlize the frontend for the client.
