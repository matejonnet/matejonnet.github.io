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

### - Atomic operations

### - The design



---

Quick Pros and Cons of MSA
=================
- Pros
    - Smaler code base
        - Maintenance
        - New team members omboarding
    - Lose coupling
    - Scalabillity
        - Stateless
            - clusterable by default
        - Runtime state ?

- Cons
    - Data consistency (DB per service)
    - Complex deployment (requires Orchestration)


---

Tipical comminucation channels
==================
- Request/Response
    - Simple
    - Node failure ?
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

Atomic operations
==================
- 2PC not an option
- SAGA = Sequence of local transations
    - compensation
    - atomic commit and notification 
     

---

Orchestration and Choreography
==================
- Choreography (Event driven)
    - Peer to peer event chain!
        - No overview
        - Small change might require multiple service updates
- Orchestration (Using commands)
    - Don't make CRUD services
    - Centralized Orchestration

[Diagram](https://www.draw.io/?lightbox=1&highlight=0000ff&edit=_blank&layers=1&nav=1&title=MSA-orchestration-vs-choreography.drawio#R7VpJU9swFP41OcJYcmKHYxNoe%2BjCkHaAU0fYiq2iWK6sbPz6yra8RQkISqLAlAvR07OW973d7rnj2eoTR2n8lYWY9qATrnrueQ9CAMGZ%2FJdT1iXF8%2FslIeIkVEwNYUIesCI6ijonIc46jIIxKkjaJQYsSXAgOjTEOVt22aaMdndNUYQ1wiRAVKdek1DEJXU4cBr6Z0yiuNoZOGpmhipmRchiFLJli%2BRe9NwxZ0yUv2arMaa58Cq5lM993DFbH4zjRJg8EHhX05GfLb3Ryfzn9a8x%2Ffanf6LAyMS6ujAO5f3VkHERs4gliF401BFn8yTE%2BaqOHDU8XxhLJRFI4m8sxFqBieaCSVIsZlTNygPz9Y16vhjc5oPTQTU8X7Unz9dqVJ41P%2BBOEShSxuY8wI%2Fcu1IlxCMsHuGDNVBSwzGbYXke%2BRzHFAmy6J4DKVWLar4GDflDAfIMcAblugtE52qnHvSoPO4oJAv5M8p%2FJngpeRgPMa9m5WYtBg1hgVeiCwjHGXlAdwVDLuiUkUQUtxmMeoNzSUGURIkkBFLSciN3tMBcEGkmH9TEjIRhoR0U3WE6QsF9VOjJmFHGi33dafFXnyhfAa96W4xYnaQxnTbCu9VYh0mtfuKcAqiEue5saIyjWvsyF0yLhU2nmdSfTaDrI7wce6Bhfzm%2FoySQtKuLyQ8N1MYoc0CXMRF4kqLCBpbSM3fx3gmAZko7ZQoqbJRAh2q4bJxkzRK3HKTn7MlYfE1gEWNhVoCcYb6QsrHg6l7RZUFDl%2BXZdFlQQ4EkC3lVpta2qbKeY6Cy4IAqe6YJK0VrO3qKV0TcNEFYjm5bM008zgd7CMeeoW4Pbeq2p7tktJ7ldz02zQZDYFm1q%2FS9JawsJmlqSbvrhPPUr5PM2%2Fbk%2FjPOoaGK70D6MCo%2B1FDbknFOJJCl2hulm7aNwb6fB3oyN44ZxyzKa2Y9MOoJeiY4u8dVLp2wJDeLKaF0g2Sepm%2FDoWtnrwDFZpLY15Hob8kR4d6AgHa9T7fchU%2FVu1VQrsJw%2B7FDRGXQN%2FRZ0GqZDFwTr%2FW%2FTq4N4H0Vyn09LTvqSrm%2FxQsetlQGemPpGGrl2k%2BCrp%2F0Tf2k0%2FGT%2FuH8pGn5YtlP6gXM8Rbn263koFmb3lGyX54%2FR8NbVY%2FnDJ9T9hSjS8yJlGQexV7dYEyLIcsGo5dDx1rxD%2FrWK369m3UMFf9biyUQGpoG2PHO40B9Xr2%2F8%2FY7BZ71mAP1TsF3HsRY1v8SVJZoInvHrQLLvQLo2gz0zyr5X9xgsOK37L6fsvPBQ%2F12xTd%2FvfK2ULX6ZgZ6VnOMl%2Fb1nFPX8zuGfjZ0H9cJOdhjXm4Md%2BsDJhtww0eipIxxtvMK1zu2jg%2FUOz7HkJy3bcWoLq0NxykL2tpwPOBbNRzH1HD%2BtaDd6K9WGudvaNzZoLtEeQP1VKNM2kJw8MRC5Q21hZ7u5sph861jyd58Mepe%2FAU%3D)


---


Thanks
======

### References
- [Events, Flows and Long-Running Services: A Modern Approach to Workflow Automation](https://www.infoq.com/articles/events-workflow-automation/)
- [Pattern: Saga @ microservices.io](https://microservices.io/patterns/data/saga.html)
- [Event-Driven Orchestration: Effective Microservices Integration Using BPMN and AMQP](https://dzone.com/articles/event-driven-orchestration-an-effective-microservi)

### Presentation tool used
- https://github.com/gnab/remark/

