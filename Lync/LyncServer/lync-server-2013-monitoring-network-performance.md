---
title: 'Lync Server 2013: supervisar el rendimiento de red'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring network performance
ms:assetid: bc3a01da-91eb-4c0c-9598-35e5e46b00f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720923(v=OCS.15)
ms:contentKeyID: 63969647
ms.date: 04/27/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2fa3c2685b4da32d5f2e3f123a938920b5ce9f7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826720"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-network-performance-in-lync-server-2013"></a>Supervisar el rendimiento de red en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-04-27_

Lync Server 2013 es una tecnología de comunicaciones en tiempo real que depende principalmente de la red para habilitar la comunicación entre los usuarios, ya sea a través de la mensajería instantánea (mi), las llamadas de voz o la comunicación de vídeo. Por lo tanto, es importante supervisar el rendimiento de la red continuamente para ayudar a garantizar que la modalidad de comunicación elegida por un usuario ofrezca la mejor experiencia posible.

El rendimiento de la red puede medirse a dos niveles:

  - **Rendimiento general de la red**   este nivel de rendimiento permite a una organización crear una vista de "panorama general" de su red y suele implementarse a través de sistemas de supervisión de redes de terceros. Estos sistemas recibirán datos de rendimiento y capacidad de los dispositivos de red remotos, como los enrutadores y se han cambiado por la red, lo que permite a los administradores determinar el estado de cualquier componente de red determinado en cualquier momento del día.

  - **Rendimiento del servidor individual**   este nivel de rendimiento se limita a un servidor específico y ayudará a los administradores a medir el rendimiento de la red de un servidor específico para ayudarle a solucionar un determinado rendimiento. problema o para evaluar el rendimiento del servidor correspondiente a lo largo de un período determinado como parte de un proceso de planeación de capacidad.

Puede supervisar la red con las herramientas que se describen en las siguientes secciones.

<div>

## <a name="tools-for-overall-network-performance-monitoring"></a>Herramientas para la supervisión general del rendimiento de la red

<div>

## <a name="system-center-operations-manager-2012"></a>System Center Operations Manager 2012

System Center Operations Manager proporciona administración de servicios de extremo a extremo que es fácil de personalizar y extender para mejorar los niveles de servicio en un entorno de ti. Esto permite a las operaciones y a los equipos de administración de ti identificar y resolver los problemas que afectan al estado de los servicios de ti distribuidos. La administración de servicios end-to-end no está restringida a entornos basados en Microsoft. La compatibilidad con los servicios web para administración (WS-Management), el Protocolo simple de administración de redes (SNMP) y las soluciones de socio permiten que los sistemas que no ejecutan sistemas operativos y hardware de Microsoft se incluyan en la supervisión de servicios de System Center. Operations Manager 2012.

</div>

<div>

## <a name="system-center-operations-manager-2012-and-third-party-network-management-solutions"></a>System Center Operations Manager 2012 y soluciones de administración de redes de terceros

****   Las soluciones de EMC Smarts de EMC para Operations Manager le ayudan a resolver rápidamente los problemas que afectan a los niveles de servicio. Al usar las soluciones de EMC para Operations Manager, puede administrar y monitorear toda su cadena de servicios de TI con una solución integrada y automática. Podrá identificar fácilmente las causas de origen y los problemas de disponibilidad y resolverlos más rápido, lo que reduce los efectos y los costos. Entre las principales ventajas se incluyen las siguientes:

  - El enfoque de administración avanzada y fácil de usar es ofrecer un valor comercial estratégico en lugar de ordenar y filtrar de forma manual alertas confusas.

  - **Resolución más rápida**   solucione problemas de ti y responda a las necesidades empresariales más rápidamente, reduciendo el efecto y el costo.

  - **Las operaciones**   simplificadas evitan la complejidad de TI al combinar varias herramientas de administración, aplicaciones y terminales.

Puede encontrar más información aquí:

[Microsoft System Center Operations Manager](http://go.microsoft.com/fwlink/p/?linkid=243651)

[Soluciones para Microsoft System Center Operations Manager](http://www.emc.com/collateral/software/data-sheet/h6135-server-manager-ds.pdf)

</div>

<div>

## <a name="third-party-solutions"></a>Soluciones de terceros

**Centro de administración de redes HP (anteriormente conocido como HP OpenView)** El    [centro de administración de redes HP](http://www8.hp.com/us/en/software-solutions/network-management/index.html?%26zn=bto%26cp=1-11-15-119_4000_100__) ofrece administración integrada de errores y rendimiento para mejorar la disponibilidad y el rendimiento de la red. El centro de administración de redes es parte de la solución de administración automatizada de redes HP, que unifica los errores, el rendimiento, la configuración y la administración de los cambios.

**Productos de administración de redes y de automatización de Cisco**   para empresas, Cisco tiene varios productos de administración disponibles, como la solución de administración LAN de CiscoWorks y el módulo de análisis de redes Cisco, para ayudar a mejorar la eficacia operativa y reduce el tiempo de inactividad de la red. Para obtener más información sobre estos productos, visite el sitio web de [http://www.cisco.com/en/US/products/sw/netmgtsw/index.html](http://www.cisco.com/en/us/products/sw/netmgtsw/index.html)Cisco en.

El Protocolo simple de administración de redes (SNMP) es un estándar de administración de redes que define una estrategia de administración de redes TCP/IP. SNMP le permite capturar información de configuración y estado de la red, y enviar la información a un equipo designado para su supervisión de eventos. Este protocolo basado en estándares de administración de redes usa una arquitectura distribuida que incluye lo siguiente:

  - Varios nodos administrados, cada uno con una entidad SNMP denominada agente, que proporciona acceso remoto al instrumental de administración.

  - Al menos una entidad SNMP denominada administrador que ejecuta las aplicaciones de administración para supervisar y controlar los elementos administrados. Los elementos administrados son dispositivos como los hosts, los enrutadores, etc. Se supervisan y controlan accediendo a su información de administración.

  - Se usa un protocolo de administración, SNMP, para comunicar la información de administración entre las estaciones y los agentes de administración. La información de administración hace referencia a una colección de objetos administrados que residen en un almacén de información virtual denominado base de información de administración (MIB).

<div>


> [!NOTE]  
> Anteriormente se proporcionan ejemplos de soluciones de supervisión de red de terceros. Esta lista no es definitiva y Microsoft no favorece la solución de un proveedor específico. Comuníquese con un proveedor de servicios de red o con su proveedor de tecnología respectivo para determinar la mejor solución de supervisión de red para su organización.



</div>

</div>

</div>

<div>

## <a name="tools-for-monitoring-individual-server-network-performance"></a>Herramientas para supervisar el rendimiento de la red del servidor

<div>

## <a name="system-center-operations-manager-2012"></a>System Center Operations Manager 2012

System Center Operations Manager 2012 permite a los administradores ver el rendimiento de la red de servidores individuales a través del módulo de administración de Windows Server 2012: el módulo de administración de sistema operativo Windows Server incluye un módulo de administración de "rendimiento" eso permitiría que los administradores supervisaran el rendimiento del adaptador de red y el estado del adaptador.

</div>

<div>

## <a name="windows-network-monitor"></a>Monitor de red de Windows

Recopila, muestra, analiza el uso de recursos en un servidor y mide el tráfico de red. Monitor de red supervisa la actividad de la red de modo exclusivo. Al capturar y analizar datos de red, y usar estos datos con registros de rendimiento, puede determinar el uso de la red, identificar problemas de red y prever las necesidades futuras de la red.

Para obtener más información sobre el monitor de red 3,4, y para obtener información sobre cómo instalar y configurar el monitor de red y capturar y analizar datos, consulte la descripción de esta sesión: monitor de red 3,3. Además, revise el [blog del monitor de red](http://blogs.technet.com/b/netmon/).

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

