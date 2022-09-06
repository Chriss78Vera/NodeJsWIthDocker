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

## MINIKUBE

* para iniciar el contenedor de kubernets ejecutaremos el siguiente comando `minikube start`.

* Con el comando `minikube status` comprobaremos que esta perfectamente iniciado.

* Acontinuación crearemos los archivos.yaml para nuestro proyecto y para la base de datos en una carpeta dentro de nuestro codigo con cualquier nombre 

    ![image](https://user-images.githubusercontent.com/65980001/188562529-a09c66c3-9ce9-497c-87e1-0a0911c1c8ad.png)

    ![image](https://user-images.githubusercontent.com/65980001/188563004-af30d1ce-2e41-4e16-8892-8feb702e956f.png) 


* Luego ejecutaremos el comando para crear los nimikubes de cada uno y dentro del codigo iniciamos con el comando `kubectl apply -f` nombre de la carpeta con los .yml

* Por último para ver los pods generados apartir de los .yml ejecutaremos el comanod `kubectl get pods --watch`

# VIDEOS

- Manual de usuario: https://youtu.be/BHrxT0b6nXA
- Manual técnico: https://youtu.be/_0TaS7x5Ims

# INTEGRANTES
- Lizbeth García
- Kevin Veliz
- Christopher Vera
