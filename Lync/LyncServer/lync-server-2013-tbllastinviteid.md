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
ms.openlocfilehash: b58f43c696a6218d0dd9b670615cc0f73b0b7ae3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42024731"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbllastinviteid-in-lync-server-2013"></a><span data-ttu-id="ea545-102">tblLastInviteId en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ea545-102">tblLastInviteId in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea545-103">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="ea545-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="ea545-104">tblLastInviteId contiene el último identificador de invitación generado (y utilizado en la tabla tblPrincipalInvites) para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="ea545-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>

### <a name="columns"></a><span data-ttu-id="ea545-105">Columns</span><span class="sxs-lookup"><span data-stu-id="ea545-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ea545-106">Columna</span><span class="sxs-lookup"><span data-stu-id="ea545-106">Column</span></span></th>
<th><span data-ttu-id="ea545-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="ea545-107">Type</span></span></th>
<th><span data-ttu-id="ea545-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="ea545-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ea545-109">prinID</span><span class="sxs-lookup"><span data-stu-id="ea545-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="ea545-110">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="ea545-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="ea545-111">Id. de la entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ea545-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea545-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="ea545-112">lastInviteID</span></span></p></td>
<td><p><span data-ttu-id="ea545-113">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="ea545-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="ea545-114">Identificador de invitación usado por última vez.</span><span class="sxs-lookup"><span data-stu-id="ea545-114">Last used invite ID.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="ea545-115">Keys</span><span class="sxs-lookup"><span data-stu-id="ea545-115">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ea545-116">Columna</span><span class="sxs-lookup"><span data-stu-id="ea545-116">Column</span></span></th>
<th><span data-ttu-id="ea545-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="ea545-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ea545-118">prinID</span><span class="sxs-lookup"><span data-stu-id="ea545-118">prinID</span></span></p></td>
<td><p><span data-ttu-id="ea545-119">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="ea545-119">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea545-120">prinID</span><span class="sxs-lookup"><span data-stu-id="ea545-120">prinID</span></span></p></td>
<td><p><span data-ttu-id="ea545-121">Clave externa con búsqueda en la tabla tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="ea545-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="ea545-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="ea545-122">See Also</span></span>


[<span data-ttu-id="ea545-123">tblPrincipalInvites en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ea545-123">tblPrincipalInvites in Lync Server 2013</span></span>](lync-server-2013-tblprincipalinvites.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

