#Database

- [Enum: Just Say No](#enum-just-say-no)
- [Database Design: Three Areas of Optimization](#database-design-three-areas-of-optimization)

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

[&#8595;](#database) [&#8593;](#database)
===========
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

[&#8595;](#database) [&#8593;](#database)
