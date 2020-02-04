---
title: 'Lync Server 2013: Plan para certificados de servidores perimetrales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Plan for Edge Server certificates
ms:assetid: f1dfe220-2398-4ac8-ba4c-206c8c0cbc50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413010(v=OCS.15)
ms:contentKeyID: 48185798
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: faad6dba610df8033b75b0c87c52fbb065dc5dcb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755180"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="plan-for-edge-server-certificates-in-lync-server-2013"></a>Plan para certificados de servidores perimetrales en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-05_

La creación de certificados para Edge se ha simplificado en Lync Server 2013.

**Diagrama de flujo de certificados para el servidor perimetral**

![a5fc20db-7ced-4364-b577-6a709a8367cd](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "a5fc20db-7ced-4364-b577-6a709a8367cd")

Cree un único certificado público, asegúrese de que tiene una clave privada exportable definida para el certificado y asígnela a las siguientes interfaces externas de servidor perimetral con el Asistente para certificados:

<div>


> [!IMPORTANT]  
> Los certificados comodín no se admiten en Lync Server, excepto cuando se usan para resumir las direcciones URL simples a través del proxy inverso. Debe definir distintos nombres alternativos de sujeto (San) para cada nombre de dominio SIP, servicio perimetral de conferencias web, servicio perimetral A/V y dominio XMPP ofrecido por su implementación.



</div>

<div>


> [!NOTE]  
> Introducida en Lync Server 2013, el almacenamiento provisional de certificados de autenticación de audio y vídeo con antelación a la fecha de expiración del certificado actual requiere una planificación adicional. En lugar de un certificado con varios propósitos para la interfaz de borde externo, necesitará dos certificados, uno asignado al servicio perimetral de acceso y el servicio perimetral de conferencia Web, y un certificado para el servicio perimetral de a/V. Para obtener más información, consulte <A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate">almacenamiento provisional de certificados AV y OAuth en Lync Server 2013 uso de-roll en Set-CsCertificate</A>



</div>

<div>


> [!IMPORTANT]  
> En el caso de un grupo de servidores perimetrales, exporte el certificado con la clave privada a cada servidor perimetral y asigne el certificado a cada servicio de servidor perimetral. Haga lo mismo para el certificado de servidor perimetral interno, exporte el certificado con la clave privada y asignándole la asignación a cada interfaz de borde interno.



</div>

  - Asegúrese de que tiene asignada una clave privada exportable para el certificado

  - Servicio perimetral de acceso (denominado **SIP perimetral de acceso externo** en el Asistente para certificados)

  - Servicio perimetral de conferencias web (denominado **borde de conferencias web externo** en el Asistente para certificados)

  - Servicio de autenticación a/V (denominado **borde a/v externo** en el Asistente para certificados)

Crear un único certificado interno con una clave privada exportable, cópielo y asígnelo a cada una de las interfaces internas del servidor perimetral:

  - Servidor perimetral (denominado interno de la **arista** en el Asistente para certificados)

<div>


> [!IMPORTANT]  
> Es posible usar certificados diferentes y diferentes para cada servicio de servidor perimetral. Una buena razón para elegir certificados independientes es si desea usar la nueva característica de certificados sucesivos para el certificado de servicio perimetral A/V. En el caso de esta característica, se recomienda disociar el certificado de servicio perimetral A/V del servicio perimetral de acceso y el servicio perimetral de conferencia Web. Si elige solicitar, adquirir y asignar certificados independientes para cada servicio, debe solicitar que la clave privada sea exportable para el servicio perimetral de A/V (de nuevo, esto es en realidad el servicio de autenticación A/V) y asignar el mismo certificado a la interfaz externa perimetral de A/V en cada servidor perimetral.



</div>

<div>

## <a name="see-also"></a>Vea también


[Almacenamiento provisional de certificados AV y OAuth en Lync Server 2013 usar-Roll en Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  


[Cambios en Lync Server 2013 que afectan a la planificación del servidor perimetral](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

