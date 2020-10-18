---
title: 'Lync Server 2013: topología de referencia para organizaciones de tamaño mediano'
description: 'Lync Server 2013: topología de referencia para organizaciones de tamaño mediano.'
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
ms.openlocfilehash: 3b9e6ef467506865193dc26887e802198b16f42f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578616"
---
# <a name="reference-topology-for-lync-server-2013-in-medium-size-organizations"></a>Topología de referencia para Lync Server 2013 en organizaciones de tamaño mediano

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-10-07_

La topología de referencia con alta disponibilidad y un único centro de datos está diseñada para pequeñas y medianas organizaciones con un sitio central. La topología exacta del siguiente diagrama es para una organización de 20.000 usuarios.

**Topología de referencia para organizaciones medianas**

![Topología de referencia para un solo diagrama de centro de datos](images/Gg425939.12b574fd-0b14-4563-a88c-3c8b0809bb90(OCS.15).jpg "Topología de referencia para un solo diagrama de centro de datos")

  - **Agregar más servidores front-end para dar cabida a más usuarios.**     La topología exacta de este diagrama tiene tres servidores front-end para proporcionar compatibilidad con 20.000 usuarios. Si tiene un único sitio central y más usuarios, simplemente puede agregar más servidores front-end al grupo. El número máximo de usuarios por grupo es 80.000, con doce servidores front-end.
    
    Sin embargo, la topología de sitio único puede admitir aún más usuarios si se agrega otro grupo de servidores front-end al sitio.

  - **Se puede Agregar la recuperación ante desastres.**     Para esta organización, la alta disponibilidad de los servicios de Lync Server es una característica necesaria, pero no la de recuperación ante desastres. El grupo de servidores front-end que ha implementado proporciona alta disponibilidad.
    
    Si quisieran agregar la capacidad de recuperación ante desastres, podrían considerar la posibilidad de establecer otro centro de recursos y agregar otro grupo de servidores front-end y emparejarlo con el grupo de servidores front-end en su centro de recursos actual. A continuación, si hubiera un desastre que afectara a su grupo principal, los administradores podrían conmutar por error a los usuarios al grupo de copia de seguridad.

  - **Los servidores back-end están reflejados**     Para proporcionar mayor disponibilidad para las características básicas de usuario, la organización ha implementado un par reflejado de servidores back-end para cada grupo de servidores front-end. Se trata de una nueva opción de topología para Lync Server 2013 y es opcional. En su lugar, puede optar por implementar un único servidor back-end.

  - **Opciones de base de datos del servidor de supervisión.**     Esta organización ha implementado la supervisión para garantizar la calidad de las llamadas de telefonía IP empresarial y las conferencias de A/V. La supervisión se implementa en todos los servidores front-end y la base de datos de supervisión se combina con los servidores back-end. También se admiten topologías en las que la base de datos de supervisión se encuentra en un servidor independiente.

  - **Alta disponibilidad**     del servidor perimetral En esta organización de ejemplo con 20.000 usuarios, solo un servidor perimetral sería suficiente para el rendimiento. Sin embargo, hay un grupo de dos servidores perimetrales implementados para proporcionar alta disponibilidad.

  - **Opciones de implementación de sitios de sucursal.**     La organización de esta topología tiene implementada la telefonía IP empresarial como solución de voz. El sitio de sucursal 1 no tiene un vínculo de red de área extensa (WAN) resistente al sitio central, por lo que tiene una aplicación de sucursal con funciones de supervivencia implementada para mantener muchas características de Lync Server en caso de que el vínculo WAN al sitio central deje de funcionar. Sin embargo, el sitio de sucursal 2 tiene un vínculo WAN resistente, por lo que solo se necesita una puerta de enlace de red telefónica conmutada (RTC). La puerta de enlace RTC implementada allí permite el desvío de medios, por lo que no se necesita ningún servidor de mediación en el sitio de sucursal 2. Para obtener más información sobre cómo decidir qué implementar en un sitio de sucursal, consulte [Planning for Branch-site Voice Resiliency en Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) en la documentación referente a la planeación.

  - **Equilibrio de carga de DNS.**     El grupo de servidores front-end andEdge, tiene el equilibrio de carga de DNS para el tráfico SIP implementado. Este equilibrio elimina la necesidad de equilibradores de carga de hardware para los servidores perimetrales y reduce notablemente la configuración y el mantenimiento de los equilibradores de carga de hardware de otros grupos de servidores, ya que estos equilibradores solo se necesitan para tráfico HTTP. Para obtener más información sobre el equilibrio de carga de DNS, vea [equilibrio de carga de DNS en Lync Server 2013](lync-server-2013-dns-load-balancing.md) en la documentación referente a la planeación.

  - **Implementación de mensajería unificada de Exchange.** Esta topología de referencia incluye un servidor de mensajería unificada (UM) de Exchange, que ejecuta Microsoft Exchange Server, no Lync Server.
    
    Para obtener más información acerca de la mensajería unificada de Exchange, consulte [Planning for Exchange Unified Messaging Integration in Lync server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) y [Hosted Exchange Unified Messaging Integration in Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) en la documentación de planeación.

  - **Office Web Apps Server.** Se recomienda implementar un Office Web Apps Server o granja de servidores de Office Web Apps Server en cada organización que use conferencias web. Office Web Apps Server permite presentar diapositivas de PowerPoint en conferencias web. Para obtener más información, consulte Configuración de la [integración con Office Web Apps Server y Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

  - **Se recomiendan los servidores perimetrales.**     Aunque no es necesario implementar un servidor perimetral, se recomienda para cualquier tamaño de implementación. Puede maximizar la inversión de Lync Server implementando un servidor perimetral para proporcionar servicio a los usuarios que están actualmente fuera de los firewalls de la organización. Entre las ventajas se incluye lo siguiente:
    
      - Los propios usuarios de su organización pueden usar la funcionalidad de Lync Server, si trabajan desde casa o están de viaje.
    
      - Sus usuarios pueden invitar a usuarios externos para participar en reuniones.
    
      - Si tiene una organización de asociados, proveedores o clientes que también usa Lync Server, puede crear una *relación federada* con esa organización. La implementación de Lync Server entonces reconocerá a los usuarios de esa organización federada, lo que le proporcionará una mejor colaboración.
    
      - Los usuarios pueden intercambiar mensajes instantáneos con usuarios de servicios de mensajería instantánea pública, entre los que se incluyen los siguientes: Windows Live, AOL, Yahoo \! y Google Talk. Es posible que se requiera una licencia independiente para la conectividad de mensajería instantánea pública con estos servicios.
        
        <div>
        

        > [!IMPORTANT]  
        > <UL>
        > <LI>
        > <P>A partir del 1 de septiembre de 2012, la licencia de suscripción de usuario de conectividad de mensajería instantánea pública de Microsoft Lync ("PIC USL") ya no está disponible para la compra de contratos nuevos o de renovación. Los clientes con licencias activas podrán seguir federando a Yahoo! Messenger hasta que se cierre la fecha del servicio. Una fecha de finalización del ciclo de vida de junio de 2014 para AOL y Yahoo! se ha anunciado. Para obtener más información, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">compatibilidad con la conectividad de mensajería instantánea pública en Lync Server 2013</A>.</P>
        > <LI>
        > <P>La capa de PIC es una licencia por usuario por mes que es necesaria para que Lync Server u Office Communications Server se federe con Yahoo! Service. La capacidad de Microsoft para proporcionar este servicio ha estado supeditada al soporte de Yahoo!, el acuerdo subyacente para el que se liquida.</P>
        > <LI>
        > <P>Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo. La Federación con Windows Live Messenger no requiere licencias de usuario o de dispositivo adicionales aparte de la CAL de Lync Standard. La Federación de Skype se agregará a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas con mi y voz.</P></LI></UL>

        
        </div>

  - **Se pueden agregar directores.**     Si esta organización deseara ayudar a aumentar la seguridad contra ataques por denegación de servicio, también podría implementar un grupo de directores. Un director es un rol de servidor opcional e independiente en Lync Server que no aloja cuentas de usuario ni proporciona servicios de presencia o conferencia. Actúa como un servidor interno del próximo salto en el que un servidor perimetral enruta el tráfico SIP entrante destinado a los servidores internos. El director autentica previamente las solicitudes entrantes y las redirige al servidor o grupo de servidores principales del usuario. La preautenticación en el Director permite omitir solicitudes de cuentas de usuario desconocidas en la implementación. Un director ayuda a aislar los servidores front-end del tráfico malintencionado, como los ataques por denegación de servicio (DoS). Si la red está inundada con tráfico externo no válido en un ataque de este tipo, el tráfico termina en el director.

  - **Se recomienda System Center Operations Manager.**    Le recomendamos que supervise el estado de la implementación de Lync Server para ayudar a garantizar la disponibilidad del servicio para los usuarios finales. Puede supervisar Lync con el módulo de administración de System Center Operations Manager para Lync que está disponible como descarga gratuita de Microsoft. Con el paquete de administración de Lync, puede obtener alertas en tiempo real de forma proactiva cuando surgen problemas, ejecutar transacciones sintéticas para probar la funcionalidad de un extremo a otro de Lync, obtener informes para la disponibilidad del servicio y así sucesivamente. Esto le ayudará a responder de forma proactiva a los problemas con su implementación antes de que los usuarios finales los experimenten.

</div>

<span> </span>

</div>

</div>

</div>

