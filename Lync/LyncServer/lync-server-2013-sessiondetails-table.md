---
title: 'Lync Server 2013: tabla SessionDetails'
description: 'Lync Server 2013: tabla SessionDetails.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SessionDetails table
ms:assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398589(v=OCS.15)
ms:contentKeyID: 48184559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd927f784fb0f2a835c896824105fe8bb112c7a1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569936"
---
# <a name="sessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="59d80-103">Tabla SessionDetails en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59d80-103">SessionDetails table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59d80-104">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="59d80-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="59d80-105">Cada registro representa una sesión punto a punto, que puede ser una llamada de teléfono de VoIP a VoIP, una sesión de mensajería instantánea entre dos partes o cualquier otro tipo de sesión.</span><span class="sxs-lookup"><span data-stu-id="59d80-105">Each record represents one peer-to-peer session, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="59d80-106">Puede realizar una combinación de tablas con la [tabla de medios en Lync Server 2013](lync-server-2013-media-table.md) para encontrar los detalles de cada elemento multimedia implicado en esta sesión.</span><span class="sxs-lookup"><span data-stu-id="59d80-106">You can perform a table join with the [Media table in Lync Server 2013](lync-server-2013-media-table.md) to find the details of each media involved in this session.</span></span>

<span data-ttu-id="59d80-107">Tenga en cuenta que los campos IsUser1IntegratedWithDeskPhone y IsUser2IntegratedWithDeskPhone se han quitado de la tabla SessionDetails usada en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="59d80-107">Note that the IsUser1IntegratedWithDeskPhone and the IsUser2IntegratedWithDeskPhone fields have been dropped from the SessionDetails table used in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="59d80-108">Columna</span><span class="sxs-lookup"><span data-stu-id="59d80-108">Column</span></span></th>
<th><span data-ttu-id="59d80-109">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="59d80-109">Data Type</span></span></th>
<th><span data-ttu-id="59d80-110">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="59d80-110">Key/Index</span></span></th>
<th><span data-ttu-id="59d80-111">Detalles</span><span class="sxs-lookup"><span data-stu-id="59d80-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="59d80-112"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="59d80-112"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="59d80-113">datetime</span><span class="sxs-lookup"><span data-stu-id="59d80-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="59d80-114">Principal, Exterior</span><span class="sxs-lookup"><span data-stu-id="59d80-114">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="59d80-115">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="59d80-115">Time of session request.</span></span> <span data-ttu-id="59d80-116">Se usa junto con <strong>SessionIdSeq</strong> para identificar una sesión de manera exclusiva.</span><span class="sxs-lookup"><span data-stu-id="59d80-116">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="59d80-117">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="59d80-117">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d80-118"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="59d80-118"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="59d80-119">entero</span><span class="sxs-lookup"><span data-stu-id="59d80-119">int</span></span></p></td>
<td><p><span data-ttu-id="59d80-120">Principal, Exterior</span><span class="sxs-lookup"><span data-stu-id="59d80-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="59d80-121">Número del identificador para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="59d80-121">ID number to identify the session.</span></span> <span data-ttu-id="59d80-122">Se usa junto con <strong>SessionIdTime</strong> para identificar de forma única una sesión. \* Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="59d80-122">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.\* See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d80-123"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="59d80-123"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="59d80-124">identificador</span><span class="sxs-lookup"><span data-stu-id="59d80-124">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d80-125">GUID con el que se correlacionan varias sesiones.</span><span class="sxs-lookup"><span data-stu-id="59d80-125">A GUID to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d80-126"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="59d80-126"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="59d80-127">datetime</span><span class="sxs-lookup"><span data-stu-id="59d80-127">datetime</span></span></p></td>
<td><p><span data-ttu-id="59d80-128">Externa</span><span class="sxs-lookup"><span data-stu-id="59d80-128">Foreign</span></span></p></td>
<td><p><span data-ttu-id="59d80-129">Número con el que se identifica el diálogo que se reemplazó por la sesión actual.</span><span class="sxs-lookup"><span data-stu-id="59d80-129">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="59d80-130">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="59d80-130">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d80-131"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="59d80-131"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="59d80-132">entero</span><span class="sxs-lookup"><span data-stu-id="59d80-132">int</span></span></p></td>
<td><p><span data-ttu-id="59d80-133">Externa</span><span class="sxs-lookup"><span data-stu-id="59d80-133">Foreign</span></span></p></td>
<td><p><span data-ttu-id="59d80-134">Número con el que se identifica la sesión.</span><span class="sxs-lookup"><span data-stu-id="59d80-134">ID number to identify the session.</span></span> <span data-ttu-id="59d80-135">Se usa junto con <strong>ReplacesDialogIdTime</strong> para identificar de manera exclusiva una sesión que se reemplazó por esta sesión.</span><span class="sxs-lookup"><span data-stu-id="59d80-135">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="59d80-136">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="59d80-136">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d80-137"><strong>User1Id</strong></span><span class="sxs-lookup"><span data-stu-id="59d80-137"><strong>User1Id</strong></span></span></p></td>
<td><p><span data-ttu-id="59d80-138">entero</span><span class="sxs-lookup"><span data-stu-id="59d80-138">int</span></span></p></td>
<td><p><span data-ttu-id="59d80-139">Externa</span><span class="sxs-lookup"><span data-stu-id="59d80-139">Foreign</span></span></p></td>
<td><p><span data-ttu-id="59d80-140">Identificador de un usuario de la sesión.</span><span class="sxs-lookup"><span data-stu-id="59d80-140">ID of one user in the session.</span></span> <span data-ttu-id="59d80-141">Consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="59d80-141">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d80-142"><strong>User2Id</strong></span><span class="sxs-lookup"><span data-stu-id="59d80-142"><strong>User2Id</strong></span></span></p></td>
<td><p><span data-ttu-id="59d80-143">entero</span><span class="sxs-lookup"><span data-stu-id="59d80-143">int</span></span></p></td>
<td><p><span data-ttu-id="59d80-144">Externa</span><span class="sxs-lookup"><span data-stu-id="59d80-144">Foreign</span></span></p></td>
<td><p><span data-ttu-id="59d80-145">Identificador de otro usuario de la sesión.</span><span class="sxs-lookup"><span data-stu-id="59d80-145">ID of the other user in the session.</span></span> <span data-ttu-id="59d80-146">Consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="59d80-146">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d80-147"><strong>User1EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="59d80-147"><strong>User1EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="59d80-148">Identificador</span><span class="sxs-lookup"><span data-stu-id="59d80-148">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d80-149">GUID que identifica el extremo que utilizó el primer usuario en la sesión.</span><span class="sxs-lookup"><span data-stu-id="59d80-149">GUID that identifies the endpoint used by the first user in the session.</span></span></p>
<p><span data-ttu-id="59d80-150">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="59d80-150">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d80-151"><strong>User2EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="59d80-151"><strong>User2EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="59d80-152">Identificador</span><span class="sxs-lookup"><span data-stu-id="59d80-152">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d80-153">GUID que identifica el extremo que utilizó el segundo usuario en la sesión.</span><span class="sxs-lookup"><span data-stu-id="59d80-153">GUID that identifies the endpoint used by the second user in the session.</span></span></p>
<p><span data-ttu-id="59d80-154">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="59d80-154">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d80-155"><strong>TargetUserId</strong></span><span class="sxs-lookup"><span data-stu-id="59d80-155"><strong>TargetUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="59d80-156">entero</span><span class="sxs-lookup"><span data-stu-id="59d80-156">int</span></span></p></td>
<td><p><span data-ttu-id="59d80-157">Externa</span><span class="sxs-lookup"><span data-stu-id="59d80-157">Foreign</span></span></p></td>
<td><p><span data-ttu-id="59d80-158">URI de destinatario original en la solicitud SIP.</span><span class="sxs-lookup"><span data-stu-id="59d80-158">The original To user URI in the SIP request.</span></span> <span data-ttu-id="59d80-159">Consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="59d80-159">see the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d80-160"><strong>SessionStartedById</strong></span><span class="sxs-lookup"><span data-stu-id="59d80-160"><strong>SessionStartedById</strong></span></span></p></td>
<td><p><span data-ttu-id="59d80-161">entero</span><span class="sxs-lookup"><span data-stu-id="59d80-161">int</span></span></p></td>
<td><p><span data-ttu-id="59d80-162">Externa</span><span class="sxs-lookup"><span data-stu-id="59d80-162">Foreign</span></span></p></td>
<td><p><span data-ttu-id="59d80-163">Identificador del usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="59d80-163">ID of the user who started the session.</span></span> <span data-ttu-id="59d80-164">Consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="59d80-164">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d80-165"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="59d80-165"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="59d80-166">entero</span><span class="sxs-lookup"><span data-stu-id="59d80-166">int</span></span></p></td>
<td><p><span data-ttu-id="59d80-167">Externa</span><span class="sxs-lookup"><span data-stu-id="59d80-167">Foreign</span></span></p></td>
<td><p><span data-ttu-id="59d80-168">Señala el identificador de usuario en cuyo nombre llama el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="59d80-168">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="59d80-169">Consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="59d80-169">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d80-170"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="59d80-170"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="59d80-171">entero</span><span class="sxs-lookup"><span data-stu-id="59d80-171">int</span></span></p></td>
<td><p><span data-ttu-id="59d80-172">Externa</span><span class="sxs-lookup"><span data-stu-id="59d80-172">Foreign</span></span></p></td>
<td><p><span data-ttu-id="59d80-173">Identificador del usuario por el que se hace referencia a la sesión.</span><span class="sxs-lookup"><span data-stu-id="59d80-173">ID of the user by who the call is referred.</span></span> <span data-ttu-id="59d80-174">Consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="59d80-174">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d80-175"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="59d80-175"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="59d80-176">entero</span><span class="sxs-lookup"><span data-stu-id="59d80-176">int</span></span></p></td>
<td><p><span data-ttu-id="59d80-177">Externa</span><span class="sxs-lookup"><span data-stu-id="59d80-177">Foreign</span></span></p></td>
<td><p><span data-ttu-id="59d80-178">Identificador del servidor front-end usado en esta sesión.</span><span class="sxs-lookup"><span data-stu-id="59d80-178">ID of the front-end server used for this session.</span></span> <span data-ttu-id="59d80-179">Consulte la <a href="lync-server-2013-servers-table.md">tabla servidores en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="59d80-179">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d80-180"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="59d80-180"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="59d80-181">entero</span><span class="sxs-lookup"><span data-stu-id="59d80-181">int</span></span></p></td>
<td><p><span data-ttu-id="59d80-182">Externa</span><span class="sxs-lookup"><span data-stu-id="59d80-182">Foreign</span></span></p></td>
<td><p><span data-ttu-id="59d80-183">Identificador del grupo en el que se capturó la sesión.</span><span class="sxs-lookup"><span data-stu-id="59d80-183">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="59d80-184">Consulte la <a href="lync-server-2013-pools-table.md">tabla grupos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="59d80-184">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d80-185"><strong>ContentTypeID</strong></span><span class="sxs-lookup"><span data-stu-id="59d80-185"><strong>ContentTypeID</strong></span></span></p></td>
<td><p><span data-ttu-id="59d80-186">entero</span><span class="sxs-lookup"><span data-stu-id="59d80-186">int</span></span></p></td>
<td><p><span data-ttu-id="59d80-187">Externa</span><span class="sxs-lookup"><span data-stu-id="59d80-187">Foreign</span></span></p></td>
<td><p><span data-ttu-id="59d80-188">Tipo de contenido empleado en la sesión.</span><span class="sxs-lookup"><span data-stu-id="59d80-188">Content type used in the session.</span></span> <span data-ttu-id="59d80-189">Consulte la <a href="lync-server-2013-contenttypes-table.md">tabla contentTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="59d80-189">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d80-190"><strong>User1ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="59d80-190"><strong>User1ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="59d80-191">entero</span><span class="sxs-lookup"><span data-stu-id="59d80-191">int</span></span></p></td>
<td><p><span data-ttu-id="59d80-192">Externa</span><span class="sxs-lookup"><span data-stu-id="59d80-192">Foreign</span></span></p></td>
<td><p><span data-ttu-id="59d80-193">Versión de cliente usada por el usuario 1.</span><span class="sxs-lookup"><span data-stu-id="59d80-193">Client version used by User1.</span></span> <span data-ttu-id="59d80-194">Consulte la <a href="lync-server-2013-clientversions-table.md">tabla ClientVersions en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="59d80-194">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d80-195"><strong>User2ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="59d80-195"><strong>User2ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="59d80-196">entero</span><span class="sxs-lookup"><span data-stu-id="59d80-196">int</span></span></p></td>
<td><p><span data-ttu-id="59d80-197">Externa</span><span class="sxs-lookup"><span data-stu-id="59d80-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="59d80-198">Versión de cliente usada por el usuario 2.</span><span class="sxs-lookup"><span data-stu-id="59d80-198">Client version used by User2.</span></span> <span data-ttu-id="59d80-199">Consulte la <a href="lync-server-2013-clientversions-table.md">tabla ClientVersions en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="59d80-199">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d80-200"><strong>User1EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="59d80-200"><strong>User1EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="59d80-201">entero</span><span class="sxs-lookup"><span data-stu-id="59d80-201">int</span></span></p></td>
<td><p><span data-ttu-id="59d80-202">Externa</span><span class="sxs-lookup"><span data-stu-id="59d80-202">Foreign</span></span></p></td>
<td><p><span data-ttu-id="59d80-203">Servidor perimetral usado por el usuario 1.</span><span class="sxs-lookup"><span data-stu-id="59d80-203">Edge Server used by User1.</span></span> <span data-ttu-id="59d80-204">Consulte la <a href="lync-server-2013-edgeservers-table.md">tabla EdgeServers en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="59d80-204">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d80-205"><strong>User2EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="59d80-205"><strong>User2EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="59d80-206">entero</span><span class="sxs-lookup"><span data-stu-id="59d80-206">int</span></span></p></td>
<td><p><span data-ttu-id="59d80-207">Externa</span><span class="sxs-lookup"><span data-stu-id="59d80-207">Foreign</span></span></p></td>
<td><p><span data-ttu-id="59d80-208">Servidor perimetral usado por el usuario 2.</span><span class="sxs-lookup"><span data-stu-id="59d80-208">Edge Server used by User2.</span></span> <span data-ttu-id="59d80-209">Consulte la <a href="lync-server-2013-edgeservers-table.md">tabla EdgeServers en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="59d80-209">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d80-210"><strong>IsUser1Internal</strong></span><span class="sxs-lookup"><span data-stu-id="59d80-210"><strong>IsUser1Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="59d80-211">bit</span><span class="sxs-lookup"><span data-stu-id="59d80-211">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d80-212">Indica si el usuario 1 ha iniciado sesión de manera interna o no.</span><span class="sxs-lookup"><span data-stu-id="59d80-212">Whether User1 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d80-213"><strong>IsUser2Internal</strong></span><span class="sxs-lookup"><span data-stu-id="59d80-213"><strong>IsUser2Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="59d80-214">bit</span><span class="sxs-lookup"><span data-stu-id="59d80-214">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d80-215">Indica si el usuario 2 ha iniciado sesión de manera interna o no.</span><span class="sxs-lookup"><span data-stu-id="59d80-215">Whether User2 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d80-216"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="59d80-216"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="59d80-217">datetime</span><span class="sxs-lookup"><span data-stu-id="59d80-217">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d80-218">Hora de la primera solicitud INVITE.</span><span class="sxs-lookup"><span data-stu-id="59d80-218">The time of the first INVITE request.</span></span> <span data-ttu-id="59d80-219">Este campo suele rellenarse con datos generados a partir del mensaje INVITE inicial en la sesión.</span><span class="sxs-lookup"><span data-stu-id="59d80-219">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="59d80-220">Si no existe el mensaje INVITE, el campo se rellenará con la fecha y hora del primer mensaje SIP relevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="59d80-220">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="59d80-221">Este campo se suele rellenar con datos generados a partir del mensaje INVITE inicial de la sesión.</span><span class="sxs-lookup"><span data-stu-id="59d80-221">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="59d80-222">Si no hay ningún mensaje INVITE, el campo se rellenará con la fecha y hora del primer mensaje SIP relevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="59d80-222">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d80-223"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="59d80-223"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="59d80-224">datetime</span><span class="sxs-lookup"><span data-stu-id="59d80-224">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d80-225">Hora de respuesta al primer mensaje INVITE.</span><span class="sxs-lookup"><span data-stu-id="59d80-225">The time of the response to the first INVITE message.</span></span> <span data-ttu-id="59d80-226">Este campo normalmente se rellena con los datos generados a partir del mensaje INVITE inicial en la sesión.</span><span class="sxs-lookup"><span data-stu-id="59d80-226">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="59d80-227">Si no hay ningún mensaje INVITE, el campo se rellena con la fecha y la hora del primer mensaje SIP relevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="59d80-227">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d80-228"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="59d80-228"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="59d80-229">entero</span><span class="sxs-lookup"><span data-stu-id="59d80-229">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d80-p121">Código de respuesta SIP a la invitación a la sesión. Este campo se suele rellenar con datos generados a partir del mensaje INVITE inicial de la sesión. Si no hay ningún mensaje INVITE, el campo se rellena con la hora y la fecha del primer mensaje SIP correspondiente (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="59d80-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d80-233"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="59d80-233"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="59d80-234">entero</span><span class="sxs-lookup"><span data-stu-id="59d80-234">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d80-235">Identificador de diagnóstico capturado del encabezado SIP.</span><span class="sxs-lookup"><span data-stu-id="59d80-235">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d80-236"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="59d80-236"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="59d80-237">entero</span><span class="sxs-lookup"><span data-stu-id="59d80-237">int</span></span></p></td>
<td><p><span data-ttu-id="59d80-238">Externa</span><span class="sxs-lookup"><span data-stu-id="59d80-238">Foreign</span></span></p></td>
<td><p><span data-ttu-id="59d80-239">Prioridad de la llamada.</span><span class="sxs-lookup"><span data-stu-id="59d80-239">Call priority.</span></span> <span data-ttu-id="59d80-240">Consulte la <a href="lync-server-2013-callpriorities-table.md">tabla CallPriorities en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="59d80-240">See the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d80-241"><strong>User1MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="59d80-241"><strong>User1MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="59d80-242">entero</span><span class="sxs-lookup"><span data-stu-id="59d80-242">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d80-243">Número de mensajes que envió el usuario 1 durante la sesión.</span><span class="sxs-lookup"><span data-stu-id="59d80-243">Number of messages sent by User1 during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d80-244"><strong>User2MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="59d80-244"><strong>User2MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="59d80-245">entero</span><span class="sxs-lookup"><span data-stu-id="59d80-245">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d80-246">Número de mensajes que envió el usuario 2 durante la sesión.</span><span class="sxs-lookup"><span data-stu-id="59d80-246">Number of messages sent by User2 during the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d80-247"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="59d80-247"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="59d80-248">datetime</span><span class="sxs-lookup"><span data-stu-id="59d80-248">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d80-249">Hora al final de la sesión.</span><span class="sxs-lookup"><span data-stu-id="59d80-249">Time at the end of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d80-250"><strong>MediaTypes</strong></span><span class="sxs-lookup"><span data-stu-id="59d80-250"><strong>MediaTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="59d80-251">entero</span><span class="sxs-lookup"><span data-stu-id="59d80-251">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d80-p123">Conjunto de bits que indica el tipo de medio de esta sesión. A continuación se enumeran las definiciones de los tipos:</span><span class="sxs-lookup"><span data-stu-id="59d80-p123">A bit set that indicates the media type of this session. Listed are the definitions of the types:</span></span></p>
<h3 id="section-1"> </h3>
<div>
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="59d80-254">Mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="59d80-254">IM</span></span></p></td>
<td><p><span data-ttu-id="59d80-255">1</span><span class="sxs-lookup"><span data-stu-id="59d80-255">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d80-256">FILE_TRANSFER</span><span class="sxs-lookup"><span data-stu-id="59d80-256">FILE_TRANSFER</span></span></p></td>
<td><p><span data-ttu-id="59d80-257">segundo</span><span class="sxs-lookup"><span data-stu-id="59d80-257">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d80-258">REMOTE_ASSISTANCE</span><span class="sxs-lookup"><span data-stu-id="59d80-258">REMOTE_ASSISTANCE</span></span></p></td>
<td><p><span data-ttu-id="59d80-259">4 </span><span class="sxs-lookup"><span data-stu-id="59d80-259">4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d80-260">APP_SHARING</span><span class="sxs-lookup"><span data-stu-id="59d80-260">APP_SHARING</span></span></p></td>
<td><p><span data-ttu-id="59d80-261">8 </span><span class="sxs-lookup"><span data-stu-id="59d80-261">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d80-262">PUERTOS</span><span class="sxs-lookup"><span data-stu-id="59d80-262">AUDIO</span></span></p></td>
<td><p><span data-ttu-id="59d80-263">16 </span><span class="sxs-lookup"><span data-stu-id="59d80-263">16</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d80-264">VÍDEO</span><span class="sxs-lookup"><span data-stu-id="59d80-264">VIDEO</span></span></p></td>
<td><p><span data-ttu-id="59d80-265">32</span><span class="sxs-lookup"><span data-stu-id="59d80-265">32</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d80-266">APP_INVITE</span><span class="sxs-lookup"><span data-stu-id="59d80-266">APP_INVITE</span></span></p></td>
<td><p><span data-ttu-id="59d80-267">64</span><span class="sxs-lookup"><span data-stu-id="59d80-267">64</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d80-268"><strong>User1Flag</strong></span><span class="sxs-lookup"><span data-stu-id="59d80-268"><strong>User1Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="59d80-269">smallint</span><span class="sxs-lookup"><span data-stu-id="59d80-269">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d80-p124">Conjunto de bits que señala los atributos del usuario 1. Se enumeran las siguientes definiciones de atributo:</span><span class="sxs-lookup"><span data-stu-id="59d80-p124">A bit set that indicates the User1 attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="59d80-272">0x01 - Integrado con el teléfono de escritorio</span><span class="sxs-lookup"><span data-stu-id="59d80-272">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d80-273"><strong>User2Flag</strong></span><span class="sxs-lookup"><span data-stu-id="59d80-273"><strong>User2Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="59d80-274">smallint</span><span class="sxs-lookup"><span data-stu-id="59d80-274">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d80-p125">Conjunto de bits que señala los atributos del usuario 2. Se enumeran las siguientes definiciones de atributo:</span><span class="sxs-lookup"><span data-stu-id="59d80-p125">A bit set that indicates the User2 attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="59d80-277">0x01 - Integrado con el teléfono de escritorio</span><span class="sxs-lookup"><span data-stu-id="59d80-277">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d80-278"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="59d80-278"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="59d80-279">smallint</span><span class="sxs-lookup"><span data-stu-id="59d80-279">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d80-p126">Conjunto de bits que indica los atributos de la llamada. Se enumeran las siguientes definiciones de atributo:</span><span class="sxs-lookup"><span data-stu-id="59d80-p126">A bit set that indicates the call attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="59d80-282">0x01 - Sesión reintentada</span><span class="sxs-lookup"><span data-stu-id="59d80-282">0x01 - Retried Session</span></span></p></li>
<li><p><span data-ttu-id="59d80-283">0x02 - Una llamada realizada por el agente en nombre de un grupo de respuestas</span><span class="sxs-lookup"><span data-stu-id="59d80-283">0x02 - A call made by agent on behalf of a response group</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d80-284"><strong>Procesan</strong></span><span class="sxs-lookup"><span data-stu-id="59d80-284"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="59d80-285">bit</span><span class="sxs-lookup"><span data-stu-id="59d80-285">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d80-286">Para uso interno del servicio de supervisión.</span><span class="sxs-lookup"><span data-stu-id="59d80-286">For internal use by the Monitoring service.</span></span></p>
<p><span data-ttu-id="59d80-287">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="59d80-287">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="59d80-288">\* Para la mayoría de las sesiones, SessionIdSeq tendrá el valor de 1.</span><span class="sxs-lookup"><span data-stu-id="59d80-288">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="59d80-289">Si hay varias sesiones que comienzan exactamente a la misma hora, el valor de SessionIdSeq para una será 1, para otra, 2 y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="59d80-289">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

