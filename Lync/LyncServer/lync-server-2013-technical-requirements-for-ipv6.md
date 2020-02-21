---
title: Lync Server 2013 requisitos técnicos para IPv6
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for IPv6
ms:assetid: caff0123-ce41-4a62-87a0-00b1d118b72b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205278(v=OCS.15)
ms:contentKeyID: 48185465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a5565080f2b5fab0f47cc944f9569f55e8721c4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194893"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-ipv6-in-lync-server-2013"></a>Requisitos técnicos para IPv6 en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-30_

Si tiene previsto configurar Lync Server 2013 para IPv6, tenga en cuenta los siguientes requisitos:

  - Para usar direcciones IPv6 con Lync Server, tiene que crear registros de sistema de nombres de dominio (DNS) para los registros que deben detectarse y resolverse en una dirección IPv6. El DNS de IPv6 usa registros AAAA de host (A cuádruple). Si usa IPv4 e IPv6 en la implementación, es mejor configurar y guardar los registros A de host para IPv4 y los registros AAAA de host para IPv6. Aun cuando pase completamente la implementación a IPv6, pueden ser necesarios registros de host DNS IPv4 para los usuarios externos que todavía usen IPv4.
    
    Puede implementar los registros de host DNS IPv6 antes de empezar a usar IPv6. Si el cliente o el servidor no usan IPv6, el registro no será referenciado. Las tecnologías de transición tomarán la decisión sobre qué registro usar, sobre la base de las directivas y la configuración de la tecnología de transición.

  - Cada dirección de IPv6 tiene un ámbito. Los tres ámbitos que puede usar para el direccionamiento IPv6 son direcciones IPv6 globales (similares a las direcciones IPv4 públicas), direcciones IPv6 locales únicas (similares a los intervalos de direcciones IPv4 privadas) y direcciones IPv6 de vínculo local (similares a las direcciones IP privadas automáticas en Windows Server para IPv4). Todos los servidores de un grupo deben tener direcciones IPv6 con el mismo ámbito.

<div>


> [!IMPORTANT]  
> IPv6 es un tema complejo y requiere una planificación minuciosa con el equipo de red y el proveedor de Internet para ayudar a garantizar que las direcciones que asigne en el nivel de Windows Server y en el nivel de 2013 de Lync Server funcionen según lo previsto. Consulte los vínculos al final de este tema para ver más recursos sobre la planeación y el direccionamiento de IPv6.



</div>

<div>

## <a name="see-also"></a>Consulta también


[Arquitectura de direcciones de IP versión 6](https://tools.ietf.org/html/rfc4291)  
[Formato de dirección de unidifusión global IPv6](https://tools.ietf.org/html/rfc3587)  
[Direcciones de unidifusión IPv6 locales únicas](https://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

