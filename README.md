\# Práctica Servidor Web Nginx con Docker



\## 1. Título

Despliegue y personalización de dos servidores web con Nginx usando Docker.



\## 2. Tiempo de duración

Aprox. 60 minutos



\## 3. Fundamentos

Docker permite crear contenedores que ejecutan aplicaciones de manera aislada. Nginx es un servidor web ampliamente utilizado para servir páginas HTML.  

En esta práctica se desplegaron dos contenedores: uno con información institucional y otro con información personal.  

Se manipuló el archivo `index.html` dentro de cada contenedor para personalizar los contenidos, comprendiendo cómo Docker mantiene cada contenedor aislado y cómo se pueden mapear puertos para acceder a los servicios desde la máquina host.  

Se reforzaron conceptos de virtualización ligera y manipulación de archivos dentro de entornos controlados.



\## 4. Conocimientos previos

\- Comandos básicos de Linux

\- Uso de navegador web

\- Conceptos de contenedores y Docker

\- Manejo de archivos HTML



\## 5. Objetivos a alcanzar

\- Implementar contenedores con Nginx.

\- Manipular archivos de configuración (`index.html`) dentro de contenedores.

\- Comprender el mapeo de puertos para acceder a servicios locales.



\## 6. Equipo necesario

\- PC con Windows 10/11

\- Docker Desktop instalado (v27.x)

\- Navegador web (Chrome, Edge, Firefox)

\- Git instalado para subir informe a GitHub



\## 7. Material de apoyo

\- Documentación oficial Docker

\- Guía de asignatura

\- Cheat sheet de Linux



\## 8. Procedimiento

1\. Descargar imagen oficial de Nginx: `docker pull nginx`

2\. Crear primer contenedor: `docker run -d --name nginx1 -p 8089:80 nginx`

3\. Crear segundo contenedor: `docker run -d --name nginx2 -p 8090:80 nginx`

4\. Copiar `index.html` del contenedor al host: `docker cp nginx1:/usr/share/nginx/html/index.html ./index1.html`

5\. Editar `index1.html` con información institucional y guardar

6\. Subir el archivo editado al contenedor: `docker cp index1.html nginx1:/usr/share/nginx/html/index.html`

7\. Repetir los pasos 4-6 para `nginx2` con información personal

8\. Verificar páginas en navegador:

&nbsp;  - Institucional → http://localhost:8089

&nbsp;  - Personal → http://localhost:8090



\## 9. Resultados esperados

\- Página institucional en contenedor nginx1

\- Página personal en contenedor nginx2

\- Ambas accesibles desde el navegador usando los puertos locales asignados

\- Capturas de pantalla de las páginas finales



