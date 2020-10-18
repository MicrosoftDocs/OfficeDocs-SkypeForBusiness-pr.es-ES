---
title: Lync Server 2013 topología de referencia para pequeñas organizaciones
description: 'Lync Server 2013: topología de referencia para pequeñas organizaciones.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reference topology for small organizations
ms:assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398095(v=OCS.15)
ms:contentKeyID: 48183272
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f2f23a963543c303e54f8f2773d499e8317a63a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578636"
---
# <a name="reference-topology-for-lync-server-2013-in-small-organizations"></a>Topología de referencia para Lync Server 2013 en pequeñas organizaciones

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-10-07_

La topología de referencia para organizaciones pequeñas muestra cómo puede implementar una solución robusta y de alta disponibilidad mediante la implementación de solo tres servidores que ejecutan Lync Server.

**Topología de referencia para pequeñas organizaciones**

![Topología de referencia implementar tres diagramas de servidores](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "Topología de referencia implementar tres diagramas de servidores")

  - **Par de servidores Standard Edition implementados**     Esta organización tiene 4.000 usuarios en su sitio central. La organización ha implementado dos servidores Standard Edition y los ha combinado para habilitar la alta disponibilidad y la recuperación ante desastres. Cada servidor aloja 2.000 usuarios, pero la información acerca de todos los usuarios se sincroniza entre los dos servidores. Si se produce un error, un administrador puede conmutar por error a los usuarios para que los atienda el otro servidor, con el mínimo de interrupciones para los usuarios. Para obtener más información sobre las características de alta disponibilidad y recuperación ante desastres en Lync Server 2013, consulte [planeación de alta disponibilidad y recuperación ante desastres en Lync server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

  - **Se recomienda la implementación de servidores perimetrales.**     Aunque no se requiere la implementación de un servidor perimetral para la mensajería instantánea interna, la presencia y la Conferencia, le recomendamos incluso en el caso de implementaciones pequeñas. Puede maximizar la inversión de Lync Server implementando un servidor perimetral para proporcionar servicio a los usuarios que están actualmente fuera de los firewalls de la organización. Entre las ventajas se incluye lo siguiente:
    
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

  - **Supervivencia del sitio de sucursal.**     Esta organización está ejecutando un programa piloto de la característica Enterprise Voice de Lync Server. Algunos usuarios usan Lync Server como su única solución de voz. Algunos de estos usuarios de la prueba piloto de voz se encuentran en el sitio de sucursal. El sitio de sucursal no tiene un vínculo de red de área extensa (WAN) confiable al sitio central, por lo que se implementa una aplicación de sucursal con funciones de supervivencia. Con esta implementación, si el vínculo WAN deja de funcionar, los usuarios del sitio de sucursal pueden seguir realizando y recibiendo llamadas (ambas llamadas dentro de la organización y las llamadas RTC), tienen funcionalidad de correo de voz y se comunican con la mensajería instantánea de dos participantes (mi). Los usuarios también pueden autenticarse cuando el vínculo WAN tampoco está disponible.

  - **Implementación de mensajería unificada de Exchange.** Esta topología de referencia incluye un servidor de mensajería unificada (UM) de Exchange, que ejecuta Microsoft Exchange Server, no Lync Server.
    
    Para obtener más información acerca de la mensajería unificada de Exchange, consulte [Planning for Exchange Unified Messaging Integration in Lync server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) y [Hosted Exchange Unified Messaging Integration in Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) en la documentación de planeación.

  - **Office Web Apps Server.** Se recomienda implementar un Office Web Apps Server o granja de servidores de Office Web Apps Server en cada organización que use conferencias web. Office Web Apps Server hace posible que las diapositivas de PowerPoint se presenten en las conferencias web. Para obtener más información, consulte Configuración de la [integración con Office Web Apps Server y Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

</div>

<span> </span>

</div>

</div>

</div>

