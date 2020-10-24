# Authentication

## Review, Research, and Discussion
* Explain what a “Singleton” is (in Computer Science terms)

Is intended to provide only one instance of itself while facilitating a global point of access.

* Explain how the Singleton pattern can be used with Node modules, specifically with classes.

When trying to decide if you need a singleton-like implementation or not, you need to consider something: how many instances of your classes will you really need? If the answer is 2 or more, then this is not your pattern.
But there might be times when having to deal with database connections that you might want to consider it.

Think about it, once you’ve connected to your database, it might be a good idea to keep that connection alive and accessible throughout your code. Mind you, this can be solved in a lot of different ways, yes, but this pattern is indeed, one of them.


## Document the following Vocabulary Terms

* **Router Middleware**:  fully featured http services and streaming templates without the bloat
* **Dynamic Module Loading**: import/export aim to provide a backbone for the code structure. That’s a good thing, as code structure can be analyzed, modules can be gathered and bundled into one file by special tools
* **Singleton Pattern**: is a software design pattern that restricts the instantiation of a class to one "single" instance. 
* **Mock Testing**: an approach to unit testing that lets you make assertions about how the code under test is interacting with other system modules.

## Preparation Materials

### Securing Passwords
Passwords are the first line of defense against cyber criminals
Cryptographic hash algorithms MD5, SHA1, SHA256, SHA512, SHA-3 are general purpose hash functions, designed to calculate a digest of huge amounts of data in as short a time as possible.

The benefit of hashing is that if someone steals the database with hashed passwords, they only make off with the hashes and not the actual plaintext passwords.

PROBLEMS WITH CRYPTOGRAPHIC HASH ALGORITHM
* Brute Force attack: Hashes can't be reversed, so instead of reversing the hash of the password, an attacker can simply keep trying different inputs until he does not find the right now that generates the same hash value, called brute force attack.

#### BCrypt 
To overcome such issues, we need algorithms which can make the brute force attacks slower and minimize the impact. Such algorithms are PBKDF2 and BCrypt, both of these algorithms use a technique called Key Stretching.

Bcrypt is an adaptive hash function based on the Blowfish symmetric block cipher cryptographic algorithm and introduces a work factor (also known as security factor), which allows you to determine how expensive the hash function will be.

### Basic Auth
basic access authentication is a method for an HTTP user agent (e.g. a web browser) to provide a user name and password when making a request. In basic HTTP authentication, a request contains a header field in the form of Authorization: Basic <credentials>, where credentials is the Base64 encoding of ID and password joined by a single colon :.

It is specified in RFC 7617 from 2015, which obsoletes RFC 2617 from 1999.

HTTP Basic authentication (BA) implementation is the simplest technique for enforcing access controls to web resources because it does not require cookies, session identifiers, or login pages; rather, HTTP Basic authentication uses standard fields in the HTTP header.

### JWT

#### What is JSON Web Token?
JSON Web Token (JWT) is an open standard (RFC 7519) that defines a compact and self-contained way for securely transmitting information between parties as a JSON object. This information can be verified and trusted because it is digitally signed.

JWTs can be signed using a secret (with the HMAC algorithm) or a public/private key pair using RSA or ECDSA.

##### When should you use JSON Web Tokens?
* Authorization
* Information Exchange

#### What is the JSON Web Token structure?
* Header
* Payload
* Signature

#### How do JSON Web Tokens work?
In authentication, when the user successfully logs in using their credentials, a JSON Web Token will be returned. Since tokens are credentials, great care must be taken to prevent security issues. In general, you should not keep tokens longer than required.

#### Why should we use JSON Web Tokens?

As JSON is less verbose than XML, when it is encoded its size is also smaller, making JWT more compact than SAML. This makes JWT a good choice to be passed in HTML and HTTP environments.

Security-wise, SWT can only be symmetrically signed by a shared secret using the HMAC algorithm. However, JWT and SAML tokens can use a public/private key pair in the form of a X.509 certificate for signing. Signing XML with XML Digital Signature without introducing obscure security holes is very difficult when compared to the simplicity of signing JSON.

### bcrypt
A library to help you hash passwords.

`npm install bcrypt`