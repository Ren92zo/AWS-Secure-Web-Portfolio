# AWS Secure Web Portfolio

## 1. Descripción del proyecto

Proyecto práctico de ciberseguridad cloud que consiste en desplegar un portafolio web estático utilizando Amazon Web Services (AWS).

La solución utiliza Amazon S3 para almacenar los archivos del sitio y Amazon CloudFront para distribuir el contenido mediante HTTPS. Se implementó un origen privado con Origin Access Control (OAC), evitando que los visitantes necesiten acceder directamente al bucket S3.

El proyecto demuestra la aplicación de controles de acceso, protección del origen, comunicación cifrada y buenas prácticas de gestión de costos en la nube.

**Sitio web:** https://d1aao9ojsg10jv.cloudfront.net/

**Repositorio:** https://github.com/Ren92zo/AWS-Secure-Web-Portfolio

## 2. Objetivos

- Desplegar un sitio web estático mediante servicios de AWS.
- Almacenar los archivos del sitio en un bucket privado de Amazon S3.
- Distribuir el contenido mediante Amazon CloudFront con HTTPS.
- Configurar Origin Access Control (OAC) para controlar el acceso al origen.
- Validar el funcionamiento del sitio y la denegación del acceso directo a los objetos de S3.
- Revisar el uso de los servicios y la información de facturación.
- Documentar las decisiones técnicas y los controles de seguridad implementados.

## 3. Arquitectura

**Flujo de acceso:**

Visitante → HTTPS/TLS → Amazon CloudFront → OAC → Bucket privado de Amazon S3.

Amazon CloudFront distribuye el contenido del sitio web y utiliza
Origin Access Control (OAC) para autorizar las solicitudes al
origen de Amazon S3. El bucket permanece privado, sin necesidad
de habilitar el acceso público a sus objetos.

Esta arquitectura separa la distribución del contenido de su
almacenamiento y reduce la exposición directa del origen.

### Diagrama de arquitectura

![Arquitectura de AWS Secure Web Portfolio](docs/aws-architecture.png)

## 4. Servicios y tecnologías

- **Amazon S3:** almacenamiento de los archivos estáticos del sitio.
- **Amazon CloudFront:** distribución del contenido web.
- **Origin Access Control (OAC):** autorización del acceso de CloudFront al origen S3.
- **HTTPS/TLS:** cifrado de la comunicación entre el navegador y CloudFront.
- **HTML5 y CSS3:** estructura y presentación del sitio.
- **GitHub:** alojamiento del código fuente y documentación del proyecto.

## 5. Controles de seguridad implementados

- Bloqueo de acceso público de Amazon S3 habilitado.
- Bucket S3 mantenido privado.
- Política del bucket configurada para autorizar el acceso requerido desde la distribución de CloudFront.
- Uso de OAC para proteger el origen.
- Distribución del sitio mediante HTTPS.
- Aplicación del principio de mínimo privilegio en los permisos necesarios para el acceso al contenido.
- Exclusión de credenciales y secretos del repositorio público.

## 6. Validaciones realizadas

### 6.1. Disponibilidad del sitio

Se comprobó que el portafolio pudiera abrirse mediante el dominio de CloudFront y que el contenido web se mostrara correctamente.

### 6.2. Comunicación HTTPS

Se verificó que el sitio fuera accesible mediante HTTPS y que el navegador estableciera una conexión segura con CloudFront.

### 6.3. Protección del origen S3

Se comprobó que el acceso directo al objeto de S3 estuviera denegado y devolviera `403 AccessDenied`. Este resultado es coherente con un origen privado y las restricciones de acceso configuradas.

### 6.4. Revisión de los controles

Se revisaron el bloqueo de acceso público del bucket y la política que autoriza el acceso de CloudFront mediante OAC.

### 6.5. Revisión de costos

Se revisó la información de facturación disponible en AWS para supervisar el consumo asociado al proyecto. Los cargos pueden variar según las solicitudes, la transferencia de datos, el almacenamiento y las condiciones aplicables a cada servicio.

Las validaciones se documentan mediante descripciones técnicas, sin publicar capturas de la consola de AWS ni información sensible de la cuenta.

## 7. Gestión de costos

La supervisión de costos forma parte del mantenimiento responsable de los recursos desplegados en AWS.

Buenas prácticas aplicables al proyecto:

- Revisar AWS Billing y Cost Explorer, según su disponibilidad.
- Evaluar el consumo de almacenamiento, solicitudes y transferencia de datos.
- Considerar la configuración de alertas presupuestarias.
- Identificar los recursos que ya no sean necesarios y comprobar sus dependencias antes de eliminarlos.
- Revisar los recursos activos y las condiciones de facturación para evitar cargos inesperados.

La disponibilidad de niveles gratuitos y los costos aplicables dependen del servicio, la región y las condiciones vigentes de la cuenta.

## 8. Privacidad del repositorio

El repositorio público presenta el código fuente y la documentación técnica necesaria para comprender el proyecto, evitando divulgar información privada.

No se incluyen intencionalmente credenciales, contraseñas, claves de acceso ni archivos de facturación. La documentación evita publicar identificadores de cuenta y detalles de infraestructura que no sean necesarios para explicar la implementación.

## 9. Conclusiones

El proyecto permitió aplicar conceptos de seguridad cloud mediante el despliegue de un sitio web estático con Amazon S3 y Amazon CloudFront. La combinación de un origen privado, OAC y HTTPS contribuye a reducir la exposición directa del almacenamiento y proteger la comunicación con los visitantes.

Las validaciones de acceso y funcionamiento permiten documentar los controles aplicados, mientras que la revisión de costos y la protección de la información publicada refuerzan las buenas prácticas de administración de recursos en la nube.

## 10. Aprendizajes obtenidos

- Despliegue de sitios web estáticos en AWS.
- Uso de Amazon S3 y Amazon CloudFront.
- Control de acceso al origen mediante OAC.
- Aplicación del principio de mínimo privilegio.
- Validación de HTTPS y de las restricciones de acceso a S3.
- Supervisión de costos y uso de recursos.
- Documentación de controles de seguridad en un proyecto práctico de ciberseguridad.
