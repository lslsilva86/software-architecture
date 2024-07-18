# Modularity 

- Making your application modular will really help you along the road.

- It will minimize the effort needed to maintain the application and make it much more flexible for changes.

- What exactly is the modular system? a modular system is a system that is built from small, well-defined building blocks that can be changed or replaced without affecting the whole system.
  - For example, let's look at a system that gets data from an API of another system and saves this data into the database. In a non-modular system, both the functionalities of the system, getting the data and saving it in the database, are performed in a single component. This is a easier choice, but also the worst one. Let's assume the external system is replaced by a new system. As a result of this replacement, the API is now different, and the application code that accesses it should be rewritten. 
  - In a non-modular system, this change affects the whole application. Since the application is composed of only a single component, we now need to test all of it and deploy it all over again. We have to think of this small change as if it means we are deploying the system for the first time. We don't have a choice. All of the application is affected.On the other hand, if the application is modular, the code that accesses the API is encapsulated in a small, independent component. If the API on the other system is changed, only this specific component should be changed, leaving the rest of the system intact.

- this results in a much more flexible and maintainable system that allows for short deployment cycles and saves a lot of time when adding or updating components.