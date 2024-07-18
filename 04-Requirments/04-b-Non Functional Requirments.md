# Non Functional Requirments

- Functional requirements define what the system should do

- Non-functional requirements describe what the system should deal with.

  - Systems can deal with many challenges during their operation.
  - They can experience large number of concurrent users.
  - They can experience server crash.
  - They can suffer extremely high load of requests and so on.

- Non-functional requirements basically describe what is expected environment for the system, with emphasis on edge cases.

## Performance

### always talk in numbers 
- What is fast?
  - Fast can mean a lot of things in a lot of systems.

- One systems fast meant 30 milliseconds, and another systems fast meant five seconds.

- The problem is that your client probably wasn't thinking on the exact number and you will have to help him with that.

- The rule of thumb

  - When there is an end user at the end of the flow, we usually need the task to be complete in less than a second. When working in a B2B environment we are usually looking at faster systems that can measure even 100 milliseconds per task.

  - The reason for that is that we human beings are less sensitive to sub-second delays, and for us, a data that is displayed in one second or 700 milliseconds looks almost the same, while for a software running on a machine with CPU cycles of few milliseconds, this will be a very long time.

- The most important thing is to work out this number together with a client or system analyst.
  
### latency and throughput

- Define the way we look at performance and give us two points of view on it.

- Latency answers the question, how much time does it take to perform a single task in the application?

  - For example, how much time will it take for the API to save the user data in the database?

  - Or, how much time will it take to read a single file from the file system?

- The latency deals with the time it takes to perform a single task.


- Throughput, on the other hand, answers a completely different question.

  - How many tasks can be performed in a given time unit?

  - For example, how many users can be saved in the database in a minute or how many files can be read in a second?


Let's say the latency of saving user data is one second. This is quite slow, but let's stay with this for the sake of the discussion.
Now, what would be the throughput?
Can we know how many users can be saved in one minute?
The answer is a resounding no.
If the application is well-designed, deployed on a strong hardware and knows its way around threads, it might have a throughput of 1000 users saved in one minute.

On the other hand, if the code is buggy and there are a lot of memory leaks and no concurrency at all, we want to be able to reach a throughput of 60, which is a latency multiplied by 60, the number of seconds in a minute.

So this is the difference between latency and throughput, and when discussing performance, both of them must be mentioned and set.

## Load.

- The load or quantity of work the application you have to withstand without crashing.

- The exact definition of load depends on the exact type of the application.

  - For example, for a web API-based application, the load will usually be defined as how many concurrent requests are going to be received by the system without crashing.

  - Note that this requirement looks similar to throughput which defines how many requests can be handled in a specific time unit.

- The difference between the two is that while throughput defines the time unit, the load defines the availability of the system, meaning the system should be able to handle the load without crashing down.

  - For example, the performance requirement can dictate throughput of 100 requests per second, but the system should be able to handle 500 concurrent requests without crashing, even if those requests will take more than a second to complete.

- This definition is important since the worst thing that can happen to a system is to crash under heavy load.

- Users can tolerate a slowdown when there is a load, but they won't like it if the system will crash and burn.

- So the best practice here is to always look at peak numbers.

  - For example, for an e-commerce website, the regular load might be up to 200 concurrent requests, but on Black Friday, we are looking at more than 2000 concurrent requests. In that case, we should plan for the extreme case, because this is when it's more important for our system to be alive and functioning.

## Data volume

- How much data in gigabytes or terabytes our system will accumulate over time.

- It'll dictate what kind of database we're going to use since not all databases can handle large quantities of data equally.

- It'll also determine what type of queries we're going to write because a query in a table of 100,000 rows will be completely different from a query in a table of 100 million rows.

- It'll help us plan ahead the storage we need to allocate.

- The data volume usually has two aspects.

  - 1. How much data is required on day one
  - 2. what is a forecasted data growth?

For example, a system might need 500 megabytes on its first day and is expected to grow by two terabytes annually.

Of course, the growth period can be different and can be weekly, monthly, quarterly, and so on.

## Concurrent users.

- How many users will be using the system simultaneously.

- Quite similar to the load requirement which also defines how many requests should be handled by the system simultaneously, but with one big difference.

- The concurrent users requirement describes how many users will be using the system, not how many users will be performing requests.

- When a user is using a system, there are a lot of dead times when no action is actually taken.

  - For example, a user is asking the system to display all the data. The system executes an API that goes to the database and retrieves the data.

  - This is an actual action. Now, the user is looking at the data. During this time, the system is doing nothing. The API is not working. The database just sits there and the network is silent. Systems that can hold 500 concurrent requests will be able to withstand a much higher number of concurrent users.

- The rule of thumb says that concurrent users are 10 times the number of concurrent requests.

  - So if the system should work with 500 concurrent requests, it can support 5,000 concurrent users. But this number actually depends on the type of system and the usage pattern.

## Service Level Agreement

- What is the required uptime for this system in percentage. 
  
- This term is widely used by almost all public cloud providers. One of the biggest competitions between them is on the SLA.

  - For example, Azure Cosmos DB takes pride with its 99.99% SLA. This is translated to less than an hour of downtime in a year.

- The SLA has great influence on the design of the system.

  - For example, a system that cannot be brought down must have a sophisticated update mechanism that won't require turning of the system while it's updating. This is possible, of course, but it has to be designed this way.

- One important thing to note about SLA is client expectations.

  - If you'll ask the client what is a required SLA for the system, he will usually give you an answer along the lines of 100% or the famous five nines, which is 99.999%. When this happens, I usually tell him, no problem. For this, we'll need to build at least three data centers in different continents with independent and dual power stations, and automatic failover between them. What do you say? This generally brings him down to earth and we discuss more realistic SLA goals.


### Never start working on the architecture before you have set those requirements.


### Who

- Most of the time, the client has no idea about non-functional requirements and what the consequences of those requirements are.

  - Eg. "What is the SLA for the system?" Assuming he knows what an SLA is, the client will usually say, "Always." When asked, "What is the required response time for the API?" The answer will be somewhere around 10 milliseconds.

- The architects

  - 1. Frame the boundaries.
    - We must explain the client that 100% uptime is not realistic and probably not really needed. We must explain to him that his current network will not enable completing an API call in less than 100 milliseconds. And after we have done all this, we can talk about possible values,

  - 2. Backed by real numbers.
    - For example, when talking about concurrent users, try to calculate the real number of concurrent users. Don't pull numbers out of a hat.Also, try to set realistic goals for the performance requirement.

- If the system is going to be used by end users, you don't need to fight for every millisecond. The users won't notice that.