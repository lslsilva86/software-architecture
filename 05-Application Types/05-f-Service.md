# Services 

- Quite similar to console application with two important distinctions.
  - They have no user interface at all as opposed to the command line window in the console application.
  - They are managed by a service manager which is a feature of the operating systems that manages the services.

- In Windows, there is one service manager. While on Linux, there are handful you can choose from.

- The service manager starts and stops the services and also monitors their activity.

- Since services cannot ask the user about their behaviors, they will usually have a configuration file containing their required parameters.

- Services are used for long running processes such as monitoring folder on the disc when no user intervention is required.