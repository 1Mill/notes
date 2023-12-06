# Why Hasn't TDD Taken Over The World?

<https://www.youtube.com/watch?v=XsbMNWW-hdY>

## Key Takeaways

* TDD increasese the stability of the system, which reduces deployment anxeity, which lets people focus on delivering instead of manually QAing for broken things.

* An often overlooked benefit of TDD is the things it prevents: bugs, unexpected edge cases, and bad code design. Good code design is easy to test, and good code design is easy to maintain and adapt. TDD is one of the earliest tools to provide feedback on code design to help prevent bad code designs from festering.

* Test act as living documentation and rigidity to the system which catches unexpected changes. Characteristics which make code easier to maintain and adapt with confidence.

## Notes

* The easier it is to write and run test the more likely it is TDD will be adopted.
* Write the test first before writing any code.
* Unit testing !== TDD
* High test coverages is a side effect: not a goal
* The goal of TDD is to build higher quality software more easily

* Common challanges
  1. Learning curve
      * TDD must be practices just like any other skill
      * TDD reveals the cost of your design decisions readily - only bad designs are difficult to test
  2. Investment in time
      * Optimize software development lifecycle for thinking - not typing
  3. Lack of education
      * Easiest to learn TDD from people that alredy know it
  4. Cultural factors
      * Resistance from others who are unfamiliar and don't see / understand the value
  5. Code design and evolution
      * Assert what you want your code to do, not how it does it.
      * Write the test first, then write the code
  6. Maintenance challenges
      * TDD gives us the earliest opportunity to learn / get feedback about our code design which makes out code easier to maintain so worth the cost
  7. Perceived benefits versus short-term costs
      * The cost of things not seen is hard to quanity for TDD like bugs caught early, adaptability of code, etc.
      * Stability and confidence reduces deployment anxiety which lets people focus on delivering rather than worrying about breaking stuff
  8. Misconceptions and misinterpretations
  9. Practicality in specific scenarios
      * Design for testability
  10. Fear of job security
      * Tests act as living documentation
