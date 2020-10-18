---
title: 'Lync Server 2013: tblAdminLock'
description: 'Lync Server 2013: tblAdminLock.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblAdminLock
ms:assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558665(v=OCS.15)
ms:contentKeyID: 48184560
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3313826b2c0d578c515fb25f83e713b8978ae63
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573716"
---
# <a name="tbladminlock-in-lync-server-2013"></a><span data-ttu-id="f3aba-103">tblAdminLock en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3aba-103">tblAdminLock in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3aba-104">_**Última modificación del tema:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="f3aba-104">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="f3aba-105">La tabla tblAdminLock contiene el bloqueo de administrador necesario para ejecutar algunos comandos de administrador.</span><span class="sxs-lookup"><span data-stu-id="f3aba-105">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>

### <a name="columns"></a><span data-ttu-id="f3aba-106">Columnas</span><span class="sxs-lookup"><span data-stu-id="f3aba-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f3aba-107">Columna</span><span class="sxs-lookup"><span data-stu-id="f3aba-107">Column</span></span></th>
<th><span data-ttu-id="f3aba-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="f3aba-108">Type</span></span></th>
<th><span data-ttu-id="f3aba-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="f3aba-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f3aba-110">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="f3aba-110">lockExpiresTime</span></span></p></td>
<td><p><span data-ttu-id="f3aba-111">datetime, no NULL</span><span class="sxs-lookup"><span data-stu-id="f3aba-111">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="f3aba-p101">Fecha y hora de expiración del bloqueo. El propietario puede ampliar este valor de manera regular.</span><span class="sxs-lookup"><span data-stu-id="f3aba-p101">Lock expiration date and time. The owner can extend this value periodically.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3aba-114">lockServerID</span><span class="sxs-lookup"><span data-stu-id="f3aba-114">lockServerID</span></span></p></td>
<td><p><span data-ttu-id="f3aba-115">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="f3aba-115">int, not null</span></span></p></td>
<td><p><span data-ttu-id="f3aba-116">Identificador del servidor que posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="f3aba-116">ID of the server that owns the lock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3aba-117">lockActorID</span><span class="sxs-lookup"><span data-stu-id="f3aba-117">lockActorID</span></span></p></td>
<td><p><span data-ttu-id="f3aba-118">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="f3aba-118">int, not null</span></span></p></td>
<td><p><span data-ttu-id="f3aba-119">Identificador de la entidad de seguridad que posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="f3aba-119">ID of the principal that owns the lock.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

