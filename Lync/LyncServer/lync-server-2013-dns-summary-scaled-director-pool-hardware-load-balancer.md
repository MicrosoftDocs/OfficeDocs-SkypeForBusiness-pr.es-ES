---
title: 'Lync Server 2013: Resumen de DNS-grupo de Director escalado, equilibrador de carga de hardware'
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
ms.openlocfilehash: 7ed4a3a810e4f1aa2fc5228e61cd68af163c91f0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031234"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="a63aa-102">Resumen de DNS-grupo de Director escalado, equilibrador de carga de hardware en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a63aa-102">DNS summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a63aa-103">_**Última modificación del tema:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="a63aa-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="a63aa-104">La siguiente tabla contiene un resumen de los registros DNS necesarios para admitir el director de carga equilibrada de hardware.</span><span class="sxs-lookup"><span data-stu-id="a63aa-104">The following table contains a summary of the DNS records that are required to support the hardware load balanced Director.</span></span> <span data-ttu-id="a63aa-105">El rol del Director requiere registros DNS similares como servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="a63aa-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="a63aa-106">El número de registros necesarios se refleja en los nombres alternativos de sujeto necesarios en el certificado de director.</span><span class="sxs-lookup"><span data-stu-id="a63aa-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="a63aa-107">Diferente del servidor front-end, el grupo de directores no hospeda las cuentas de usuario ni hospeda los servicios de movilidad.</span><span class="sxs-lookup"><span data-stu-id="a63aa-107">Different from the Front End Server, the Director pool does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director-pool-using-a-hardware-load-balancer-and-dns-load-balancing"></a><span data-ttu-id="a63aa-108">Registros DNS necesarios para el grupo de directores mediante un equilibrador de carga de hardware y el equilibrio de carga de DNS</span><span class="sxs-lookup"><span data-stu-id="a63aa-108">DNS Records Required for the Director pool using a Hardware Load Balancer and DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a63aa-109">Ubicación/tipo/puerto</span><span class="sxs-lookup"><span data-stu-id="a63aa-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="a63aa-110">FQDN/Registro DNS</span><span class="sxs-lookup"><span data-stu-id="a63aa-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="a63aa-111">Dirección IP/FQDN</span><span class="sxs-lookup"><span data-stu-id="a63aa-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="a63aa-112">Asignado a/Comentarios</span><span class="sxs-lookup"><span data-stu-id="a63aa-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a63aa-113">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="a63aa-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="a63aa-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="a63aa-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="a63aa-115">Dirección</span><span class="sxs-lookup"><span data-stu-id="a63aa-115">Director</span></span></p></td>
<td><p><span data-ttu-id="a63aa-116">Registro de host de Director usado para la replicación y la comunicación de servidor a servidor</span><span class="sxs-lookup"><span data-stu-id="a63aa-116">Director host record used for replication and server to server communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a63aa-117">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="a63aa-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="a63aa-118">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="a63aa-118">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="a63aa-119">Director del grupo de HLB VIP</span><span class="sxs-lookup"><span data-stu-id="a63aa-119">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="a63aa-120">Registro de host del grupo de directores de equilibrio de carga de DNS</span><span class="sxs-lookup"><span data-stu-id="a63aa-120">Host record for the DNS load balanced Director pool</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a63aa-121">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="a63aa-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="a63aa-122">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a63aa-122">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="a63aa-123">Director del grupo de HLB VIP</span><span class="sxs-lookup"><span data-stu-id="a63aa-123">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="a63aa-124">Protocolo de inicio de sesión (SIP) entrante desde la interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="a63aa-124">Inbound session initiation protocol (SIP) from the internal interface of the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a63aa-125">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="a63aa-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="a63aa-126">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a63aa-126">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="a63aa-127">Director del grupo de HLB VIP</span><span class="sxs-lookup"><span data-stu-id="a63aa-127">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="a63aa-128">Servicios web de marcado publicados con equilibrio de carga de hardware desde proxy inverso</span><span class="sxs-lookup"><span data-stu-id="a63aa-128">Hardware load balanced published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a63aa-129">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="a63aa-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="a63aa-130">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a63aa-130">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="a63aa-131">Director del grupo de HLB VIP</span><span class="sxs-lookup"><span data-stu-id="a63aa-131">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="a63aa-132">Servicios web de reunión publicados con equilibrio de carga desde proxy inverso</span><span class="sxs-lookup"><span data-stu-id="a63aa-132">Hardware load balanced published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a63aa-133">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="a63aa-133">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="a63aa-134">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a63aa-134">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="a63aa-135">Director del grupo de HLB VIP</span><span class="sxs-lookup"><span data-stu-id="a63aa-135">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="a63aa-136">Carga de hardware equilibrada publicada y definida por los servicios web externos de vale web de proxy inverso para el grupo de directores</span><span class="sxs-lookup"><span data-stu-id="a63aa-136">Hardware load balanced published and defined by the reverse proxy Web Ticket external web services for the Director pool</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

