# ProyectoFinalAppDist
## Creación del Docker
- Para comenzar con el proyecto debemos crear una imagen de docker de nuestro proyecto. Para lo cual procederemos a crear un archivo "dockerfile" dentro de nuestro proycto y dentro de este procederemos a agregar la siguiente estructura.

    ![image](https://user-images.githubusercontent.com/65980001/188552593-3feab757-1fbc-4b98-9335-2d8d6fb39cbe.png)

      > Esta estructura nos sirve para crear una imagen de node, con una versión correspondiente.

* Acontinuación procederemos a ejecutar el siguiente comando `docker build -t knote`

      > Este comando nos sirve principalmente para crear la imagen de docker.

* Ahora procederemos a verificar si la imagen se creo de manera correcta para lo cual ejecutaremos el siguiente comando `docker images`.

* Ahora crearemos una imagen de MongoDB para realizar la conexión correspondiente. Para lo cual ejecutaremos el siguiente comando: `docker run --name=mongo --rm --network=knote mongo`
    
      > La estructura de este comando es la siguiente: 
        --name=mongo: es la imagen a crear
        --network=nombre del proyecto: es la instancia del network al cual le asignamos el nombre del proyecto.
      
### DOCKER-HUB

* Creamos un tag del proyecto con el siguiente comando `docker tag knote <username>/knote-js:1.0.0`
 
* Cambiamos `<username>` por el usuario que nos registramos en dockerhub 

* Acontinuación realizamos el push de la imagen con el comando `docker push <username>/knote-js:1.0.0`

* Luego corremos nuestra base MongoDB con el comando `docker run --name=mongo --rm --network=nodekub mongo`

* Y por último desplegamos la aplicación con el siguiente comando `docker run --name=nodekub --rm --network=nodekub -p 3000:3000 -e MONGO_URL=mongodb://mongo:27017/appdist chrissvera78/nodekub-js:1.0.0`

Ahora las imagenes creadas anteriormente se reflejan en la siguiente imagen

   ![image](https://user-images.githubusercontent.com/65980001/188557127-f397c297-0aef-4b63-b511-95a3df1a0ff4.png)

