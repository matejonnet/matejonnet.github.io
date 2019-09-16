Microservice Patterns
=============================================

.footnote[
Matej Lazar
- OpenBlend, RedHat
- https://github.com/matejonnet/
- matejonnet@gmail.com

Tomaž Cerar
- OpenBlend
- https://github.com/ctomc
]



???

Visit [http://matejonnet.github.io/presentations/microservice-patterns/](http://matejonnet.github.io/presentations/microservice-patterns/) to see slides in presentation mode.

---

Agenda
======

### - Quick Pros and Cons of MSA

### - Tipical comminucation channels

### - State

### - Atomic operaton

### - The design



---

Quick Pros and Cons of MSA
=================
- Pros
    - Smaler code base
        - Maintenance
        - New team members omboarding
    - Lose coupling
    - Easier to make them clusterable
        - Stateless
        - Runtime state ?

- Cons
    - Data consistency (DB per service)
    - Complex deployment (requires Orchestration)


---

Tipical comminucation channels
==================
- Request/Response
    - Simple
    - Node failuer ?
        - Istio
    - What about log running ?
- Request/Callback
    - How long to wait ?
    - How to monitor timeout ?
- MQ
    - How long to wait ?
    - How to monitor timeout ?

---

State
==================
- Data state
    - State of completed operations
    - Usually DB
- Runtime state
    - State of potentially long running operations
    - Shared Memory

---

Atomic operaton
==================
- 2PC not an option
- SAGA = Sequence of local transations
- 

---

The design
==================
- Event driven
    - Peer to peer event chain!
        - Example: checkout -> inventory -> payment -> shipping
        - No overview
        - Small change might require multiple service updates
- Using commands
    - Example: checkout -> Order service -> inventory -> Order service -> payment -> Order service -> shipping
    - Don't make CRUD services
    - Centralized Orchestration

---


Thanks
======

### References
- [Events, Flows and Long-Running Services: A Modern Approach to Workflow Automation](https://www.infoq.com/articles/events-workflow-automation/)
- [Pattern: Saga @ microservices.io](https://microservices.io/patterns/data/saga.html)

### Presentation tool used
- https://github.com/gnab/remark/

