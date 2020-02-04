---
title: 'Lync Server 2013: Resumen DNS - Director único'
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
ms.openlocfilehash: 71fb3052de36a92afb4ed9076820f7fcb2b54997
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757584"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="51dd8-102">Resumen DNS - Director único en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51dd8-102">DNS summary - Single Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51dd8-103">_**Última modificación del tema:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="51dd8-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="51dd8-104">La tabla siguiente contiene un resumen de los registros DNS necesarios para admitir un único Director.</span><span class="sxs-lookup"><span data-stu-id="51dd8-104">The following table contains a summary of the DNS records that are required to support the single Director.</span></span> <span data-ttu-id="51dd8-105">La función del Director requiere registros DNS similares como servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="51dd8-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="51dd8-106">El número de registros necesarios se refleja en el asunto nombres alternativos requeridos en el certificado de director.</span><span class="sxs-lookup"><span data-stu-id="51dd8-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="51dd8-107">Diferente del servidor front-end, el director no hospeda cuentas de usuario ni hospeda los servicios de movilidad.</span><span class="sxs-lookup"><span data-stu-id="51dd8-107">Different from the Front End Server, the Director does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director"></a><span data-ttu-id="51dd8-108">Registros DNS necesarios para el director</span><span class="sxs-lookup"><span data-stu-id="51dd8-108">DNS Records Required for the Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="51dd8-109">Ubicación/tipo/puerto</span><span class="sxs-lookup"><span data-stu-id="51dd8-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="51dd8-110">FQDN/registro DNS</span><span class="sxs-lookup"><span data-stu-id="51dd8-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="51dd8-111">Dirección IP/FQDN</span><span class="sxs-lookup"><span data-stu-id="51dd8-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="51dd8-112">Se asigna a/comentarios</span><span class="sxs-lookup"><span data-stu-id="51dd8-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="51dd8-113">DNS/A interno</span><span class="sxs-lookup"><span data-stu-id="51dd8-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="51dd8-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="51dd8-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="51dd8-115">Director</span><span class="sxs-lookup"><span data-stu-id="51dd8-115">Director</span></span></p></td>
<td><p><span data-ttu-id="51dd8-116">Registro de host de Director usado para la replicación y el servidor a servidor</span><span class="sxs-lookup"><span data-stu-id="51dd8-116">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51dd8-117">DNS/A interno</span><span class="sxs-lookup"><span data-stu-id="51dd8-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="51dd8-118">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="51dd8-118">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="51dd8-119">Director</span><span class="sxs-lookup"><span data-stu-id="51dd8-119">Director</span></span></p></td>
<td><p><span data-ttu-id="51dd8-120">Protocolo de inicio de sesión (SIP) entrante de la interfaz de borde interno del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="51dd8-120">Inbound session initiation protocol (SIP) from the internal Edge interface of the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51dd8-121">DNS/A interno</span><span class="sxs-lookup"><span data-stu-id="51dd8-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="51dd8-122">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="51dd8-122">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="51dd8-123">Director</span><span class="sxs-lookup"><span data-stu-id="51dd8-123">Director</span></span></p></td>
<td><p><span data-ttu-id="51dd8-124">Servicios Web de marcado publicados desde proxy inverso</span><span class="sxs-lookup"><span data-stu-id="51dd8-124">Published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51dd8-125">DNS/A interno</span><span class="sxs-lookup"><span data-stu-id="51dd8-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="51dd8-126">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="51dd8-126">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="51dd8-127">Director</span><span class="sxs-lookup"><span data-stu-id="51dd8-127">Director</span></span></p></td>
<td><p><span data-ttu-id="51dd8-128">Se han publicado los servicios web desde un proxy inverso</span><span class="sxs-lookup"><span data-stu-id="51dd8-128">Published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51dd8-129">DNS/A interno</span><span class="sxs-lookup"><span data-stu-id="51dd8-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="51dd8-130">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="51dd8-130">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="51dd8-131">Director</span><span class="sxs-lookup"><span data-stu-id="51dd8-131">Director</span></span></p></td>
<td><p><span data-ttu-id="51dd8-132">Publicado y definido por el vale Web de proxy inverso servicios web externos para el director</span><span class="sxs-lookup"><span data-stu-id="51dd8-132">Published and defined by the reverse proxy Web Ticket external web services for the Director</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

