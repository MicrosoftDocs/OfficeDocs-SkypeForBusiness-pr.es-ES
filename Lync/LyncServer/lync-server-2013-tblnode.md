---
title: 'Lync Server 2013: tblNode'
description: 'Lync Server 2013: tblNode.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblNode
ms:assetid: a31d2961-aa83-4286-a12e-15d279c95f19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615024(v=OCS.15)
ms:contentKeyID: 48184960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0a5d630621c32cbc54501249c7a679bf4023c60
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547556"
---
# <a name="tblnode-in-lync-server-2013"></a><span data-ttu-id="4c4ee-103">tblNode en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4c4ee-103">tblNode in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c4ee-104">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="4c4ee-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="4c4ee-105">tblNode contiene el árbol de objetos (con nodos de categoría o de salón de chat) tal como se administra en el panel de control de Lync Server 2013 y en los cmdlets administrativos.</span><span class="sxs-lookup"><span data-stu-id="4c4ee-105">tblNode contains the object tree (with category or chat room nodes) as managed in the Lync Server 2013 Control Panel and administrative cmdlets.</span></span>

### <a name="columns"></a><span data-ttu-id="4c4ee-106">Columnas</span><span class="sxs-lookup"><span data-stu-id="4c4ee-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c4ee-107">Columna</span><span class="sxs-lookup"><span data-stu-id="4c4ee-107">Column</span></span></th>
<th><span data-ttu-id="4c4ee-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="4c4ee-108">Type</span></span></th>
<th><span data-ttu-id="4c4ee-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="4c4ee-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c4ee-110">nodeID</span><span class="sxs-lookup"><span data-stu-id="4c4ee-110">nodeID</span></span></p></td>
<td><p><span data-ttu-id="4c4ee-111">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="4c4ee-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="4c4ee-112">IDENTIFICADOR de nodo (número único).</span><span class="sxs-lookup"><span data-stu-id="4c4ee-112">Node ID (unique number).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c4ee-113">nodeGuid</span><span class="sxs-lookup"><span data-stu-id="4c4ee-113">nodeGuid</span></span></p></td>
<td><p><span data-ttu-id="4c4ee-114">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="4c4ee-114">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="4c4ee-115">GUID de nodo.</span><span class="sxs-lookup"><span data-stu-id="4c4ee-115">Node GUID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c4ee-116">parentID</span><span class="sxs-lookup"><span data-stu-id="4c4ee-116">parentID</span></span></p></td>
<td><p><span data-ttu-id="4c4ee-117">entero</span><span class="sxs-lookup"><span data-stu-id="4c4ee-117">int</span></span></p></td>
<td><p><span data-ttu-id="4c4ee-118">IDENTIFICADOR de nodo de primario.</span><span class="sxs-lookup"><span data-stu-id="4c4ee-118">Node ID of parent.</span></span> <span data-ttu-id="4c4ee-119">El nodo raíz (con identificador 1) también se incluye como primario.</span><span class="sxs-lookup"><span data-stu-id="4c4ee-119">The root node (with ID 1) includes itself as parent as well.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c4ee-120">nodeType</span><span class="sxs-lookup"><span data-stu-id="4c4ee-120">nodeType</span></span></p></td>
<td><p><span data-ttu-id="4c4ee-121">bit, not null</span><span class="sxs-lookup"><span data-stu-id="4c4ee-121">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="4c4ee-122">True si el nodo es una categoría.</span><span class="sxs-lookup"><span data-stu-id="4c4ee-122">True if the node is a category.</span></span></p>
<p><span data-ttu-id="4c4ee-123">False si el nodo es un salón de chat.</span><span class="sxs-lookup"><span data-stu-id="4c4ee-123">False if the node is a chat room.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c4ee-124">nodeName</span><span class="sxs-lookup"><span data-stu-id="4c4ee-124">nodeName</span></span></p></td>
<td><p><span data-ttu-id="4c4ee-125">nvarchar (256), no NULL</span><span class="sxs-lookup"><span data-stu-id="4c4ee-125">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="4c4ee-126">Nombre del nodo.</span><span class="sxs-lookup"><span data-stu-id="4c4ee-126">Node name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c4ee-127">nodeDesc</span><span class="sxs-lookup"><span data-stu-id="4c4ee-127">nodeDesc</span></span></p></td>
<td><p><span data-ttu-id="4c4ee-128">nvarchar (256), no NULL</span><span class="sxs-lookup"><span data-stu-id="4c4ee-128">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="4c4ee-129">Descripción del nodo.</span><span class="sxs-lookup"><span data-stu-id="4c4ee-129">Node description.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c4ee-130">invitar</span><span class="sxs-lookup"><span data-stu-id="4c4ee-130">invite</span></span></p></td>
<td><p><span data-ttu-id="4c4ee-131">bit</span><span class="sxs-lookup"><span data-stu-id="4c4ee-131">bit</span></span></p></td>
<td><p><span data-ttu-id="4c4ee-132">Para categorías:</span><span class="sxs-lookup"><span data-stu-id="4c4ee-132">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="4c4ee-133">True si se activan las invitaciones.</span><span class="sxs-lookup"><span data-stu-id="4c4ee-133">True if invites are on.</span></span></p></li>
<li><p><span data-ttu-id="4c4ee-134">False si los invitados están desactivados.</span><span class="sxs-lookup"><span data-stu-id="4c4ee-134">False if invites are off.</span></span></p></li>
</ul>
<p><span data-ttu-id="4c4ee-135">Para los salones:</span><span class="sxs-lookup"><span data-stu-id="4c4ee-135">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="4c4ee-136">False si los invitados están desactivados (invalida la categoría principal).</span><span class="sxs-lookup"><span data-stu-id="4c4ee-136">False if invites are off (overrides the parent category).</span></span></p></li>
<li><p><span data-ttu-id="4c4ee-137">NULL si la configuración de invitaciones se ha heredado de la categoría principal.</span><span class="sxs-lookup"><span data-stu-id="4c4ee-137">Null if the invites setting is inherited from the parent category.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c4ee-138">iniciado sesión</span><span class="sxs-lookup"><span data-stu-id="4c4ee-138">logged</span></span></p></td>
<td><p><span data-ttu-id="4c4ee-139">bit</span><span class="sxs-lookup"><span data-stu-id="4c4ee-139">bit</span></span></p></td>
<td><p><span data-ttu-id="4c4ee-140">Para categorías:</span><span class="sxs-lookup"><span data-stu-id="4c4ee-140">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="4c4ee-141">True si el historial de chat está activado.</span><span class="sxs-lookup"><span data-stu-id="4c4ee-141">True if chat history is on.</span></span></p></li>
<li><p><span data-ttu-id="4c4ee-142">False si el historial de chat está desactivado.</span><span class="sxs-lookup"><span data-stu-id="4c4ee-142">False if chat history is off.</span></span></p></li>
</ul>
<p><span data-ttu-id="4c4ee-143">Para los salones:</span><span class="sxs-lookup"><span data-stu-id="4c4ee-143">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="4c4ee-144">Que.</span><span class="sxs-lookup"><span data-stu-id="4c4ee-144">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c4ee-145">filePost</span><span class="sxs-lookup"><span data-stu-id="4c4ee-145">filePost</span></span></p></td>
<td><p><span data-ttu-id="4c4ee-146">bit</span><span class="sxs-lookup"><span data-stu-id="4c4ee-146">bit</span></span></p></td>
<td><p><span data-ttu-id="4c4ee-147">Para categorías:</span><span class="sxs-lookup"><span data-stu-id="4c4ee-147">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="4c4ee-148">True si se permiten las cargas de archivos.</span><span class="sxs-lookup"><span data-stu-id="4c4ee-148">True if file uploads are allowed.</span></span></p></li>
<li><p><span data-ttu-id="4c4ee-149">False si no se permiten las cargas de archivos.</span><span class="sxs-lookup"><span data-stu-id="4c4ee-149">False if file uploads are disallowed.</span></span></p></li>
</ul>
<p><span data-ttu-id="4c4ee-150">Para los salones:</span><span class="sxs-lookup"><span data-stu-id="4c4ee-150">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="4c4ee-151">Que.</span><span class="sxs-lookup"><span data-stu-id="4c4ee-151">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c4ee-152">deshabilitado</span><span class="sxs-lookup"><span data-stu-id="4c4ee-152">disabled</span></span></p></td>
<td><p><span data-ttu-id="4c4ee-153">bit, not null</span><span class="sxs-lookup"><span data-stu-id="4c4ee-153">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="4c4ee-154">True si el salón de chat está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="4c4ee-154">True if the chat room is disabled.</span></span> <span data-ttu-id="4c4ee-155">Solo se aplica a salones de chat.</span><span class="sxs-lookup"><span data-stu-id="4c4ee-155">Applies only to chat rooms.</span></span> <span data-ttu-id="4c4ee-156">(False para las categorías.)</span><span class="sxs-lookup"><span data-stu-id="4c4ee-156">(False for categories.)</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c4ee-157">comportamiento</span><span class="sxs-lookup"><span data-stu-id="4c4ee-157">behavior</span></span></p></td>
<td><p><span data-ttu-id="4c4ee-158">smallint, no NULL</span><span class="sxs-lookup"><span data-stu-id="4c4ee-158">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="4c4ee-159">Comportamiento (buscar en la tabla EnumValue):</span><span class="sxs-lookup"><span data-stu-id="4c4ee-159">Behavior (looked up in EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="4c4ee-160">4: normal (salones de chat normales).</span><span class="sxs-lookup"><span data-stu-id="4c4ee-160">4: Normal (normal chat rooms).</span></span></p></li>
<li><p><span data-ttu-id="4c4ee-161">5: auditorio (los salones de chat de auditorio, solo los moderadores pueden contribuir).</span><span class="sxs-lookup"><span data-stu-id="4c4ee-161">5: Auditorium (auditorium chat rooms, only presenters can contribute).</span></span></p></li>
</ul>
<p><span data-ttu-id="4c4ee-162">Solo se aplica a salones de chat.</span><span class="sxs-lookup"><span data-stu-id="4c4ee-162">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c4ee-163">visibility</span><span class="sxs-lookup"><span data-stu-id="4c4ee-163">visibility</span></span></p></td>
<td><p><span data-ttu-id="4c4ee-164">smallint, no NULL</span><span class="sxs-lookup"><span data-stu-id="4c4ee-164">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="4c4ee-165">Visibilidad (buscar en la tabla EnumValue):</span><span class="sxs-lookup"><span data-stu-id="4c4ee-165">Visibility (looked up on EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="4c4ee-166">2: privado</span><span class="sxs-lookup"><span data-stu-id="4c4ee-166">2: Private</span></span></p></li>
<li><p><span data-ttu-id="4c4ee-167">3: con ámbito</span><span class="sxs-lookup"><span data-stu-id="4c4ee-167">3: Scoped</span></span></p></li>
<li><p><span data-ttu-id="4c4ee-168">6: abrir</span><span class="sxs-lookup"><span data-stu-id="4c4ee-168">6: Open</span></span></p></li>
</ul>
<p><span data-ttu-id="4c4ee-169">Solo se aplica a salones de chat.</span><span class="sxs-lookup"><span data-stu-id="4c4ee-169">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c4ee-170">siopID</span><span class="sxs-lookup"><span data-stu-id="4c4ee-170">siopID</span></span></p></td>
<td><p><span data-ttu-id="4c4ee-171">GUID</span><span class="sxs-lookup"><span data-stu-id="4c4ee-171">GUID</span></span></p></td>
<td><p><span data-ttu-id="4c4ee-172">Add-In GUID si un complemento está asociado con este salón de chat.</span><span class="sxs-lookup"><span data-stu-id="4c4ee-172">Add-In GUID if an add-in is associated with this chat room.</span></span> <span data-ttu-id="4c4ee-173">(Las categorías no tienen complementos).</span><span class="sxs-lookup"><span data-stu-id="4c4ee-173">(Categories do not have add-ins.)</span></span></p>
<p><span data-ttu-id="4c4ee-174">La información del complemento se busca en la tabla SiopWhiteList.</span><span class="sxs-lookup"><span data-stu-id="4c4ee-174">The add-in information is looked up in SiopWhiteList table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c4ee-175">nodeAddedBy</span><span class="sxs-lookup"><span data-stu-id="4c4ee-175">nodeAddedBy</span></span></p></td>
<td><p><span data-ttu-id="4c4ee-176">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="4c4ee-176">int, not null</span></span></p></td>
<td><p><span data-ttu-id="4c4ee-177">IDENTIFICADOR de la entidad de identidad que creó este nodo.</span><span class="sxs-lookup"><span data-stu-id="4c4ee-177">ID of the principal that created this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c4ee-178">nodeAddedOn</span><span class="sxs-lookup"><span data-stu-id="4c4ee-178">nodeAddedOn</span></span></p></td>
<td><p><span data-ttu-id="4c4ee-179">bigint, no NULL</span><span class="sxs-lookup"><span data-stu-id="4c4ee-179">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="4c4ee-180">Marca de tiempo de la creación del nodo.</span><span class="sxs-lookup"><span data-stu-id="4c4ee-180">Time stamp of the node creation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c4ee-181">nodeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="4c4ee-181">nodeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="4c4ee-182">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="4c4ee-182">int, not null</span></span></p></td>
<td><p><span data-ttu-id="4c4ee-183">IDENTIFICADOR de la entidad de identidad que realizó la última actualización de este nodo.</span><span class="sxs-lookup"><span data-stu-id="4c4ee-183">ID of the principal that did the latest update of this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c4ee-184">nodeUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="4c4ee-184">nodeUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="4c4ee-185">bigint, no NULL</span><span class="sxs-lookup"><span data-stu-id="4c4ee-185">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="4c4ee-186">Marca de tiempo de la última actualización de este nodo.</span><span class="sxs-lookup"><span data-stu-id="4c4ee-186">Time stamp of the latest update of this node.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c4ee-187">purgedOn</span><span class="sxs-lookup"><span data-stu-id="4c4ee-187">purgedOn</span></span></p></td>
<td><p><span data-ttu-id="4c4ee-188">datetime</span><span class="sxs-lookup"><span data-stu-id="4c4ee-188">datetime</span></span></p></td>
<td><p><span data-ttu-id="4c4ee-189">Hora de la última operación de purga (la eliminación de ámbitos de la tabla tblScopedPrincipal y los roles de la tabla tblPrincipalRole) que afectaban a este nodo.</span><span class="sxs-lookup"><span data-stu-id="4c4ee-189">Time of the latest purge operation (removal of scopes from tblScopedPrincipal table and roles from tblPrincipalRole table) that affected this node.</span></span> <span data-ttu-id="4c4ee-190">Se usa en el mecanismo de actualización de caché interna del servicio de chat.</span><span class="sxs-lookup"><span data-stu-id="4c4ee-190">This is used by the Chat service’s internal cache update mechanism.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="4c4ee-191">Keys</span><span class="sxs-lookup"><span data-stu-id="4c4ee-191">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c4ee-192">Columna</span><span class="sxs-lookup"><span data-stu-id="4c4ee-192">Column</span></span></th>
<th><span data-ttu-id="4c4ee-193">Descripción</span><span class="sxs-lookup"><span data-stu-id="4c4ee-193">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c4ee-194">nodeID</span><span class="sxs-lookup"><span data-stu-id="4c4ee-194">nodeID</span></span></p></td>
<td><p><span data-ttu-id="4c4ee-195">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="4c4ee-195">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c4ee-196">comportamiento</span><span class="sxs-lookup"><span data-stu-id="4c4ee-196">behavior</span></span></p></td>
<td><p><span data-ttu-id="4c4ee-197">Clave externa con búsqueda en la tabla tblEnumValue. valueID.</span><span class="sxs-lookup"><span data-stu-id="4c4ee-197">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c4ee-198">visibility</span><span class="sxs-lookup"><span data-stu-id="4c4ee-198">visibility</span></span></p></td>
<td><p><span data-ttu-id="4c4ee-199">Clave externa con búsqueda en la tabla tblEnumValue. valueID.</span><span class="sxs-lookup"><span data-stu-id="4c4ee-199">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c4ee-200">parentID</span><span class="sxs-lookup"><span data-stu-id="4c4ee-200">parentID</span></span></p></td>
<td><p><span data-ttu-id="4c4ee-201">Clave externa con búsqueda en la tabla tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="4c4ee-201">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c4ee-202">siopID</span><span class="sxs-lookup"><span data-stu-id="4c4ee-202">siopID</span></span></p></td>
<td><p><span data-ttu-id="4c4ee-203">Clave externa con búsqueda en la tabla tblSiopWhiteList. siopId.</span><span class="sxs-lookup"><span data-stu-id="4c4ee-203">Foreign key with lookup in tblSiopWhiteList.siopId table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

