#Database

- [camelCase or underscore_case?](#camelcase-or-underscore_case)
- [When to Index?](#when-to-index)
- [Why "ID"?](#why-id)
- [Naming ID Columns](#naming-id-columns)
- [Normalization Example: States](#normalization-example-states)
- [Database Design: Three Areas of Optimization](#database-design-three-areas-of-optimization)
- [Enum: Just Say No](#enum-just-say-no)


22 November 2016

#camelCase or underscore_case?

The formatting of table names and column names within a database schema has been debated for decades. The same discussion occurs in relation to programming source code.

The discussions (arguments) go round-and-round. They will probably never end.

I don't want to write anything lengthy about this. Let me point out a few general facts:

- This relates specifically to optimizing for maintainability. This doesn't make any difference when it comes to optimizing for data integrity or speed.

- The most important decision on this topic is to be consistent. Stick with one format throughout the database design. Otherwise, people will type in the wrong column names and table names, and that will cause errors.

- Although some RDBMS are case-insensitive with regards to table names and column names, some are case-sensitive. Moreover, the programming languages you use to interact with a database may be case-sensitive. Don't ever be sloppy with regards to case. Always capitalize names consistently. Never use alternatively-capitalized variants to signify something different.

Before I whether or not you should use camelCase or underscore_case for naming tables and columns, let me point out that there ARE other alternatives, which I find even less preferable than these two naming conventions:
<br />- alllowercaseruntogether
<br />- ALLCAPSRUNTOGETHER
<br />- spaces between words
<br />- dashes-between-words
<br />- ALL_CAPS_WITH_UNDERSCORES

These alternative formats, which you may see in some databases, are all inferior. They are either difficult to read, or they are error prone. Some of these formats might even seem impossible, such as naming tables and columns with spaces in between words. In most RDBMS, something like this IS possible, it's just a very bad idea, because such a name only works by enclosing it to force the system to recognize it as a string, such as by enclosing it within double-quotes. That's just asking for trouble, though. Also, there may be places where it won't work at all, so you would end up with a table schema which is not very portable.

I do not use camelCase in table and column names. I use underscore_case.

Two main reasons:
I find that underscore_case is easier to read.

Not everybody agrees. But I think most people agree.

The other main reason I use underscore_case: It is programmatically very easy to resolve into a human-readable word, phrase or label.

For example, if I want to automatically convert a table to a form that is presented on a user-interface screen to be seen by human users, I might want to convert the name of a table and its columns to titles and labels. It is easy for any program (including a "replace" command within SQL) to convert underscores to spaces, and thus make a human friendly label. Like this:

original_product_name => original product name

But what if a column is like this:
originalProductName

Not so easy is it? A clever programmer using an application programming language can come up with an elegant function to handle this. But can it be done easily within a pure SQL query statement? Not really.

And even the cleverest programmer is going to run into trouble working with something like this:

originalProductUPCCode

How would you easily convert that to something human-readable? It's not even very readable in camelCase.

Compare that to this:

original_product_UPC_code

You can see how this is much easier to read as part of a schema. And it is much easier to utilize in automated name conversion scripts and functions.

My advice:
<br />- Be consistent.
<br />- Don't go to war over naming conventions if you're a guest in an already-established database.
<br />- if you have a choice, use underscore_case.

[&#8595;](#watch-this-space) [&#8593;](#database)



21 November 2016

#When to Index?

Indexing is a awesome. It really is like a magic bullet to turbo-charge the speed of your database system.

But that doesn't mean you should index everything all the time. High-quality database design requires an awareness of what indexing means for your database, including when to use it and when to NOT use it.

One of the most common "big mistakes" I have seen in database schemas created by programmers inexperienced in database design is that they don't add any indices to tables that really need them.

They might be a programmer creating a new app or web application, and they create a database that their system needs. They add a few test rows, connect the database to the front-end, and everything works fine. So they think they're done.

And they are done. As long as the table is small. For a few rows or a few hundred rows, having an index is not going to matter. But then their system grows. More people use it. Now they have 10,000+ rows in that table, or 100,000+ rows... And their whole system starts to get slower, and slower, and slower. Why?

Because their system involves a search on the "name" column within that 100,000+ table. That search is taking a long time, although it was previously very fast. Add an index to the "name" column and like magic, the queries begin returning results instantaneously, just like when the table only had 100 rows in it.

Don't wait to add an index that the table will need when it grows.

If a table might grow to be large enough that indexing will make a difference, add the index to the columns that need it right from the beginning. This will mean your design is really "finished" and you won't need to monitor the system for the point in time when it starts to slow down because the table is getting too big to operate quickly without additional indices.

So we know that adding an index to a table can speed it up tremendously. Does that mean we should simply index every column right from the start?

No. Don't index every column.

I only add an index to a column if it will be beneficial. I don't do it by default.

There are many tables that may have a dozen or a few dozen columns, but which only need to have one or two of them indexed.

Here is a very simple guide about when to add an index to a column:
<br />- add an index to columns that are uses as SEARCH criteria
<br />- add an index to columns that are used in a "SORT BY" clause
<br />- add an index to columns that need to be referenced by FOREIGN KEY LINKS
<br />- add an index to columns that are used in any JOINS

Note that there other index types aside from the standard index: unique contraints and primary key indices and others. We will not discuss those index types today, except to point out that if a column already has been indexed using one of these other index types, it does NOT need to be indexed again. You don't need to index the same column twice. A unique constraint index (for example) does double duty: preventing the same value from being used twice in a column AND also provides the speed optimization that a non-unique index provides.

Can't I just index everything and not think about it?

No, you shouldn't do that. Although indexing is great when you can benefit it, indexing isn't "free."

Every index you add DOES increase overhead on the system. Indices take up file space. Indices require additional processing time when inserting rows. Indexing columns unnecessarily will create a net drain on your system rather than a boost.

A truly interactive information system which connects many relational tables to each other (joins, foreign keys), allows a user to conduct searches and to sort data using different criteria is likely to have MANY indexed columns. But it won't have EVERY column be indexed.

[&#8595;](#watch-this-space) [&#8593;](#database)


20 November 2016

#Why "ID"?

In a previous entry I suggested that when designing a new database, the best name for an "ID column" ("primary identity column" or "primary key column") is simply:

ID

Yet... if you have seen a wide range of databases created by different people using different RDBMS, covering different periods of time, you may have seen many different naming conventions. Here are some examples:

We have have seen various databases which use different names:
ID
id
Id
state_ID
state_id
state_Id
STATEID
StateID
StateId
stateid
state_num
state_primary_key

Why is "ID" the best name to use?

Let us put aside the interesting fact that some software and source code libraries specifically look for this name and provide some benefits when using it. That is really a minor point. And it is NOT a "universal" thing. Not by a longshot.

I like to use "ID" because it is very readable and instantly recognizable. It really stands out as something distinctive and different from the other column names. Look at this example of column names for a single table:
<br />ID
<br />name
<br />abbreviation
<br />description
<br />population
<br />capitol

I like the way that the capitalized form "ID" stands out.

Also, if I reference this column name in a foreign key column (linking from another table), I like how it stands out from the table name:

state_ID

I want to consistently use the same primary identity column name as a part of foreign key column names. When I use "ID", I can pick that part of a column name out quickly and easily.

One final question:
Why don't I use a naming convention like this for the ID columns:
<br />STATES
<br />state_ID
<br />name
<br />abbreviation

I have seen this in some database designs. In these designs, there are NO primary identity columns named "ID". These columns are all named something different.

Don't do this.

This introduces unnecessary complexity and duplication into your database design.

Your goal should be to make the database design as simple and as non-duplicative as necessary.

If you add a version of a table name in the table's primary identity column, then your database is NOT as simple.

Instead of having ONE name for ID columns ("ID"), you end up having many. You would theoretically have as many different names for ID columns as you have tables.

A table with 20 table would have 20 different tables would have 20 different names for primary identity columns. 20 is NOT as simple as 1.

And you have also introduced duplication. Because what you really have, if you reference the "full name" of these columns is this:
<br />states.state_ID
<br />users.user_ID
<br />products.product_ID

See how each column DUPLICATES information?

If I have an ID column within "states" table, I don't need to name the column "state_ID." I already know that the "ID" column within the states table is the ID column for states.

See how these column names avoid unnecessary duplication:
<br />states.ID
<br />users.ID
<br />products.ID

So to summarize my advice on this topic:
<br />- keep it simple
<br />- make it easy to read
<br />- avoid duplication
<br />- use "ID"

[&#8595;](#watch-this-space) [&#8593;](#database)


19 November 2016

#Naming ID Columns

I want to discuss one of the most important aspects of database design: naming ID columns.

What are "ID columns"? This is one simple and common way to refer to primary identity columns.

For example, in a table like this:
<br />STATES
<br />ID	101
<br />Name	Alabama
<br />Code	AL

...the "ID column" is the first column: "ID".

This is the column within the table that is intended to be unchanging, and it is intended to be the most reliable way to reference a row in a table. These columns are also known as the "primary key." There are some technical distinctions between the complete meanings of these terms, but that is a topic for another day.

Many techniques impact two or even three areas of database optimization (data integrity, speed, and maintainability.) But naming ID columns is something that is really ONLY related to ONE of these areas of optimization: maintainability.

This IS important, even though the database engine itself doesn't really care. Your database is not going to run faster due to the column names you use. The technical ability of your database to be able to enforce data integrity will not change.

But your ability of human user and developers to maintain the database will be significantly impacted.

Your naming conventions can positively or negatively impact the human actions that have an effect on data integrity. So I suppose we could say that how you name ID columns impacts "one and a half" areas of optimization.

We have have seen various databases which use different names:
ID
id
Id
state_ID
state_id
state_Id
STATEID
StateID
StateId
stateid
state_num
state_primary_key

How should you name your ID columns?

The most important answer to this question is:

CONSISTENTLY.

Because if you are consistent, your database will be maintainable.

If you are not consistent, then mistakes will happen. Subtle bugs will creep in that are hard to track down. The ad hoc queries that users write won't work.

BE CONSISTENT!

So many choices! Argh! Just tell me what to do!

Okay: Here is a short answer to what to do:

If you are coming to an already-established database and you are being asked to use it but not recreate its naming conventions, then just BE CONSISTENT. Use whatever naming convention is already in place.

If you are adding a new table to a database in which ID columns all look like this: "id", then that is what you should use.

Simple.

But if you are designing a database from scratch, you can use the convention you prefer. This may be a slightly "controversial" decision. The preferred format may vary depending on the specific RDBMS being used.

I will tell you that in working with MySQL databases, the convention I see most often in "best practices" databases, and the convention I personally use in creating new database is to always use: ID

Two letters only. Capitalized. Always and consistently when I create new databases, I use "ID."

Some MySQL tools actually recognize this column name and provide you with a few extra benefits when you use "ID." For example, phpMyAdmin will automatically provide you with in-line editing functionality on query result screens in which the ID column is "ID", but doesn't provide this functionality when ID columns are spelled or capitalized differently. Maybe this will change in the future, but for now, it's a significant advantage.

So when confronted with the question about how to name an ID column, my simple answer is:

- Use the naming convention already in place within your database
- Use "ID"

(Tomorrow, I'll explain more reasons for using "ID".)

[&#8595;](#watch-this-space) [&#8593;](#database)



18 November 2016

#Normalization Example: States

I want to discuss one specific data concept: States.

As with most any specific data concept example, this discussion serves a dual purpose. It presents ideas about how a specific type of data can be handled, and it also serves as an example of root principles.

So we will talk about how to handle states, which is a common, useful concept. But this example also illustrates principles for optimizing the database for data integrity (through normalization) and for speed.

Sometimes I see databases which store contact information, such as a user's address, and the table with contact information has a varchar (text string) column for "state."

Often these are varchar columns that contain values such as "NY", "AZ" and "NSW."

I never do this. I never store states as text strings. Even in a small, simple database, it is better to store states in a separate table, such as "states" or "locations", and then link an address to that table through an integer foreign key link.

So I may have a table like this:
ID	Name
1	Alabama
2	Alaska
3	Arizona

And in the table with contact information, we would store only the integer that references the states/locations table like this:
state_ID = 1

(This means "Alabama.")

This will save all kinds of headaches.

What we do NOT want to have happen is somebody else on the team coming to us and saying:

"Why are there only 90 customers from New York in this report? I know there are 100."

And then we look in the database and we have to tell them:
"There are 90 customers from New York, but there are also 5 customers from "N.Y.", 4 customers from "NY", and 1 customer from "NewYork."

If we store states as blind text strings in a varchar field, then we are asking to have problems with data integrity. People don't always spell state names correctly. People don't always get the abbreviations correct. So we want to constraint the possible values for states to a list that contains ONLY possible values.

And it isn't that complicated to do so. There are only 50 states in the United States. Even if we add in all states and territories from Australia and the United States, and all provinces from Canada, and even the special military service mailing codes, there are still fewer than 100 items in our "states" table.

If our database encompasses other countries, then we can license a comprehensive location data source, build our own or (most likely) either leave this blank or allow for a general "province" field for other countries. In practice, most international addresses work fine with a city name, a postal code and a country name, and don't need a "state" field.

Normalizing states (storing values as foreign key-referencing integers such as 1, 4, and 40) instead of using varchars ("AL" or "Alabama") will also improve the speed of your database.

If you have only a few hundred records, it won't matter. But if you have a large number of records, such as a hundred thousand or more, you will definitely notice a difference between how fast it takes your database to do a search for all records using a text string ("AL") versus an integer (1).

[&#8595;](#watch-this-space) [&#8593;](#database)


17 November 2016

#Database Design: Three Areas of Optimization

Real database design is more than just creating a database schema that "works."

Real database design means creating a database schema that works well. It should work well now, and it should work well in the future, as a project continues to be used and (in all likelihood) changes as new features are added or new situations are encountered.

Whenever I engage in the task of "database design" -- whether I'm designing a database from scratch or redesigning an existing database -- I like to explain to project owners, project managers, and development teams that I'm focusing on three areas of optimization:

- data integrity
- speed
- maintainability

This helps everybody (including myself) stay focused on important goals and helps explain why I make the decisions that I make. These are straightforward concepts that everybody from non-technical people to highly experienced programmers can understand.

If you think about it, these same goals (or "areas of optimization") should seem very similar to key "best practices" used in non-database programming.

In practice, it is rare that I find a database project which needs to be optimized for some other goal.

Here are simple examples of these optimization concepts:

[optimization for: data integrity]
Question: Why do we need to add a foreign key constraint to this column?

Answer: This will help guarantee that valid data is always stored in this column which references a foreign key. Even if a programmer messes up with integrity checking at the source code level, or even if a back-end database user attempts to inset invalid data, this foreign key constraint will ensure that only valid data is input into the table.

[optimization for: speed]
Question? Why do we need to add an index to this column? The table already works without it?

Answer: This column is used by the front end as a key search field. The system will return results much faster if we index it.

[optimization for: maintainability]
Question: Why do we have to change these column names? The app is already written to use "location_ID" in most tables, and "location_Id" in a few tables.

Answer: Then we need to change the app's source code AND change the column names so that they all match. Things may work now. But as soon as anybody starts making changes, somebody will mis-type the column name, and case-sensitive source code will fail to work.


I find that that nearly every decision in database design can be explained as something that is done in order to optimize the database for one of these three areas: data integrity, speed, and maintainability.

Rather than doing database design based on a large collection of "textbook rules" whose meanings and purposes are obscure, I like to use these key goals as a guiding philosophy.

[&#8595;](#watch-this-space) [&#8593;](#database)



16 November 2016

#Enum: Just Say No

There is a time and place for everything, so the saying goes. And I agree this is true for most database concepts and techniques.

But not for enum. Don't use enum at all. It's a nasty habit.

Many database designers might have blissfully worked their entire careers without running into enum. But then they help out with somebody else's database and see these little critters all over the place.

So what is "enum"? This is an odd data construct masquerading as a "datatype" option within an SQL table. Instead of being a specific type of data (such as varchar, int, decimal, etc.), an enum is actually a LIST of items, such a list of varchar values.

If you're thinking: "A list? Isn't that what a table is for?"

...Then my response is: Exactly.

A column which uses the "enum" datatype in a table is essentially hiding a little table WITHIN a column. It may seem handy, but it is a complete violation of the SQL relational data model.

Enum columns are NOT part of the ANSI SQL standard. They are NOT universally accepted among SQL databases. They are NOT handled the same way by different SQL databases. So when one uses an enum, one ends up with a table design which is not easily or consistently portable.

"But they're so convenient," some people might say. They can be used to store a discrete set of values, such as for a drop-down menu in a mobile app. An example might be a "status" field which contains only these possibilities: "pending", "in progress", and "complete."

Create an enum field and you've got a varchar that only allows those values:
pending
in progress
complete

But by doing that, you're basically hiding these values in a place that isn't where users of the database would look for it.

You can't simply type in "select * from status_types".

There are no standard SQL queries for obtaining the possible values of an enum datatype column.

And what if you want to ADD a NEW status type? Are you ABSOLUTELY certain your system will NEVER need a new status type?

A few months into the project, it turns out you need a new status type: "under review."

Can you just add that status to the enum set of values? It's not so simple. This change will actually require a change to the table schema. Which is fine if you've got a tiny database. But what if that column is used in a table with 5 million records? In many RDBMS, adding a single string ("under review") to that list will actually require the database software to create an entirely new table, with the new schema, and copy all of the record to it. You could wait an hour just to add "under review" to your list of possible values. It might seem far-fetched, but I've seen this. It's a pain.

But if you had a separate table for "status_types," it would take a microsecond to add that new fourth value to a tiny 3-row table.

So EVEN if you don't care about standards, EVEN IF you don't care that many standard database tools and techniques won't know what to make of enums, and EVEN if you don't think your database schema will ever migrate to another type of database... you could still run into major headaches if you use enum.

There are better ways (standard ways) to handle discrete, defined lists. That’s what relational databases are all about. Enum may seem convenient, but it’s really a cheap shortcut that will come back to bite you in the end.

[&#8595;](#watch-this-space) [&#8593;](#database)

#Watch This Space
...for more database tips!
