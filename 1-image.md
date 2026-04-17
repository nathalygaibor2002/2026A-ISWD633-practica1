# Imagen
### Descargar imagen
Descarga la última versión de la imagen disponible en el registro de Docker.

```
docker pull <nombre imagen> 
```

Descarga una versión específica de la imagen, cada imagen tiene etiquetas (tags) para diferentes versiones.
Una imagen puede tener la etiqueta latest para representar la última versión, si no se especifica una etiqueta se hará referencia a la versión latest.

```
docker pull <nombre imagen>:<tag>
```

Descargar la imagen **hello-world**

<img width="1247" height="158" alt="image" src="https://github.com/user-attachments/assets/ed0b7225-3f0f-44bf-a8ca-cb4dfa47e164" />


**¿Qué es nginx?**

 Es un servidor web de código abierto de alto rendimiento que también funciona como proxy inverso, balanceador de carga y caché HTTP

Descargar la imagen  **nginx** en la versión **alpine**

<img width="1358" height="378" alt="image" src="https://github.com/user-attachments/assets/442870a9-ccf0-4da0-ab27-ada422a9a72a" />


### Listar imágenes

```
docker images
```
<img width="959" height="186" alt="image" src="https://github.com/user-attachments/assets/587a8a6f-401a-49ac-b0ba-47b3a2931a50" />

**Identificadores**

En Docker, se utilizan varios identificadores para diferenciar de manera única los elementos del sistema, como imágenes, contenedores, volúmenes y redes. Estos identificadores son generados automáticamente por Docker y son únicos dentro del contexto del sistema Docker en el que se encuentran. 

### Inspeccionar una imagen
El comando docker inspect se utiliza para obtener información detallada sobre un objeto de Docker específico, como un contenedor, una imagen, un volumen o una red.  Proporciona información en formato JSON sobre el objeto especificado.

```
docker inspect <nombre imagen>
docker inspect <nombre imagen>:<tag>
```

Inspeccionar la imagen hello-world 
<img width="960" height="822" alt="image" src="https://github.com/user-attachments/assets/402f3bc7-7ef9-48e7-97b4-760b6230a665" />


**¿Con qué algoritmo se está generando el ID de la imagen?**

sha256

### Filtrar imágenes

```
docker images | grep <termino a buscar>

```

### Para eliminar una imagen
Eliminar permanentemente la imagen de tu sistema Docker.

```
docker rmi <nombre imagen>:<tag>
```

Eliminar la imagen hello-world 

<img width="1146" height="101" alt="image" src="https://github.com/user-attachments/assets/442fa020-c158-409a-a780-f0526fdb73a7" />


-f: Es la opción para forzar la eliminación de la imagen incluso si hay contenedores en ejecución que utilizan esa imagen.
Cuando eliminas una imagen Docker, Docker no elimina automáticamente los contenedores que se han creado a partir de esa imagen. Esto significa que, aunque hayas eliminado la imagen, el contenedor seguirá ejecutándose normalmente.  
**Considerar**
Eliminar una imagen no afecta a los contenedores que se han creado a partir de esa imagen, a menos que esos contenedores dependan de archivos o configuraciones específicas de la imagen eliminada. En ese caso, es posible que los contenedores se comporten de manera inesperada después de eliminar la imagen.
Es una buena práctica detener y eliminar todos los contenedores que dependan de una imagen antes de eliminar la imagen en sí.

```
docker rmi -f <nombre imagen>:<tag>
```
