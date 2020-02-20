---
title: 'Lync Server 2013: tabla SessionDetails'
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
ms.openlocfilehash: b27721923e265bbb687b5df42b32e0fb6f25e92e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143804"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="d57a6-102">Tabla SessionDetails en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d57a6-102">SessionDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d57a6-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="d57a6-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="d57a6-104">Cada registro representa una sesión punto a punto, que puede ser una llamada de teléfono de VoIP a VoIP, una sesión de mensajería instantánea entre dos partes o cualquier otro tipo de sesión.</span><span class="sxs-lookup"><span data-stu-id="d57a6-104">Each record represents one peer-to-peer session, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="d57a6-105">Puede realizar una combinación de tablas con la [tabla de medios en Lync Server 2013](lync-server-2013-media-table.md) para encontrar los detalles de cada elemento multimedia implicado en esta sesión.</span><span class="sxs-lookup"><span data-stu-id="d57a6-105">You can perform a table join with the [Media table in Lync Server 2013](lync-server-2013-media-table.md) to find the details of each media involved in this session.</span></span>

<span data-ttu-id="d57a6-106">Tenga en cuenta que los campos IsUser1IntegratedWithDeskPhone y IsUser2IntegratedWithDeskPhone se han quitado de la tabla SessionDetails usada en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d57a6-106">Note that the IsUser1IntegratedWithDeskPhone and the IsUser2IntegratedWithDeskPhone fields have been dropped from the SessionDetails table used in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d57a6-107">Columna</span><span class="sxs-lookup"><span data-stu-id="d57a6-107">Column</span></span></th>
<th><span data-ttu-id="d57a6-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="d57a6-108">Data Type</span></span></th>
<th><span data-ttu-id="d57a6-109">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="d57a6-109">Key/Index</span></span></th>
<th><span data-ttu-id="d57a6-110">Detalles</span><span class="sxs-lookup"><span data-stu-id="d57a6-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d57a6-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="d57a6-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d57a6-112">datetime</span><span class="sxs-lookup"><span data-stu-id="d57a6-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="d57a6-113">Principal, Externa</span><span class="sxs-lookup"><span data-stu-id="d57a6-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="d57a6-114">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="d57a6-114">Time of session request.</span></span> <span data-ttu-id="d57a6-115">Se usa junto con <strong>SessionIdSeq</strong> para identificar una sesión de manera exclusiva.</span><span class="sxs-lookup"><span data-stu-id="d57a6-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="d57a6-116">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d57a6-116">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d57a6-117"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="d57a6-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d57a6-118">int</span><span class="sxs-lookup"><span data-stu-id="d57a6-118">int</span></span></p></td>
<td><p><span data-ttu-id="d57a6-119">Principal, Exterior</span><span class="sxs-lookup"><span data-stu-id="d57a6-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="d57a6-120">Número del identificador para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="d57a6-120">ID number to identify the session.</span></span> <span data-ttu-id="d57a6-121">Se usa junto con <strong>SessionIdTime</strong> para identificar de forma única una sesión. \* Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d57a6-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.\* See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d57a6-122"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="d57a6-122"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="d57a6-123">identificador</span><span class="sxs-lookup"><span data-stu-id="d57a6-123">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d57a6-124">GUID con el que se correlacionan varias sesiones.</span><span class="sxs-lookup"><span data-stu-id="d57a6-124">A GUID to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d57a6-125"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="d57a6-125"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d57a6-126">datetime</span><span class="sxs-lookup"><span data-stu-id="d57a6-126">datetime</span></span></p></td>
<td><p><span data-ttu-id="d57a6-127">Externa</span><span class="sxs-lookup"><span data-stu-id="d57a6-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d57a6-128">Número con el que se identifica el diálogo que se reemplazó por la sesión actual.</span><span class="sxs-lookup"><span data-stu-id="d57a6-128">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="d57a6-129">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d57a6-129">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d57a6-130"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="d57a6-130"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d57a6-131">int</span><span class="sxs-lookup"><span data-stu-id="d57a6-131">int</span></span></p></td>
<td><p><span data-ttu-id="d57a6-132">Externa</span><span class="sxs-lookup"><span data-stu-id="d57a6-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d57a6-133">Número con el que se identifica la sesión.</span><span class="sxs-lookup"><span data-stu-id="d57a6-133">ID number to identify the session.</span></span> <span data-ttu-id="d57a6-134">Se usa junto con <strong>ReplacesDialogIdTime</strong> para identificar de manera exclusiva una sesión que se reemplazó por esta sesión.</span><span class="sxs-lookup"><span data-stu-id="d57a6-134">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="d57a6-135">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d57a6-135">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d57a6-136"><strong>User1Id</strong></span><span class="sxs-lookup"><span data-stu-id="d57a6-136"><strong>User1Id</strong></span></span></p></td>
<td><p><span data-ttu-id="d57a6-137">int</span><span class="sxs-lookup"><span data-stu-id="d57a6-137">int</span></span></p></td>
<td><p><span data-ttu-id="d57a6-138">Externa</span><span class="sxs-lookup"><span data-stu-id="d57a6-138">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d57a6-139">Identificador de un usuario de la sesión.</span><span class="sxs-lookup"><span data-stu-id="d57a6-139">ID of one user in the session.</span></span> <span data-ttu-id="d57a6-140">Consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d57a6-140">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d57a6-141"><strong>User2Id</strong></span><span class="sxs-lookup"><span data-stu-id="d57a6-141"><strong>User2Id</strong></span></span></p></td>
<td><p><span data-ttu-id="d57a6-142">int</span><span class="sxs-lookup"><span data-stu-id="d57a6-142">int</span></span></p></td>
<td><p><span data-ttu-id="d57a6-143">Externa</span><span class="sxs-lookup"><span data-stu-id="d57a6-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d57a6-144">Identificador de otro usuario de la sesión.</span><span class="sxs-lookup"><span data-stu-id="d57a6-144">ID of the other user in the session.</span></span> <span data-ttu-id="d57a6-145">Consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d57a6-145">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d57a6-146"><strong>User1EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="d57a6-146"><strong>User1EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="d57a6-147">Identificador</span><span class="sxs-lookup"><span data-stu-id="d57a6-147">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d57a6-148">GUID que identifica el extremo que utilizó el primer usuario en la sesión.</span><span class="sxs-lookup"><span data-stu-id="d57a6-148">GUID that identifies the endpoint used by the first user in the session.</span></span></p>
<p><span data-ttu-id="d57a6-149">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d57a6-149">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d57a6-150"><strong>User2EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="d57a6-150"><strong>User2EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="d57a6-151">Identificador</span><span class="sxs-lookup"><span data-stu-id="d57a6-151">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d57a6-152">GUID que identifica el extremo que utilizó el segundo usuario en la sesión.</span><span class="sxs-lookup"><span data-stu-id="d57a6-152">GUID that identifies the endpoint used by the second user in the session.</span></span></p>
<p><span data-ttu-id="d57a6-153">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d57a6-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d57a6-154"><strong>TargetUserId</strong></span><span class="sxs-lookup"><span data-stu-id="d57a6-154"><strong>TargetUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="d57a6-155">int</span><span class="sxs-lookup"><span data-stu-id="d57a6-155">int</span></span></p></td>
<td><p><span data-ttu-id="d57a6-156">Externa</span><span class="sxs-lookup"><span data-stu-id="d57a6-156">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d57a6-157">URI de destinatario original en la solicitud SIP.</span><span class="sxs-lookup"><span data-stu-id="d57a6-157">The original To user URI in the SIP request.</span></span> <span data-ttu-id="d57a6-158">Consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d57a6-158">see the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d57a6-159"><strong>SessionStartedById</strong></span><span class="sxs-lookup"><span data-stu-id="d57a6-159"><strong>SessionStartedById</strong></span></span></p></td>
<td><p><span data-ttu-id="d57a6-160">int</span><span class="sxs-lookup"><span data-stu-id="d57a6-160">int</span></span></p></td>
<td><p><span data-ttu-id="d57a6-161">Externa</span><span class="sxs-lookup"><span data-stu-id="d57a6-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d57a6-162">Identificador del usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="d57a6-162">ID of the user who started the session.</span></span> <span data-ttu-id="d57a6-163">Consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d57a6-163">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d57a6-164"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="d57a6-164"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="d57a6-165">int</span><span class="sxs-lookup"><span data-stu-id="d57a6-165">int</span></span></p></td>
<td><p><span data-ttu-id="d57a6-166">Externa</span><span class="sxs-lookup"><span data-stu-id="d57a6-166">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d57a6-167">Señala el identificador de usuario en cuyo nombre llama el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d57a6-167">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="d57a6-168">Consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d57a6-168">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d57a6-169"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="d57a6-169"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="d57a6-170">int</span><span class="sxs-lookup"><span data-stu-id="d57a6-170">int</span></span></p></td>
<td><p><span data-ttu-id="d57a6-171">Externa</span><span class="sxs-lookup"><span data-stu-id="d57a6-171">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d57a6-172">Identificador del usuario por el que se hace referencia a la sesión.</span><span class="sxs-lookup"><span data-stu-id="d57a6-172">ID of the user by who the call is referred.</span></span> <span data-ttu-id="d57a6-173">Consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d57a6-173">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d57a6-174"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="d57a6-174"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="d57a6-175">int</span><span class="sxs-lookup"><span data-stu-id="d57a6-175">int</span></span></p></td>
<td><p><span data-ttu-id="d57a6-176">Externa</span><span class="sxs-lookup"><span data-stu-id="d57a6-176">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d57a6-177">Identificador del servidor front-end usado en esta sesión.</span><span class="sxs-lookup"><span data-stu-id="d57a6-177">ID of the front-end server used for this session.</span></span> <span data-ttu-id="d57a6-178">Consulte la <a href="lync-server-2013-servers-table.md">tabla servidores en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d57a6-178">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d57a6-179"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="d57a6-179"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="d57a6-180">int</span><span class="sxs-lookup"><span data-stu-id="d57a6-180">int</span></span></p></td>
<td><p><span data-ttu-id="d57a6-181">Externa</span><span class="sxs-lookup"><span data-stu-id="d57a6-181">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d57a6-182">Identificador del grupo en el que se capturó la sesión.</span><span class="sxs-lookup"><span data-stu-id="d57a6-182">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="d57a6-183">Consulte la <a href="lync-server-2013-pools-table.md">tabla grupos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d57a6-183">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d57a6-184"><strong>ContentTypeID</strong></span><span class="sxs-lookup"><span data-stu-id="d57a6-184"><strong>ContentTypeID</strong></span></span></p></td>
<td><p><span data-ttu-id="d57a6-185">int</span><span class="sxs-lookup"><span data-stu-id="d57a6-185">int</span></span></p></td>
<td><p><span data-ttu-id="d57a6-186">Externa</span><span class="sxs-lookup"><span data-stu-id="d57a6-186">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d57a6-187">Tipo de contenido empleado en la sesión.</span><span class="sxs-lookup"><span data-stu-id="d57a6-187">Content type used in the session.</span></span> <span data-ttu-id="d57a6-188">Consulte la <a href="lync-server-2013-contenttypes-table.md">tabla contentTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d57a6-188">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d57a6-189"><strong>User1ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="d57a6-189"><strong>User1ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="d57a6-190">int</span><span class="sxs-lookup"><span data-stu-id="d57a6-190">int</span></span></p></td>
<td><p><span data-ttu-id="d57a6-191">Externa</span><span class="sxs-lookup"><span data-stu-id="d57a6-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d57a6-192">Versión de cliente usada por el usuario 1.</span><span class="sxs-lookup"><span data-stu-id="d57a6-192">Client version used by User1.</span></span> <span data-ttu-id="d57a6-193">Consulte la <a href="lync-server-2013-clientversions-table.md">tabla ClientVersions en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d57a6-193">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d57a6-194"><strong>User2ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="d57a6-194"><strong>User2ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="d57a6-195">int</span><span class="sxs-lookup"><span data-stu-id="d57a6-195">int</span></span></p></td>
<td><p><span data-ttu-id="d57a6-196">Externa</span><span class="sxs-lookup"><span data-stu-id="d57a6-196">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d57a6-197">Versión de cliente usada por el usuario 2.</span><span class="sxs-lookup"><span data-stu-id="d57a6-197">Client version used by User2.</span></span> <span data-ttu-id="d57a6-198">Consulte la <a href="lync-server-2013-clientversions-table.md">tabla ClientVersions en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d57a6-198">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d57a6-199"><strong>User1EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="d57a6-199"><strong>User1EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="d57a6-200">int</span><span class="sxs-lookup"><span data-stu-id="d57a6-200">int</span></span></p></td>
<td><p><span data-ttu-id="d57a6-201">Externa</span><span class="sxs-lookup"><span data-stu-id="d57a6-201">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d57a6-202">Servidor perimetral usado por el usuario 1.</span><span class="sxs-lookup"><span data-stu-id="d57a6-202">Edge Server used by User1.</span></span> <span data-ttu-id="d57a6-203">Consulte la <a href="lync-server-2013-edgeservers-table.md">tabla EdgeServers en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d57a6-203">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d57a6-204"><strong>User2EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="d57a6-204"><strong>User2EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="d57a6-205">int</span><span class="sxs-lookup"><span data-stu-id="d57a6-205">int</span></span></p></td>
<td><p><span data-ttu-id="d57a6-206">Externa</span><span class="sxs-lookup"><span data-stu-id="d57a6-206">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d57a6-207">Servidor perimetral usado por el usuario 2.</span><span class="sxs-lookup"><span data-stu-id="d57a6-207">Edge Server used by User2.</span></span> <span data-ttu-id="d57a6-208">Consulte la <a href="lync-server-2013-edgeservers-table.md">tabla EdgeServers en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d57a6-208">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d57a6-209"><strong>IsUser1Internal</strong></span><span class="sxs-lookup"><span data-stu-id="d57a6-209"><strong>IsUser1Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="d57a6-210">bit</span><span class="sxs-lookup"><span data-stu-id="d57a6-210">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d57a6-211">Indica si el usuario 1 ha iniciado sesión de manera interna o no.</span><span class="sxs-lookup"><span data-stu-id="d57a6-211">Whether User1 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d57a6-212"><strong>IsUser2Internal</strong></span><span class="sxs-lookup"><span data-stu-id="d57a6-212"><strong>IsUser2Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="d57a6-213">bit</span><span class="sxs-lookup"><span data-stu-id="d57a6-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d57a6-214">Indica si el usuario 2 ha iniciado sesión de manera interna o no.</span><span class="sxs-lookup"><span data-stu-id="d57a6-214">Whether User2 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d57a6-215"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="d57a6-215"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d57a6-216">datetime</span><span class="sxs-lookup"><span data-stu-id="d57a6-216">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d57a6-217">Hora de la primera solicitud INVITE.</span><span class="sxs-lookup"><span data-stu-id="d57a6-217">The time of the first INVITE request.</span></span> <span data-ttu-id="d57a6-218">Este campo suele rellenarse con datos generados a partir del mensaje INVITE inicial en la sesión.</span><span class="sxs-lookup"><span data-stu-id="d57a6-218">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="d57a6-219">Si no existe el mensaje INVITE, el campo se rellenará con la fecha y hora del primer mensaje SIP relevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="d57a6-219">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="d57a6-220">Este campo se suele rellenar con datos generados a partir del mensaje INVITE inicial de la sesión.</span><span class="sxs-lookup"><span data-stu-id="d57a6-220">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="d57a6-221">Si no hay ningún mensaje INVITE, el campo se rellenará con la fecha y hora del primer mensaje SIP relevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="d57a6-221">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d57a6-222"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="d57a6-222"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d57a6-223">datetime</span><span class="sxs-lookup"><span data-stu-id="d57a6-223">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d57a6-224">Hora de respuesta al primer mensaje INVITE.</span><span class="sxs-lookup"><span data-stu-id="d57a6-224">The time of the response to the first INVITE message.</span></span> <span data-ttu-id="d57a6-225">Este campo normalmente se rellena con los datos generados a partir del mensaje INVITE inicial en la sesión.</span><span class="sxs-lookup"><span data-stu-id="d57a6-225">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="d57a6-226">Si no hay ningún mensaje INVITE, el campo se rellena con la fecha y la hora del primer mensaje SIP relevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="d57a6-226">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d57a6-227"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="d57a6-227"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="d57a6-228">int</span><span class="sxs-lookup"><span data-stu-id="d57a6-228">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d57a6-p121">Código de respuesta SIP a la invitación a la sesión. Este campo se suele rellenar con datos generados a partir del mensaje INVITE inicial de la sesión. Si no hay ningún mensaje INVITE, el campo se rellena con la hora y la fecha del primer mensaje SIP correspondiente (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="d57a6-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d57a6-232"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="d57a6-232"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="d57a6-233">int</span><span class="sxs-lookup"><span data-stu-id="d57a6-233">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d57a6-234">Identificador de diagnóstico capturado del encabezado SIP.</span><span class="sxs-lookup"><span data-stu-id="d57a6-234">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d57a6-235"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="d57a6-235"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="d57a6-236">int</span><span class="sxs-lookup"><span data-stu-id="d57a6-236">int</span></span></p></td>
<td><p><span data-ttu-id="d57a6-237">Externa</span><span class="sxs-lookup"><span data-stu-id="d57a6-237">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d57a6-238">Prioridad de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d57a6-238">Call priority.</span></span> <span data-ttu-id="d57a6-239">Consulte la <a href="lync-server-2013-callpriorities-table.md">tabla CallPriorities en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d57a6-239">See the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d57a6-240"><strong>User1MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="d57a6-240"><strong>User1MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="d57a6-241">int</span><span class="sxs-lookup"><span data-stu-id="d57a6-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d57a6-242">Número de mensajes que envió el usuario 1 durante la sesión.</span><span class="sxs-lookup"><span data-stu-id="d57a6-242">Number of messages sent by User1 during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d57a6-243"><strong>User2MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="d57a6-243"><strong>User2MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="d57a6-244">int</span><span class="sxs-lookup"><span data-stu-id="d57a6-244">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d57a6-245">Número de mensajes que envió el usuario 2 durante la sesión.</span><span class="sxs-lookup"><span data-stu-id="d57a6-245">Number of messages sent by User2 during the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d57a6-246"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="d57a6-246"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d57a6-247">datetime</span><span class="sxs-lookup"><span data-stu-id="d57a6-247">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d57a6-248">Hora al final de la sesión.</span><span class="sxs-lookup"><span data-stu-id="d57a6-248">Time at the end of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d57a6-249"><strong>MediaTypes</strong></span><span class="sxs-lookup"><span data-stu-id="d57a6-249"><strong>MediaTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="d57a6-250">int</span><span class="sxs-lookup"><span data-stu-id="d57a6-250">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d57a6-p123">Conjunto de bits que indica el tipo de medio de esta sesión. A continuación se enumeran las definiciones de los tipos:</span><span class="sxs-lookup"><span data-stu-id="d57a6-p123">A bit set that indicates the media type of this session. Listed are the definitions of the types:</span></span></p>
<h3 id="section-1"> </h3>
<div>
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d57a6-253">Mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="d57a6-253">IM</span></span></p></td>
<td><p><span data-ttu-id="d57a6-254">1</span><span class="sxs-lookup"><span data-stu-id="d57a6-254">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d57a6-255">FILE_TRANSFER</span><span class="sxs-lookup"><span data-stu-id="d57a6-255">FILE_TRANSFER</span></span></p></td>
<td><p><span data-ttu-id="d57a6-256">segundo</span><span class="sxs-lookup"><span data-stu-id="d57a6-256">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d57a6-257">REMOTE_ASSISTANCE</span><span class="sxs-lookup"><span data-stu-id="d57a6-257">REMOTE_ASSISTANCE</span></span></p></td>
<td><p><span data-ttu-id="d57a6-258">4</span><span class="sxs-lookup"><span data-stu-id="d57a6-258">4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d57a6-259">APP_SHARING</span><span class="sxs-lookup"><span data-stu-id="d57a6-259">APP_SHARING</span></span></p></td>
<td><p><span data-ttu-id="d57a6-260">8 </span><span class="sxs-lookup"><span data-stu-id="d57a6-260">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d57a6-261">PUERTOS</span><span class="sxs-lookup"><span data-stu-id="d57a6-261">AUDIO</span></span></p></td>
<td><p><span data-ttu-id="d57a6-262">16 </span><span class="sxs-lookup"><span data-stu-id="d57a6-262">16</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d57a6-263">VÍDEO</span><span class="sxs-lookup"><span data-stu-id="d57a6-263">VIDEO</span></span></p></td>
<td><p><span data-ttu-id="d57a6-264">32</span><span class="sxs-lookup"><span data-stu-id="d57a6-264">32</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d57a6-265">APP_INVITE</span><span class="sxs-lookup"><span data-stu-id="d57a6-265">APP_INVITE</span></span></p></td>
<td><p><span data-ttu-id="d57a6-266">64</span><span class="sxs-lookup"><span data-stu-id="d57a6-266">64</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d57a6-267"><strong>User1Flag</strong></span><span class="sxs-lookup"><span data-stu-id="d57a6-267"><strong>User1Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="d57a6-268">smallint</span><span class="sxs-lookup"><span data-stu-id="d57a6-268">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d57a6-p124">Conjunto de bits que señala los atributos del usuario 1. Se enumeran las siguientes definiciones de atributo:</span><span class="sxs-lookup"><span data-stu-id="d57a6-p124">A bit set that indicates the User1 attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="d57a6-271">0x01 - Integrado con el teléfono de escritorio</span><span class="sxs-lookup"><span data-stu-id="d57a6-271">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d57a6-272"><strong>User2Flag</strong></span><span class="sxs-lookup"><span data-stu-id="d57a6-272"><strong>User2Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="d57a6-273">smallint</span><span class="sxs-lookup"><span data-stu-id="d57a6-273">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d57a6-p125">Conjunto de bits que señala los atributos del usuario 2. Se enumeran las siguientes definiciones de atributo:</span><span class="sxs-lookup"><span data-stu-id="d57a6-p125">A bit set that indicates the User2 attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="d57a6-276">0x01 - Integrado con el teléfono de escritorio</span><span class="sxs-lookup"><span data-stu-id="d57a6-276">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d57a6-277"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="d57a6-277"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="d57a6-278">smallint</span><span class="sxs-lookup"><span data-stu-id="d57a6-278">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d57a6-p126">Conjunto de bits que indica los atributos de la llamada. Se enumeran las siguientes definiciones de atributo:</span><span class="sxs-lookup"><span data-stu-id="d57a6-p126">A bit set that indicates the call attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="d57a6-281">0x01 - Sesión reintentada</span><span class="sxs-lookup"><span data-stu-id="d57a6-281">0x01 - Retried Session</span></span></p></li>
<li><p><span data-ttu-id="d57a6-282">0x02 - Una llamada realizada por el agente en nombre de un grupo de respuestas</span><span class="sxs-lookup"><span data-stu-id="d57a6-282">0x02 - A call made by agent on behalf of a response group</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d57a6-283"><strong>Procesan</strong></span><span class="sxs-lookup"><span data-stu-id="d57a6-283"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="d57a6-284">bit</span><span class="sxs-lookup"><span data-stu-id="d57a6-284">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d57a6-285">Para uso interno del servicio de supervisión.</span><span class="sxs-lookup"><span data-stu-id="d57a6-285">For internal use by the Monitoring service.</span></span></p>
<p><span data-ttu-id="d57a6-286">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d57a6-286">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d57a6-287">\*Para la mayoría de las sesiones, SessionIdSeq tendrá el valor de 1.</span><span class="sxs-lookup"><span data-stu-id="d57a6-287">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="d57a6-288">Si hay varias sesiones que comienzan exactamente a la misma hora, el valor de SessionIdSeq para una será 1, para otra, 2 y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="d57a6-288">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

