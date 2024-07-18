# Extensibility.

- is a system that its functionality can be extended without modifying its existing code.


  - The API has a specific parameter called format that specifies the exact format of the data to be returned. On day one, the system supports two formats, JSON and XML. Then one day a new requirement is received that requires a new format to be added to the list, CSV. a switch statement that checks what is the required format and executes code accordingly. In a code built like that the new requirement presents a serious problem. We now have to modify a core piece of code and then perform all the tests it requires in order to ensure we didn't screw anything. 
  - In an extensible system, the process is quite different. In such a system, we do not need to modify the original code but rather to extend it.

- By extending, we mean that we can add new code to the application and make it work without modifying the original code.
    - For example, inheritance, plugin framework and more. One of the most common patterns is using a plugin framework with a dependency injection.

- The format name, which is XML, JSON, or CSV, or any other future format is passed to the factory method GetFormatter. The factory method returns an implementation of the IFormatter interface. Note that the calling code has no idea what is the specific implementation that was returned.

