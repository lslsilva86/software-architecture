# Console applications, command line applications - CLI,

- Applications that run inside the command line of the operating system.

- These applications have few common characteristics.

  - They don't have any fancy UI.
  - The only thing the end user sees are the lines of text displayed in the command line window.
  - They requires some level of technical knowledge.

- Console applications are triggered by typing a command in clear text, often with some parameters.

- Normal end users who are accustomed to point-and-click applications 
will have a hard time working with these applications.

- They usually have a very limited interaction with the user, if at all.

- The console application might present some questions to the user in order to configure its behavior, and then will start running.

- This configuration can be set also via command line parameters.

- They can trigger long-running process as well as execute very short, focused actions.

- Console applications are used mainly for 
  - executing long-running processes that do not interact with the end user 
  - short, focused actions such as exporting data,that should be used by specially-trained power users.

- The fact the application is a console application does not change anything to its architecture. All the architectures, patterns, and practices apply also to console applications.