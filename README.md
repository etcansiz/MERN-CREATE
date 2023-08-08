# MERN-CREATE

## STEPS OF MERN

### For Server Side Creating Node.js


> ***npm create -y***
>
> ***npm i mongoose express dotenv nodemon***
>

In package.json  

>***"type": "module"***
>
> "scripts": {
    "devStart": "nodemon server.js"
  } 

  

### This is server.js file which connects us to the DB
  
```javascript
//server.js

import dotenv from 'dotenv';
import mongoose from 'mongoose';
import express from 'express';
import cors from 'cors';
import routes from './Router/routes.js';


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

app.use(routes);

app.listen(4000, () => console.log('Server Started.'));


```







