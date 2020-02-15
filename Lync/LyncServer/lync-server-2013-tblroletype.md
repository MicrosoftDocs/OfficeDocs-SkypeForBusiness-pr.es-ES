---
title: 'Lync Server 2013: tblRoleType'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblRoleType
ms:assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558623(v=OCS.15)
ms:contentKeyID: 48183577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab96d6cd090ebaaa9e33ddf1672ab704ee371f8b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046153"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblroletype-in-lync-server-2013"></a><span data-ttu-id="50b4e-102">tblRoleType en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50b4e-102">tblRoleType in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50b4e-103">_**Última modificación del tema:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="50b4e-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="50b4e-104">tblRoleType es una tabla de búsqueda estática con tipos de rol y sus conjuntos de permisos asociados.</span><span class="sxs-lookup"><span data-stu-id="50b4e-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>

### <a name="columns"></a><span data-ttu-id="50b4e-105">Columns</span><span class="sxs-lookup"><span data-stu-id="50b4e-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="50b4e-106">Columna</span><span class="sxs-lookup"><span data-stu-id="50b4e-106">Column</span></span></th>
<th><span data-ttu-id="50b4e-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="50b4e-107">Type</span></span></th>
<th><span data-ttu-id="50b4e-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="50b4e-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="50b4e-109">Prinid</span><span class="sxs-lookup"><span data-stu-id="50b4e-109">rtypeID</span></span></p></td>
<td><p><span data-ttu-id="50b4e-110">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="50b4e-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="50b4e-111">Identificador del tipo de rol.</span><span class="sxs-lookup"><span data-stu-id="50b4e-111">Role type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50b4e-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="50b4e-112">rtypeDesc</span></span></p></td>
<td><p><span data-ttu-id="50b4e-113">nvarchar (256), no NULL</span><span class="sxs-lookup"><span data-stu-id="50b4e-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="50b4e-p101">Descripción del tipo de rol. Existen cuatro roles disponibles:</span><span class="sxs-lookup"><span data-stu-id="50b4e-p101">Role type description. There are four available roles:</span></span></p>
<ul>
<li><p><span data-ttu-id="50b4e-116">Miembro: miembro de salón de chat</span><span class="sxs-lookup"><span data-stu-id="50b4e-116">Member: Chat room member</span></span></p></li>
<li><p><span data-ttu-id="50b4e-117">Administrador: administrador de salón de chat</span><span class="sxs-lookup"><span data-stu-id="50b4e-117">Manager: Chat room manager</span></span></p></li>
<li><p><span data-ttu-id="50b4e-118">Miembro con voz: moderador de un salón de chat de tipo auditorio</span><span class="sxs-lookup"><span data-stu-id="50b4e-118">Voiced: Presenter for an auditorium chat room</span></span></p></li>
<li><p><span data-ttu-id="50b4e-119">Creador: puede crear salones de chat</span><span class="sxs-lookup"><span data-stu-id="50b4e-119">Creator: Can create chat rooms</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50b4e-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="50b4e-120">rtypeAllowedPermSet</span></span></p></td>
<td><p><span data-ttu-id="50b4e-121">bigint, no NULL</span><span class="sxs-lookup"><span data-stu-id="50b4e-121">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="50b4e-p102">Conjunto de permisos del rol. Los valores usados son:</span><span class="sxs-lookup"><span data-stu-id="50b4e-p102">Permission set for the role. The used bits are:</span></span></p>
<ul>
<li><p><span data-ttu-id="50b4e-124">2: True si el rol puede administrar nodos.</span><span class="sxs-lookup"><span data-stu-id="50b4e-124">2: True if the role can manage nodes.</span></span></p></li>
<li><p><span data-ttu-id="50b4e-125">4: True si el rol puede crear nodos secundarios.</span><span class="sxs-lookup"><span data-stu-id="50b4e-125">4: True if the role can create children nodes.</span></span></p></li>
<li><p><span data-ttu-id="50b4e-126">7: True si el rol puede unirse a un salón de chat (o salones de chat secundarios de una categoría).</span><span class="sxs-lookup"><span data-stu-id="50b4e-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span></p></li>
<li><p><span data-ttu-id="50b4e-127">8: True si el rol puede hablar en un salón de chat (o salones de chat secundarios de una categoría).</span><span class="sxs-lookup"><span data-stu-id="50b4e-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span></p></li>
<li><p><span data-ttu-id="50b4e-128">10: True si el rol puede leer el historial de chat incluso cuando no se unió a un salón de chat.</span><span class="sxs-lookup"><span data-stu-id="50b4e-128">10: True if the role can read chat history even when not joined to a chat room.</span></span></p></li>
<li><p><span data-ttu-id="50b4e-p103">11: True si el rol puede ver el salón de chat. (Restricción adicional según factores, como ámbito y visibilidad).</span><span class="sxs-lookup"><span data-stu-id="50b4e-p103">11: True if the role can see the chat room. (This is further refined by factors such as scope and visibility.)</span></span></p></li>
<li><p><span data-ttu-id="50b4e-131">12: True si el rol puede hablar en un salón de chat de tipo auditorio.</span><span class="sxs-lookup"><span data-stu-id="50b4e-131">12: True if the role can chat in an auditorium chat room.</span></span></p></li>
<li><p><span data-ttu-id="50b4e-132">13: True si el rol puede omitir las reglas de visibilidad al ver nodos.</span><span class="sxs-lookup"><span data-stu-id="50b4e-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="50b4e-133">Key </span><span class="sxs-lookup"><span data-stu-id="50b4e-133">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="50b4e-134">Columna</span><span class="sxs-lookup"><span data-stu-id="50b4e-134">Column</span></span></th>
<th><span data-ttu-id="50b4e-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="50b4e-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="50b4e-136">Prinid</span><span class="sxs-lookup"><span data-stu-id="50b4e-136">rtypeID</span></span></p></td>
<td><p><span data-ttu-id="50b4e-137">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="50b4e-137">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

