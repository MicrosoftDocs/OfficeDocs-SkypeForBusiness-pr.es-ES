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
ms.openlocfilehash: cee7c67421ae12d08e52bee1b013dfa6280472f3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142066"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblnode-in-lync-server-2013"></a><span data-ttu-id="0e3ac-102">tblNode en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e3ac-102">tblNode in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e3ac-103">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="0e3ac-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="0e3ac-104">tblNode contiene el árbol de objetos (con nodos de categoría o de salón de chat) tal como se administra en el panel de control de Lync Server 2013 y en los cmdlets administrativos.</span><span class="sxs-lookup"><span data-stu-id="0e3ac-104">tblNode contains the object tree (with category or chat room nodes) as managed in the Lync Server 2013 Control Panel and administrative cmdlets.</span></span>

### <a name="columns"></a><span data-ttu-id="0e3ac-105">Columns</span><span class="sxs-lookup"><span data-stu-id="0e3ac-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0e3ac-106">Columna</span><span class="sxs-lookup"><span data-stu-id="0e3ac-106">Column</span></span></th>
<th><span data-ttu-id="0e3ac-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="0e3ac-107">Type</span></span></th>
<th><span data-ttu-id="0e3ac-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="0e3ac-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0e3ac-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="0e3ac-109">nodeID</span></span></p></td>
<td><p><span data-ttu-id="0e3ac-110">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="0e3ac-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="0e3ac-111">IDENTIFICADOR de nodo (número único).</span><span class="sxs-lookup"><span data-stu-id="0e3ac-111">Node ID (unique number).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e3ac-112">nodeGuid</span><span class="sxs-lookup"><span data-stu-id="0e3ac-112">nodeGuid</span></span></p></td>
<td><p><span data-ttu-id="0e3ac-113">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="0e3ac-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="0e3ac-114">GUID de nodo.</span><span class="sxs-lookup"><span data-stu-id="0e3ac-114">Node GUID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e3ac-115">parentID</span><span class="sxs-lookup"><span data-stu-id="0e3ac-115">parentID</span></span></p></td>
<td><p><span data-ttu-id="0e3ac-116">int</span><span class="sxs-lookup"><span data-stu-id="0e3ac-116">int</span></span></p></td>
<td><p><span data-ttu-id="0e3ac-117">IDENTIFICADOR de nodo de primario.</span><span class="sxs-lookup"><span data-stu-id="0e3ac-117">Node ID of parent.</span></span> <span data-ttu-id="0e3ac-118">El nodo raíz (con identificador 1) también se incluye como primario.</span><span class="sxs-lookup"><span data-stu-id="0e3ac-118">The root node (with ID 1) includes itself as parent as well.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e3ac-119">nodeType</span><span class="sxs-lookup"><span data-stu-id="0e3ac-119">nodeType</span></span></p></td>
<td><p><span data-ttu-id="0e3ac-120">bit, not null</span><span class="sxs-lookup"><span data-stu-id="0e3ac-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="0e3ac-121">True si el nodo es una categoría.</span><span class="sxs-lookup"><span data-stu-id="0e3ac-121">True if the node is a category.</span></span></p>
<p><span data-ttu-id="0e3ac-122">False si el nodo es un salón de chat.</span><span class="sxs-lookup"><span data-stu-id="0e3ac-122">False if the node is a chat room.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e3ac-123">nodeName</span><span class="sxs-lookup"><span data-stu-id="0e3ac-123">nodeName</span></span></p></td>
<td><p><span data-ttu-id="0e3ac-124">nvarchar (256), no NULL</span><span class="sxs-lookup"><span data-stu-id="0e3ac-124">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="0e3ac-125">Nombre del nodo.</span><span class="sxs-lookup"><span data-stu-id="0e3ac-125">Node name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e3ac-126">nodeDesc</span><span class="sxs-lookup"><span data-stu-id="0e3ac-126">nodeDesc</span></span></p></td>
<td><p><span data-ttu-id="0e3ac-127">nvarchar (256), no NULL</span><span class="sxs-lookup"><span data-stu-id="0e3ac-127">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="0e3ac-128">Descripción del nodo.</span><span class="sxs-lookup"><span data-stu-id="0e3ac-128">Node description.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e3ac-129">invitar</span><span class="sxs-lookup"><span data-stu-id="0e3ac-129">invite</span></span></p></td>
<td><p><span data-ttu-id="0e3ac-130">bit</span><span class="sxs-lookup"><span data-stu-id="0e3ac-130">bit</span></span></p></td>
<td><p><span data-ttu-id="0e3ac-131">Para categorías:</span><span class="sxs-lookup"><span data-stu-id="0e3ac-131">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="0e3ac-132">True si se activan las invitaciones.</span><span class="sxs-lookup"><span data-stu-id="0e3ac-132">True if invites are on.</span></span></p></li>
<li><p><span data-ttu-id="0e3ac-133">False si los invitados están desactivados.</span><span class="sxs-lookup"><span data-stu-id="0e3ac-133">False if invites are off.</span></span></p></li>
</ul>
<p><span data-ttu-id="0e3ac-134">Para los salones:</span><span class="sxs-lookup"><span data-stu-id="0e3ac-134">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="0e3ac-135">False si los invitados están desactivados (invalida la categoría principal).</span><span class="sxs-lookup"><span data-stu-id="0e3ac-135">False if invites are off (overrides the parent category).</span></span></p></li>
<li><p><span data-ttu-id="0e3ac-136">NULL si la configuración de invitaciones se ha heredado de la categoría principal.</span><span class="sxs-lookup"><span data-stu-id="0e3ac-136">Null if the invites setting is inherited from the parent category.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e3ac-137">iniciado sesión</span><span class="sxs-lookup"><span data-stu-id="0e3ac-137">logged</span></span></p></td>
<td><p><span data-ttu-id="0e3ac-138">bit</span><span class="sxs-lookup"><span data-stu-id="0e3ac-138">bit</span></span></p></td>
<td><p><span data-ttu-id="0e3ac-139">Para categorías:</span><span class="sxs-lookup"><span data-stu-id="0e3ac-139">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="0e3ac-140">True si el historial de chat está activado.</span><span class="sxs-lookup"><span data-stu-id="0e3ac-140">True if chat history is on.</span></span></p></li>
<li><p><span data-ttu-id="0e3ac-141">False si el historial de chat está desactivado.</span><span class="sxs-lookup"><span data-stu-id="0e3ac-141">False if chat history is off.</span></span></p></li>
</ul>
<p><span data-ttu-id="0e3ac-142">Para los salones:</span><span class="sxs-lookup"><span data-stu-id="0e3ac-142">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="0e3ac-143">Que.</span><span class="sxs-lookup"><span data-stu-id="0e3ac-143">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e3ac-144">filePost</span><span class="sxs-lookup"><span data-stu-id="0e3ac-144">filePost</span></span></p></td>
<td><p><span data-ttu-id="0e3ac-145">bit</span><span class="sxs-lookup"><span data-stu-id="0e3ac-145">bit</span></span></p></td>
<td><p><span data-ttu-id="0e3ac-146">Para categorías:</span><span class="sxs-lookup"><span data-stu-id="0e3ac-146">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="0e3ac-147">True si se permiten las cargas de archivos.</span><span class="sxs-lookup"><span data-stu-id="0e3ac-147">True if file uploads are allowed.</span></span></p></li>
<li><p><span data-ttu-id="0e3ac-148">False si no se permiten las cargas de archivos.</span><span class="sxs-lookup"><span data-stu-id="0e3ac-148">False if file uploads are disallowed.</span></span></p></li>
</ul>
<p><span data-ttu-id="0e3ac-149">Para los salones:</span><span class="sxs-lookup"><span data-stu-id="0e3ac-149">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="0e3ac-150">Que.</span><span class="sxs-lookup"><span data-stu-id="0e3ac-150">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e3ac-151">capacidad</span><span class="sxs-lookup"><span data-stu-id="0e3ac-151">disabled</span></span></p></td>
<td><p><span data-ttu-id="0e3ac-152">bit, not null</span><span class="sxs-lookup"><span data-stu-id="0e3ac-152">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="0e3ac-153">True si el salón de chat está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="0e3ac-153">True if the chat room is disabled.</span></span> <span data-ttu-id="0e3ac-154">Solo se aplica a salones de chat.</span><span class="sxs-lookup"><span data-stu-id="0e3ac-154">Applies only to chat rooms.</span></span> <span data-ttu-id="0e3ac-155">(False para las categorías.)</span><span class="sxs-lookup"><span data-stu-id="0e3ac-155">(False for categories.)</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e3ac-156">comportamiento</span><span class="sxs-lookup"><span data-stu-id="0e3ac-156">behavior</span></span></p></td>
<td><p><span data-ttu-id="0e3ac-157">smallint, no NULL</span><span class="sxs-lookup"><span data-stu-id="0e3ac-157">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="0e3ac-158">Comportamiento (buscar en la tabla EnumValue):</span><span class="sxs-lookup"><span data-stu-id="0e3ac-158">Behavior (looked up in EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="0e3ac-159">4: normal (salones de chat normales).</span><span class="sxs-lookup"><span data-stu-id="0e3ac-159">4: Normal (normal chat rooms).</span></span></p></li>
<li><p><span data-ttu-id="0e3ac-160">5: auditorio (los salones de chat de auditorio, solo los moderadores pueden contribuir).</span><span class="sxs-lookup"><span data-stu-id="0e3ac-160">5: Auditorium (auditorium chat rooms, only presenters can contribute).</span></span></p></li>
</ul>
<p><span data-ttu-id="0e3ac-161">Solo se aplica a salones de chat.</span><span class="sxs-lookup"><span data-stu-id="0e3ac-161">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e3ac-162">visibility</span><span class="sxs-lookup"><span data-stu-id="0e3ac-162">visibility</span></span></p></td>
<td><p><span data-ttu-id="0e3ac-163">smallint, no NULL</span><span class="sxs-lookup"><span data-stu-id="0e3ac-163">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="0e3ac-164">Visibilidad (buscar en la tabla EnumValue):</span><span class="sxs-lookup"><span data-stu-id="0e3ac-164">Visibility (looked up on EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="0e3ac-165">2: privado</span><span class="sxs-lookup"><span data-stu-id="0e3ac-165">2: Private</span></span></p></li>
<li><p><span data-ttu-id="0e3ac-166">3: con ámbito</span><span class="sxs-lookup"><span data-stu-id="0e3ac-166">3: Scoped</span></span></p></li>
<li><p><span data-ttu-id="0e3ac-167">6: abrir</span><span class="sxs-lookup"><span data-stu-id="0e3ac-167">6: Open</span></span></p></li>
</ul>
<p><span data-ttu-id="0e3ac-168">Solo se aplica a salones de chat.</span><span class="sxs-lookup"><span data-stu-id="0e3ac-168">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e3ac-169">siopID</span><span class="sxs-lookup"><span data-stu-id="0e3ac-169">siopID</span></span></p></td>
<td><p><span data-ttu-id="0e3ac-170">GUID</span><span class="sxs-lookup"><span data-stu-id="0e3ac-170">GUID</span></span></p></td>
<td><p><span data-ttu-id="0e3ac-171">GUID de complemento si un complemento está asociado con este salón de chat.</span><span class="sxs-lookup"><span data-stu-id="0e3ac-171">Add-In GUID if an add-in is associated with this chat room.</span></span> <span data-ttu-id="0e3ac-172">(Las categorías no tienen complementos).</span><span class="sxs-lookup"><span data-stu-id="0e3ac-172">(Categories do not have add-ins.)</span></span></p>
<p><span data-ttu-id="0e3ac-173">La información del complemento se busca en la tabla SiopWhiteList.</span><span class="sxs-lookup"><span data-stu-id="0e3ac-173">The add-in information is looked up in SiopWhiteList table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e3ac-174">nodeAddedBy</span><span class="sxs-lookup"><span data-stu-id="0e3ac-174">nodeAddedBy</span></span></p></td>
<td><p><span data-ttu-id="0e3ac-175">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="0e3ac-175">int, not null</span></span></p></td>
<td><p><span data-ttu-id="0e3ac-176">IDENTIFICADOR de la entidad de identidad que creó este nodo.</span><span class="sxs-lookup"><span data-stu-id="0e3ac-176">ID of the principal that created this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e3ac-177">nodeAddedOn</span><span class="sxs-lookup"><span data-stu-id="0e3ac-177">nodeAddedOn</span></span></p></td>
<td><p><span data-ttu-id="0e3ac-178">bigint, no NULL</span><span class="sxs-lookup"><span data-stu-id="0e3ac-178">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="0e3ac-179">Marca de tiempo de la creación del nodo.</span><span class="sxs-lookup"><span data-stu-id="0e3ac-179">Time stamp of the node creation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e3ac-180">nodeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="0e3ac-180">nodeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="0e3ac-181">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="0e3ac-181">int, not null</span></span></p></td>
<td><p><span data-ttu-id="0e3ac-182">IDENTIFICADOR de la entidad de identidad que realizó la última actualización de este nodo.</span><span class="sxs-lookup"><span data-stu-id="0e3ac-182">ID of the principal that did the latest update of this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e3ac-183">nodeUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="0e3ac-183">nodeUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="0e3ac-184">bigint, no NULL</span><span class="sxs-lookup"><span data-stu-id="0e3ac-184">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="0e3ac-185">Marca de tiempo de la última actualización de este nodo.</span><span class="sxs-lookup"><span data-stu-id="0e3ac-185">Time stamp of the latest update of this node.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e3ac-186">purgedOn</span><span class="sxs-lookup"><span data-stu-id="0e3ac-186">purgedOn</span></span></p></td>
<td><p><span data-ttu-id="0e3ac-187">datetime</span><span class="sxs-lookup"><span data-stu-id="0e3ac-187">datetime</span></span></p></td>
<td><p><span data-ttu-id="0e3ac-188">Hora de la última operación de purga (la eliminación de ámbitos de la tabla tblScopedPrincipal y los roles de la tabla tblPrincipalRole) que afectaban a este nodo.</span><span class="sxs-lookup"><span data-stu-id="0e3ac-188">Time of the latest purge operation (removal of scopes from tblScopedPrincipal table and roles from tblPrincipalRole table) that affected this node.</span></span> <span data-ttu-id="0e3ac-189">Se usa en el mecanismo de actualización de caché interna del servicio de chat.</span><span class="sxs-lookup"><span data-stu-id="0e3ac-189">This is used by the Chat service’s internal cache update mechanism.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="0e3ac-190">Keys</span><span class="sxs-lookup"><span data-stu-id="0e3ac-190">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0e3ac-191">Columna</span><span class="sxs-lookup"><span data-stu-id="0e3ac-191">Column</span></span></th>
<th><span data-ttu-id="0e3ac-192">Descripción</span><span class="sxs-lookup"><span data-stu-id="0e3ac-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0e3ac-193">nodeID</span><span class="sxs-lookup"><span data-stu-id="0e3ac-193">nodeID</span></span></p></td>
<td><p><span data-ttu-id="0e3ac-194">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="0e3ac-194">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e3ac-195">comportamiento</span><span class="sxs-lookup"><span data-stu-id="0e3ac-195">behavior</span></span></p></td>
<td><p><span data-ttu-id="0e3ac-196">Clave externa con búsqueda en la tabla tblEnumValue. valueID.</span><span class="sxs-lookup"><span data-stu-id="0e3ac-196">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e3ac-197">visibility</span><span class="sxs-lookup"><span data-stu-id="0e3ac-197">visibility</span></span></p></td>
<td><p><span data-ttu-id="0e3ac-198">Clave externa con búsqueda en la tabla tblEnumValue. valueID.</span><span class="sxs-lookup"><span data-stu-id="0e3ac-198">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e3ac-199">parentID</span><span class="sxs-lookup"><span data-stu-id="0e3ac-199">parentID</span></span></p></td>
<td><p><span data-ttu-id="0e3ac-200">Clave externa con búsqueda en la tabla tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="0e3ac-200">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e3ac-201">siopID</span><span class="sxs-lookup"><span data-stu-id="0e3ac-201">siopID</span></span></p></td>
<td><p><span data-ttu-id="0e3ac-202">Clave externa con búsqueda en la tabla tblSiopWhiteList. siopId.</span><span class="sxs-lookup"><span data-stu-id="0e3ac-202">Foreign key with lookup in tblSiopWhiteList.siopId table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

