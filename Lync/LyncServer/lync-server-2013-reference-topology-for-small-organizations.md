---
title: Topología de referencia de Lync Server 2013 para pequeñas organizaciones
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reference topology for small organizations
ms:assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398095(v=OCS.15)
ms:contentKeyID: 48183272
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c06a3585a342ecc7fa7c41ff2b2b2682d2b8a0c3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823815"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-small-organizations"></a>Topología de referencia para Lync Server 2013 en pequeñas organizaciones

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-10-07_

La topología de referencia para organizaciones pequeñas muestra cómo puede implementar una solución robusta y de alta disponibilidad implementando solo tres servidores que ejecuten Lync Server.

**Topología de referencia para pequeñas organizaciones**

![Topología de referencia implementar tres diagramas de servidores] (images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "Topología de referencia implementar tres diagramas de servidores")

  - **Par de servidores Standard Edition implementados**     esta organización tiene 4.000 usuarios en su sitio central. La organización ha implementado dos servidores Standard Edition y los ha emparejado para habilitar la alta disponibilidad y la recuperación ante desastres. Each server homes 2,000 users, but information about all users is synchronized between the two servers. If one goes down, an administrator can fail over those users to be served by the other server, with a minimum of disruption to users. Para obtener más información sobre las características de alta disponibilidad y recuperación ante desastres de Lync Server 2013, consulte [planear la alta disponibilidad y la recuperación ante desastres en Lync server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

  - **Se recomienda la implementación del servidor perimetral.**    Aunque no es necesario implementar un servidor perimetral para la mensajería instantánea interna, la presencia y las conferencias, le recomendamos incluso para implementaciones pequeñas. Puede maximizar la inversión de Lync Server implementando un servidor perimetral para proporcionar servicio a los usuarios que se encuentran fuera de los firewalls de la organización. Entre las ventajas se incluye las siguientes:
    
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

  - **Supervivencia del sitio de la sucursal.**    Esta organización está ejecutando un programa piloto de la característica de telefonía IP empresarial de Lync Server. Algunos usuarios usan Lync Server como su única solución de voz. Algunos de estos usuarios de la prueba piloto de voz se encuentran en el sitio de la sucursal. El sitio de la sucursal no tiene un vínculo de red de área extensa (WAN) confiable al sitio central para que se implemente en él un dispositivo de sucursal con la supervivencia. Gracias a esta implementación, si el vínculo WAN deja de funcionar, los usuarios del sitio de sucursal podrán seguir realizando y recibiendo llamadas (llamadas dentro de la organización y llamadas RTC), disponer de la función del correo de voz y comunicarse por medio de la mensajería instantánea (MI) entre dos participantes. Los usuarios también pueden autenticarse cuando el vínculo WAN no está disponible.

  - **Implementación de mensajería unificada de Exchange.** Esta topología de referencia incluye un servidor de mensajería unificada (UM) de Exchange, que ejecuta Microsoft Exchange Server, no Lync Server.
    
    Para obtener más información sobre la mensajería unificada de Exchange, consulte [planificación de la integración de mensajería unificada de Exchange en Lync server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) y la [integración de mensajería unificada de Exchange hospedada en Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) en la documentación de planificación.

  - **Servidor de Office Web Apps.** Recomendamos implementar un servidor de Office Web Apps o una granja de servidores de Office Web Apps en cada organización que use conferencias web. Office Web Apps Server permite que las diapositivas de PowerPoint se presenten en conferencias web. Para obtener más información, vea [configurar la integración con Office Web Apps Server y Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

</div>

<span> </span>

</div>

</div>

</div>

