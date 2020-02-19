---
title: 'Lync Server 2013: Resumen de DNS-carga equilibrada DNS y HLB'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - DNS and HLB load balanced
ms:assetid: d2132695-1956-4190-a98e-cd7255cbded6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205273(v=OCS.15)
ms:contentKeyID: 48185447
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2c4b2df2200ecd7cc5af6e3aa651c18866c8924
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135076"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="d1e8d-102">Resumen de DNS-carga equilibrada DNS y HLB en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1e8d-102">DNS summary - DNS and HLB load balanced in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1e8d-103">_**Última modificación del tema:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="d1e8d-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="d1e8d-104">La siguiente tabla contiene un resumen de los registros DNS necesarios para admitir el equilibrio de carga de DNS y el director de carga equilibrada de hardware.</span><span class="sxs-lookup"><span data-stu-id="d1e8d-104">The following table contains a summary of the DNS records that are required to support the DNS load balanced and hardware load balanced Director.</span></span> <span data-ttu-id="d1e8d-105">El rol del Director requiere registros DNS similares como servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="d1e8d-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="d1e8d-106">El número de registros necesarios se refleja en los nombres alternativos de sujeto necesarios en el certificado de director.</span><span class="sxs-lookup"><span data-stu-id="d1e8d-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="d1e8d-107">Diferente del servidor front-end, el grupo de directores no hospeda las cuentas de usuario ni hospeda los servicios de movilidad.</span><span class="sxs-lookup"><span data-stu-id="d1e8d-107">Different from the Front End Server, the Director pool does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director-pool-using-dns-load-balancing-and-hardware-load-balancer"></a><span data-ttu-id="d1e8d-108">Registros DNS necesarios para el grupo de directores que usan carga de DNS y carga de hardware equilibradas</span><span class="sxs-lookup"><span data-stu-id="d1e8d-108">DNS Records Required for the Director Pool using DNS Load Balancing and Hardware Load Balancer</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1e8d-109">Ubicación/tipo/puerto</span><span class="sxs-lookup"><span data-stu-id="d1e8d-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="d1e8d-110">FQDN/Registro DNS</span><span class="sxs-lookup"><span data-stu-id="d1e8d-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="d1e8d-111">Dirección IP/FQDN</span><span class="sxs-lookup"><span data-stu-id="d1e8d-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="d1e8d-112">Asignado a/Comentarios</span><span class="sxs-lookup"><span data-stu-id="d1e8d-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1e8d-113">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="d1e8d-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="d1e8d-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="d1e8d-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="d1e8d-115">Dirección</span><span class="sxs-lookup"><span data-stu-id="d1e8d-115">Director</span></span></p></td>
<td><p><span data-ttu-id="d1e8d-116">Registro de host de Director usado para la replicación y el servidor a servidor</span><span class="sxs-lookup"><span data-stu-id="d1e8d-116">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1e8d-117">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="d1e8d-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="d1e8d-118">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="d1e8d-118">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="d1e8d-119">Grupo de servidores Director</span><span class="sxs-lookup"><span data-stu-id="d1e8d-119">Director pool</span></span></p></td>
<td><p><span data-ttu-id="d1e8d-120">Registro de host del grupo de directores con equilibrio de carga de DNS para el servidor al servidor</span><span class="sxs-lookup"><span data-stu-id="d1e8d-120">Host record for the DNS load balanced Director pool for server to server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1e8d-121">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="d1e8d-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="d1e8d-122">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d1e8d-122">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d1e8d-123">Grupo de servidores Director</span><span class="sxs-lookup"><span data-stu-id="d1e8d-123">Director pool</span></span></p></td>
<td><p><span data-ttu-id="d1e8d-124">Protocolo de inicio de sesión (SIP) entrante desde la interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d1e8d-124">Inbound session initiation protocol (SIP) from the internal interface of the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1e8d-125">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="d1e8d-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="d1e8d-126">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d1e8d-126">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d1e8d-127">Director del grupo de HLB VIP</span><span class="sxs-lookup"><span data-stu-id="d1e8d-127">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="d1e8d-128">Servicios web de marcado publicados con equilibrio de carga de hardware desde proxy inverso</span><span class="sxs-lookup"><span data-stu-id="d1e8d-128">Hardware load balanced published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1e8d-129">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="d1e8d-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="d1e8d-130">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d1e8d-130">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d1e8d-131">Director del grupo de HLB VIP</span><span class="sxs-lookup"><span data-stu-id="d1e8d-131">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="d1e8d-132">Servicios web de reunión publicados con equilibrio de carga desde proxy inverso</span><span class="sxs-lookup"><span data-stu-id="d1e8d-132">Hardware load balanced published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1e8d-133">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="d1e8d-133">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="d1e8d-134">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d1e8d-134">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d1e8d-135">Director del grupo de HLB VIP</span><span class="sxs-lookup"><span data-stu-id="d1e8d-135">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="d1e8d-136">Carga de hardware equilibrada publicada y definida por los servicios web externos de vale web de proxy inverso para el grupo de directores</span><span class="sxs-lookup"><span data-stu-id="d1e8d-136">Hardware load balanced published and defined by the reverse proxy Web Ticket external web services for the Director pool</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

