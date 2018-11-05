---
title: 'Lync Server 2013: Componente de servidor de mediación'
TOCTitle: Componente de servidor de mediación
ms:assetid: 5b19edef-4a54-43c9-aa12-5643b8108355
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398399(v=OCS.15)
ms:contentKeyID: 48275377
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Componente de servidor de mediación en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-21_

Debe implementar un Servidor de mediación de Lync Server 2013 si implementa la carga de trabajo de Telefonía IP empresarial. En esta sección se describe la funcionalidad básica, dependencias, topologías básicas y directrices de planeación.

El Servidor de mediación traduce la señalización y, en algunas configuraciones, los medios entre el servidor de Lync Server 2013, la infraestructura de Telefonía IP empresarial y una puerta de enlace de red telefónica conmutada (RTC) o un tronco de Protocolo de inicio de sesión (SIP). En el lado de Lync Server 2013, el Servidor de mediación escucha en una única dirección de transporte de Mutual TLS (MTLS). En el lado de la puerta de enlace, el servidor de mediación escucha en todos los puertos de escucha asociados con los troncos definidos en el documento de topología. Todas las puertas de enlace cualificadas deben admitir TLS, pero pueden estar habilitadas también para TCP. El protocolo TCP es compatible con puertas de enlace que no admiten TLS.

Si su entorno también dispone de una central pública de conmutación (PBX), el Servidor de mediación administra las llamadas entre usuarios de Telefonía IP empresarial y la PBX. Si dicha PBX es una IP-PBX, puede crear una conexión SIP directa entre ella y el Servidor de mediación; si es una PBX de multiplexación por división de tiempo (TDM), deberá implementar también una puerta de enlace RTC entre el Servidor de mediación y la PBX.

El Servidor de mediación se combina con el Servidor front-end de manera predeterminada. El Servidor de mediación también se puede implementar en un grupo de servidores independiente por motivos de rendimiento o si implementa enlaces troncales SIP, en cuyo caso se recomienda encarecidamente el grupo de servidores independiente.

Si implementa conexiones SIP directas hacia una puerta de enlace RTC cualificada compatible con el desvío de medios y el equilibrio de carga DNS, no será necesario un Grupo de servidores de mediación independiente, ya que las puertas de enlace cualificadas pueden realizar el equilibrio de carga DNS en un grupo de servidores de mediación y pueden recibir tráfico de cualquier Servidor de mediación de un grupo.

Se recomienda también combinar el Servidor de mediación en un Grupo de servidores front-end si se ha implementado sistemas IP-PBX o si se conecta a un controlador de borde de sesión (SBC) del proveedor de servicios de telefonía por Internet, siempre y cuando se cumpla alguna de las condiciones siguientes:

  - El IP-PBX o SBC se configura para recibir tráfico desde cualquier Servidor de mediación del grupo de servidores y puede enrutar el tráfico uniformemente a todos los Servidores de mediación del grupo.

  - El IP-PBX no admite el desvío de medios, pero el Grupo de servidores front-end en que se hospeda el Servidor de mediación puede gestionar la transcodificación de voz para llamadas en las que no se aplique el desvío de medios.

Puede utilizar Microsoft Lync Server 2013, herramienta de planeación para evaluar si el Grupo de servidores front-end en el que ha combinado el Servidor de mediación puede gestionar la carga. Si el entorno no cumple estos requisitos, deberá implementar un Grupo de servidores de mediación independiente.

Las funciones principales del Servidor de mediación son las siguientes:

  - Cifrar y descifrar SRTP en el lado de Lync Server

  - Convertir SIP sobre TCP (para puertas de enlace que no admiten TLS) en SIP sobre Mutual TLS

  - Convertir secuencias de medios entre Lync Server y la puerta de enlace del mismo nivel del Servidor de mediación

  - Conectar clientes que están fuera de la red con componentes ICE internos, que habilitan el paso de los medios a través de NAT y firewalls

  - Actuar como intermediario de los flujos de llamada que una puerta de enlace no admite, como las llamadas de trabajadores remotos en un cliente de Telefonía IP empresarial

  - En implementaciones que incluyen enlaces troncales SIP, trabajar con el proveedor de servicios de enlaces troncales SIP para proporcionar compatibilidad con la RTC, con lo que se elimina la necesidad de una puerta de enlace de RTC

En la siguiente figura se muestran los protocolos de señalización y medios que el Servidor de mediación usa al comunicarse con una puerta de enlace RTC básica y la infraestructura de Telefonía IP empresarial.

**Señalización y protocolos multimedia que usa el servidor de mediación**

![Diagrama de protocolos de servidor de mediación](images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "Diagrama de protocolos de servidor de mediación")


> [!NOTE]
> Si usa TCP o RTP/RTCP (en lugar de SRTP o SRTCP) en la red entre la puerta de enlace RTC y el Servidor de mediación, recomendamos que adopte las medidas necesarias para garantizar la seguridad y privacidad de la red.



## En esta sección

  - [Tronco M:N en Lync Server 2013](lync-server-2013-m-n-trunk.md)

  - [Control de admisión de llamadas y servidor de mediación en Lync Server 2013](lync-server-2013-call-admission-control-and-mediation-server.md)

  - [9-1-1 mejorado (E9-1-1) y servidor de mediación en Lync Server 2013](lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md)

  - [Omisión de medios y servidor de mediación en Lync Server 2013](lync-server-2013-media-bypass-and-mediation-server.md)

  - [Componentes y topologías para el servidor de mediación en Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md)

  - [Directrices de implementación para el servidor de mediación en Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md)

