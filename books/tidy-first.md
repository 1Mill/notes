# Tidy First

<https://www.amazon.com/Tidy-First-Personal-Exercise-Empirical/dp/1098151240>

## Key Takeaways

* TODO

## Notes

### Foreward

* "Practicing software developers often pay scant attention to theory." - p xi
* "Coupling and cohesion are ispmly measures of the complexity of computer code ... from the perspective of the ... human beings trying to understand the code." - p xii
* "To understand any program, wheather to create it or to correct it or to change it, requires understanding the piece of code immedietely in front of you as well as those other pieces to which it is connected, which it depends on or affects or is effected by." - p xii
* Gestalt
  * "Gestalt psychology is often associated with the adage, 'The whole is something else than the sum of its parts'. In Gestalt theory, information is perceived as wholes rather than disparate parts which are then processed summatively. - [Wikipedia](https://en.wikipedia.org/wiki/Gestalt_psychology)
  * Humans best understand things in the context of wholes, not the context of individual parts. It is easier to start big picture and work down to the implementation details than it to start with the implementation and work upwards.
* "Coupling and cohesion are really all about how your brain deals with complicated systems." - p xii

* **Key takeaways**
  * People writing code rarely think about the theory or craftsmanship around the code
  * Code is writen for humans, not computers; computers can understand binary no problem: humans cannot, that is why we wrote C, C++, ... for people first
  * People understand systems best as wholes first before drilling down into the parts
  * Strive for high cohesion (sinlge purpose) and low coupling (minimum dependencies) to keep systems understandable.
  * Optimize code for understandability / humanity first

### Preface

* "Software design is an exercise in human relationships." - p xiii
* "Software design is a powerful tool to ease pain in the world - if it is used well. Used badly, it becomes just another instrument of oppression." - p xiii
* "Part of the tidying philosophy is that it should never be a big deal. Its's never something that has to be reported, tracked, planned, and scheduled. You need to change code, and its hard to change because it's messy, so you tidy first." - p xv

* **Key takeaways**
  * Tidying / refactoring is part of doing the work to make doing the (future) work easier
    * To maximize the amount of work not done: make the work easier to do, make the work effortless, make the work unnessesary - [Woody Zuill](https://github.com/1Mill/notes/blob/main/conferences/agile-open-northwest-2024.md#dogma)
  * What makes software design oppressive versus powerful? Maybe an example is patterns people actively hate haha.

### Introduction

* "It's far better to feel unsafe when you're acting unsafe than it is to feel blithely, cluelessly safe." - p xxi
* "... workg in small, safe steps ..." - p xxi
* "Avalanches are the best." - p xxii

* **Key takeaways**
  * Work in (extremely) tiny steps to work more safely
  * Refactoring affords understanding which often leads to an avalanch of more refactoring from new understandings and perspectives on the code / domains.

### Part 1

* "'Refactoring' took fatel damangew hen folks started using it to refer to long pauses in feature development. They even eliminated the 'that don't change behavior' clause ..." - p 3
* "Its easy to get lost in nested conditions." - p 3
* "Code with guard clauses is easier to analyze because the preconditions are explicit." - p 3
* "A routine with seven or eight guard clases ... is *not* easier to read. It needs more acute care to partition complexity" - p 3
* "...*always& and only take tiny steps." - p 4

* "If the code doesn't get executed, just delete it." - p 5
* "If you suspect code isn't used, pre-tidy it by logging its use ... until you're confident." - p 5
* "... delete only a little code in each tidying diff. That way, if it turns out you were wrong it will be relatively easy to revert the change." - p 5

* "As a reader, you'd like consistency. If you see a pattern, you can confidently jump to the conlusiojn that you know what's going on." - p 7
* "You as a reader will quickly get acclimated to any and one of them. Things get confusing when two or more of the patterns are used interchangeably. As a reader, you expect that difference means difference." - p 8
* "Pick a way. Convert one of the variatns into that way."  - p 8

* "... new interface by sipmly calling the old one."  - p 9
  * Make a sub-system more intuitive to work with by giving it a new interface but internally it just calls the old one still. This way, you don't lose functionality but get more engineer friendly code.
  * This is called a "pass-through interface" - p 9

* "Give the gift of that sequence to the next reader." - p 11
  * Reader order / declaration order can help readers better understand the code (e.g. what is dependent on what like `import` vs `export` vs nothing (i.e.`private`) in Node)

* "... if two routines are coupled, put them next to each other." - p 13
  * May be same file, same directory, same project.

* "As you're executing this tidying, remember that you have to maintain the order of the data dependencies." - p 16
* "You'll accidentally change the behavior ... No problem. Back up to a know correct version of the code. Work in smaller steps. That's the tidying way. Big design changes too hard and scary? Take samller steps. No, samller. Still scary? No? Good."

* Variable names communicate important context - give variables explaining names. Same for constants - no magic numbers or magric strings.

* Explicit parameters / arguments (e.g. keyword arguments) make code easier to reason about. - p 21

* "You're reading a big chunk of code and realize, 'Oh, this part does *this* and then that part does *that*. Put a blank line between the parts." - p 23
* "Here's the cool thing - compound interest. Software design also makes softeare design easier." - p 23
* "Done well, software design enables software design that enables change." - p 23
  * Steps for tidying - don't get stuck in an endless loop
    1. Think
    2. Think
    3. Do

* "Name the routine after the purpose (not how the routine works)." - p 25
  * REF: 7 stages of naming (Arlo Belshee)

* "Inline as much of the code as you need until it's all in one bilg peile. Tidy from there." - p 27
* "The biggest cost of code is the cost of reading and understanding it, not the cost of writing it." - p 27

* "You know that moment when you're reading some code and you say, 'Oh, so *that's* what's going on!' That's a valuable moment. Record it [with an explianing code comment]." - p 29

* "When you see a comment that says exactly what the code says, remove it." - p 31
* Only use comments to help communicate what the code cannot clearly communicate - do not be dogmatic about other comment practicies.

* **Key takeaways**
  * The primary goal of code is to help others (or your future self) understand what is happening. Computers understand binary, so higher level langauges were created to help facilitate understanding between humans: not machines. Strive to make code as understandable as posible: use explaining code comments, dependency ordering, empty lines, proximity, clear variable names, and more to improve how people understand the code.
  * Understanding code is the most expensive things software engineers must do.
  * Work in extremely tiny steps to reduce risk, particularly when refactoring. If a refactor does not feel safe, work try working in tinier and tinier steps until it feels safe. But, feeling safe is not the same as being safe. Use other practicies, such as TDD, to better guage safty.

### Part 2

* "Tidying is geek self-care." - p 33

* Code changes fall into two categories: B = Behavior, S = Structural - p 36
* "Sequences of tidyings (or even just one tidying) go in one PR. Behavior changes go in a seperate PR. Each time we switch between tidying and changing behavior, we open a new PR." - p 36
* "Review latency is also an incentive. If code gets reviewed rapidly, then you're encouraged to create more, smaller PRs. Those more-focsued PRs encourage even more rapid reviews. Equally, this reinforcing loop can run backwards, with slow reviews encouraging larger PRs, further slowing future reviews." - p 37
  * The slower the process, the bigger (and more risky) the change(s) as people min-max
* "I encourage you to experiment with not requiring reviews for tidying PRs. This reduces latency further, incentivizing even smaller tidying PRs." - p 37

* Tidying leads to a chaining / avalanches: (p 39 - 40)
  * **Guard clause** - can it be abstracted into an explaining helper? (e.g. age >= 18 -> isAnAdault?(age))
  * **Dead code** - improves clarity
  * **Normalize symmetries** - "... make identical code identical and different code different"
  * **New interface**, old implementation - Make tools easier to use by giving them more inutitive interfaces (e.g. isAnAdult?(age, :smoking_rules) -> canSmoke?(age) === isAnAdult?(age, :smoking_rules))
  * **Reading order** - Use ordering to improve clarity
  * **Cohesion order** - hunt for abstractions after identifying patterns
  * **Explaining variables** - improve variable names to improve understandabilty
  * **Expicit parameters** - Use keyword arguments vs amorphic blobs (e.g. isAnAdult(person) === person.age >= 18 -> isAnAdult(person.age))
  * **Chunk statements** - Use empty new lines before and after code blocks to communicate ideas in the code
  * **Extract helper** - hunt for abstractions which make expaining variables or explaining comments unnessesary
  * **One pile** - Pile everything into a single method to understand how everything works together, then start tidying from there
  * **Explaining comments** - Last resort, prefer explianing variables, explaining constants, or explaining helpers; make the code self-documenting and comments unnessesary.
  * **Delete redudent comments**

* "Goldilocks Delemma[: what] are the competing costs that let us evaluate what consitutes too few tidyings per batch, to many tidyings per batch, and the range of just the right number of tidyhing per batch?" - p 43
* Factors that go into the Goldilocks Delemma:
  * **Collisions** - Frequency of merge conflicts
  * **Interactions** - Accidentally changing behavior hidden within the changes
  * **Speculation** - Tidying because we think we need to; focus on tidying just enough to make the next immediate behavior change easier
* "In many organizations, the fixed cost of getting a single change through review and deployment is substantial. Programmers feel this cost, so they move right in the trae-off spcae, even as the cost of sollissions, interactions, and speculation rise." - p 45
* "If we want to reduce the cost of tidying, thus increasing tidying and reducing the cost of making behavior changes, then we can reduce the cost of review." - p 45
  * TODO: Insert photo p46

* "You are tidying to make future changes to the behavior of the system easier." - p 47
* "Software design has a strong 'pave the path' [(desire path)] tendency." - p 48
  * Just like in nature, people will take the path of least action to achieve their goals.
* "... tidying is a minutes-to-an-hour kind of activity." - p 48

* "The sunk cost fallacy complicates the choice between these options. ... The answer, as always, is because you are not just instructing a computer, you are explaining your intentions for the computer to other people. The shortest path to instructing the computer is not an interesting end goal."
  * When doing tidying, optimize for human understandability (e.g. tiny PRs, easy to see changes)

* "Tidying makes future changes to the behavior of the system easier. If there is an area of the system that's guaranteed to change (strong word, 'guaranteed'), then tidying in that general area creates value if it simplifies those future changes." - p 52
  * Tidying in itself can provide buisness value in the right situations - it should always strive to make the next behavior change easier.
* "Tidying later creates value in a couple of other ways[:] ... One is by reducing the tax of mesiness[.] Another reason ... is as a learning tool. Finally, tidying later just feels good [and] Software development is a human process." - p 52
* "... taking the pebble out of your shoe lets you walk better." - p 52
* Tidy after if:
  * "You're going to change the same area again. Soon." - p 53
  * "It's cheaper to tidy now." - p 53
  * "The cost of tidying is roughtly in proportin to the cost of the behavior changes." - p 53
* "If tidying doesn't make it any easier, don't tidy first" - p 53
* "Tidying helps you comprehend faster. Sure, tidy first." - p 53
* "If this tidying will pay off weekly for years, then go for it." - p 54
* "In general, bias towards tidying first, but be wary of tidying becoming an end in itself. The tidyings I've cateloged are tiny precisely so you don't have to think too hard about applying them. If you tidy and it doesn't pay off, no big deal. Bias towards tidying shouldn't cost you much, and most of the time it will pay off." - p 54

* Summary (p 54)
  * **Tidy Never when**
    * "You're never changing this code again."
    * "There's nothing to learn by improving the design."
  * **Tidy Later when**
    * "You have a big batch of tidying to do without immediate payoff."
    * "There's eventual payoff for completing the tidying."
    * "You can tidy in little batches."
  * **Tidy After when**
    * "Waiting until next time to tidy first will be more expensive."
    * "You won't feel a sense of completion if you don't tidy after."
  * **Tidy First when**
    * "It will pay off immediately, either in improved comprehension or in cheaper behavior changes."
    * "You know what to tidy and how."

* **Key takeaways**
  * Code changes are broken into two categories: Behavior Changes (B) and Structural Changes (S). Isolate B and S in their own seperate PRs to make code review easier. S changes are tidies and should not change behavior (i.e. refactoring).
  * The lower the review + deployment process, the bigger PRs are encouraged to be. Find the Goldilocks Zone for your orgnaization which min-maxes time to review (i.e. human readability), time to delpoy, risk to deploy, chance of merge conflicts, and utility.
  * Tidying leads to more tidying which leads to more tidying which leads to more ... in an avalanche of tidying. But you must have guardrailes; only tidy enough to make the next immediate behavior change easier to do: go no further.
  * Bias towards tidying first, sometimes after, later, and never are valid strategies.

### Part 3

* "Understanding theory optimizes application. The forver questions in software design are:" (p 55)
  * What do I start making software design decisions?
  * When do I stop making software design decisions and get on with changing the behavior of the system?
  * How do I make the next decision?

* "When we're stuck on 'X', 'No, Y', then we're stuck in a battle of wills, likely to be resolved through our relative power positions in our relationship." - p 56

* "software design is an exercise in human relationships" - p 57
* The elements of software design are "tokens -> expressions -> statements -> functions -> objects / modules -> systems" - p 57
* "Elements have boundaries. You know where they start and end." - p 57
* "In software design, we have a handful of relationships like: Invokes, Publishes, Listens, Refers (as in fetting the value of a variable)" - p 58
  * Refers are getters
* "When I talk about the structure of the system, I'm talking about: The element Hierarchy; The relationships between elements; The benefits created by those relationships" - p 59

* "Software creates value in two ways: What it does today; The possibility of new things we can make it do tomorow" - p 61
* "Behavior can be caracterized in two ways: input/output pairs; invariants." - p 61
  * Input / output: If you give me (A, B, C) I will automate the output of D for you for a small fee (e.g. tax software)
  * Invariants: ???
* "Behavior creates value." - p 61
* "Bit rot is real. Something is always changing. Staying in place in the river requires constant paddling." - p 61
* "Options are the economic magic of software - especially the option to expand." - p 62
* "*Extreme Programming Explained* 'Embrace change'" - p 62
* "... some scenarios that reduce [ ] options:" - p 62
  * A key employee quites. Change that would have taken days now take months.
  * You distance yourself from your customers. If you get a provocation suggestion a month instead of one every day, you have fewer options.
  * The cost of changes skyrockets. Instead of being able to exercise an option a day, you can only excersie an ption a month. Fewer options, less value.
* "The structure [of the code] creates options. The structure could make it easy to add new countries to our paycheck calculation, or it could make it hard." - p 62
* "... structure changes and behavior changes are both ways to create value, but that they are fundementally fundementally different. How? In a word, reversibility." - p 63
  * People do not become dependent on structure, but they do on behavior (i.e. breaking changes in major SEMVER releases).

* "... money represents this 'frozen desire' [to want stuff later, but not right now]" - p 65
* "When geeky imperatives clash with money imperatives, money wins. Eventually." - p 65
* "Strategies that had made perfect sense to me now seemed bizarre where they contridicted the nature of money. Strategies that had seemed fringe or sketchy or naive become just sensible money management." - p 65
* "... the time value of money encourages tidy after over tidy first." - p 68
  * A dollar today is worth more than a dollar tomorrow. Tidying is often a fixed cost, so doing it later makes more economic sense. But, opportunity cost in refactor delay also needs to be appropriately managed.
* "What behavior can I implement next?" - p 70
* "I don't have to care which item will be most valuable, as long as I keep open the option of implementing it." - p 70
* "Software design is preparation for change: change of behavior." - p 71

* "Tidy first? Yes. And also no." - p 73
* Tidy first if and only if "`cost(tidying) + cost(behavior change after tidying) < cost(behavior change without tidying)`" - p 73
* At the scale of tidying - minutes to hours - we can't (and shouldn't try to) precisely calculate the economics of our tidying." - p 74
  * Tidying should just be part of the work.
  * If we must evaluate the economic benefits of a tidying (i.e. make a buisness case) then the tidying is too big.
  * Tidying should be measure in minutes to hours - not longer.

* "One property relevant to tidying first is that structure changes are generally reversible. You extract a helper function and you don't like it? Inline it. It's like that hallper never existed." - p 75
* "There's great value in reviewing, double-ehcking, triple-ehcking rirreversibile decisions. The pace should be slow and deliberate." - p 75
* Make decisions reversible -> Make it safe to fail -> Make it safe to learn / try. - p 76

* "... what made them so expsnive. They noticed that the expensive programs all had one property in commong: changing one element required changing other elements. The cheap programs tended to require localized changes." - p 77
* "... coupling has two properties that drag it center stage: 1-N; Cascading." - p 78
  * 1-N: On element can be coupled with any number of other elements with respect to a change.
  * Cascading: Once a change has rippled from one element to another, that implied change can trigger another round of changes, which can themselve trigger changes of their own.
* "Cascading changes are the bigger issue. As we will see in the next book, the cost of changes follows a power law distribution. ... You will be using software esign to reduce the probability and magnitude of cascading changes." - p 78
* "It's not enough to know that one service invokes another; we need to nkow what changes to one service would erquire changes to the other." - p 78
* "Couplling drives the cost of software." - p 79

* "turns out that mental model of software, as a *thing* that is *made* and then should run forever unchanged, like some kind of perpetual motion machine, is the opposite of what really happens, and what *should* happen, too. The future value of a system reveals itself in today's realities, not yesterday's speculation." - p 81
* "'Constantine's Equivalance,' then, is that the cost of software is approximately equal to the cost of changeing it." - p 81
  * `cost(software) ~= cost(change)`
* "So, the cost of software is approximately equal to coupling:" - p 83
      ```bash
      cost(big changes) ~= cost(coupling)
      cost(software) ~= cost(change)

      => cost(software) ~= cost(change) ~= cost(coupling)
      => cost(software) ~= cost(coupling)
      ```
* "To reduce the cost of software, we must reduce coupling." - p 83

* "The boulder that was perched on the hill decided now was a good time to roll down." - p 85
  * You rarely get to choose when technical debt or deferred maintinance must be paid; so best to be aware and managed eagerly rather than lazily.
* "Here's something I believe but can't prove or adequately explain: the more you reduce coupling for one class of changes, the greater the coupling becomes for other classes of changes. THe practical implication of this (if it matches your intuition) is that you shouldn't bother to squeeze out every last bit of coupling." - p 86
* "Cost of coupling trades off with cost of decoupling" - p 87
  * Look at graph on page
  * As you decreasing coupling in one space you are increasing coupling in another; so don't seek to eliminate all coupling, seek to find the optimal balance.

* "Make the code tider for the next person. If everyone follows the Scount rule ('leave it better than you found it'), the code will become more livable-with over time." - p 90

* "..." - p 91
  * Cost - Will tidying make costs smaller, later, or less likely?
  * Revenue - Will tidying make revenue larger, sooner, or more likely?
  * Coupling - Will tidying make it so I need to change fewer elements?
  * Cohesion - Will tidying make it so the elements I need to change are in a smaller, more concentrated scope?
* "You can't be your best self if you're always rusing, if you're always changing code that's painful to change." - p 91
* "Tidy to enable the enxt behavior change. Save the tidying binge for later, when you can go nuts without delaying the change someone else is waiting for." - p 91
* "... making software design an ordinary, blaance part of development." - p 91
* "Once you make software design part of both daily buisness and strategic planning, you have the opportunity to play your part in healing the rift between business and technology." - p 92
* "Tidy first? Likely yes. Just enough. You're worth it." - p 92

* **Key takeaways**
  * Products / software is mostly about profitability and min-maxing effort for economic output. Contextualizing tidying in this economic sense means it is only worth doing if and only if it makes implementing the next desired behavior of the product earier. If it doesn't, don't do it. This is a learned art to know when and how to tidy. But as a guardrail, tidying should be timeboxed to minutes to hours - not days; and tidying should be done as part of the work itself: not relegated to a deprioritized backlog item.
  * To create profitable software we must make software easy to change. The most hidden cost center in software is tight coupling between elements. A sign of coupling is when you make a change in one element which creates a cascade of changes throughout the code. Think of changing your default API response from JSON to XML in an all-or-nothing approach. To keep the product working you must change everything to support XML in one giant release. Instead, seek to work in tiny steps and decouped ways. But, do not go to hard in striving to decouple everything. At some point, practically speaking, something is going to be tightly coupled to something else. For example, the english alphabet can be composed into english words to form english sentences. It doesn't make sense to try and decouple "english words" from their "english alphabet" - but it may make sense to decouple "english words" from their english origin for the sake of translating to a different language using a different word with a different alphabet. So, decouple just enough to make the next behavior changes in the system simple.
