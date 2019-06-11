---
title: 'Lync Server 2013: Tabla SessionDetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SessionDetails table
ms:assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398589(v=OCS.15)
ms:contentKeyID: 48184559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: faebef9ad03370c2fa969d3b119f13b88d1d3173
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822114"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="e0e8b-102">Tabla SessionDetails en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0e8b-102">SessionDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0e8b-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="e0e8b-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="e0e8b-104">Cada registro representa una sesión de punto a punto, que puede ser una llamada de teléfono VoIP-VoIP, una sesión de mi de dos partes u otro tipo de sesión.</span><span class="sxs-lookup"><span data-stu-id="e0e8b-104">Each record represents one peer-to-peer session, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="e0e8b-105">Puede realizar una combinación de tabla con la [tabla multimedia en Lync Server 2013](lync-server-2013-media-table.md) para buscar los detalles de cada elemento multimedia implicado en esta sesión.</span><span class="sxs-lookup"><span data-stu-id="e0e8b-105">You can perform a table join with the [Media table in Lync Server 2013](lync-server-2013-media-table.md) to find the details of each media involved in this session.</span></span>

<span data-ttu-id="e0e8b-106">Observe que los campos IsUser1IntegratedWithDeskPhone y IsUser2IntegratedWithDeskPhone se han quitado de la tabla SessionDetails que se usa en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e0e8b-106">Note that the IsUser1IntegratedWithDeskPhone and the IsUser2IntegratedWithDeskPhone fields have been dropped from the SessionDetails table used in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e0e8b-107">Columna</span><span class="sxs-lookup"><span data-stu-id="e0e8b-107">Column</span></span></th>
<th><span data-ttu-id="e0e8b-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="e0e8b-108">Data Type</span></span></th>
<th><span data-ttu-id="e0e8b-109">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="e0e8b-109">Key/Index</span></span></th>
<th><span data-ttu-id="e0e8b-110">Detalles</span><span class="sxs-lookup"><span data-stu-id="e0e8b-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0e8b-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="e0e8b-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e0e8b-112">datetime</span><span class="sxs-lookup"><span data-stu-id="e0e8b-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="e0e8b-113">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="e0e8b-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e0e8b-114">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="e0e8b-114">Time of session request.</span></span> <span data-ttu-id="e0e8b-115">Se usa en conjunción con <strong>SessionIdSeq</strong> para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="e0e8b-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="e0e8b-116">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e0e8b-116">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0e8b-117"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e0e8b-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e0e8b-118">int</span><span class="sxs-lookup"><span data-stu-id="e0e8b-118">int</span></span></p></td>
<td><p><span data-ttu-id="e0e8b-119">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="e0e8b-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e0e8b-120">Número de identificación para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="e0e8b-120">ID number to identify the session.</span></span> <span data-ttu-id="e0e8b-121">Se usa junto con <strong>SessionIdTime</strong> para identificar de forma única una sesión. \* para obtener más información, consulta la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e0e8b-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.\* See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0e8b-122"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="e0e8b-122"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="e0e8b-123">identificador</span><span class="sxs-lookup"><span data-stu-id="e0e8b-123">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e0e8b-124">Un GUID para correlacionar varias sesiones.</span><span class="sxs-lookup"><span data-stu-id="e0e8b-124">A GUID to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0e8b-125"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="e0e8b-125"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e0e8b-126">datetime</span><span class="sxs-lookup"><span data-stu-id="e0e8b-126">datetime</span></span></p></td>
<td><p><span data-ttu-id="e0e8b-127">Extranjero</span><span class="sxs-lookup"><span data-stu-id="e0e8b-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e0e8b-128">Número de identificación para identificar el cuadro de diálogo que se reemplazó por la sesión actual.</span><span class="sxs-lookup"><span data-stu-id="e0e8b-128">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="e0e8b-129">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e0e8b-129">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0e8b-130"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e0e8b-130"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e0e8b-131">int</span><span class="sxs-lookup"><span data-stu-id="e0e8b-131">int</span></span></p></td>
<td><p><span data-ttu-id="e0e8b-132">Extranjero</span><span class="sxs-lookup"><span data-stu-id="e0e8b-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e0e8b-133">Número de identificación para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="e0e8b-133">ID number to identify the session.</span></span> <span data-ttu-id="e0e8b-134">Se usa junto con <strong>ReplacesDialogIdTime</strong> para identificar de forma única una sesión que se reemplaza por esta sesión.</span><span class="sxs-lookup"><span data-stu-id="e0e8b-134">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="e0e8b-135">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e0e8b-135">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0e8b-136"><strong>User1Id</strong></span><span class="sxs-lookup"><span data-stu-id="e0e8b-136"><strong>User1Id</strong></span></span></p></td>
<td><p><span data-ttu-id="e0e8b-137">int</span><span class="sxs-lookup"><span data-stu-id="e0e8b-137">int</span></span></p></td>
<td><p><span data-ttu-id="e0e8b-138">Extranjero</span><span class="sxs-lookup"><span data-stu-id="e0e8b-138">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e0e8b-139">IDENTIFICADOR de un usuario de la sesión.</span><span class="sxs-lookup"><span data-stu-id="e0e8b-139">ID of one user in the session.</span></span> <span data-ttu-id="e0e8b-140">Para obtener más información, consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e0e8b-140">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0e8b-141"><strong>User2Id</strong></span><span class="sxs-lookup"><span data-stu-id="e0e8b-141"><strong>User2Id</strong></span></span></p></td>
<td><p><span data-ttu-id="e0e8b-142">int</span><span class="sxs-lookup"><span data-stu-id="e0e8b-142">int</span></span></p></td>
<td><p><span data-ttu-id="e0e8b-143">Extranjero</span><span class="sxs-lookup"><span data-stu-id="e0e8b-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e0e8b-144">IDENTIFICADOR del otro usuario de la sesión.</span><span class="sxs-lookup"><span data-stu-id="e0e8b-144">ID of the other user in the session.</span></span> <span data-ttu-id="e0e8b-145">Para obtener más información, consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e0e8b-145">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0e8b-146"><strong>User1EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="e0e8b-146"><strong>User1EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="e0e8b-147">Identificador</span><span class="sxs-lookup"><span data-stu-id="e0e8b-147">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e0e8b-148">GUID que identifica el extremo utilizado por el primer usuario de la sesión.</span><span class="sxs-lookup"><span data-stu-id="e0e8b-148">GUID that identifies the endpoint used by the first user in the session.</span></span></p>
<p><span data-ttu-id="e0e8b-149">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e0e8b-149">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0e8b-150"><strong>User2EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="e0e8b-150"><strong>User2EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="e0e8b-151">Identificador</span><span class="sxs-lookup"><span data-stu-id="e0e8b-151">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e0e8b-152">GUID que identifica el extremo usado por el segundo usuario de la sesión.</span><span class="sxs-lookup"><span data-stu-id="e0e8b-152">GUID that identifies the endpoint used by the second user in the session.</span></span></p>
<p><span data-ttu-id="e0e8b-153">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e0e8b-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0e8b-154"><strong>TargetUserId</strong></span><span class="sxs-lookup"><span data-stu-id="e0e8b-154"><strong>TargetUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="e0e8b-155">int</span><span class="sxs-lookup"><span data-stu-id="e0e8b-155">int</span></span></p></td>
<td><p><span data-ttu-id="e0e8b-156">Extranjero</span><span class="sxs-lookup"><span data-stu-id="e0e8b-156">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e0e8b-157">El URI del usuario original para la solicitud SIP.</span><span class="sxs-lookup"><span data-stu-id="e0e8b-157">The original To user URI in the SIP request.</span></span> <span data-ttu-id="e0e8b-158">para obtener más información, consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e0e8b-158">see the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0e8b-159"><strong>SessionStartedById</strong></span><span class="sxs-lookup"><span data-stu-id="e0e8b-159"><strong>SessionStartedById</strong></span></span></p></td>
<td><p><span data-ttu-id="e0e8b-160">int</span><span class="sxs-lookup"><span data-stu-id="e0e8b-160">int</span></span></p></td>
<td><p><span data-ttu-id="e0e8b-161">Extranjero</span><span class="sxs-lookup"><span data-stu-id="e0e8b-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e0e8b-162">IDENTIFICADOR del usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="e0e8b-162">ID of the user who started the session.</span></span> <span data-ttu-id="e0e8b-163">Para obtener más información, consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e0e8b-163">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0e8b-164"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="e0e8b-164"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="e0e8b-165">int</span><span class="sxs-lookup"><span data-stu-id="e0e8b-165">int</span></span></p></td>
<td><p><span data-ttu-id="e0e8b-166">Extranjero</span><span class="sxs-lookup"><span data-stu-id="e0e8b-166">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e0e8b-167">Indica el identificador del usuario de la persona que llama en nombre.</span><span class="sxs-lookup"><span data-stu-id="e0e8b-167">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="e0e8b-168">Para obtener más información, consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e0e8b-168">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0e8b-169"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="e0e8b-169"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="e0e8b-170">int</span><span class="sxs-lookup"><span data-stu-id="e0e8b-170">int</span></span></p></td>
<td><p><span data-ttu-id="e0e8b-171">Extranjero</span><span class="sxs-lookup"><span data-stu-id="e0e8b-171">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e0e8b-172">IDENTIFICADOR del usuario al que hace referencia la llamada.</span><span class="sxs-lookup"><span data-stu-id="e0e8b-172">ID of the user by who the call is referred.</span></span> <span data-ttu-id="e0e8b-173">Para obtener más información, consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e0e8b-173">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0e8b-174"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="e0e8b-174"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="e0e8b-175">int</span><span class="sxs-lookup"><span data-stu-id="e0e8b-175">int</span></span></p></td>
<td><p><span data-ttu-id="e0e8b-176">Extranjero</span><span class="sxs-lookup"><span data-stu-id="e0e8b-176">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e0e8b-177">IDENTIFICADOR del servidor front-end usado para esta sesión.</span><span class="sxs-lookup"><span data-stu-id="e0e8b-177">ID of the front-end server used for this session.</span></span> <span data-ttu-id="e0e8b-178">Para obtener más información, consulte la <a href="lync-server-2013-servers-table.md">tabla servidores en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e0e8b-178">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0e8b-179"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="e0e8b-179"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="e0e8b-180">int</span><span class="sxs-lookup"><span data-stu-id="e0e8b-180">int</span></span></p></td>
<td><p><span data-ttu-id="e0e8b-181">Extranjero</span><span class="sxs-lookup"><span data-stu-id="e0e8b-181">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e0e8b-182">IDENTIFICADOR del grupo en el que se capturó la sesión.</span><span class="sxs-lookup"><span data-stu-id="e0e8b-182">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="e0e8b-183">Para obtener más información, consulte la <a href="lync-server-2013-pools-table.md">tabla de grupos en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e0e8b-183">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0e8b-184"><strong>ContentTypeID</strong></span><span class="sxs-lookup"><span data-stu-id="e0e8b-184"><strong>ContentTypeID</strong></span></span></p></td>
<td><p><span data-ttu-id="e0e8b-185">int</span><span class="sxs-lookup"><span data-stu-id="e0e8b-185">int</span></span></p></td>
<td><p><span data-ttu-id="e0e8b-186">Extranjero</span><span class="sxs-lookup"><span data-stu-id="e0e8b-186">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e0e8b-187">Tipo de contenido usado en la sesión.</span><span class="sxs-lookup"><span data-stu-id="e0e8b-187">Content type used in the session.</span></span> <span data-ttu-id="e0e8b-188">Para obtener más información, consulte la <a href="lync-server-2013-contenttypes-table.md">tabla contentTypes en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e0e8b-188">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0e8b-189"><strong>User1ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="e0e8b-189"><strong>User1ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="e0e8b-190">int</span><span class="sxs-lookup"><span data-stu-id="e0e8b-190">int</span></span></p></td>
<td><p><span data-ttu-id="e0e8b-191">Extranjero</span><span class="sxs-lookup"><span data-stu-id="e0e8b-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e0e8b-192">Versión de cliente usada por el usuario1.</span><span class="sxs-lookup"><span data-stu-id="e0e8b-192">Client version used by User1.</span></span> <span data-ttu-id="e0e8b-193">Para obtener más información, consulte la <a href="lync-server-2013-clientversions-table.md">tabla ClientVersions en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e0e8b-193">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0e8b-194"><strong>User2ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="e0e8b-194"><strong>User2ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="e0e8b-195">int</span><span class="sxs-lookup"><span data-stu-id="e0e8b-195">int</span></span></p></td>
<td><p><span data-ttu-id="e0e8b-196">Extranjero</span><span class="sxs-lookup"><span data-stu-id="e0e8b-196">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e0e8b-197">Versión de cliente usada por usuario2.</span><span class="sxs-lookup"><span data-stu-id="e0e8b-197">Client version used by User2.</span></span> <span data-ttu-id="e0e8b-198">Para obtener más información, consulte la <a href="lync-server-2013-clientversions-table.md">tabla ClientVersions en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e0e8b-198">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0e8b-199"><strong>User1EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="e0e8b-199"><strong>User1EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="e0e8b-200">int</span><span class="sxs-lookup"><span data-stu-id="e0e8b-200">int</span></span></p></td>
<td><p><span data-ttu-id="e0e8b-201">Extranjero</span><span class="sxs-lookup"><span data-stu-id="e0e8b-201">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e0e8b-202">Servidor perimetral usado por el usuario1.</span><span class="sxs-lookup"><span data-stu-id="e0e8b-202">Edge Server used by User1.</span></span> <span data-ttu-id="e0e8b-203">Para obtener más información, consulte la <a href="lync-server-2013-edgeservers-table.md">tabla EdgeServers en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e0e8b-203">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0e8b-204"><strong>User2EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="e0e8b-204"><strong>User2EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="e0e8b-205">int</span><span class="sxs-lookup"><span data-stu-id="e0e8b-205">int</span></span></p></td>
<td><p><span data-ttu-id="e0e8b-206">Extranjero</span><span class="sxs-lookup"><span data-stu-id="e0e8b-206">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e0e8b-207">Servidor perimetral usado por usuario2.</span><span class="sxs-lookup"><span data-stu-id="e0e8b-207">Edge Server used by User2.</span></span> <span data-ttu-id="e0e8b-208">Para obtener más información, consulte la <a href="lync-server-2013-edgeservers-table.md">tabla EdgeServers en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e0e8b-208">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0e8b-209"><strong>IsUser1Internal</strong></span><span class="sxs-lookup"><span data-stu-id="e0e8b-209"><strong>IsUser1Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="e0e8b-210">bit</span><span class="sxs-lookup"><span data-stu-id="e0e8b-210">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e0e8b-211">Si user1 está conectado desde interno o no.</span><span class="sxs-lookup"><span data-stu-id="e0e8b-211">Whether User1 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0e8b-212"><strong>IsUser2Internal</strong></span><span class="sxs-lookup"><span data-stu-id="e0e8b-212"><strong>IsUser2Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="e0e8b-213">bit</span><span class="sxs-lookup"><span data-stu-id="e0e8b-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e0e8b-214">Si usuario2 está conectado desde interno o no.</span><span class="sxs-lookup"><span data-stu-id="e0e8b-214">Whether User2 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0e8b-215"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="e0e8b-215"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e0e8b-216">datetime</span><span class="sxs-lookup"><span data-stu-id="e0e8b-216">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e0e8b-217">La hora de la primera solicitud de invitación.</span><span class="sxs-lookup"><span data-stu-id="e0e8b-217">The time of the first INVITE request.</span></span> <span data-ttu-id="e0e8b-218">Por lo general, este campo se rellena con los datos generados desde el mensaje de invitación inicial de la sesión.</span><span class="sxs-lookup"><span data-stu-id="e0e8b-218">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="e0e8b-219">Si no hay ningún mensaje de invitación, el campo se rellena con la fecha y la hora del primer mensaje SIP pertinente (BYE, cancelar, mensaje o información).</span><span class="sxs-lookup"><span data-stu-id="e0e8b-219">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="e0e8b-220">Por lo general, este campo se rellena con los datos generados desde el mensaje de invitación inicial de la sesión.</span><span class="sxs-lookup"><span data-stu-id="e0e8b-220">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="e0e8b-221">Si no hay ningún mensaje de invitación, el campo se rellena con la fecha y la hora del primer mensaje SIP pertinente (BYE, cancelar, mensaje o información).</span><span class="sxs-lookup"><span data-stu-id="e0e8b-221">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0e8b-222"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="e0e8b-222"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e0e8b-223">datetime</span><span class="sxs-lookup"><span data-stu-id="e0e8b-223">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e0e8b-224">La hora de la respuesta al primer mensaje de invitación.</span><span class="sxs-lookup"><span data-stu-id="e0e8b-224">The time of the response to the first INVITE message.</span></span> <span data-ttu-id="e0e8b-225">Por lo general, este campo se rellena con los datos generados desde el mensaje de invitación inicial de la sesión.</span><span class="sxs-lookup"><span data-stu-id="e0e8b-225">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="e0e8b-226">Si no hay ningún mensaje de invitación, el campo se rellena con la fecha y la hora del primer mensaje SIP pertinente (BYE, cancelar, mensaje o información).</span><span class="sxs-lookup"><span data-stu-id="e0e8b-226">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0e8b-227"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="e0e8b-227"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="e0e8b-228">int</span><span class="sxs-lookup"><span data-stu-id="e0e8b-228">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e0e8b-229">Código de respuesta SIP a la invitación de la sesión.</span><span class="sxs-lookup"><span data-stu-id="e0e8b-229">SIP response code to the session invitation.</span></span> <span data-ttu-id="e0e8b-230">Por lo general, este campo se rellena con los datos generados desde el mensaje de invitación inicial de la sesión.</span><span class="sxs-lookup"><span data-stu-id="e0e8b-230">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="e0e8b-231">Si no hay ningún mensaje de invitación, el campo se rellena con la fecha y la hora del primer mensaje SIP pertinente (BYE, cancelar, mensaje o información).</span><span class="sxs-lookup"><span data-stu-id="e0e8b-231">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0e8b-232"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="e0e8b-232"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="e0e8b-233">int</span><span class="sxs-lookup"><span data-stu-id="e0e8b-233">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e0e8b-234">IDENTIFICACIÓN de diagnóstico capturada del encabezado de SIP.</span><span class="sxs-lookup"><span data-stu-id="e0e8b-234">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0e8b-235"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="e0e8b-235"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="e0e8b-236">int</span><span class="sxs-lookup"><span data-stu-id="e0e8b-236">int</span></span></p></td>
<td><p><span data-ttu-id="e0e8b-237">Extranjero</span><span class="sxs-lookup"><span data-stu-id="e0e8b-237">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e0e8b-238">Prioridad de la llamada.</span><span class="sxs-lookup"><span data-stu-id="e0e8b-238">Call priority.</span></span> <span data-ttu-id="e0e8b-239">Para obtener más información, consulte la <a href="lync-server-2013-callpriorities-table.md">tabla CallPriorities en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e0e8b-239">See the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0e8b-240"><strong>User1MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="e0e8b-240"><strong>User1MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="e0e8b-241">int</span><span class="sxs-lookup"><span data-stu-id="e0e8b-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e0e8b-242">Número de mensajes enviados por el usuario1 durante la sesión.</span><span class="sxs-lookup"><span data-stu-id="e0e8b-242">Number of messages sent by User1 during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0e8b-243"><strong>User2MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="e0e8b-243"><strong>User2MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="e0e8b-244">int</span><span class="sxs-lookup"><span data-stu-id="e0e8b-244">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e0e8b-245">Número de mensajes enviados por usuario2 durante la sesión.</span><span class="sxs-lookup"><span data-stu-id="e0e8b-245">Number of messages sent by User2 during the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0e8b-246"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="e0e8b-246"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e0e8b-247">datetime</span><span class="sxs-lookup"><span data-stu-id="e0e8b-247">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e0e8b-248">Hora de finalización de la sesión.</span><span class="sxs-lookup"><span data-stu-id="e0e8b-248">Time at the end of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0e8b-249"><strong>MediaTypes</strong></span><span class="sxs-lookup"><span data-stu-id="e0e8b-249"><strong>MediaTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="e0e8b-250">int</span><span class="sxs-lookup"><span data-stu-id="e0e8b-250">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e0e8b-251">Un conjunto de bits que indica el tipo de medio de esta sesión.</span><span class="sxs-lookup"><span data-stu-id="e0e8b-251">A bit set that indicates the media type of this session.</span></span> <span data-ttu-id="e0e8b-252">En la lista se muestran las definiciones de los tipos:</span><span class="sxs-lookup"><span data-stu-id="e0e8b-252">Listed are the definitions of the types:</span></span></p>
<h3 id="section-1"> </h3>
<div>
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0e8b-253">MI</span><span class="sxs-lookup"><span data-stu-id="e0e8b-253">IM</span></span></p></td>
<td><p><span data-ttu-id="e0e8b-254">1</span><span class="sxs-lookup"><span data-stu-id="e0e8b-254">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0e8b-255">FILE_TRANSFER</span><span class="sxs-lookup"><span data-stu-id="e0e8b-255">FILE_TRANSFER</span></span></p></td>
<td><p><span data-ttu-id="e0e8b-256">2</span><span class="sxs-lookup"><span data-stu-id="e0e8b-256">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0e8b-257">REMOTE_ASSISTANCE</span><span class="sxs-lookup"><span data-stu-id="e0e8b-257">REMOTE_ASSISTANCE</span></span></p></td>
<td><p><span data-ttu-id="e0e8b-258">4</span><span class="sxs-lookup"><span data-stu-id="e0e8b-258">4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0e8b-259">APP_SHARING</span><span class="sxs-lookup"><span data-stu-id="e0e8b-259">APP_SHARING</span></span></p></td>
<td><p><span data-ttu-id="e0e8b-260">4,8</span><span class="sxs-lookup"><span data-stu-id="e0e8b-260">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0e8b-261">AUDIO</span><span class="sxs-lookup"><span data-stu-id="e0e8b-261">AUDIO</span></span></p></td>
<td><p><span data-ttu-id="e0e8b-262">apartado</span><span class="sxs-lookup"><span data-stu-id="e0e8b-262">16</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0e8b-263">CÁMARA</span><span class="sxs-lookup"><span data-stu-id="e0e8b-263">VIDEO</span></span></p></td>
<td><p><span data-ttu-id="e0e8b-264">32</span><span class="sxs-lookup"><span data-stu-id="e0e8b-264">32</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0e8b-265">APP_INVITE</span><span class="sxs-lookup"><span data-stu-id="e0e8b-265">APP_INVITE</span></span></p></td>
<td><p><span data-ttu-id="e0e8b-266">64</span><span class="sxs-lookup"><span data-stu-id="e0e8b-266">64</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0e8b-267"><strong>User1Flag</strong></span><span class="sxs-lookup"><span data-stu-id="e0e8b-267"><strong>User1Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="e0e8b-268">smallint</span><span class="sxs-lookup"><span data-stu-id="e0e8b-268">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e0e8b-269">Un conjunto de bits que indica los atributos del Usuario1.</span><span class="sxs-lookup"><span data-stu-id="e0e8b-269">A bit set that indicates the User1 attributes.</span></span> <span data-ttu-id="e0e8b-270">Se muestran las siguientes definiciones de atributos:</span><span class="sxs-lookup"><span data-stu-id="e0e8b-270">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="e0e8b-271">0x01: integrado con un teléfono de escritorio</span><span class="sxs-lookup"><span data-stu-id="e0e8b-271">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0e8b-272"><strong>User2Flag</strong></span><span class="sxs-lookup"><span data-stu-id="e0e8b-272"><strong>User2Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="e0e8b-273">smallint</span><span class="sxs-lookup"><span data-stu-id="e0e8b-273">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e0e8b-274">Un conjunto de bits que indica los atributos de usuario2.</span><span class="sxs-lookup"><span data-stu-id="e0e8b-274">A bit set that indicates the User2 attributes.</span></span> <span data-ttu-id="e0e8b-275">Se muestran las siguientes definiciones de atributos:</span><span class="sxs-lookup"><span data-stu-id="e0e8b-275">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="e0e8b-276">0x01: integrado con un teléfono de escritorio</span><span class="sxs-lookup"><span data-stu-id="e0e8b-276">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0e8b-277"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="e0e8b-277"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="e0e8b-278">smallint</span><span class="sxs-lookup"><span data-stu-id="e0e8b-278">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e0e8b-279">Un conjunto de bits que indica los atributos de la llamada.</span><span class="sxs-lookup"><span data-stu-id="e0e8b-279">A bit set that indicates the call attributes.</span></span> <span data-ttu-id="e0e8b-280">Se muestran las siguientes definiciones de atributos:</span><span class="sxs-lookup"><span data-stu-id="e0e8b-280">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="e0e8b-281">0x01-reintento de sesión</span><span class="sxs-lookup"><span data-stu-id="e0e8b-281">0x01 - Retried Session</span></span></p></li>
<li><p><span data-ttu-id="e0e8b-282">0x02: una llamada realizada por el agente en nombre de un grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="e0e8b-282">0x02 - A call made by agent on behalf of a response group</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0e8b-283"><strong>Procesar</strong></span><span class="sxs-lookup"><span data-stu-id="e0e8b-283"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="e0e8b-284">bit</span><span class="sxs-lookup"><span data-stu-id="e0e8b-284">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e0e8b-285">Para uso interno del servicio de supervisión.</span><span class="sxs-lookup"><span data-stu-id="e0e8b-285">For internal use by the Monitoring service.</span></span></p>
<p><span data-ttu-id="e0e8b-286">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e0e8b-286">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e0e8b-287">\*Para la mayoría de las sesiones, SessionIdSeq tendrá el valor 1.</span><span class="sxs-lookup"><span data-stu-id="e0e8b-287">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="e0e8b-288">Si varias sesiones comienzan exactamente al mismo tiempo, la SessionIdSeq para una será 1, la otra será 2, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="e0e8b-288">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

