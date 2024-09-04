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

* TODO
