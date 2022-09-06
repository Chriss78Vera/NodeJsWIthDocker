# ProyectoFinalAppDist
## Creación del Docker
- Para comenzar con el proyecto debemos crear una imagen de docker de nuestro proyecto. Para lo cual procederemos a crear un archivo "dockerfile" dentro de nuestro proycto y dentro de este procederemos a agregar la siguiente estructura.

    ![image](https://user-images.githubusercontent.com/65980001/188552593-3feab757-1fbc-4b98-9335-2d8d6fb39cbe.png)

      > Esta estructura nos sirve para crear una imagen de node, con una versión correspondiente.

* Acontinuación procederemos a ejecutar el siguiente comando `docker build -t nombre del proyecto`

      > Este comando nos sirve principalmente para crear la imagen de docker.

* Ahora procederemos a verificar si la imagen se creo de manera correcta para lo cual ejecutaremos el siguiente comando `docker images`.

* Acontinuación nos vamos a docker y comprobaremos que se haya creado la imagen. 

    ![image](https://user-images.githubusercontent.com/65980001/188553410-4714309a-4107-44ca-a480-1279861879cc.png)

* Ahora crearemos una imagen de MongoDB para realizar la conexión correspondiente. Para lo cual ejecutaremos el siguiente comando: `docker run --name=mongo --rm --network=nombre del proyecto mongo`
    
      > La estructura de este comando es la siguiente: 
        --name=mongo: es la imagen a crear
        --network=nombre del proyecto: es la instancia del network al cual le asignamos el nombre del proyecto.
      
      
