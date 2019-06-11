---
title: 'Lync Server 2013: Definir los requisitos de los servidores front-end, la mensajería instantánea y la presencia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your requirements for Front End Servers, instant messaging, and presence
ms:assetid: c21198bc-520c-4d17-8b84-7ff1475b9b0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412956(v=OCS.15)
ms:contentKeyID: 48185319
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 176b73f6d82c03e3bcdb0f2b0066752cd68f307c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835688"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>Definir los requisitos de los servidores front-end, la mensajería instantánea y la presencia en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-10-07_

La tarea principal de planear la mensajería instantánea y la presencia es asegurarse de que tiene los servidores frontales suficientes para sus usuarios.

<div>

## <a name="enabling-communication-with-external-users"></a>Habilitar la comunicación con usuarios externos

Puede aumentar enormemente los beneficios de su inversión en Lync Server al permitir que los usuarios se comuniquen con usuarios externos. Entre los usuarios externos se pueden incluir:

  - **Los usuarios**   remotos de su organización, cuando trabajan fuera de los firewalls y usan sus equipos portátiles u otros dispositivos de Lync Server.

  - **Usuarios federados**   usuarios de empresas con las que trabaja y que también ejecutan Lync Server. Si desea habilitar a sus usuarios para que se pongan en contacto fácilmente con estos otros usuarios, cree relaciones federadas con estas compañías.

  - **Usuarios públicos los**   usuarios de servicios de mensajería instantánea pública, como los servicios de mensajería instantánea proporcionados por la red de\!Windows Live de servicios de Internet, Yahoo y AOL, y los usuarios de proveedores y servidores que usan el protocolo de presencia y mensajería extensible (XMPP), como Google Talk.
    
    <div>
    

    > [!NOTE]  
    > Tenga en cuenta que es posible que se necesite una licencia independiente para la conectividad de mensajería instantánea pública con Windows Live, AOL y Yahoo!

    
    </div>
    
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

Para habilitar cualquiera de estos escenarios o todos ellos, debe implementar un servidor perimetral que le ayude a habilitar las comunicaciones seguras entre la implementación de Lync Server y los usuarios externos. Los usuarios remotos de su organización y los usuarios de las organizaciones federadas podrán ver la presencia de los demás y comunicarse por medio de la mensajería instantánea. Para obtener más información sobre cómo habilitar la comunicación con usuarios externos, vea [planificación de acceso a usuarios externos en Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) en la documentación de planeación.

</div>

<div>

## <a name="archiving-im-content"></a>Archivar contenido de mensajería instantánea

Lync Server proporciona características que puede usar si su organización debe seguir las normas de cumplimiento. Puede usar el servidor de archivado para archivar el contenido de los mensajes de MI de todos los usuarios de la organización, o solamente de algunos específicos. Para obtener más información, vea [planificación de archivado en Lync Server 2013](lync-server-2013-planning-for-archiving.md) en la documentación de planeación.

Si también ha implementado Microsoft Exchange Server 2013, puede integrar el archivado de datos de Exchange con el archivado de datos de Lync Server y usar una única herramienta para buscar en los dos tipos de datos archivados. Para obtener más información, vea [configurar Microsoft Lync server 2013 para usar el archivado de Microsoft Exchange server 2013](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

