Questions
====
1.Scope of systems you own and the impact of your work?
**Problem**

Current payment application is a complex and heavily coupled monolith. It does various functionalities which are distinct in nature. 
These can be clearly divided but due to the nature of layered architecture we have Business logic heavily coupled to maintain the transaction integrity, 
this has caused complex coupling. 
Time has come to refactor the payment application. We have chosen to go the route of Modular Monoliths to do so. 

**Approach**
Rails Engines are an architectural pattern that can be used to modularize a Rails application. 
They are self-contained applications that can be mounted within a larger Rails application. 
Rails Engines are essentially mini-applications that can be plugged into a larger Rails application. 
They allow you to modularize your code and keep it separate from the core application. 
This makes it easier to maintain and update the codebase as a whole. 
In the end state of gateway an functionally different component would be encapsulated into an engine and engines would be talking with each via a strictly defined APIs by passing the business objects that will be shared via gems


**Phase1**:
Phase 1 introduces Packwerk-backed mini-modules to a large Rails payments monolith because the system is too large and entangled to correctly identify bounded contexts upfront. By mechanically grouping code into model/module-sized components, we create immediate structure, improve navigability and ownership, and expose real dependency patterns. This low-risk step establishes a concrete component map and dependency baseline, 
enabling informed boundary definition and deeper refactoring in later phases without destabilizing the system.

