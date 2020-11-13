# Read 13 - Notes: Local Storage

Source article: [The past, present, and future of local storage for web applications](http://diveinto.html5doctor.com/storage.html)

## Overview
+ Persistent local storage (a.k.a. DOM storage) is one of the areas where native client applications have held advantage over web applications.
+ **Cookies** were invented early in the web's history and can be used for persistent local storage of small amounts of data.
+ Downside of cookies:
  - they are included with every HTTP request, thereby slowing down your web application
  - they are included with every HHTP request, thereby sending data unencrypted over the internet
  - they are limited to about 4 KB of data (but enough to slow down your application)
+ Desired state:
  - lots of storage space
  - on the client
  - persists beyond a page refresh
  - isn't transmitted to the server

### HTML 5 Storage
+ Standard is defined under [Web Storage](https://html.spec.whatwg.org/multipage/webstorage.html)
+ HTML 5 storage is a way for web pages to store named key/value pairs locally, within the client web browser.
  - this data persists even after you navigate away from the web site, close your browser tab, exit your browser, etc.
  - it is never transmitted to the remote web server (unless manually sent)
  - implemented natively in web browsers, so it is available even when third-party browser plugins are not
+ Accessed through the `localStorage` object on the global `window` object.
+ To check for HTML 5 storage, use the following code in the `<head>` element of your HTML:
```
<script scr="modernizr.min.js"></script>
```

### Using HTML5 storage
+ Data is stored as **strings** If you are storing something other than a string, you'll need to coerce it yourself when you retrieve it
  - for conversion to boolean, manually construct the boolean value
  - for numbers, use `parseInt`
+ The [Indexed Database API](https://w3c.github.io/IndexedDB/) exposes an *object store*. It has similiar features as SQL. The primary difference is that the object store has no structured query language.
  - instead of using statements like: "SELECT * from USERS where ACTIVE = 'Y'", you use methods provided by the object store to open a cursor on the database named "USERS", then use accessor methods to get the values of each field in the record.
+ Good tutorial of [IndexedDB](https://hacks.mozilla.org/2010/06/comparing-indexeddb-and-webdatabase/) shows a side-by-side comparison of IndexedDB and Web SQL database.

### Further Reading
1. [Web Storage API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API)
2. [Indexed Database API 3.0](https://w3c.github.io/IndexedDB/
)


*****
[<<< Back to Main](https://sangmlee76.github.io/reading-notes/)