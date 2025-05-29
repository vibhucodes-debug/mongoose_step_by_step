## What is the difference between a Schema and a Model in Mongoose?
> In Mongoose, both Schemas and Models are essential building blocks for working with MongoDB, but they serve different purposes.
>  - A Schema defines the structure of the documents within a MongoDB collection. It’s like a blueprint or a contract that tells Mongoose what fields a document should have and what types those fields should be.
>  - A Model is a wrapper for the schema and provides an interface to interact with the database. It lets you create, read, update, and delete documents (CRUD operations).
>  - `const User = mongoose.model('User', userSchema);`
>  This creates a Model called User based on the userSchema. We can now use 'User' to interact with the users collection in Mongo DB.
