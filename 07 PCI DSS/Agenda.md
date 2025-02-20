
## PCIDSS - Análisis GAP: Alcance

Validación de Alcance PCI DSS Alcance 12.5.2 Definir el canal, proceso, flujo; del que se es responsable e incluye envío, manipulación o almacenamiento de datos de tarjeta de pago. - Necesario tener reuniones de esta estimación con cada responsable del departamento de una compañía en concreto, si ese departamento manipula datos de tarjeta de crédito. Se recomienda que este tipo de reuniones se mantengan en compañía de personal con conocimientos técnicos para ir identificando componentes, estructura de Red, etc Cantidad de transacciones con tarjetas procesadas en último año. Revisión del alcance documentado de PCI DSS

## Identificación de Infraestructura tecnológica

Identificación de Infraestructura tecnológica, de red y seguridad 1.2.4, 12.5.1 Identificar la infraestructura en la que se sustentan todos los flujos de información definidos. Servidores, workstations, hypervisores, clientes, laptops, impresoras, etc., cabinas de almacenamiento, infraestructuras de backup, etc.. Identificar la infraestructura de red en la que se sustentan todos los flujos de información definidos. Firewalls, Routers, switches, balanceadores, proxy, redes inalámbricas, etc. El objetivo sería identificar todos los componentes para registrar la información en el informe. Para la reunión, se debe disponer de un diagrama de red, diagramas de flujo de datos de tarjeta, y que el responsable sepa identificar los componentes, e información adicional; como versiones de SO, o direccionamiento (producción, gestión)

## PCIDSS - Análisis GAP: Procesos de seguridad de la información

---

## PCIDSS - Análisis GAP:  Transmisión, cifrado y almacenamiento de datos sensibles

Transmisión, cifrado y almacenamiento de datos sensibles 3, 4, 12.3.3 Revisión de la matriz de datos sensibles Revisión de los mecanismos de cifrado de datos sensibles en almacenamiento Revisión de los mecanismos de cifrado de datos sensibles en transporte Revisión de los certificados Revisión del mecanismo de envío de información por mecanismos de mensajería de usuario final. Revisión de la arquitectura de cifrado Revisión del inventario criptografico Gestión de llaves de cifrado

## PCIDSS - Análisis GAP: Desarrollo de Software en el ambiente de datos de tarjeta (CDE)

Desarrollo de Software en el ambiente de datos de tarjeta (CDE) 6.1, 6.2, 6.4, 6.5 Si en el entorno en concreto no hay desarrollos internos, no aplica. Si los desarrolla un proveedor, habrá que revisar el AoC, o bien los requisitos con dicho proveedor. Revisión de evidencias de formación anual al equipo de desarrollo. Revisión de la separación de los entornos de desarrollo y producción.

## PCIDSS - Análisis GAP:  Revisión de los procesos de gestión de vulnerabilidades

Revisión de los procesos de gestión de vulnerabilidades  
6.1, 6.3, 11  
Revisión del proceso para identificación de nuevas vulnerabilidades  
Revisión del proceso de categorización de vulnerabilidades  
Revisión del proceso de aplicación de parches de seguridad  
Revisión del listado de redes inalámbricas autorizadas.  
Revisión del proceso de búsqueda de redes inalámbricas no autorizadas y los respectivos reportes  
Revisión de las metodologías de pruebas de vulnerabilidades y penetración.  
Revisión de los reportes de pruebas de penetración, vulnerabilidades, segmentación y ASV

## PCIDSS - Análisis GAP: Gestión del software y la página de pagos

Gestión del software y la página de pagos 6.3.2, 6.4.3, 11.6, 12.3.4 Revisión del inventario de software a medida y personalizado y de los componentes del software de terceros incorporados en el entorno (incluye librerias). Revisión de inventario de scripts de cargan en la página de pagos. Revisión de la implementación para asegurar la integridad de cada script en la página de pago. Revisión de los mecanismos de detección de cambios y manipulaciones de la página de pagos (encabezados HTTP y el contenido de la página). Evidencia de la revisión anual que las tecnologías de hardware y software continuaran siendo soportadas.

## PCIDSS - Análisis GAP: Roles y responsabilidades

Roles y responsabilidades 7, *.1.2 Matriz de roles y responsabilidades Privilegios de administradores de plataforma Privilegios de administradores de bases de datos Aprobación de los privilegios asignados Revisión periódica de roles y usuarios.

## PCIDSS - Análisis GAP: Responsabilidades como proveedor de servicio

## PCIDSS - Análisis GAP: Gestión de usuarios y MFA

Gestión de usuarios y MFA 8 8.4, 8.5 Revisión del proceso general. Revisión de registros de altas. Revisión de registros de bajas. Revisión de registros de la revisión periódica de usuarios. Revisión del proceso de cambio de contraseñas. Listado de los usuarios que ingresaron y dejaron la organización en los últimos 6 meses. Inventario de las cuentas de aplicación o servicios. Revisión de que las cuentas aplicación/sistema no sean utilizadas para el inicio de sesión interactivo, ni estén codificadas en scripts o archivos de configuración Revisión de que el acceso administrativo al CDE no puede obtenerse mediante el uso de único factor de autenticación. Revisión que se solicita MFA a todos los accesos al CDE que se originan fuera de la red de la entidad. Revisión que los sistemas MFA no pueden ser omitidos por ningún usuario, incluyendo los usuarios administrativos.

---

## PCIDSS - Análisis GAP: Gestión de cambios

Gestión de cambios 6.5 Revisión del proceso de gestión de cambios. Revisión de registros de cambios significativos. Revisión de registros de cambios de red. Revisión de registros de cambios de aplicaciones. Revisión de registros de cambios de sistemas operativos y/o firmware. Listado de cambios significativos implementados en el ambiente de datos de tarjeta en los últimos 12 meses.

## PCIDSS - Análisis GAP: Monitoreo y SIEM

Monitoreo y SIEM 10 Revisión del proceso de monitoreo de eventos de seguridad Revisión de las plataformas reportando al sistema de monitoreo de eventos Revisión del sistema de monitoreo de disponibilidad de dispositivos críticos de seguridad (proveedores de servicio) Revisión de una muestra de eventos analizados.

## PCIDSS - Análisis GAP: Revisión de controles de seguridad perimetral (SG), WAF y del IPS/IDS

Revisión de controles de seguridad perimetral (SG), WAF y Revisión del IPS/IDS 1, 2, 4, 8, 10 Revisión de actualizaciones Revisión de zonas (MZ, DMZ, Internet, etc.) Revisión de configuración contra la guía Revisión de usuarios Revisión de configuración de hora (NTP) Revisión de envío de logs Revisión de funcionamiento activo. Revisión de políticas de bloqueo y/o alertamiento.

## PCIDSS - Análisis GAP: Revisión de instancias ECS, servicios del entorno AWS y bases de datos.

Revisión de instancias ECS, servicios del entorno AWS y bases de datos. 2, 8, 10 Revisión de actualizaciones Revisión de configuración contra la guía Revisión de usuarios Revisión de configuración de hora (NTP) Revisión de envío de logs Revisión de antivirus Revisión de FIM

## PCIDSS - Análisis GAP: Revisión del antivirus y FIM

Revisión del antivirus y FIM 5, 10 Revisión de dispositivos asociados Revisión de actualizaciones Revisión de políticas Revisión de configuración contra la guía Revisión de usuarios Revisión de alertas y reportes Revisión de almacenamiento de 1 año (3 meses en línea)