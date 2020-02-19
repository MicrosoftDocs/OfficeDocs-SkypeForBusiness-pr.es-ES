---
title: 'Lync Server 2013: tabla Dialogs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dialogs table
ms:assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425954(v=OCS.15)
ms:contentKeyID: 48184001
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf2f23e9c82c1c6d4dd21519f1193b902c8e6434
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136397"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dialogs-table-in-lync-server-2013"></a><span data-ttu-id="e9f91-102">Tabla de cuadros de diálogo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9f91-102">Dialogs table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9f91-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="e9f91-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="e9f91-104">La tabla Dialogs es una tabla de apoyo que almacena la información sobre DialogIDs para las sesiones punto a punto.</span><span class="sxs-lookup"><span data-stu-id="e9f91-104">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e9f91-105">Columna</span><span class="sxs-lookup"><span data-stu-id="e9f91-105">Column</span></span></th>
<th><span data-ttu-id="e9f91-106">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="e9f91-106">Data Type</span></span></th>
<th><span data-ttu-id="e9f91-107">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="e9f91-107">Key/Index</span></span></th>
<th><span data-ttu-id="e9f91-108">Detalles</span><span class="sxs-lookup"><span data-stu-id="e9f91-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e9f91-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="e9f91-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e9f91-110">datetime</span><span class="sxs-lookup"><span data-stu-id="e9f91-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="e9f91-111">Principal</span><span class="sxs-lookup"><span data-stu-id="e9f91-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="e9f91-112">Hora de la solicitud de sesión; se usa junto con SessionIDSeq para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="e9f91-112">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9f91-113"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e9f91-113"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e9f91-114">int</span><span class="sxs-lookup"><span data-stu-id="e9f91-114">int</span></span></p></td>
<td><p><span data-ttu-id="e9f91-115">Principal</span><span class="sxs-lookup"><span data-stu-id="e9f91-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="e9f91-116">Número de identificador para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="e9f91-116">ID number to identify the session.</span></span> <span data-ttu-id="e9f91-117">Se usa junto con SessionIDTime para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="e9f91-117">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9f91-118"><strong>ExternalChecksum</strong></span><span class="sxs-lookup"><span data-stu-id="e9f91-118"><strong>ExternalChecksum</strong></span></span></p></td>
<td><p><span data-ttu-id="e9f91-119">int</span><span class="sxs-lookup"><span data-stu-id="e9f91-119">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e9f91-120">Suma de comprobación de ExternalID.</span><span class="sxs-lookup"><span data-stu-id="e9f91-120">Checksum of the ExternalID.</span></span> <span data-ttu-id="e9f91-121">Este campo se usa para aumentar la velocidad de las búsquedas en bases de datos.</span><span class="sxs-lookup"><span data-stu-id="e9f91-121">This field is used to increase the speed of database searches.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9f91-122"><strong>ExternalId</strong></span><span class="sxs-lookup"><span data-stu-id="e9f91-122"><strong>ExternalId</strong></span></span></p></td>
<td><p><span data-ttu-id="e9f91-123">varbinary (775)</span><span class="sxs-lookup"><span data-stu-id="e9f91-123">varbinary(775)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e9f91-124">IDENTIFICADOR del cuadro de diálogo SIP, almacenado como binario.</span><span class="sxs-lookup"><span data-stu-id="e9f91-124">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="e9f91-125">El formato del binario es:</span><span class="sxs-lookup"><span data-stu-id="e9f91-125">The format of the binary is:</span></span></p>
<p><span data-ttu-id="e9f91-126">Dialog; from-Tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="e9f91-126">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="e9f91-127">Estos datos pueden convertirse en formato de texto con esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="e9f91-127">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(ExternalId as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

