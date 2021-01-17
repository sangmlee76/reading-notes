# Read 07 - Notes: APIs continued

## [How I explained REST to my brother](https://gist.github.com/brookr/5977550)

+ The whole world wide web is built on an architectural style called “REST”. 

+ **REST** provides a definition of a “resource”, which is what those things point to.

+ A web page is a “representation” of a resource. Resources are just concepts. 

+ URLs tell the browser that there's a concept somewhere. A browser can then go ask for a specific representation of the concept. Specifically, the browser asks for the web page representation of the concept.

+ “Web Services” or "APIs" - the basic concept is that machines could use the web just like people do. Computers can use those same protocols to send messages back and forth to each other.

+ **Polymorphism** - different "nouns" can have the same "verb" applied to them (e.g. **GET**)

+ HTTP is all about applying verbs to nouns. For instance, when you go to a web page, the browser does an HTTP **GET** on the URL you type in and back comes a web page.

+ Web browsers generally just "GET stuff". They don't do a lot of other types of interaction with resources. This is a problem because it has led many people to assume that HTTP is just for GETing. But HTTP is actually a general purpose protocol for applying verbs to nouns.

+ Ideally, every URL would have a **human readable** and a **machine readable** representation. When a machine GETs the resource, it will ask for the machine readable one. When a browser GETs a resource for a human, it will ask for the human readable one.

+ Each of the systems would retrieve information from each other using a simple HTTP GET. If one system needs to add something to another system, it would use an HTTP POST. If a system wants to replace something in another system, it uses an HTTP PUT, or, to do a partial update, it'll hopefully use PATCH. The only thing left to figure out is what the data models should look like.

**Reference: notes in this section are direct or summary of content from the [source document](https://gist.github.com/brookr/5977550)**

## [Documentation for SuperAgent](https://visionmedia.github.io/superagent/)

+ SuperAgent is light-weight progressive ajax API crafted for flexibility, readability, and a low learning curve after being frustrated with many of the existing request APIs. It also works with Node.js!


***
[<<< Back to Main](https://sangmlee76.github.io/reading-notes/)

