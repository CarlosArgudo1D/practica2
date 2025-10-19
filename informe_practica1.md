\# Práctica Servidor Web con Docker y Nginx



\## 1. Título

\*\*Despliegue y personalización de servidores web Nginx usando contenedores Docker en Windows\*\*



\## 2. Tiempo de duración

Aproximadamente 90 minuto# Práctica Servidor Web con Docker y Nginx



\## 1. Título

\*\*Despliegue y personalización de servidores web Nginx usando contenedores Docker en Windows\*\*



\## 2. Tiempo de duración

Aproximadamente 90 minutos (instalación, configuración y personalización).



\## 3. Fundamentos

En esta práctica se trabaja con \*\*Docker\*\*, una plataforma de virtualización ligera que permite crear contenedores independientes. Un contenedor es un paquete que incluye todo lo necesario para ejecutar una aplicación, incluyendo el código, las librerías y dependencias. Esto asegura que la aplicación se ejecute de manera consistente en cualquier entorno.



Se utilizará \*\*Nginx\*\*, un servidor web de alto rendimiento, para desplegar páginas HTML. Nginx sirve contenido estático y actúa como proxy inverso si fuera necesario. La manipulación de los archivos `index.html` dentro del contenedor permitirá personalizar la página de inicio según los requerimientos (institucional o personal).



\*\*Imágenes de apoyo:\*\*



\*\*Figura 1-1. Arquitectura de contenedores Nginx\*\*

!\[Diagrama de contenedores](https://upload.wikimedia.org/wikipedia/commons/6/62/Docker\_Containers.png)



El flujo es el siguiente: el contenedor Nginx se ejecuta aislado, pero mapea un puerto del host de Windows para que sea accesible desde el navegador. Se copian los archivos HTML hacia y desde el contenedor para modificar el contenido, demostrando el aislamiento de contenedores y la persistencia de cambios.



\*\*Conceptos clave:\*\*

\- Contenedor: entorno aislado para aplicaciones.

\- Imagen: plantilla inmutable para crear contenedores.

\- Volumen: permite persistir datos fuera del contenedor.

\- Puertos: mapeo entre host y contenedor para acceso externo.



Se demuestra cómo los contenedores permiten \*\*desarrollar, probar y desplegar aplicaciones\*\* de manera uniforme, evitando conflictos de dependencias y simplificando la gestión de entornos.



---



\## 4. Conocimientos previos

Para realizar esta práctica, se requiere:

\- Comandos básicos de PowerShell o terminal de Windows.

\- Manejo de navegador web para pruebas locales.

\- Conocimientos de HTML básico.

\- Conceptos de virtualización y contenedores.

\- Uso de Docker: imágenes, contenedores, puertos y copiado de archivos.



---



\## 5. Objetivos a alcanzar

\- Implementar contenedores con Nginx en Windows.

\- Manipular archivos de configuración y páginas web dentro de contenedores.

\- Exponer puertos de los contenedores para acceso local desde navegador.

\- Generar evidencia y documentación de la práctica en formato Markdown.



---



\## 6. Equipo necesario

\- Computador con Windows 10/11.

\- Docker Desktop instalado.

\- Navegador web (Chrome, Edge o Firefox).

\- Editor de texto (Notepad, VS Code o nano para Windows si se instala).

\- Git para subir repositorio a GitHub.

\- Conexión a internet estable.



---



\## 7. Material de apoyo

\- Documentación oficial de Docker: \[https://docs.docker.com/](https://docs.docker.com/)

\- Guía de asignatura de Tendencias Tecnológicas.

\- Cheat sheet de comandos básicos de Linux y Docker.

\- Tutorial de Nginx: \[https://nginx.org/en/docs/](https://nginx.org/en/docs/)



---



\## 8. Procedimiento



\### Paso 1: Descargar imagen Nginx

```powershell

docker pull nginx

s (instalación, configuración y personalización).



\## 3. Fundamentos

En esta práctica se trabaja con \*\*Docker\*\*, una plataforma de virtualización ligera que permite crear contenedores independientes. Un contenedor es un paquete que incluye todo lo necesario para ejecutar una aplicación, incluyendo el código, las librerías y dependencias. Esto asegura que la aplicación se ejecute de manera consistente en cualquier entorno.



Se utilizará \*\*Nginx\*\*, un servidor web de alto rendimiento, para desplegar páginas HTML. Nginx sirve contenido estático y actúa como proxy inverso si fuera necesario. La manipulación de los archivos `index.html` dentro del contenedor permitirá personalizar la página de inicio según los requerimientos (institucional o personal).



\*\*Imágenes de apoyo:\*\*



\*\*Figura 1-1. Arquitectura de contenedores Nginx\*\*

!\[Diagrama de contenedores](https://upload.wikimedia.org/wikipedia/commons/6/62/Docker\_Containers.png)



El flujo es el siguiente: el contenedor Nginx se ejecuta aislado, pero mapea un puerto del host de Windows para que sea accesible desde el navegador. Se copian los archivos HTML hacia y desde el contenedor para modificar el contenido, demostrando el aislamiento de contenedores y la persistencia de cambios.



\*\*Conceptos clave:\*\*

\- Contenedor: entorno aislado para aplicaciones.

\- Imagen: plantilla inmutable para crear contenedores.

\- Volumen: permite persistir datos fuera del contenedor.

\- Puertos: mapeo entre host y contenedor para acceso externo.



Se demuestra cómo los contenedores permiten \*\*desarrollar, probar y desplegar aplicaciones\*\* de manera uniforme, evitando conflictos de dependencias y simplificando la gestión de entornos.



---



\## 4. Conocimientos previos

Para realizar esta práctica, se requiere:

\- Comandos básicos de PowerShell o terminal de Windows.

\- Manejo de navegador web para pruebas locales.

\- Conocimientos de HTML básico.

\- Conceptos de virtualización y contenedores.

\- Uso de Docker: imágenes, contenedores, puertos y copiado de archivos.



---



\## 5. Objetivos a alcanzar

\- Implementar contenedores con Nginx en Windows.

\- Manipular archivos de configuración y páginas web dentro de contenedores.

\- Exponer puertos de los contenedores para acceso local desde navegador.

\- Generar evidencia y documentación de la práctica en formato Markdown.



---



\## 6. Equipo necesario

\- Computador con Windows 10/11.

\- Docker Desktop instalado.

\- Navegador web (Chrome, Edge o Firefox).

\- Editor de texto (Notepad, VS Code o nano para Windows si se instala).

\- Git para subir repositorio a GitHub.

\- Conexión a internet estable.



---



\## 7. Material de apoyo

\- Documentación oficial de Docker: \[https://docs.docker.com/](https://docs.docker.com/)

\- Guía de asignatura de Tendencias Tecnológicas.

\- Cheat sheet de comandos básicos de Linux y Docker.

\- Tutorial de Nginx: \[https://nginx.org/en/docs/](https://nginx.org/en/docs/)



---



\## 8. Procedimiento



\### Paso 1: Descargar imagen Nginx

```powershell

docker pull nginx



Paso 2: Crear contenedores

docker run -d --name nginx1 -p 8089:80 nginx

docker run -d --name nginx2 -p 8090:80 nginx





Paso 3: Copiar y editar archivos

docker cp nginx1:/usr/share/nginx/html/index.html C:\\Users\\carlo\\index1.html

docker cp nginx2:/usr/share/nginx/html/index.html C:\\Users\\carlo\\index2.html

notepad C:\\Users\\carlo\\index1.html

notepad C:\\Users\\carlo\\index2.html

docker cp C:\\Users\\carlo\\index1.html nginx1:/usr/share/nginx/html/index.html

docker cp C:\\Users\\carlo\\index2.html nginx2:/usr/share/nginx/html/index.html







Paso 4: Verificar en navegador



http://localhost:8089

&nbsp;→ Información institucional



http://localhost:8090

&nbsp;→ Información personal







9\. Resultados esperados



Dos contenedores Nginx corriendo de forma independiente.



Páginas web personalizadas accesibles desde el navegador.



Comprensión de manipulación de archivos dentro de contenedores y mapeo de puertos.



