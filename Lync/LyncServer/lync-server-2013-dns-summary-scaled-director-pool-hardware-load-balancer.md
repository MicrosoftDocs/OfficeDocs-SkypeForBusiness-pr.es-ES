---
title: 'Lync Server 2013: Resumen de DNS-grupo de Director escalado, equilibrador de carga de hardware'
description: 'Lync Server 2013: Resumen de DNS-grupo de Director escalado, equilibrador de carga de hardware.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled Director pool, hardware load balancer
ms:assetid: 08ba48e6-bfa1-4ab0-bc89-d58ddb9c20af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204655(v=OCS.15)
ms:contentKeyID: 48183340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7198e6a97feed8ce70cb16753ad1f21d58ef246c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555886"
---
# <a name="dns-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="b5bc7-103">Resumen de DNS-grupo de Director escalado, equilibrador de carga de hardware en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5bc7-103">DNS summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5bc7-104">_**Última modificación del tema:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="b5bc7-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="b5bc7-105">La siguiente tabla contiene un resumen de los registros DNS necesarios para admitir el director de carga equilibrada de hardware.</span><span class="sxs-lookup"><span data-stu-id="b5bc7-105">The following table contains a summary of the DNS records that are required to support the hardware load balanced Director.</span></span> <span data-ttu-id="b5bc7-106">El rol del Director requiere registros DNS similares como servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="b5bc7-106">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="b5bc7-107">El número de registros necesarios se refleja en los nombres alternativos de sujeto necesarios en el certificado de director.</span><span class="sxs-lookup"><span data-stu-id="b5bc7-107">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="b5bc7-108">Diferente del servidor front-end, el grupo de directores no hospeda las cuentas de usuario ni hospeda los servicios de movilidad.</span><span class="sxs-lookup"><span data-stu-id="b5bc7-108">Different from the Front End Server, the Director pool does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director-pool-using-a-hardware-load-balancer-and-dns-load-balancing"></a><span data-ttu-id="b5bc7-109">Registros DNS necesarios para el grupo de directores mediante un equilibrador de carga de hardware y el equilibrio de carga de DNS</span><span class="sxs-lookup"><span data-stu-id="b5bc7-109">DNS Records Required for the Director pool using a Hardware Load Balancer and DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b5bc7-110">Ubicación/tipo/puerto</span><span class="sxs-lookup"><span data-stu-id="b5bc7-110">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="b5bc7-111">FQDN/Registro DNS</span><span class="sxs-lookup"><span data-stu-id="b5bc7-111">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="b5bc7-112">Dirección IP/FQDN</span><span class="sxs-lookup"><span data-stu-id="b5bc7-112">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="b5bc7-113">Asignado a/Comentarios</span><span class="sxs-lookup"><span data-stu-id="b5bc7-113">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b5bc7-114">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="b5bc7-114">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="b5bc7-115">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="b5bc7-115">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="b5bc7-116">Director</span><span class="sxs-lookup"><span data-stu-id="b5bc7-116">Director</span></span></p></td>
<td><p><span data-ttu-id="b5bc7-117">Registro de host de Director usado para la replicación y la comunicación de servidor a servidor</span><span class="sxs-lookup"><span data-stu-id="b5bc7-117">Director host record used for replication and server to server communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5bc7-118">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="b5bc7-118">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="b5bc7-119">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="b5bc7-119">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="b5bc7-120">Director del grupo de HLB VIP</span><span class="sxs-lookup"><span data-stu-id="b5bc7-120">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="b5bc7-121">Registro de host del grupo de directores de equilibrio de carga de DNS</span><span class="sxs-lookup"><span data-stu-id="b5bc7-121">Host record for the DNS load balanced Director pool</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5bc7-122">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="b5bc7-122">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="b5bc7-123">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b5bc7-123">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b5bc7-124">Director del grupo de HLB VIP</span><span class="sxs-lookup"><span data-stu-id="b5bc7-124">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="b5bc7-125">Protocolo de inicio de sesión (SIP) entrante desde la interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="b5bc7-125">Inbound session initiation protocol (SIP) from the internal interface of the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5bc7-126">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="b5bc7-126">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="b5bc7-127">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b5bc7-127">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b5bc7-128">Director del grupo de HLB VIP</span><span class="sxs-lookup"><span data-stu-id="b5bc7-128">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="b5bc7-129">Servicios web de marcado publicados con equilibrio de carga de hardware desde proxy inverso</span><span class="sxs-lookup"><span data-stu-id="b5bc7-129">Hardware load balanced published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5bc7-130">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="b5bc7-130">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="b5bc7-131">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b5bc7-131">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b5bc7-132">Director del grupo de HLB VIP</span><span class="sxs-lookup"><span data-stu-id="b5bc7-132">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="b5bc7-133">Servicios web de reunión publicados con equilibrio de carga desde proxy inverso</span><span class="sxs-lookup"><span data-stu-id="b5bc7-133">Hardware load balanced published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5bc7-134">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="b5bc7-134">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="b5bc7-135">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b5bc7-135">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b5bc7-136">Director del grupo de HLB VIP</span><span class="sxs-lookup"><span data-stu-id="b5bc7-136">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="b5bc7-137">Carga de hardware equilibrada publicada y definida por los servicios web externos de vale web de proxy inverso para el grupo de directores</span><span class="sxs-lookup"><span data-stu-id="b5bc7-137">Hardware load balanced published and defined by the reverse proxy Web Ticket external web services for the Director pool</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

