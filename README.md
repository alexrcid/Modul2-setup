# Modul 2 Kick-Off

## Comenzar un proyecto
### Express 

[Link](https://expressjs.com/en/4x/api.html)

instalar express generator global 
    `$ npm install -g express-generator`
1- crear un proyecto
    `$ express <carpeta name> --view=ejs --git`
2 - Asegurarse que entras en la carpeta
     `$ cd <carpeta name >`
3 - Instalar dependencias 
     `$ npm install`
4 - Borrar rutas/vistas que no utilices
5 - Instalar nodemon 
    `$ npm install --save-dev nodemon`
    package.json
```
{
    ...
    "scripts": {
        "dev": "nodemon ./bin/www",
        "start": "node ./bin/www"
    },
    ...
}
```

### Mongoose

[Link](https://mongoosejs.com/docs/guide.html)

5 - Configurar Mongoose 
     `npm install --save mongoose`

**app.js**
```
    const mongoose = require('mongoose');
    mongoose.connect('mongodb://localhost/product-example-development')
```

6 - Crear el modelo y una carpeta llamada `models`

**models.js**
```
....
const mongoose = require('mongoose');
const Schema = mongoose.Schema;

const blogSchema = new Schema({
  name: String
}, {
  timestamps: {
    createdAt: "created_at",
    updatedAt: "updated_at"
  }
});

const Blog = mongoose.model('Blog', blogSchema);

module.exports = Blog;
....
```

7 - CRUD - Queries

- [Methods model](https://mongoosejs.com/docs/api.html#Model)

### Express Layout

8 - Express EJS Layout

[Link](https://github.com/Soarez/express-ejs-layouts#readme)

`$ npm install --save express-ejs-layouts`
**app.js**
```
    const expressLayouts = require('express-ejs-layouts');

    ...
    app.set('views', path.join(__dirname, 'views'));
    app.set('view engine', 'ejs');
    app.set('layout', 'layouts/main'); // custom layout

    app.use(expressLayouts); 
    ...
```
crear la carpeta layout `views/layouts/` y dentro `main.ejs`

```
views
├── ...
├── partials
│   ├── navbar.ejs
│   └── footer.ejs
└── layouts
    ├── main.ejs
    └── secondLayout.ejs
```
