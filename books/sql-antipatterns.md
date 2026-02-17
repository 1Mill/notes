# SQL Antipatterns

<https://www.amazon.com/SQL-Antipatterns-Programming-Pragmatic-Programmers/dp/1934356557>

## Key Takeaways

* TODO

## Notes

### Introduction

* "'An expert is a person who has made all the mistakes that can be made in a very narrow field' - Niels Bohr" - p 1
* "SQL uses *sets* as a fundamental data structure, while objective orientated languages use objects." - p 2
* "An *antipattern* is a technique that is inteded to solve a problem but that oftens leads to other problems." - p 3
* "It's traditional to give both positive design patterns and antipatterns names that serve as a metaphor or mnemonic." - p 4

![image](./sql-antipatterns_entity-relationship-diagrams.jpg)

### Jaywalking

* "Programmers commonly use comma-seperated lists to avoid creating an intersection table for a many-to-many relationsip. I call this antipattern *Jaywalking*, because jaywalking is also an act of avoiding an intersection." - p 13
* "You can no longer use equality; instead you have to use a test against some kind of pattern. ... Pattern-matching expressions may return false matches and can't benefit from indexes." - p 15
* "Tricks like this can be clever but never clear. These kinds of solutions are time-consuming to develop and hard to debug." - p 15
* "Try explaining the reason for this length limit to your boss or to your customers." - p 17
* "If you hear phrases like the following spoken by your project team, treat it as a clue that the Jaywalking antipattern is being employed:" - p 17
  * "What is the greatest number of entries this list must support?"
  * "Do you know how to match a word boundary in SQL?"
  * "What character will never appear in any list entry?"
* "When the table has forein keys referencing two tables, it's called an *intersection table*. This implements a *many-to-many* relationship between the two referenced tables." - p 18

* **Key takeaways**
  * Intersection tables afford many-to-many associations without needing to use pattern-matching tricks to parse lists of foreign keys.
  * If limitations in SQL are impacting your product experience, you are likeing using an antipattern somewhere.
  * SQL tricks are handy, but not sustainable or efficeint. Use normal SQL as much as possible - if you are doing pattern matching that is an antipattern. Strive to keep code understandable.

### Naive Trees

* TODO
