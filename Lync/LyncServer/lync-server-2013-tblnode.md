---
title: 'Lync Server 2013: tblNode'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblNode
ms:assetid: a31d2961-aa83-4286-a12e-15d279c95f19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615024(v=OCS.15)
ms:contentKeyID: 48184960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84bf7cf57f9890093a56deb2e0769b82e92aa0ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850501"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblnode-in-lync-server-2013"></a><span data-ttu-id="85e63-102">tblNode en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85e63-102">tblNode in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85e63-103">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="85e63-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="85e63-104">tblNode contiene el árbol de objetos (con nodos de categoría o de salón de chat) tal como se administra en el panel de control y los cmdlets administrativos de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="85e63-104">tblNode contains the object tree (with category or chat room nodes) as managed in the Lync Server 2013 Control Panel and administrative cmdlets.</span></span>

### <a name="columns"></a><span data-ttu-id="85e63-105">Columnas</span><span class="sxs-lookup"><span data-stu-id="85e63-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="85e63-106">Columna</span><span class="sxs-lookup"><span data-stu-id="85e63-106">Column</span></span></th>
<th><span data-ttu-id="85e63-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="85e63-107">Type</span></span></th>
<th><span data-ttu-id="85e63-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="85e63-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="85e63-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="85e63-109">nodeID</span></span></p></td>
<td><p><span data-ttu-id="85e63-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="85e63-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="85e63-111">IDENTIFICADOR de nodo (número único).</span><span class="sxs-lookup"><span data-stu-id="85e63-111">Node ID (unique number).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85e63-112">nodeGuid</span><span class="sxs-lookup"><span data-stu-id="85e63-112">nodeGuid</span></span></p></td>
<td><p><span data-ttu-id="85e63-113">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="85e63-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="85e63-114">GUID de nodo.</span><span class="sxs-lookup"><span data-stu-id="85e63-114">Node GUID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85e63-115">parentID</span><span class="sxs-lookup"><span data-stu-id="85e63-115">parentID</span></span></p></td>
<td><p><span data-ttu-id="85e63-116">int</span><span class="sxs-lookup"><span data-stu-id="85e63-116">int</span></span></p></td>
<td><p><span data-ttu-id="85e63-117">IDENTIFICADOR de nodo del elemento primario.</span><span class="sxs-lookup"><span data-stu-id="85e63-117">Node ID of parent.</span></span> <span data-ttu-id="85e63-118">El nodo raíz (con identificador 1) también se incluye como principal.</span><span class="sxs-lookup"><span data-stu-id="85e63-118">The root node (with ID 1) includes itself as parent as well.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85e63-119">Nodo</span><span class="sxs-lookup"><span data-stu-id="85e63-119">nodeType</span></span></p></td>
<td><p><span data-ttu-id="85e63-120">bit, not null</span><span class="sxs-lookup"><span data-stu-id="85e63-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="85e63-121">True si el nodo es una categoría.</span><span class="sxs-lookup"><span data-stu-id="85e63-121">True if the node is a category.</span></span></p>
<p><span data-ttu-id="85e63-122">Falso si el nodo es un salón de chat.</span><span class="sxs-lookup"><span data-stu-id="85e63-122">False if the node is a chat room.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85e63-123">nombreDeNodo</span><span class="sxs-lookup"><span data-stu-id="85e63-123">nodeName</span></span></p></td>
<td><p><span data-ttu-id="85e63-124">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="85e63-124">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="85e63-125">Nombre del nodo.</span><span class="sxs-lookup"><span data-stu-id="85e63-125">Node name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85e63-126">nodeDesc</span><span class="sxs-lookup"><span data-stu-id="85e63-126">nodeDesc</span></span></p></td>
<td><p><span data-ttu-id="85e63-127">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="85e63-127">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="85e63-128">Descripción del nodo.</span><span class="sxs-lookup"><span data-stu-id="85e63-128">Node description.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85e63-129">recibir</span><span class="sxs-lookup"><span data-stu-id="85e63-129">invite</span></span></p></td>
<td><p><span data-ttu-id="85e63-130">bit</span><span class="sxs-lookup"><span data-stu-id="85e63-130">bit</span></span></p></td>
<td><p><span data-ttu-id="85e63-131">Para las categorías:</span><span class="sxs-lookup"><span data-stu-id="85e63-131">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="85e63-132">True si los invitados están activados.</span><span class="sxs-lookup"><span data-stu-id="85e63-132">True if invites are on.</span></span></p></li>
<li><p><span data-ttu-id="85e63-133">False si los invitados están deshabilitados.</span><span class="sxs-lookup"><span data-stu-id="85e63-133">False if invites are off.</span></span></p></li>
</ul>
<p><span data-ttu-id="85e63-134">Para salas:</span><span class="sxs-lookup"><span data-stu-id="85e63-134">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="85e63-135">False si los invitados están deshabilitados (reemplaza la categoría principal).</span><span class="sxs-lookup"><span data-stu-id="85e63-135">False if invites are off (overrides the parent category).</span></span></p></li>
<li><p><span data-ttu-id="85e63-136">NULL si la configuración de invitados se hereda de la categoría principal.</span><span class="sxs-lookup"><span data-stu-id="85e63-136">Null if the invites setting is inherited from the parent category.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85e63-137">conectarse</span><span class="sxs-lookup"><span data-stu-id="85e63-137">logged</span></span></p></td>
<td><p><span data-ttu-id="85e63-138">bit</span><span class="sxs-lookup"><span data-stu-id="85e63-138">bit</span></span></p></td>
<td><p><span data-ttu-id="85e63-139">Para las categorías:</span><span class="sxs-lookup"><span data-stu-id="85e63-139">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="85e63-140">True si el historial de chat está activado.</span><span class="sxs-lookup"><span data-stu-id="85e63-140">True if chat history is on.</span></span></p></li>
<li><p><span data-ttu-id="85e63-141">Falso si el historial de conversaciones está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="85e63-141">False if chat history is off.</span></span></p></li>
</ul>
<p><span data-ttu-id="85e63-142">Para salas:</span><span class="sxs-lookup"><span data-stu-id="85e63-142">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="85e63-143">Valor.</span><span class="sxs-lookup"><span data-stu-id="85e63-143">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85e63-144">filePost</span><span class="sxs-lookup"><span data-stu-id="85e63-144">filePost</span></span></p></td>
<td><p><span data-ttu-id="85e63-145">bit</span><span class="sxs-lookup"><span data-stu-id="85e63-145">bit</span></span></p></td>
<td><p><span data-ttu-id="85e63-146">Para las categorías:</span><span class="sxs-lookup"><span data-stu-id="85e63-146">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="85e63-147">True si se permiten las cargas de archivos.</span><span class="sxs-lookup"><span data-stu-id="85e63-147">True if file uploads are allowed.</span></span></p></li>
<li><p><span data-ttu-id="85e63-148">False si no se permiten las cargas de archivos.</span><span class="sxs-lookup"><span data-stu-id="85e63-148">False if file uploads are disallowed.</span></span></p></li>
</ul>
<p><span data-ttu-id="85e63-149">Para salas:</span><span class="sxs-lookup"><span data-stu-id="85e63-149">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="85e63-150">Valor.</span><span class="sxs-lookup"><span data-stu-id="85e63-150">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85e63-151">habilitar</span><span class="sxs-lookup"><span data-stu-id="85e63-151">disabled</span></span></p></td>
<td><p><span data-ttu-id="85e63-152">bit, not null</span><span class="sxs-lookup"><span data-stu-id="85e63-152">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="85e63-153">True si el salón de chat está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="85e63-153">True if the chat room is disabled.</span></span> <span data-ttu-id="85e63-154">Solo se aplica a salones de chat.</span><span class="sxs-lookup"><span data-stu-id="85e63-154">Applies only to chat rooms.</span></span> <span data-ttu-id="85e63-155">(Falso para categorías).</span><span class="sxs-lookup"><span data-stu-id="85e63-155">(False for categories.)</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85e63-156">problema</span><span class="sxs-lookup"><span data-stu-id="85e63-156">behavior</span></span></p></td>
<td><p><span data-ttu-id="85e63-157">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="85e63-157">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="85e63-158">Comportamiento (que se busca en la tabla EnumValue):</span><span class="sxs-lookup"><span data-stu-id="85e63-158">Behavior (looked up in EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="85e63-159">4: normal (salones de chat normales).</span><span class="sxs-lookup"><span data-stu-id="85e63-159">4: Normal (normal chat rooms).</span></span></p></li>
<li><p><span data-ttu-id="85e63-160">5: auditorio (salones de chat de Auditorio; solo los moderadores pueden contribuir).</span><span class="sxs-lookup"><span data-stu-id="85e63-160">5: Auditorium (auditorium chat rooms, only presenters can contribute).</span></span></p></li>
</ul>
<p><span data-ttu-id="85e63-161">Solo se aplica a salones de chat.</span><span class="sxs-lookup"><span data-stu-id="85e63-161">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85e63-162">visión</span><span class="sxs-lookup"><span data-stu-id="85e63-162">visibility</span></span></p></td>
<td><p><span data-ttu-id="85e63-163">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="85e63-163">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="85e63-164">Visibilidad (en la tabla EnumValue):</span><span class="sxs-lookup"><span data-stu-id="85e63-164">Visibility (looked up on EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="85e63-165">2: privado</span><span class="sxs-lookup"><span data-stu-id="85e63-165">2: Private</span></span></p></li>
<li><p><span data-ttu-id="85e63-166">3: ámbito</span><span class="sxs-lookup"><span data-stu-id="85e63-166">3: Scoped</span></span></p></li>
<li><p><span data-ttu-id="85e63-167">6: abrir</span><span class="sxs-lookup"><span data-stu-id="85e63-167">6: Open</span></span></p></li>
</ul>
<p><span data-ttu-id="85e63-168">Solo se aplica a salones de chat.</span><span class="sxs-lookup"><span data-stu-id="85e63-168">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85e63-169">siopID</span><span class="sxs-lookup"><span data-stu-id="85e63-169">siopID</span></span></p></td>
<td><p><span data-ttu-id="85e63-170">Identificador único global</span><span class="sxs-lookup"><span data-stu-id="85e63-170">GUID</span></span></p></td>
<td><p><span data-ttu-id="85e63-171">GUID de complemento si un complemento está asociado con este salón de chat.</span><span class="sxs-lookup"><span data-stu-id="85e63-171">Add-In GUID if an add-in is associated with this chat room.</span></span> <span data-ttu-id="85e63-172">(Las categorías no tienen complementos).</span><span class="sxs-lookup"><span data-stu-id="85e63-172">(Categories do not have add-ins.)</span></span></p>
<p><span data-ttu-id="85e63-173">La información del complemento se busca en la tabla SiopWhiteList.</span><span class="sxs-lookup"><span data-stu-id="85e63-173">The add-in information is looked up in SiopWhiteList table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85e63-174">nodeAddedBy</span><span class="sxs-lookup"><span data-stu-id="85e63-174">nodeAddedBy</span></span></p></td>
<td><p><span data-ttu-id="85e63-175">int, not null</span><span class="sxs-lookup"><span data-stu-id="85e63-175">int, not null</span></span></p></td>
<td><p><span data-ttu-id="85e63-176">IDENTIFICADOR de la entidad de identidad que creó este nodo.</span><span class="sxs-lookup"><span data-stu-id="85e63-176">ID of the principal that created this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85e63-177">nodeAddedOn</span><span class="sxs-lookup"><span data-stu-id="85e63-177">nodeAddedOn</span></span></p></td>
<td><p><span data-ttu-id="85e63-178">BIGINT, not null</span><span class="sxs-lookup"><span data-stu-id="85e63-178">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="85e63-179">Marca de tiempo de la creación del nodo.</span><span class="sxs-lookup"><span data-stu-id="85e63-179">Time stamp of the node creation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85e63-180">nodeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="85e63-180">nodeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="85e63-181">int, not null</span><span class="sxs-lookup"><span data-stu-id="85e63-181">int, not null</span></span></p></td>
<td><p><span data-ttu-id="85e63-182">IDENTIFICADOR de la entidad de identidad que realizó la última actualización de este nodo.</span><span class="sxs-lookup"><span data-stu-id="85e63-182">ID of the principal that did the latest update of this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85e63-183">nodeUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="85e63-183">nodeUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="85e63-184">BIGINT, not null</span><span class="sxs-lookup"><span data-stu-id="85e63-184">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="85e63-185">Marca de tiempo de la última actualización de este nodo.</span><span class="sxs-lookup"><span data-stu-id="85e63-185">Time stamp of the latest update of this node.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85e63-186">purgedOn</span><span class="sxs-lookup"><span data-stu-id="85e63-186">purgedOn</span></span></p></td>
<td><p><span data-ttu-id="85e63-187">datetime</span><span class="sxs-lookup"><span data-stu-id="85e63-187">datetime</span></span></p></td>
<td><p><span data-ttu-id="85e63-188">Hora de la última operación de purga (eliminación de ámbitos de la tabla tblScopedPrincipal y roles de la tabla tblPrincipalRole) que afectó a este nodo.</span><span class="sxs-lookup"><span data-stu-id="85e63-188">Time of the latest purge operation (removal of scopes from tblScopedPrincipal table and roles from tblPrincipalRole table) that affected this node.</span></span> <span data-ttu-id="85e63-189">Lo usa el mecanismo de actualización de la caché interna del servicio de chat.</span><span class="sxs-lookup"><span data-stu-id="85e63-189">This is used by the Chat service’s internal cache update mechanism.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="85e63-190">Sus</span><span class="sxs-lookup"><span data-stu-id="85e63-190">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="85e63-191">Columna</span><span class="sxs-lookup"><span data-stu-id="85e63-191">Column</span></span></th>
<th><span data-ttu-id="85e63-192">Descripción</span><span class="sxs-lookup"><span data-stu-id="85e63-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="85e63-193">nodeID</span><span class="sxs-lookup"><span data-stu-id="85e63-193">nodeID</span></span></p></td>
<td><p><span data-ttu-id="85e63-194">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="85e63-194">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85e63-195">problema</span><span class="sxs-lookup"><span data-stu-id="85e63-195">behavior</span></span></p></td>
<td><p><span data-ttu-id="85e63-196">Clave externa con la búsqueda en la tabla tblEnumValue. valueID.</span><span class="sxs-lookup"><span data-stu-id="85e63-196">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85e63-197">visión</span><span class="sxs-lookup"><span data-stu-id="85e63-197">visibility</span></span></p></td>
<td><p><span data-ttu-id="85e63-198">Clave externa con la búsqueda en la tabla tblEnumValue. valueID.</span><span class="sxs-lookup"><span data-stu-id="85e63-198">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85e63-199">parentID</span><span class="sxs-lookup"><span data-stu-id="85e63-199">parentID</span></span></p></td>
<td><p><span data-ttu-id="85e63-200">Clave externa con la búsqueda en la tabla tblNode. nodeID.</span><span class="sxs-lookup"><span data-stu-id="85e63-200">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85e63-201">siopID</span><span class="sxs-lookup"><span data-stu-id="85e63-201">siopID</span></span></p></td>
<td><p><span data-ttu-id="85e63-202">Clave externa con la búsqueda en la tabla tblSiopWhiteList. siopId.</span><span class="sxs-lookup"><span data-stu-id="85e63-202">Foreign key with lookup in tblSiopWhiteList.siopId table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

