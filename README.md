# Jenkins Lab

## Ejecutar Docker Compose

Para ejecutar Docker Compose, asegúrate de que tengas Docker Compose instalado en tu sistema. Luego, sigue estos pasos:

1. Navega a la ubicación donde se encuentra tu archivo `docker-compose.yml`.

2. Ejecuta el siguiente comando en tu terminal para iniciar los contenedores definidos en el archivo `docker-compose.yml`:

```bash
docker-compose up -d
```
<img width="562" alt="Screenshot 2024-04-25 at 8 25 58 PM" src="https://github.com/juanosorio0219/jenkins-lab/assets/80568091/abf3edd9-566c-432b-baee-ec99d2478827">

3. Extraer passwords

```bash
docker logs id_container
```
<img width="564" alt="Screenshot 2024-04-25 at 8 27 32 PM" src="https://github.com/juanosorio0219/jenkins-lab/assets/80568091/2b94bd04-277c-480c-b5de-62e067239f83">

```bash
docker exec id_container cat /var/jenkins_home/secrets/initialAdminPassword
```
## Accedemos a Jenkins
En este caso: `http://localhost:8080`
<img width="988" alt="Screenshot 2024-04-25 at 8 32 05 PM" src="https://github.com/juanosorio0219/jenkins-lab/assets/80568091/f438501e-b563-4cff-b7e9-75b009aa7817">

## Instalamos los plugins
<img width="990" alt="Screenshot 2024-04-25 at 8 35 03 PM" src="https://github.com/juanosorio0219/jenkins-lab/assets/80568091/8b2340d8-9f67-426d-ab89-8d8eb994d7a6">


## Creación del Item
Escogemos un nombre y damos clic en Freestyle project
<img width="987" alt="Screenshot 2024-04-25 at 7 30 45 PM" src="https://github.com/juanosorio0219/jenkins-lab/assets/80568091/a1961037-d269-4749-bf66-2e8fb71d823d">

## Agregamos nuestro repositorio de GitHub
<img width="991" alt="Screenshot 2024-04-25 at 7 28 09 PM" src="https://github.com/juanosorio0219/jenkins-lab/assets/80568091/969f49de-2fba-4e7e-aeeb-381b5b3ce928">

## Proporcionamos el entorno de compilación necesario para nuestra app de Node.js
<img width="992" alt="Screenshot 2024-04-25 at 7 28 31 PM" src="https://github.com/juanosorio0219/jenkins-lab/assets/80568091/f9c6a7a3-0810-452c-bf5f-85e324c865ba">

## Agregamos los pasos que queremos verificar mediante la automatización
En este caso vamos a usar `npm install` para instalar las dependencias, `npm run build` para construir la app y `node app.js &` para correr la app. El símbolo agregado al final del comando es necesario para que el Item termine de ejecutarse, ya que al correr la app en segundo plano, Jenkins puede seguir con el paso a paso y terminar el Item.
<img width="972" alt="Screenshot 2024-04-25 at 7 28 45 PM" src="https://github.com/juanosorio0219/jenkins-lab/assets/80568091/bbce9521-1134-4ce9-aa5f-55c45bff5603">

## Aquí vemos los outputs que nos da el Item
<img width="998" alt="Screenshot 2024-04-25 at 7 29 23 PM" src="https://github.com/juanosorio0219/jenkins-lab/assets/80568091/dd56c11d-11dc-4ba8-9327-e0a3994cbb77">

## Verificamos que terminó de forma exitosa
<img width="1062" alt="Screenshot 2024-04-25 at 7 29 57 PM" src="https://github.com/juanosorio0219/jenkins-lab/assets/80568091/9830cc68-f87a-4aa4-845e-2f28b2efc0d5">

