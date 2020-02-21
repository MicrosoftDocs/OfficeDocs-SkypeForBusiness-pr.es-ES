---
title: 'Lync Server 2013: tblAdminLock'
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
ms.openlocfilehash: bd22a75b8a3e8e405b8720e4b12899f912232f3f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192103"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tbladminlock-in-lync-server-2013"></a><span data-ttu-id="8a05c-102">tblAdminLock en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a05c-102">tblAdminLock in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a05c-103">_**Última modificación del tema:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="8a05c-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="8a05c-104">La tabla tblAdminLock contiene el bloqueo de administrador necesario para ejecutar algunos comandos de administrador.</span><span class="sxs-lookup"><span data-stu-id="8a05c-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>

### <a name="columns"></a><span data-ttu-id="8a05c-105">Columns</span><span class="sxs-lookup"><span data-stu-id="8a05c-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8a05c-106">Columna</span><span class="sxs-lookup"><span data-stu-id="8a05c-106">Column</span></span></th>
<th><span data-ttu-id="8a05c-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="8a05c-107">Type</span></span></th>
<th><span data-ttu-id="8a05c-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="8a05c-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8a05c-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="8a05c-109">lockExpiresTime</span></span></p></td>
<td><p><span data-ttu-id="8a05c-110">datetime, no NULL</span><span class="sxs-lookup"><span data-stu-id="8a05c-110">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="8a05c-p101">Fecha y hora de expiración del bloqueo. El propietario puede ampliar este valor de manera regular.</span><span class="sxs-lookup"><span data-stu-id="8a05c-p101">Lock expiration date and time. The owner can extend this value periodically.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a05c-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="8a05c-113">lockServerID</span></span></p></td>
<td><p><span data-ttu-id="8a05c-114">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="8a05c-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="8a05c-115">Identificador del servidor que posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="8a05c-115">ID of the server that owns the lock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a05c-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="8a05c-116">lockActorID</span></span></p></td>
<td><p><span data-ttu-id="8a05c-117">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="8a05c-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="8a05c-118">Identificador de la entidad de seguridad que posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="8a05c-118">ID of the principal that owns the lock.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

