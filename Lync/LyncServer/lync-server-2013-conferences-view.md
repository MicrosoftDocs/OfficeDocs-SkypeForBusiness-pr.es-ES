---
title: 'Lync Server 2013: vista conferencias'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferences view
ms:assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721871(v=OCS.15)
ms:contentKeyID: 49733803
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36278c1053c2b5737e0de6caf914c050db93ea4b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741610"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferences-view-in-lync-server-2013"></a><span data-ttu-id="328b5-102">Vista conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="328b5-102">Conferences view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="328b5-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="328b5-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="328b5-104">La vista conferencias almacena información sobre las conferencias.</span><span class="sxs-lookup"><span data-stu-id="328b5-104">The Conferences View stores information about the conferences.</span></span> <span data-ttu-id="328b5-105">Esta vista se presentó en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="328b5-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="328b5-106">Columna</span><span class="sxs-lookup"><span data-stu-id="328b5-106">Column</span></span></th>
<th><span data-ttu-id="328b5-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="328b5-107">Data Type</span></span></th>
<th><span data-ttu-id="328b5-108">Detalles</span><span class="sxs-lookup"><span data-stu-id="328b5-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="328b5-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="328b5-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="328b5-110">datetime</span><span class="sxs-lookup"><span data-stu-id="328b5-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="328b5-111">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="328b5-111">Time of session request.</span></span> <span data-ttu-id="328b5-112">Se usa en conjunción con SessionIdSeq para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="328b5-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="328b5-113">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="328b5-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="328b5-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="328b5-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="328b5-115">int</span><span class="sxs-lookup"><span data-stu-id="328b5-115">int</span></span></p></td>
<td><p><span data-ttu-id="328b5-116">Número de identificación para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="328b5-116">ID number to identify the session.</span></span> <span data-ttu-id="328b5-117">Se usa en conjunción con SessionIdTime para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="328b5-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="328b5-118">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="328b5-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="328b5-119"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="328b5-119"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="328b5-120">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="328b5-120">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="328b5-121">URI de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="328b5-121">URI for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="328b5-122"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="328b5-122"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="328b5-123">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="328b5-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="328b5-124">Tipo de URI de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="328b5-124">Type of the conference URI.</span></span> <span data-ttu-id="328b5-125">Para obtener más información, consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="328b5-125">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="328b5-126"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="328b5-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="328b5-127">identificador</span><span class="sxs-lookup"><span data-stu-id="328b5-127">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="328b5-128">Se usa para conferencias periódicas.</span><span class="sxs-lookup"><span data-stu-id="328b5-128">Used for recurring conferences.</span></span> <span data-ttu-id="328b5-129">Cada instancia de una conferencia periódica tiene el mismo ConferenceUri pero un ConfInstance diferente.</span><span class="sxs-lookup"><span data-stu-id="328b5-129">Each instance of a recurring conference has the same ConferenceUri but a different ConfInstance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="328b5-130"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="328b5-130"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="328b5-131">datetime</span><span class="sxs-lookup"><span data-stu-id="328b5-131">datetime</span></span></p></td>
<td><p><span data-ttu-id="328b5-132">Hora de inicio de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="328b5-132">Starting time for the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="328b5-133"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="328b5-133"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="328b5-134">datetime</span><span class="sxs-lookup"><span data-stu-id="328b5-134">datetime</span></span></p></td>
<td><p><span data-ttu-id="328b5-135">Hora de finalización de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="328b5-135">Ending time for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="328b5-136"><strong>OrganizerUri</strong></span><span class="sxs-lookup"><span data-stu-id="328b5-136"><strong>OrganizerUri</strong></span></span></p></td>
<td><p><span data-ttu-id="328b5-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="328b5-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="328b5-138">Identificador URI del usuario que organizó la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="328b5-138">URI of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="328b5-139"><strong>OrganizerType</strong></span><span class="sxs-lookup"><span data-stu-id="328b5-139"><strong>OrganizerType</strong></span></span></p></td>
<td><p><span data-ttu-id="328b5-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="328b5-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="328b5-141">Tipo de URI del usuario que organizó la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="328b5-141">Type of URI of the user who organized the conference.</span></span> <span data-ttu-id="328b5-142">Para obtener más información, consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="328b5-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="328b5-143"><strong>OrganizerTenant</strong></span><span class="sxs-lookup"><span data-stu-id="328b5-143"><strong>OrganizerTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="328b5-144">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="328b5-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="328b5-145">Espacio empresarial del usuario que organizó la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="328b5-145">Tenant of the user who organized the conference.</span></span> <span data-ttu-id="328b5-146">Para obtener más información, consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos de Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="328b5-146">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="328b5-147"><strong>Grupo</strong></span><span class="sxs-lookup"><span data-stu-id="328b5-147"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="328b5-148">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="328b5-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="328b5-149">Nombre de dominio completo del grupo que ha hospedado la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="328b5-149">Fully qualified domain name of the pool that hosted the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="328b5-150"><strong>Fdisableautoindexingonschemaupdate</strong></span><span class="sxs-lookup"><span data-stu-id="328b5-150"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="328b5-151">smallint</span><span class="sxs-lookup"><span data-stu-id="328b5-151">smallint</span></span></p></td>
<td><p><span data-ttu-id="328b5-152">Máscara de bits que contiene atributos de conferencia.</span><span class="sxs-lookup"><span data-stu-id="328b5-152">Bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="328b5-153">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="328b5-153">Possible values are:</span></span></p>
<p><span data-ttu-id="328b5-154">0X01: transacción sintética</span><span class="sxs-lookup"><span data-stu-id="328b5-154">0X01 – Synthetic Transaction</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

