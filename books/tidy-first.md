# TITLE

LINK

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

* TODO p 13
