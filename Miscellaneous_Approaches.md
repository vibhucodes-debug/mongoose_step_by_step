# Connection Approach 1

const mongoose = require('mongoose');

mongoose.connect('mongodb://localhost/my_database', { useNewUrlParser: true });
> Mongoose creates a default connection object when you call mongoose.connect().

const db = mongoose.connection; > Default connection object

db.on('error', console.error.bind(console, 'connection error:'));
db.once('open', function() {
  console.log('Database connected successfully');
});

- Here's what it does:
  mongoose.connection gives you direct access to the connection instance.
  By assigning it to db, you can easily attach event listeners like:
  db.on('error', ...) — to handle connection errors.
  db.once('open', ...) — to run code once the connection is successfully opened.

- Why use it?
  This approach is useful when:  

  You want fine-grained control over connection events.
  You need to listen to multiple events (e.g., connected, disconnected, reconnected, etc.).
  You're working in an environment where event-driven programming is preferred.
  
# Connection approach 2


const mongoose = require('mongoose'); 

mongoose.connect('mongodb://localhost/my_database', { useNewUrlParser: true, useUnifiedTopology: true }) \
  .then(() => { \
    console.log('Database connected successfully'); \
  }) \
  .catch((err) => { \
    console.error('Connection error:', err); \
  });

  - *We can use .then() and .catch() with mongoose.connect() instead of using db.on() and db.once(). This approach uses Promises, which can make your code cleaner and easier to manage, especially when working with asynchronous operations.*


