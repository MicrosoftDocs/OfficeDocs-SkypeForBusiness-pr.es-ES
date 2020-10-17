---
title: 'Lync Server 2013: Resumen de DNS-Director único'
description: 'Lync Server 2013: Resumen de DNS-Director único.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Single Director
ms:assetid: 790ecb56-92cd-41f4-baf6-c290a707aa4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205021(v=OCS.15)
ms:contentKeyID: 48184568
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78ef19383df45644ad951ca5da69ef893b231980
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553236"
---
# <a name="dns-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="a6a9e-103">Resumen de DNS-Director único en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6a9e-103">DNS summary - Single Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6a9e-104">_**Última modificación del tema:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="a6a9e-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="a6a9e-105">La siguiente tabla contiene un resumen de los registros DNS necesarios para admitir el director único.</span><span class="sxs-lookup"><span data-stu-id="a6a9e-105">The following table contains a summary of the DNS records that are required to support the single Director.</span></span> <span data-ttu-id="a6a9e-106">El rol del Director requiere registros DNS similares como servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="a6a9e-106">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="a6a9e-107">El número de registros necesarios se refleja en los nombres alternativos de sujeto necesarios en el certificado de director.</span><span class="sxs-lookup"><span data-stu-id="a6a9e-107">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="a6a9e-108">Diferente del servidor front-end, el director no hospeda cuentas de usuario ni hospeda los servicios de movilidad.</span><span class="sxs-lookup"><span data-stu-id="a6a9e-108">Different from the Front End Server, the Director does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director"></a><span data-ttu-id="a6a9e-109">Registros DNS necesarios para el director</span><span class="sxs-lookup"><span data-stu-id="a6a9e-109">DNS Records Required for the Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a6a9e-110">Ubicación/tipo/puerto</span><span class="sxs-lookup"><span data-stu-id="a6a9e-110">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="a6a9e-111">FQDN/Registro DNS</span><span class="sxs-lookup"><span data-stu-id="a6a9e-111">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="a6a9e-112">Dirección IP/FQDN</span><span class="sxs-lookup"><span data-stu-id="a6a9e-112">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="a6a9e-113">Asignado a/Comentarios</span><span class="sxs-lookup"><span data-stu-id="a6a9e-113">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a6a9e-114">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="a6a9e-114">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="a6a9e-115">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="a6a9e-115">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="a6a9e-116">Director</span><span class="sxs-lookup"><span data-stu-id="a6a9e-116">Director</span></span></p></td>
<td><p><span data-ttu-id="a6a9e-117">Registro de host de Director usado para la replicación y el servidor a servidor</span><span class="sxs-lookup"><span data-stu-id="a6a9e-117">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6a9e-118">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="a6a9e-118">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="a6a9e-119">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a6a9e-119">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="a6a9e-120">Director</span><span class="sxs-lookup"><span data-stu-id="a6a9e-120">Director</span></span></p></td>
<td><p><span data-ttu-id="a6a9e-121">Protocolo de inicio de sesión (SIP) entrante de la interfaz perimetral interna del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="a6a9e-121">Inbound session initiation protocol (SIP) from the internal Edge interface of the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6a9e-122">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="a6a9e-122">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="a6a9e-123">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a6a9e-123">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="a6a9e-124">Director</span><span class="sxs-lookup"><span data-stu-id="a6a9e-124">Director</span></span></p></td>
<td><p><span data-ttu-id="a6a9e-125">Servicios Web de marcado publicados desde el proxy inverso</span><span class="sxs-lookup"><span data-stu-id="a6a9e-125">Published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6a9e-126">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="a6a9e-126">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="a6a9e-127">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a6a9e-127">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="a6a9e-128">Director</span><span class="sxs-lookup"><span data-stu-id="a6a9e-128">Director</span></span></p></td>
<td><p><span data-ttu-id="a6a9e-129">Se publicaron los servicios web desde el proxy inverso</span><span class="sxs-lookup"><span data-stu-id="a6a9e-129">Published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6a9e-130">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="a6a9e-130">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="a6a9e-131">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a6a9e-131">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="a6a9e-132">Director</span><span class="sxs-lookup"><span data-stu-id="a6a9e-132">Director</span></span></p></td>
<td><p><span data-ttu-id="a6a9e-133">Publicado y definido por los servicios web externos de vale Web de proxy inverso para el director</span><span class="sxs-lookup"><span data-stu-id="a6a9e-133">Published and defined by the reverse proxy Web Ticket external web services for the Director</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

