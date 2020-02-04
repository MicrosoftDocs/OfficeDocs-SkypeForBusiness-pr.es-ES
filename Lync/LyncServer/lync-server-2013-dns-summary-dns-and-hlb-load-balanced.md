---
title: 'Lync Server 2013: Resumen de DNS - Carga equilibrada DNS y HLB'
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
ms.openlocfilehash: c5b84ccab2b3074662016a19c5f0a51d0cb70405
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737240"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="5cab4-102">Resumen de DNS - Carga equilibrada DNS y HLB en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5cab4-102">DNS summary - DNS and HLB load balanced in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5cab4-103">_**Última modificación del tema:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="5cab4-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="5cab4-104">La tabla siguiente contiene un resumen de los registros DNS necesarios para admitir el equilibrio de carga de hardware y equilibrio de carga de DNS.</span><span class="sxs-lookup"><span data-stu-id="5cab4-104">The following table contains a summary of the DNS records that are required to support the DNS load balanced and hardware load balanced Director.</span></span> <span data-ttu-id="5cab4-105">La función del Director requiere registros DNS similares como servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="5cab4-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="5cab4-106">El número de registros necesarios se refleja en el asunto nombres alternativos requeridos en el certificado de director.</span><span class="sxs-lookup"><span data-stu-id="5cab4-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="5cab4-107">Diferente al servidor front-end, el grupo de directores no hospeda cuentas de usuario ni hospeda los servicios de movilidad.</span><span class="sxs-lookup"><span data-stu-id="5cab4-107">Different from the Front End Server, the Director pool does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director-pool-using-dns-load-balancing-and-hardware-load-balancer"></a><span data-ttu-id="5cab4-108">Registros DNS necesarios para el grupo de directores mediante el equilibrio de carga de DNS y el equilibrador de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="5cab4-108">DNS Records Required for the Director Pool using DNS Load Balancing and Hardware Load Balancer</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5cab4-109">Ubicación/tipo/puerto</span><span class="sxs-lookup"><span data-stu-id="5cab4-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="5cab4-110">FQDN/registro DNS</span><span class="sxs-lookup"><span data-stu-id="5cab4-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="5cab4-111">Dirección IP/FQDN</span><span class="sxs-lookup"><span data-stu-id="5cab4-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="5cab4-112">Se asigna a/comentarios</span><span class="sxs-lookup"><span data-stu-id="5cab4-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5cab4-113">DNS/A interno</span><span class="sxs-lookup"><span data-stu-id="5cab4-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="5cab4-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="5cab4-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="5cab4-115">Director</span><span class="sxs-lookup"><span data-stu-id="5cab4-115">Director</span></span></p></td>
<td><p><span data-ttu-id="5cab4-116">Registro de host de Director usado para la replicación y el servidor a servidor</span><span class="sxs-lookup"><span data-stu-id="5cab4-116">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5cab4-117">DNS/A interno</span><span class="sxs-lookup"><span data-stu-id="5cab4-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="5cab4-118">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="5cab4-118">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="5cab4-119">Grupo de directores</span><span class="sxs-lookup"><span data-stu-id="5cab4-119">Director pool</span></span></p></td>
<td><p><span data-ttu-id="5cab4-120">Registro de host para el grupo de directores de carga equilibrada de DNS para servidor a servidor</span><span class="sxs-lookup"><span data-stu-id="5cab4-120">Host record for the DNS load balanced Director pool for server to server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5cab4-121">DNS/A interno</span><span class="sxs-lookup"><span data-stu-id="5cab4-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="5cab4-122">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5cab4-122">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5cab4-123">Grupo de directores</span><span class="sxs-lookup"><span data-stu-id="5cab4-123">Director pool</span></span></p></td>
<td><p><span data-ttu-id="5cab4-124">Protocolo de inicio de sesión (SIP) entrante de la interfaz interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="5cab4-124">Inbound session initiation protocol (SIP) from the internal interface of the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5cab4-125">DNS/A interno</span><span class="sxs-lookup"><span data-stu-id="5cab4-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="5cab4-126">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5cab4-126">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5cab4-127">Grupo de directores HLB VIP</span><span class="sxs-lookup"><span data-stu-id="5cab4-127">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="5cab4-128">Equilibrio de carga de hardware publicado servicios Web de marcado desde proxy inverso</span><span class="sxs-lookup"><span data-stu-id="5cab4-128">Hardware load balanced published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5cab4-129">DNS/A interno</span><span class="sxs-lookup"><span data-stu-id="5cab4-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="5cab4-130">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5cab4-130">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5cab4-131">Grupo de directores HLB VIP</span><span class="sxs-lookup"><span data-stu-id="5cab4-131">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="5cab4-132">El equilibrio de carga de hardware publicado cumple con los servicios web del proxy inverso</span><span class="sxs-lookup"><span data-stu-id="5cab4-132">Hardware load balanced published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5cab4-133">DNS/A interno</span><span class="sxs-lookup"><span data-stu-id="5cab4-133">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="5cab4-134">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5cab4-134">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5cab4-135">Grupo de directores HLB VIP</span><span class="sxs-lookup"><span data-stu-id="5cab4-135">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="5cab4-136">Equilibrio de carga de hardware publicado y definido por el vale Web de proxy inverso servicios web externos para el grupo de directores</span><span class="sxs-lookup"><span data-stu-id="5cab4-136">Hardware load balanced published and defined by the reverse proxy Web Ticket external web services for the Director pool</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

