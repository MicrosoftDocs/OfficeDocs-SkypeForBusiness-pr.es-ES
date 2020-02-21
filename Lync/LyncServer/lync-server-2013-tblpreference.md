---
title: 'Lync Server 2013: tblPreference'
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
ms.openlocfilehash: 6d1405634ad92b3f2cde2d085875648d738d6200
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214548"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblpreference-in-lync-server-2013"></a><span data-ttu-id="6d4b3-102">tblPreference en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d4b3-102">tblPreference in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d4b3-103">_**Última modificación del tema:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="6d4b3-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="6d4b3-104">tblPreference contiene las preferencias de cliente de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="6d4b3-104">tblPreference contains the users’ client preferences.</span></span> <span data-ttu-id="6d4b3-105">Esto suele ser usado por los clientes anteriores a Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="6d4b3-105">This is generally used by clients previous to Lync 2013.</span></span>

### <a name="columns"></a><span data-ttu-id="6d4b3-106">Columns</span><span class="sxs-lookup"><span data-stu-id="6d4b3-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6d4b3-107">Columna</span><span class="sxs-lookup"><span data-stu-id="6d4b3-107">Column</span></span></th>
<th><span data-ttu-id="6d4b3-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="6d4b3-108">Type</span></span></th>
<th><span data-ttu-id="6d4b3-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="6d4b3-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6d4b3-110">prefLabel</span><span class="sxs-lookup"><span data-stu-id="6d4b3-110">prefLabel</span></span></p></td>
<td><p><span data-ttu-id="6d4b3-111">nvarchar (255), no NULL</span><span class="sxs-lookup"><span data-stu-id="6d4b3-111">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="6d4b3-112">Etiqueta con un formato como: &lt;URI&gt;del SIP del usuario | nombre de usuario. &lt;conjunto&gt;de preferencias.</span><span class="sxs-lookup"><span data-stu-id="6d4b3-112">Label with a format such as: &lt;user sip uri&gt;|username.&lt;preference set&gt;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d4b3-113">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="6d4b3-113">prefSeqID</span></span></p></td>
<td><p><span data-ttu-id="6d4b3-114">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="6d4b3-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="6d4b3-115">Número secuencial (por etiqueta) para el control de versiones.</span><span class="sxs-lookup"><span data-stu-id="6d4b3-115">A sequential number (per label) for versioning purposes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d4b3-116">prefContent</span><span class="sxs-lookup"><span data-stu-id="6d4b3-116">prefContent</span></span></p></td>
<td><p><span data-ttu-id="6d4b3-117">nvarchar (máx.)</span><span class="sxs-lookup"><span data-stu-id="6d4b3-117">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="6d4b3-118">Contenido codificado.</span><span class="sxs-lookup"><span data-stu-id="6d4b3-118">Encoded content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d4b3-119">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="6d4b3-119">lastModifiedBy</span></span></p></td>
<td><p><span data-ttu-id="6d4b3-120">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="6d4b3-120">int, not null</span></span></p></td>
<td><p><span data-ttu-id="6d4b3-121">Identificador de la entidad de seguridad que ha actualizado la preferencia.</span><span class="sxs-lookup"><span data-stu-id="6d4b3-121">ID of the principal that updated the preference.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="6d4b3-122">Key </span><span class="sxs-lookup"><span data-stu-id="6d4b3-122">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6d4b3-123">Columna</span><span class="sxs-lookup"><span data-stu-id="6d4b3-123">Column</span></span></th>
<th><span data-ttu-id="6d4b3-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="6d4b3-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6d4b3-125">&lt;prefLabel, prefSeqID&gt;</span><span class="sxs-lookup"><span data-stu-id="6d4b3-125">&lt;prefLabel, prefSeqID&gt;</span></span></p></td>
<td><p><span data-ttu-id="6d4b3-126">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="6d4b3-126">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

