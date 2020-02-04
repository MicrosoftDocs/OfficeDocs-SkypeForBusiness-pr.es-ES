---
title: 'Lync Server 2013: Tabla Dialogs'
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
ms.openlocfilehash: 326ecac8df81eeba11ed29ff9f1968b681cdb98f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762258"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dialogs-table-in-lync-server-2013"></a><span data-ttu-id="54a2d-102">Tabla Dialogs en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54a2d-102">Dialogs table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54a2d-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="54a2d-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="54a2d-104">La tabla de cuadros de diálogo es una tabla de soporte que almacena la información sobre DialogIDs para las sesiones de punto a punto.</span><span class="sxs-lookup"><span data-stu-id="54a2d-104">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="54a2d-105">Columna</span><span class="sxs-lookup"><span data-stu-id="54a2d-105">Column</span></span></th>
<th><span data-ttu-id="54a2d-106">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="54a2d-106">Data Type</span></span></th>
<th><span data-ttu-id="54a2d-107">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="54a2d-107">Key/Index</span></span></th>
<th><span data-ttu-id="54a2d-108">Detalles</span><span class="sxs-lookup"><span data-stu-id="54a2d-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="54a2d-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="54a2d-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="54a2d-110">datetime</span><span class="sxs-lookup"><span data-stu-id="54a2d-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="54a2d-111">Primary</span><span class="sxs-lookup"><span data-stu-id="54a2d-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="54a2d-112">Hora de la solicitud de sesión; se usa en conjunción con SessionIDSeq para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="54a2d-112">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54a2d-113"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="54a2d-113"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="54a2d-114">int</span><span class="sxs-lookup"><span data-stu-id="54a2d-114">int</span></span></p></td>
<td><p><span data-ttu-id="54a2d-115">Primary</span><span class="sxs-lookup"><span data-stu-id="54a2d-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="54a2d-116">Número de identificación para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="54a2d-116">ID number to identify the session.</span></span> <span data-ttu-id="54a2d-117">Se usa en conjunción con SessionIDTime para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="54a2d-117">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54a2d-118"><strong>ExternalChecksum</strong></span><span class="sxs-lookup"><span data-stu-id="54a2d-118"><strong>ExternalChecksum</strong></span></span></p></td>
<td><p><span data-ttu-id="54a2d-119">int</span><span class="sxs-lookup"><span data-stu-id="54a2d-119">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="54a2d-120">Suma de comprobación de la ExternalID.</span><span class="sxs-lookup"><span data-stu-id="54a2d-120">Checksum of the ExternalID.</span></span> <span data-ttu-id="54a2d-121">Este campo se usa para aumentar la velocidad de las búsquedas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="54a2d-121">This field is used to increase the speed of database searches.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54a2d-122"><strong>ExternalId</strong></span><span class="sxs-lookup"><span data-stu-id="54a2d-122"><strong>ExternalId</strong></span></span></p></td>
<td><p><span data-ttu-id="54a2d-123">varbinary (775)</span><span class="sxs-lookup"><span data-stu-id="54a2d-123">varbinary(775)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="54a2d-124">IDENTIFICADOR del cuadro de diálogo SIP, almacenado como binario.</span><span class="sxs-lookup"><span data-stu-id="54a2d-124">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="54a2d-125">El formato del binario es:</span><span class="sxs-lookup"><span data-stu-id="54a2d-125">The format of the binary is:</span></span></p>
<p><span data-ttu-id="54a2d-126">cuadro de diálogo; desde: etiqueta; to-Tag</span><span class="sxs-lookup"><span data-stu-id="54a2d-126">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="54a2d-127">Estos datos se pueden convertir a formato de texto con esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="54a2d-127">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(ExternalId as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

