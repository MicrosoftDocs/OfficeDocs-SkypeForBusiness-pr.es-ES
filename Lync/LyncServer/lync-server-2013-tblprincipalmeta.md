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
ms.openlocfilehash: 5a1b4161a04b3107e3aff7b55ab82840ac6680e6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141996"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipalmeta-in-lync-server-2013"></a><span data-ttu-id="d1a2f-102">tblPrincipalMeta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1a2f-102">tblPrincipalMeta in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1a2f-103">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="d1a2f-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="d1a2f-104">tblPrincipalMeta contiene las entidades de identidad que se deben actualizar desde los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d1a2f-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>

### <a name="columns"></a><span data-ttu-id="d1a2f-105">Columns</span><span class="sxs-lookup"><span data-stu-id="d1a2f-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1a2f-106">Columna</span><span class="sxs-lookup"><span data-stu-id="d1a2f-106">Column</span></span></th>
<th><span data-ttu-id="d1a2f-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="d1a2f-107">Type</span></span></th>
<th><span data-ttu-id="d1a2f-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="d1a2f-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1a2f-109">prinID</span><span class="sxs-lookup"><span data-stu-id="d1a2f-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="d1a2f-110">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="d1a2f-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="d1a2f-111">Identificador de la entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="d1a2f-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1a2f-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="d1a2f-112">prinAffiliationsDirty</span></span></p></td>
<td><p><span data-ttu-id="d1a2f-113">bit, not null</span><span class="sxs-lookup"><span data-stu-id="d1a2f-113">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="d1a2f-114">True si hay que actualizar las afiliaciones de la entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="d1a2f-114">True if principal affiliations have to be refreshed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1a2f-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="d1a2f-115">prinAttributesDirty</span></span></p></td>
<td><p><span data-ttu-id="d1a2f-116">bit, not null</span><span class="sxs-lookup"><span data-stu-id="d1a2f-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="d1a2f-117">True si hay que actualizar los atributos de la entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="d1a2f-117">True if principal attributes have to be refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1a2f-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="d1a2f-118">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="d1a2f-119">bit, no NULL</span><span class="sxs-lookup"><span data-stu-id="d1a2f-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="d1a2f-120">True si la entidad de seguridad se ha eliminado.</span><span class="sxs-lookup"><span data-stu-id="d1a2f-120">True if the principal has been deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1a2f-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="d1a2f-121">tryCount</span></span></p></td>
<td><p><span data-ttu-id="d1a2f-122">int</span><span class="sxs-lookup"><span data-stu-id="d1a2f-122">int</span></span></p></td>
<td><p><span data-ttu-id="d1a2f-123">Número de intentos realizados hasta la fecha para actualizar la entidad de seguridad de AD DS.</span><span class="sxs-lookup"><span data-stu-id="d1a2f-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1a2f-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="d1a2f-124">lastTry</span></span></p></td>
<td><p><span data-ttu-id="d1a2f-125">datetime</span><span class="sxs-lookup"><span data-stu-id="d1a2f-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="d1a2f-p101">Marca de tiempo del último intento por actualizar la entidad de seguridad. Puede ser null si aún no se ha realizado ninguna actualización.</span><span class="sxs-lookup"><span data-stu-id="d1a2f-p101">Time stamp from the latest attempt to refresh the principal. Can be null if no refresh has been attempted yet.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1a2f-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="d1a2f-128">nextTry</span></span></p></td>
<td><p><span data-ttu-id="d1a2f-129">datetime</span><span class="sxs-lookup"><span data-stu-id="d1a2f-129">datetime</span></span></p></td>
<td><p><span data-ttu-id="d1a2f-p102">Marca de tiempo de la siguiente actualización programada. Puede ser NULL si no se han programado más actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="d1a2f-p102">Time stamp for the next scheduled refresh. Can be null if no further refresh has been scheduled.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="d1a2f-132">Keys</span><span class="sxs-lookup"><span data-stu-id="d1a2f-132">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1a2f-133">Columna</span><span class="sxs-lookup"><span data-stu-id="d1a2f-133">Column</span></span></th>
<th><span data-ttu-id="d1a2f-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="d1a2f-134">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1a2f-135">prinID</span><span class="sxs-lookup"><span data-stu-id="d1a2f-135">prinID</span></span></p></td>
<td><p><span data-ttu-id="d1a2f-136">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="d1a2f-136">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1a2f-137">prinID</span><span class="sxs-lookup"><span data-stu-id="d1a2f-137">prinID</span></span></p></td>
<td><p><span data-ttu-id="d1a2f-138">Clave externa con búsqueda en la tabla tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="d1a2f-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

