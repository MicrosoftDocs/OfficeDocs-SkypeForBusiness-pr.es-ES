---
title: 'Lync Server 2013: tblPrincipalAffiliations'
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
ms.openlocfilehash: 2900a2ca780cfc239cb7045ea564bbba581f2f55
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142036"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipalaffiliations-in-lync-server-2013"></a><span data-ttu-id="f4b47-102">tblPrincipalAffiliations en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4b47-102">tblPrincipalAffiliations in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4b47-103">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="f4b47-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="f4b47-104">tblPrincipalAffiliations contiene las afiliaciones principales que describen las pertenencias en ubicaciones, incluidos los grupos de seguridad de servicios de dominio de Active Directory, en contenedores de Active Directory, en dominios.</span><span class="sxs-lookup"><span data-stu-id="f4b47-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>

### <a name="columns"></a><span data-ttu-id="f4b47-105">Columns</span><span class="sxs-lookup"><span data-stu-id="f4b47-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f4b47-106">Columna</span><span class="sxs-lookup"><span data-stu-id="f4b47-106">Column</span></span></th>
<th><span data-ttu-id="f4b47-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="f4b47-107">Type</span></span></th>
<th><span data-ttu-id="f4b47-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="f4b47-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f4b47-109">principalID</span><span class="sxs-lookup"><span data-stu-id="f4b47-109">principalID</span></span></p></td>
<td><p><span data-ttu-id="f4b47-110">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="f4b47-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="f4b47-111">Id. de la entidad de seguridad afiliada.</span><span class="sxs-lookup"><span data-stu-id="f4b47-111">ID of the affiliated principal.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4b47-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="f4b47-112">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="f4b47-113">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="f4b47-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="f4b47-p101">Id. de la entidad de seguridad que representa la afiliación. Todas las entidades de seguridad (excepto system-user-types) tienen también una afiliación propia.</span><span class="sxs-lookup"><span data-stu-id="f4b47-p101">ID of the principal representing the affiliation. Each principal (except system-user-types) has a self-affiliation as well.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4b47-116">index</span><span class="sxs-lookup"><span data-stu-id="f4b47-116">index</span></span></p></td>
<td><p><span data-ttu-id="f4b47-117">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="f4b47-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="f4b47-118">TopIndex.</span><span class="sxs-lookup"><span data-stu-id="f4b47-118">Index.</span></span> <span data-ttu-id="f4b47-119">El valor de Self-Afiliation es-1 y para las otras afiliaciones que aumenta secuencialmente de 1 en cada &lt;PrincipalID, affiliationId&gt; bucket.</span><span class="sxs-lookup"><span data-stu-id="f4b47-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each &lt;principalID, affiliationId&gt; bucket.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4b47-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="f4b47-120">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="f4b47-121">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="f4b47-121">int, not null</span></span></p></td>
<td><p><span data-ttu-id="f4b47-p103">Entidad de seguridad que realizó la actualización más reciente. Suele ser 1, lo que significa sincronización de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f4b47-p103">Principal that did the latest update. This is usually 1, which means Active Directory Sync.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="f4b47-124">Keys</span><span class="sxs-lookup"><span data-stu-id="f4b47-124">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f4b47-125">Columns</span><span class="sxs-lookup"><span data-stu-id="f4b47-125">Columns</span></span></th>
<th><span data-ttu-id="f4b47-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="f4b47-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f4b47-127">&lt;principalID, index, affiliationID&gt;</span><span class="sxs-lookup"><span data-stu-id="f4b47-127">&lt;principalID, index, affiliationID&gt;</span></span></p></td>
<td><p><span data-ttu-id="f4b47-128">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="f4b47-128">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4b47-129">principalID</span><span class="sxs-lookup"><span data-stu-id="f4b47-129">principalID</span></span></p></td>
<td><p><span data-ttu-id="f4b47-130">Clave externa con búsqueda en la tabla tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="f4b47-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4b47-131">affiliationID</span><span class="sxs-lookup"><span data-stu-id="f4b47-131">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="f4b47-132">Clave externa con búsqueda en la tabla tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="f4b47-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

