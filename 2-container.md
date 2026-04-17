# Contenedores

### Crear un contenedor
Para crear un nuevo contenedor Docker a partir de una imagen específica, pero sin iniciarlo automáticamente. 

```
docker create --name <nombre contenedor> <nombre imagen>:<tag>
```
Crear el contenedor  **srv-web** usando la imagen nginx version alpine

<img width="988" height="107" alt="image" src="https://github.com/user-attachments/assets/c971dfbe-57f7-4400-b5c1-676322614109" />


Si creas un contenedor en Docker sin asignarle un nombre específico utilizando la opción --name, Docker asignará automáticamente un nombre aleatorio al contenedor. Este nombre suele consistir en una combinación de palabras y números.  

Crear el contenedor usando la imagen hello-world
<img width="1069" height="208" alt="image" src="https://github.com/user-attachments/assets/28d121ba-d018-4c41-a8b1-dc95bb39ffe0" />


### Listar los contenedores ejecutándose o no

```
docker ps -a
```

### Para iniciar un contenedor

```
docker start <nombre contenedor o identificador>
```
Iniciar el contenedor srv-web 

<img width="1441" height="163" alt="image" src="https://github.com/user-attachments/assets/aeba94f7-7bf5-4ea7-a0a1-104c18c68baa" />


### Listar los contenedores ejecutándose
```
docker ps 
docker ps | grep <nombre contenedor>
```

### Para detener un contenedor

```
docker stop <nombre contenedor>
```

### Para crear un contenedor y ejecutarlo inmediatamente

```
docker run --name <nombre contenedor> <nombre imagen>:<tag>
```
![Ecosistema de Docker](dockerRun.PNG)

Crear y ejecutar inmediatamente el contenedor **srv-web2** usando la imagen nginx:alpine

<img width="1566" height="768" alt="image" src="https://github.com/user-attachments/assets/318d277c-0742-4766-ac87-28451e541705" />


**¿Qué sucede luego de la ejecución del comando?**

La creacion del contenedor entra en una especie de bucle en el cual existen procesos que se estan ejecutando es decir el contenedor esta trabajando en primer plano mientras que la entrada de la terminal esta siendo capturada por el contenedor.

Cuando ejecutas un contenedor en primer plano sin la opción -d (modo detach), el contenedor captura la entrada estándar (stdin) del terminal, lo que significa que el terminal queda "atrapado" y no puedes introducir más comandos hasta que detengas el contenedor.

### Para crear un contenedor y ejecutarlo inmediatamente sin estar vinculados al mismo
-d: Es la opción que indica a Docker que ejecute el contenedor en segundo plano (en modo "detach").
Cuando un contenedor se ejecuta en segundo plano, Docker devuelve el control al terminal inmediatamente después de iniciar el contenedor, lo que permite al usuario seguir ejecutando otros comandos en el mismo terminal sin que el contenedor detenga la interacción.

```
docker run -d --name <nombre contenedor> <nombre imagen>:tag
```
Crear y ejecutar inmediatamente el contenedor **srv-web3** en modo detach usando la imagen nginx:alpine

<img width="973" height="113" alt="image" src="https://github.com/user-attachments/assets/0abbf315-4612-4b77-8165-97958363e8cc" />


### Para eliminar un contenedor

```
docker rm <nombre contenedor>
```
Eliminar el contenedor que se creó a partir de la imagen hello-world 

<img width="1619" height="280" alt="image" src="https://github.com/user-attachments/assets/ea744ab0-9a25-41db-bab2-b5893e875260" />


Verificar que el contenedor que se eliminó

<img width="1597" height="358" alt="image" src="https://github.com/user-attachments/assets/08ab468a-1ebc-4255-8d32-6512ac348f87" />


### Para eliminar un contenedor que esté ejecutándose

```
docker rm -f <nombre contenedor>
```
Eliminar el contenedor **srv-web3** 

<img width="808" height="80" alt="image" src="https://github.com/user-attachments/assets/6908f73a-5fcc-451a-8a6e-4e5f46561f49" />


Verificar que el contenedor que se eliminó

<img width="1878" height="103" alt="image" src="https://github.com/user-attachments/assets/15d8254b-66c9-4cd2-a9c3-fa3154360138" />


### Para inspecionar un contenedor 

Inspeccionar el contenedor **srv-web** 

<img width="1916" height="969" alt="image" src="https://github.com/user-attachments/assets/1d948108-d397-413a-8e9f-29b019a7f3eb" />

