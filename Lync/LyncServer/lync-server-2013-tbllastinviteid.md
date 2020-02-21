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
ms.openlocfilehash: 702c754830a34a445b11da394fc15add20ab4b0b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42218276"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tbllastinviteid-in-lync-server-2013"></a><span data-ttu-id="fb318-102">tblLastInviteId en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb318-102">tblLastInviteId in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb318-103">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="fb318-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="fb318-104">tblLastInviteId contiene el último identificador de invitación generado (y utilizado en la tabla tblPrincipalInvites) para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="fb318-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>

### <a name="columns"></a><span data-ttu-id="fb318-105">Columns</span><span class="sxs-lookup"><span data-stu-id="fb318-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fb318-106">Columna</span><span class="sxs-lookup"><span data-stu-id="fb318-106">Column</span></span></th>
<th><span data-ttu-id="fb318-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="fb318-107">Type</span></span></th>
<th><span data-ttu-id="fb318-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="fb318-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fb318-109">prinID</span><span class="sxs-lookup"><span data-stu-id="fb318-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="fb318-110">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="fb318-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="fb318-111">Id. de la entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="fb318-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb318-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="fb318-112">lastInviteID</span></span></p></td>
<td><p><span data-ttu-id="fb318-113">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="fb318-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="fb318-114">Identificador de invitación usado por última vez.</span><span class="sxs-lookup"><span data-stu-id="fb318-114">Last used invite ID.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="fb318-115">Keys</span><span class="sxs-lookup"><span data-stu-id="fb318-115">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fb318-116">Columna</span><span class="sxs-lookup"><span data-stu-id="fb318-116">Column</span></span></th>
<th><span data-ttu-id="fb318-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="fb318-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fb318-118">prinID</span><span class="sxs-lookup"><span data-stu-id="fb318-118">prinID</span></span></p></td>
<td><p><span data-ttu-id="fb318-119">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="fb318-119">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb318-120">prinID</span><span class="sxs-lookup"><span data-stu-id="fb318-120">prinID</span></span></p></td>
<td><p><span data-ttu-id="fb318-121">Clave externa con búsqueda en la tabla tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="fb318-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="fb318-122">Consulta también</span><span class="sxs-lookup"><span data-stu-id="fb318-122">See Also</span></span>


[<span data-ttu-id="fb318-123">tblPrincipalInvites en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb318-123">tblPrincipalInvites in Lync Server 2013</span></span>](lync-server-2013-tblprincipalinvites.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

