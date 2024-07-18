# Scalability 

- is the ability of the application to support adding computing resources in order to support additional load without any interruption to the application's activity.

  - In other more simple words, let's say an e-commerce application is deployed on a virtual machine, everything works fine and the application is humming along happily and then Black Friday arrives, a huge low is expected and the CIO believes the current virtual machine won't be able to support the expected load.

- In systems that do not support scalability the following will occur. The applications code will be for code pieces that will not support the expected load. Probably some code fragments will have to be rewritten and the VM will be reinforced, more CPU and more memory.

- As you can guess, this is a long cumbersome process that is never fast enough to respond to actual challenges.

- On the other hand, in systems that do support scalability, the process is much simpler and faster. Add another virtual machine, notify the load balancer about the new virtual machine, and that's it.

- As you can see, no changes were made to the code. It's important to notice the difference between the two types of scalability.

- In the first case, we took an existing VM and added CPU power and memory to it. This is called Scale Up.

- In the second case, we simply added new VMs and did not touch any existing one. This is called Scale Out.

- Now we will always prefer Scale Out over Scale Up. And why that? Because of two very important reasons. 
  - One, redundancy. The more VMs we have, the more we are protected against the VMs crash situation. If you'll have a single, very powerful VM, the application will still won't work if this single server will crash.
  - Two, there is a limit to the CPN memory we can add to a server. If the application consumes a large amount of memory, we'll hit this limit somewhere along the road. On the other hand, there is virtually no limit to the number of VMs we can add to the load balancer thus making the application grow infinitely.

- So the bottom line here is clear. Always opt for scaling out your application. Note that the scale out scenario includes load balancer which is not part of the scale up scenario. Scale out always uses load balancer to distribute the load between the VMs.

- One of the key architectural patterns for supporting scale out scenario is stateless.