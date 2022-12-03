# Documentacion
Esta es una aplicacion web utilizando el framework flask y bootstrap. Su proposito es ejemplificar un CRUD utilizando el recurso mensaje.
Los datos se guardan en la base de datos postgres utilizando migraciones.
Las dependencias del proyecto de gestionan con pipenv.
## Dependencias
Para correr este proyecto de necesita previamente tener instalado python 3 y su herramienta pip.
Para revisar si las tienes instalado debes ejecutar los siguientes comandos:
```
python -V
pip -V
```
El resultado debe indicar el número superior a 3.
Luego de clonar el repositorio y para instalar las dependencias debe ejecutar el comando
`pipenv install`
## Migraciones
Para ejecutar las migraciones el comando es el siguiente:
para ejecutar hacia adelante
```
flask db upgrade
```
para ejecutar hacia atràs 
```
flask db downgrade
```
En caso de modificar un modelo agregando o modificando un atributo , debemos generar una nueva migración con el comando
```
flask db migrate -m "Mensaje de la migracion"
```
**nota**:
Los comandos anteriores se deben ejecutar dentro de `pipenv shell`

## Blueprint
Los blueprint permiten componer aplicaciones desde componentes pequeños. Cada  componente es como una mini aplicaciòn.Permite crear aplicaciones grandes manteniendo el còdigo y la estructura  simples.

## Mòdulos

Para que los blueprint estenbien organizados, es mejor trabajarlos como modulos,es decir,que estèn dentro de una carpeta.Los mòdulos se pueden anidar,de hecho,nosotros hicimos el mòdulo `app` con su respectivo `__init__.py`y dentro tenemos otro mòdulo como el mòdulo `messages` que es ademas un blueprint.

## Levantando la aplicación
Para ejecutar el servidor de desarrollo el comando es el siguiente
```
flask --app app-- debug run
```

## Tarea 
crear un nuevo recurso sencillo,sin base de datos,como blueprint bajo la url`/memes` y debe renderiar un html lleno de memes.

## MVC (Model-View.Controller)
## Levantar el servidor de desarrollo
con todo esto
```bash
pipenv shell
pipenv install
set FLASK_APP=app
set FLASK_ENV=development
flask run
```
o con la siguiente linea
'pipenv run flask --app app ..debug run'
Y si tiene el archivo .env con las variables FLASK_DEBUG=1 y FLASK_APP=app, solo debe ejecutar lo siguiente
'flask run'
## Blueprints
## MVC
(Model-View-Controller)
![MVC](https://cdn.educba.com/academy/wp-content/uploads/2019/04/what-is-mvc-design-pattern.jpg.webp)
Es una arquitectura para separar las responsabilidades en la manipulacion de las solicitudes y respuestas. Quien recibe las solicitudes es el controlador  o en flask, las rutas .
los controladores se encargan de revisar las solicitudes cumpla con las caracteristicas ppara entregar respuestas acorde (que tenga todos los datos) Si el controlador lo permite, se podria opcionalmente llamar al modelo  para obtener o modificar los datos de la BBDO. Y finalmente enviar una respuesta que contenga la presentacion de la aplicacion. En nuestro caso la capa de ppresentacion comunmente conocida como Vistas(views)se llaman Templates.
Por lo tanto en flask el MVC podria ser adaptado como MTR (Modelo, Template,), pero es lo mismo en terminos de separar la responsabilidad.
(19 kB)
