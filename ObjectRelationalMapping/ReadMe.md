# Object Relational Mapping

The ORM handles how you can persist the state of the business entities as well as how you can retrieve them from a data store. 
These required enterprise patterns resides in the infrastructure code

## Unit of Work 
The Unit of Work pattern is designed to maintain a list of business objects that have been changed by a business transaction, whether that be adding, removing, or updating. The Unit of Work then coordinates the persistence of the changes as one atomic action. If there are problems, the entire transaction rolls back.
## Repository
The Repository pattern, by and large, is used with logical collections of objects, or aggregates as they are better known. It acts as an in-memory collection or repository for business entities, completely abstracting away the underlying data infrastructure.
## Data Mapper 
The Data Mapper pattern is used to hydrate an object from raw data and transfer information from a business object to a database. Neither the business object nor the database is aware of the other.
## Identity Map 
An Identity Map keeps tabs on every object loaded from a database, ensuring everything is loaded only once. When objects are subsequently requested, the Identity Map is checked before retrieving from the database.
## Lazy Loading 
Lazy or deferred loading is the act of deferring the process of obtaining a resource until it’s needed. If you imagine a Customer object with an address book, you could hydrate the customer from the database but hold the population of the address book until the address book is needed. This enables the on-demand loading of the address book, thus avoiding the hit to the database if the address data is never needed.
## Query object 
The Query Object pattern is an implementation of a Gang of Four interpreter design pattern. The query object acts as an object-oriented query that is abstracted from the underlying database, referring to properties and classes rather than real tables and columns. Typically, you will also have a translator object to generate the native SQL to query the database.

