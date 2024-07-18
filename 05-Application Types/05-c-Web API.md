# Web API 

- Quite similar to web app with two important differences.

  - 1. It does not serve HTML pages but data, usually in the form of JSON structure.

  - 2. It's clients are not web browsers but other applications including JavaScript codes that runs inside web browser.

- Web API has become extremely popular in the last few years and almost every web app expose also Web API,

- Web API, exposes an API, application programming interface, which allows other programs to access it and execute various actions.

- There are various types of web API implementation, but the most popular one by large margin is definitely the REST API.

  - REST API is a huge topic with a lot of philosophy and the thinking. REST allows us to access entities with a combination of URL parameters and HTTP verb.

  - The main advantage of REST is that it does not require more than a standard URL to execute the API and it does not require cumbersome protocols on top of the HTTP protocol, as was with the SOAP protocol

- Web APIs are used for data retrieval and receiving. It should not be used for returning visual markup such as HTML. For this reason, almost any kind of application can be a client of web API, any code that can access REST API, almost every language supports that capability, can access web API and use it.

- This is the reason that web APIs are used by web apps, rich client apps, and other systems.

- Web API applications are best for 

  - Systems that require data retrieval and store, though not huge amount of data in each action, client initiated actions, meaning the caller is the one making the request to do something, such as getting all the data, saving username and so on.

  - Large scale, with a large number of users and a lot of data, and short, focused action, as opposed to long running processes.

- Web API and web apps are built on the same concepts and usually share the same underpinnings. 
  
- With web apps, web API also works best in the request-response model and should be used for this kind of systems. Long running processes should be avoided when using web API.