# OAuth

## Review, Research, and Discussion

* Why is authentication important?

To secure the web app.

* Why should we be careful about storing a user’s password?

If any leak happened to db, nothing happen.

* What is the difference between hashing and encryption?

Encryption is a two-way function; what is encrypted can be decrypted with the proper key. Hashing, however, is a one-way function that scrambles plain text to produce a unique message digest.

* What is the difference between encryption and encoding?

Encoding is for maintaining data usability and can be reversed by employing the same algorithm that encoded the content, i.e. no key is used. Encryption is for maintaining data confidentiality and requires the use of a key (kept secret) in order to return to plaintext.

* What is a token used for?

A security token is a peripheral device used to gain access to an electronically restricted resource.


## Document the following Vocabulary Terms

* **authentication**:the act of proving an assertion, such as the identity of a computer system user. In contrast with identification,

* **authorization**: the function of specifying access rights/privileges to resources, which is related to information security and computer security in general and to access control in particular.

* **encryption**:process that encodes a message or file so that it can be only be read by certain people.

* **hashing**:Function is any function that can be used to map data of arbitrary size to fixed-size values. 

* **session**: temporary and interactive information interchange between two or more communicating devices, or between a computer and user.

* **cookie**:are text files with small pieces of data — like a username and password — that are used to identify your computer as you use a computer network.

* **token**:single element of a programming language.

* **Basic Auth**: method for an HTTP user agent (e.g. a web browser) to provide a user name and password when making a request.

* **encoding**: the process of converting data from one form to another.

* **secret**: secret key is private to you which means you will never reveal that to the public or inject inside the JWT token.

* **cryptography**: method of protecting information and communications through the use of codes, so that only those for whom the information is intended can read and process it.

## Preparation Materials

### OAuth
OAuth is an open standard for access delegation, commonly used as a way for Internet users to grant websites or applications access to their information on other websites but without giving them the passwords.[1] This mechanism is used by companies such as Amazon,[2] Google, Facebook, Microsoft and Twitter to permit the users to share information about their accounts with third party applications or websites.

#### OAuth Examples
The simplest example of OAuth in action is one website saying “hey, do you want to log into our website with other website’s login?” In this scenario, the only thing the first website – let’s refer to that website as the consumer – wants to know is that the user is the same user on both websites and has logged in successfully to the service provider – which is the site the user initially logged into, not the consumer.

#### OAuth Explained
OAuth is about authorization and not authentication. Authorization is asking for permission to do stuff. Authentication is about proving you are the correct person because you know things. OAuth doesn’t pass authentication data between consumers and service providers – but instead acts as an authorization token of sorts.

#### OAuth 1.0 vs. OAuth 2.0
* OAuth 2.0 is a complete redesign from OAuth 1.0, and the two are not compatible. If you create a new application today, use OAuth 2.0. This blog only applies to OAuth 2.0, since OAuth 1.0 is deprecated.

* OAuth 2.0 is faster and easier to implement. OAuth 1.0 used complicated cryptographic requirements, only supported three flows, and did not scale.

* OAuth 2.0, on the other hand, has six flows for different types of applications and requirements, and enables signed secrets over HTTPS. OAuth tokens no longer need to be encrypted on the endpoints in 2.0 since they are encrypted in transit.
