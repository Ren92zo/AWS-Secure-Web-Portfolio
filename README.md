# AWS Secure Web Portfolio

## 1. Descripción del proyecto

Este proyecto consiste en diseñar e implementar un sitio web estático para presentar un currículum profesional, utilizando Amazon Web Services (AWS).

La solución utilizará Amazon S3 para almacenar los archivos del sitio y Amazon CloudFront para distribuir el contenido mediante HTTPS. Se aplicarán buenas prácticas de seguridad para restringir el acceso al almacenamiento y proteger la comunicación con los visitantes.

## 2. Objetivos

- Crear un sitio web estático utilizando HTML y CSS.
- Almacenar los archivos en un bucket de Amazon S3.
- Distribuir el sitio mediante Amazon CloudFront.
- Mantener el bucket privado y restringir el acceso al origen mediante Origin Access Control (OAC).
- Configurar y verificar HTTPS.
- Documentar las pruebas de seguridad y revisar los costos de AWS.

## 3. Arquitectura propuesta

**Flujo de acceso:**

Visitante → HTTPS → Amazon CloudFront → Origin Access Control (OAC) → Bucket privado de Amazon S3.

CloudFront entregará el contenido del sitio y utilizará OAC para acceder al origen S3 de forma autorizada. El bucket no necesitará habilitar el acceso público.

El diagrama definitivo se incorporará después de completar la configuración.

## 4. Servicios y tecnologías

- **Amazon S3:** almacenamiento de los archivos HTML, CSS e imágenes.
- **Amazon CloudFront:** distribución del contenido mediante ubicaciones perimetrales.
- **Origin Access Control (OAC):** control del acceso de CloudFront al origen S3.
- **HTTPS/TLS:** protección de la comunicación entre el navegador y el sitio.
- **HTML y CSS:** estructura y presentación visual del currículum.
- **GitHub:** documentación y control de versiones del proyecto.

## 5. Medidas de seguridad previstas

- Mantener activado el bloqueo de acceso público de Amazon S3.
- Utilizar un bucket privado.
- Aplicar una política de bucket que autorice únicamente el acceso necesario desde CloudFront.
- Utilizar HTTPS para las conexiones de los visitantes.
- Aplicar el principio de mínimo privilegio.
- Evitar publicar credenciales, claves de acceso y datos sensibles.

## 6. Plan de implementación

1. Preparar los archivos del sitio web.
2. Crear y configurar el bucket privado de Amazon S3.
3. Subir los archivos del sitio.
4. Crear una distribución de Amazon CloudFront.
5. Configurar OAC y los permisos necesarios en el bucket.
6. Verificar el acceso al sitio mediante HTTPS.
7. Realizar pruebas de seguridad y documentar los resultados.

## 7. Validación y evidencias

Se documentarán las siguientes comprobaciones una vez realizadas:

- Acceso correcto al sitio mediante la URL de CloudFront.
- Funcionamiento de HTTPS.
- Denegación del acceso público directo a los objetos de S3.
- Configuración de seguridad del bucket y de CloudFront.
- Revisión del uso y de los costos de AWS.

Las capturas de pantalla y los resultados se añadirán cuando las pruebas hayan sido ejecutadas.

## 8. Gestión de costos

Se revisarán los precios aplicables y el consumo de los servicios utilizados. Se comprobará la facturación durante el laboratorio y se eliminarán los recursos que ya no sean necesarios, después de verificar que se pueden retirar de forma segura.

## 9. Estado del proyecto

**Estado actual:** documentación inicial y planificación.

Las configuraciones, pruebas y resultados se actualizarán a medida que avance la implementación.

## 10. Aprendizajes esperados

- Despliegue de sitios web estáticos en AWS.
- Configuración básica de Amazon S3 y CloudFront.
- Control de acceso al origen mediante OAC.
- Aplicación de buenas prácticas de seguridad en la nube.
- Validación de HTTPS y de los permisos de acceso.
- Documentación técnica de un proyecto práctico de ciberseguridad.
