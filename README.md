# AWS Secure Web Portfolio

## 1. Descripción del proyecto

Este proyecto consiste en diseñar e implementar un sitio web estático para presentar un currículum profesional utilizando Amazon Web Services (AWS).

La solución utiliza Amazon S3 para almacenar los archivos del sitio y Amazon CloudFront para distribuir el contenido mediante HTTPS. Se aplicaron medidas de seguridad para mantener privado el almacenamiento y permitir que CloudFront acceda al origen de forma autorizada.

El proyecto demuestra la aplicación práctica de conceptos de seguridad en la nube, control de acceso, protección de datos y gestión de costos.

## 2. Objetivos

- Crear un sitio web estático utilizando HTML y CSS.
- Almacenar los archivos del sitio en Amazon S3.
- Distribuir el contenido mediante Amazon CloudFront.
- Mantener el bucket privado mediante Origin Access Control (OAC).
- Verificar el funcionamiento de HTTPS.
- Comprobar que el acceso directo no autorizado a los objetos de S3 esté denegado.
- Revisar el uso de los servicios y los costos de AWS.
- Documentar la arquitectura y las decisiones de seguridad.

## 3. Arquitectura

**Flujo de acceso:**

Visitante → HTTPS/TLS → Amazon CloudFront → OAC → Bucket privado de Amazon S3.

Amazon CloudFront distribuye el contenido del sitio web y utiliza Origin Access Control (OAC) para autorizar las solicitudes al origen de Amazon S3. El bucket permanece privado, sin necesidad de habilitar el acceso público a sus objetos.

Esta arquitectura separa la distribución del contenido de su almacenamiento y reduce la exposición directa del origen.

## 4. Servicios y tecnologías

- **Amazon S3:** almacenamiento de los archivos HTML, CSS e imágenes del sitio.
- **Amazon CloudFront:** distribución del contenido mediante una red de ubicaciones perimetrales.
- **Origin Access Control (OAC):** mecanismo que permite autorizar el acceso de CloudFront al origen S3.
- **HTTPS/TLS:** protección de la comunicación entre el navegador y CloudFront.
- **HTML y CSS:** estructura y presentación visual del sitio web.
- **GitHub:** documentación y control de versiones del proyecto.

## 5. Medidas de seguridad implementadas

- Bloqueo de acceso público de Amazon S3 habilitado.
- Bucket de S3 mantenido privado.
- Política del bucket configurada para autorizar el acceso requerido desde la distribución de CloudFront.
- Uso de OAC para controlar el acceso al origen.
- Distribución del sitio mediante HTTPS.
- Aplicación del principio de mínimo privilegio en los permisos necesarios.
- Exclusión de credenciales, claves de acceso y otros datos sensibles del repositorio público.

## 6. Validaciones realizadas

Se efectuaron comprobaciones del funcionamiento y de la configuración de seguridad de la solución.

### 6.1. Acceso al sitio mediante CloudFront

Se comprobó que el sitio web fuera accesible mediante la URL de la distribución de Amazon CloudFront y que el contenido se entregara correctamente.

### 6.2. Funcionamiento de HTTPS

Se verificó que el sitio pudiera abrirse mediante HTTPS y que el navegador estableciera una conexión segura con CloudFront.

### 6.3. Denegación del acceso directo a S3

Se comprobó que el acceso directo al objeto de S3 estuviera denegado, obteniéndose una respuesta `403 AccessDenied`. Este resultado es coherente con la restricción del acceso público y el uso de un origen privado.

### 6.4. Configuración de seguridad

Se revisó el bloqueo de acceso público del bucket y la política que permite a CloudFront acceder al contenido autorizado mediante OAC.

### 6.5. Uso y costos de AWS

Se revisó la información de facturación disponible para comprobar el uso de los servicios y detectar posibles cargos. La facturación puede variar según las solicitudes, la transferencia de datos y otros conceptos aplicables.

Por motivos de seguridad y privacidad, este repositorio presenta las comprobaciones mediante documentación técnica, sin publicar capturas de la consola de AWS, identificadores de cuenta ni información sensible de la infraestructura.

## 7. Gestión de costos

Se revisó la información de facturación disponible en AWS para supervisar el consumo de los servicios utilizados durante el proyecto.

Para reducir el riesgo de costos innecesarios, se recomienda:

- Revisar periódicamente AWS Billing y Cost Explorer, cuando esté disponible.
- Considerar los posibles cargos de almacenamiento, solicitudes y transferencia de datos.
- Configurar alertas presupuestarias cuando corresponda.
- Eliminar los recursos que ya no sean necesarios, previa comprobación de sus dependencias.
- Verificar que no queden recursos activos que puedan generar cargos.

La disponibilidad de niveles gratuitos y las condiciones de facturación dependen de los servicios, la región y las condiciones aplicables a la cuenta.

## 8. Privacidad y seguridad del repositorio

El repositorio está orientado a mostrar el diseño, la implementación y las decisiones técnicas del proyecto sin exponer información privada.

No se publican:

- Claves de acceso, contraseñas ni credenciales.
- Archivos con información de facturación.
- Identificadores sensibles de la cuenta o recursos que no sea necesario divulgar.
- Capturas de la consola de AWS.
- Políticas o archivos de configuración que contengan secretos.

La documentación se centra en explicar los controles implementados y los resultados de las validaciones, sin revelar información innecesaria de la infraestructura.

## 9. Conclusiones

El proyecto permitió aplicar conceptos de despliegue web y seguridad en AWS mediante la integración de Amazon S3 y Amazon CloudFront.

El uso de un bucket privado, Origin Access Control y HTTPS contribuye a reducir la exposición del origen y proteger la comunicación con los visitantes. Las validaciones realizadas permiten documentar el funcionamiento esperado de la solución y las medidas de seguridad aplicadas.

Asimismo, la revisión de costos y la protección de la información publicada forman parte de las buenas prácticas necesarias para mantener un proyecto en la nube de manera responsable.

## 10. Aprendizajes obtenidos

- Despliegue de sitios web estáticos en AWS.
- Configuración de Amazon S3 y Amazon CloudFront.
- Control de acceso al origen mediante OAC.
- Aplicación del principio de mínimo privilegio.
- Validación de HTTPS y de las restricciones de acceso.
- Revisión del uso y de los costos de AWS.
- Documentación técnica de un proyecto práctico de ciberseguridad.
