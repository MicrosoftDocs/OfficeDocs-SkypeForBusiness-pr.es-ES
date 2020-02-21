---
title: 'Lync Server 2013: Planeación de la conectividad de mensajería instantánea pública'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for public instant messaging connectivity
ms:assetid: e75e8884-05c7-414a-8014-bc9aa8126fb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205349(v=OCS.15)
ms:contentKeyID: 48185698
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52bc8a563a45e75b01932ee716df90f1cf2ca7da
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201976"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-public-instant-messaging-connectivity-in-lync-server-2013"></a>Planeación de la conectividad de mensajería instantánea pública en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-10-07_

La conectividad de mensajería instantánea pública es una clase de Federación y está configurada para permitir que los usuarios internos y externos de Lync Server 2013 puedan agregar contactos desde cualquiera de las siguientes opciones:

  - Contactos de Messenger

  - Toolbar\! contacts

  - Contactos de America Online (AOL)

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>A partir del 1 de septiembre de 2012, la licencia de suscripción de usuario de la conectividad de mensajería instantánea pública de Microsoft Lync (PIC USL) ya no está disponible para la compra de contratos nuevos o de renovación. Los clientes con licencias activas podrán seguir federando a Yahoo! Messenger hasta la fecha de cierre del servicio. Una fecha de finalización del ciclo de vida de junio de 2014 para AOL y Yahoo! se ha anunciado. Para obtener más información, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">compatibilidad con la conectividad de mensajería instantánea pública en Lync Server 2013</A>.</P>
> <LI>
> <P>La capa de PIC es una licencia por usuario, por mes, que es necesaria para que Lync Server u Office Communications Server se federe con Yahoo! Service. La capacidad de Microsoft para proporcionar este servicio ha estado supeditada al soporte de Yahoo!, el acuerdo subyacente que no se renovará.</P>
> <LI>
> <P>Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo. La Federación con Windows Live Messenger no requiere licencias de usuario o de dispositivo adicionales aparte de la CAL de Lync Standard. La Federación de Skype se agregará a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas a través de mensajería instantánea y voz.</P></LI></UL>



</div>

Esta clase de federación requiere las siguientes consideraciones de planificación:

  - Los usuarios de Windows Live Messenger pueden tener comunicación de audio/visual de punto a punto con los usuarios de Lync Server 2013, además de la mensajería instantánea. Los servidores perimetrales deben cumplir unos requisitos de puerto y protocolo específicos. Para obtener más información, consulte [determinación de requisitos de firewall y de puerto a/V externos para Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).

  - La mensajería instantánea de Yahoo no tiene requisitos únicos, excepto los que se usan normalmente en la planeación y la implementación del servidor perimetral típico que proporciona la Federación.

  - America Online requiere que el certificado del servidor perimetral asignado al servicio perimetral de acceso tenga un uso mejorado de clave (EKU) de cliente.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Resumen de certificado-conectividad de mensajería instantánea pública en Lync Server 2013](lync-server-2013-certificate-summary-public-instant-messaging-connectivity.md)

  - [Resumen de Puerto-conectividad de mensajería instantánea pública en Lync Server 2013](lync-server-2013-port-summary-public-instant-messaging-connectivity.md)

  - [Resumen de DNS-conectividad de mensajería instantánea pública en Lync Server 2013](https://technet.microsoft.com/library/jj618375\(v=ocs.15\))

</div>

</div>

<span> </span>

</div>

</div>

</div>

