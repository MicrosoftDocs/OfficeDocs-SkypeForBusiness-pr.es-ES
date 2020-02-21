---
title: 'Lync Server 2013: tblNode'
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
ms.openlocfilehash: 459b5393f255ade4e510f17c11beccf2f38f7cfc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214556"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblnode-in-lync-server-2013"></a><span data-ttu-id="42e71-102">tblNode en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42e71-102">tblNode in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42e71-103">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="42e71-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="42e71-104">tblNode contiene el árbol de objetos (con nodos de categoría o de salón de chat) tal como se administra en el panel de control de Lync Server 2013 y en los cmdlets administrativos.</span><span class="sxs-lookup"><span data-stu-id="42e71-104">tblNode contains the object tree (with category or chat room nodes) as managed in the Lync Server 2013 Control Panel and administrative cmdlets.</span></span>

### <a name="columns"></a><span data-ttu-id="42e71-105">Columns</span><span class="sxs-lookup"><span data-stu-id="42e71-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="42e71-106">Columna</span><span class="sxs-lookup"><span data-stu-id="42e71-106">Column</span></span></th>
<th><span data-ttu-id="42e71-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="42e71-107">Type</span></span></th>
<th><span data-ttu-id="42e71-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="42e71-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="42e71-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="42e71-109">nodeID</span></span></p></td>
<td><p><span data-ttu-id="42e71-110">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="42e71-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="42e71-111">IDENTIFICADOR de nodo (número único).</span><span class="sxs-lookup"><span data-stu-id="42e71-111">Node ID (unique number).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42e71-112">nodeGuid</span><span class="sxs-lookup"><span data-stu-id="42e71-112">nodeGuid</span></span></p></td>
<td><p><span data-ttu-id="42e71-113">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="42e71-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="42e71-114">GUID de nodo.</span><span class="sxs-lookup"><span data-stu-id="42e71-114">Node GUID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42e71-115">parentID</span><span class="sxs-lookup"><span data-stu-id="42e71-115">parentID</span></span></p></td>
<td><p><span data-ttu-id="42e71-116">int</span><span class="sxs-lookup"><span data-stu-id="42e71-116">int</span></span></p></td>
<td><p><span data-ttu-id="42e71-117">IDENTIFICADOR de nodo de primario.</span><span class="sxs-lookup"><span data-stu-id="42e71-117">Node ID of parent.</span></span> <span data-ttu-id="42e71-118">El nodo raíz (con identificador 1) también se incluye como primario.</span><span class="sxs-lookup"><span data-stu-id="42e71-118">The root node (with ID 1) includes itself as parent as well.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42e71-119">nodeType</span><span class="sxs-lookup"><span data-stu-id="42e71-119">nodeType</span></span></p></td>
<td><p><span data-ttu-id="42e71-120">bit, not null</span><span class="sxs-lookup"><span data-stu-id="42e71-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="42e71-121">True si el nodo es una categoría.</span><span class="sxs-lookup"><span data-stu-id="42e71-121">True if the node is a category.</span></span></p>
<p><span data-ttu-id="42e71-122">False si el nodo es un salón de chat.</span><span class="sxs-lookup"><span data-stu-id="42e71-122">False if the node is a chat room.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42e71-123">nodeName</span><span class="sxs-lookup"><span data-stu-id="42e71-123">nodeName</span></span></p></td>
<td><p><span data-ttu-id="42e71-124">nvarchar (256), no NULL</span><span class="sxs-lookup"><span data-stu-id="42e71-124">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="42e71-125">Nombre del nodo.</span><span class="sxs-lookup"><span data-stu-id="42e71-125">Node name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42e71-126">nodeDesc</span><span class="sxs-lookup"><span data-stu-id="42e71-126">nodeDesc</span></span></p></td>
<td><p><span data-ttu-id="42e71-127">nvarchar (256), no NULL</span><span class="sxs-lookup"><span data-stu-id="42e71-127">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="42e71-128">Descripción del nodo.</span><span class="sxs-lookup"><span data-stu-id="42e71-128">Node description.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42e71-129">invitar</span><span class="sxs-lookup"><span data-stu-id="42e71-129">invite</span></span></p></td>
<td><p><span data-ttu-id="42e71-130">bit</span><span class="sxs-lookup"><span data-stu-id="42e71-130">bit</span></span></p></td>
<td><p><span data-ttu-id="42e71-131">Para categorías:</span><span class="sxs-lookup"><span data-stu-id="42e71-131">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="42e71-132">True si se activan las invitaciones.</span><span class="sxs-lookup"><span data-stu-id="42e71-132">True if invites are on.</span></span></p></li>
<li><p><span data-ttu-id="42e71-133">False si los invitados están desactivados.</span><span class="sxs-lookup"><span data-stu-id="42e71-133">False if invites are off.</span></span></p></li>
</ul>
<p><span data-ttu-id="42e71-134">Para los salones:</span><span class="sxs-lookup"><span data-stu-id="42e71-134">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="42e71-135">False si los invitados están desactivados (invalida la categoría principal).</span><span class="sxs-lookup"><span data-stu-id="42e71-135">False if invites are off (overrides the parent category).</span></span></p></li>
<li><p><span data-ttu-id="42e71-136">NULL si la configuración de invitaciones se ha heredado de la categoría principal.</span><span class="sxs-lookup"><span data-stu-id="42e71-136">Null if the invites setting is inherited from the parent category.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42e71-137">iniciado sesión</span><span class="sxs-lookup"><span data-stu-id="42e71-137">logged</span></span></p></td>
<td><p><span data-ttu-id="42e71-138">bit</span><span class="sxs-lookup"><span data-stu-id="42e71-138">bit</span></span></p></td>
<td><p><span data-ttu-id="42e71-139">Para categorías:</span><span class="sxs-lookup"><span data-stu-id="42e71-139">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="42e71-140">True si el historial de chat está activado.</span><span class="sxs-lookup"><span data-stu-id="42e71-140">True if chat history is on.</span></span></p></li>
<li><p><span data-ttu-id="42e71-141">False si el historial de chat está desactivado.</span><span class="sxs-lookup"><span data-stu-id="42e71-141">False if chat history is off.</span></span></p></li>
</ul>
<p><span data-ttu-id="42e71-142">Para los salones:</span><span class="sxs-lookup"><span data-stu-id="42e71-142">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="42e71-143">Que.</span><span class="sxs-lookup"><span data-stu-id="42e71-143">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42e71-144">filePost</span><span class="sxs-lookup"><span data-stu-id="42e71-144">filePost</span></span></p></td>
<td><p><span data-ttu-id="42e71-145">bit</span><span class="sxs-lookup"><span data-stu-id="42e71-145">bit</span></span></p></td>
<td><p><span data-ttu-id="42e71-146">Para categorías:</span><span class="sxs-lookup"><span data-stu-id="42e71-146">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="42e71-147">True si se permiten las cargas de archivos.</span><span class="sxs-lookup"><span data-stu-id="42e71-147">True if file uploads are allowed.</span></span></p></li>
<li><p><span data-ttu-id="42e71-148">False si no se permiten las cargas de archivos.</span><span class="sxs-lookup"><span data-stu-id="42e71-148">False if file uploads are disallowed.</span></span></p></li>
</ul>
<p><span data-ttu-id="42e71-149">Para los salones:</span><span class="sxs-lookup"><span data-stu-id="42e71-149">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="42e71-150">Que.</span><span class="sxs-lookup"><span data-stu-id="42e71-150">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42e71-151">capacidad</span><span class="sxs-lookup"><span data-stu-id="42e71-151">disabled</span></span></p></td>
<td><p><span data-ttu-id="42e71-152">bit, not null</span><span class="sxs-lookup"><span data-stu-id="42e71-152">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="42e71-153">True si el salón de chat está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="42e71-153">True if the chat room is disabled.</span></span> <span data-ttu-id="42e71-154">Solo se aplica a salones de chat.</span><span class="sxs-lookup"><span data-stu-id="42e71-154">Applies only to chat rooms.</span></span> <span data-ttu-id="42e71-155">(False para las categorías.)</span><span class="sxs-lookup"><span data-stu-id="42e71-155">(False for categories.)</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42e71-156">comportamiento</span><span class="sxs-lookup"><span data-stu-id="42e71-156">behavior</span></span></p></td>
<td><p><span data-ttu-id="42e71-157">smallint, no NULL</span><span class="sxs-lookup"><span data-stu-id="42e71-157">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="42e71-158">Comportamiento (buscar en la tabla EnumValue):</span><span class="sxs-lookup"><span data-stu-id="42e71-158">Behavior (looked up in EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="42e71-159">4: normal (salones de chat normales).</span><span class="sxs-lookup"><span data-stu-id="42e71-159">4: Normal (normal chat rooms).</span></span></p></li>
<li><p><span data-ttu-id="42e71-160">5: auditorio (los salones de chat de auditorio, solo los moderadores pueden contribuir).</span><span class="sxs-lookup"><span data-stu-id="42e71-160">5: Auditorium (auditorium chat rooms, only presenters can contribute).</span></span></p></li>
</ul>
<p><span data-ttu-id="42e71-161">Solo se aplica a salones de chat.</span><span class="sxs-lookup"><span data-stu-id="42e71-161">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42e71-162">visibility</span><span class="sxs-lookup"><span data-stu-id="42e71-162">visibility</span></span></p></td>
<td><p><span data-ttu-id="42e71-163">smallint, no NULL</span><span class="sxs-lookup"><span data-stu-id="42e71-163">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="42e71-164">Visibilidad (buscar en la tabla EnumValue):</span><span class="sxs-lookup"><span data-stu-id="42e71-164">Visibility (looked up on EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="42e71-165">2: privado</span><span class="sxs-lookup"><span data-stu-id="42e71-165">2: Private</span></span></p></li>
<li><p><span data-ttu-id="42e71-166">3: con ámbito</span><span class="sxs-lookup"><span data-stu-id="42e71-166">3: Scoped</span></span></p></li>
<li><p><span data-ttu-id="42e71-167">6: abrir</span><span class="sxs-lookup"><span data-stu-id="42e71-167">6: Open</span></span></p></li>
</ul>
<p><span data-ttu-id="42e71-168">Solo se aplica a salones de chat.</span><span class="sxs-lookup"><span data-stu-id="42e71-168">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42e71-169">siopID</span><span class="sxs-lookup"><span data-stu-id="42e71-169">siopID</span></span></p></td>
<td><p><span data-ttu-id="42e71-170">GUID</span><span class="sxs-lookup"><span data-stu-id="42e71-170">GUID</span></span></p></td>
<td><p><span data-ttu-id="42e71-171">GUID de complemento si un complemento está asociado con este salón de chat.</span><span class="sxs-lookup"><span data-stu-id="42e71-171">Add-In GUID if an add-in is associated with this chat room.</span></span> <span data-ttu-id="42e71-172">(Las categorías no tienen complementos).</span><span class="sxs-lookup"><span data-stu-id="42e71-172">(Categories do not have add-ins.)</span></span></p>
<p><span data-ttu-id="42e71-173">La información del complemento se busca en la tabla SiopWhiteList.</span><span class="sxs-lookup"><span data-stu-id="42e71-173">The add-in information is looked up in SiopWhiteList table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42e71-174">nodeAddedBy</span><span class="sxs-lookup"><span data-stu-id="42e71-174">nodeAddedBy</span></span></p></td>
<td><p><span data-ttu-id="42e71-175">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="42e71-175">int, not null</span></span></p></td>
<td><p><span data-ttu-id="42e71-176">IDENTIFICADOR de la entidad de identidad que creó este nodo.</span><span class="sxs-lookup"><span data-stu-id="42e71-176">ID of the principal that created this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42e71-177">nodeAddedOn</span><span class="sxs-lookup"><span data-stu-id="42e71-177">nodeAddedOn</span></span></p></td>
<td><p><span data-ttu-id="42e71-178">bigint, no NULL</span><span class="sxs-lookup"><span data-stu-id="42e71-178">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="42e71-179">Marca de tiempo de la creación del nodo.</span><span class="sxs-lookup"><span data-stu-id="42e71-179">Time stamp of the node creation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42e71-180">nodeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="42e71-180">nodeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="42e71-181">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="42e71-181">int, not null</span></span></p></td>
<td><p><span data-ttu-id="42e71-182">IDENTIFICADOR de la entidad de identidad que realizó la última actualización de este nodo.</span><span class="sxs-lookup"><span data-stu-id="42e71-182">ID of the principal that did the latest update of this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42e71-183">nodeUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="42e71-183">nodeUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="42e71-184">bigint, no NULL</span><span class="sxs-lookup"><span data-stu-id="42e71-184">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="42e71-185">Marca de tiempo de la última actualización de este nodo.</span><span class="sxs-lookup"><span data-stu-id="42e71-185">Time stamp of the latest update of this node.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42e71-186">purgedOn</span><span class="sxs-lookup"><span data-stu-id="42e71-186">purgedOn</span></span></p></td>
<td><p><span data-ttu-id="42e71-187">datetime</span><span class="sxs-lookup"><span data-stu-id="42e71-187">datetime</span></span></p></td>
<td><p><span data-ttu-id="42e71-188">Hora de la última operación de purga (la eliminación de ámbitos de la tabla tblScopedPrincipal y los roles de la tabla tblPrincipalRole) que afectaban a este nodo.</span><span class="sxs-lookup"><span data-stu-id="42e71-188">Time of the latest purge operation (removal of scopes from tblScopedPrincipal table and roles from tblPrincipalRole table) that affected this node.</span></span> <span data-ttu-id="42e71-189">Se usa en el mecanismo de actualización de caché interna del servicio de chat.</span><span class="sxs-lookup"><span data-stu-id="42e71-189">This is used by the Chat service’s internal cache update mechanism.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="42e71-190">Keys</span><span class="sxs-lookup"><span data-stu-id="42e71-190">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="42e71-191">Columna</span><span class="sxs-lookup"><span data-stu-id="42e71-191">Column</span></span></th>
<th><span data-ttu-id="42e71-192">Descripción</span><span class="sxs-lookup"><span data-stu-id="42e71-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="42e71-193">nodeID</span><span class="sxs-lookup"><span data-stu-id="42e71-193">nodeID</span></span></p></td>
<td><p><span data-ttu-id="42e71-194">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="42e71-194">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42e71-195">comportamiento</span><span class="sxs-lookup"><span data-stu-id="42e71-195">behavior</span></span></p></td>
<td><p><span data-ttu-id="42e71-196">Clave externa con búsqueda en la tabla tblEnumValue. valueID.</span><span class="sxs-lookup"><span data-stu-id="42e71-196">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42e71-197">visibility</span><span class="sxs-lookup"><span data-stu-id="42e71-197">visibility</span></span></p></td>
<td><p><span data-ttu-id="42e71-198">Clave externa con búsqueda en la tabla tblEnumValue. valueID.</span><span class="sxs-lookup"><span data-stu-id="42e71-198">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42e71-199">parentID</span><span class="sxs-lookup"><span data-stu-id="42e71-199">parentID</span></span></p></td>
<td><p><span data-ttu-id="42e71-200">Clave externa con búsqueda en la tabla tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="42e71-200">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42e71-201">siopID</span><span class="sxs-lookup"><span data-stu-id="42e71-201">siopID</span></span></p></td>
<td><p><span data-ttu-id="42e71-202">Clave externa con búsqueda en la tabla tblSiopWhiteList. siopId.</span><span class="sxs-lookup"><span data-stu-id="42e71-202">Foreign key with lookup in tblSiopWhiteList.siopId table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

