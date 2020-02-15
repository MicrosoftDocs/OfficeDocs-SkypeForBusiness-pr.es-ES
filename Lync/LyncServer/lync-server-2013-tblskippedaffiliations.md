---
title: 'Lync Server 2013: tblSkippedAffiliations'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblSkippedAffiliations
ms:assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558611(v=OCS.15)
ms:contentKeyID: 48183373
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c61c2744c6a2cdf8b857161d3476885992c4d74e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42024721"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblskippedaffiliations-in-lync-server-2013"></a><span data-ttu-id="ee5ce-102">tblSkippedAffiliations en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee5ce-102">tblSkippedAffiliations in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee5ce-103">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="ee5ce-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="ee5ce-104">tblSkippedAffiliations contiene las afiliaciones que no se pudieron leer (normalmente debido a errores de acceso a los servicios de dominio de Active Directory).</span><span class="sxs-lookup"><span data-stu-id="ee5ce-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>

### <a name="columns"></a><span data-ttu-id="ee5ce-105">Columns</span><span class="sxs-lookup"><span data-stu-id="ee5ce-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ee5ce-106">Columna</span><span class="sxs-lookup"><span data-stu-id="ee5ce-106">Column</span></span></th>
<th><span data-ttu-id="ee5ce-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="ee5ce-107">Type</span></span></th>
<th><span data-ttu-id="ee5ce-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="ee5ce-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ee5ce-109">prinID</span><span class="sxs-lookup"><span data-stu-id="ee5ce-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="ee5ce-110">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="ee5ce-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="ee5ce-111">Id. de la entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ee5ce-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee5ce-112">affDescription</span><span class="sxs-lookup"><span data-stu-id="ee5ce-112">affDescription</span></span></p></td>
<td><p><span data-ttu-id="ee5ce-113">nvarchar (256), no NULL</span><span class="sxs-lookup"><span data-stu-id="ee5ce-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="ee5ce-114">Cadena que identifica la afiliación.</span><span class="sxs-lookup"><span data-stu-id="ee5ce-114">A string identifying the affiliation.</span></span></p>
<p><span data-ttu-id="ee5ce-115">El formato es: GUID: {0} URI: {1} &gt; ID:{2}</span><span class="sxs-lookup"><span data-stu-id="ee5ce-115">The format is: guid: {0} uri: {1}&gt; id: {2}</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee5ce-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="ee5ce-116">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="ee5ce-117">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="ee5ce-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="ee5ce-p101">Identificador de la entidad de seguridad que actualizó esta fila. Siempre es 1 (usuario del sistema) porque la sincronización de Active Directory es el único origen de estas entradas.</span><span class="sxs-lookup"><span data-stu-id="ee5ce-p101">ID of the principal that updated this row. It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="ee5ce-120">Keys</span><span class="sxs-lookup"><span data-stu-id="ee5ce-120">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ee5ce-121">Columna (s)</span><span class="sxs-lookup"><span data-stu-id="ee5ce-121">Column(s)</span></span></th>
<th><span data-ttu-id="ee5ce-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="ee5ce-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ee5ce-123">&lt;prinID, affDescription&gt;</span><span class="sxs-lookup"><span data-stu-id="ee5ce-123">&lt;prinID, affDescription&gt;</span></span></p></td>
<td><p><span data-ttu-id="ee5ce-124">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="ee5ce-124">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee5ce-125">prinID</span><span class="sxs-lookup"><span data-stu-id="ee5ce-125">prinID</span></span></p></td>
<td><p><span data-ttu-id="ee5ce-126">Clave externa con búsqueda en la tabla tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="ee5ce-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

