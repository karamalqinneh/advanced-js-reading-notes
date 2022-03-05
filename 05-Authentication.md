# Authentication

## Singleton

Singleton is a creational design pattern that lets you ensure that a class has only one instance, while providing a global access point to this instance.

### To use a Singleton design pattern:

1. Make the default constructor private, to prevent other objects from using the new operator with the Singleton class.
2. Create a static creation method that acts as a constructor. Under the hood, this method calls the private constructor to create an object and saves it in a static field. All following calls to this method return the cached object.
   _If your code has access to the Singleton class, then it’s able to call the Singleton’s static method. So whenever that method is called, the same object is always returned._

## Authentication

### Securing Passwords with Bcrypt Hashing Function

Everybody knows it is dummy to store your passwords in plain text in databases. As you are vulnerable to any types of attacks you'll shelter to the hashing techniques but you'll still be vulnerable to these two attacks:

1. Brute Force attack: Due to advancments in GPU capabilities you can randomly generate hashed values by iterating over all the possiablities of the input.
2. Hash Collision attack: Hash functions have infinite input length and a predefined output length, so there is inevitably going to be the possibility of two different inputs that produce the same output hash.

To overcome these obstacles BCrypt was introduced. Bcrypt is an adaptive hash function based on the Blowfish symmetric block cipher cryptographic algorithm and introduces a work factor (also known as security factor), which allows you to determine how expensive the hash function will be.

### The OWASP Cheat Sheet Series was created to provide a concise collection of high value information on specific application security topics.

### Authentication General Guidelines:

1. Authentication Solution and Sensitive Accounts
2. Implement Proper Password Strength Controls
3. Implement Secure Password Recovery Mechanism
4. Store Passwords in a Secure Fashion
5. Compare Password Hashes Using Safe Functions
6. Transmit Passwords Only Over TLS or Other Strong Transport
7. Require Re-authentication for Sensitive Features
8. Consider Strong Transaction Authentication
9. Protect Against Automated Attacks
10. Use of authentication protocols that require no password¶
