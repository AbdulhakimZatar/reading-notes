# Forms and JS Events

## Forms
HTML borrows the concept of a form to refer to different elements that allow you to collect information from visitors to your site.

### Example of forms
```
<html>
<head>
 <title>Forms</title>
</head>
<body>
 <form action="http://www.example.com/review.php" method="get">
 <fieldset>
 <legend>
 Your Details:
 </legend>
 <label>
 Name:
 <input type="text" name="name" size="30" maxlength="100">
 </label>
 <br />
 <label>
 Email:
 <input type="email" name="email" size="30" maxlength="100">
 </label>
 <br />
 </fieldset>
 <br />
 <fieldset>
 <legend>
 Your Review:
 </legend>
 <p>
 <label for="hear-about">
 How did you hear about us?
 </label>
 <select name="referrer" id="hear-about">
 <option value="google">Google</option>
 <option value="friend">Friend</option>
 <option value="advert">Advert</option>
 <option value="other">Other</option>
 </select>
 </p>
 <p>
 Would you visit again?
 <br />
 <label>
 <input type="radio" name="rating" value="yes" />
 Yes
 </label>
 <label>
 <input type="radio" name="rating" value="no" />
 No
 </label>
 <label>
 <input type="radio" name="rating" value="maybe" />
 Maybe
 </label>
 </p>
 <p>
 <label for="comments">
 Comments:
 </label>
 <br />
 <textarea rows="4" cols="40" id="comments">
 </textarea>
 </p>
 <label>
 <input type="checkbox" name="subscribe" checked="checked" />
 Sign me up for email updates
 </label>
 <br />
 <input type="submit" value="Submit review" />
 </fieldset>
 </form>
</body>
</html>
```

## Events
W hen you browse the web, your browser registers different types of events. It's the browser's way of saying, "Hey, this just happened." Your script can then respond to these events.

### How Events Trigger JS
When the user interacts with the HTML on a web page, there are three steps involved in getting it to trigger some JavaScript code. Together these steps are known as event handling

### Event Listeners
Event listeners are a more recent approach to handling events. They can deal with more than one function at a time but they are not supported in older browsers.