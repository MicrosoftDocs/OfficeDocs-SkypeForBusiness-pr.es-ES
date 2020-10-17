---
title: Requisitos del puerto de Lync Server 2013
description: Lync Server 2013 los requisitos de puerto.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port requirements
ms:assetid: 9a6c1300-ef88-4181-a8f1-43cd3093962b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398798(v=OCS.15)
ms:contentKeyID: 48184886
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba7ae9a1ee098f55c61ae476f12c3b856c69f90e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543166"
---
# <a name="port-requirements-for-lync-server-2013"></a><span data-ttu-id="6f948-103">Requisitos de puertos para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f948-103">Port requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f948-104">_**Última modificación del tema:** 2013-03-27_</span><span class="sxs-lookup"><span data-stu-id="6f948-104">_**Topic Last Modified:** 2013-03-27_</span></span>

<span data-ttu-id="6f948-105">Lync Server requiere que estén abiertos los puertos específicos del firewall.</span><span class="sxs-lookup"><span data-stu-id="6f948-105">Lync Server requires that specific ports on the firewall be open.</span></span> <span data-ttu-id="6f948-106">Además, si se ha implementado el protocolo de seguridad de Internet (IPSec) en la organización, IPSec debe estar deshabilitado en el intervalo de puertos usado para la entrega de audio, vídeo y vídeo panorámico.</span><span class="sxs-lookup"><span data-stu-id="6f948-106">Additionally, if Internet Protocol security (IPsec) is deployed in your organization, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6f948-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="6f948-107">In This Section</span></span>

<span data-ttu-id="6f948-108">Esta sección incluye los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="6f948-108">This section includes the following topics:</span></span>

  - [<span data-ttu-id="6f948-109">Puertos y protocolos para servidores internos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f948-109">Ports and protocols for internal servers in Lync Server 2013</span></span>](lync-server-2013-ports-and-protocols-for-internal-servers.md)

  - [<span data-ttu-id="6f948-110">Excepciones de IPsec en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f948-110">IPsec exceptions in Lync Server 2013</span></span>](lync-server-2013-ipsec-exceptions.md)

  - [<span data-ttu-id="6f948-111">Resumen de Puerto-perímetro consolidado de un solo servidor con direcciones IP privadas mediante NAT en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f948-111">Port summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-port-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="6f948-112">Resumen de Puerto-perímetro consolidado de un solo servidor con direcciones IP públicas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f948-112">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-port-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="6f948-113">Resumen de Puerto-servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP privadas mediante NAT en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f948-113">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="6f948-114">Resumen de Puerto-servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP públicas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f948-114">Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="6f948-115">Resumen de Puerto-servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f948-115">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [<span data-ttu-id="6f948-116">Resumen de Puerto-proxy inverso en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f948-116">Port summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-port-summary-reverse-proxy.md)

  - [<span data-ttu-id="6f948-117">Resumen de Puerto-SIP, Federación XMPP y mensajería instantánea pública en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f948-117">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

