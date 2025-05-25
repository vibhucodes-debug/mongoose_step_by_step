# Monogoose CRUD 
Mongoose is a popular ODM (Object Data Modeling) library for MongoDB and Node.js that simplifies database interactions by providing a schema-based solution to model application data.

- Built on MongoDB for seamless integration with Node.js applications.
- Provides schema-based modeling to define document structure.
- Includes built-in validation to ensure data consistency.
- Enables easy querying and data relationships with chain query methods.

> `const mongoose = require('mongoose');`
  - Import mongoose in the application

> `mongoose.connect('mongodb://localhost:27017/myDatabase', {
    useNewUrlParser: true,
    useUnifiedTopology: true,
});`


