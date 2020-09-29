# FilmApiRestFlask
Para crear el API, además de Flask, haremos uso de las siguientes extensiones:

* **Flask Restful:** Es una extensión que permite generar APIs REST muy fácilmente. Además, viene con un montón de utilidades.
* **Flask SQLAlchemy:** Para interactuar con la base de datos a través de su ORM. Puedes encontrar más información aquí.
* **lask Migrate:** Esta extensión permite generar las tablas de la base de datos a partir de ficheros de migración. Puedes encontrar más información aquí.
* **Flask Marshmallow:** Es una extensión que facilita la serialización de los modelos de la base de datos a JSON y viceversa. Está basada en Marshmallow.
Marshmallow SQLAlchemy: Para integrar Flask Marshmallow con SQLAlchemy.

```
$> pip install flask flask_restful flask_sqlalchemy flask_migrate flask_marshmallow marshmallow-sqlalchemy
```


# Los modelos

Vamos a utilizar dos modelos: Film y Actor. El modelo Film representa a una película del catálogo y está compuesto por los siguientes atributos:

* ```id```, clave primaria.
* ```title```, título de la película.
* ```length```, duración (en segundos) de la película.
* ```year```, año de estreno.
* ```director```, director de la película.
* ```actors```, lista con los actores de la película.

Por su parte, el modelo Actor representa a un actor y está formado por los siguientes atributos:

* ```id```, clave primaria.
* ```name```, nombre del actor.
* ```film_id```, clave ajena a la película en la que aparece.

# Variables de entorno
``` 
export FLASK_APP="entrypoint:app"
export FLASK_ENV="development"
export APP_SETTINGS_MODULE="config.default" 
```

# Crear base de datos y tablas
```
$> flask db init
$> flask db migrate -m "Initial_db"
$> flask db upgrade 
```

# El API REST en Flask en funcionamiento
```
$> flask run
```

# Estructura de pelicula en JSON
```
{
    "title": "Forrest Gump",
    "length": 8520,
    "year": 1994,
    "director": "Robert Zemeckis",
    "actors": [
        { "name": "Tom Hanks"},
        { "name": "Robin Wright"},
        { "name": "Gary Sinise"},
        { "name": "Mykelti Williamson"},
        { "name": "Sally Field"},
        { "name": "Michael Conner Humphreys"}
    ]
}
```
