# Domain-Driven Design

LINK

## Key Takeaways

* <https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215>

## Notes

### Putting the domain model to work

* Every map / model is bad but useful for the context it is in today.
* Do not keep model abstract from implementation - they go hand-in-hand.

#### The utility of a model in domain-driven design

* Traits of a model
  1. The model and the ehart of the design shape each other
  2. The model is the backbone of a language used by all team members.
  3. The model is distilled knowledge.

#### The heart of software

* Every person has a different perspective and therefore considers different factors to know what is "good enough". Proactively communicate and probe to understand those differences and align around if they are worth favoring or not. Do not let one person's perfection get in the way of good enough at the team level.

### Crunching knowledge

* The customer is often not great at software engineering - talk through problems, not lines of code.
* Have engineers and domain experts build the model together in real time together.
* Ignore details which are not yet important / relevant - let the model incrementally emerge.

### Ingredients of effective modeling

1. Binding the model and the implementation
2. Cultivating a language based on the model (i.e. nomenclature)
3. Developing a knowledge-rich model (e.g. define rules)
4. Distilling the model - focus on the essential, not everything
5. Brainstorming and experimenting

### Knowledge crunching

* Knowledge trickling in one direction is a practice small (i.e. handoffs); programmers and domain experts must accumulate knowledge together.

### Continuous learning

* We don't know how much we don't known (unknown-unknowns) so working with others, particularly domain experts, helps fill those gaps.
* Oral traditions (i.e. knowledge) is lost when teams break up, people move around, etc. - teams are inherently leakly.
  * The solution is collective knowledge through collective learning; not silos, hero programmers, or documentation.

### Knowledge-rich design

* Find the "nouns", but also the rules and business activities for those nouns.

### Extracting a hidden concept

* Use service objects to make policies / rules clear (e.g. `OverbookingPolicy.isAllow(voyage, cargo)`)
  * Naming communicates something more than just a single line of code

### Deep models

* Models evolve as we learn; sometimes that means even the business problem we started out with changes.

### Communication and the use of language

* Language around the model is critical and informs how people collaborate and how the code is ultimately written.
* If only a few members of the team know how to bridge the domain <> code gap, they become an information bottle neck (i.e. process smell)
  * Everybody must understand the model (perhaps to various different levels of detail but collectively nonetheless)
  * Cost of translation multiplied by risk of misunderstanding is way to high
* Language should be reflected in the code (i.e. function names match domain rules)
* Reject the use of any terms or structures that are awkward or inadequate to convey domain understanding
  * Eliminate ambiguity or inconsistency from the language.

### Modeling out loud

* "When people are talking, they naturally discover differences in interpretation and the meaning of their words, and they naturally resolve those differences."
* Leverage both audio and visio-spacial capabilities to model domains - writing requirements is a process smell (i.e. information flowing one way) and prone to mis-communication.

### One team, one language

* People are smart and capable of learning (unless proven otherwise) - create a single language that programmers, product owners, etc. use; do not leave room for mis-communication.
* Languages / models evolve with time, understanding, and nuance - start somewhere and always be willing to evolve.
* "Multiple languages is often necessary, but the linguistic division should never be between the domain exports and the developers."

### Documents and diagrams

* When in doubt, draw it out!
* The model is not the design, just a tool to help communicate, brainstorm ideas, and drive alignment.

### Written design documents

* Documents should complement code and speech.
* XP asks for no documentation; only code which is unambiguous vs written words.
* "A document shouldn't try to do what the code already does well. The code already supplies the detail."
* Documents should clarify intent which cannot be communicated cleanly through code.
* "Documents should work for a living and stay current"
  * Most documents are short lived snap shots filled with vacation pictures (i.e. if you weren't there you don't get it) which means they fall out of usefulness quickly.
* "A document must be involved in project activities"
  * Oudated documents lead to confusion.
* Don't be afraid to delete documentation.

### Executable bedrock

* Code should communicate intent, but this is not always easy and not always current: ruthlessly refactor to keep things current and expressive.

### Explanatory models

* Keep drawings simple and goal specific; you don't have to describe how the world works.
* You can visualize the same information in different ways and sometimes those different ways better communicate the intent (e.g. Challenger O-rings)

### Binding model and implementation

* A good model is tightly coupled to the implementedion.
* "...crucial discoveries always emerge during the design/implementation effort." - design is emergent / evoling
  * Rarely from the start do you never know all the information you need to complete the work - you discover it along the way.
* "If the managers perceive analysis [models] to be a separate process, the development team may not be given adequate access to domian experts."
* There is a difference between thinking how to do something and actually doing something; the "analysis model" is created independently of the code / implementation and does not create opportunities for feedback based on learnings while coding.

### Modeling paradigms and tool support

* Reference: Prolog lanuage for model driven design (competitor to object orientated programming)
* Domain driven designs have clean interfaces which are easier to unit test.

### Letting the bones show: Why models matter to users

* Try to avoid building meaningless abstractions around common tools / interfaces. Just expose the underlying abstraction to the user or create something new and unique to your domain.

### Hands-on modelers

* Do not silo people; leverage all their expertise / capabilities throughout every aspect of the buisness.
* Programmers own the model - somebody should not dictate it to them.
  * Also, the model is influenced by infastructure, deployments, etc. - they are tightly coupled.
* Require everybody be a generalist, but that doen't mean they can't still be specialized - it just means they somewhat understand the whole picture through hands on practical experience.

### The building blocks of a model-driven design

* Reference: "Responsibility driven design"
* If domain driven design doesn't feel like it is working, it is likely an issue with the domain model and not the practice.

### Isolating the domain

* In object orientated programming UI, database, UI behavior, and more are often written directly into the object. This often results in requests to change how the UI works to also change how the buiness rules themselves.
* In a layered architecture, things only depends on things in the same or a lower layer: never a higher layer.
* Four common layers:
  * UI / presentation layer - show relevant information
  * Application layer - cooridnates tasks / delegates work to domain objects to take and resolve requests.
  * Domain / model layer - the state and rules of the system / product.
  * Infrastructure layer - technical capabilities to make the above layers work and communicate with each other.

### Relating the layers

* Keep things loosely coupled by using pub-sub models to communicat across layers.

### Architectural frameworks

* Using tools and frameworks which keeps the domain model adaptable to change; sometimes emergent frameworks seem cool but straitjacket an application in the long run.

### The domain layer is where the model lives

* Pitfall of Smart UIs (where business logic exists in both the UI and elsewhere) is that
  * Business rules must be duplicated across stacks. Those stacks may be frontend Node, frontend Python, backend Go you must replicate the logic in each stack so the only way to reconcile state is ultimiately to hit the database.
  * Create lock-in - you can't pivot to a new technology without a complete rewrite or starting to adapt a more layed approach.

### Other kinds of isolation

* People will mess up your domain model for the sake of speed, a lack of awareness, or perhaps a different mindset.

### A model express in software

* "A SERVICE is something that is done for a client on request."
* Three ways to make associations more tractable:
  1. Imposing a traversal direction
  2. Adding a qualifier, effectively reducing multiplicity
  3. Eliminating nonessential associations
* A bi-directional association means the objects are tightly coupled and can only be understood together: not independently.
* Hunt for natural hierachies / traversal directions (e.g. a File belongs to a User)

* "Does the user of the application care if I am the same person I ws at age five?"
* An ENTITY is an abstract continuitity threading through a lifecycle and even passing through multiple forms.
  * An ENTITY is consistent and unique to something, even as that something changes.
  * Example: A customer may change their name, phone number, preferred email address, etc. but the "Customer" ENTITIY in your system should remain the same (but perhaps with updated attributes).
* ENTITY values, traits, characteristics, attributes, etc. revolve around who the entity is describing / tracking vs the values in the attributes themselves.
* When an object is distinghuiushed by its identity, rather than its attributes, keep the definition simple and focused on lifecycle continuitity and identity.
* "The model must define what it means to be the same thing."
  * E.g. A seat number in a theater is a unique way to identify a physical seat in a theater; this seat number must be unique to the seat.

* "... the most basic responsibility of ENTITIES is to esatblish continuity ..."
* An identifying attribute must be unique across the system, even in distributed systems where delays may happen.
* If an ID attribute is randomly generated, it must be unique and unchaning forever.

* VALUE OBJECTS have no conceptual identity, they instead describe the characteristics of something.
* VALUE OBJECTS must be immutable, and can only change through full and complete replacement.
* VALUE OBJECTS can be passed by reference or copy - each has their pros and cons and is influenced by the design of the system (e.g. centralized vs distributed)

* Use denormalizatoin when time is more critical than storage space.

* Domain layers manage state and govern system behavior; application layers make requests to the domain layer (i.e. the application asks the domain authority to do something); both use the infrastructure layer to communicate with each other and do other things (e.g. send emails).
* SERVICES are stateless versus ENTITIES or VALUE OBJECTS which are stateful.
* There can be both application or domain services; services is kind of a catch-all for stateless helpers.

* Medium grain services, services wich encapsulate a good chunk of functionality behind an intuiitive interface, are the most ideal - especially in distributed systems.
* Small grain services require tight coordination which often leak into the application layer to coordinate and creates tight coupling.
  * Choreography is better than orchestration.

* MODULES (i.e. packages) are abstractions.
* MODULES should be well named so their intent is clear to keep cognitive load down and code simple to understand.

* Do not let infrastructure or idealistic coding patterns get in the way of developing practical working software.
* Picking off the beaten patch technologies ois probably not worth the risk or cost to most companies - but sometimes it is the only solution to gain an competitive advantage.
  * Doing complex statistical analysis is simple in Julia or R vs Ruby; but Ruby is better at general product development then Julia or R.
* The paradigm influces the model and visa versa.
  * Try to conform to keep things easy
  * Always be skeptical and look for compatable alternatives that aren't too far off the beaten path to improve.

### Chapter 6 - The lifecycle of a domain object

* An AGGREGATE contains an single ENTITY (the root) and a clear boundary.
  * Things within the boundary should (and ideally cannot) be access by things outside of the boundary.
* A car is a AGGREGATE ROOT for tires, whereas a car engine might be another AGGREGATE ROOT which is associated with a car depending on who is tracking the engine. Using the tires as an example, a tire manufacturer may care consider a tire an AGGREGATE ROOT for quality purposes, but a local car mechanic would not car too much.
  * The frame of reference often influences if something is an AGGREGATE ROOT with a global identity vs just a local AGGREGATE within the AGGREGATE ROOT.

* Rules that span multiple AGGREGATES should be expected to be eventually consistent - not always consistent.
* AGGREGATES can output values / VALUES OBJECTS, but any state changes must be done and permitted through the AGGREGATE interfaces.
* Maintaining AGGREGATES requires alignment - people will reach in and mess with internals to get their job done quickly.

* FACTORIES encapsulate the creation of AGGREGATES when creating the AGGREGATE itself becomes too complicated.
* A self-screwing screw is probably too complicated for it's core purpose of holding things together - we acknowledge somebody or something will do the some assembly required part when appropriate.
* FACTORIES are the responsibility of the domain layer but they are not part of the domain model.

* FACTORIES are useful when they are encapsulating setup complexity. If they are not encapuslating setup complexity and are merely just wrapping primitive code, perhaps stick with just the raw primitive to avoid unhelpful indirection / abstraction.
* FACTORY operations must be atomic: all or nothing.
  * Be consistent in throwing errors or returning null to communicate errors.
* ENTITY FACTORIES just need the essentials to make a valid AGGREGATE - this has always been my take on FactoryBot factories in Rspec; you can always modify the AGGREGATE later to suit it to your particular use case.
* When reconstructing an existing ENTITY using a FACTORY, and the existing ENTITY is invalid you must have a way to handle such cases (e.g. handle missing data which is newly required)

* Coupling records tightly via foreign keys or loosely via search is an important design descision and influenced by the domain
  * E.g. Is a tire a ROOT AGGREGATE or just a sub-AGGREGATE belonging to a car ROOT AGGREGATE? Depends on the frame of reference.
* Engineers work so frequently at the database it becomes common to fall into the trap that the database is the domain - bypassing models / AGGREGATES.
