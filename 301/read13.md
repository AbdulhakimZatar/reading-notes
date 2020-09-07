# Sending Form Data
HTML forms can send an HTTP request declaratively. But forms can also prepare an HTTP request to send via JavaScript, for example via XMLHttpRequest. This article explores such approaches.


## A form is not always a form
With progressive web apps, single page apps, and framework based apps, it's common to use HTML forms to send data without loading a new document when response data is received.


## Sending form data
1.Building an XMLHttpRequest manually.

2.Using a standalone FormData object.

3.Using FormData bound to a <form> element.


### Dealing with binary data
If you use a FormData object with a form that includes <input type="file"> widgets, the data will be processed automatically. But to send binary data by hand, there's extra work to do.