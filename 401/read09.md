# API Server

## Review, Research, and Discussion
* How does route prefixing work with an external routing module?
Route grouping is a concept to make the route function that receive same prefix of different requests.
The route is being handle from route group.

* When routing, what’s the difference between app.get('/data/:id') and app.get('/data/:name')?
The diffrence in request pararms

* Explain how Express handles routing conflicts?
Routes are processed by Express in order

* What are the ways that a browser can send “data” or request variables to an HTTP server
Ajax, jQuery methods, fetch, Axios and forms

## Document the following Vocabulary Terms
* **Routing**: How an application’s endpoints (URIs) respond to client requests.
* **Route Prefixing**: Is a concept to make the route function that receive same prefix of different requests.
* **Request “Body”**: Data sent by the client to your API.
* **Request “Query”**: This property is an object containing a property for each query string parameter in the route. 
* **Request “Params”**: This property is an object containing properties mapped to the named route “parameters”.

## Preparation Materials

### express router.param() middleware
Adds callback triggers to route parameters, where name is the name of the parameter and callback is the callback function.

The parameters of the callback function are:

* req, the request object.
* res, the response object.
* next, indicating the next middleware function.
* The value of the name parameter.
* The name of the parameter.

For example, when :user is present in a route path, you may map user loading logic to automatically provide req.user to the route, or perform validations on the parameter input.

```js
router.param('user', function (req, res, next, id) {
  // try to get the user details from the User model and attach it to the request object
  User.find(id, function (err, user) {
    if (err) {
      next(err)
    } else if (user) {
      req.user = user
      next()
    } else {
      next(new Error('failed to load user'))
    }
  })
})
```

Param callback functions are local to the router on which they are defined. They are not inherited by mounted apps or routers.

### mongoose middleware
Middleware (also called pre and post hooks) are functions which are passed control during execution of asynchronous functions.

#### Types of Middleware
* document middleware
* model middleware
* aggregate middleware
* query middleware.

##### Use Cases
Middleware are useful for atomizing model logic. Here are some other ideas:

* complex validation
* removing dependent documents (removing a user removes all his blogposts)
* asynchronous defaults
* asynchronous tasks that a certain action triggers

#### Post middleware
post middleware are executed after the hooked method and all of its pre middleware have completed.

### Subdocuments
Subdocuments are documents embedded in other documents. In Mongoose, this means you can nest schemas in other schemas.

#### Subdocuments versus Nested Paths
In Mongoose, nested paths are subtly different from subdocuments.

#### Finding a Subdocument
Each subdocument has an _id by default. Mongoose document arrays have a special id method for searching a document array to find a document with a given _id.

### mongoose virtual joins
Using mongoose virtuals, you can define more sophisticated relationships between documents.

```js
const PersonSchema = new Schema({
  name: String,
  band: String
});

const BandSchema = new Schema({
  name: String
});
BandSchema.virtual('members', {
  ref: 'Person', // The model to use
  localField: 'name', // Find people where `localField`
  foreignField: 'band', // is equal to `foreignField`
  // If `justOne` is true, 'members' will be a single doc as opposed to
  // an array. `justOne` is false by default.
  justOne: false,
  options: { sort: { name: -1 }, limit: 5 } // Query options, see http://bit.ly/mongoose-query-options
});

const Person = mongoose.model('Person', PersonSchema);
const Band = mongoose.model('Band', BandSchema);

/**
 * Suppose you have 2 bands: "Guns N' Roses" and "Motley Crue"
 * And 4 people: "Axl Rose" and "Slash" with "Guns N' Roses", and
 * "Vince Neil" and "Nikki Sixx" with "Motley Crue"
 */
Band.find({}).populate('members').exec(function(error, bands) {
  /* `bands.members` is now an array of instances of `Person` */
});
```

#### Populate Virtuals: The Count Option
Populate virtuals also support counting the number of documents with matching foreignField as opposed to the documents themselves. 

#### Populate in Middleware
You can populate in either pre or post hooks. 
