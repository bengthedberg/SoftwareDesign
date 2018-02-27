# Application Layered Design

A multitier architecture or multilayered architecture is a system design that seperate the software into layers based on their responsibilities. 

An application layered architecture provides a model by which developers can create flexible and reusable applications. By segregating an application into tiers, developers acquire the option of modifying or adding a specific layer, instead of reworking the entire application. A three-tier architecture is typically composed of a presentation tier, a domain logic tier, and a data storage tier.

There is no one silver bullet solution for what layers you should implement but generally these are the basic ones:

* **Domain Model Layer**:   
This layer is also called business logic layer and its responsiility is to implement the business logic of the application. 

* **Domain Service Layer**:   

* **Application Service Layer**:  

* **Presentation Layer**:  
ViewModel

* **User Experience Layer**:  
UX

There are also additional parts required for general responsibilities:

* **Repository Layer**:  
This layer is responsible for persisting the data in the domain model.

* **Infrastructure Layer**:  
General responsibilites such as logging, application montoring, authentication, etc
