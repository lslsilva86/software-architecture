# manageability 

- is the ability to manage the application. Simply put, it's the ability to know what's going on with the application at any given time, and to take actions that will improve its work.

  - For example, a manageable application will constantly report its status to monitoring agent and let them know when errors occur, when there is an exceptionally high load, when the RAM is becoming dangerously high and so on. The monitoring agents report this back to a management console and then a decision can be made either automatically or by a human operator to take some action such as retrying the process that caused the error or adding resources to cope with the load and with the wrong situation.

- The best way to differentiate a manageable system from one that is not is by finding out who is the one that reports problems.
  - If it's the end user, then the system is not manageable, and as a side effect, we have made your users a QA team,
  - On the other hand, if the system itself report problems, the experience is much better. The system will find out a problem is going to occur.
    - For example, a mass of request is received in a very short time and the response time degradates substantially. As a result, the system alerts the monitoring agent about it and the operator decides to add more VMs to support that load. The end result is that the users don't even know there is a problem and the system is just humming alone happily.