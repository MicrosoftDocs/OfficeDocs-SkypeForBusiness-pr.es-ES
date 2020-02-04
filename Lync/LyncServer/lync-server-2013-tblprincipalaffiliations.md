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
ms.openlocfilehash: 3976b98fddc96ad08f3de4413bf8f38ec3525496
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764156"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalaffiliations-in-lync-server-2013"></a><span data-ttu-id="01129-102">tblPrincipalAffiliations en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01129-102">tblPrincipalAffiliations in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01129-103">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="01129-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="01129-104">tblPrincipalAffiliations contiene las afiliaciones principales que describen las pertenencias en ubicaciones, incluidos los grupos de seguridad de los servicios de dominio de Active Directory, en contenedores de Active Directory, en dominios.</span><span class="sxs-lookup"><span data-stu-id="01129-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>

### <a name="columns"></a><span data-ttu-id="01129-105">Columnas</span><span class="sxs-lookup"><span data-stu-id="01129-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="01129-106">Columna</span><span class="sxs-lookup"><span data-stu-id="01129-106">Column</span></span></th>
<th><span data-ttu-id="01129-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="01129-107">Type</span></span></th>
<th><span data-ttu-id="01129-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="01129-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="01129-109">principalID</span><span class="sxs-lookup"><span data-stu-id="01129-109">principalID</span></span></p></td>
<td><p><span data-ttu-id="01129-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="01129-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="01129-111">IDENTIFICADOR de la entidad de identidad afiliada.</span><span class="sxs-lookup"><span data-stu-id="01129-111">ID of the affiliated principal.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01129-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="01129-112">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="01129-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="01129-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="01129-114">IDENTIFICADOR de la identidad que representa la afiliación.</span><span class="sxs-lookup"><span data-stu-id="01129-114">ID of the principal representing the affiliation.</span></span> <span data-ttu-id="01129-115">Cada principal (excepto los tipos de usuario del sistema) tiene también una afiliación propia.</span><span class="sxs-lookup"><span data-stu-id="01129-115">Each principal (except system-user-types) has a self-affiliation as well.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01129-116">clasificación</span><span class="sxs-lookup"><span data-stu-id="01129-116">index</span></span></p></td>
<td><p><span data-ttu-id="01129-117">int, not null</span><span class="sxs-lookup"><span data-stu-id="01129-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="01129-118">Clasificación.</span><span class="sxs-lookup"><span data-stu-id="01129-118">Index.</span></span> <span data-ttu-id="01129-119">El valor de las afiliaciones automáticas es de-1 y para las otras afiliaciones que aumenta secuencialmente de 1 en cada &lt;PrincipalID, affiliationId&gt; bucket.</span><span class="sxs-lookup"><span data-stu-id="01129-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each &lt;principalID, affiliationId&gt; bucket.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01129-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="01129-120">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="01129-121">int, not null</span><span class="sxs-lookup"><span data-stu-id="01129-121">int, not null</span></span></p></td>
<td><p><span data-ttu-id="01129-122">Principal que realizó la actualización más reciente.</span><span class="sxs-lookup"><span data-stu-id="01129-122">Principal that did the latest update.</span></span> <span data-ttu-id="01129-123">Esto suele ser 1, que significa sincronización de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="01129-123">This is usually 1, which means Active Directory Sync.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="01129-124">Sus</span><span class="sxs-lookup"><span data-stu-id="01129-124">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="01129-125">Columnas</span><span class="sxs-lookup"><span data-stu-id="01129-125">Columns</span></span></th>
<th><span data-ttu-id="01129-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="01129-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="01129-127">&lt;principalID, Indice, affiliationID&gt;</span><span class="sxs-lookup"><span data-stu-id="01129-127">&lt;principalID, index, affiliationID&gt;</span></span></p></td>
<td><p><span data-ttu-id="01129-128">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="01129-128">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01129-129">principalID</span><span class="sxs-lookup"><span data-stu-id="01129-129">principalID</span></span></p></td>
<td><p><span data-ttu-id="01129-130">Clave externa con la búsqueda en la tabla tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="01129-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01129-131">affiliationID</span><span class="sxs-lookup"><span data-stu-id="01129-131">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="01129-132">Clave externa con la búsqueda en la tabla tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="01129-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

