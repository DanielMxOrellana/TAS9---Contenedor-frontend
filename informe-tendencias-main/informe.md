# Practica servidor web
## 1. Titulo
Implementación de un Servidor Web Contenerizado usando Docker y Nginx
## 2. Tiempo de duración
60 minutos
## 3. Fundamentos:

Para comprender esta práctica es necesario entender cómo funcionan los servidores web, la contenerización y el rol que cumplen herramientas como Docker y Nginx. Un servidor web es un software capaz de recibir solicitudes HTTP de los clientes (generalmente navegadores) y responder con contenido como archivos HTML, CSS, imágenes o datos. Entre los servidores web más utilizados se encuentra Nginx, conocido por su alto rendimiento, baja utilización de recursos y capacidad de manejar miles de conexiones simultáneas.

Por otro lado, Docker es una plataforma que permite empaquetar aplicaciones y sus dependencias dentro de contenedores. Estos contenedores son entornos ligeros y portables que aseguran que la aplicación corra de la misma manera en cualquier sistema operativo compatible. La combinación de Docker con Nginx facilita el despliegue de páginas web estáticas o dinámicas sin necesidad de instalar software adicional en el sistema operativo principal.

Un contenedor se crea a partir de una imagen, que es una plantilla que incluye todo lo necesario para ejecutar la aplicación. En esta práctica usarás la imagen oficial de Nginx y montarás dentro del contenedor un sitio web personalizado. Además, aprenderás a manipular archivos de configuración, exponer puertos y verificar el funcionamiento del servidor desde el navegador.

La arquitectura típica involucra un cliente que hace solicitudes a un servidor Nginx que corre dentro de un contenedor Docker. Esta separación permite modificar, actualizar o reiniciar el servidor sin afectar el sistema anfitrión. Figura 1-1 muestra un diagrama general de esta arquitectura:.


## 4. Conocimientos previos.
   
Para realizar esta práctica necesitas tener claros los siguientes temas:

Comandos Linux básicos.

Uso del navegador web.

Conceptos generales de redes.

Familiarización con Docker.

## 5. Objetivos a alcanzar
   
Implementar contenedores con Nginx.

Manipular archivos de configuración de un servidor web.

Exponer puertos para acceso desde el navegador.

Verificar el funcionamiento del servidor desplegado.
  
## 6. Equipo necesario:
  
-Computador con sistema operativo Windows.

Docker Desktop o Docker Engine instalado.

Conexión a internet.

Editor de texto (VS Code).

## 7. Material de apoyo.
Documentación oficial de Docker.

Guía de asignatura.

Linux cheat sheet.

Documentación de Nginx.
  
## 8. Procedimiento

Paso 1: Crear una carpeta llamada servidor-nginx.

Paso 2: Dentro de la carpeta, crear otra carpeta llamada html y agregar un archivo index.html.

Paso 3: Crear un archivo Dockerfile con el siguiente contenido:

FROM nginx:latest
COPY ./html /usr/share/nginx/html

Paso 4: Construir la imagen con:

docker build -t servidor-nginx .

Paso 5: Ejecutar el contenedor:

docker run -d -p 3000:30 servidor-nginx

Paso 6: Abrir el navegador y acceder a:

http://localhost:3000

Evidencias:
![alt text](<Captura de pantalla 2025-12-06 103139.png>)

![alt text](<Captura de pantalla 2025-12-06 105847.png>)

![alt text](<Captura de pantalla 2025-12-06 105905.png>)

![alt text](<Captura de pantalla 2025-12-06 105920.png>)
## 9. Resultados esperados:
    
El servidor web se ejecuta correctamente dentro del contenedor Docker y que la aplicación es accesible desde el navegador. Para validar esto, se espera que el estudiante logre:

Confirmar que el contenedor está corriendo mediante comandos como:
docker ps

Acceder desde el navegador a la aplicación web disponible en:
http://localhost:3000/

Visualizar correctamente la página index.html o la aplicación React, demostrando que el servidor Nginx (o el servidor de desarrollo de React, según el caso) está funcionando dentro del contenedor.

Evidenciar que el contenido mostrado proviene del contenedor, validando que el puerto ha sido expuesto y mapeado correctamente.

Comprobar que la estructura y archivos configurados se sirven sin errores, mostrando que el proceso de contenerización fue realizado con éxito.

## 10. Bibliografía
    
Docker, Inc. (s.f.). Docker Documentation. https://docs.docker.com

Nginx, Inc. (s.f.). Nginx Official Documentation. https://nginx.org

Smith, J. (2020). Web Servers Essentials. TechPress.
