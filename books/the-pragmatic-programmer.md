# The Pragmatic Programmer

<https://www.amazon.com/Pragmatic-Programmer-journey-mastery-Anniversary-dp-0135957052/dp/0135957052>

## Key Takeaways

* TODO

## Notes

* TODO: Find the rest of these notes in some other notebook ...

* Refactor everywhere
  1. SOmetimes it feel wrong
  2. You learn to do better
* Refactoring is long-term pain management
* Refactoring creates opportunities to learn and grow about the business logic, domains, and technical practicies
* Refactory, early, refactor often - not rewrite completely and do it in small chunks
* Don't refactor and add behavior changes at the same change - keep them seperate

* Build end-to-end, learn as you go - don't build isolated layers void of the overall mission / context

* Design to test
  * Michael Feathers: (paraphrasing) "If it is akward to test, it is usually a design problem."
* Testing later / after is akin to testing never - the point of TDD is to get feedback about the design early and often
* Tests act as documentation for others also helps others reduce anxiety around their code changes
* Property based tests?

* Security through obsurity does not work
* Apply security patches frequently and quickly
* Rely only on reliable things (e.g. boring technology)

* Stroop Effect for code
  * Make variable names and function name as clear as possible
  * Don't violate norms for language, ???, etc. (e.g. `i` vs `myVar` for indexes)
* Pattern language part of culture
* Names are important to understanding
  * Practice and think of motivation of why we are creating this slice of code
* Variables declare what you mean
* If you spot a problem, fix it! (e.g. radically refactor varaible names for imporved clarity)
* Make renaming easy - if this is possible then a litmus test for decoupled code

* Programmers as Therapy
  * Help people work through what they want
  * Look for edge cases (be diplomatic)
  * Deliver facts, tests, feedback, and implications around solution
* The real project requirements (technical and otherwise) are discovered through feedback loops
  * "Is this what you ment?" school of feedback
  * Work with a user to act like a user

* Policies are metadata -> Implement general cases so they are easy to plug and play (e.g. Authentication and Authorization)

* Successful tools adapt to the hands that use them.
* Engineers are abstractions / interfaces to product development
  * Fit requirements onto index cards, no longer / bigger - requirements are a placeholder for having a conversation because the code is the documentation
  * Visualize the work to be done
* Prioritize and identify constraints
* Take mental breaks to keep a clear perspective (good ??? reserve ???)
* User are part of the team, include them in the "mob"
* Don't go into code alone, do it as a group
* Sign code, but don't grow ego

* Agile is not a noun, it is how you do things
  * Nothing out fo the box
  * Adapt to both your business and PEOPLE
* Reduce code coupling by reducing feature interface to niminum data required (e.g. email vs entire user record) affords agility because of minimal coupling
* Engineerings should have collective ownership of code - No Broken Windows
* Teams should work on more than just feature development
  * Schedule time to fix leaks to secure the ship long term
* Great product teams speak with one voice that people have confidence in
* Frictionaless communication
* Adding more people don't make it faster to deliver, just like reading a book adding more people likely add more overhead and communication costs
* Don't be an "Agile Cargo Cult" do what works fo your context
  * Take the best parts from other frameworks if it works for you
  * Deliver valuable functionality as soon as possible to user when it makes sense.
* Don't do manual processes / steps -> Automate CICD, tests, etc.
* Delighting users is the gola of a product, they don't care about code
