---
title: 'Lync Server 2013: tblPrincipalMeta'
description: 'Lync Server 2013: tblPrincipalMeta.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalMeta
ms:assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615009(v=OCS.15)
ms:contentKeyID: 48184648
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 899fd1e450dac52afa56c1ee1de86da82b2db309
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573646"
---
# <a name="tblprincipalmeta-in-lync-server-2013"></a><span data-ttu-id="99449-103">tblPrincipalMeta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99449-103">tblPrincipalMeta in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99449-104">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="99449-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="99449-105">tblPrincipalMeta contiene las entidades de identidad que se deben actualizar desde los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="99449-105">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>

### <a name="columns"></a><span data-ttu-id="99449-106">Columnas</span><span class="sxs-lookup"><span data-stu-id="99449-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="99449-107">Columna</span><span class="sxs-lookup"><span data-stu-id="99449-107">Column</span></span></th>
<th><span data-ttu-id="99449-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="99449-108">Type</span></span></th>
<th><span data-ttu-id="99449-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="99449-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="99449-110">prinID</span><span class="sxs-lookup"><span data-stu-id="99449-110">prinID</span></span></p></td>
<td><p><span data-ttu-id="99449-111">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="99449-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="99449-112">Identificador de la entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="99449-112">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99449-113">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="99449-113">prinAffiliationsDirty</span></span></p></td>
<td><p><span data-ttu-id="99449-114">bit, no NULL</span><span class="sxs-lookup"><span data-stu-id="99449-114">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="99449-115">True si hay que actualizar las afiliaciones de la entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="99449-115">True if principal affiliations have to be refreshed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99449-116">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="99449-116">prinAttributesDirty</span></span></p></td>
<td><p><span data-ttu-id="99449-117">bit, no NULL</span><span class="sxs-lookup"><span data-stu-id="99449-117">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="99449-118">True si hay que actualizar los atributos de la entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="99449-118">True if principal attributes have to be refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99449-119">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="99449-119">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="99449-120">bit, no NULL</span><span class="sxs-lookup"><span data-stu-id="99449-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="99449-121">True si la entidad de seguridad se ha eliminado.</span><span class="sxs-lookup"><span data-stu-id="99449-121">True if the principal has been deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99449-122">tryCount</span><span class="sxs-lookup"><span data-stu-id="99449-122">tryCount</span></span></p></td>
<td><p><span data-ttu-id="99449-123">entero</span><span class="sxs-lookup"><span data-stu-id="99449-123">int</span></span></p></td>
<td><p><span data-ttu-id="99449-124">Número de intentos realizados hasta la fecha para actualizar la entidad de seguridad de AD DS.</span><span class="sxs-lookup"><span data-stu-id="99449-124">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99449-125">lastTry</span><span class="sxs-lookup"><span data-stu-id="99449-125">lastTry</span></span></p></td>
<td><p><span data-ttu-id="99449-126">datetime</span><span class="sxs-lookup"><span data-stu-id="99449-126">datetime</span></span></p></td>
<td><p><span data-ttu-id="99449-p101">Marca de tiempo del último intento por actualizar la entidad de seguridad. Puede ser null si aún no se ha realizado ninguna actualización.</span><span class="sxs-lookup"><span data-stu-id="99449-p101">Time stamp from the latest attempt to refresh the principal. Can be null if no refresh has been attempted yet.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99449-129">nextTry</span><span class="sxs-lookup"><span data-stu-id="99449-129">nextTry</span></span></p></td>
<td><p><span data-ttu-id="99449-130">datetime</span><span class="sxs-lookup"><span data-stu-id="99449-130">datetime</span></span></p></td>
<td><p><span data-ttu-id="99449-p102">Marca de tiempo de la siguiente actualización programada. Puede ser NULL si no se han programado más actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="99449-p102">Time stamp for the next scheduled refresh. Can be null if no further refresh has been scheduled.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="99449-133">Keys</span><span class="sxs-lookup"><span data-stu-id="99449-133">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="99449-134">Columna</span><span class="sxs-lookup"><span data-stu-id="99449-134">Column</span></span></th>
<th><span data-ttu-id="99449-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="99449-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="99449-136">prinID</span><span class="sxs-lookup"><span data-stu-id="99449-136">prinID</span></span></p></td>
<td><p><span data-ttu-id="99449-137">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="99449-137">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99449-138">prinID</span><span class="sxs-lookup"><span data-stu-id="99449-138">prinID</span></span></p></td>
<td><p><span data-ttu-id="99449-139">Clave externa con búsqueda en la tabla tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="99449-139">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

