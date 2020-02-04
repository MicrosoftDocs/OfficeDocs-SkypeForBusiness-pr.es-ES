---
title: 'Lync Server 2013: tblPrincipalMeta'
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
ms.openlocfilehash: 848f4dc19ddf64c53c2dd30ae6ca4c8036b67c79
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764100"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalmeta-in-lync-server-2013"></a><span data-ttu-id="567de-102">tblPrincipalMeta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="567de-102">tblPrincipalMeta in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="567de-103">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="567de-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="567de-104">tblPrincipalMeta contiene las entidades de identidad que deben actualizarse desde los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="567de-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>

### <a name="columns"></a><span data-ttu-id="567de-105">Columnas</span><span class="sxs-lookup"><span data-stu-id="567de-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="567de-106">Columna</span><span class="sxs-lookup"><span data-stu-id="567de-106">Column</span></span></th>
<th><span data-ttu-id="567de-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="567de-107">Type</span></span></th>
<th><span data-ttu-id="567de-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="567de-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="567de-109">prinID</span><span class="sxs-lookup"><span data-stu-id="567de-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="567de-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="567de-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="567de-111">IDENTIFICADOR principal.</span><span class="sxs-lookup"><span data-stu-id="567de-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="567de-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="567de-112">prinAffiliationsDirty</span></span></p></td>
<td><p><span data-ttu-id="567de-113">bit, not null</span><span class="sxs-lookup"><span data-stu-id="567de-113">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="567de-114">True si es necesario actualizar las afiliaciones principales.</span><span class="sxs-lookup"><span data-stu-id="567de-114">True if principal affiliations have to be refreshed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="567de-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="567de-115">prinAttributesDirty</span></span></p></td>
<td><p><span data-ttu-id="567de-116">bit, not null</span><span class="sxs-lookup"><span data-stu-id="567de-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="567de-117">True si es necesario actualizar los atributos de principal.</span><span class="sxs-lookup"><span data-stu-id="567de-117">True if principal attributes have to be refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="567de-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="567de-118">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="567de-119">bit, not null</span><span class="sxs-lookup"><span data-stu-id="567de-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="567de-120">True si el principal se ha eliminado.</span><span class="sxs-lookup"><span data-stu-id="567de-120">True if the principal has been deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="567de-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="567de-121">tryCount</span></span></p></td>
<td><p><span data-ttu-id="567de-122">int</span><span class="sxs-lookup"><span data-stu-id="567de-122">int</span></span></p></td>
<td><p><span data-ttu-id="567de-123">Número de intentos de actualizar el principal de AD DS que se ha producido hasta el momento.</span><span class="sxs-lookup"><span data-stu-id="567de-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="567de-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="567de-124">lastTry</span></span></p></td>
<td><p><span data-ttu-id="567de-125">datetime</span><span class="sxs-lookup"><span data-stu-id="567de-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="567de-126">Marca de tiempo del último intento de actualizar la entidad de la identidad.</span><span class="sxs-lookup"><span data-stu-id="567de-126">Time stamp from the latest attempt to refresh the principal.</span></span> <span data-ttu-id="567de-127">Puede ser null si aún no se ha intentado ninguna actualización.</span><span class="sxs-lookup"><span data-stu-id="567de-127">Can be null if no refresh has been attempted yet.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="567de-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="567de-128">nextTry</span></span></p></td>
<td><p><span data-ttu-id="567de-129">datetime</span><span class="sxs-lookup"><span data-stu-id="567de-129">datetime</span></span></p></td>
<td><p><span data-ttu-id="567de-130">Marca de tiempo de la siguiente actualización programada.</span><span class="sxs-lookup"><span data-stu-id="567de-130">Time stamp for the next scheduled refresh.</span></span> <span data-ttu-id="567de-131">Puede ser null si no se ha programado ninguna actualización adicional.</span><span class="sxs-lookup"><span data-stu-id="567de-131">Can be null if no further refresh has been scheduled.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="567de-132">Sus</span><span class="sxs-lookup"><span data-stu-id="567de-132">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="567de-133">Columna</span><span class="sxs-lookup"><span data-stu-id="567de-133">Column</span></span></th>
<th><span data-ttu-id="567de-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="567de-134">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="567de-135">prinID</span><span class="sxs-lookup"><span data-stu-id="567de-135">prinID</span></span></p></td>
<td><p><span data-ttu-id="567de-136">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="567de-136">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="567de-137">prinID</span><span class="sxs-lookup"><span data-stu-id="567de-137">prinID</span></span></p></td>
<td><p><span data-ttu-id="567de-138">Clave externa con la búsqueda en la tabla tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="567de-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

