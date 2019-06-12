---
title: 'Lync Server 2013: tblRoleType'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblRoleType
ms:assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558623(v=OCS.15)
ms:contentKeyID: 48183577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 698d6b07d5662a403a7485d009a39a0a8beccc73
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850472"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblroletype-in-lync-server-2013"></a><span data-ttu-id="82491-102">tblRoleType en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82491-102">tblRoleType in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82491-103">_**Última modificación del tema:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="82491-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="82491-104">tblRoleType es una tabla de búsqueda estática con tipos de roles y sus conjuntos de permisos asociados.</span><span class="sxs-lookup"><span data-stu-id="82491-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>

### <a name="columns"></a><span data-ttu-id="82491-105">Columnas</span><span class="sxs-lookup"><span data-stu-id="82491-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="82491-106">Columna</span><span class="sxs-lookup"><span data-stu-id="82491-106">Column</span></span></th>
<th><span data-ttu-id="82491-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="82491-107">Type</span></span></th>
<th><span data-ttu-id="82491-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="82491-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="82491-109">rtypeID</span><span class="sxs-lookup"><span data-stu-id="82491-109">rtypeID</span></span></p></td>
<td><p><span data-ttu-id="82491-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="82491-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="82491-111">IDENTIFICADOR de tipo de rol.</span><span class="sxs-lookup"><span data-stu-id="82491-111">Role type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82491-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="82491-112">rtypeDesc</span></span></p></td>
<td><p><span data-ttu-id="82491-113">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="82491-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="82491-114">Descripción de tipo de rol.</span><span class="sxs-lookup"><span data-stu-id="82491-114">Role type description.</span></span> <span data-ttu-id="82491-115">Hay cuatro roles disponibles:</span><span class="sxs-lookup"><span data-stu-id="82491-115">There are four available roles:</span></span></p>
<ul>
<li><p><span data-ttu-id="82491-116">Miembro: miembro del salón de chat</span><span class="sxs-lookup"><span data-stu-id="82491-116">Member: Chat room member</span></span></p></li>
<li><p><span data-ttu-id="82491-117">Administrador: administrador del salón de chat</span><span class="sxs-lookup"><span data-stu-id="82491-117">Manager: Chat room manager</span></span></p></li>
<li><p><span data-ttu-id="82491-118">Voz: moderador de un salón de chat de Auditorio</span><span class="sxs-lookup"><span data-stu-id="82491-118">Voiced: Presenter for an auditorium chat room</span></span></p></li>
<li><p><span data-ttu-id="82491-119">Creador: puede crear salones de chat</span><span class="sxs-lookup"><span data-stu-id="82491-119">Creator: Can create chat rooms</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82491-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="82491-120">rtypeAllowedPermSet</span></span></p></td>
<td><p><span data-ttu-id="82491-121">BIGINT, not null</span><span class="sxs-lookup"><span data-stu-id="82491-121">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="82491-122">Conjunto de permisos para el rol.</span><span class="sxs-lookup"><span data-stu-id="82491-122">Permission set for the role.</span></span> <span data-ttu-id="82491-123">Los bits utilizados son:</span><span class="sxs-lookup"><span data-stu-id="82491-123">The used bits are:</span></span></p>
<ul>
<li><p><span data-ttu-id="82491-124">2: verdadero si el rol puede administrar nodos.</span><span class="sxs-lookup"><span data-stu-id="82491-124">2: True if the role can manage nodes.</span></span></p></li>
<li><p><span data-ttu-id="82491-125">4: true si el rol puede crear nodos secundarios.</span><span class="sxs-lookup"><span data-stu-id="82491-125">4: True if the role can create children nodes.</span></span></p></li>
<li><p><span data-ttu-id="82491-126">7: verdadero si el rol puede unirse a un salón de chat (o a salones de chat de niños de una categoría).</span><span class="sxs-lookup"><span data-stu-id="82491-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span></p></li>
<li><p><span data-ttu-id="82491-127">8: verdadero si el rol puede chatear en un salón de chat (o en los salones de chat de los niños de una categoría).</span><span class="sxs-lookup"><span data-stu-id="82491-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span></p></li>
<li><p><span data-ttu-id="82491-128">10: verdadero si el rol puede leer el historial de chats incluso cuando no está unido a un salón de chat.</span><span class="sxs-lookup"><span data-stu-id="82491-128">10: True if the role can read chat history even when not joined to a chat room.</span></span></p></li>
<li><p><span data-ttu-id="82491-129">11: verdadero si el rol puede ver el salón de chat.</span><span class="sxs-lookup"><span data-stu-id="82491-129">11: True if the role can see the chat room.</span></span> <span data-ttu-id="82491-130">(Esto se ha refinado con factores como el alcance y la visibilidad).</span><span class="sxs-lookup"><span data-stu-id="82491-130">(This is further refined by factors such as scope and visibility.)</span></span></p></li>
<li><p><span data-ttu-id="82491-131">12: verdadero si el rol puede chatear en un salón de chat de Auditorio.</span><span class="sxs-lookup"><span data-stu-id="82491-131">12: True if the role can chat in an auditorium chat room.</span></span></p></li>
<li><p><span data-ttu-id="82491-132">13: verdadero si el rol puede omitir las reglas de visibilidad al ver los nodos.</span><span class="sxs-lookup"><span data-stu-id="82491-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="82491-133">Clave</span><span class="sxs-lookup"><span data-stu-id="82491-133">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="82491-134">Columna</span><span class="sxs-lookup"><span data-stu-id="82491-134">Column</span></span></th>
<th><span data-ttu-id="82491-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="82491-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="82491-136">rtypeID</span><span class="sxs-lookup"><span data-stu-id="82491-136">rtypeID</span></span></p></td>
<td><p><span data-ttu-id="82491-137">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="82491-137">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

