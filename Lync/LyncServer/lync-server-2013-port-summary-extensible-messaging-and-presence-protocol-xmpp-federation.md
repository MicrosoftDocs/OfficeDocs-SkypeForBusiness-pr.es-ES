---
title: Resumen de Puerto-Federación del protocolo extensible de mensajería y presencia (XMPP)
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
ms.openlocfilehash: b72ab2f2912a78ee30e9c032592a704eccbab8bf
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152658"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="076c4-102">Resumen de puertos-Federación del protocolo extensible de mensajería y presencia (XMPP) en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="076c4-102">Port summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="076c4-103">_**Última modificación del tema:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="076c4-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="076c4-104">Los puertos y protocolos definidos para el proxy de protocolo extensible de mensajería y presencia (XMPP) implementado en el servidor perimetral permiten las comunicaciones desde el socio federado de XMPP hacia el servidor perimetral y también permiten la comunicación desde el servidor perimetral al XMPP socio federado.</span><span class="sxs-lookup"><span data-stu-id="076c4-104">The ports and protocols defined for the extensible messaging and presence protocol (XMPP) proxy deployed on the Edge Server allow communications from the XMPP federated partner to the Edge Server, and also allows communication from your Edge Server to the XMPP federated partner.</span></span> <span data-ttu-id="076c4-105">Una regla también se define en el Firewall orientado internamente desde el servidor front-end o el grupo de servidores front-end hasta el servidor perimetral o el grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="076c4-105">A rule is also defined on the internal-facing firewall from the Front End Server or Front End pool to the Edge Server or Edge pool.</span></span>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="076c4-106">Resumen de firewall para el protocolo extensible de mensajería y presencia</span><span class="sxs-lookup"><span data-stu-id="076c4-106">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="076c4-107">Protocolo/TCP o UDP/Puerto</span><span class="sxs-lookup"><span data-stu-id="076c4-107">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="076c4-108">Origen (Dirección IP)</span><span class="sxs-lookup"><span data-stu-id="076c4-108">Source (IP address)</span></span></th>
<th><span data-ttu-id="076c4-109">Destino (Dirección IP)</span><span class="sxs-lookup"><span data-stu-id="076c4-109">Destination (IP address)</span></span></th>
<th><span data-ttu-id="076c4-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="076c4-110">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="076c4-111">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="076c4-111">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="076c4-112">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="076c4-112">Any</span></span></p></td>
<td><p><span data-ttu-id="076c4-113">Dirección IP de la interfaz del servicio perimetral de acceso</span><span class="sxs-lookup"><span data-stu-id="076c4-113">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="076c4-114">Puerto de comunicación estándar de servidor a servidor para XMPP.</span><span class="sxs-lookup"><span data-stu-id="076c4-114">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="076c4-115">Permite la comunicación con el proxy XMPP del servidor perimetral desde socios XMPP federados.</span><span class="sxs-lookup"><span data-stu-id="076c4-115">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="076c4-116">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="076c4-116">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="076c4-117">Dirección IP de la interfaz del servicio perimetral de acceso</span><span class="sxs-lookup"><span data-stu-id="076c4-117">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="076c4-118">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="076c4-118">Any</span></span></p></td>
<td><p><span data-ttu-id="076c4-119">Puerto de comunicación estándar de servidor a servidor para XMPP.</span><span class="sxs-lookup"><span data-stu-id="076c4-119">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="076c4-120">Permite la comunicación desde el proxy XMPP del servidor perimetral a asociados de XMPP federados.</span><span class="sxs-lookup"><span data-stu-id="076c4-120">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="076c4-121">XMPP/MTLS/23456</span><span class="sxs-lookup"><span data-stu-id="076c4-121">XMPP/MTLS/23456</span></span></p></td>
<td><p><span data-ttu-id="076c4-122">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="076c4-122">Any</span></span></p></td>
<td><p><span data-ttu-id="076c4-123">IP de la interfaz del servidor perimetral interno</span><span class="sxs-lookup"><span data-stu-id="076c4-123">Internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="076c4-124">Tráfico XMPP interno de la puerta de enlace XMPP del servidor front-end o del grupo de servidores front-end al servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="076c4-124">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="076c4-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="076c4-125">See Also</span></span>


[<span data-ttu-id="076c4-126">Configuración XMPP de ejemplo en Lync Server 2013: Federación XMPP con Google Talk</span><span class="sxs-lookup"><span data-stu-id="076c4-126">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="076c4-127">Administrar socios federados XMPP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="076c4-127">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

