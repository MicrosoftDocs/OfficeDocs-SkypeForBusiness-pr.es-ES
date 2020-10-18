---
title: 'Lync Server 2013: planear los certificados del servidor perimetral'
description: 'Lync Server 2013: planear los certificados del servidor perimetral.'
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
ms.openlocfilehash: 22ec3743256fe3e4c55dba0f6357a85b1ad81cd0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578196"
---
# <a name="plan-for-edge-server-certificates-in-lync-server-2013"></a>Planeación de certificados de servidor perimetral en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-05_

La creación de certificados para Edge se ha simplificado en Lync Server 2013.

**Diagrama de flujo de certificados para servidores perimetrales**

![a5fc20db-7ced-4364-b577-6a709a8367cd](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "a5fc20db-7ced-4364-b577-6a709a8367cd")

Cree un certificado público único, compruebe que tiene una clave privada exportable definida para el certificado y asígnela a las interfaces externas del servidor perimetral usando el asistente para certificados:

<div>


> [!IMPORTANT]  
> Los certificados comodín no son compatibles con Lync Server, excepto cuando se usan para resumir las direcciones URL sencillas a través del proxy inverso. Debe definir distintos nombres alternativos de sujeto (San) para cada nombre de dominio SIP, servicio perimetral de conferencia Web, servicio perimetral A/V y dominio XMPP ofrecido por la implementación.



</div>

<div>


> [!NOTE]  
> Presentada en Lync Server 2013, el almacenamiento provisional de certificados de autenticación de audio y vídeo antes de la fecha de expiración del certificado actual requiere una planificación adicional. En lugar de un certificado con varios propósitos para la interfaz perimetral externa, necesitará dos certificados, uno asignado al servicio perimetral de acceso y el servicio perimetral de conferencia Web, y un certificado para el servicio perimetral A/V. Para obtener más información, consulte staging de los <A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate">certificados AV y OAuth en Lync Server 2013 usando-Roll en Set-CsCertificate</A>



</div>

<div>


> [!IMPORTANT]  
> En el caso de un grupo de servidores perimetrales, exporte el certificado con la clave privada a cada servidor perimetral y asigne el certificado a cada servicio de servidor perimetral. Haga lo mismo con el certificado del servidor perimetral interno, exporte el certificado con la clave privada y asigne a cada interfaz perimetral interna.



</div>

  - Compruebe que se ha asignado la clave privada exportable al certificado

  - Servicio perimetral de acceso (denominado servidor **perimetral de acceso SIP externo** en el Asistente para certificados)

  - Servicio perimetral de conferencia web (denominado servidor **perimetral externo de conferencia web** en el Asistente para certificados)

  - Servicio de autenticación A/V (denominado **Servidor perimetral externo de A/V** en el asistente para certificados)

Cree un solo certificado interno con una clave privada exportable, cópielo y asígnelo a cada una de las siguientes interfaces internas de servidor perimetral:

  - Servidor perimetral (denominado **Servidor perimetral interno** en el asistente para certificados)

<div>


> [!IMPORTANT]  
> Es posible usar certificados separados y distintos para cada servicio de servidor perimetral. Una buena razón para elegir certificados separados es si desea usar la nueva característica de certificado rodante para el certificado del servicio perimetral A/V. En el caso de esta característica, se recomienda desacoplar el certificado del servicio perimetral A/V del servicio perimetral de acceso y del servicio perimetral de conferencia Web. Si elige solicitar, adquirir y asignar certificados independientes para cada servicio, debe solicitar que la clave privada sea exportable para el servicio perimetral A/V (de nuevo, esto es en realidad el servicio de autenticación A/V) y asignar el mismo certificado a la interfaz perimetral externa a/V en cada servidor perimetral.



</div>

<div>

## <a name="see-also"></a>Consulte también


[Almacenamiento provisional de certificados AV y OAuth en Lync Server 2013 usando-Roll en Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  


[Cambios en Lync Server 2013 que afectan a la planeación del servidor perimetral](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

