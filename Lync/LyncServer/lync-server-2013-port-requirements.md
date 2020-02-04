---
title: Requisitos del puerto 2013 de Lync Server
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
ms.openlocfilehash: 584d1c8391f0393711b2caf6de46a0df6c437c51
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747660"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-requirements-for-lync-server-2013"></a><span data-ttu-id="eb2aa-102">Requisitos de puerto para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb2aa-102">Port requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb2aa-103">_**Última modificación del tema:** 2013-03-27_</span><span class="sxs-lookup"><span data-stu-id="eb2aa-103">_**Topic Last Modified:** 2013-03-27_</span></span>

<span data-ttu-id="eb2aa-104">Lync Server requiere que los puertos específicos del firewall estén abiertos.</span><span class="sxs-lookup"><span data-stu-id="eb2aa-104">Lync Server requires that specific ports on the firewall be open.</span></span> <span data-ttu-id="eb2aa-105">Además, si se ha implementado el protocolo de seguridad de Internet (IPSec) en la organización, IPSec debe estar deshabilitado en el intervalo de puertos que se usa para la entrega de audio, vídeo y vídeo panorámico.</span><span class="sxs-lookup"><span data-stu-id="eb2aa-105">Additionally, if Internet Protocol security (IPsec) is deployed in your organization, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="eb2aa-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="eb2aa-106">In This Section</span></span>

<span data-ttu-id="eb2aa-107">Esta sección incluye los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="eb2aa-107">This section includes the following topics:</span></span>

  - [<span data-ttu-id="eb2aa-108">Puertos y protocolos para servidores internos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb2aa-108">Ports and protocols for internal servers in Lync Server 2013</span></span>](lync-server-2013-ports-and-protocols-for-internal-servers.md)

  - [<span data-ttu-id="eb2aa-109">Excepciones de IPsec en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb2aa-109">IPsec exceptions in Lync Server 2013</span></span>](lync-server-2013-ipsec-exceptions.md)

  - [<span data-ttu-id="eb2aa-110">Resumen de puerto - Perímetro consolidado de un solo equipo con direcciones IP privadas mediante NAT en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb2aa-110">Port summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-port-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="eb2aa-111">Resumen de puerto - Perímetro consolidado de equipo único con direcciones IP públicas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb2aa-111">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-port-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="eb2aa-112">Resumen de puerto - Servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP privadas mediante NAT en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb2aa-112">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="eb2aa-113">Resumen de puerto - Servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP públicas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb2aa-113">Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="eb2aa-114">Resumen de puerto - Servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb2aa-114">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [<span data-ttu-id="eb2aa-115">Resumen de puerto - Proxy inverso en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb2aa-115">Port summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-port-summary-reverse-proxy.md)

  - [<span data-ttu-id="eb2aa-116">Resumen de puertos: SIP, Federación XMPP y mensajería instantánea pública en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb2aa-116">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

