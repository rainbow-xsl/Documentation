#Database

- [Why "ID"?](#why-id)
- [Naming ID Columns](#naming-id-columns)
- [Normalization Example: States](#normalization-example-states)
- [Database Design: Three Areas of Optimization](#database-design-three-areas-of-optimization)
- [Enum: Just Say No](#enum-just-say-no)


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
