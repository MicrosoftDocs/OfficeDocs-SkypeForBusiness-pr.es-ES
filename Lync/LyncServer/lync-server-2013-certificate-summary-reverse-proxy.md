---
title: 'Lync Server 2013: Resumen de certificado - Proxy inverso'
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
ms.openlocfilehash: 42e52fa8522de53404fee3f3b5798f159361dbf5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736620"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="798a3-102">Resumen de certificado - Proxy inverso en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="798a3-102">Certificate summary - Reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="798a3-103">_**Última modificación del tema:** 2012-11-14_</span><span class="sxs-lookup"><span data-stu-id="798a3-103">_**Topic Last Modified:** 2012-11-14_</span></span>

<span data-ttu-id="798a3-104">Los requisitos de certificados para el proxy inverso son mucho más simples que el de los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="798a3-104">Certificate requirements for the reverse proxy are much simpler than that for the Edge Servers.</span></span> <span data-ttu-id="798a3-105">El diagrama de flujo proporcionado presenta los requisitos necesarios.</span><span class="sxs-lookup"><span data-stu-id="798a3-105">The provided flowchart presents the requirements necessary.</span></span> <span data-ttu-id="798a3-106">La tabla adjunta presenta el nombre de asunto del certificado y los nombres alternativos del sujeto típicos en relación con los escenarios que hemos revisado en las discusiones del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="798a3-106">The accompanying table presents typical certificate subject name and subject alternative names in relation to the scenarios that we have been reviewed in the Edge Server discussions.</span></span> <span data-ttu-id="798a3-107">Para obtener más información sobre los escenarios del servidor perimetral, consulte [escenarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="798a3-107">For more details on the Edge Server scenarios, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="798a3-108">**Diagrama de flujo de certificados para el proxy inverso**</span><span class="sxs-lookup"><span data-stu-id="798a3-108">**Certificates Flow Chart for Reverse Proxy**</span></span>

<span data-ttu-id="798a3-109">![Diagrama de flujo de certificados para el servidor perimetral](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Diagrama de flujo de certificados para el servidor perimetral")</span><span class="sxs-lookup"><span data-stu-id="798a3-109">![Certificates Flow Chart for Edge Server](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Certificates Flow Chart for Edge Server")</span></span>

### <a name="reverse-proxy-external-interface"></a><span data-ttu-id="798a3-110">Proxy inverso: interfaz externa</span><span class="sxs-lookup"><span data-stu-id="798a3-110">Reverse Proxy: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="798a3-111">Componente</span><span class="sxs-lookup"><span data-stu-id="798a3-111">Component</span></span></th>
<th><span data-ttu-id="798a3-112">Nombre del asunto</span><span class="sxs-lookup"><span data-stu-id="798a3-112">Subject name</span></span></th>
<th><span data-ttu-id="798a3-113">Nombre alternativo de asunto (SAN)/Order</span><span class="sxs-lookup"><span data-stu-id="798a3-113">Subject alternative name (SAN)/Order</span></span></th>
<th><span data-ttu-id="798a3-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="798a3-114">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="798a3-115">Proxy inverso</span><span class="sxs-lookup"><span data-stu-id="798a3-115">Reverse Proxy</span></span></p></td>
<td><p><span data-ttu-id="798a3-116">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="798a3-116">webext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="798a3-117">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="798a3-117">webext.contoso.com</span></span></p>
<p><span data-ttu-id="798a3-118">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="798a3-118">webdirext.contoso.com</span></span></p>
<p><span data-ttu-id="798a3-119">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="798a3-119">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="798a3-120">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="798a3-120">meet.contoso.com</span></span></p>
<p><span data-ttu-id="798a3-121">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="798a3-121">officewebapps01.contoso.com</span></span></p>
<p><span data-ttu-id="798a3-122">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="798a3-122">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="798a3-123">(Opcional):\*. contoso.com</span><span class="sxs-lookup"><span data-stu-id="798a3-123">(Optional):\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="798a3-124">El certificado debe ser emitido por una entidad de certificación pública y con el EKU de servidor.</span><span class="sxs-lookup"><span data-stu-id="798a3-124">Certificate must be issued by a public CA and with the server EKU.</span></span> <span data-ttu-id="798a3-125">Los servicios incluyen el servicio de libreta de direcciones, Office Web Apps para conferencias y las reglas de publicación de dispositivos IP de Lync.</span><span class="sxs-lookup"><span data-stu-id="798a3-125">Services include Address Book Service, distribution group expansion Office Web Apps for conferencing, and Lync IP Device publishing rules.</span></span> <span data-ttu-id="798a3-126">El nombre alternativo del firmante incluye:</span><span class="sxs-lookup"><span data-stu-id="798a3-126">Subject alternative name includes:</span></span></p>
<ul>
<li><p><span data-ttu-id="798a3-127">FQDN de servicios web externos para servidor front-end o grupo front-end</span><span class="sxs-lookup"><span data-stu-id="798a3-127">External Web Services FQDN for Front End Server or Front End pool</span></span></p></li>
<li><p><span data-ttu-id="798a3-128">FQDN de servicios web externos para el grupo de directores o directores</span><span class="sxs-lookup"><span data-stu-id="798a3-128">External Web Services FQDN for Director or Director pool</span></span></p></li>
<li><p><span data-ttu-id="798a3-129">Conferencia de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="798a3-129">Dial-in conferencing</span></span></p></li>
<li><p><span data-ttu-id="798a3-130">Regla de publicación de reuniones en línea</span><span class="sxs-lookup"><span data-stu-id="798a3-130">Online meeting publishing rule</span></span></p></li>
<li><p><span data-ttu-id="798a3-131">Office Web Apps para conferencias</span><span class="sxs-lookup"><span data-stu-id="798a3-131">Office Web Apps for conferencing</span></span></p></li>
<li><p><span data-ttu-id="798a3-132">Lyncdiscover (detección automática)</span><span class="sxs-lookup"><span data-stu-id="798a3-132">Lyncdiscover (Autodiscover)</span></span></p></li>
</ul>
<p><span data-ttu-id="798a3-133">El comodín opcional reemplaza a reunirse y a través de SAN</span><span class="sxs-lookup"><span data-stu-id="798a3-133">The optional wildcard replaces both meet and dialin SAN</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

