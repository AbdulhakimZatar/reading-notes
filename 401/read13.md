# Bearer Authorization

## Review, Research, and Discussion

* Write the following steps in the correct order:
* * Register your application to get a client_id and client_secret
* * Ask the client if they want to sign in via a third party
* * Redirect to a third party authentication endpoint
* * Make a request to the access token endpoint
* * Receive access token
* * Make a request to a third-party API endpoint
* * Receive authorization code

* What can you do with an authorization code?
save it in cookies or header to check the authorization of the user.
* What can you do with an access token?
request the user data from third party.
* What’s a benefit of using OAuth instead of your own basic authentication?
Secure and faster for users

## Document the following Vocabulary Terms

* **Client ID**: is a public identifier for apps.
* **Client Secret**: is a secret known only to the application and the authorization server.
* **Authentication Endpoint**: is used to interact with the resource
owner and obtain an authorization grant.
* **Access Token Endpoint**: used by the client to exchange an authorization
grant for an access token, typically with client authentication.
* **API Endpoint**: one end of a communication channel. When an API interacts with another system, the touchpoints of this communication are considered endpoints.
* **Authorization Code**: are used for any transaction or entry that has restrictions on which users are entitled to access.
* **Access Token**: an object encapsulating the security identity of a process or thread.

## Preparation Materials

### JSON Web Tokens
JSON Web Token (JWT) is an open standard (RFC 7519) that defines a compact and self-contained way for securely transmitting information between parties as a JSON object.

#### When should you use JSON Web Tokens?
* Authorization
* Information Exchange

#### What is the JSON Web Token structure?
* Header
* Payload
* Signature

#### How do JSON Web Tokens work?
In authentication, when the user successfully logs in using their credentials, a JSON Web Token will be returned.

#### Why should we use JSON Web Tokens?
As JSON is less verbose than XML, when it is encoded its size is also smaller, making JWT more compact than SAML. This makes JWT a good choice to be passed in HTML and HTTP environments.