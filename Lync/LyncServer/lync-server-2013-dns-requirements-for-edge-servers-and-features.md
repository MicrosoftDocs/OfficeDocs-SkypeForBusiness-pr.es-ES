---
title: 'Lync Server 2013: requisitos de DNS para servidores perimetrales y características'
description: 'Lync Server 2013: requisitos de DNS para servidores perimetrales y características.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Edge Servers and features
ms:assetid: e3bf05c8-96fb-4dd2-acb1-f0d141c9e2ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721912(v=OCS.15)
ms:contentKeyID: 49733846
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9bcfd00080e765924eecc3138bc3d552ce331b63
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574396"
---
# <a name="dns-requirements-for-edge-servers-and-features-in-lync-server-2013"></a><span data-ttu-id="86b4b-103">Requisitos de DNS para servidores perimetrales y características en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86b4b-103">DNS requirements for Edge Servers and features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86b4b-104">_**Última modificación del tema:** 2014-04-08_</span><span class="sxs-lookup"><span data-stu-id="86b4b-104">_**Topic Last Modified:** 2014-04-08_</span></span>

<span data-ttu-id="86b4b-105">Lync Server 2013 los servidores perimetrales, los grupos de servidores perimetrales y los proxies inversos tienen requisitos específicos para los registros del sistema de nombres de dominio (DNS).</span><span class="sxs-lookup"><span data-stu-id="86b4b-105">Lync Server 2013 Edge Servers, Edge pools, and reverse proxies have specific requirements for Domain Name System (DNS) records.</span></span> <span data-ttu-id="86b4b-106">En Lync Server 2013, cuando están en uso IPv4 e IPv6, debe planear los registros A y AAAA del host.</span><span class="sxs-lookup"><span data-stu-id="86b4b-106">In Lync Server 2013 when IPv4 and IPv6 are in use, you must plan for both host A and AAAA records.</span></span>

<span data-ttu-id="86b4b-107">Los temas enumerados a continuación definen el uso de registros DNS para la planeación de implementación:</span><span class="sxs-lookup"><span data-stu-id="86b4b-107">The topics listed below define the use of DNS records for your deployment planning:</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="86b4b-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="86b4b-108">In This Section</span></span>

  - [<span data-ttu-id="86b4b-109">Resumen de DNS-servidor perimetral consolidado único con direcciones IP privadas que usan NAT en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86b4b-109">DNS summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-dns-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="86b4b-110">Resumen de DNS-servidor perimetral consolidado único con direcciones IP públicas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86b4b-110">DNS summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-dns-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="86b4b-111">Resumen de DNS-servidor perimetral consolidado ampliado, equilibrio de carga de DNS con direcciones IP privadas mediante NAT en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86b4b-111">DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="86b4b-112">Resumen de DNS-servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP públicas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86b4b-112">DNS summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="86b4b-113">Resumen de DNS-servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86b4b-113">DNS summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [<span data-ttu-id="86b4b-114">Resumen de DNS-proxy inverso en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86b4b-114">DNS summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-dns-summary-reverse-proxy.md)

  - [<span data-ttu-id="86b4b-115">Resumen de DNS: SIP, Federación XMPP y mensajería instantánea pública en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86b4b-115">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

