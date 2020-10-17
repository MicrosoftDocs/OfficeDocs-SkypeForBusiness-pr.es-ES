---
title: 'Lync Server 2013: compatibilidad con mensajería instantánea pública'
description: 'Lync Server 2013: compatibilidad con mensajería instantánea pública.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Public instant messaging support
ms:assetid: 1f45163b-52c6-4a78-b9c8-dfe3abe4e5eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204732(v=OCS.15)
ms:contentKeyID: 48183582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e071e8b79be82d865a85a9488e48dd0a4264c7f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565576"
---
# <a name="public-instant-messaging-support-in-lync-server-2013"></a>Compatibilidad con mensajería instantánea pública en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-10-07_

Lync Server 2013 admite el uso de proveedores de conectividad de mensajería instantánea pública con licencia (mi), así como el uso del protocolo extensible de mensajería y presencia (XMPP) para implementar un tipo especial de Federación que permite que Lync Server obtenga acceso a asociados de dominio XMPP configurados mediante el cliente de Lync 2013.

<div>

## <a name="public-im-connectivity-provider-support"></a>Soporte de proveedor de conectividad de mensajería instantánea pública

Los socios de conectividad de mensajería instantánea pública admitidos actualmente son:

  - America Online

  - Windows Live

  - Toolbar\!

Para las comunicaciones con los usuarios de Windows Live, Lync Server 2013 admite la mensajería instantánea de punto a punto y las llamadas de audio y vídeo. Para las comunicaciones con AOL y Yahoo \! , Lync Server 2013 admite la mensajería instantánea punto a punto. Podrá exigirse una licencia independiente.

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

</div>

<div>

## <a name="xmpp-federation-support"></a>Compatibilidad con la federación XMPP

La federación XMPP admite la comunicación de los usuarios de Lync con usuarios del dominio XMPP configurados que usan un proveedor público, como GTalk. Las comunicaciones con estos usuarios pueden incluir lo siguiente:

  - Presencia y mensajería instantánea punto a punto

  - Creación de contactos federados XMPP en el cliente de Lync

</div>

</div>

<span> </span>

</div>

</div>

</div>

