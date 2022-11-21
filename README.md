# PRACTICA-RED-PG

PASO 1:

Para empezar la practica primero abrimos play with docker e iniciamos sesión

![Captura de pantalla 2022-11-11 154731](https://user-images.githubusercontent.com/91167254/201429122-005c34fa-95d5-478c-b039-dec5d7081f81.png)


Los comando a utilizar para la practica son: 
 * docker run: descarga y ejecuta un contenedor
 * -d: Permite correr en segundo plano
 * - - name: Agrega el nombre del contenedor
 * -p: Especifica que el puerto del anfitrión y el puerto del contenedor
 * -e: variable de entorno para el usuario Postgres
 *  postgres: nombre de la imagen tal cual aparece en el buscardor de dockerhub
 
 
 PASO 2:
 
 Una vez abierto play with docker poner el siguiente comando
 
 docker run -d --name dbpsql -e POSTGRES_PASSWORD=admin  -p 5432:5432 postgres
 
 
![image](https://user-images.githubusercontent.com/91167254/201429765-4c9388f3-48d0-4993-867c-51fb7f4780b7.png)
![image](https://user-images.githubusercontent.com/91167254/201429821-5a625f54-50be-43bd-9670-ba4d5ce627b7.png)

PASO 3:

Poner el siguiente comando para poner el EMAIL y la CONTRASEÑA

docker run -d --name pgadmin -p 8090:80 -e PGADMIN_DEFAULT_EMAIL=dflandi@sudamericano.edu.ec -e PGADMIN_DEFAULT_PASSWORD=admin dpage/pgadmin4

![image](https://user-images.githubusercontent.com/91167254/201430894-5beadba5-66f2-4b81-89c4-66ba76d62174.png)
![image](https://user-images.githubusercontent.com/91167254/201430924-6cffffe7-5029-4924-bf63-3d37a7960bc0.png)



PASO 4:
 Abir con localhost:8090
 
![image](https://user-images.githubusercontent.com/91167254/201431081-a1bbe06f-b3f4-46de-bd6e-3ddf29b074a9.png)

Y poner las credenciales para el inicio de sesión, al entrar a pgAdmin darle a añadir nuevo servidor


![WhatsApp Image 2022-11-19 at 12 01 14](https://user-images.githubusercontent.com/91167254/202937367-81b680f1-8136-4918-af1c-cc40fe84c0d8.jpeg)
 
 
Posteriormente agregar todas las credenciales para crear la base de datos

![WhatsApp Image 2022-11-19 at 12 01 20](https://user-images.githubusercontent.com/91167254/202937506-7ae9486c-22e5-42df-8978-7aa14a4ddade.jpeg)


PASO 5:

Crear red poniendo el siguiente comando:

![image](https://user-images.githubusercontent.com/91167254/201431180-a78da5bd-c90f-42dd-b1dd-541daa9eb358.png)


PASO 6:

(redfl puede cambiarse y ponerse otro nombre)

Agregar contenedores a la red
con los siguientes comandos:


Agrega contenedor de postgresql

docker network connect redfl dbpsql

![image](https://user-images.githubusercontent.com/91167254/201431434-f902ebb2-d9a7-410c-adf8-92cd012ee999.png)



#Agregar contenedor de pagadmin

docker network connect redfl pgadmin

![image](https://user-images.githubusercontent.com/91167254/201431555-05da7083-a335-4a90-bea4-b589e156ac04.png)



verificar contenedores conectados a la red. Este comando muestras las IPs
asignadas a cada contenedor

docker inspect redfl

![image](https://user-images.githubusercontent.com/91167254/201431860-f98ef27b-1de7-4297-9e62-3c15a019ee22.png)
![image](https://user-images.githubusercontent.com/91167254/201431888-0ae26a3a-bb43-4941-97e0-e261f7b20de0.png)
![image](https://user-images.githubusercontent.com/91167254/201431908-293d03d6-3e36-4ba5-85e4-d29ea12d6fea.png)
![image](https://user-images.githubusercontent.com/91167254/201431939-8a72aef2-5ad9-4953-aa1c-4dc856e2a193.png)

Y listo practica hecha. :)



