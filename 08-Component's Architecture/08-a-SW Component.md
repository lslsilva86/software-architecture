# components' architecture

- Software component, also sometimes known as service, is a piece of code that runs in a single process, which means it is not distributed.

- Modern systems are usually distributed, meaning they are composed of independent software components deployed on separate processes, and often on separate containers or servers.
  - microservices application
  - server application
  - and more.

- All these systems are distributed systems that have components or services deployed independently and which communicate via some kind of network protocol, usually HTTP.

- two levels of architecture.

  - the components' architecture.
    - This is architecture of the individual components. The components' architecture deals with the various inner components of the code, the way they interact with each other, and how to make it fast and easy to maintain.

  - the architecture of the whole system.
    - This kind of architecture deals with the bigger picture and makes sure the system is scalable, reliable, fast, and easy to maintain.

- the architect should never distance himself from the code and he should be able to have an intelligent discussion about coding, patterns, and programming as a whole. It is because of this reason that the architect must be at least aware of the inner workings of the individual components and must be able to make sure his design supports the bigger picture of the system.