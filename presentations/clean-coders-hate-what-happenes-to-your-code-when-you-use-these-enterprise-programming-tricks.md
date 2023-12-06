# Clean Coders Hate What Happens to Your Code When You Use These Enterprise Programming Tricks

<https://www.youtube.com/watch?v=FyCYva9DhsI>

## Key Takeaways

* There are only three ways to express intent through code: (1) punctuation, (2) spacing, and (3) naming. Most programming languages are very opinionated about punctuation and spacing can only express so much (e.g. loose groupings). This leaves naming as the most powerful technique to crafing high quality code. So, instead of being verbose, be specific and intentional with names.

* Poor quality code is systemically created. It isn't random or by chance; it is a symptom of company culture. Some try to force quality through automation, like linting in the IDE. However, this only shifts the conversation to discussing "sacred defaults" instead of teaching others how to craft high quality code.

* Crafting high quality code is an art and must be intentionally practiced to improve.

## Notes

* The term "Enterpise" usually implies some sort of constraints (e.g. limited budget, unknown feasability) or scale (e.g. large)
* The term "Code" usually implised some sort of shared and/or standardized practice
* Debate on using term "developer" versus "programmer" versus "engineer" - everybody has their thoughts
* Approaching a problem from the wrong angle can really make it difficult to understand and maintain
* FizzBuzz implementations
  * Accumulation approach
  * Tail return approach
* Anderson's Law: "I have yet to see any problem however complicated, which, when you looked at it in the right way, did not become still more complicated."
* People fill the time given to them for a project.
* "Enterprise solutions" usually go one of two ways: clever code that is difficult to understand or complex file structures that are difficult to understand - hence why it is "enterprise" and perhaps a little self-fulfilling
* "A work of art is the unique result of a unique temperament." - Oscar Wilde
* Cargo Cult Programming: "...ritual inclusion of code or program structure that servers no real purpose."
  * Dependency injection in Rails
  * Classes versus functions or functions over classes
* A common source of noise in code (e.g. unneeded effort to understand what is happening) are:
  * Code comments
    * Code should be living documentation
    * Writing easy to understand code (i.e. clean code) is not simple and is a skill people must practice at
    * Comments are often not updated when the business logic changes, making it worthless
  * IDE with "sacred defaults"
    * Off loads thinking about how to write good code so people do not practice or think about what makes code good
    * Use wildcard imports because the most important thing is communicating what pacakges we are using, not what sub-methods in those packages we are using - at least not at the top of the file.
      * If there is a known conflict between packages (e.g. both import `List`), then explicitly import the one you want
        * A gotacha though is what if you don't know two packages export something else you care about?
* Repetition is "truth" which turns into culture
* Sometimes a golden hammer (i.e. certain programming paradigms like factory patterns) are not the right solution
  * Factories
  * Singletons
  * Screen size are the antithesis of good variable names because more real estate encourages more verbose names - Object Oriented Programming
* "Stop trying to communicate, and just communicate!" - Sometimes a door can just be a door; it doesn't have to be a front door with white trim
* "Your name is your design" and "you only have three tools":
  1. Name
  2. Space
  3. Punctuation
* Most language are opinionated about punctuation, spacing can only communicate so much, so naming is the most important tool to make code understandable and don't be afraid to get specific (but avoid verbosity)
* Renaming is a powerful refactoring method
  * Names should be as fluid as possible until you really understand the domain you are working in
    * Some only start with things like `function blah(something:, something1:) {...}` until when first writing a new function so the name doesn't pigeonhole them or bias their discovery process.
* Anti patterns
  * Singleton configurations
  * Singletons
  * Verbose naming
  * Noisy logging
  * Log and throw
  * Repetition and duplication - "when you become comfortable with something is disappears"
  * Unnecessary code
  * Mixed levels of abstraction
  * Legacy coding habits
    * The longer this goes unresolved, the more it will cost because often there is no clear migration from habit v1 to habit v15 - you must often still do habit v2 through v14. So invest in that change while v2 is still actively supported and understood in the larger developer community.
  * Programming by Coincidence
    * Survivership bias
  * Programming by Superstition
    * Something aking to 'This is how we have always done it'
* People follow conventions which are implicitly and expilcitly learned.
* **Poor quality code is a systemic created, it isn't random or by chance - it is a result of the system people are working in.**
* When writing an interface, figure out the internals before writing the interface because the internals will inform what inputs you need in what types / shape - don't make this decision prematurely.
* Watch out for things working by coincidence, like digging deep into inputs - perhaps ask explictly for that thing and force the person using your interface to dig for it.
* `CreateServerConnection` and `ConnectToServer` communicate different intents - emphasising the importance of naming and how it can produce clarity.
* The mission of a constructure is not to create an object but to create an object in a well defined state
  * If there is an error, throw it and let the parent handle it with respect to logging, fallbacks, etc.
