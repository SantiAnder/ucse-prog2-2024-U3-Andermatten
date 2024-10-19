Una vez agregados ambos dockerfiles, ejecuto el comando <docker build -t app1/app2> para crear la imagen de cada aplicación.

![image](https://github.com/user-attachments/assets/b5b2bb13-fc7c-4b31-975f-7c1b551d7ded)

Luego, creamos el docker compose situandonos en el archivo raíz de ambas apps en la terminal y ejecutando "docker-compose up".

![image](https://github.com/user-attachments/assets/49fe2d4a-8a30-42df-be09-eb9ec9ee7706)

Ahora podemos obserar que mientras el docker-compose esta corriendo, podemos acceder a las urls <http://localhost:4000/tz?zone=America/Los_Angeles>, <http://localhost:4000/tz?zone=America/New_York> y ver la zona horaria de New York y Los Angeles.

![image](https://github.com/user-attachments/assets/caacce86-e1ca-4959-92ca-660871dfc7ac)


# Correcciones - Estado: APROBADO
- La aplicación funciona bien y el docker-compose es correcto, muy buen trabajo
- Como aclaración porque veo que en el README.md no lo están probando correctamente, cuando se hace "docker-compose up" la aplicación debería hacer el build y el bootstraping de los servicios. 
Una vez se ejecutaron, al acceder a la siguiente url `http://localhost:4001/checker?url=aplicacion1&zone=America/New_York` éste servicio "aplicacion2" se conecta con la "aplicacion1" y retorna el valor. 
Noten que se pasan 2 query parameters, uno es el zone y el otro el nombre del contenedor del servicio 1 para poder generar el request correspondiente al contenedor del servicio1.

Les dejo otras urls para testear:

	http://localhost:4001/checker
	http://localhost:4001/checker?url=aplicacion1&zone=America/Argentina/Buenos_Aires
	http://localhost:4001/checker?url=aplicacion1&zone=America/New_York
	http://localhost:4001/checker?url=aplicacion1&zone=Europe/London
Más acerca de timezones https://en.wikipedia.org/wiki/List_of_tz_database_time_zones

- Podrían haber utilizado "container_name" como parámetro en el docker-compose.yml (https://community.bigbeartechworld.com/t/customizing-container-names-in-docker-and-docker-compose/320)

