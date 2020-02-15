---
title: Mensajería instantánea y presencia de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IM and presence
ms:assetid: 6a93ae95-3b64-410b-ab72-74dea232f065
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417162(v=OCS.15)
ms:contentKeyID: 48184398
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a7713f7b09602aed01ac20e5a76a361e04277a5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038782"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="im-and-presence-in-lync-server-2013"></a>Mensajería instantánea y presencia en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-10-07_

La mensajería instantánea (mi) y la presencia se instalan automáticamente en cualquier implementación de Lync Server.

La información de *Presencia* permite que los usuarios puedan dirigirse a sus colegas en el momento oportuno y usando el canal de comunicación adecuado y, así, lograr un entorno de trabajo más productivo. La presencia de los usuarios es una colección de información que incluye la disponibilidad, el deseo de comunicarse, otras notas (como la ubicación y el estado) y el modo de establecer contacto con el usuario. La presencia se ha mejorado en Lync Server con imágenes, información de ubicación y un amplio conjunto de Estados de presencia que incluye el trabajo "no laborable", "no molestar" y "volver atrás", además de los Estados básicos, como "disponible", "ocupado" y "en una conferencia". Los administradores también pueden definir estados de presencia personalizados o específicos de una organización.

Las opciones de administración de contactos y de acceso de usuarios permiten a los usuarios controlar la información que pueden ver los demás. Los usuarios pueden establecer varios niveles de contactos, que podrán ver diferentes niveles de información de presencia.

Con solo mirar la lista de contactos, los usuarios podrán encontrar de inmediato todo lo que necesiten. Unos iconos sencillos de colores indican el estado de presencia de otros usuarios, y además aparecen la foto y la ubicación.

Con la integración entre Lync Server y otros productos como Outlook y SharePoint, siempre que aparezca el nombre de un contacto, como en un mensaje de correo electrónico o en un sitio web de grupo, también se muestra el estado y la información de contacto. Además, si implementa Exchange 2013, Lync Server y Exchange 2013 pueden compartir un almacén de contactos unificado, al que pueden tener acceso los clientes de ambos productos.

Con la mensajería instantánea en Lync Server, los usuarios pueden crear mensajes rápidamente entre sí con información oportuna. Si lo prefiere, los usuarios también pueden comunicarse con usuarios de redes de mensajería instantánea pública, como MSN/Windows Live\!, Yahoo y AOL. Tenga en cuenta que es posible que se requiera una licencia independiente para la conectividad de mensajería instantánea pública con Windows Live, AOL y Yahoo\! Lync Server también incluye compatibilidad con el protocolo extensible de mensajería y presencia (XMPP), por lo que los usuarios pueden intercambiar mensajes INSTANTÁNEos e información de presencia con usuarios de servicios XMPP, como Google Talk.

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

El historial de la conversación permite que los usuarios mantengan un registro de las conversaciones de mensajería instantánea antiguas, y que puedan recuperar información que hayan enviado mediante mensajería instantánea hace meses.

La característica chat persistente permite a los usuarios participar en conversaciones basadas en temas con varios participantes que persisten a lo largo del tiempo. Los mensajes enviados a los salones de chat (foros de discusión) pueden ser persistentes (esto es, disponibles en el tiempo) para que las personas en diferentes ubicaciones y departamentos puedan participar, incluso cuando no están todos en línea al mismo tiempo.

Si su organización debe seguir normativas de cumplimiento, puede implementar una característica de archivado de mensajes para almacenar el contenido de los mensajes instantáneos de todos los usuarios de su organización, o solo de algunos usuarios que se especifiquen. Si también implementa Exchange 2013, el archivo de mensajería instantánea se puede integrar con la característica de conservación local de Exchange, para proporcionar una única experiencia de administración para el cumplimiento.

</div>

<span> </span>

</div>

</div>

</div>

