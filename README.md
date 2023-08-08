# MERN-CREATE
Steps of creating mern stack project


import dotenv from 'dotenv';
import mongoose from 'mongoose';
import express from 'express';
import cors from 'cors';
import routes from './Router/routes.js';

//npm create -y
//npm i mongoose express dotenv nodemon
//"type": "module",
// add scripts -- "devStart": "nodemon server.js"
// now project is ready


dotenv.config();

const app = express();
app.use(express.json());
app.use(cors());

mongoose.connect(process.env.DATABASE_URL, { useNewUrlParser: true });

const db = mongoose.connection;
db.on('error', (error) => console.error(error));
db.once('open', () => console.log('Database\'a bağlandı'));

app.use(routes);

app.listen(4000, () => console.log('Sunucu başlatıldı.'));
