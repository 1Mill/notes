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

* A REPOSITORY is the interface for retreiving and reconstructing ENTITIES (e.g. scopes or Models in Rails)
* A client calling a REPOSITORY on the backend makes it easy to refactor the implementation without changing the result. Or, change the result without having to modify the client.
* REPOSITORIES are read-only - let the client dictate when to save, update, create, etc. because they have more context about when those operations are appropriate.

* Look for affinities between the frameworks you are using and domain driven design - but don't constantly fight against the framework because you are only going to make it more difficult on yourself.

* FACTORIES manage the beginning of an object's life (e.g. initialize); REPOSITORIES manage the middle and end (e.g. find, delete).
* The responsibility of a FACTORY is to initialize, not create, save, or modify database rows - push modifying / managing state up at least one level.
* When using a relational database, compromise normalization if it helps maintain the structure of objects more simply.
  * Relational vs Non-relational (i.e. document) databases for DDD?
* Only REPOSITORIES should be interacting with the database and only external things should be interacting with AGGREGATES - if they start reaching into the database the schema becomes a lot more difficult to change.
  * Contributes to signficant and growing technical debt - need clear and enforced wedges.
* "The tradition of refactoring that has increasingly taken hold in the object world has not really affected relational database design much."

### Chapter 7 - Using the language: An extended example

* Intentionally try to place logic in one of the four layers: UI, application, domain, or infastructure.
* Sometimes it is best to manually identify ENTITIES so they can stay consistent across products (e.g. reuse Sales customer ID inside the product for continuitity)
* "REPOSITORIES are prohibited from interior of AGGREGATE." - page 172
* Walking through examples is helpful to troubleshoot and make sure the domain / application is going to work as expected.
  * Event Storming is useful for this purpose as well
* When you create a copy / duplicate of an AGGREGATE, it should only modify itself: nothing else outside of its boundary.

* "Modeling and design is not a constant forwrd process. It will grind to a halt unless there is frequent refactoring to take advantage of new insights to improve the model and design" - page 177
  * Radical refactoring

* Visualize ENTITIES, SERVICES, etc. as parts of the domains they belong to: not part of layer they are in.
  * Data visualization is all about telling a story and often the story with DDD is how things work together.
* The visualization in DDD is critical to driving alignment and building a ubiquitous language.

* Create SERVICES which translate the needs of one domain into the needs of another domain so that the system can easily interact without needing to worry about the others domain model.

### Part 3 - Refactoring towards deeper insights

* Useful domain models are build through:
  1. Assuming they are worth while to achieve
  2. Continuous refactoring derived from insights from domain experts
  3. Require practice to implement and use effectively

* Test make it safe to refactor code.
* Micro-refactors encourages understanding the *why* of the code to help facilitate communication
* Implement continuous collaboration between domain experts and software engineers to uncover undiscovered models which better capture the domain.
* A well worn glove becomes flexible where the fingers bend; continuously reworking models again and again and again inform where the domain is well understood versus not.
* Models are the foundation of systems.

### Chapter 8 - Breakthrough

* The benefits of refactoring are not linear, they are often bursts in the form of breakthroughs in understanding before plateauing again.
* Walk through examples is a great way to get quick feedback about how a model should work before writing any code.
* If the domain expert doesn't know what what something is in the technical model, it probably means the technical model is wrong.
* Radical refactoring requires trust and political will.
* Use refactoring to crunch knowledge and improve clarity; insights which leads to breakthroughts: don't become paralyzed hunting for them.
* Breakthroughts feel enlightening!

### Chapter 9 - Making implicit concepts explicit

* Recognizing hidden domain concepts in existing models is a big part of evolutionary design.
* When the domain expert uses a word not in the design, it is a sign of mis-alignment and an opportunity to dig deeper into this domain / word to fill the gaps.
* The frame of reference from the domain expert influences how we see and think about the domain space.
* Books are often domain experts in their subject - use them in place of a person when nessesary.

* Rules that a constraint is distorting the design of the host object:
  1. Requires data unnessesary to the domain itself (e.g. fetches data from some other aggrigate)
  2. Related / similar rules appear in multiple places - forcing duplication or inheritance between otherwise unreleated domains
  3. A lot of design and requirements conversation revolves around the constraints (e.g. when X can do Y) but are hidden around procedural code instead of standalone domain objects or services.

* "SPECIFICATIONS provide a concise way of expressing certain kinds of rules, extricating them from conditional logic and making them explicit in the model." - page 223
* Rules / SPECIFICATIONS should exist and be enforced at the domain layer always
  * Don't abstract them away to the application layer where only duplication is the way to enforce SPECIFICATIONS.
* A SPECIFICATIONS is  a TRUE/FALSE checker to determine if an object does or does not satisfy some criteria.
* SPECIFICATIONS are a subset of VALUE OBJECTS

* Coupling SQL quiries to REPOSITORIES couples the database schema, which is the responsibility of the domain, making the domain / database schema more difficult to change.

* Always build the frontend first.
* Don't let good enouht get in the way of perfect.
* Working software is better than theoretical software.
* Feedback through early prototypes is often more valuable than theory crafting.

### Chapter 10 - Supple Design

* "A lot of overengineering has been justified in the name of flexibility." - p. 244
* Code servers two user profiles: paying customers and software engineers.
* Most designs start of rigid and evolve along with new uses cases - wait and response to those real signals before re-working.
  * A glove bends becomes flexible where the fingers bend - not where it doesn't - because of real feedback.
* Naming is critial to making the intent, side-effects, etc. of code clear and should confirm to the ubiquitous language; these are called INTENTION-REVEALING INTERFACES.

* Queries read state, commands modify state; side-effects are unexpected commands. Avoid side-effects as much as possible through clear naming conventions.
* "... easy to test" is a sign of good code design
* Strive to get away from understanding through inspection (e.g. looking at the code to understand what is happening) and instead strive for understanding through naming.

* The contract-mindset uses ASSERTIONS which are split into pre- and post-conditions. Pre-conditions are what state is verified before performing the lynch-pin commit, whereas post-conditions are the contracted state the system should now be in after. This makes things easier to test because the ASSERTION is only performed if the pre-conditions are meet, so tests just guard against the pre-conditions and ensure the post-condition is meet if all pre-conditions are happy.

* "... modifying arguments is a particularly risky kind of side effect anyway." - p 257
  * This has caused sooo many issues in the past because you have no idea where state is being set and modified. Instead, I recommend forcing the parent / client / consumer to pass through all the arguments they care about. In practice, this means rarely setting defaults because defaults assume you know the intent of the parent / client / consumer which is a coin flip.

* Don't apply arbitrary rules to your SERVICE OBJECTS or other models - make them as large or as small as they need to be to encapsulate a meaningful behavior.
* "CONCEPTUAL CONTOURS emerge as the code is adapted to newly understood concepts or requiements" - p 260

* Every concept software engineers have to maintain in working memory increases cognitive load which is a finite resource. The intent of many coding practicies is to reduce this cognitive load as much as possible on engineers working in the code.

* CLOSURE OF OPERATIONS
  * 1 + 1 = 2 (i.e. addition with Integers returns another Integer)
  * If you perform an operation on a model, VALUE OBJECT, etc. try and strive to return the same thing (e.g. valueObject.someAction => newValueObject)

* Closure, iterators, etc. are all about reducing cognitive load on software engineers so software engineers can keep large models and their actions in chunked in their brain versus having to know all the tiny implementation details.

* Adding, removing, or re-ordering rules (e.g. early returns) can often have unexpected and un-tested consequences.
* Frameworks are often opinionated to make some sort of boiler plate easier on software engineers, but at some point they also run into limitations like they are not easy to extend for a new use case.

* The ability to create and combine SPECIFICATIONS (i.e. simple rules for a domain) to create new SPECIFICATIONS (i.e. CLOSURE OF OPERATIONS) makes it easier to do Declaritive Designs.
* Rules based SPECIFICATIONS lend themselves to stacking / composition easily.

* Take domains on one at a time: "it is more useful to make a big impact on one area, ... then to spread your efforts thin." - p 283

### Chapter 11 - Applying analysis patterns

* Familiarity with the domain and recurring patterns across domains makes one an expert in those patterns.
* Patterns are easier to communicate through metaphors or examples.
* Supple design / evolutionary design requires iterations - which means refactoring and reworking; you are never going to get it right the first time.

* When using patterns, it is recommended to adapt the language of the pattern to your domain. It is more important to be clear what is happening by using the ubiquitous language versus more abstract pattern lanuage.
* Analysis Patterns focus on trade offs, and often emphasizing downstream consequences which may be expensive if discovered too late.

### Chapter 12 - Relating design patterns to the model

* Domain models are business motivated, not technically motivated. Domain models encapsulate technical processes so that people don't have to think about what that technical processes unless they are actively working inside that domain. For example, I don't want to know the technical process to send an email: I just want to hit send.
* A STRATEGY / POLICY pattern "... factors apart a rule and the behavior it governs." - p. 312
  * STRATEGIES / POLICIES sound like configs which are passed into domain models
  * STRATEGIES / POLICIES allow multiple configs to be experimented with in parellel
* STRATEGIES / POLICIES are stateful but that state can be safe in a database or just a normal static file depending on your use case.
* This is a different usage of the word POLICIES than how Event Storming uses it.

* Bad domain models require constraints to be duplicated.
* A COMPOSITE is a has-and-belongs-to-many relationship with the same model. For example, Route A may have start point A1 and end point A2 and Route B may have start point B1 and start point B2 whereas Route C is composed of Route A and Route B starting at A1 -> A2 -> B1 -> B2.
* A COMPOSITE may be composed with other COMPOSITES of the same type to create a new COMPOSIT of the same time. For example, Route A + Route B = Route C

### Chapter 13 - Refactoring towards deeper insight

* Focus on:
  1. Live in the domain
  2. Keep looking at things a different way
  3. Maintain an unbroken dialog with domain experts

* Hunt for missing concepts or relationships in the domain layer
* Try, try, and try again.
* When you get something worth trying do it!

* Productivity tips:
  1. Self-determination - let the process take as much or little time as natural
  2. Scope and sleep - place long breaks in between conversations so people can think about ideas
  3. Excersising the UBIQUITOUS LANGUAGE - involve domain experts and trial-and-error using the language before coding anything

* Use existing knowledge or patterns to get a leg up instead of always starting from scratch.

* Code is as much for customers as it is for other software engineers.
* "Continous refactoring has come to be considered a 'best practice', but most project teams are still too cautious about it." - p. 324
* It is easy to see the costs of refactoring in terms of hours spent while it is difficult to see the cost of working around not-refactored code.
* Needing to make a business case for refactoring often just drive refactoring underground or ensuring it doesn't happen at all - it should just be a practice engineers are empowered to do.

* When to refactor:
  * The design does not match the team's current understanding
  * Implicit concepts can be made explicit
  * An opportunity to make an important part of the design suppler

* "Don't introduce 'suple designs' that are just demonstrations of technical virtuosity but fail to cut to the core of the domain"
  * Let the domain evolve, don't over engineer - respond to real signals, not imaginary or wishful ones.
* Don't build a domain model which you have to force experts to adopt - adapt to the domain exports.

* Refactoring occassionally goes through ah-ha moments when new insights are discovered which completely change the domain model, but more often than not it is stable and small incremental improvements to improve the design of the system. It is these incremental improvements which lead to these often unexpected ah-ha moments of change.

### Part 4 - Strategic design

* "... domain-driven design does not produce models unconnected to the implementation" - everything is an implementation detail!

### Chatper 14 - Maintaining model integrity

* People will often take the shortest path to finish their job, which may make your job harder. Sometimes, this is mutiliating an otherwise stable domain model.
* UNOFICATION: where a model is so complete it does not contain any contradictions or ambiguity - in reality there are always gaps.
* "... model divergences are likely to come from political fragmentation and differing management priorities as from techincal concerns." - p 333
* A BOUNDED CONTEXT is a slice of the UBIQUITOUS LANGUAGE and encampsulates a model and how it relates to other models.
  * Draw it out, keep it updated!

#### BOUNDED CONTEXT

* Cells exists in biology because their membranes define what is in, what is out, and what can pass - like a BOUNDED CONTEXT
* Lack of communication and alignment leads to models diverging.
* How to keep a model clean: (1) define a BOUNDED CONTEXT, (2) keep the model strictly consistent within that BOUNDED CONTEXT.
* It is better to have multiple slightly similar models than having one huge unstable model with a lot of conflicting or conditoinal rules.
* Being specific with model naming makes it cleare the intent / BOUNDED CONTEXT of the model (e.g. Voyage Booking vs Rental Car Booking vs Booking)
* FALSE COGNATES: two or more people using the same term and thinking they are talking about the same thing - but in realty they mean different things

#### CONTINUOUS INTEGRATION

* Defining a BOUNDED CONTEXT too small often isn't worth the effort - it is an art to figure out what is large enough to be a meaningful and practical BOUNDED CONTEXT.
* Reference: Extreme Programming (XP)
* Practicies to reduce model splintering / fragmentation:
  1. Reproducible builds
  2. Automated tests
  3. Rules which plance an upper limit time limit on unintegrated changes (e.g. 2 hours, 1 day)
  4. Constant exercise of the UBIQUITOUS LANGUAGE (e.g. pair programming)

#### CONTEXT MAP

* "Code reuse between BOUNDED CONTEXTS is a hazard to be avoided." - p. 344
* "People who work closely will naturally share a model context. People on different teams, or those that don't talk, even if they are on the same team, will split off into differente contexts" - p. 334
  * Frequent and effective communication if critical to maintainging the integrety of systems, domain models, etc.
  * Reference: Conway's law - how a system is designed mirrors the ways in with the organization communicates.
* If you can't describe a certain model, put a dragon there and return to it later - focus on diagraming the core and return to the danger areas later (which are hopefully not the core).
* The CONTEXT MAP should always reflect the current reality - not wishful thinking.
* Good interfaces / contracts are easy to test, and critically important to test to ensure the contract is never broken (unintentionally).

* Using CONTEXT MAPS
  1. The BOUNDED CONTEXT should have a name from the UBIQUITOUS LANGUAGE.
  2. Everyone must know there the BOUNDED CONTEXT begings / ends within the larger system.

* BOUNDED CONTEXTS are often broken down into smaller MODULES, which is where naming, folder conventions, etc. become very important to make it clear what MODULES belong to which BOUNDED CONTEXTS.
* Keep the CONTEXT MAP approachable, don't make it super complicated - anybody with some knowledge of the domain should be able to understand what is going on to a degree.

#### SHARED KERNEL

* A SHARED KERNEL is often a generic domain model which is shared between one or more teams. A good example is the infastructure layer of a product: teams often plug-and-play their stuff without a formal KERNEL / Platform team.
* A SHARED KERNEL is owned by one or more teams and therefore any changes to the SHARED KERNEL must be approved by all owners so the domain model does not drift.

#### CUSTOMER / SUPPLIER DEVELOPMENT TEAMS

* UPSTREAM and DOWNSTREAM dependencies are two seperate BOUNDED CONTEXTS and should be treated as such.
* Engineers are customers of platform work / teams and normal customer testing / feedback should be sought after.
* "... changing the test implies changing the interface." - p 358
* Trust is critical in high performing teams / organizations - if you have to keep double checking the other teams / persons work it slows things down.
  * Product development should focus on building profitable products, not making sure people aren't being things they know they shouldn't be breaking.
* A BOUNDED CONTEXT should have a clear owner who can change the rules whenever they want - if that effects multiple BOUNDED CONTEXT that is a design issue that should be addressed. This same idea can be applied to UPSTREAM and DOWNSTREAM teams - keep them as decoupled as possible.
* If an UPSTREAM team is not motivated / incentivized to support a DOWNSTREAM team like a paying customer, things go wrong quickly because incentive models are not aligned.

#### CONFORMIST

* A CONFORMIST team is one which "... slavishly adher[s] to the model of the upstream team." - p 362
* Conforming often creates limitations in the DOWNSTREAM team in terms of capabilities (e.g. feature X is missing from platform Y, so we can't do X any time soon)

#### ANTICORRUPTION LAYER

* When a new system is built, it often has to integrate with an old system with not as clear domain boundaries or interfaces. This often causes the new system to adapt to the semantics of the old system causing the new system's models to become corrupted.
* An ANITCORRUPTION LAYER converts exists between two systems as a translation layer so that system 1 can talk to system 2 without either having to know how the others works: just their interfaces. This also enpasulates how the two systems integrate together so details don't leak into either system.

* System 1 -> ANTICORRUPTION LAYER owned by System 1 which calls SERVICES, ADAPTERS, AND TRANSLATORS which then make a request through a FACADE to SYSTEM 2.

* ANTICORRUPTION LAYERS are useful for keeping a domain very clean and isolated, but they are also expensive to maintain and manage so be sure to be pragmatic about when they are nessesary versus unnessesary.

#### SEPARATE WAYS

* It is okay to have multiple BOUNDED CONTEXTS which do very very very similar things but in slightly different ways or for different purposes. It is better to have many decoupled and specialized SERVICES than to have a single SERVICE which is terrible to maintain.
* Communication cost to manager shared things can be high, so sometimes having different things is pragmatic.

#### OPEN HOST SERVICE

* Sometimes it it best just to have a availible to anybody to use service, like a SHARED KERNEL, but don't like others modify / change it. Instead, gate keep how changes can be made to ensure they don't compromise the core DOMAIN MODEL. If somebody finds it doesn't do quite what they want, they can either (1) go through the review process, (2) CONFIRM, or (3) roll their own. Either way, don't destroy the core of the model for a one-off use case.
* Provide a standard way for others to use your service, even if it requires them adaopting your SERVICES and/or UBIQUITOUS LANGUAGE - make them do the translation for their own needs.

#### PUBLISHED LANGUAGE

* Use common languages / tools / data formats to facilitate translations (e.g. JSON, XML, etc.)
* Hide migrations behind interfaces so that people using the interface have no clue or need to worry about the implementation details.
* During translations "None of them is likely to give up his model and adopt one of the others" - frame of reference influences how we think.
* Unification of multiple models often requires a new model.
* Teams are responsible for managing a BOUNDED CONTEXT, so the entire team must be on the same page when important decisions are being made.
* "... a BOUNDED CONTEXT is defined by an ***intention*** to unify the model within certain boundaries." - p 384
* ANTICORRUPTION LAYERS are often on-sided because they other side isn't going to help maintain your BOUNDED CONTEXT (e.g. Stripe doesn't care how you implement your product pages as long as you CONFORM to their API)
* The UBIQUITOUS LANGUAGE is often localized to a specific group, so as groups splinter into smaller groups they each form their own UBIQUITOUS LANGUAGE which may make cross-group communication more difficult.

* Communication costs grow exponentially with every person added, so having effective communication is critical to staying aligned. How each organization achieves this is different.
  * Pair programming
  * Documentation
  * Law of two feet
* Each type of strategy requires a different type of communication and alignment when implementing changes
  * SHARED KERNEL needs everybody on the same page
  * SEPERATE WAYS doesn't care what others are doing
  * ANTICCORUPTION LAYER needs to say integrated with the external service, but the external service can care little about the ANTICORUPTION LAYER for some other service.

* When replacing an old system with a new system, tests help make sure the old system continues to work as expected.
* Maintaining a large BOUNDED CONTEXT may be a political endeavore more than an opertional one. Make sure the INTEGRATION and COMMUNICATION costs are worth it and continously reenforce the benefits.

### CHAPTER 15 - Distillation

* TODO
