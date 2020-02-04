---
title: 'Lync Server 2013: Topología de referencia para organizaciones medianas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reference topology for medium-size organizations
ms:assetid: 446b0914-2198-445e-ab6e-94802acebd5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425939(v=OCS.15)
ms:contentKeyID: 48184026
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da4c29107a6ca3d33e76708be9eec07297eeaf93
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724410"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-medium-size-organizations"></a>Topología de referencia para organizaciones medianas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-10-07_

La topología de referencia con alta disponibilidad y un único centro de datos está diseñada para pequeñas y medianas organizaciones con un sitio central. La topología exacta del diagrama siguiente es para una organización de 20 000 usuarios.

**Topología de referencia para organizaciones medianas**

![Diagrama de la topología de referencia para un solo centro de datos](images/Gg425939.12b574fd-0b14-4563-a88c-3c8b0809bb90(OCS.15).jpg "Diagrama de la topología de referencia para un solo centro de datos")

  - **Dar cabida a más usuarios agregando más servidores de aplicaciones para el usuario.**    La topología exacta de este diagrama tiene tres servidores front-end para proporcionar compatibilidad con usuarios de 20.000. Si dispone de un único sitio central y más usuarios, solo tiene que agregar más servidores front-end al grupo de servidores. La cantidad máxima de usuarios por grupo de servidores es de 80 000, con doce servidores front-end.
    
    Pero, la topología de sitio único puede admitir incluso más usuarios si se agrega otro grupo de servidores front-end al sitio.

  - **Se puede Agregar la recuperación ante desastres.**    Para esta organización, la alta disponibilidad de los servicios de Lync Server es una característica necesaria, pero no la de recuperación ante desastres. El grupo de servidores front-end que ha implementado proporciona alta disponibilidad.
    
    Si desearan agregar la capacidad de recuperación ante desastres, podrían pensar en establecer otro centro de datos y agregar allí otro grupo de servidores front-end y vincularlo con el grupo de servidores front-end de su centro de datos actual. Luego, si se produjera un desastre que afectara al grupo principal, los administradores podrían realizar la conmutación por error de los usuarios al grupo de copia de seguridad.

  - **Los servidores de servicios**   de fondo se reflejan para proporcionar una mayor disponibilidad para las características básicas de los usuarios, la organización ha implementado un par de servidores back-end reflejados para cada grupo de servidores front-end. Esta es una nueva opción de topología para Lync Server 2013 y es opcional. En su lugar, puede optar por implementar un único servidor de back-end.

  - **Supervisar las opciones de base de datos del servidor.**    Esta organización ha implementado la supervisión para garantizar la calidad de las llamadas de voz de empresa y las conferencias a/V. La supervisión se implementa en cada servidor front-end y la base de datos de supervisión se combina con los servidores back-end. También se admiten topologías en las que la base de datos de supervisión se encuentra en un servidor independiente.

  - **Servidor perimetral alta disponibilidad**    en esta organización de ejemplo con usuarios de 20.000, solo un servidor perimetral sería suficiente para el rendimiento. Sin embargo, hay un grupo de dos servidores perimetrales implementados para ofrecer una alta disponibilidad.

  - **Opciones de implementación de sitio de sucursal.**    La organización de esta topología tiene la característica telefonía IP implementada como solución de voz. El sitio de la sucursal 1 no tiene un vínculo de red de área extensa (WAN) resistente al sitio central, por lo que tiene un dispositivo de sucursal que se ha implementado para mantener muchas características de Lync Server en caso de que se produzca un vínculo WAN al sitio central. Pero, el sitio de sucursal 2 tiene un vínculo WAN resistente, por lo que solo se necesita una puerta de enlace de la red telefónica conmutada (RTC). La puerta de enlace RTC implementada allí permite la omisión de medios, por lo que no se necesita ningún servidor de mediación en el sitio de sucursal 2. Para obtener más información sobre cómo decidir qué implementar en un sitio de sucursal, consulte planear la resistencia de voz de un [sitio de sucursal en Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) en la documentación de planificación.

  - **Equilibrio de carga de DNS.**    El grupo de servidores de AndEdge Pool front-end, tiene el equilibrio de carga de DNS para el tráfico SIP implementado. Este equilibrio elimina la necesidad de equilibradores de carga de hardware para los servidores perimetrales y reduce notablemente la instalación y el mantenimiento de los equilibradores de carga de hardware de otros grupos de servidores, ya que estos equilibradores solo se necesitan para tráfico HTTP. Para obtener más información sobre el equilibrio de carga de DNS, consulte [equilibrio de carga de DNS en Lync Server 2013](lync-server-2013-dns-load-balancing.md) en la documentación de planeación.

  - **Implementación de mensajería unificada de Exchange.** Esta topología de referencia incluye un servidor de mensajería unificada (UM) de Exchange, que ejecuta Microsoft Exchange Server, no Lync Server.
    
    Para obtener más información sobre la mensajería unificada de Exchange, consulte [planificación de la integración de mensajería unificada de Exchange en Lync server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) y la [integración de mensajería unificada de Exchange hospedada en Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) en la documentación de planificación.

  - **Servidor de Office Web Apps.** Recomendamos implementar un servidor de Office Web Apps o una granja de servidores de Office Web Apps en cada organización que use conferencias web. El servidor de Office Web Apps permite presentar diapositivas de PowerPoint en conferencias web. Para obtener más información, vea [configurar la integración con Office Web Apps Server y Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

  - **Se recomienda usar servidores perimetrales.**    Aunque no es necesario implementar un servidor perimetral, le recomendamos que lo recomiende para cualquier tamaño de implementación. Puede maximizar la inversión de Lync Server implementando un servidor perimetral para proporcionar servicio a los usuarios que se encuentran fuera de los firewalls de la organización. Entre las ventajas se incluye las siguientes:
    
      - Los usuarios de su organización pueden usar la funcionalidad de Lync Server, si están trabajando desde casa o están de viaje.
    
      - Los usuarios pueden invitar a usuarios externos para participar en reuniones.
    
      - Si tiene una organización de socios, proveedores o clientes que también usa Lync Server, puede formar una *relación federada* con esa organización. La implementación de Lync Server reconocería los usuarios de esa organización federada, lo que lleva a una mejor colaboración.
    
      - Los usuarios pueden intercambiar mensajes instantáneos con usuarios de servicios de mensajería instantánea pública, entre los que se incluyen cualquiera de los siguientes: Windows\!Live, AOL, Yahoo y Google Talk. Es posible que se necesite una licencia por separado para la conectividad de mensajería instantánea pública con estos servicios.
        
        <div>
        

        > [!IMPORTANT]  
        > <UL>
        > <LI>
        > <P>A partir del 1 de septiembre de 2012, la licencia de suscripción de usuario de conectividad de mensajería instantánea pública de Microsoft Lync ("PIC USL") ya no está disponible para la compra de contratos nuevos o de renovación. Los clientes con licencias activas podrán seguir federando a Yahoo! Messenger hasta que se cierre la fecha del servicio. Una fecha de fin de vida de junio de 2014 para AOL y Yahoo! ha sido anunciado. Para obtener más información, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">compatibilidad de la conectividad de mensajería instantánea pública en Lync Server 2013</A>.</P>
        > <LI>
        > <P>El PIC USL es una licencia por usuario por mes de suscripción que es necesaria para que Lync Server o Office Communications Server se federe con Yahoo! Mensajería. La capacidad de Microsoft para proporcionar este servicio está supeditada al soporte de Yahoo!, el contrato subyacente para el que se está pospuesto.</P>
        > <LI>
        > <P>Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo. La Federación con Windows Live Messenger no requiere licencias adicionales para usuarios y dispositivos más allá de la CAL de Lync Standard. La Federación de Skype se agrega a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas con la mensajería instantánea y la voz.</P></LI></UL>

        
        </div>

  - **Se pueden agregar directores.**    Si esta organización desea ayudar a aumentar la seguridad contra ataques de denegación de servicio, también podría implementar un grupo de directores. Un director es un rol de servidor independiente y opcional de Lync Server que no aloja cuentas de usuario o proporciona servicios de presencia o de conferencia. Actúa como un servidor interno del próximo salto al que un servidor perimetral enruta el tráfico SIP entrante destinado a los servidores internos. El director autentica previamente las solicitudes entrantes y las redirige al grupo de servidores o al grupo de servidores domésticos del usuario. La autenticación previa en el director permite quitar las solicitudes de cuentas de usuario desconocidas de la implementación. Un director ayuda a aislar a los servidores front-end de tráfico malintencionado, como ataques de denegación de servicio (DoS). Si la red se inunda con tráfico externo no válido en tal ataque, el tráfico termina en el director.

  - **Se recomienda System Center Operations Manager.**   Le recomendamos que supervise el estado de la implementación de Lync Server para garantizar la disponibilidad del servicio para los usuarios finales. Puede supervisar Lync con el paquete de administración de System Center Operations Manager para Lync que está disponible como descarga gratuita de Microsoft. Con el paquete de administración de Lync, puede obtener alertas en tiempo real de forma activa cuando se producen problemas, ejecutar transacciones sintéticas para probar la funcionalidad completa de Lync, obtener informes para la disponibilidad del servicio, etc. This helps you to proactively respond to issues with your deployment before end-users experience them.

</div>

<span> </span>

</div>

</div>

</div>

