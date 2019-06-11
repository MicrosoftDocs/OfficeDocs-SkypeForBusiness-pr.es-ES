---
title: 'Lync Server 2013: Topología de referencia para grandes organizaciones con varios centros de datos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reference topology for large organizations with multiple data centers
ms:assetid: 9a6aeae6-629b-49e6-9804-7ef369d7c3dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398797(v=OCS.15)
ms:contentKeyID: 48184887
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2460378d19f8edb4e845778cacaf01c7141204c3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823836"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-large-organizations-with-multiple-data-centers"></a>Topología de referencia para grandes organizaciones con varios centros de datos para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-22_

La topología de referencia para una organización de gran tamaño con varios centros de datos es compatible con organizaciones de cualquier tamaño con más de un sitio central. La topología exacta del diagrama siguiente es para una organización de 50 000 usuarios, con 20 000 usuarios en el sitio central A, 20 000 en el sitio central B y un total de 10 000 en el sitio central C y los sitios de sucursal. El tipo de topología mostrada en este diagrama puede adaptarse a organizaciones con cualquier cantidad de usuarios.

Además de la alta disponibilidad proporcionada por los grupos de servidores de aplicaciones para el usuario, esta topología agrega compatibilidad de recuperación ante desastres. Los grupos front-end de los sitios centrales A y B están emparejados. Si uno de estos grupos de servidores deja de funcionar, el administrador podrá cambiar los servicios de los usuarios afectados al grupo emparejado en el sitio no afectado.

Esta topología se muestra en varios diagramas con información general seguida de vistas detalladas de los sitios centrales.

**Información general de la topología de referencia para organizaciones de gran tamaño con varios centros de datos**

![Topología de referencia para varios centros de datos] (images/Gg398797.471e1ce9-be11-44b9-9f4a-59e0551b7b30(OCS.15).jpg "Topología de referencia para varios centros de datos")

**Topología de referencia para organizaciones de gran tamaño: Vista detallada del Sitio central A**

![dab33f19-e77b-42da-9047-858fb9851264] (images/Gg398797.dab33f19-e77b-42da-9047-858fb9851264(OCS.15).jpg "dab33f19-e77b-42da-9047-858fb9851264")

**Topología de referencia para organizaciones de gran tamaño: Vista detallada del Sitio central B**

![5ccaf1d4-bd53-4cb7-96fe-723147334e7f] (images/Gg398797.5ccaf1d4-bd53-4cb7-96fe-723147334e7f(OCS.15).jpg "5ccaf1d4-bd53-4cb7-96fe-723147334e7f")

**Topología de referencia para organizaciones de gran tamaño: Vista detallada del Sitio central C**

![7238ca40-340c-491f-b497-ddc2665dadb6] (images/Gg398797.7238ca40-340c-491f-b497-ddc2665dadb6(OCS.15).jpg "7238ca40-340c-491f-b497-ddc2665dadb6")

  - **Los grupos de servidores front-end se emparejan para habilitar la recuperación ante desastres.**    Los grupos de aplicaciones para el usuario del sitio a y el sitio B están emparejados entre sí, para proporcionar compatibilidad con la recuperación ante desastres. Si se produce un error en el grupo de un sitio, el administrador puede migrar por error los usuarios de ese sitio a la agrupación front-end del otro sitio, con una interrupción mínima de servicio para los usuarios. Each of these two Front End pools has six servers, which is enough for all 40,000 users in both pools in case of failover. Para obtener más información, vea [planear la alta disponibilidad y la recuperación ante desastres en Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

  - **Los servidores de servicios**   de fondo se reflejan para proporcionar una mayor disponibilidad para las características básicas de los usuarios, la organización ha implementado un par de servidores back-end reflejados para cada grupo de servidores front-end. Esta es una topología opcional y puede optar por implementar un único servidor de servicios de fondo en su lugar.

  - **Usar un servidor Standard Edition en un sitio de sucursal.**    Esta organización considera que el sitio C es un sitio de sucursal porque tiene solo 600 empleados. However, the users there have many A/V conferences among themselves. Si se ha implementado en Lync Server como sitio de sucursal, los medios de estas conferencias se ejecutarán en la red de área extensa (WAN) a y desde un sitio central que tiene un servidor front-end implementado. Para evitar esta carga potencial de ancho de banda, han instalado un par de servidores Standard Edition en este sitio, que hospedarán estas conferencias. Y como los servidores Standard Edition están instalados allí, Lync Server por definición lo considera un sitio central, y se trata como tal en el generador de topologías y la herramienta de planeación.
    
    Solo un servidor Standard Edition sería suficiente para el rendimiento, pero la organización ha implementado dos y los ha emparejado para ofrecer alta disponibilidad en caso de que un servidor se quede sin funcionar.
    
    A pesar de que el sitio C se considera un sitio central, no es necesario implementar servidores perimetrales en él. En este ejemplo, el sitio C usará los servidores perimetrales implementados en el sitio A.

  - **La supervisión**y el archivado de esta organización han implementado la supervisión y el archivado.    Si se implementa la supervisión o el archivado, se ejecutarán en todos los servidores front-end. Las bases de datos de estas características pueden combinarse con la base de datos back-end, o bien ubicarse en un servidor aparte. Esta organización ha ubicado dichas bases de datos en un servidor aparte de los servidores back-end, en el sitio central B. Las bases de datos de esta ubicación reciben datos de supervisión y archivado desde los servidores front-end de todos los sitios.

  - **Opciones de implementación de sitio de sucursal.**    En realidad, esta organización tiene más de 50 sitios de sucursales, solo tres de los cuales se muestran en los diagramas detallados. Los sitios de sucursales 1 y 3 no tienen un vínculo WAN resistente al sitio central, por lo que tienen equipos de sucursales reutilizables implementados para proporcionar servicio telefónico en caso de que se produzca un vínculo WAN al sitio central. El sitio de la sucursal 2 no obstante, tiene un vínculo WAN resistente, por lo que solo necesita una puerta de enlace de red telefónica conmutada (RTC). La puerta de enlace RTC implementada admite la omisión de medios, por lo que no es necesario un servidor de mediación en el sitio de sucursal B. Para más información sobre cómo decidir qué instalar en un sitio de sucursal, consulte [planificación de la resistencia de telefonía IP empresarial en Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) en la documentación de planificación.

  - **Servidor de mediación y Troncalización SIP.**    Observe que en el sitio central B, el servidor de mediación no se colocará con los servidores front-end. Esto se debe a que se recomienda un servidor de mediación independiente para los sitios que usan Troncalización SIP. En la mayoría de las demás instancias, le recomendamos que Collocate servidor de mediación con el servidor front-end. Para obtener más información sobre las topologías de servidores de mediación, vea [componentes y topologías de servidor de mediación en Lync server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) en la documentación de planeación.

  - **El chat persistente se ha implementado.**    Esta organización ha implementado los servidores necesarios para habilitar el chat persistente. Ha implementado varios servidores front-end de chat persistente para, por un lado, procesar la carga de la cantidad de usuarios del grupo de servidores y, por otro, ofrecer alta disponibilidad. También ha implementado el cumplimiento para el chat persistente y ha ubicado el almacén de chat persistente y el almacén de cumplimiento de chat persistente en servidores independientes. Estos almacenes pueden combinarse entre sí e incluso con el servidor back-end, pero esta organización ha optado por separarlos para ofrecer un mejor rendimiento.

  - **Equilibrio de carga de DNS.**    El grupo de servidores front-end y el grupo de servidores perimetrales. De esta manera, no son necesarios los equilibradores de carga de hardware para la interfaz interna de los servidores perimetrales y se reduce significativamente la cantidad de tiempo que necesaria para la instalación y el mantenimiento de los equilibradores de carga de hardware para el resto de los grupos de servidores, ya que los equilibradores de carga de hardware solo se necesitan para el tráfico HTTP. Para obtener más información sobre el equilibrio de carga de DNS, consulte [equilibrio de carga de DNS en Lync Server 2013](lync-server-2013-dns-load-balancing.md) en la documentación de planeación.

  - **Implementación de mensajería unificada de Exchange.**   Lync Server funciona con las implementaciones *locales* de mensajería unificada de Exchange (UM) y la mensajería unificada de Exchange *hospedada* . El sitio central A incluye un servidor de mensajería unificada (UM) de Exchange, que ejecuta Microsoft Exchange Server, no Lync Server. La funcionalidad de mensajería unificada de Exchange para Lync Server se ejecuta en el grupo de servidores front-end.
    
    El sitio central B usa servicios de Exchange hospedados, de modo que las funciones del servidor de mensajería unificada de Exchange también están hospedadas.
    
    Para obtener más información sobre la mensajería unificada de Exchange, consulte [planificación de la integración de mensajería unificada de Exchange en Lync server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) y la [integración de mensajería unificada de Exchange hospedada en Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) en la documentación de planificación.

  - **Office Web Apps Server.**   Recomendamos implementar un servidor de Office Web Apps o una granja de servidores de Office Web Apps en cada organización que use conferencias web. Puede implementar una sola granja de Office Web Apps Server en un sitio que sirva de tráfico de todos los sitios o implementarla en cada sitio. El servidor de Office Web Apps permite presentar diapositivas de PowerPoint en conferencias web. Para obtener más información, vea [configurar la integración con Office Web Apps Server y Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

  - **Se pueden agregar directores.**   Si esta organización desea aumentar la seguridad contra ataques de denegación de servicio, también podría implementar un grupo de directores. Un director es un rol de servidor independiente y opcional de Lync Server que no aloja cuentas de usuario o proporciona servicios de presencia o de conferencia. Actúa como un servidor interno del próximo salto al que un servidor perimetral enruta el tráfico SIP entrante destinado a los servidores internos. El director autentica previamente las solicitudes entrantes y las redirige al grupo de servidores o al grupo de servidores domésticos del usuario. La autenticación previa en el director permite quitar las solicitudes de cuentas de usuario desconocidas de la implementación. Un director ayuda a aislar a los servidores front-end de tráfico malintencionado, como ataques de denegación de servicio (DoS). Si la red se inunda con tráfico externo no válido en tal ataque, el tráfico termina en el director.

  - **Se ha implementado System Center Operations Manager.**   Le recomendamos que supervise el estado de la implementación de Lync Server para garantizar la disponibilidad del servicio para los usuarios finales. Puede supervisar Lync con el paquete de administración de System Center Operations Manager para Lync que está disponible como descarga gratuita de Microsoft. Con el paquete de administración de Lync, puede obtener alertas en tiempo real de forma activa cuando se producen problemas, ejecutar transacciones sintéticas para probar la funcionalidad completa de Lync, obtener informes para la disponibilidad del servicio, etc. This helps you to proactively respond to issues with your deployment before end-users experience them.
    
    Esta organización ha implementado un servidor de System Center Operations Manager en cada sitio central.

</div>

<span> </span>

</div>

</div>

</div>

