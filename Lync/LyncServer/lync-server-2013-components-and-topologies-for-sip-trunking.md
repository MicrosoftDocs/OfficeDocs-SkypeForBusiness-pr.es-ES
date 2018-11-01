---
title: 'Lync Server 2013: Componentes y topologías para el enlace troncal SIP'
TOCTitle: Componentes y topologías para el enlace troncal SIP
ms:assetid: 8ed9a9d0-517e-4f36-a131-22cdafa257fa
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398720(v=OCS.15)
ms:contentKeyID: 48275993
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Componentes y topologías para el enlace troncal SIP en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-21_

La ilustración siguiente refleja la topología de enlace troncal SIP de Lync Server.

**Topología del enlace troncal SIP**

![Topología de enlace troncal SIP](images/Gg398720.669fb55d-7c81-4e21-9421-fabc43d6e064(OCS.15).jpg "Topología de enlace troncal SIP")

Como se muestra en el diagrama, se usa una red privada virtual (VPN) de IP para la conectividad entre la red empresarial y el proveedor de servicios de la red telefónica conmutada (RTC). El objetivo de esta red privada es proporcionar conectividad IP, mejorar la seguridad y obtener garantías (opcionales) de Calidad de servicio (QoS). Dada la naturaleza de una VPN, no necesita usar Seguridad de la capa de transporte (TLS) para el tráfico de señalización SIP ni el Protocolo de transporte en tiempo real seguro (SRTP) para el tráfico de medios. Las conexiones entre la empresa y el proveedor de servicios constan, por lo tanto, de conexiones TCP simples para SIP y el Protocolo de transporte en tiempo real (RTP) simple (sobre UDP) para los medios de túnel a través de una VPN de IP. Asegúrese de que todos los firewalls que hay entre los enrutadores de VPN tienen los puertos abiertos para permitir la comunicación de dichos enrutadores, y que las direcciones IP de los bordes externos de los enrutadores de VPN se pueden redirigir públicamente.

> [!IMPORTANT]  
> Consulte a su proveedor de servicios para saber si admite alta disponibilidad, incluida la conmutación por error. Si es así, tendrá que averiguar los procedimientos para instalarla. Por ejemplo, ¿es necesario configurar una sola dirección IP y un tronco SIP en cada Servidor de mediación, o tiene que configurar varios troncos SIP en cada Servidor de mediación?<br />
> Si tiene varios sitios centrales, pregunte también si el proveedor de servicios tiene la capacidad de habilitar conexiones a otro sitio central y desde él.



> [!NOTE]
> Para el enlace troncal SIP, se recomienda encarecidamente implementar Servidores de mediación independientes. Para ver más detalles, consulte <A href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Implementar servidores de mediación y definir servidores del mismo nivel en Lync Server 2013</A> en la documentación sobre implementación.



## Protección del servidor de mediación para el enlace troncal SIP

Por motivos de seguridad, debe instalar una LAN virtual (VLAN) por cada conexión que haya entre ambos enrutadores de VPN. El proceso concreto para instalar una VLAN varía según el fabricante del enrutador. Para obtener información detallada, contacte con el proveedor de su enrutador.

Se recomienda seguir estas instrucciones:

  - Instale una LAN virtual (VLAN) entre el Servidor de mediación y el enrutador de VPN en la red perimetral (también llamada DMZ, zona desmilitarizada o subred filtrada).

  - No permita la difusión ni la transferencia de paquetes multidifusión desde el enrutador a la VLAN.

  - Bloquee todas las reglas de enrutamiento que enruten el tráfico del enrutador a cualquier lugar que no sea el Servidor de mediación.

Si usa un servidor de VPN, se recomienda seguir estas instrucciones:

  - Instale una VLAN entre el servidor de VPN y el Servidor de mediación.

  - No permita la difusión ni la transmisión de paquetes multidifusión desde el servidor de VPN a la VLAN.

  - Bloquee todas las reglas de enrutamiento que enruten el tráfico del servidor de VPN a cualquier lugar que no sea el Servidor de mediación.

  - Cifre los datos de la VPN mediante encapsulación de enrutamiento genérico (GRE).

