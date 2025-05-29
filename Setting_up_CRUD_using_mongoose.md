# Monogoose CRUD 
Mongoose is a popular ODM (Object Data Modeling) library for MongoDB and Node.js that simplifies database interactions by providing a schema-based solution to model application data.

- Built on MongoDB for seamless integration with Node.js applications.
- Provides schema-based modeling to define document structure.
- Includes built-in validation to ensure data consistency.
- Enables easy querying and data relationships with chain query methods.

## Import mongoose in the application
> `const mongoose = require('mongoose');`

## Connect mongo db database
> `mongoose.connect('mongodb://localhost:27017/myDatabase', {useNewUrlParser: true,useUnifiedTopology: true,})` \
    `.then(() => console.log('MongoDB connected'))` \
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

## Creating a User Data using the Schema

> `const newUser = new User({
  name: 'Vaibhav Sharma',
  email: 'vaibhavsha@example.com',
  password: 'password123'
});`

>  Saving the created User data 

> `newUser.save()` \
  `.then(() => console.log('User created'))` \
  `.catch((err) => console.log(err));`

> *Create Method*
> `User.create({ name: 'Bob', email: 'bob@example.com', age: 30 })` \
  `.then(user => console.log('User created:', user))` \
  `.catch(err => console.error(err));`


## Reading the data from the database

> `User.find()` \
  `.then((users) => console.log(users))` \
  `.catch((err) => console.log(err));`


## Updating an Object to the database

> `User.findOneAndUpdate({name:'Vaibhav Sharma'},{name:'Vaibhav Only'})`

## Deleting an object from the database

> `User.deleteOne({name:'Vaibhav Sharma})` \
    `.then(console.log('User deleted')` \
    `.catch((error)=>console.log(error))`


# Other important Mongoose Queries

## Finding
> `User.find()` Find all users
> `User.find({ age: { $gt: 20 } })` For users older than 20
> `User.findOne({ email: 'alice@example.com' })` Finding one specific user
> `User.findById('60f7c0d5e1b2c8a1d4e8b123')`

## Updating
> `User.updateOne({ name: 'Alice' }, { age: 26 })` Update age of document with name 'Alice'
> `User.findByIdAndUpdate('60f7c0d5e1b2c8a1d4e8b123', { age: 27 }, { new: true })` Find a document with ID and update the following fields

## Deleting
> `User.deleteOne({name:'George'})`
> `User.findByIdAndDelete('60f7c0d5e1b2c8a1d4e8b123')`









