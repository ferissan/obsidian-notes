## PCIDSS - Análisis GAP: Alcance

- El objetivo de la certificación PCI DSS es el core de pagos de Jelou
- Se explican dos procesos de pago:
	- Pago desde enlace generado
	- Pago desde WhatsApp Flows
- PCI aplicable solo sí flujo del que se es responsable incluye envío, manipulación o almacenamiento de datos de tarjetas de pago.

❗️PCI aplicable solo si manipulamos datos de tarjetas es decir transitan, se almacenan o eliminan

## Identificación de Infraestructura tecnológica

- Se presenta diagrama de arquitectura de Jelou

❗️PCI Diagrama de arquitectura detallado de [payments.jelou.ai](https://payments.jelou.ai)
> Se debe incluir servicio Payments y Lambda para procesamiento de tarjetas Meta

❗️PCI Docs guía de configuración WAF aplicables al servicio considerando las mejores prácticas del fabricante.
> WAF en modo logging enviando alertas 

❗️PCI Flujo de la solución

❗️PCI Sistema de Detección de Intrusos IDS/IPS
> Guard Duty cubre parcialmente esto hay que agregar controles adicionales en AWS Networking Firewalls
> Detectar vulnerabilidades OWASP Top 10

❗️PCI Bastión host aplicar control perimetral a ambiente PCI
> Requiere factor de autenticación múltiple una opción es instalar una VPN y activar MFA

❗️PCI Manejar ambientes de desarrollo, pre-producción y producción independientes
## PCIDSS - Análisis GAP: Procesos de seguridad de la información

> En esta reunión participó @compliance

---
## PCIDSS - Análisis GAP:  Transmisión, cifrado y almacenamiento de datos sensibles

❗️PCI Docs inventario de certificados
> Esto aplica si manejamos diferentes custodios, en caso que sea uno (por ej. AWS) no se requiere el inventario y se puede mostrar directamente en ACM

❗️PCI Docs Proceso de gestión de la llave
> Protocolo para compartir llave pública con WhatsApp
> Custodio de la llave privada en Jelou (Solo el Lambda debe poder acceder al secreto)
> Es el proceso más crítico se debe usar AWS KMS

❗️PCI Investigar el compromiso de Meta en la captura de datos desde WhatsApp Flows

## PCIDSS - Análisis GAP: Desarrollo de Software en el ambiente de datos de tarjeta (CDE)

- Proceso de despliegue a producción

❗️PCI Recomendación importante aislare el ambiente PCI en una cuenta dedicada de AWS
> Esto implica que payments.jelou.ai y Lambda WhatsApp Flow deben estar en la misma cuenta de AWS para poder aplicar controles perimetrales a los componentes de red.

❗️PCI Docs y aplicar procedimiento de buenas práticas desarrollo seguro
> Esto implica ciclo de desarrollo seguro
> Control de versiones con GitHub
> Revisión de código tomando en cuenta parámetros de seguridad
> Aprobación explicita de pull requests
> No dejar pasar vulnerabilidades de impacto alto
> Dejar comentarios en GitHub en caso que se salte algún control con autorización y consecuente tarea de seguimiento para remediación o pull request

❗️PCI Robustecer checklist de revisión de código
> Fomentar el uso de la checklist
> Checklist enfocada para Líder Técnico
> Checklist para desarrolladores pares
> Se requiere mayor descripción a nivel de código, alertas de código inseguro basadas en umbral XX.
> Todo debe estar documentado en relación a solicitud de cambios en desarrollo

❗️PCI Análisis de código SonarQ Cloud en core de pagos

❗️PCI Formación del equipo
> Se debe capacitar al equipo que gestiona el core de pagos al menos 1 vez al año, esta capacitación puede ser interna o externa.
> 
> **Capacitación externa**
> Capacitación anual para entrenamiento en temas de desarrollo seguro
> Formación desarrollo seguro Udemy, LinkedIn similares que emitan certificado
> La evidencia es el certificado de la capacitación
> Se debe considerar en la capacitación todos los roles que participan de este proceso es decir desarrollador, revisor desarrollador par y revisor líder técnico
>   
> **Capacitación interna**
> Se debe presentar como evidencia la presentación, prueba de conocimiento, control de asistencia y temas en discusión
> Los temas a tratar deben incluir como base: SonarCloud y OWASP Top 10

## PCIDSS - Análisis GAP:  Revisión de los procesos de gestión de vulnerabilidades

> En esta reunión participó @compliance

## PCIDSS - Análisis GAP: Gestión del software y la página de pagos

> En esta reunión participó @producto

## PCIDSS - Análisis GAP: Roles y responsabilidades

> En esta reunión participó @compliance

## PCIDSS - Análisis GAP: Responsabilidades como proveedor de servicio

> En esta reunión participó @compliance

## PCIDSS - Análisis GAP: Gestión de usuarios y MFA

- Proceso de ingreso del personal
- Proceso de salida del personal

❗️PCI Ambiente PCI requiere acceso con MFA
> La cuenta de AWS debe tener activado el factor de autenticación múltiple

❗️PCI Roles a nivel de base de datos

❗️PCI Rotación de clave de usuarios de servicios
> Se recomienda realizar cada año porque se trata de servicios

❗️PCI Matriz de roles de acuerdo a formato RACI PCI DSS

❗️PCI Inactivar usuarios luego de 6 meses de inactividad

❗️PCI Cláusula en contrato que especifique que protegemos datos procesamiento de pago
> Aunque no se almacene el dato de tarjetas, se debe agregar cláusula donde se indique que tanto nosotros como proveedor, como proveedores que se utilizan para el procesamiento de pago, todos son empresas certificadas PCI DSS esto con la finalidad de proteger el procesamiento del pago
> Agregar cláusula de protección de datos de tarjeta

❗️PCI Matriz de responsabilidad compartida
> En contrato de manera general se debe especificar cláusulas PCI donde se indique responsabilidad como tratantes de tarjetas y como clientes.
> En esta matriz se aterriza en un más bajo nivel en cuanto a responsabilidades

❗️PCI Política de cambios de clave (12 caracters)
> Accesos a AWS de 12 caracteres, esto se debe fomentar a nivel de toda la compañia
> Accesos de AWS deben requerir MFA, esto incluye los accesos a través Bastion Host para conexiones de DB y otros usando como recomendación VPN.

---

## PCIDSS - Análisis GAP: Gestión de cambios

- Revisión documental de cambios a nivel de infraestructura
- Revisión documental de cambios a nivel de desarrollo

❗️PCI Nivel de riesgo o impacto del cambio ventana de mantenimiento
> Se debe documentar todo el proceso y mantener un registro

❗️PCI Niveles de aprobación

❗️PCI Cambios significativos
> Análisis de vulnerabilidades
> Actualizar inventario y diagramas
> 	Diagrama de red
> 	Diagrama de flujo
> 	Documentos actualizados después del cambio
> Se puede usar un sistema donde se evidencie los cambios realizados

❗️PCI Docs Política donde se detalle puertos/fuente/destino SG

❗️PCI Proceso recurrente que borre las tarjetas expiradas de la base de datos
> Entiendo que este borrado debería ser físico porque las tarjetas almacenadas están caducadas

❗️PCI Algoritmo AES256 CBE es aceptable para tokens personales en payments

## PCIDSS - Análisis GAP: Monitoreo y SIEM

- En esta reunión participó @devops

❗️PCI Almacenar eventos de seguridad durante 1 año
> Enfoque asociado a seguridad de los recursos
> Monitorear todos los eventos de seguridad que hacen parte del entorno
> Enviar a otro almacenamiento distinto (por ej. S3), esto por que a veces logs de desarrollo se almacenan por un periodo corto en CloudWatch, sin embargo para persistirlos el tiempo que demanda PCI podríamos llevarlos a un S3

## PCIDSS - Análisis GAP: Revisión de controles de seguridad perimetral (SG), WAF y del IPS/IDS

- Acceso a Bastion a través de SSH y llave privada
- Laravel Vapor usamos las configuraciones de SG por defecto y no tenemos mucho control sobre esto de lado de AWS porque afecta toda la cuenta
- Sistema de notificaciones y alertas CloudWatch, SNK

❗️PCI Almacenar eventos de seguridad durante 1 año
> Se recomienda Guard Duty como IDS/IPS pero agregando reglas adicionales en AWS Networking Firewall

❗️PCI Acceso a Bastion Host
> Recomendaciones sobre EC2 control de antivirus, fire monitor + VPN (MFA)
> La VPN no sería necesario si encuentro otra manera de implementar el control de MFA para acceder
> AWS Connect instance es un servicio que nos puede ayudar a remover el Bastion Host

❗️PCI Docs Política donde se detalle puertos/fuente/destino SG
> Esto porque la configuración de Security Groups ahora mismo están bastante abiertos
> Security Groups aplicados solo a cuenta AWS donde reside el core de pagos
> Configurar los SG podría limitar el acceso de recursos a Vapor
> Limitar la superficie de ataque

❗️PCI Docs recomendaciones de AWS sobre WAF
> Documento donde se especifique cuales de las recomendaciones del fabricante aplicamos a nuestro servicio y cuales por limitantes que afectan la operatividad del servicio no hemos podido implementar.

## PCIDSS - Análisis GAP: Revisión de instancias ECS, servicios del entorno AWS y bases de datos.

- En esta reunión participó @devops

## PCIDSS - Análisis GAP: Revisión del antivirus y FIM

- En esta reunión participó @devops

---

## Conclusiones IsecAuditors

Algunos de los controles que requiere PCI DSS ya tenemos implementados por ISO27001 sin embargo se requiere mantener los documentos actualizados y alinearlos a PCI

El objetivo del PCI es el core de pagos, porque es aplicable solamente si hay datos de tarjeta, es decir transitan, manipulan o eliminan.

La certificación nos entrega documentos (AOC es uno de ellos) donde nosotros debemos detallar el **nombre de servicio certificado PCI** (por ej. Jelou Apps + Payments), también se debe indicar una **descripción del alcance PCI** (por ej. Pagos con enlaces generados y Pago con WhatsApp Flows), en estos detalles debemos hablar con área de marketing y producto para estratégicamente cubrir todas las aristas que como negocio necesitamos. Nosotros tenemos control total de este apartado, los auditores se encargan de revisar y aprobar en base a la evaluación que se cumplan y estén alineados al alcance detallado en el PCI DSS que debemos llenar antes de solicitar la certificación y auditoría (esto se explica más adelante).

Aquí también nos recomienda agregar en la descripción:
> En caso que usuarios por omisión o por ignorancia nos envían datos de tarjetas (En imagen o texto) por medio del chat (el cuál no requerimos y no hemos solicitado porque no es una necesidad de negocio) aseguramos el cumplimiento de medidas y controles necesarios para que el dato sea eliminado y nunca sea almacenado. Siendo que se notifica al cliente (por ej. Banco Guayaquil, Netlife, etc) que esta información fue recibida pero eliminada con la medida de protección de datos explicada anteriormente.
> 
> Se debe demostrar que tanto para imágenes y texto no se almacenan datos de tarjeta porque durante la evaluación se revisara el cumplimiento de estas medidas y controles en cuestión para garantizar la protección de datos de tarjetas.
> 
> ❗️EL IMPACTO COMERCIAL ES IMPORTANTE
> Los canales por los cuales Jelou actualmente maneja datos personales y de tarjetas no necesarios para soporte y procesos comerciales pasan por un proceso automatizado de eliminado de información asegurando la protección de estos datos.


![[Pasted image 20250219113550.png]]

La recomendación de ISecAuditors
- Segmentar el core de pagos de Jelou
- Tener en una cuenta de AWS Jelou Payments para poder aplicar los controles de seguridad perimetral.
	- Esta cuenta de AWS sería mi ambiente PCI que incluye [payments.jelou.ai](https://payments.jelou.ai) y Lambda
	- Pasar a privado sus componentes
	- Hardening usando Security Groups

> Ambiente PCI es todo donde transita, almacena, manipulan datos de tarjetas en nuestro caso es solamente core de pagos, cualquier comunicación por HTTPS esta fuera del alcance PCI, pero para seguridad perimetral si algún componente requiere comunicarse con payments se debe tener documentado los puertos/fuentes/destinos que se comunicarán con el mismo
> 
> A pesar que esto último no aplica porque deberíamos buscar tener aislado el core de pagos en una cuenta de AWS, Laravel Vapor dedicada para pagos y es mejor dejarlo así para poder mantener la certificación, luego puedo propagar estas prácticas a los otros microservicios que existen en Laravel Vapor

A nivel de documentación es importante listar las redes, segmentos, Security Groups que son PCI y que se conectan a PCI.
> Conexiones HTTPS no se consideran dentro del ambiente PCI, son externas

Siempre nos van a exigir que todos los proveedores con los que trabajemos en ambiente PCI cuenten con certificación PCI DSS, como nuestro vendor es AWS no tenemos mayor problema porque cuenta con esta certificación. Importante tener listado los proveedores con los que trabajamos esto se verá reflejado en los documentos del alcance PCI DSS (por ej. AWS, Stripe, Datafast, etc)
![[Pasted image 20250219123944.png]]

**Próximos pasos**
- Reporte y recomendaciones de ISecAuditors 7 de marzo <u>En espera</u>
- Documento de alcance PCI <u>En espera</u>