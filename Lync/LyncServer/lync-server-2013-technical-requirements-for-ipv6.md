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

# <a name="technical-requirements-for-ipv6-in-lync-server-2013"></a><span data-ttu-id="c1a9f-102">Requisitos técnicos para IPv6 en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1a9f-102">Technical requirements for IPv6 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1a9f-103">_**Última modificación del tema:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="c1a9f-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="c1a9f-104">Si tiene previsto configurar Lync Server 2013 para IPv6, tenga en cuenta los siguientes requisitos:</span><span class="sxs-lookup"><span data-stu-id="c1a9f-104">If you plan to configure Lync Server 2013 for IPv6, keep the following requirements in mind:</span></span>

  - <span data-ttu-id="c1a9f-105">Para usar las direcciones IPv6 con Lync Server, debe crear registros del sistema de nombres de dominio (DNS) para los registros que se deben detectar y resolver en una dirección IPv6.</span><span class="sxs-lookup"><span data-stu-id="c1a9f-105">To use IPv6 addresses with Lync Server, you need to create domain name system (DNS) records for records that must be discovered and resolved to an IPv6 address.</span></span> <span data-ttu-id="c1a9f-106">El DNS de IPv6 usa registros AAAA de host (A cuádruple).</span><span class="sxs-lookup"><span data-stu-id="c1a9f-106">IPv6 DNS uses host AAAA (quad-A) records.</span></span> <span data-ttu-id="c1a9f-107">Si usa IPv4 e IPv6 en la implementación, es mejor configurar y guardar los registros A de host para IPv4 y los registros AAAA de host para IPv6.</span><span class="sxs-lookup"><span data-stu-id="c1a9f-107">If you use both IPv4 and IPv6 in your deployment, it is best to configure and maintain both host A records for IPv4 and host AAAA records for IPv6.</span></span> <span data-ttu-id="c1a9f-108">Aun cuando pase completamente la implementación a IPv6, pueden ser necesarios registros de host DNS IPv4 para los usuarios externos que todavía usen IPv4.</span><span class="sxs-lookup"><span data-stu-id="c1a9f-108">Even when you fully transition your deployment to IPv6, you may still require IPv4 DNS host records for external users who still use IPv4.</span></span>
    
    <span data-ttu-id="c1a9f-p102">Puede implementar los registros de host DNS IPv6 antes de empezar a usar IPv6. Si el cliente o el servidor no usan IPv6, el registro no será referenciado. Las tecnologías de transición decidirán qué registro usar, sobre la base de las directivas y la configuración de la tecnología de transición.</span><span class="sxs-lookup"><span data-stu-id="c1a9f-p102">You can deploy IPv6 DNS host records before you start using IPv6. If the client or server doesn't use IPv6, the record will not be referenced. Transitional technologies will make the decision about which record to use, based on transition technology configuration and policies.</span></span>

  - <span data-ttu-id="c1a9f-112">Cada dirección de IPv6 tiene un ámbito.</span><span class="sxs-lookup"><span data-stu-id="c1a9f-112">Each IPv6 address has a scope.</span></span> <span data-ttu-id="c1a9f-113">Los tres ámbitos que puede usar para el direccionamiento IPv6 son direcciones globales de IPv6 (similares a las direcciones IPv4 públicas), direcciones locales IPv6 únicas (similares a los intervalos de direcciones IPv4 privadas) y direcciones locales del vínculo IPv6 (similares a las direcciones IP privadas automáticas de Windows Server para IPv4).</span><span class="sxs-lookup"><span data-stu-id="c1a9f-113">The three scopes that you can use for IPv6 addressing are IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges), and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4).</span></span> <span data-ttu-id="c1a9f-114">Todos los servidores de un grupo necesitan tener direcciones IPv6 con el mismo ámbito.</span><span class="sxs-lookup"><span data-stu-id="c1a9f-114">All the servers within a pool should have IPv6 addresses with the same scope.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c1a9f-115">IPv6 es un tema complejo y requiere un cuidadoso planeamiento con el equipo de redes y el proveedor de Internet para garantizar que las direcciones que asigne en el nivel de servidor de Windows y en el nivel de 2013 de Lync Server funcionen de la manera esperada.</span><span class="sxs-lookup"><span data-stu-id="c1a9f-115">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to help ensure that the addresses that you assign at the Windows Server level and at the Lync Server 2013 level work as expected.</span></span> <span data-ttu-id="c1a9f-116">Vea los vínculos del final de este tema para conocer otros recursos sobre la planeación y el direccionamiento de IPv6.</span><span class="sxs-lookup"><span data-stu-id="c1a9f-116">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c1a9f-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1a9f-117">See Also</span></span>


[<span data-ttu-id="c1a9f-118">Arquitectura de direccionamiento de IP versión 6</span><span class="sxs-lookup"><span data-stu-id="c1a9f-118">IP Version 6 Addressing Architecture</span></span>](http://tools.ietf.org/html/rfc4291)  
[<span data-ttu-id="c1a9f-119">Formato de dirección global de unidifusión IPv6</span><span class="sxs-lookup"><span data-stu-id="c1a9f-119">IPv6 Global Unicast Address Format</span></span>](http://tools.ietf.org/html/rfc3587)  
[<span data-ttu-id="c1a9f-120">Direcciones de unidifusión IPv6 locales únicas</span><span class="sxs-lookup"><span data-stu-id="c1a9f-120">Unique Local IPv6 Unicast Addresses</span></span>](http://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

