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

### Part 1 - Logical Database Design Antipatterns

#### Jaywalking

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

#### Naive Trees

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

#### ID Required

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

#### Keyless Entry

* "... when referential integreity wasn't satisfied, discrepancies showed up in reports, subtotals didn't add up, and schedules became double booked." - p 53
* "... skipping foreign key constraints makes your database simpler, more flexible, or speedier, you pay for this in other ways. It becomes your responsibility to write code to ensure referential integrity manually." - p 54
* "One in a million is next Tuesday." - p 55
* "You need the database to be *consistent* - that is you need to be able to depend on references in the database being satisfied at all times. But you can't be certain that all applications and scripts that have accessed your database have made their changes correctly." - p 56
* "There are also some ultra-flexible database designs where foreign keys can't model the relationships. It should be strong clue that you're using another SQL antipattern if you can't use traditional referential integrity constraints." - p 58
* "The Japanese phrase *poka-yoke* means 'mistake-proofing.' This term refers to a manufacturing process that helps eliminate  product defects by preventing, correcting, or drawing attention to errors as they occure. This practice improves quality and decreases the need for correction, which more than makes up for the cost of its use." - p 58

* **Key takeaways**
  * Foreign key constraints and database column type constraints make domain entities stable and consistent. If you do not use these native constraints, you must write application code which enforces them instead. This creates opportunities for gaps where one script does this enforcement and another does not: leading to inconsistency and in turn unexpected data results.

#### Entity-Attribute-Value (EAV)

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

#### Polymorphic Associations

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

#### Multicolumn Attributes

* "*Store each value with the same meaning in a single column.*" - p 96

#### Metadata Tribbles

* "Performance degrades for nay database query as the volume of data goes up. Even if a query returns results prompty with a few thousand rows, the tables naturally accumulate data to the point where the same query may not have acceptable performance. Using indexes intelligently helps, but nevertheless the tables grow, and this affects the speed of queries against them." - p 98
* "... to meet the goal of having few rows in every table, you have to either create more tables that have too many columns or else create a greater number of tables. In both cases, you find that the number of tables or columns continues to grow, since nw data values can make you create new schema objects." - 98
* "This is the reverse of *mixing data with metadata* that we saw earlier in the [EAV] and Polymorphic Associations antipatterns. In those cases, we stored metadata identified (a column name and table name) as string data. In Multicolumn Attributes and Metadata Tribbles, we're making a data value into a column name or a table name." - p 99
* "If you need to search many tables with identical structure, you should have stored them together in a single table, with one extra attribute column to distinguish the rows." - p 103
* "One good use of manually splitting tables is for *archiving* - removing historical data form day-to-day use. Often the need to run queries against historical data is greatly reduced after the data is no longer current." - p 103
* "Archiving keeps the data in a compatible table structure for occasional analysis but allows queries against current data to run with greater performance." - p 103
* "Although it seems like the right thing to do from a data modeling perspective to keep everything in a single database, splitting the database sensibly makes database administration tasks easier after the database size passes a certain threshold." - p 104
* "You can gain the benefits of splitting a large table without the drawbacks by using a feature that is called either *horizontal partitioning* or *sharding*." - p 104
* "But in most queries against that table, you wouldn't need the [large blob of data]. Storing such a large column of data in the `Products` table, which you use infrequently, could lead to inadvertent performance problems if you're in the habit of retrieving all columns using the `*` wildcard. The remedy is to store the `BLOB` column in another table, separate from from dependent on the `Products` table." - p 106

* **Key takeaways**
  * As tables become bigger - either in number of rows or number of columns - quries which were once fast become slower and slower. To mitigate this, using *archiving* or *sharding* to make the search space smaller and more targeted. Additionally, move rarely accessed but big in memory size in a dependent table. This way, these big but infrequently accessed data is easliy findable via `JOIN` but don't unnessesary slow down quries using `SELECT * FROM ...`. Examples are adding upload files for an entity as a secondary table instead of directly on the entity table itself.
  * While EAV and Polymorphic Associations are "*mixing data with metadata*" (e.g. associated table name as strings in a column), Tribbles are mixing data with table or column names (e.g. `profits_2025`, `profits_2026`, ...). Instead, make a unifying table where the differentiator is a column (e.g. `profits(fk_id, year)`).

### Part 2 - Physical Database Design Antipatterns

#### Rounding Errors

* "Many programmers ar enot aware of a characteristic of this floating-point format: not all values you can describe in decimal can be stored in binary. Out of necessity, some numbers must be rounded to a value that is very close." - p 112
* "You can't guarantee that a `FLOAT` column in the database will be given only values that are cooperative, so your application should assume that any value in this column may have been rounded." - p 113
* "There's no need to use IEEE 754 for money, because the scalled decimal format described in this chapter can handle money values just as easily and more accurately." - p 114
* "Thedifference seems small, but it compounds. For example, if you multiply the value `1` by a factor of exactly `1.0`, the result is always `1`. It doesn't matter how many times you apply this factor. However, if the factor is actually `0.999`, this has a different result. If you multiply a v alue of one by `0.999` a thousand times in succession, you get a result of about `0.3677`." - p 115
* "Instead of `FLOAT` or its siblings, use the `NUMERIC` or `DECIMAL` SQL data types for fixed precision fractional numbers." - p 116
* "*Do not use `FLOAT` if you can avoid it*" - p 117

* **Key takeaways**
  * Don't use `FLOAT` data types, instead use `NUMERIC` or `DECIMAL` because they are more accurate and make it clear the scale and percision that is supported - unlike `FLOAT` which rounds at hidden levels of percision.

#### 31 Flavors

* "The problem with using `ENUM` or a check constraint araise when the set of values is not fixed. if you're considering using `ENUM`, first ask yuourself wheather the set of values are expected to change or even whether they *might* change. If so, it's probably not a good time to employ an `ENUM`." - p 123
* "*Shouldn't need to* are weasel words, and this says something quite differently from *can't*." - p 123
* "There's a better solution to restrict values in a column: create a *lookukp table* with one row for each value you allow in the `Bugs.status` column. Then delcare a foreign key constraint on `Bugs.status` referencing the new table." - p 124
* "However, you can add attribute column to the lookup table to designate some values as obsolete. This allows you to maintain historical data in the `Bugs.status` column, while distinguishing between the obsolete values and the values that are eligible to appear in your user interface." - p 125
* "*Use metadata when validating against a fixed set of values. Use data when validating against a fluid set of values.*" - p 126

* **Key takeaways**
  * Do not use `ENUM` constraints in a database, instead use a lookup table which a record belongs to. This way, you can easily add more supported values and enforce data integrity through foreign key constraints. Only use `ENUM` when there are two possible options: like "ACTIVE" and "INACTIVE".

#### Phantom Files

* "*Whenever a theory appears to you as the only possible one, take this as a sign that you have neither understood the theory nor the problem which it was intended to solve.* - Karl Popper" - p 127
* "Files don't Obey `DELETE`. ... If your images are outside the database and you delete the row that contains the path, there is no way for the file name by that path to be removed automatically. Unless you design your application to remove those 'orphaned' image files as you delete the database row that references them, they will accumulate." - p 129
* "Files Don't Obey Transation Isolation" - p 129
* "Files Don't Obey `ROLLBACK`" - p 130
* "Files Don't Obey Database Backup Tools" - p 130
* "What is the data dackup and restore procedure? How can a backup be verified? Have you tested restoring data on a clean serve or a different serve tha nwhere the backup was made?" - p 131
* "You need to plan how you application uses images to nkow wheather the issues described in the 'Antipattern' section would affect you. Make an informed decisions, instead of listneing to generalizeations from programmers that store images in exeternal files is always the best solution." - p 133
* "*Resources outside the database are not managed by the database.*" - p 134

* **Key takeaways**
  * "*Resources outside the database are not managed by the database.*" - p 134
  * Files and database `BLOB` have their pros and cons - files easier to do files actions (e.g. process photos), `BLOB` lives within database lifecycle - pick and choose the pros and cons based on the needs of your product. But, most importantly make sure whatever recovery plan you have in place accounts for whatever solution you choose.

#### Index Shotgun

* "The best technique for improving performance in your databse is to use indexes well." - p 136
* "A statement that searches an unindexed column has to eprform a full table scan to find matching rows." - p 137
* "You benefit from an index only if you run queries that use that index. There's no benefit to creating indexes that you don't use." - p 137
* "Also, the order of columns in a compound index is important; you should use the columns left-to-right in search criteria, join criteria, or sorting order." - p 138
* "Some databases support indexes on expressions, or indexes on generated [(virtual)] columns, as well as indexes on plain columns. But you have to define the index prior to using it, and that index helps only for the expression you specity in its definition." - p 139
* "*Selectivity* is a statistic about a database index. It's the ratio of the nuimbe rof distrinct values in that index to the total number of rows in the table[.] THe lower the selectivity ratio, the less effective the an index is." - p 140
* "*MENTOR* your indexes: *Measure*, *Explain*, *Nominate*, *Test*, *Optimize*, *Rebuild*." - p 141
* "Before making assumptions about where the perfromance problem exists, use sotware diagnostic tools to measure. Otherwise, you could be practicing premature optimization." - p 142
* "*covering index*": All the data needed to satify a query completely without having to read from the HEAP for additionally fields - making the query much faster. - p 145
* "How frequently should you rebuild an index? You might hear generic answers such as 'once a week,' but in truth there's no single answer that fits all applications." - p 146

* **Key takeaways**
  * Indexes are incredibly powerful tools to improve the performance of your queries. Particularly *covering indexes* which contain all the data nessesary to satisfy a query in the index itself so the query does not have to reach into the raw database data to fetch addtional data. But, more critically, indexes only improve performance if they are used. If an index has low *selectivity* then an index might just be skipped all together.
  * Indexes cost resources (e.g. memory, storage, etc.) so indexes must be *MENTOR*-ed over time to ensure they are still being used and optimzed for the quries being performed. Additionally, indexes can become imballanced for various reaosns. So, it is best to re-build indexes occassionally to better optimze them.
  * Index can be created on virtual columns for expressions for example. But, such an index only works for that exact expression. If the expression change then the index must also change - these must be tightly coupled.

### Part 3 - Query Antipatterns

#### Fear of the Unknown

* TODO

* **Key takeaways**

#### Ambiguous Groups

* TODO

* **Key takeaways**

#### Random Selection

* TODO

* **Key takeaways**
