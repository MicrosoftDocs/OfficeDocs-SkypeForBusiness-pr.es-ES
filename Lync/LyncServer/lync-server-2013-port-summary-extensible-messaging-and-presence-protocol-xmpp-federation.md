---
title: 'Resumen de puertos: Federación protocolo de presencia y mensajería extensible (XMPP)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary -  Extensible messaging and presence protocol (XMPP) federation
ms:assetid: 62e98fab-7add-4983-a3fa-dbe74e1c3849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618371(v=OCS.15)
ms:contentKeyID: 49105658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b36a74393a8c61d5281bb009d212ee0bb12cf0a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="e3a3a-102">Resumen de puertos: Federación protocolo de presencia y mensajería extensible (XMPP) en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3a3a-102">Port summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3a3a-103">_**Última modificación del tema:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="e3a3a-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="e3a3a-104">Los puertos y protocolos definidos para el proxy protocolo de presencia y mensajería extensible (XMPP) implementado en el servidor perimetral permiten las comunicaciones del socio XMPP federado hasta el servidor perimetral, y también permiten la comunicación desde el servidor perimetral al XMPP socio federado.</span><span class="sxs-lookup"><span data-stu-id="e3a3a-104">The ports and protocols defined for the extensible messaging and presence protocol (XMPP) proxy deployed on the Edge Server allow communications from the XMPP federated partner to the Edge Server, and also allows communication from your Edge Server to the XMPP federated partner.</span></span> <span data-ttu-id="e3a3a-105">Una regla también se define en el Firewall de orientación interna desde el servidor front-end o el grupo front-end hasta el servidor perimetral o el grupo Edge.</span><span class="sxs-lookup"><span data-stu-id="e3a3a-105">A rule is also defined on the internal-facing firewall from the Front End Server or Front End pool to the Edge Server or Edge pool.</span></span>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="e3a3a-106">Resumen de Firewall para el protocolo de presencia y mensajería extensible</span><span class="sxs-lookup"><span data-stu-id="e3a3a-106">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3a3a-107">Protocolo/TCP o UDP/puerto</span><span class="sxs-lookup"><span data-stu-id="e3a3a-107">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="e3a3a-108">Origen (dirección IP)</span><span class="sxs-lookup"><span data-stu-id="e3a3a-108">Source (IP address)</span></span></th>
<th><span data-ttu-id="e3a3a-109">Destino (dirección IP)</span><span class="sxs-lookup"><span data-stu-id="e3a3a-109">Destination (IP address)</span></span></th>
<th><span data-ttu-id="e3a3a-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e3a3a-110">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3a3a-111">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="e3a3a-111">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="e3a3a-112">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e3a3a-112">Any</span></span></p></td>
<td><p><span data-ttu-id="e3a3a-113">Dirección IP de la interfaz de servicio perimetral de Access</span><span class="sxs-lookup"><span data-stu-id="e3a3a-113">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="e3a3a-114">Puerto de comunicación de servidor a servidor estándar para XMPP.</span><span class="sxs-lookup"><span data-stu-id="e3a3a-114">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="e3a3a-115">Permite la comunicación con el proxy XMPP del servidor perimetral de socios de XMPP</span><span class="sxs-lookup"><span data-stu-id="e3a3a-115">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3a3a-116">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="e3a3a-116">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="e3a3a-117">Dirección IP de la interfaz de servicio perimetral de Access</span><span class="sxs-lookup"><span data-stu-id="e3a3a-117">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="e3a3a-118">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e3a3a-118">Any</span></span></p></td>
<td><p><span data-ttu-id="e3a3a-119">Puerto de comunicación de servidor a servidor estándar para XMPP.</span><span class="sxs-lookup"><span data-stu-id="e3a3a-119">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="e3a3a-120">Permite la comunicación desde el proxy XMPP del servidor perimetral a socios XMPP de Federación</span><span class="sxs-lookup"><span data-stu-id="e3a3a-120">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3a3a-121">XMPP/MTLS/23456</span><span class="sxs-lookup"><span data-stu-id="e3a3a-121">XMPP/MTLS/23456</span></span></p></td>
<td><p><span data-ttu-id="e3a3a-122">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e3a3a-122">Any</span></span></p></td>
<td><p><span data-ttu-id="e3a3a-123">IP de la interfaz del servidor perimetral interno</span><span class="sxs-lookup"><span data-stu-id="e3a3a-123">Internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="e3a3a-124">Tráfico de XMPP interno de la puerta de enlace XMPP del servidor front-end o del grupo front-end al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="e3a3a-124">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e3a3a-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="e3a3a-125">See Also</span></span>


[<span data-ttu-id="e3a3a-126">Configuración XMPP de ejemplo en Lync Server 2013 - Federación XMPP con Google Talk</span><span class="sxs-lookup"><span data-stu-id="e3a3a-126">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="e3a3a-127">Administrar socios federados XMPP para su organización en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3a3a-127">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

