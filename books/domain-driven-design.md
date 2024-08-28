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

* TODO
