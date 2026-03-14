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

* "... when referential integreity wasn't satisfied, discrepancies showed up in reports, subtotals didn't add up, and schedules became double booked." - p 53
* "... skipping foreign key constraints makes your database simpler, more flexible, or speedier, you pay for this in other ways. It becomes your responsibility to write code to ensure referential integrity manually." - p 54
* "One in a million is next Tuesday." - p 55
* "You need the database to be *consistent* - that is you need to be able to depend on references in the database being satisfied at all times. But you can't be certain that all applications and scripts that have accessed your database have made their changes correctly." - p 56
* "There are also some ultra-flexible database designs where foreign keys can't model the relationships. It should be strong clue that you're using another SQL antipattern if you can't use traditional referential integrity constraints." - p 58
* "The Japanese phrase *poka-yoke* means 'mistake-proofing.' This term refers to a manufacturing process that helps eliminate  product defects by preventing, correcting, or drawing attention to errors as they occure. This practice improves quality and decreases the need for correction, which more than makes up for the cost of its use." - p 58

* **Key takeaways**
  * Foreign key constraints and database column type constraints make domain entities stable and consistent. If you do not use these native constraints, you must write application code which enforces them instead. This creates opportunities for gaps where one script does this enforcement and another does not: leading to inconsistency and in turn unexpected data results.

### Entity-Attribute-Value (EAV)

* "A conventional table consists of attribute columns that are relevant for every row in the table, since every row represents an instance of a similar object. A different set of attributes represents a different type of object, so it belongs in a different table." - p 62
* "Entity-Attribute-Value, or *EAV* for short. It's also sometimes called *open schema*, *schemaless*, or *name-value pairs*." - p 63
* "In a conventional database design, it would be sipmle to enforce a mandatory column by declairing the column `NOT NULL`. In the EAV design, ... you would need to a constraint that checks that a row exists for each `issuer_id` value, and the row must have the string `date_reported` in its `attr_name` column. However, SQL doesn't support a constraint that can do this. So you must write application code to enforce it." - p 65
* "... people have entered dates in different formates or sometimes even a string that isn't a date. In a conventional database, you can prevent this if you declared the column with the `DATE` data type." - p 65
* "When someone claims to have designed an arbitrarily extensible database, they're probably using the EAV design." - p 68
* "If you have nonrelational data management needs, the best answer is to use a *nonrelational* technology." - p 69
* "If EAV seems like the right design, you should take a second look before you implement it. If you do some good old-fashioned analysis, you will probably find that your project's data can be modeled in a traditional table design more easily and with greater assurance of data integrity." - p 69
* "Single Table Inheritance is best when you have few subtypes and few subtype-specific attributes, and you need to use a single-table database access pattern like Active Record." - p 71
* "An advantage of Concrete Table Inheritance over Single Table Inheritance is that you are prevented from storing a row containing values for attributes that don't apply to that row's subtytpe." - p 71
* "The Concrete Table Inheritance design is best used when you seldom need to query against all subtypes at once." - p 72
* "Class Table Inheritence: Create a single table for the base type, containing attributes common to all subtypes. Then for each subtype, create another table with a primary key that also serves as a foreign key to the base table." - p 72
* "*Serialized LOB*" where you save a JSON object to a database column as a sort of semistructured set of data - p 73
* "... it's the consequence of a system-within-a-system like EAV." - p 75

* **Key takeaways**
  * A database-within-a-database may feel extensible, but grows in code complexity very quickly. Database constraints can only be conditionally used, which forces data validation up a layer from the database layer to the application layer. This means engineers writing data must also be diligent in enforcing thost validations everywhere because there is not last layer of enforcement past the application layer.
  * Different models require different fields, types and more. While object inheritience is nice in Object Orientated Programming, database do not provide the same inheritance capabilities. There are solutions to handle these different scenarios outlined in the chapter (e.g. Single Table Inheritence, Concrete Table Inheritance, Class Table Inheritece, Serialized LOB) which all have their unique pros and cons.
  * If you think you need unstructured data, you should either (a) use a nonstructured database like MongoDB or (b) critically challenge your assumptions.

### Polymorphic Associations

* "As in EAV, you should be suspicious of any claims of unlimited flexibility." - p 81
* Simplify the Relationship: "It's better to redesign your database to avoid the weaknesses of Polymorphic Associations but still support the data modeling you need." - p 83
* Reverse the Reference: "One solution to this antipattern is simple once you see the nature of the problem: *Polymorphic Associations are backwards*.", instead create Intersection Tables. - p 83
* "Intersection tables usually model many-to-many associations, ... [y]ou can enforce a least part of this [one-to-many] rule by declarining a `UNIQUE` constraint on the `comment_id` column of each intersection table." - p 84
* "Also, you can depend on referential integrity when using intersection tables, whereas with Polymorphic Associations you couldn't." - p 85
* Common Super-Table: "In object-oriented polymorphism, two subtypes can be referenced similarly because they implicitly share a common supertype. In SQL, the Polymorphic Associations antipattern leaves out that crucial entity: the common supertype. You can fix that by creating a base table that all of your parent tables extend (see *Class Table Inheritance*, on page 72)." - p 87
* "*In every table relationship, there is one referencing talbe and one referenced table." - p 88

* **Key takeaways**
  * Polymorphic Associaitons can be better implemented with referential integrity (not dependnet on string `..._type` columns) through Intersection Tables with a `UNIQUE` constraint to enforce a one-to-many relationship or through a Common Super Table.
  * When a database model offers unlimited flexibility, be suspicious of what buisness logic is going to leak into the application layer because it cannot be enforced at the database layer.

### Multicolumn Attributes

* TODO
