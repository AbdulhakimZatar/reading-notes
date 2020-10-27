# Access Control (ACL)

## Review, Research, and Discussion
* When is Basic Authorization used vs. Bearer Authorization?
The Basic and Digest authentication schemes are dedicated to the authentication using a username and a secret.

The Bearer authentication scheme is dedicated to the authentication using a token and is described by the RFC6750. Even if this scheme comes from an OAuth2 specification, you can still use it in any other context where tokens are exchange between a client and a server. 

* What does the JSON Web Token package do?
an open standard (RFC 7519) that defines a compact and self-contained way for securely transmitting information between parties as a JSON object.
* What considerations should we make when creating and storing a SECRET?
* * Never store unencrypted secrets in .git repositories
* * Avoid git add * commands on git
* * Add sensitive files in .gitignore
* * Don’t rely on code reviews to discover secrets
* * Use automated secrets scanning on repositories
* * Store secrets safely
* * Use encryption to store secrets within .git repositories
* * Use local environment variables, when feasible


## Document the following Vocabulary Terms

* **encryption**:process that encodes a message or file so that it can be only be read by certain people. 
* **bearer**:is an HTTP authentication scheme that involves security tokens called bearer tokens. The name “Bearer authentication” can be understood as “give access to the bearer of this token.
* **secret**: is private to you which means you will never reveal that to the public or inject inside the JWT token.
* **JSON Web Token**:is a compact URL-safe means of representing claims to be transferred between two parties.

## Preparation Materials

### RBAC
RBAC is nothing more than the idea of assigning system access to users based on their role within an organization. The system needs of a given workforce are analyzed, with users grouped into roles based on common job responsibilities and system access needs. Access is then assigned to each person based strictly on their role assignment. With tight adherence to access requirements established for each role, access management becomes much easier.

#### Benefits of RBAC?
With the proper implementation of RBAC, the assignment of access rights becomes systematic and repeatable. Further, it is much easier to audit user rights, and to correct any issues identified.

#### RBAC implementation 
* Inventory your systems
* Analyze your workforce and create roles
* Assign people to roles
* Never make one-off changes
* Audit