---
title: 'Lync Server 2013: tblPreference'
description: 'Lync Server 2013: tblPreference.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPreference
ms:assetid: f94eb128-f782-42ff-a568-ed3529573bc8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615052(v=OCS.15)
ms:contentKeyID: 48185913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86e8b81a6af93e9bf1d7673e54492579a1bed08e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547516"
---
# <a name="tblpreference-in-lync-server-2013"></a><span data-ttu-id="31174-103">tblPreference en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31174-103">tblPreference in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31174-104">_**Última modificación del tema:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="31174-104">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="31174-105">tblPreference contiene las preferencias de cliente de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="31174-105">tblPreference contains the users’ client preferences.</span></span> <span data-ttu-id="31174-106">Esto suele ser usado por los clientes anteriores a Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="31174-106">This is generally used by clients previous to Lync 2013.</span></span>

### <a name="columns"></a><span data-ttu-id="31174-107">Columnas</span><span class="sxs-lookup"><span data-stu-id="31174-107">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="31174-108">Columna</span><span class="sxs-lookup"><span data-stu-id="31174-108">Column</span></span></th>
<th><span data-ttu-id="31174-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="31174-109">Type</span></span></th>
<th><span data-ttu-id="31174-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="31174-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="31174-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="31174-111">prefLabel</span></span></p></td>
<td><p><span data-ttu-id="31174-112">nvarchar (255), no NULL</span><span class="sxs-lookup"><span data-stu-id="31174-112">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="31174-113">Etiqueta con un formato como: &lt; URI del SIP del usuario &gt; | nombre de usuario. &lt; conjunto de preferencias &gt; .</span><span class="sxs-lookup"><span data-stu-id="31174-113">Label with a format such as: &lt;user sip uri&gt;|username.&lt;preference set&gt;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31174-114">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="31174-114">prefSeqID</span></span></p></td>
<td><p><span data-ttu-id="31174-115">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="31174-115">int, not null</span></span></p></td>
<td><p><span data-ttu-id="31174-116">Número secuencial (por etiqueta) para el control de versiones.</span><span class="sxs-lookup"><span data-stu-id="31174-116">A sequential number (per label) for versioning purposes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31174-117">prefContent</span><span class="sxs-lookup"><span data-stu-id="31174-117">prefContent</span></span></p></td>
<td><p><span data-ttu-id="31174-118">nvarchar (máx.)</span><span class="sxs-lookup"><span data-stu-id="31174-118">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="31174-119">Contenido codificado.</span><span class="sxs-lookup"><span data-stu-id="31174-119">Encoded content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31174-120">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="31174-120">lastModifiedBy</span></span></p></td>
<td><p><span data-ttu-id="31174-121">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="31174-121">int, not null</span></span></p></td>
<td><p><span data-ttu-id="31174-122">Identificador de la entidad de seguridad que ha actualizado la preferencia.</span><span class="sxs-lookup"><span data-stu-id="31174-122">ID of the principal that updated the preference.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="31174-123">Key </span><span class="sxs-lookup"><span data-stu-id="31174-123">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="31174-124">Columna</span><span class="sxs-lookup"><span data-stu-id="31174-124">Column</span></span></th>
<th><span data-ttu-id="31174-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="31174-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="31174-126">&lt;prefLabel, prefSeqID&gt;</span><span class="sxs-lookup"><span data-stu-id="31174-126">&lt;prefLabel, prefSeqID&gt;</span></span></p></td>
<td><p><span data-ttu-id="31174-127">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="31174-127">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

