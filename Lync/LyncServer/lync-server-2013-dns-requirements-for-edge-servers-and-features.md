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
ms.openlocfilehash: 23927c5ee6682622d9a23befd384b1bdf1e2b9b0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214656"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-edge-servers-and-features-in-lync-server-2013"></a><span data-ttu-id="b2ee9-102">Requisitos de DNS para servidores perimetrales y características en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2ee9-102">DNS requirements for Edge Servers and features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2ee9-103">_**Última modificación del tema:** 2014-04-08_</span><span class="sxs-lookup"><span data-stu-id="b2ee9-103">_**Topic Last Modified:** 2014-04-08_</span></span>

<span data-ttu-id="b2ee9-104">Lync Server 2013 los servidores perimetrales, los grupos de servidores perimetrales y los proxies inversos tienen requisitos específicos para los registros del sistema de nombres de dominio (DNS).</span><span class="sxs-lookup"><span data-stu-id="b2ee9-104">Lync Server 2013 Edge Servers, Edge pools, and reverse proxies have specific requirements for Domain Name System (DNS) records.</span></span> <span data-ttu-id="b2ee9-105">En Lync Server 2013, cuando están en uso IPv4 e IPv6, debe planear los registros A y AAAA del host.</span><span class="sxs-lookup"><span data-stu-id="b2ee9-105">In Lync Server 2013 when IPv4 and IPv6 are in use, you must plan for both host A and AAAA records.</span></span>

<span data-ttu-id="b2ee9-106">Los temas enumerados a continuación definen el uso de registros DNS para la planeación de implementación:</span><span class="sxs-lookup"><span data-stu-id="b2ee9-106">The topics listed below define the use of DNS records for your deployment planning:</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b2ee9-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="b2ee9-107">In This Section</span></span>

  - [<span data-ttu-id="b2ee9-108">Resumen de DNS-servidor perimetral consolidado único con direcciones IP privadas que usan NAT en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2ee9-108">DNS summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-dns-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="b2ee9-109">Resumen de DNS-servidor perimetral consolidado único con direcciones IP públicas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2ee9-109">DNS summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-dns-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="b2ee9-110">Resumen de DNS-servidor perimetral consolidado ampliado, equilibrio de carga de DNS con direcciones IP privadas mediante NAT en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2ee9-110">DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="b2ee9-111">Resumen de DNS-servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP públicas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2ee9-111">DNS summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="b2ee9-112">Resumen de DNS-servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2ee9-112">DNS summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [<span data-ttu-id="b2ee9-113">Resumen de DNS-proxy inverso en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2ee9-113">DNS summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-dns-summary-reverse-proxy.md)

  - [<span data-ttu-id="b2ee9-114">Resumen de DNS: SIP, Federación XMPP y mensajería instantánea pública en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2ee9-114">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

