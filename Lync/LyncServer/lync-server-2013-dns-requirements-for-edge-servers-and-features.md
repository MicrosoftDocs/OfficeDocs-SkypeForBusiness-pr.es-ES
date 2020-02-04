---
title: 'Lync Server 2013: requisitos de DNS para servidores perimetrales y características'
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
ms.openlocfilehash: 9e9f0cb2eb68ed29984811f1c42a97dab4693a2f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739150"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-edge-servers-and-features-in-lync-server-2013"></a><span data-ttu-id="c1e2f-102">Requisitos de DNS para los servidores perimetrales y las características de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1e2f-102">DNS requirements for Edge Servers and features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1e2f-103">_**Última modificación del tema:** 2014-04-08_</span><span class="sxs-lookup"><span data-stu-id="c1e2f-103">_**Topic Last Modified:** 2014-04-08_</span></span>

<span data-ttu-id="c1e2f-104">Los servidores perimetrales de Lync Server 2013, los grupos perimetrales y los proxies inversos tienen requisitos específicos para los registros del sistema de nombres de dominio (DNS).</span><span class="sxs-lookup"><span data-stu-id="c1e2f-104">Lync Server 2013 Edge Servers, Edge pools, and reverse proxies have specific requirements for Domain Name System (DNS) records.</span></span> <span data-ttu-id="c1e2f-105">En Lync Server 2013 cuando se usan IPv4 e IPv6, debe planear los registros A y AAAA del host.</span><span class="sxs-lookup"><span data-stu-id="c1e2f-105">In Lync Server 2013 when IPv4 and IPv6 are in use, you must plan for both host A and AAAA records.</span></span>

<span data-ttu-id="c1e2f-106">Los temas siguientes definen el uso de registros DNS para la planificación de su implementación:</span><span class="sxs-lookup"><span data-stu-id="c1e2f-106">The topics listed below define the use of DNS records for your deployment planning:</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c1e2f-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c1e2f-107">In This Section</span></span>

  - [<span data-ttu-id="c1e2f-108">Resumen DNS - Servidor perimetral consolidado simple con dirección IP privada mediante NAT en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1e2f-108">DNS summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-dns-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="c1e2f-109">Resumen DNS - Servidor perimetral consolidado simple con direcciones IP públicas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1e2f-109">DNS summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-dns-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="c1e2f-110">Resumen de DNS - Topologías perimetrales consolidadas escaladas, equilibrio de carga DNS con direcciones IP privadas con NAT en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1e2f-110">DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="c1e2f-111">Resumen de DNS - Servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP públicas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1e2f-111">DNS summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="c1e2f-112">Resumen DNS - Servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1e2f-112">DNS summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [<span data-ttu-id="c1e2f-113">Resumen DNS - Proxy inverso en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1e2f-113">DNS summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-dns-summary-reverse-proxy.md)

  - [<span data-ttu-id="c1e2f-114">Resumen DNS: SIP, Federación XMPP y mensajería instantánea pública en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1e2f-114">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

