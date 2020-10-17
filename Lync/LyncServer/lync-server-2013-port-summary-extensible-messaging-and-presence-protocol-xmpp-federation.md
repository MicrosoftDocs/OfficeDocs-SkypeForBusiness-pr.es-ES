---
title: Resumen de Puerto-Federación del protocolo extensible de mensajería y presencia (XMPP)
description: Resumen de puertos-Federación del protocolo extensible de mensajería y presencia (XMPP).
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary -  Extensible messaging and presence protocol (XMPP) federation
ms:assetid: 62e98fab-7add-4983-a3fa-dbe74e1c3849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618371(v=OCS.15)
ms:contentKeyID: 49105658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9508bc8b9fbcca6fb6a37478def258a9fa52c373
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543096"
---
# <a name="port-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="bd77b-103">Resumen de puertos-Federación del protocolo extensible de mensajería y presencia (XMPP) en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd77b-103">Port summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd77b-104">_**Última modificación del tema:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="bd77b-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="bd77b-105">Los puertos y protocolos definidos para el proxy de protocolo extensible de mensajería y presencia (XMPP) implementado en el servidor perimetral permiten las comunicaciones desde el socio federado de XMPP hasta el servidor perimetral y también permiten la comunicación desde el servidor perimetral al socio federado de XMPP.</span><span class="sxs-lookup"><span data-stu-id="bd77b-105">The ports and protocols defined for the extensible messaging and presence protocol (XMPP) proxy deployed on the Edge Server allow communications from the XMPP federated partner to the Edge Server, and also allows communication from your Edge Server to the XMPP federated partner.</span></span> <span data-ttu-id="bd77b-106">Una regla también se define en el Firewall orientado internamente desde el servidor front-end o el grupo de servidores front-end hasta el servidor perimetral o el grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="bd77b-106">A rule is also defined on the internal-facing firewall from the Front End Server or Front End pool to the Edge Server or Edge pool.</span></span>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="bd77b-107">Resumen de firewall para el protocolo extensible de mensajería y presencia</span><span class="sxs-lookup"><span data-stu-id="bd77b-107">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bd77b-108">Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="bd77b-108">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="bd77b-109">Origen (Dirección IP)</span><span class="sxs-lookup"><span data-stu-id="bd77b-109">Source (IP address)</span></span></th>
<th><span data-ttu-id="bd77b-110">Destino (Dirección IP)</span><span class="sxs-lookup"><span data-stu-id="bd77b-110">Destination (IP address)</span></span></th>
<th><span data-ttu-id="bd77b-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bd77b-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bd77b-112">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="bd77b-112">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="bd77b-113">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="bd77b-113">Any</span></span></p></td>
<td><p><span data-ttu-id="bd77b-114">Dirección IP de la interfaz del servicio perimetral de acceso</span><span class="sxs-lookup"><span data-stu-id="bd77b-114">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="bd77b-115">Puerto de comunicación estándar de servidor a servidor para XMPP.</span><span class="sxs-lookup"><span data-stu-id="bd77b-115">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="bd77b-116">Permite la comunicación con el proxy XMPP del servidor perimetral desde socios XMPP federados.</span><span class="sxs-lookup"><span data-stu-id="bd77b-116">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd77b-117">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="bd77b-117">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="bd77b-118">Dirección IP de la interfaz del servicio perimetral de acceso</span><span class="sxs-lookup"><span data-stu-id="bd77b-118">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="bd77b-119">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="bd77b-119">Any</span></span></p></td>
<td><p><span data-ttu-id="bd77b-120">Puerto de comunicación estándar de servidor a servidor para XMPP.</span><span class="sxs-lookup"><span data-stu-id="bd77b-120">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="bd77b-121">Permite la comunicación desde el proxy XMPP del servidor perimetral a asociados de XMPP federados.</span><span class="sxs-lookup"><span data-stu-id="bd77b-121">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd77b-122">XMPP/MTLS/23456</span><span class="sxs-lookup"><span data-stu-id="bd77b-122">XMPP/MTLS/23456</span></span></p></td>
<td><p><span data-ttu-id="bd77b-123">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="bd77b-123">Any</span></span></p></td>
<td><p><span data-ttu-id="bd77b-124">IP de la interfaz del servidor perimetral interno</span><span class="sxs-lookup"><span data-stu-id="bd77b-124">Internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="bd77b-125">Tráfico XMPP interno de la puerta de enlace XMPP del servidor front-end o del grupo de servidores front-end al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="bd77b-125">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bd77b-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bd77b-126">See Also</span></span>


[<span data-ttu-id="bd77b-127">Configuración XMPP de ejemplo en Lync Server 2013: Federación XMPP con Google Talk</span><span class="sxs-lookup"><span data-stu-id="bd77b-127">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="bd77b-128">Administrar socios federados XMPP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd77b-128">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

