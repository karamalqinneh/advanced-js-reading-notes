To use mongoDB:

1-require mongoose after instaling it
2 define the schema using mongoose,Schema
3-create an instance of the schema and name it ex:

```
const blogSchema = new Schema(
  {
    title: {
      type: String,
      required: true,
    },
    snippet: {
      type: String,
      required: true,
    },
    body: {
      type: String,
      required: true,
    },
  },
  { timestamps: true }
);

```

4-create the model using mongoose.model('a singular name of the collection in mongo atlas', scehma instance object)
5- export the model

To use the model

1- create the DBURL provided by atlas (create a database then click connect using application to get url)
2-start listening to the requests (ex: app.listen()) in the .then handler as mongoose.connect returns a promise

To save data to the DB:

1- create an instance using the model that you imported to the controllers `const blog = new Blog({title: "example", .... , .... })`

2- use the save method on the instance noting that it returns a promise so you'll maybe need to send the response from it.

To get all data from the DB:

use the find method on the Model (not the instance) and it also returns a promise.

To get specific data from the DB:

use the findById method on the Model (not the instance) and it also returns a promise.
