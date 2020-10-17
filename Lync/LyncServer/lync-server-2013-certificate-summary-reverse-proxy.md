---
title: 'Lync Server 2013: Resumen del certificado-proxy inverso'
description: 'Lync Server 2013: Resumen del certificado-proxy inverso.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Reverse proxy
ms:assetid: f2b9a53f-aead-413d-81e9-4a294a010fbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205381(v=OCS.15)
ms:contentKeyID: 48185820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cc250d6de2eb1a0b6c3ad3495c8df62942f9a81
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572306"
---
# <a name="certificate-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="a8304-103">Resumen de certificado-proxy inverso en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8304-103">Certificate summary - Reverse proxy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8304-104">_**Última modificación del tema:** 2012-11-14_</span><span class="sxs-lookup"><span data-stu-id="a8304-104">_**Topic Last Modified:** 2012-11-14_</span></span>

<span data-ttu-id="a8304-105">Los requisitos de certificado para el proxy inverso son mucho más simples que los de los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="a8304-105">Certificate requirements for the reverse proxy are much simpler than that for the Edge Servers.</span></span> <span data-ttu-id="a8304-106">El diagrama de flujo proporcionado muestra los requisitos necesarios.</span><span class="sxs-lookup"><span data-stu-id="a8304-106">The provided flowchart presents the requirements necessary.</span></span> <span data-ttu-id="a8304-107">La tabla adjunta presenta los nombres de sujeto de certificado típicos y los nombres alternativos de sujeto en relación con los escenarios que se han revisado en las discusiones del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="a8304-107">The accompanying table presents typical certificate subject name and subject alternative names in relation to the scenarios that we have been reviewed in the Edge Server discussions.</span></span> <span data-ttu-id="a8304-108">Para obtener más información sobre los escenarios del servidor perimetral, consulte [escenarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="a8304-108">For more details on the Edge Server scenarios, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="a8304-109">**Diagrama de flujo de certificados para proxy inverso**</span><span class="sxs-lookup"><span data-stu-id="a8304-109">**Certificates Flow Chart for Reverse Proxy**</span></span>

<span data-ttu-id="a8304-110">![Diagrama de flujo de certificados para servidores perimetrales](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Diagrama de flujo de certificados para servidores perimetrales")</span><span class="sxs-lookup"><span data-stu-id="a8304-110">![Certificates Flow Chart for Edge Server](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Certificates Flow Chart for Edge Server")</span></span>

### <a name="reverse-proxy-external-interface"></a><span data-ttu-id="a8304-111">Proxy inverso: Interfaz externa</span><span class="sxs-lookup"><span data-stu-id="a8304-111">Reverse Proxy: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a8304-112">Componente</span><span class="sxs-lookup"><span data-stu-id="a8304-112">Component</span></span></th>
<th><span data-ttu-id="a8304-113">Nombre de sujeto</span><span class="sxs-lookup"><span data-stu-id="a8304-113">Subject name</span></span></th>
<th><span data-ttu-id="a8304-114">Nombre alternativo del sujeto (SAN)/orden</span><span class="sxs-lookup"><span data-stu-id="a8304-114">Subject alternative name (SAN)/Order</span></span></th>
<th><span data-ttu-id="a8304-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a8304-115">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a8304-116">Proxy inverso</span><span class="sxs-lookup"><span data-stu-id="a8304-116">Reverse Proxy</span></span></p></td>
<td><p><span data-ttu-id="a8304-117">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a8304-117">webext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="a8304-118">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a8304-118">webext.contoso.com</span></span></p>
<p><span data-ttu-id="a8304-119">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a8304-119">webdirext.contoso.com</span></span></p>
<p><span data-ttu-id="a8304-120">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a8304-120">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="a8304-121">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a8304-121">meet.contoso.com</span></span></p>
<p><span data-ttu-id="a8304-122">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a8304-122">officewebapps01.contoso.com</span></span></p>
<p><span data-ttu-id="a8304-123">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a8304-123">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="a8304-124">(Opcional):\*. contoso.com</span><span class="sxs-lookup"><span data-stu-id="a8304-124">(Optional):\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="a8304-125">Una entidad emisora de certificados debe otorgar el certificado junto con el servidor EKU.</span><span class="sxs-lookup"><span data-stu-id="a8304-125">Certificate must be issued by a public CA and with the server EKU.</span></span> <span data-ttu-id="a8304-126">Los servicios incluyen el servicio de libreta de direcciones, la expansión de grupos de distribución Office Web apps for Conferencing y las reglas de publicación de dispositivos IP de Lync.</span><span class="sxs-lookup"><span data-stu-id="a8304-126">Services include Address Book Service, distribution group expansion Office Web Apps for conferencing, and Lync IP Device publishing rules.</span></span> <span data-ttu-id="a8304-127">Los nombres alternativos del sujeto incluyen:</span><span class="sxs-lookup"><span data-stu-id="a8304-127">Subject alternative name includes:</span></span></p>
<ul>
<li><p><span data-ttu-id="a8304-128">FQDN de servicios web externos para el servidor front-end o el grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="a8304-128">External Web Services FQDN for Front End Server or Front End pool</span></span></p></li>
<li><p><span data-ttu-id="a8304-129">FQDN de servicios web externos para el director o el grupo de directores</span><span class="sxs-lookup"><span data-stu-id="a8304-129">External Web Services FQDN for Director or Director pool</span></span></p></li>
<li><p><span data-ttu-id="a8304-130">Conferencia de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="a8304-130">Dial-in conferencing</span></span></p></li>
<li><p><span data-ttu-id="a8304-131">Regla de publicación de reunión en línea</span><span class="sxs-lookup"><span data-stu-id="a8304-131">Online meeting publishing rule</span></span></p></li>
<li><p><span data-ttu-id="a8304-132">Office Web Apps para conferencias</span><span class="sxs-lookup"><span data-stu-id="a8304-132">Office Web Apps for conferencing</span></span></p></li>
<li><p><span data-ttu-id="a8304-133">Lyncdiscover (Autodiscover)</span><span class="sxs-lookup"><span data-stu-id="a8304-133">Lyncdiscover (Autodiscover)</span></span></p></li>
</ul>
<p><span data-ttu-id="a8304-134">El carácter comodín opcional sustituye tanto la SAN de reuniones, como de marcado</span><span class="sxs-lookup"><span data-stu-id="a8304-134">The optional wildcard replaces both meet and dialin SAN</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

