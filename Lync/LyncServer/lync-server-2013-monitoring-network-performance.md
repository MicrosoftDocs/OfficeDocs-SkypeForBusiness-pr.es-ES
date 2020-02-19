---
title: 'Lync Server 2013: supervisión del rendimiento de la red'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring network performance
ms:assetid: bc3a01da-91eb-4c0c-9598-35e5e46b00f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720923(v=OCS.15)
ms:contentKeyID: 63969647
ms.date: 04/27/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aafea72c7e30644f8a882f1cf556c665e1e285ad
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140183"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-network-performance-in-lync-server-2013"></a>Supervisión del rendimiento de la red en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-04-27_

Lync Server 2013 es una tecnología de comunicaciones en tiempo real que depende en gran medida de la red para habilitar la comunicación entre los usuarios, ya sea a través de la mensajería instantánea (mi), las llamadas de voz o la comunicación de vídeo. Por lo tanto, es importante supervisar el rendimiento de la red de forma continua para ayudar a garantizar que la modalidad de comunicación elegida por un usuario ofrezca la mejor experiencia posible.

El rendimiento de la red se puede medir en dos niveles:

  - **Rendimiento general de la red**   este nivel de medida de rendimiento permite que una organización cree una vista de "gran tamaño" de la red y se implementa normalmente a través de sistemas de supervisión de red de terceros. Estos sistemas recibirán datos de rendimiento y capacidad de los dispositivos de red remotos, como enrutadores y cambiados a través de la red, para permitir que los administradores determinen el estado de cualquier componente de red determinado en cualquier momento del día.

  - **Rendimiento del servidor individual**   este nivel de medida de rendimiento se limita a un servidor específico y ayudará a los administradores a evaluar el rendimiento de la red de un servidor específico para ayudarle a solucionar un problema de rendimiento específico o para evaluar el rendimiento del servidor respectivo en un período determinado como parte del proceso de planeación de la capacidad.

Puede supervisar la red con las herramientas que se describen en las secciones siguientes.

<div>

## <a name="tools-for-overall-network-performance-monitoring"></a>Herramientas para la supervisión general del rendimiento de la red

<div>

## <a name="system-center-operations-manager-2012"></a>System Center Operations Manager 2012

System Center Operations Manager proporciona administración de servicios de un extremo a otro que es fácil de personalizar y ampliar para los niveles de servicio mejorados en un entorno de ti. Esto permite a las operaciones y a los equipos de administración de ti identificar y resolver los problemas que afectan al estado de los servicios de ti distribuidos. La administración de servicios de un extremo a otro no se limita a los entornos basados en Microsoft. La compatibilidad con los servicios web para la administración (WS-Management), el Protocolo simple de administración de redes (SNMP) y las soluciones de asociados permiten que los sistemas que no ejecutan sistemas operativos de Microsoft y hardware se incluyan en la supervisión de servicios de System Center. Operations Manager 2012.

</div>

<div>

## <a name="system-center-operations-manager-2012-and-third-party-network-management-solutions"></a>System Center Operations Manager 2012 y soluciones de administración de redes de terceros

****   Las soluciones de EMC Smarts de EMC para Operations Manager lo ayudan a resolver rápidamente los problemas que afectan a los niveles de servicio en todo el. Mediante el uso de soluciones de EMC para Operations Manager, puede administrar y monitorear toda su cadena de servicios de TI con una solución integrada y automatizada. Puede identificar fácilmente las causas de origen de los problemas de rendimiento y disponibilidad y resolverlos con mayor rapidez, lo que reduce los efectos y los costos. Entre las principales ventajas se incluyen las siguientes:

  - La administración avanzada y fácil de usar se centra en proporcionar valor empresarial estratégico en lugar de ordenar y filtrar de forma manual las alertas confusas.

  - **Resolución más rápida**   resuelve los problemas de ti y responde a las necesidades del negocio más rápido, lo que reduce el efecto y el costo.

  - **Las operaciones**   simplificadas evitan la complejidad de TI mediante la combinación de varias herramientas de administración, aplicaciones y terminales.

Puede encontrar más información aquí:

[Microsoft System Center Operations Manager](https://go.microsoft.com/fwlink/p/?linkid=243651)

[Soluciones para Microsoft System Center Operations Manager](http://www.emc.com/collateral/software/data-sheet/h6135-server-manager-ds.pdf)

</div>

<div>

## <a name="third-party-solutions"></a>Soluciones de otros fabricantes

**HP Network Management Center (anteriormente conocido como HP OpenView)**   [HP Network Management Center](http://www8.hp.com/us/en/software-solutions/network-management/index.html?%26zn=bto%26cp=1-11-15-119_4000_100__) ofrece una administración integrada de errores y rendimiento para mejorar la disponibilidad y el rendimiento de la red. El centro de administración de redes forma parte de la solución de administración automatizada de redes de HP que unifica los errores, el rendimiento, la configuración y la administración de cambios.

**Cisco Network Management and Automation Products**   for The Enterprise, Cisco tiene varios productos de administración disponibles, incluidos la solución de administración de LAN de CiscoWorks y el módulo de análisis de red de Cisco, para mejorar la eficiencia operativa y reducir el tiempo de inactividad de la red. Para obtener información adicional sobre estos productos, consulte el sitio web de [https://www.cisco.com/en/US/products/sw/netmgtsw/index.html](https://www.cisco.com/en/us/products/sw/netmgtsw/index.html)Cisco en.

Protocolo simple de administración de redes (SNMP) Protocolo simple de administración de redes (SNMP) es un estándar de administración de redes que define una estrategia para administrar redes TCP/IP. SNMP permite capturar información de configuración y estado sobre la red y enviar la información a un equipo designado para la supervisión de eventos. Este protocolo de administración de red basado en estándares usa una arquitectura distribuida que incluye lo siguiente:

  - Varios nodos administrados, cada uno con una entidad SNMP llamada un agente que proporciona acceso remoto a instrumental de administración.

  - Al menos una entidad SNMP conocida como administrador que ejecuta las aplicaciones de administración para supervisar y controlar los elementos administrados. Los elementos administrados son dispositivos como hosts, enrutadores, etc. Se supervisan y controlan mediante el acceso a su información de administración.

  - Se usa un protocolo de administración, SNMP, para comunicar la información de administración entre las estaciones de administración y los agentes. La información de administración se refiere a una colección de objetos administrados que residen en un almacén de información virtual denominado base de datos de información de administración (MIB).

<div>


> [!NOTE]  
> A continuación se ofrecen ejemplos de soluciones de supervisión de red de terceros. Esta lista no es definitiva y Microsoft no favorece a ninguna solución de proveedor específica. Consulte a un proveedor de servicios de red o a su proveedor de tecnología respectivo para determinar la mejor solución de supervisión de red para su organización.



</div>

</div>

</div>

<div>

## <a name="tools-for-monitoring-individual-server-network-performance"></a>Herramientas para supervisar el rendimiento de una red de servidor individual

<div>

## <a name="system-center-operations-manager-2012"></a>System Center Operations Manager 2012

System Center Operations Manager 2012 permitiría a los administradores ver el rendimiento de red de servidores individuales a través del módulo de administración de Windows Server 2012: el módulo de administración del sistema operativo Windows Server incluye un módulo de administración de "rendimiento" Esto permitiría a los administradores supervisar el rendimiento del adaptador de red y el estado del adaptador.

</div>

<div>

## <a name="windows-network-monitor"></a>Monitor de red de Windows

Recopila, muestra, analiza el uso de recursos en un servidor y mide el tráfico de red. Monitor de red supervisa exclusivamente la actividad de la red. Al capturar y analizar datos de red y usar estos datos con registros de rendimiento, puede determinar el uso de la red, identificar problemas de red y prever las necesidades futuras de la red.

Para obtener más información acerca del monitor de red 3,4 y para saber cómo instalar y configurar el monitor de red, y capturar y analizar datos, revise esta sesión: Introducción al monitor de red 3,3. Además, revise el [blog del monitor de red](https://blogs.technet.com/b/netmon/).

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

