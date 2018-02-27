# CQRS Command and Query Responsibility Segregation

Many people have been getting confused over what CQRS is. They look at CQRS as being an architecture; it is not. CQRS is a very simple pattern that enables many opportunities for architecture that may otherwise not exist. CQRS is not eventual consistency, it is not eventing, it is not messaging, it is not having separated models for reading and writing, nor is it using event sourcing.

Starting with CQRS, CQRS is simply the creation of two objects where there was previously only one. The separation occurs based upon whether the methods are a command or a query (the same definition that is used by Meyer in Command and Query Separation, a command is any method that mutates state and a query is any method that returns a value).

Hence the fundamental idea is that we should divide an object's methods into two sharply separated categories:

* **Queries**  
Return a result and do not change the observable state of the system (are free of side effects).
* **Commands**  
Change the state of a system but do not return a value.
Because the term 'command' is widely used in other contexts I prefer to refer to them as 'modifiers', you also see the term 'mutators'.

The really valuable idea in this principle is that it's extremely handy if you can clearly separate methods that change state from those that don't. This is because you can use queries in many situations with much more confidence, introducing them anywhere, changing their order. You have to be more careful with modifiers.

CQRS naturally fits with some other architectural patterns.

* As we move away from a single representation that we interact with via CRUD, we can easily move to a task-based UI.
* CQRS fits well with event-based programming models. It's common to see CQRS system split into separate services communicating with Event Collaboration. This allows these services to easily take advantage of Event Sourcing.
* Having separate models raises questions about how hard to keep those models consistent, which raises the likelihood of using eventual consistency.
* For many domains, much of the logic is needed when you're updating, so it may make sense to use EagerReadDerivation to simplify your query-side models.
* If the write model generates events for all updates, you can structure read models as EventPosters, allowing them to be MemoryImages and thus avoiding a lot of database interactions.
* CQRS is suited to complex domains, the kind that also benefit from Domain-Driven Design.

In particular CQRS should only be used on specific portions of a system (a BoundedContext in DDD lingo) and not the system as a whole. In this way of thinking, each Bounded Context needs its own decisions on how it should be modeled.