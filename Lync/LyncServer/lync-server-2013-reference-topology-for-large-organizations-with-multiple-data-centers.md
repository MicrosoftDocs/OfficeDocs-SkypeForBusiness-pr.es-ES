---
title: Lync Server 2013 topología de referencia para grandes organizaciones con varios centros de datos
description: 'Lync Server 2013: topología de referencia para grandes organizaciones con varios centros de datos.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reference topology for large organizations with multiple data centers
ms:assetid: 9a6aeae6-629b-49e6-9804-7ef369d7c3dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398797(v=OCS.15)
ms:contentKeyID: 48184887
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bfb88bd59e4bc27aefbdc94fdf53f094a09998f4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567606"
---
# <a name="reference-topology-for-lync-server-2013-in-large-organizations-with-multiple-data-centers"></a>Topología de referencia para Lync Server 2013 en grandes organizaciones con varios centros de datos

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-22_

La topología de referencia para una organización de gran tamaño con varios centros de datos es compatible con organizaciones de cualquier tamaño con más de un sitio central. La topología exacta del diagrama siguiente es para una organización de 50 000 usuarios, con 20 000 usuarios en el Sitio central A, 20 000 en el Sitio central B y un total de 10 000 en el Sitio central C y los sitios de sucursal. El tipo de topología mostrada en este diagrama puede adaptarse a organizaciones con un número cualquiera de usuarios.

Además de la alta disponibilidad proporcionada por los grupos de servidores front-end, esta topología agrega compatibilidad con la recuperación ante desastres. Los grupos de servidores front-end en los sitios centrales A y B se emparejan entre sí. Si uno de estos grupos de servidores deja de funcionar, el administrador podrá pasar los servicios para los usuarios afectados al grupo emparejado en el sitio no afectado.

Esta topología se muestra en varios diagramas con información general seguida de vistas detalladas de los sitios centrales.

**Información general de la topología de referencia para organizaciones de gran tamaño con varios centros de datos**

![Topología de referencia para varios centros de datos](images/Gg398797.471e1ce9-be11-44b9-9f4a-59e0551b7b30(OCS.15).jpg "Topología de referencia para varios centros de datos")

**Topología de referencia para organizaciones de gran tamaño: Vista detallada del Sitio central A**

![dab33f19-e77b-42da-9047-858fb9851264](images/Gg398797.dab33f19-e77b-42da-9047-858fb9851264(OCS.15).jpg "dab33f19-e77b-42da-9047-858fb9851264")

**Topología de referencia para organizaciones de gran tamaño: Vista detallada del Sitio central B**

![5ccaf1d4-bd53-4cb7-96fe-723147334e7f](images/Gg398797.5ccaf1d4-bd53-4cb7-96fe-723147334e7f(OCS.15).jpg "5ccaf1d4-bd53-4cb7-96fe-723147334e7f")

**Topología de referencia para organizaciones de gran tamaño: Vista detallada del Sitio central C**

![7238ca40-340c-491f-b497-ddc2665dadb6](images/Gg398797.7238ca40-340c-491f-b497-ddc2665dadb6(OCS.15).jpg "7238ca40-340c-491f-b497-ddc2665dadb6")

  - Los **grupos de servidores front-end se emparejan para habilitar la recuperación ante desastres.**     Los grupos de servidores front-end del sitio A y el sitio B se emparejan entre sí, para proporcionar compatibilidad con la recuperación ante desastres. Si se produce un error en el grupo de un sitio, el administrador puede realizar la conmutación por error de los usuarios de ese sitio en el grupo de servidores front-end emparejado en el otro sitio, con una interrupción mínima del servicio para los usuarios. Cada uno de estos dos grupos de servidores front-end tiene seis servidores, suficiente para 40 000 usuarios en ambos grupos en caso de conmutación por error. Para obtener más información, consulte [planeación de alta disponibilidad y recuperación ante desastres en Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

  - **Los servidores back-end están reflejados**     Para proporcionar mayor disponibilidad para las características básicas de usuario, la organización ha implementado un par reflejado de servidores back-end para cada grupo de servidores front-end. Esta es una topología opcional y, en su lugar, puede optar por implementar un único servidor back-end.

  - **Uso de un servidor Standard Edition en un sitio de sucursal.**     Esta organización considera el sitio C como un sitio de sucursal porque tiene solo 600 empleados. Sin embargo, los usuarios de este sitio realizan muchas conferencias de A/V entre ellos. Si se implementó en Lync Server como sitio de sucursal, los medios de estas conferencias se ejecutarían en la red de área extensa (WAN) hacia y desde un sitio central que tiene un servidor front-end implementado. Para evitar esta carga de ancho de banda potencial, ha instalado un par de servidores Standard Edition en este sitio, que hospedarán estas conferencias. Y como los servidores Standard Edition están instalados allí, Lync Server por definición lo considera un sitio central y se trata como tal en el generador de topologías y la herramienta de planeación.
    
    Solo un servidor Standard Edition sería suficiente para mejorar el rendimiento, pero la organización ha implementado dos y los ha emparejado para proporcionar alta disponibilidad en caso de que un servidor deje de funcionar.
    
    A pesar de que el Sitio C se considera un sitio central, no es necesario implementar servidores perimetrales en él. En este ejemplo, el Sitio C usará los servidores perimetrales implementados en el Sitio A.

  - **Supervisión y archivado**     Esta organización ha implementado la supervisión y el archivado. Si se implementa Supervisión o Archivado, se ejecutará en todos los servidores front-end. Las bases de datos de estas características pueden combinarse con la base de datos back-end o bien ubicarse en un servidor aparte. Esta organización ha ubicado dichas bases de datos en un servidor aparte de los servidores back-end, en el Sitio central B. Las bases de datos de esta ubicación reciben datos de Supervisión y Archivado desde los servidores front-end de todos los sitios.

  - **Opciones de implementación de sitios de sucursal.**     Esta organización tiene en realidad más de 50 sitios de sucursal, solo tres de los cuales se muestran en los diagramas detallados. Los sitios de sucursal 1 y 3 no tienen un vínculo WAN resistente al sitio central, por lo que tienen aplicaciones de sucursal con funciones de supervivencia implementadas para proporcionar el servicio de telefonía en caso de que el vínculo WAN al sitio central deje de funcionar. Sin embargo, el sitio de sucursal 2 tiene un vínculo WAN resistente, por lo que solo necesita una puerta de enlace de red telefónica conmutada (RTC). La puerta de enlace RTC implementada admite la omisión de medios, por lo que no se necesita ningún servidor de mediación en el sitio de sucursal B. Para obtener más información sobre cómo decidir qué instalar en un sitio de sucursal, consulte [Planning for Enterprise Voice Resiliency in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) en la documentación referente a la planeación.

  - **Enlace troncal SIP y servidor de mediación.**     Observe que en el sitio central B, el servidor de mediación no se combina con los servidores front-end. Esto se debe a que el servidor de mediación independiente es recomendable para sitios que usen el enlace troncal SIP. En la mayoría de casos restantes, se recomienda instalar el servidor de mediación con el servidor front-end. Para obtener más información sobre las topologías de servidores de mediación, consulte [componentes y topologías para servidor de mediación en Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) en la documentación referente a la planeación.

  - **Chat persistente está implementado.**     Esta organización ha implementado los servidores necesarios para habilitar el chat persistente. Ha implementado varios servidores front-end de Chat persistente para, por un lado, procesar la carga del número de usuarios del grupo de servidores y, por otro, ofrecer alta disponibilidad. También ha implementado Cumplimiento para Chat persistente y ha ubicado el Almacén de Chat persistente y el Almacén de Cumplimiento de Chat persistente en servidores aparte. Estos almacenes pueden combinarse entre sí e incluso con el servidor back-end, pero esta organización ha optado por separarlos para ofrecer un mejor rendimiento.

  - **Equilibrio de carga de DNS.**     El grupo de servidores front-end y el grupo de servidores perimetrales. De esta forma, no son necesarios equilibradores de carga de hardware para la interfaz interna de los servidores perimetrales y se reduce significativamente la cantidad de tiempo que se debe invertir en la configuración y el mantenimiento de los equilibradores de carga de hardware para el resto de grupos de servidores, ya que los equilibradores de carga de hardware solo se necesitan para el tráfico HTTP. Para obtener más información sobre el equilibrio de carga de DNS, vea [equilibrio de carga de DNS en Lync Server 2013](lync-server-2013-dns-load-balancing.md) en la documentación referente a la planeación.

  - **Implementación de mensajería unificada de Exchange.**    Lync Server funciona con implementaciones *locales* de mensajería unificada (MU) de Exchange y mensajería unificada de Exchange *hospedada* . El sitio central A incluye un servidor de mensajería unificada (UM) de Exchange, que ejecuta Microsoft Exchange Server, no Lync Server. La funcionalidad de mensajería unificada de Exchange para Lync Server se ejecuta en el grupo de servidores front-end.
    
    El Sitio central B usa servicios de Exchange hospedados, de modo que las funciones del servidor de mensajería unificada de Exchange también están hospedadas.
    
    Para obtener más información acerca de la mensajería unificada de Exchange, consulte [Planning for Exchange Unified Messaging Integration in Lync server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) y [Hosted Exchange Unified Messaging Integration in Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) en la documentación de planeación.

  - **Office Web Apps Server.**   Se recomienda implementar un Office Web Apps Server o granja de servidores de Office Web Apps Server en cada organización que use conferencias web. Puede implementar una única granja de servidores de Office Web Apps Server en un sitio que sirva tráfico desde todos los sitios, o bien implementarla en cada sitio. Office Web Apps Server permite presentar diapositivas de PowerPoint en conferencias web. Para obtener más información, consulte Configuración de la [integración con Office Web Apps Server y Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

  - **Se pueden agregar directores.**    Si esta organización deseara aumentar la seguridad contra ataques por denegación de servicio, también podría implementar un grupo de directores. Un director es un rol de servidor opcional e independiente en Lync Server que no aloja cuentas de usuario ni proporciona servicios de presencia o conferencia. Actúa como un servidor interno del próximo salto en el que un servidor perimetral enruta el tráfico SIP entrante destinado a los servidores internos. El director autentica previamente las solicitudes entrantes y las redirige al servidor o grupo de servidores principales del usuario. La preautenticación en el Director permite omitir solicitudes de cuentas de usuario desconocidas en la implementación. Un director ayuda a aislar los servidores front-end del tráfico malintencionado, como los ataques por denegación de servicio (DoS). Si la red está inundada con tráfico externo no válido en un ataque de este tipo, el tráfico termina en el director.

  - **Se ha implementado System Center Operations Manager.**    Le recomendamos que supervise el estado de la implementación de Lync Server para garantizar la disponibilidad del servicio para los usuarios finales. Puede supervisar Lync con el módulo de administración de System Center Operations Manager para Lync que está disponible como descarga gratuita de Microsoft. Con el paquete de administración de Lync, puede obtener alertas en tiempo real de forma proactiva cuando surgen problemas, ejecutar transacciones sintéticas para probar la funcionalidad de un extremo a otro de Lync, obtener informes para la disponibilidad del servicio y así sucesivamente. Esto le ayudará a responder de forma proactiva a los problemas con su implementación antes de que los usuarios finales los experimenten.
    
    Esta organización ha implementado un servidor de System Center Operations Manager en cada sitio central.

</div>

<span> </span>

</div>

</div>

</div>

