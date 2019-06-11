---
title: 'Lync Server 2013: tblAdminLock'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblAdminLock
ms:assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558665(v=OCS.15)
ms:contentKeyID: 48184560
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cdfbc28f440fe9bbcc186e685cd5efdb5f23498
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850490"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladminlock-in-lync-server-2013"></a><span data-ttu-id="3ce95-102">tblAdminLock en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ce95-102">tblAdminLock in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ce95-103">_**Última modificación del tema:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="3ce95-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="3ce95-104">tblAdminLock contiene el bloqueo de administrador necesario para ejecutar algunos comandos de administrador.</span><span class="sxs-lookup"><span data-stu-id="3ce95-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>

### <a name="columns"></a><span data-ttu-id="3ce95-105">Columnas</span><span class="sxs-lookup"><span data-stu-id="3ce95-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3ce95-106">Columna</span><span class="sxs-lookup"><span data-stu-id="3ce95-106">Column</span></span></th>
<th><span data-ttu-id="3ce95-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="3ce95-107">Type</span></span></th>
<th><span data-ttu-id="3ce95-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="3ce95-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3ce95-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="3ce95-109">lockExpiresTime</span></span></p></td>
<td><p><span data-ttu-id="3ce95-110">DateTime, not null</span><span class="sxs-lookup"><span data-stu-id="3ce95-110">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="3ce95-111">Bloquear la fecha y la hora de expiración.</span><span class="sxs-lookup"><span data-stu-id="3ce95-111">Lock expiration date and time.</span></span> <span data-ttu-id="3ce95-112">El propietario puede extender este valor de forma periódica.</span><span class="sxs-lookup"><span data-stu-id="3ce95-112">The owner can extend this value periodically.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ce95-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="3ce95-113">lockServerID</span></span></p></td>
<td><p><span data-ttu-id="3ce95-114">int, not null</span><span class="sxs-lookup"><span data-stu-id="3ce95-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="3ce95-115">IDENTIFICADOR del servidor que posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="3ce95-115">ID of the server that owns the lock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ce95-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="3ce95-116">lockActorID</span></span></p></td>
<td><p><span data-ttu-id="3ce95-117">int, not null</span><span class="sxs-lookup"><span data-stu-id="3ce95-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="3ce95-118">IDENTIFICADOR de la entidad de identidad que posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="3ce95-118">ID of the principal that owns the lock.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

