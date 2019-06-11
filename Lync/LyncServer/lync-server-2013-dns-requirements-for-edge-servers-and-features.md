---
title: 'Lync Server 2013: requisitos de DNS para servidores perimetrales y características'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for Edge Servers and features
ms:assetid: e3bf05c8-96fb-4dd2-acb1-f0d141c9e2ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721912(v=OCS.15)
ms:contentKeyID: 49733846
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18c5069e82da9d063cc19e230db7503cd1bc640e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835370"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-edge-servers-and-features-in-lync-server-2013"></a><span data-ttu-id="12d35-102">Requisitos de DNS para los servidores perimetrales y las características de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12d35-102">DNS requirements for Edge Servers and features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12d35-103">_**Última modificación del tema:** 2014-04-08_</span><span class="sxs-lookup"><span data-stu-id="12d35-103">_**Topic Last Modified:** 2014-04-08_</span></span>

<span data-ttu-id="12d35-104">Los servidores perimetrales de Lync Server 2013, los grupos perimetrales y los proxies inversos tienen requisitos específicos para los registros del sistema de nombres de dominio (DNS).</span><span class="sxs-lookup"><span data-stu-id="12d35-104">Lync Server 2013 Edge Servers, Edge pools, and reverse proxies have specific requirements for Domain Name System (DNS) records.</span></span> <span data-ttu-id="12d35-105">En Lync Server 2013 cuando se usan IPv4 e IPv6, debe planear los registros A y AAAA del host.</span><span class="sxs-lookup"><span data-stu-id="12d35-105">In Lync Server 2013 when IPv4 and IPv6 are in use, you must plan for both host A and AAAA records.</span></span>

<span data-ttu-id="12d35-106">Los temas siguientes definen el uso de registros DNS para la planificación de su implementación:</span><span class="sxs-lookup"><span data-stu-id="12d35-106">The topics listed below define the use of DNS records for your deployment planning:</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="12d35-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="12d35-107">In This Section</span></span>

  - [<span data-ttu-id="12d35-108">Resumen DNS - Servidor perimetral consolidado simple con dirección IP privada mediante NAT en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12d35-108">DNS summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-dns-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="12d35-109">Resumen DNS - Servidor perimetral consolidado simple con direcciones IP públicas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12d35-109">DNS summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-dns-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="12d35-110">Resumen de DNS - Topologías perimetrales consolidadas escaladas, equilibrio de carga DNS con direcciones IP privadas con NAT en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12d35-110">DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="12d35-111">Resumen de DNS - Servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP públicas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12d35-111">DNS summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="12d35-112">Resumen DNS - Servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12d35-112">DNS summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [<span data-ttu-id="12d35-113">Resumen DNS - Proxy inverso en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12d35-113">DNS summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-dns-summary-reverse-proxy.md)

  - [<span data-ttu-id="12d35-114">Resumen DNS: SIP, Federación XMPP y mensajería instantánea pública en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12d35-114">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

