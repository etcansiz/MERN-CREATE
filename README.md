# MERN-CREATE

## STEPS OF MERN

### For Server Side Creating Node.js

```sh
npm create -y
```
 Now we are ready to install packages

```sh
npm i mongoose express dotenv nodemon cors
```


In package.json  

> ***"type": "module"***
>
> ***"scripts": {
    "devStart": "nodemon server.js"
  }*** 
  
  

### This is server.js file which connects us to the DB
  
```javascript
//server.js

import dotenv from 'dotenv';
import mongoose from 'mongoose';
import express from 'express';
import cors from 'cors';



//This file for security,we create .env file and giving the DATABASE_URL = "you will copy from your own mongodb cluster" 
//Import top of the this project.

dotenv.config();


const app = express();
app.use(express.json());

//To data transfer we should use the cors
app.use(cors());

mongoose.connect(process.env.DATABASE_URL, { useNewUrlParser: true });

const db = mongoose.connection;
db.on('error', (error) => console.error(error));
db.once('open', () => console.log('Connected to the database...'));



app.listen(4000, () => console.log('Server Started.'));


```

### To start server ...
```sh
npm run devStart
```

## CLIENT SIDE

### It is easy, we just create and start a React project.

```sh
npx create-react-app my-react-app
```

### After create write this to the terminal.
```sh
npm start
```
## Now you are ready to the develope full stack websites.








