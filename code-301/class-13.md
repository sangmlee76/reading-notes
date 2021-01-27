# Read 13 - Notes: Update/Delete

## [Sending Form Data](https://developer.mozilla.org/en-US/docs/Learn/HTML/Forms/Sending_and_retrieving_form_data)

+ This article reviews what happens when a user submits a form, where the data goes and how it is handled upon arrival; also some security concerns associated with sending form data.
  - See [Client-side form validation](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation) for a refresher and a background information to this article.

+ An HTML form on a web page is nothing more than a convenient user-friendly way to configure an HTTP request to send data to a server.
  - This enables the user to provide information to be delivered in the HTTP request.

+ The `<form>` element defines how the data will be sent. All of its attributes are designed to let you configure the request to be sent when a user hits a submit button. The two most important attributes are `action` and `method`.
  - The `action` attribute defines **where** the data gets sent (e.g. absolute or relative URL).
  - The `method` attribute defines **how** data is sent (e.g. `GET`, `POST`).

### `GET` method
+ If a form is sent using the `GET` method the data sent to the server is appended to the URL with the `name = value` attribute pair. This is reflected in the updated URL once submitted.
  - the URL is appended by adding a `?` after the core URL web address and each name=value pair is separated by `&`. For example: `www.foo.com/?say=Hi&to=Mom`

### `POST` method
+ The method the browser users to talk to the server when asking for a reponse that take into accou nt the data provided in the body of the HTTP.


### Viewing HTTP requests
+ HTTP requests are never displayed to the user --> must use dev console:
  - Open the developer tools.
  - Select "Network"
  - Select "All"
  - Select "foo.com" in the "Name" tab
  - Select "Headers"

+ 2 main benefits of using `POST` over `GET`:
  - security (e.g. passwords) -- not visible to general public
  - capacity -- able to send large amounts of data

### Server side: data retrieval
+ There are many other server-side technologies you can use for form handling; however, more common to use one of the many high quality frameworks that make handling forms easier, such as:

  - Django for Python (a bit more heavyweight than Flask, but with more tools and options).
  - Express for Node.js.
  - Laravel for PHP.
  - Ruby On Rails for Ruby.

### Security issues
+ HTML forms are by far the most common server attack vectors (places where attacks can occur). The problems never come from the HTML forms themselves — **they come from how the server handles data.**

+ See this reference article on [website security](https://developer.mozilla.org/en-US/docs/Learn/Server-side/First_steps/Website_security)

**Be Paranoid: never trust your users**
  - watch out for character sequences that look like executable code (such as JavaScript or SQL commands).
  - Limit the incoming amount of data to allow only what's necessary.
  - Sandbox uploaded files. Store them on a different server and allow access to the file only through a different subdomain or even better through a completely different domain.

**Key Takeaway: All data that comes to your server must be checked and sanitized. Always. No exception.**

***

## Additional Resources

1. [HTML5 Forms Reference](https://htmlreference.io/forms/) -- Pay special attention to the “action” and “method” attributes.

+ `action` defines which URL the form's information is sent to when submitted.
  - `"/contact"` : you can use a **relative** URL.
  - `"https://htmlreference.io/contact"` : you can use an **absolute** URL.

+ `method` defines the HTTP method used when submitting the form.
  - `"post"` : the form information is sent to the server as part of the **request body**.
  - `"get"` : the form information is sent ot the server as part of **URL parameters**: `/contact?first_name=Alex&last_name=Smith.`



2. [Video Series on Styling HTML5 Forms](https://www.youtube.com/playlist?list=PL4cUxeGkcC9g5_p_BVUGWykHfqx6bb7qK)
    - This is a 40 minute video series.

***
[<<< Back to Main](https://sangmlee76.github.io/reading-notes/)


