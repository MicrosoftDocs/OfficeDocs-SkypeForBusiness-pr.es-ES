---
title: 'Lync Server 2013: tblLastInviteId'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblLastInviteId
ms:assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558625(v=OCS.15)
ms:contentKeyID: 48183608
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a49682d5c154b154ddda6c5fd411905f5850722d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523797"
---
# <a name="tbllastinviteid-in-lync-server-2013"></a><span data-ttu-id="92267-102">tblLastInviteId en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92267-102">tblLastInviteId in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92267-103">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="92267-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="92267-104">tblLastInviteId contiene el último identificador de invitación generado (y utilizado en la tabla tblPrincipalInvites) para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="92267-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>

### <a name="columns"></a><span data-ttu-id="92267-105">Columnas</span><span class="sxs-lookup"><span data-stu-id="92267-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="92267-106">Columna</span><span class="sxs-lookup"><span data-stu-id="92267-106">Column</span></span></th>
<th><span data-ttu-id="92267-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="92267-107">Type</span></span></th>
<th><span data-ttu-id="92267-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="92267-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="92267-109">prinID</span><span class="sxs-lookup"><span data-stu-id="92267-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="92267-110">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="92267-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="92267-111">Id. de la entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="92267-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92267-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="92267-112">lastInviteID</span></span></p></td>
<td><p><span data-ttu-id="92267-113">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="92267-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="92267-114">Identificador de invitación usado por última vez.</span><span class="sxs-lookup"><span data-stu-id="92267-114">Last used invite ID.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="92267-115">Keys</span><span class="sxs-lookup"><span data-stu-id="92267-115">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="92267-116">Columna</span><span class="sxs-lookup"><span data-stu-id="92267-116">Column</span></span></th>
<th><span data-ttu-id="92267-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="92267-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="92267-118">prinID</span><span class="sxs-lookup"><span data-stu-id="92267-118">prinID</span></span></p></td>
<td><p><span data-ttu-id="92267-119">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="92267-119">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92267-120">prinID</span><span class="sxs-lookup"><span data-stu-id="92267-120">prinID</span></span></p></td>
<td><p><span data-ttu-id="92267-121">Clave externa con búsqueda en la tabla tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="92267-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="92267-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="92267-122">See Also</span></span>


[<span data-ttu-id="92267-123">tblPrincipalInvites en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92267-123">tblPrincipalInvites in Lync Server 2013</span></span>](lync-server-2013-tblprincipalinvites.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

