---
title: 'Lync Server 2013: tblPrincipalAffiliations'
description: 'Lync Server 2013: tblPrincipalAffiliations.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalAffiliations
ms:assetid: 45fd8484-5837-44d2-85bb-45c83546607c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558642(v=OCS.15)
ms:contentKeyID: 48183993
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01c373147a58300e64f22e60e989a777c59b2653
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547486"
---
# <a name="tblprincipalaffiliations-in-lync-server-2013"></a><span data-ttu-id="36425-103">tblPrincipalAffiliations en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36425-103">tblPrincipalAffiliations in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36425-104">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="36425-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="36425-105">tblPrincipalAffiliations contiene las afiliaciones principales que describen las pertenencias en ubicaciones, incluidos los grupos de seguridad de servicios de dominio de Active Directory, en contenedores de Active Directory, en dominios.</span><span class="sxs-lookup"><span data-stu-id="36425-105">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>

### <a name="columns"></a><span data-ttu-id="36425-106">Columnas</span><span class="sxs-lookup"><span data-stu-id="36425-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="36425-107">Columna</span><span class="sxs-lookup"><span data-stu-id="36425-107">Column</span></span></th>
<th><span data-ttu-id="36425-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="36425-108">Type</span></span></th>
<th><span data-ttu-id="36425-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="36425-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="36425-110">principalID</span><span class="sxs-lookup"><span data-stu-id="36425-110">principalID</span></span></p></td>
<td><p><span data-ttu-id="36425-111">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="36425-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="36425-112">Id. de la entidad de seguridad afiliada.</span><span class="sxs-lookup"><span data-stu-id="36425-112">ID of the affiliated principal.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36425-113">affiliationID</span><span class="sxs-lookup"><span data-stu-id="36425-113">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="36425-114">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="36425-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="36425-p101">Id. de la entidad de seguridad que representa la afiliación. Todas las entidades de seguridad (excepto system-user-types) tienen también una afiliación propia.</span><span class="sxs-lookup"><span data-stu-id="36425-p101">ID of the principal representing the affiliation. Each principal (except system-user-types) has a self-affiliation as well.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36425-117">index</span><span class="sxs-lookup"><span data-stu-id="36425-117">index</span></span></p></td>
<td><p><span data-ttu-id="36425-118">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="36425-118">int, not null</span></span></p></td>
<td><p><span data-ttu-id="36425-119">TopIndex.</span><span class="sxs-lookup"><span data-stu-id="36425-119">Index.</span></span> <span data-ttu-id="36425-120">El valor de Self-Afiliation es-1 y para las otras afiliaciones que aumenta secuencialmente de 1 en cada &lt; principalID, affiliationId &gt; bucket.</span><span class="sxs-lookup"><span data-stu-id="36425-120">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each &lt;principalID, affiliationId&gt; bucket.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36425-121">updatedBy</span><span class="sxs-lookup"><span data-stu-id="36425-121">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="36425-122">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="36425-122">int, not null</span></span></p></td>
<td><p><span data-ttu-id="36425-p103">Entidad de seguridad que realizó la actualización más reciente. Suele ser 1, lo que significa sincronización de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="36425-p103">Principal that did the latest update. This is usually 1, which means Active Directory Sync.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="36425-125">Keys</span><span class="sxs-lookup"><span data-stu-id="36425-125">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="36425-126">Columnas</span><span class="sxs-lookup"><span data-stu-id="36425-126">Columns</span></span></th>
<th><span data-ttu-id="36425-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="36425-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="36425-128">&lt;principalID, index, affiliationID&gt;</span><span class="sxs-lookup"><span data-stu-id="36425-128">&lt;principalID, index, affiliationID&gt;</span></span></p></td>
<td><p><span data-ttu-id="36425-129">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="36425-129">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36425-130">principalID</span><span class="sxs-lookup"><span data-stu-id="36425-130">principalID</span></span></p></td>
<td><p><span data-ttu-id="36425-131">Clave externa con búsqueda en la tabla tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="36425-131">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36425-132">affiliationID</span><span class="sxs-lookup"><span data-stu-id="36425-132">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="36425-133">Clave externa con búsqueda en la tabla tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="36425-133">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

