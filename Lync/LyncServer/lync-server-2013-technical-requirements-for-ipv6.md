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
ms.openlocfilehash: 88e0d822e14ea1792751338bd3606766cc98ab96
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006706"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-ipv6-in-lync-server-2013"></a><span data-ttu-id="f19e9-102">Requisitos técnicos para IPv6 en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f19e9-102">Technical requirements for IPv6 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f19e9-103">_**Última modificación del tema:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="f19e9-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="f19e9-104">Si tiene previsto configurar Lync Server 2013 para IPv6, tenga en cuenta los siguientes requisitos:</span><span class="sxs-lookup"><span data-stu-id="f19e9-104">If you plan to configure Lync Server 2013 for IPv6, keep the following requirements in mind:</span></span>

  - <span data-ttu-id="f19e9-105">Para usar direcciones IPv6 con Lync Server, tiene que crear registros de sistema de nombres de dominio (DNS) para los registros que deben detectarse y resolverse en una dirección IPv6.</span><span class="sxs-lookup"><span data-stu-id="f19e9-105">To use IPv6 addresses with Lync Server, you need to create domain name system (DNS) records for records that must be discovered and resolved to an IPv6 address.</span></span> <span data-ttu-id="f19e9-106">El DNS de IPv6 usa registros AAAA de host (A cuádruple).</span><span class="sxs-lookup"><span data-stu-id="f19e9-106">IPv6 DNS uses host AAAA (quad-A) records.</span></span> <span data-ttu-id="f19e9-107">Si usa IPv4 e IPv6 en la implementación, es mejor configurar y guardar los registros A de host para IPv4 y los registros AAAA de host para IPv6.</span><span class="sxs-lookup"><span data-stu-id="f19e9-107">If you use both IPv4 and IPv6 in your deployment, it is best to configure and maintain both host A records for IPv4 and host AAAA records for IPv6.</span></span> <span data-ttu-id="f19e9-108">Aun cuando pase completamente la implementación a IPv6, pueden ser necesarios registros de host DNS IPv4 para los usuarios externos que todavía usen IPv4.</span><span class="sxs-lookup"><span data-stu-id="f19e9-108">Even when you fully transition your deployment to IPv6, you may still require IPv4 DNS host records for external users who still use IPv4.</span></span>
    
    <span data-ttu-id="f19e9-109">Puede implementar los registros de host DNS IPv6 antes de empezar a usar IPv6.</span><span class="sxs-lookup"><span data-stu-id="f19e9-109">You can deploy IPv6 DNS host records before you start using IPv6.</span></span> <span data-ttu-id="f19e9-110">Si el cliente o el servidor no usan IPv6, el registro no será referenciado.</span><span class="sxs-lookup"><span data-stu-id="f19e9-110">If the client or server doesn't use IPv6, the record will not be referenced.</span></span> <span data-ttu-id="f19e9-111">Las tecnologías de transición tomarán la decisión sobre qué registro usar, sobre la base de las directivas y la configuración de la tecnología de transición.</span><span class="sxs-lookup"><span data-stu-id="f19e9-111">Transitional technologies will make the decision about which record to use, based on transition technology configuration and policies.</span></span>

  - <span data-ttu-id="f19e9-112">Cada dirección de IPv6 tiene un ámbito.</span><span class="sxs-lookup"><span data-stu-id="f19e9-112">Each IPv6 address has a scope.</span></span> <span data-ttu-id="f19e9-113">Los tres ámbitos que puede usar para el direccionamiento IPv6 son direcciones IPv6 globales (similares a las direcciones IPv4 públicas), direcciones IPv6 locales únicas (similares a los intervalos de direcciones IPv4 privadas) y direcciones IPv6 de vínculo local (similares a las direcciones IP privadas automáticas en Windows Server para IPv4).</span><span class="sxs-lookup"><span data-stu-id="f19e9-113">The three scopes that you can use for IPv6 addressing are IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges), and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4).</span></span> <span data-ttu-id="f19e9-114">Todos los servidores de un grupo deben tener direcciones IPv6 con el mismo ámbito.</span><span class="sxs-lookup"><span data-stu-id="f19e9-114">All the servers within a pool should have IPv6 addresses with the same scope.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f19e9-115">IPv6 es un tema complejo y requiere una planificación minuciosa con el equipo de red y el proveedor de Internet para ayudar a garantizar que las direcciones que asigne en el nivel de Windows Server y en el nivel de 2013 de Lync Server funcionen según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="f19e9-115">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to help ensure that the addresses that you assign at the Windows Server level and at the Lync Server 2013 level work as expected.</span></span> <span data-ttu-id="f19e9-116">Consulte los vínculos al final de este tema para ver más recursos sobre la planeación y el direccionamiento de IPv6.</span><span class="sxs-lookup"><span data-stu-id="f19e9-116">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f19e9-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="f19e9-117">See Also</span></span>


[<span data-ttu-id="f19e9-118">Arquitectura de direcciones de IP versión 6</span><span class="sxs-lookup"><span data-stu-id="f19e9-118">IP Version 6 Addressing Architecture</span></span>](http://tools.ietf.org/html/rfc4291)  
[<span data-ttu-id="f19e9-119">Formato de dirección de unidifusión global IPv6</span><span class="sxs-lookup"><span data-stu-id="f19e9-119">IPv6 Global Unicast Address Format</span></span>](http://tools.ietf.org/html/rfc3587)  
[<span data-ttu-id="f19e9-120">Direcciones de unidifusión IPv6 locales únicas</span><span class="sxs-lookup"><span data-stu-id="f19e9-120">Unique Local IPv6 Unicast Addresses</span></span>](http://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

