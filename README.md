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

  


  
```javascript

dotenv.config();

const app = express();
app.use(express.json());
app.use(cors());

mongoose.connect(process.env.DATABASE_URL, { useNewUrlParser: true });

const db = mongoose.connection;
db.on('error', (error) => console.error(error));
db.once('open', () => console.log('Database\'a baðlandý'));

app.use(routes);

app.listen(4000, () => console.log('Sunucu baþlatýldý.'));


```







