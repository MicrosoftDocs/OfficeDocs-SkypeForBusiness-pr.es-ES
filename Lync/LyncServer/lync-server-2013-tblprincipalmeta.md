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
ms.openlocfilehash: 04ad0fbdb9a4e3bb2e5962089fe1c30f960bdc91
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195223"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipalmeta-in-lync-server-2013"></a><span data-ttu-id="39529-102">tblPrincipalMeta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39529-102">tblPrincipalMeta in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39529-103">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="39529-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="39529-104">tblPrincipalMeta contiene las entidades de identidad que se deben actualizar desde los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="39529-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>

### <a name="columns"></a><span data-ttu-id="39529-105">Columns</span><span class="sxs-lookup"><span data-stu-id="39529-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="39529-106">Columna</span><span class="sxs-lookup"><span data-stu-id="39529-106">Column</span></span></th>
<th><span data-ttu-id="39529-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="39529-107">Type</span></span></th>
<th><span data-ttu-id="39529-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="39529-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="39529-109">prinID</span><span class="sxs-lookup"><span data-stu-id="39529-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="39529-110">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="39529-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="39529-111">Identificador de la entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="39529-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39529-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="39529-112">prinAffiliationsDirty</span></span></p></td>
<td><p><span data-ttu-id="39529-113">bit, not null</span><span class="sxs-lookup"><span data-stu-id="39529-113">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="39529-114">True si hay que actualizar las afiliaciones de la entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="39529-114">True if principal affiliations have to be refreshed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39529-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="39529-115">prinAttributesDirty</span></span></p></td>
<td><p><span data-ttu-id="39529-116">bit, not null</span><span class="sxs-lookup"><span data-stu-id="39529-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="39529-117">True si hay que actualizar los atributos de la entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="39529-117">True if principal attributes have to be refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39529-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="39529-118">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="39529-119">bit, no NULL</span><span class="sxs-lookup"><span data-stu-id="39529-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="39529-120">True si la entidad de seguridad se ha eliminado.</span><span class="sxs-lookup"><span data-stu-id="39529-120">True if the principal has been deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39529-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="39529-121">tryCount</span></span></p></td>
<td><p><span data-ttu-id="39529-122">int</span><span class="sxs-lookup"><span data-stu-id="39529-122">int</span></span></p></td>
<td><p><span data-ttu-id="39529-123">Número de intentos realizados hasta la fecha para actualizar la entidad de seguridad de AD DS.</span><span class="sxs-lookup"><span data-stu-id="39529-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39529-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="39529-124">lastTry</span></span></p></td>
<td><p><span data-ttu-id="39529-125">datetime</span><span class="sxs-lookup"><span data-stu-id="39529-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="39529-p101">Marca de tiempo del último intento por actualizar la entidad de seguridad. Puede ser null si aún no se ha realizado ninguna actualización.</span><span class="sxs-lookup"><span data-stu-id="39529-p101">Time stamp from the latest attempt to refresh the principal. Can be null if no refresh has been attempted yet.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39529-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="39529-128">nextTry</span></span></p></td>
<td><p><span data-ttu-id="39529-129">datetime</span><span class="sxs-lookup"><span data-stu-id="39529-129">datetime</span></span></p></td>
<td><p><span data-ttu-id="39529-p102">Marca de tiempo de la siguiente actualización programada. Puede ser NULL si no se han programado más actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="39529-p102">Time stamp for the next scheduled refresh. Can be null if no further refresh has been scheduled.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="39529-132">Keys</span><span class="sxs-lookup"><span data-stu-id="39529-132">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="39529-133">Columna</span><span class="sxs-lookup"><span data-stu-id="39529-133">Column</span></span></th>
<th><span data-ttu-id="39529-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="39529-134">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="39529-135">prinID</span><span class="sxs-lookup"><span data-stu-id="39529-135">prinID</span></span></p></td>
<td><p><span data-ttu-id="39529-136">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="39529-136">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39529-137">prinID</span><span class="sxs-lookup"><span data-stu-id="39529-137">prinID</span></span></p></td>
<td><p><span data-ttu-id="39529-138">Clave externa con búsqueda en la tabla tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="39529-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

