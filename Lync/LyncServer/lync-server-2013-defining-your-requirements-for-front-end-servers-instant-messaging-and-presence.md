---
title: 'Lync Server 2013: definición de los requisitos para los servidores front-end, la mensajería instantánea y la presencia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for Front End Servers, instant messaging, and presence
ms:assetid: c21198bc-520c-4d17-8b84-7ff1475b9b0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412956(v=OCS.15)
ms:contentKeyID: 48185319
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82cce58ab401149871073f6bc49ed4c53f301cb7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42032096"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>Definición de los requisitos para los servidores front-end, la mensajería instantánea y la presencia en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-10-07_

La tarea principal de la planeación de la mensajería instantánea (MI) y la presencia es comprobar que tenga suficientes servidores front-end para sus usuarios.

<div>

## <a name="enabling-communication-with-external-users"></a>Habilitación de la comunicación con usuarios externos

Puede aumentar en gran medida los beneficios de su inversión en Lync Server al permitir que los usuarios se comuniquen con usuarios externos. Entre los usuarios externos se pueden incluir:

  - **Usuarios remotos**   los propios usuarios de su organización, cuando trabajan fuera de los firewalls y están usando sus equipos portátiles u otros dispositivos de Lync Server.

  - **Usuarios federados**   usuarios de empresas con las que trabaja y que también ejecutan Lync Server. Para habilitar a sus usuarios para que se pongan en contacto fácilmente con estos usuarios, cree relaciones federadas con estas compañías.

  - **Usuarios públicos los**   usuarios de servicios de mensajería instantánea pública, como los servicios de mensajería instantánea proporcionados por la red de\!Windows Live de servicios de Internet, Yahoo y AOL, y los usuarios de proveedores y servidores que usan el protocolo extensible de mensajería y presencia (XMPP), como Google Talk.
    
    <div>
    

    > [!NOTE]  
    > Tenga en cuenta que quizás sea necesaria otra licencia para la conectividad de mensajería instantánea pública con Windows Live, AOL y Yahoo!.

    
    </div>
    
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

Para habilitar uno o todos estos escenarios, debe implementar un servidor perimetral que ayude a habilitar las comunicaciones seguras entre la implementación de Lync Server y los usuarios externos. Los usuarios remotos de su organización y los usuarios de organizaciones federadas podrán ver la presencia de los demás y comunicarse mediante MI. Para obtener información detallada sobre cómo habilitar la comunicación con usuarios externos, consulte [Planning for external User Access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) en la documentación de planeación.

</div>

<div>

## <a name="archiving-im-content"></a>Archivado del contenido de mensajería instantánea

Lync Server proporciona características que se pueden usar si la organización debe seguir las normas de cumplimiento. Puede usar el archivado para archivar el contenido de los mensajes de mensajería instantánea para todos los usuarios de la organización o solo para determinados usuarios que especifique. Para obtener más información, consulte [planeación del archivado en Lync Server 2013](lync-server-2013-planning-for-archiving.md) en la documentación de planeación.

Si también tiene implementado Microsoft Exchange Server 2013, puede integrar el archivado de datos de Exchange con el archivado de datos de Lync Server y usar una única herramienta para buscar en ambos tipos de datos archivados. Para obtener más información, consulte [configuración de Microsoft Lync server 2013 para usar el archivado de Microsoft Exchange server 2013](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

