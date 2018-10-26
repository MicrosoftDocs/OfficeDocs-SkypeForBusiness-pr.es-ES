---
title: 'Lync Server 2013: Opciones de implementación de la puerta de enlace RTC'
TOCTitle: Opciones de implementación de la puerta de enlace RTC
ms:assetid: d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398899(v=OCS.15)
ms:contentKeyID: 48276761
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Opciones de implementación de la puerta de enlace RTC en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-21_

## Puertas de enlace RTC

Las puertas de enlace RTC son componentes de hardware de terceros que convierten la señalización y los medios entre la infraestructura de Telefonía IP empresarial y la RTC ya sea de forma directa o con una conexión a troncos SIP. En cualquier topología, la puerta de enlace finaliza la RTC. Se encuentra aislada en su propia subred y se conecta a la red de empresa a través del Servidor de mediación.

Una empresa con varios sitios, normalmente deberá implementar una o más puertas de enlace en cada sitio. Los sitios de sucursal pueden conectarse a la RTC con una puerta de enlace o con una Aplicación de sucursal con funciones de supervivencia, que combina una puerta de enlace y servidores en un mismo componente. Si los sitios de sucursal usan una puerta de enlace, se necesita un registrador y un Servidor de mediación en el sitio, a menos que el vínculo WAN sea resistente. Uno o más Servidores de mediación, instalados en Servidores front-end, pueden enrutar llamadas para una o más puertas de enlace en cada sitio. Recomendamos que el registrador, el Servidor de mediación y la puerta de enlace necesarios en el sitio se implementen como Aplicación de sucursal con funciones de supervivencia.

Determinar el número, el tamaño y la ubicación de las puertas de enlace RTC es, posiblemente, la decisión más importante y costosa que hay que tomar al planear la infraestructura de Telefonía IP empresarial.

A continuación presentamos las principales preguntas que hay que plantearse. Recuerde que las respuestas a estas preguntas están todas interrelacionadas

  - ¿Cuántas puertas de enlace RTC se necesitan? La respuesta depende del número de usuarios, el número previsto de llamadas simultáneas (carga de tráfico) y el número de sitios (cada sitio necesita una).

  - ¿Qué tamaño deben tener las puertas de enlace? La respuesta depende del número de usuarios en el sitio y en la carga de trabajo.

  - ¿Dónde deben colocarse las puertas de enlace? La respuesta depende en parte de la topología y en parte de la distribución geográfica de la organización.

Tenga en cuenta también las opciones de topología de la puerta de enlace (para más información, vea Topologías de puerta de enlace más adelante, en este tema).

## Compatibilidad con troncos M:N

Los Servidores de mediación pueden enrutar las llamadas a través de varias puertas de enlace, de los controladores de borde de sesión (SBC) proporcionados por los proveedores de servicios de telefonía por Internet, o de una combinación de ambos. Además, varios Servidores de mediación del grupo de servidores pueden interactuar con varias puertas de enlace. La ruta lógica definida entre un Servidor de mediación y una puerta de enlace se denomina un *tronco* . Cuando un usuario interno realiza una llamada RTC, la lógica de redirección de salida del Grupo de servidores front-end elige el tronco al que se redireccionarán todas las posibles combinaciones que pueden estar disponibles para redirigir esta llamada en concreto. Con el equilibrio de carga de DNS, si una llamada no llega a una puerta de enlace debido a un problema con un servidor de mediación del grupo de servidores, se reintentará la llamada en un Servidor de mediación alternativo del grupo de servidores.

Para más información sobre la planeación de varias puertas de enlace, vea [Tronco M:N en Lync Server 2013](lync-server-2013-m-n-trunk.md).

Para obtener más información detallada sobre otras mejoras de enrutamiento saliente, vea [Rutas de voz en Lync Server 2013](lync-server-2013-voice-routes.md).

## Topologías de puerta de enlace

Cuando vaya a responder las preguntas fundamentales de la implementación de puertas de enlace, haga lo siguiente:

1.  Cuente los sitios donde desea proporcionar conectividad con RTC mediante Telefonía IP empresarial.

2.  Calcule el tráfico en cada sitio (número de usuarios y promedio de llamadas por hora y por usuario).

3.  Implemente una o varias puertas de enlace en cada sitio para administrar el tráfico previsto.

La topología de puertas de enlace distribuidas resultante se muestra en la figura siguiente.

**Topología de puertas de enlace distribuida**

![Diagrama de topología de puerta de enlace distribuida](images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "Diagrama de topología de puerta de enlace distribuida")

Con esta topología, las llamadas entre los empleados de cada sitio y entre los sitios se redirigen a través de la intranet de la compañía. Las llamadas a la RTC se redirigen a través de la red IP de la empresa a las puertas de enlace que se encuentran más cerca de la ubicación de los números de destino. No obstante, ¿qué sucede si la organización admite docenas, cientos o incluso miles de sitios distribuidos por uno o varios continentes, como es el caso de muchas entidades financieras y otras empresas de gran tamaño? En esos casos, no es práctico implementar una puerta de enlace independiente en cada sitio.

Para solucionar este problema, muchas compañías grandes prefieren implementar uno o varios sitios centrales de telefonía de gran tamaño, tal y como se muestra en la figura siguiente.

**Topología de sitio central de telefonía**

![Topología de puerta de enlace de centro de datos](images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "Topología de puerta de enlace de centro de datos")

En esta topología, en cada sitio central se implementan varias puertas de enlace grandes que puedan hacer frente a la carga de usuarios prevista. El proveedor de servicios de telefonía de la compañía transfiere a un sitio central todas las llamadas para los usuarios de la empresa. La lógica de redirección del sitio central determina si la llamada debe redirigirse a través de la intranet o a la RTC.

## Ubicación de las puertas de enlace

La ubicación de las puertas de enlace también puede determinar los tipos de puertas de enlace elegidos y su configuración. Hay docenas de protocolos RTC, pero ninguno es un estándar mundial. Si todas las puertas de enlace se encuentran en un solo país o región, esto no supone un problema. Ahora bien, si se colocan puertas de enlace en varios países o regiones, cada una de ellas debe configurarse según las normas RTC de cada país o región. Es más, las puertas de enlace certificadas para, por ejemplo, Canadá pueden no estar certificadas en la India, Brasil o la Unión Europea.

## Tamaño y número de las puertas de enlace

Las puertas de enlace RTC que la mayoría de las organizaciones considerarán implementar varía entre 2 y 960 puertos. (Hay puertas de enlace incluso más grandes, pero las usan principalmente los proveedores de servicios de telefonía.) A la hora de valorar el número de puertos que la organización necesita, siga estas directrices:

  - Las organizaciones con necesidades de telefonía reducidas (una llamada de RTC por usuario y por hora) deben asignar un puerto por cada quince usuarios. Por ejemplo, si hay veinte usuarios, se necesitará una puerta de enlace con dos puertos.

  - Las organizaciones con necesidades de telefonía moderadas (dos llamadas de RTC por usuario y por hora) deben asignar un puerto por cada diez usuarios. Por ejemplo, si hay cien usuarios, se necesitará un total de diez puertos asignados a una o varias puertas de enlace.

  - Las organizaciones con grandes necesidades de telefonía (tres o más llamadas de RTC por usuario y por hora) deben asignar un puerto por cada cinco usuarios. Por ejemplo, si hay 47 000 usuarios, se necesitarán 9400 puertos repartidos entre al menos diez puertas de enlace grandes.

  - Se pueden adquirir puertos adicionales a medida que aumenta el número de usuarios o el tráfico de la organización.

Sea cual sea el número de usuarios, existe la opción de implementar menos puertas de enlace grandes o más puertas de enlace pequeñas. Como regla general, se recomienda un mínimo de dos puertas de enlace para mantener la disponibilidad si una de ellas deja de funcionar.

Cada puerta de enlace RTC implementada debe tener por lo menos un Servidor de mediación correspondiente.

