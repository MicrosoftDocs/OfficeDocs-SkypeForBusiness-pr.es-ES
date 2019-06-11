---
title: 'Lync Server 2013: vista conferencias'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conferences view
ms:assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721871(v=OCS.15)
ms:contentKeyID: 49733803
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 710aadb2770e9389d9e4becf206d68b8e8d815ee
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842486"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferences-view-in-lync-server-2013"></a><span data-ttu-id="34c93-102">Vista conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34c93-102">Conferences view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34c93-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="34c93-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="34c93-104">La vista conferencias almacena información sobre las conferencias.</span><span class="sxs-lookup"><span data-stu-id="34c93-104">The Conferences View stores information about the conferences.</span></span> <span data-ttu-id="34c93-105">Esta vista se presentó en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="34c93-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="34c93-106">Columna</span><span class="sxs-lookup"><span data-stu-id="34c93-106">Column</span></span></th>
<th><span data-ttu-id="34c93-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="34c93-107">Data Type</span></span></th>
<th><span data-ttu-id="34c93-108">Detalles</span><span class="sxs-lookup"><span data-stu-id="34c93-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="34c93-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="34c93-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="34c93-110">datetime</span><span class="sxs-lookup"><span data-stu-id="34c93-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="34c93-111">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="34c93-111">Time of session request.</span></span> <span data-ttu-id="34c93-112">Se usa en conjunción con SessionIdSeq para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="34c93-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="34c93-113">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="34c93-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34c93-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="34c93-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="34c93-115">int</span><span class="sxs-lookup"><span data-stu-id="34c93-115">int</span></span></p></td>
<td><p><span data-ttu-id="34c93-116">Número de identificación para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="34c93-116">ID number to identify the session.</span></span> <span data-ttu-id="34c93-117">Se usa en conjunción con SessionIdTime para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="34c93-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="34c93-118">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="34c93-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34c93-119"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="34c93-119"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="34c93-120">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="34c93-120">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="34c93-121">URI de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="34c93-121">URI for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34c93-122"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="34c93-122"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="34c93-123">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="34c93-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="34c93-124">Tipo de URI de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="34c93-124">Type of the conference URI.</span></span> <span data-ttu-id="34c93-125">Para obtener más información, consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="34c93-125">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34c93-126"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="34c93-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="34c93-127">identificador</span><span class="sxs-lookup"><span data-stu-id="34c93-127">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="34c93-128">Se usa para conferencias periódicas.</span><span class="sxs-lookup"><span data-stu-id="34c93-128">Used for recurring conferences.</span></span> <span data-ttu-id="34c93-129">Cada instancia de una conferencia periódica tiene el mismo ConferenceUri pero un ConfInstance diferente.</span><span class="sxs-lookup"><span data-stu-id="34c93-129">Each instance of a recurring conference has the same ConferenceUri but a different ConfInstance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34c93-130"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="34c93-130"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="34c93-131">datetime</span><span class="sxs-lookup"><span data-stu-id="34c93-131">datetime</span></span></p></td>
<td><p><span data-ttu-id="34c93-132">Hora de inicio de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="34c93-132">Starting time for the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34c93-133"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="34c93-133"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="34c93-134">datetime</span><span class="sxs-lookup"><span data-stu-id="34c93-134">datetime</span></span></p></td>
<td><p><span data-ttu-id="34c93-135">Hora de finalización de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="34c93-135">Ending time for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34c93-136"><strong>OrganizerUri</strong></span><span class="sxs-lookup"><span data-stu-id="34c93-136"><strong>OrganizerUri</strong></span></span></p></td>
<td><p><span data-ttu-id="34c93-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="34c93-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="34c93-138">Identificador URI del usuario que organizó la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="34c93-138">URI of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34c93-139"><strong>OrganizerType</strong></span><span class="sxs-lookup"><span data-stu-id="34c93-139"><strong>OrganizerType</strong></span></span></p></td>
<td><p><span data-ttu-id="34c93-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="34c93-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="34c93-141">Tipo de URI del usuario que organizó la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="34c93-141">Type of URI of the user who organized the conference.</span></span> <span data-ttu-id="34c93-142">Para obtener más información, consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="34c93-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34c93-143"><strong>OrganizerTenant</strong></span><span class="sxs-lookup"><span data-stu-id="34c93-143"><strong>OrganizerTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="34c93-144">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="34c93-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="34c93-145">Espacio empresarial del usuario que organizó la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="34c93-145">Tenant of the user who organized the conference.</span></span> <span data-ttu-id="34c93-146">Para obtener más información, consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos de Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="34c93-146">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34c93-147"><strong>Grupo</strong></span><span class="sxs-lookup"><span data-stu-id="34c93-147"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="34c93-148">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="34c93-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="34c93-149">Nombre de dominio completo del grupo que ha hospedado la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="34c93-149">Fully qualified domain name of the pool that hosted the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34c93-150"><strong>Fdisableautoindexingonschemaupdate</strong></span><span class="sxs-lookup"><span data-stu-id="34c93-150"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="34c93-151">smallint</span><span class="sxs-lookup"><span data-stu-id="34c93-151">smallint</span></span></p></td>
<td><p><span data-ttu-id="34c93-152">Máscara de bits que contiene atributos de conferencia.</span><span class="sxs-lookup"><span data-stu-id="34c93-152">Bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="34c93-153">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="34c93-153">Possible values are:</span></span></p>
<p><span data-ttu-id="34c93-154">0X01: transacción sintética</span><span class="sxs-lookup"><span data-stu-id="34c93-154">0X01 – Synthetic Transaction</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

