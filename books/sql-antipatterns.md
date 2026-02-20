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

* "You can get only the immediate children or perhaps join with the grandchildren, to a fixed depth [with Adjacency List]. But the threads can hae any *unlimited* dept." - p 23
* "Adjacency List can be an antipattern when it's the default choice of so many developers yet it fils to be a solution for one of the most common tasks you need to do with a tree: query all descendants." - p 25
* "If you want to delete and an entire subtree, you have to issue multiple queries to find all descendants. Then remove the descendants from the lowest level up to satisfy the foreign key integrity." - p 27
* "If you instead want to delete a nonleaf node and promote its children or move them to another place in the tree, you first need to change the `parent_id` of children and then delete the desired node." - p 27
* "How to Recognize the Antipattern" - p 28
  * "How many levels do we need to support in trees?"
  * "I dread having to touch the code that manages the tree data structures"
  * "I need to run a script periodically to clean up the orphaned rows in the trees." - p 28
* "There are several alternatives to the Adjacency List model of storing hierarchical data, including *Path Enumeration*, *Nested Sets*, and *Closure Table*." - p 30
* "The Closure Table design is more straightforward than the Nested Sets design. Both have quick and easy methods for query ancestors and descendants, but the Closure Table is easier to maintain the hierarchy information. In both designs, it's more convenient to query immediate child or parent nodes than in the Adjacency List or Path Enumeration designs." - p 39

* **Key takeaways**
  * Adjacency List is an antipattern which is very easy to implement but extremely limited in its capabilities. Instead, favor either *Path Enumeration* where the ancestry is encoded in a string like structure (e.g. `ancestry: 1/43/8212`) or *Closure Table* which is more sophisticated and does not rely on string manipulation so it is indexible.

### ID Required

* "A table without a primary key is like organizing your MP3 collection with no songs titles. You can still listen tot he music, but you can't find the one you want or keep duplicates out of your collection." - p 44
* "A new column is needed in such tables to store an artificial value that has no meaning in the domain model by the table. This column i used as the primary key, so you can address rows uniquely while allowing any other attribute column to contain duplicates, if that's appropriate. This type of primary key column is sometimes called a *pseudokey* or a *surrogate key*." - p 45
* "The presence of a column named `id` in every table is so common that this has become synonymous with a primary key. Programmers learning SQL get the false idea that a primary key always means a column defined in this manner." - p 45
* "A compound key consists of multiple column. ... Duplicates in this intersection table cause unintended results when you use the table. ... To prevent duplicates, you could declare a `UNIQUE` constraint over the two columns besides `id`: ... But if you need a unique constraint over those two columns anyways, the `id` column is superfluous." - p 46 - 47
* "SQL also supports a more concise syntax for expressing a `JOIN` between two tables. You can rewrite the previous query in the following way if the columns have the same name in both tables:" - p 48
      ```sql
      SELECT * FROM bugs JOIN bug_products ON bug_products.bug_id = bugs.bug_id
      SELECT * FROM bugs JOIN bug_products USING bug_id
      ```
* "The symptom of this antipattern is easy to recognize: tables us the overly generic name `id` for the primary key." - p 48
* "Some object-relational frameworks simplify development by assuming *convention over configuration*. They expect every table to define its primary key in the same way: as an integer pseudokey column named `id`. If you use such a framework, you may want to conform to its conventions, because this gives you access to other desirable features of the framework." - p 50
* "A primary key is constraint, not a data type. You can declare a primary key on any column of set of columns, as long as the data types support indexing." - p 50
* "Choose sensible names for your primary key. The name should convey the type of entity that the primary key identifies. For example, the primary key of the `Bugs` table should be `bug_id`. Use the same column name in foreign keys where possible." - p 50
* "... a primary key should be unique within your schema; no two tables should use the same name for their primary key, unless one is also a foreign key referencing the other." - p 50

* **Key takeaways**
  * Many frameworks add an `id` column to database tables and then assume that `id` column is the primary key of the table itself. Instead, the primary key can be a single column or a set of columns which give an entity instance uniquness within the database. This way, `bugs.bug_id = 1` is a different `Bug` than `bugs.bug_id = 2`. Sometimes these "real" primary keys are called a *pseudokey* or a *surrogate key*. With a surrogate key, you can do eaiser SQL joins like
        ```sql
        SELECT * FROM bugs JOIN bug_products ON bug_products.bug_id = bugs.bug_id
        SELECT * FROM bugs JOIN bug_products USING bug_id
        ```

### Keyless Entry

* TODO
