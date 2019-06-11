---
title: 'Lync Server 2013: Requisitos técnicos para IPv6'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for IPv6
ms:assetid: caff0123-ce41-4a62-87a0-00b1d118b72b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205278(v=OCS.15)
ms:contentKeyID: 48185465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 972b59ba2ea01f967d5cfb8a7767a4f322bcb2fd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850441"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-ipv6-in-lync-server-2013"></a>Requisitos técnicos para IPv6 en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-30_

Si tiene previsto configurar Lync Server 2013 para IPv6, tenga en cuenta los siguientes requisitos:

  - Para usar las direcciones IPv6 con Lync Server, debe crear registros del sistema de nombres de dominio (DNS) para los registros que se deben detectar y resolver en una dirección IPv6. El DNS de IPv6 usa registros AAAA de host (A cuádruple). Si usa IPv4 e IPv6 en la implementación, es mejor configurar y guardar los registros A de host para IPv4 y los registros AAAA de host para IPv6. Aun cuando pase completamente la implementación a IPv6, pueden ser necesarios registros de host DNS IPv4 para los usuarios externos que todavía usen IPv4.
    
    Puede implementar los registros de host DNS IPv6 antes de empezar a usar IPv6. Si el cliente o el servidor no usan IPv6, el registro no será referenciado. Las tecnologías de transición decidirán qué registro usar, sobre la base de las directivas y la configuración de la tecnología de transición.

  - Cada dirección de IPv6 tiene un ámbito. Los tres ámbitos que puede usar para el direccionamiento IPv6 son direcciones globales de IPv6 (similares a las direcciones IPv4 públicas), direcciones locales IPv6 únicas (similares a los intervalos de direcciones IPv4 privadas) y direcciones locales del vínculo IPv6 (similares a las direcciones IP privadas automáticas de Windows Server para IPv4). Todos los servidores de un grupo necesitan tener direcciones IPv6 con el mismo ámbito.

<div>


> [!IMPORTANT]  
> IPv6 es un tema complejo y requiere un cuidadoso planeamiento con el equipo de redes y el proveedor de Internet para garantizar que las direcciones que asigne en el nivel de servidor de Windows y en el nivel de 2013 de Lync Server funcionen de la manera esperada. Vea los vínculos del final de este tema para conocer otros recursos sobre la planeación y el direccionamiento de IPv6.



</div>

<div>

## <a name="see-also"></a>Vea también


[Arquitectura de direccionamiento de IP versión 6](http://tools.ietf.org/html/rfc4291)  
[Formato de dirección global de unidifusión IPv6](http://tools.ietf.org/html/rfc3587)  
[Direcciones de unidifusión IPv6 locales únicas](http://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

