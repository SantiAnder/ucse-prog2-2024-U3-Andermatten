Una vez agregados ambos dockerfiles, ejecuto el comando <docker build -t app1/app2> para crear la imagen de cada aplicación.

![image](https://github.com/user-attachments/assets/b5b2bb13-fc7c-4b31-975f-7c1b551d7ded)

Luego, creamos el docker compose situandonos en el archivo raíz de ambas apps en la terminal y ejecutando "docker-compose up".

![image](https://github.com/user-attachments/assets/49fe2d4a-8a30-42df-be09-eb9ec9ee7706)

Ahora podemos obserar que mientras el docker-compose esta corriendo, podemos acceder a las urls <http://localhost:4000/tz?zone=America/Los_Angeles>, <http://localhost:4000/tz?zone=America/New_York> y ver la zona horaria de New York y Los Angeles.

![image](https://github.com/user-attachments/assets/caacce86-e1ca-4959-92ca-660871dfc7ac)




