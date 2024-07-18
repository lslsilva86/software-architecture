# Data store technology i

- is one of the more important decisions you will make in the project design.

- where your precious data is going to be stored for the use of the application.

## SQL databases or relational databases

- are the more traditional databases.

- They have been around for almost 40 years and have served the industry well.

- The most popular relation databases are Microsoft SQL Server, Oracle and MySQL. 
- Relational databases have some common characteristics.

- They store the data in tables. 
- Each table stores a specific type of entity and each table has a concrete set of columns, which represent the various properties of the entities.

  - For example, a table demonstrates how a very simplified order entity will be represented in a relational database. Tables can have relationships with each other, hence the relational in the database name.
  - For example, if I have an Orders table, it will probably have also an Order Items table, which will contain the items in the order.

- Each row in the Order Items table relates to a specific order in the Orders table. This relationship is done with the OrderId field of the order item.

- Another characteristic of relational database is transactions.
  
- A transaction represent an atomic set of actions that either executes all the actions or executes none of them.

- There is no way that only part of the actions in the transaction will be executed.

  - For example, if the customer placed an item in the order, the item's stock must be decreased by one. It should never happen that the item was placed, but the stock was not updated. This is a transaction. Transactions are defined with the ACID acronym, which stands for Atomicity, Consistency, Isolation, and Durability. Only a database that supports all these can claim to support transactions. Transactions are one of the most important capabilities of relational database and naturally they are widely used.

- The last characteristic is the querying language. All the relational databases enable querying data using the SQL language. SQL, which stands for Structured Query Language, is a very mature language that was introduced by IBM more than 40 years ago. It allows querying and modifying data in an easy to understand language and is considered the defacto standard for accessing data in relational databases.
  - For example, here is an SQL snippet that demonstrates querying the Orders table for orders that were generated since January 1, 2018.


## NoSQL database

- NoSQL databases try to be the opposite of SQL databases.

- One of the most significant limitations of SQL databases are performance and size. Since relational databases maintains schema for each record and in first transactions, the performance degrade as the database is getting larger and larger. This is a problem the NoSQL movement is trying to solve.

- The greatest strength of NoSQL is the scale and performance. NoSQL databases can become really huge and they are often distributed on many servers. 
  - For example, Baidu, the Chinese search engine, stores more than 300 terabytes on MongoDB, one of the most popular NoSQL databases, and it's not uncommon to look at NoSQL databases with billions of entities. This strength dictate the capabilities of NoSQL databases and the differences between them and traditional SQL databases.

- First of all, NoSQL databases are in general schema-less. What that means is that while SQL databases store the data in a well-defined table with well-defined columns, which defines an actual schema for the entities,

- NoSQL database do not force any schema. They can store completely different entities with completely different fields in the same table.

- Usually these entities are stored as JSON documents and since JSON is a fully-flexible format, you are not limited to a specific field or size.

- This is great if your application is going to store semi-structured or unstructured data, which does not have a concrete schema. In this case, the flexibility offered by NoSQL database is a great advantage.

- about transactions. With NoSQL databases, transaction support is varied. Most databases support a concept called eventual consistency, which means that the database guarantees that the action will be performed, but it will not guarantee when exactly it will be performed. Of course, we are not talking here about minutes and usually not about seconds, but it won't be immediate. This means the code must be able to cope with temporary inconsistencies in the data.

- Why would a NoSQL database support ACID transactions? The answer lies in the NoSQL mission statement. Size and performance. As we mentioned before, transactions are what block relational database from reaching the level of performance required today by huge data consumers and creators, and that's why NoSQL databases support only part of the ACID definition.

- Each database select its own version of transaction support and it's important to look closely at the transaction support of the NoSQL database you are going to work with.

- about querying. Relational databases allow access to their data using the SQL language. SQL is universal language and can be used on any relational database. On the other hand, there is no standard or accessing data in NoSQL database. Each database has its own language and driver and requires its own learning curve.


### summarize

- If your system is not going to be huge, and by huge I mean at least 10 of terabytes, and the data is mostly structured, and if data consistency is important to you, go for traditional SQL databases.

- It doesn't really matter which of them you will take. They're all doing a very good work. Just make sure it's compatible with your development platform and off you go. 
  
- If on the other hand, you are planning to have a huge unstructured data store, opt for the NoSQL database. MongoDB is the most popular NoSQL database at this time with support from every major software vendor, so it's a natural choice.


- Lately, the line between SQL and NoSQL databases has started to blur
and we are seeing various capabilities leak from one type to the other

  - For example, traditionally NoSQL database were great at querying JSON documents, whereas SQL databases, to put it bluntly, just sucked However, we can find today great JSON querying capabilities in databases such as SQL Server and Postgres.

  - Another example is aforementioned transaction support. MongoDB has added full ACID support a few months ago, which was a great breakthrough for the NoSQL database. They claim it won't impact performance and it will be very interesting to see whether other NoSQL vendors will adopt this attitude.