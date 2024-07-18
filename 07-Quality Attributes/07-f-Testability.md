# Testability 

- is the attribute that defines how easy it is to test the application.

- manual testing

   - In this kind as you can expect, the actual tester is sitting in front of the screen and test various functions of the system using the user interface it provides.

  - This type has nothing to do with testability.

- Other types of testing involve code that executes the applications code and not an actual person that executes the system functions. This happens with unit testing and integration testing.

- unit testing, a programmer writes code that tests the application code. This code executes specific method with specific parameters and checks whether the result returned from the method is expected one.

  - For example, let's say we have a method called Add that accepts two parameters an integer named X and an integer named Y. This method should add Y to X and return the result. A typical unit test will cause this method and pass it to numbers, say five and nine. In this case, the unit test will expect to get back the number 14. If that's the case, the test is marked as passed. If not, it's marked as failed.

- integration test is similar, but on larger scale. With integration test, we don't test a specific method but a whole model or flow. We execute a method that will trigger a chain of actions that will result in a specific outcome.
  - For example, a new record in the database and now back to the testability.

- A testable system is a system that is easy to test using unit test and integration test.

- And easy to test system can be identified by two characteristics.
  - One, its method and models are not dependent on other method or models.
  - two, every method is responsible for one and only one action. By making methods independent from each other, we make it extremely easy to test each method in isolation which is exactly what we are trying to achieve using unit tests and by enduring each method is responsible for only one action.

- For example, if the above mentioned ad method will check whether the given numbers are positive, We'll have a problem isolating the Add action and testing it specifically.

- In this case, the correct path is to make the check in a separate method. Let's call it Check for Positive and test it separately.

- The most common techniques to achieve these two characteristics is with dependency injection, often called DI and the single responsibility concept.
