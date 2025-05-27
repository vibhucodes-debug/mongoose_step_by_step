# Monogoose CRUD 
Mongoose is a popular ODM (Object Data Modeling) library for MongoDB and Node.js that simplifies database interactions by providing a schema-based solution to model application data.

- Built on MongoDB for seamless integration with Node.js applications.
- Provides schema-based modeling to define document structure.
- Includes built-in validation to ensure data consistency.
- Enables easy querying and data relationships with chain query methods.

## Import mongoose in the application
> `const mongoose = require('mongoose');`

## Connect mongo db database
> `mongoose.connect('mongodb://localhost:27017/myDatabase', {`  
    `useNewUrlParser: true,`
    `useUnifiedTopology: true,`
`}).then(() => console.log('MongoDB connected'))`
  `.catch((err) => console.log(err));` 

## Defining a Schema. Schemas define the structure of the documents in your collection.

> `const Schema = mongoose.Schema;`

> `const userSchema = new Schema({
  name: {
    type: String,
    required: true
  },
  email: {
    type: String,
    required: true,
    unique: true
  },
  password: {
    type: String,
    required: true
  },
  createdAt: {
    type: Date,
    default: Date.now
  }
});`

> `module.exports = mongoose.model('User', userSchema);`

## Creating a User Data using the schema

> `const newUser = new User({
  name: 'John Doe',
  email: 'johndoe@example.com',
  password: 'password123'
});`

>  

> 
