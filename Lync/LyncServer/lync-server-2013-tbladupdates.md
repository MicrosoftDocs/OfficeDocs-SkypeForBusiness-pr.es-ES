---
title: 'Lync Server 2013: tblADUpdates'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblADUpdates
ms:assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615033(v=OCS.15)
ms:contentKeyID: 48185227
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f171d8346442f915cd71fb48d51bba80bcfa32ca
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850511"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladupdates-in-lync-server-2013"></a><span data-ttu-id="d0035-102">tblADUpdates en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0035-102">tblADUpdates in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0035-103">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="d0035-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="d0035-104">tblADUpdates contiene cambios de servicios de dominio de Active Directory que aún no han sido procesados por los pasos más recientes de sincronización de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d0035-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="d0035-105">Columnas</span><span class="sxs-lookup"><span data-stu-id="d0035-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d0035-106">Columna</span><span class="sxs-lookup"><span data-stu-id="d0035-106">Column</span></span></th>
<th><span data-ttu-id="d0035-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="d0035-107">Type</span></span></th>
<th><span data-ttu-id="d0035-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="d0035-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d0035-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="d0035-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="d0035-110">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="d0035-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="d0035-111">GUID principal del objeto que cambió.</span><span class="sxs-lookup"><span data-stu-id="d0035-111">Principal GUID of the object that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0035-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="d0035-112">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="d0035-113">nvarchar (384), not null</span><span class="sxs-lookup"><span data-stu-id="d0035-113">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="d0035-114">Nombre distintivo del objeto.</span><span class="sxs-lookup"><span data-stu-id="d0035-114">Distinguished name of the object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0035-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="d0035-115">prinAttributesChanged</span></span></p></td>
<td><p><span data-ttu-id="d0035-116">bit, not null</span><span class="sxs-lookup"><span data-stu-id="d0035-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="d0035-117">True si ha cambiado al menos un atributo del objeto.</span><span class="sxs-lookup"><span data-stu-id="d0035-117">True if at least one attribute of the object changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0035-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="d0035-118">prinMembersChanged</span></span></p></td>
<td><p><span data-ttu-id="d0035-119">bit, not null</span><span class="sxs-lookup"><span data-stu-id="d0035-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="d0035-120">True si la pertenencia ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="d0035-120">True if the membership changed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0035-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="d0035-121">prinAffiliationsChanged</span></span></p></td>
<td><p><span data-ttu-id="d0035-122">bit, not null</span><span class="sxs-lookup"><span data-stu-id="d0035-122">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="d0035-123">No usado.</span><span class="sxs-lookup"><span data-stu-id="d0035-123">Not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0035-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="d0035-124">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="d0035-125">bit, not null</span><span class="sxs-lookup"><span data-stu-id="d0035-125">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="d0035-126">True si el objeto se ha eliminado.</span><span class="sxs-lookup"><span data-stu-id="d0035-126">True if the object was deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0035-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="d0035-127">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="d0035-128">DateTime, not null</span><span class="sxs-lookup"><span data-stu-id="d0035-128">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="d0035-129">Marca de tiempo del momento en que se insertó la fila.</span><span class="sxs-lookup"><span data-stu-id="d0035-129">Time stamp of when the row was inserted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

