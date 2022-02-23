# Data Modeling

## SQL VS. NoSQL

### SQL

SQL databases Consists of tables that has records and fields, in most cases there is more than one table and they should be relatable to fully take advantage of SQL databases.
SQL databases uses SQL (structured query language) for defining and manipulating the data, which is very powerful therefore SQL databases records have to adhere to the schema.

For complex queries: SQL databases are good fit for the complex query intensive environment. To sum it up, SQL main characteristics are strict schema and the relation world.

The relational databases usually are scaled vertically updating the server capabilities. A good point to know about them is that they can’t be horizontally scaled.

### NoSQL

NoSQL on the other hand also have databases but consists of collections which have documents. These documents don’t have to have the same schema, therefore documents can have multiple documents in one collection that have different fields. This means that there is usually no relations and that’s the thing in NoSQL they rely less on relations than SQL.

Having no relations leads having the data stored and managed in several places, which gives the flexibility of both horizontal and vertical scaling.

# Review, Research, and Discussion

### What’s the primary difference between ES6 Classes and Constructor/Prototype Classes?

They mainly differ on hoisting as the constructor based classes can be called even before instantiating.

### Name 3 advantages to Test Driven Development

1. The software design becomes modular.
2. The code is easier to maintain.
3. Code refactoring goes more smoothly.

### What is one downside of Test Driven Development?

It may be tough to write the tests, especially if they go beyond unit testing. It may initially slow down development, but in the long run, it actually accelerates it. For unit testing to be effective, the entire team must believe in it.

### In what case would you need to use `beforeEach()` or `afterEach()` in a test suite?

If each test in your describe requires a new copy of the structure because each test modifies it, you should use beforeEach to build a new copy of the structure for each test and then afterEach to cleanly break it down.
