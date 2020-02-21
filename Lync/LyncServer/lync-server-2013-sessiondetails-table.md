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
ms.openlocfilehash: bfdf5552f150b23c50e8ad6867e90f96a6b586fb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182313"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="2194a-102">Tabla SessionDetails en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2194a-102">SessionDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2194a-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="2194a-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="2194a-104">Cada registro representa una sesión punto a punto, que puede ser una llamada de teléfono de VoIP a VoIP, una sesión de mensajería instantánea entre dos partes o cualquier otro tipo de sesión.</span><span class="sxs-lookup"><span data-stu-id="2194a-104">Each record represents one peer-to-peer session, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="2194a-105">Puede realizar una combinación de tablas con la [tabla de medios en Lync Server 2013](lync-server-2013-media-table.md) para encontrar los detalles de cada elemento multimedia implicado en esta sesión.</span><span class="sxs-lookup"><span data-stu-id="2194a-105">You can perform a table join with the [Media table in Lync Server 2013](lync-server-2013-media-table.md) to find the details of each media involved in this session.</span></span>

<span data-ttu-id="2194a-106">Tenga en cuenta que los campos IsUser1IntegratedWithDeskPhone y IsUser2IntegratedWithDeskPhone se han quitado de la tabla SessionDetails usada en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2194a-106">Note that the IsUser1IntegratedWithDeskPhone and the IsUser2IntegratedWithDeskPhone fields have been dropped from the SessionDetails table used in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2194a-107">Columna</span><span class="sxs-lookup"><span data-stu-id="2194a-107">Column</span></span></th>
<th><span data-ttu-id="2194a-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="2194a-108">Data Type</span></span></th>
<th><span data-ttu-id="2194a-109">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="2194a-109">Key/Index</span></span></th>
<th><span data-ttu-id="2194a-110">Detalles</span><span class="sxs-lookup"><span data-stu-id="2194a-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2194a-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="2194a-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2194a-112">datetime</span><span class="sxs-lookup"><span data-stu-id="2194a-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="2194a-113">Principal, Externa</span><span class="sxs-lookup"><span data-stu-id="2194a-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="2194a-114">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="2194a-114">Time of session request.</span></span> <span data-ttu-id="2194a-115">Se usa junto con <strong>SessionIdSeq</strong> para identificar una sesión de manera exclusiva.</span><span class="sxs-lookup"><span data-stu-id="2194a-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="2194a-116">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2194a-116">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2194a-117"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="2194a-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="2194a-118">int</span><span class="sxs-lookup"><span data-stu-id="2194a-118">int</span></span></p></td>
<td><p><span data-ttu-id="2194a-119">Principal, Exterior</span><span class="sxs-lookup"><span data-stu-id="2194a-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="2194a-120">Número del identificador para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="2194a-120">ID number to identify the session.</span></span> <span data-ttu-id="2194a-121">Se usa junto con <strong>SessionIdTime</strong> para identificar de forma única una sesión. \* Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2194a-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.\* See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2194a-122"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="2194a-122"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="2194a-123">identificador</span><span class="sxs-lookup"><span data-stu-id="2194a-123">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2194a-124">GUID con el que se correlacionan varias sesiones.</span><span class="sxs-lookup"><span data-stu-id="2194a-124">A GUID to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2194a-125"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="2194a-125"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2194a-126">datetime</span><span class="sxs-lookup"><span data-stu-id="2194a-126">datetime</span></span></p></td>
<td><p><span data-ttu-id="2194a-127">Externa</span><span class="sxs-lookup"><span data-stu-id="2194a-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2194a-128">Número con el que se identifica el diálogo que se reemplazó por la sesión actual.</span><span class="sxs-lookup"><span data-stu-id="2194a-128">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="2194a-129">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2194a-129">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2194a-130"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="2194a-130"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="2194a-131">int</span><span class="sxs-lookup"><span data-stu-id="2194a-131">int</span></span></p></td>
<td><p><span data-ttu-id="2194a-132">Externa</span><span class="sxs-lookup"><span data-stu-id="2194a-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2194a-133">Número con el que se identifica la sesión.</span><span class="sxs-lookup"><span data-stu-id="2194a-133">ID number to identify the session.</span></span> <span data-ttu-id="2194a-134">Se usa junto con <strong>ReplacesDialogIdTime</strong> para identificar de manera exclusiva una sesión que se reemplazó por esta sesión.</span><span class="sxs-lookup"><span data-stu-id="2194a-134">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="2194a-135">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2194a-135">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2194a-136"><strong>User1Id</strong></span><span class="sxs-lookup"><span data-stu-id="2194a-136"><strong>User1Id</strong></span></span></p></td>
<td><p><span data-ttu-id="2194a-137">int</span><span class="sxs-lookup"><span data-stu-id="2194a-137">int</span></span></p></td>
<td><p><span data-ttu-id="2194a-138">Externa</span><span class="sxs-lookup"><span data-stu-id="2194a-138">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2194a-139">Identificador de un usuario de la sesión.</span><span class="sxs-lookup"><span data-stu-id="2194a-139">ID of one user in the session.</span></span> <span data-ttu-id="2194a-140">Consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2194a-140">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2194a-141"><strong>User2Id</strong></span><span class="sxs-lookup"><span data-stu-id="2194a-141"><strong>User2Id</strong></span></span></p></td>
<td><p><span data-ttu-id="2194a-142">int</span><span class="sxs-lookup"><span data-stu-id="2194a-142">int</span></span></p></td>
<td><p><span data-ttu-id="2194a-143">Externa</span><span class="sxs-lookup"><span data-stu-id="2194a-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2194a-144">Identificador de otro usuario de la sesión.</span><span class="sxs-lookup"><span data-stu-id="2194a-144">ID of the other user in the session.</span></span> <span data-ttu-id="2194a-145">Consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2194a-145">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2194a-146"><strong>User1EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="2194a-146"><strong>User1EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="2194a-147">Identificador</span><span class="sxs-lookup"><span data-stu-id="2194a-147">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2194a-148">GUID que identifica el extremo que utilizó el primer usuario en la sesión.</span><span class="sxs-lookup"><span data-stu-id="2194a-148">GUID that identifies the endpoint used by the first user in the session.</span></span></p>
<p><span data-ttu-id="2194a-149">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2194a-149">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2194a-150"><strong>User2EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="2194a-150"><strong>User2EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="2194a-151">Identificador</span><span class="sxs-lookup"><span data-stu-id="2194a-151">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2194a-152">GUID que identifica el extremo que utilizó el segundo usuario en la sesión.</span><span class="sxs-lookup"><span data-stu-id="2194a-152">GUID that identifies the endpoint used by the second user in the session.</span></span></p>
<p><span data-ttu-id="2194a-153">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2194a-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2194a-154"><strong>TargetUserId</strong></span><span class="sxs-lookup"><span data-stu-id="2194a-154"><strong>TargetUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="2194a-155">int</span><span class="sxs-lookup"><span data-stu-id="2194a-155">int</span></span></p></td>
<td><p><span data-ttu-id="2194a-156">Externa</span><span class="sxs-lookup"><span data-stu-id="2194a-156">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2194a-157">URI de destinatario original en la solicitud SIP.</span><span class="sxs-lookup"><span data-stu-id="2194a-157">The original To user URI in the SIP request.</span></span> <span data-ttu-id="2194a-158">Consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2194a-158">see the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2194a-159"><strong>SessionStartedById</strong></span><span class="sxs-lookup"><span data-stu-id="2194a-159"><strong>SessionStartedById</strong></span></span></p></td>
<td><p><span data-ttu-id="2194a-160">int</span><span class="sxs-lookup"><span data-stu-id="2194a-160">int</span></span></p></td>
<td><p><span data-ttu-id="2194a-161">Externa</span><span class="sxs-lookup"><span data-stu-id="2194a-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2194a-162">Identificador del usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="2194a-162">ID of the user who started the session.</span></span> <span data-ttu-id="2194a-163">Consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2194a-163">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2194a-164"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="2194a-164"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="2194a-165">int</span><span class="sxs-lookup"><span data-stu-id="2194a-165">int</span></span></p></td>
<td><p><span data-ttu-id="2194a-166">Externa</span><span class="sxs-lookup"><span data-stu-id="2194a-166">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2194a-167">Señala el identificador de usuario en cuyo nombre llama el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2194a-167">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="2194a-168">Consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2194a-168">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2194a-169"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="2194a-169"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="2194a-170">int</span><span class="sxs-lookup"><span data-stu-id="2194a-170">int</span></span></p></td>
<td><p><span data-ttu-id="2194a-171">Externa</span><span class="sxs-lookup"><span data-stu-id="2194a-171">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2194a-172">Identificador del usuario por el que se hace referencia a la sesión.</span><span class="sxs-lookup"><span data-stu-id="2194a-172">ID of the user by who the call is referred.</span></span> <span data-ttu-id="2194a-173">Consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2194a-173">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2194a-174"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="2194a-174"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="2194a-175">int</span><span class="sxs-lookup"><span data-stu-id="2194a-175">int</span></span></p></td>
<td><p><span data-ttu-id="2194a-176">Externa</span><span class="sxs-lookup"><span data-stu-id="2194a-176">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2194a-177">Identificador del servidor front-end usado en esta sesión.</span><span class="sxs-lookup"><span data-stu-id="2194a-177">ID of the front-end server used for this session.</span></span> <span data-ttu-id="2194a-178">Consulte la <a href="lync-server-2013-servers-table.md">tabla servidores en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2194a-178">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2194a-179"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="2194a-179"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="2194a-180">int</span><span class="sxs-lookup"><span data-stu-id="2194a-180">int</span></span></p></td>
<td><p><span data-ttu-id="2194a-181">Externa</span><span class="sxs-lookup"><span data-stu-id="2194a-181">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2194a-182">Identificador del grupo en el que se capturó la sesión.</span><span class="sxs-lookup"><span data-stu-id="2194a-182">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="2194a-183">Consulte la <a href="lync-server-2013-pools-table.md">tabla grupos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2194a-183">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2194a-184"><strong>ContentTypeID</strong></span><span class="sxs-lookup"><span data-stu-id="2194a-184"><strong>ContentTypeID</strong></span></span></p></td>
<td><p><span data-ttu-id="2194a-185">int</span><span class="sxs-lookup"><span data-stu-id="2194a-185">int</span></span></p></td>
<td><p><span data-ttu-id="2194a-186">Externa</span><span class="sxs-lookup"><span data-stu-id="2194a-186">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2194a-187">Tipo de contenido empleado en la sesión.</span><span class="sxs-lookup"><span data-stu-id="2194a-187">Content type used in the session.</span></span> <span data-ttu-id="2194a-188">Consulte la <a href="lync-server-2013-contenttypes-table.md">tabla contentTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2194a-188">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2194a-189"><strong>User1ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="2194a-189"><strong>User1ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="2194a-190">int</span><span class="sxs-lookup"><span data-stu-id="2194a-190">int</span></span></p></td>
<td><p><span data-ttu-id="2194a-191">Externa</span><span class="sxs-lookup"><span data-stu-id="2194a-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2194a-192">Versión de cliente usada por el usuario 1.</span><span class="sxs-lookup"><span data-stu-id="2194a-192">Client version used by User1.</span></span> <span data-ttu-id="2194a-193">Consulte la <a href="lync-server-2013-clientversions-table.md">tabla ClientVersions en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2194a-193">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2194a-194"><strong>User2ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="2194a-194"><strong>User2ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="2194a-195">int</span><span class="sxs-lookup"><span data-stu-id="2194a-195">int</span></span></p></td>
<td><p><span data-ttu-id="2194a-196">Externa</span><span class="sxs-lookup"><span data-stu-id="2194a-196">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2194a-197">Versión de cliente usada por el usuario 2.</span><span class="sxs-lookup"><span data-stu-id="2194a-197">Client version used by User2.</span></span> <span data-ttu-id="2194a-198">Consulte la <a href="lync-server-2013-clientversions-table.md">tabla ClientVersions en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2194a-198">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2194a-199"><strong>User1EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="2194a-199"><strong>User1EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="2194a-200">int</span><span class="sxs-lookup"><span data-stu-id="2194a-200">int</span></span></p></td>
<td><p><span data-ttu-id="2194a-201">Externa</span><span class="sxs-lookup"><span data-stu-id="2194a-201">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2194a-202">Servidor perimetral usado por el usuario 1.</span><span class="sxs-lookup"><span data-stu-id="2194a-202">Edge Server used by User1.</span></span> <span data-ttu-id="2194a-203">Consulte la <a href="lync-server-2013-edgeservers-table.md">tabla EdgeServers en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2194a-203">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2194a-204"><strong>User2EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="2194a-204"><strong>User2EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="2194a-205">int</span><span class="sxs-lookup"><span data-stu-id="2194a-205">int</span></span></p></td>
<td><p><span data-ttu-id="2194a-206">Externa</span><span class="sxs-lookup"><span data-stu-id="2194a-206">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2194a-207">Servidor perimetral usado por el usuario 2.</span><span class="sxs-lookup"><span data-stu-id="2194a-207">Edge Server used by User2.</span></span> <span data-ttu-id="2194a-208">Consulte la <a href="lync-server-2013-edgeservers-table.md">tabla EdgeServers en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2194a-208">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2194a-209"><strong>IsUser1Internal</strong></span><span class="sxs-lookup"><span data-stu-id="2194a-209"><strong>IsUser1Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="2194a-210">bit</span><span class="sxs-lookup"><span data-stu-id="2194a-210">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2194a-211">Indica si el usuario 1 ha iniciado sesión de manera interna o no.</span><span class="sxs-lookup"><span data-stu-id="2194a-211">Whether User1 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2194a-212"><strong>IsUser2Internal</strong></span><span class="sxs-lookup"><span data-stu-id="2194a-212"><strong>IsUser2Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="2194a-213">bit</span><span class="sxs-lookup"><span data-stu-id="2194a-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2194a-214">Indica si el usuario 2 ha iniciado sesión de manera interna o no.</span><span class="sxs-lookup"><span data-stu-id="2194a-214">Whether User2 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2194a-215"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="2194a-215"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2194a-216">datetime</span><span class="sxs-lookup"><span data-stu-id="2194a-216">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2194a-217">Hora de la primera solicitud INVITE.</span><span class="sxs-lookup"><span data-stu-id="2194a-217">The time of the first INVITE request.</span></span> <span data-ttu-id="2194a-218">Este campo suele rellenarse con datos generados a partir del mensaje INVITE inicial en la sesión.</span><span class="sxs-lookup"><span data-stu-id="2194a-218">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="2194a-219">Si no existe el mensaje INVITE, el campo se rellenará con la fecha y hora del primer mensaje SIP relevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="2194a-219">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="2194a-220">Este campo se suele rellenar con datos generados a partir del mensaje INVITE inicial de la sesión.</span><span class="sxs-lookup"><span data-stu-id="2194a-220">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="2194a-221">Si no hay ningún mensaje INVITE, el campo se rellenará con la fecha y hora del primer mensaje SIP relevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="2194a-221">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2194a-222"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="2194a-222"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2194a-223">datetime</span><span class="sxs-lookup"><span data-stu-id="2194a-223">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2194a-224">Hora de respuesta al primer mensaje INVITE.</span><span class="sxs-lookup"><span data-stu-id="2194a-224">The time of the response to the first INVITE message.</span></span> <span data-ttu-id="2194a-225">Este campo normalmente se rellena con los datos generados a partir del mensaje INVITE inicial en la sesión.</span><span class="sxs-lookup"><span data-stu-id="2194a-225">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="2194a-226">Si no hay ningún mensaje INVITE, el campo se rellena con la fecha y la hora del primer mensaje SIP relevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="2194a-226">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2194a-227"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="2194a-227"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="2194a-228">int</span><span class="sxs-lookup"><span data-stu-id="2194a-228">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2194a-p121">Código de respuesta SIP a la invitación a la sesión. Este campo se suele rellenar con datos generados a partir del mensaje INVITE inicial de la sesión. Si no hay ningún mensaje INVITE, el campo se rellena con la hora y la fecha del primer mensaje SIP correspondiente (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="2194a-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2194a-232"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="2194a-232"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="2194a-233">int</span><span class="sxs-lookup"><span data-stu-id="2194a-233">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2194a-234">Identificador de diagnóstico capturado del encabezado SIP.</span><span class="sxs-lookup"><span data-stu-id="2194a-234">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2194a-235"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="2194a-235"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="2194a-236">int</span><span class="sxs-lookup"><span data-stu-id="2194a-236">int</span></span></p></td>
<td><p><span data-ttu-id="2194a-237">Externa</span><span class="sxs-lookup"><span data-stu-id="2194a-237">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2194a-238">Prioridad de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2194a-238">Call priority.</span></span> <span data-ttu-id="2194a-239">Consulte la <a href="lync-server-2013-callpriorities-table.md">tabla CallPriorities en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2194a-239">See the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2194a-240"><strong>User1MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="2194a-240"><strong>User1MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="2194a-241">int</span><span class="sxs-lookup"><span data-stu-id="2194a-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2194a-242">Número de mensajes que envió el usuario 1 durante la sesión.</span><span class="sxs-lookup"><span data-stu-id="2194a-242">Number of messages sent by User1 during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2194a-243"><strong>User2MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="2194a-243"><strong>User2MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="2194a-244">int</span><span class="sxs-lookup"><span data-stu-id="2194a-244">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2194a-245">Número de mensajes que envió el usuario 2 durante la sesión.</span><span class="sxs-lookup"><span data-stu-id="2194a-245">Number of messages sent by User2 during the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2194a-246"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="2194a-246"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2194a-247">datetime</span><span class="sxs-lookup"><span data-stu-id="2194a-247">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2194a-248">Hora al final de la sesión.</span><span class="sxs-lookup"><span data-stu-id="2194a-248">Time at the end of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2194a-249"><strong>MediaTypes</strong></span><span class="sxs-lookup"><span data-stu-id="2194a-249"><strong>MediaTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="2194a-250">int</span><span class="sxs-lookup"><span data-stu-id="2194a-250">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2194a-p123">Conjunto de bits que indica el tipo de medio de esta sesión. A continuación se enumeran las definiciones de los tipos:</span><span class="sxs-lookup"><span data-stu-id="2194a-p123">A bit set that indicates the media type of this session. Listed are the definitions of the types:</span></span></p>
<h3 id="section-1"> </h3>
<div>
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2194a-253">Mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="2194a-253">IM</span></span></p></td>
<td><p><span data-ttu-id="2194a-254">1</span><span class="sxs-lookup"><span data-stu-id="2194a-254">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2194a-255">FILE_TRANSFER</span><span class="sxs-lookup"><span data-stu-id="2194a-255">FILE_TRANSFER</span></span></p></td>
<td><p><span data-ttu-id="2194a-256">segundo</span><span class="sxs-lookup"><span data-stu-id="2194a-256">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2194a-257">REMOTE_ASSISTANCE</span><span class="sxs-lookup"><span data-stu-id="2194a-257">REMOTE_ASSISTANCE</span></span></p></td>
<td><p><span data-ttu-id="2194a-258">4</span><span class="sxs-lookup"><span data-stu-id="2194a-258">4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2194a-259">APP_SHARING</span><span class="sxs-lookup"><span data-stu-id="2194a-259">APP_SHARING</span></span></p></td>
<td><p><span data-ttu-id="2194a-260">8 </span><span class="sxs-lookup"><span data-stu-id="2194a-260">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2194a-261">PUERTOS</span><span class="sxs-lookup"><span data-stu-id="2194a-261">AUDIO</span></span></p></td>
<td><p><span data-ttu-id="2194a-262">16 </span><span class="sxs-lookup"><span data-stu-id="2194a-262">16</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2194a-263">VÍDEO</span><span class="sxs-lookup"><span data-stu-id="2194a-263">VIDEO</span></span></p></td>
<td><p><span data-ttu-id="2194a-264">32</span><span class="sxs-lookup"><span data-stu-id="2194a-264">32</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2194a-265">APP_INVITE</span><span class="sxs-lookup"><span data-stu-id="2194a-265">APP_INVITE</span></span></p></td>
<td><p><span data-ttu-id="2194a-266">64</span><span class="sxs-lookup"><span data-stu-id="2194a-266">64</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2194a-267"><strong>User1Flag</strong></span><span class="sxs-lookup"><span data-stu-id="2194a-267"><strong>User1Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="2194a-268">smallint</span><span class="sxs-lookup"><span data-stu-id="2194a-268">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2194a-p124">Conjunto de bits que señala los atributos del usuario 1. Se enumeran las siguientes definiciones de atributo:</span><span class="sxs-lookup"><span data-stu-id="2194a-p124">A bit set that indicates the User1 attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="2194a-271">0x01 - Integrado con el teléfono de escritorio</span><span class="sxs-lookup"><span data-stu-id="2194a-271">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2194a-272"><strong>User2Flag</strong></span><span class="sxs-lookup"><span data-stu-id="2194a-272"><strong>User2Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="2194a-273">smallint</span><span class="sxs-lookup"><span data-stu-id="2194a-273">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2194a-p125">Conjunto de bits que señala los atributos del usuario 2. Se enumeran las siguientes definiciones de atributo:</span><span class="sxs-lookup"><span data-stu-id="2194a-p125">A bit set that indicates the User2 attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="2194a-276">0x01 - Integrado con el teléfono de escritorio</span><span class="sxs-lookup"><span data-stu-id="2194a-276">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2194a-277"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="2194a-277"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="2194a-278">smallint</span><span class="sxs-lookup"><span data-stu-id="2194a-278">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2194a-p126">Conjunto de bits que indica los atributos de la llamada. Se enumeran las siguientes definiciones de atributo:</span><span class="sxs-lookup"><span data-stu-id="2194a-p126">A bit set that indicates the call attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="2194a-281">0x01 - Sesión reintentada</span><span class="sxs-lookup"><span data-stu-id="2194a-281">0x01 - Retried Session</span></span></p></li>
<li><p><span data-ttu-id="2194a-282">0x02 - Una llamada realizada por el agente en nombre de un grupo de respuestas</span><span class="sxs-lookup"><span data-stu-id="2194a-282">0x02 - A call made by agent on behalf of a response group</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2194a-283"><strong>Procesan</strong></span><span class="sxs-lookup"><span data-stu-id="2194a-283"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="2194a-284">bit</span><span class="sxs-lookup"><span data-stu-id="2194a-284">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2194a-285">Para uso interno del servicio de supervisión.</span><span class="sxs-lookup"><span data-stu-id="2194a-285">For internal use by the Monitoring service.</span></span></p>
<p><span data-ttu-id="2194a-286">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2194a-286">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2194a-287">\*Para la mayoría de las sesiones, SessionIdSeq tendrá el valor de 1.</span><span class="sxs-lookup"><span data-stu-id="2194a-287">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="2194a-288">Si hay varias sesiones que comienzan exactamente a la misma hora, el valor de SessionIdSeq para una será 1, para otra, 2 y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="2194a-288">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

