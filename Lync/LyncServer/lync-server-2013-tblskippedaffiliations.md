---
title: 'Lync Server 2013: tblSkippedAffiliations'
description: 'Lync Server 2013: tblSkippedAffiliations.'
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
ms.openlocfilehash: 31746cee7302d34a1d19b3059ca1da6beab9345d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563806"
---
# <a name="tblskippedaffiliations-in-lync-server-2013"></a><span data-ttu-id="7ac62-103">tblSkippedAffiliations en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ac62-103">tblSkippedAffiliations in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ac62-104">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="7ac62-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="7ac62-105">tblSkippedAffiliations contiene las afiliaciones que no se pudieron leer (normalmente debido a errores de acceso a los servicios de dominio de Active Directory).</span><span class="sxs-lookup"><span data-stu-id="7ac62-105">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>

### <a name="columns"></a><span data-ttu-id="7ac62-106">Columnas</span><span class="sxs-lookup"><span data-stu-id="7ac62-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7ac62-107">Columna</span><span class="sxs-lookup"><span data-stu-id="7ac62-107">Column</span></span></th>
<th><span data-ttu-id="7ac62-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="7ac62-108">Type</span></span></th>
<th><span data-ttu-id="7ac62-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="7ac62-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7ac62-110">prinID</span><span class="sxs-lookup"><span data-stu-id="7ac62-110">prinID</span></span></p></td>
<td><p><span data-ttu-id="7ac62-111">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="7ac62-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="7ac62-112">Id. de la entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="7ac62-112">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ac62-113">affDescription</span><span class="sxs-lookup"><span data-stu-id="7ac62-113">affDescription</span></span></p></td>
<td><p><span data-ttu-id="7ac62-114">nvarchar (256), no NULL</span><span class="sxs-lookup"><span data-stu-id="7ac62-114">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="7ac62-115">Cadena que identifica la afiliación.</span><span class="sxs-lookup"><span data-stu-id="7ac62-115">A string identifying the affiliation.</span></span></p>
<p><span data-ttu-id="7ac62-116">El formato es: GUID: {0} URI: {1} &gt; ID:{2}</span><span class="sxs-lookup"><span data-stu-id="7ac62-116">The format is: guid: {0} uri: {1}&gt; id: {2}</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ac62-117">updatedBy</span><span class="sxs-lookup"><span data-stu-id="7ac62-117">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="7ac62-118">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="7ac62-118">int, not null</span></span></p></td>
<td><p><span data-ttu-id="7ac62-p101">Identificador de la entidad de seguridad que actualizó esta fila. Siempre es 1 (usuario del sistema) porque la sincronización de Active Directory es el único origen de estas entradas.</span><span class="sxs-lookup"><span data-stu-id="7ac62-p101">ID of the principal that updated this row. It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="7ac62-121">Keys</span><span class="sxs-lookup"><span data-stu-id="7ac62-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7ac62-122">Columna (s)</span><span class="sxs-lookup"><span data-stu-id="7ac62-122">Column(s)</span></span></th>
<th><span data-ttu-id="7ac62-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="7ac62-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7ac62-124">&lt;prinID, affDescription&gt;</span><span class="sxs-lookup"><span data-stu-id="7ac62-124">&lt;prinID, affDescription&gt;</span></span></p></td>
<td><p><span data-ttu-id="7ac62-125">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="7ac62-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ac62-126">prinID</span><span class="sxs-lookup"><span data-stu-id="7ac62-126">prinID</span></span></p></td>
<td><p><span data-ttu-id="7ac62-127">Clave externa con búsqueda en la tabla tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="7ac62-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

