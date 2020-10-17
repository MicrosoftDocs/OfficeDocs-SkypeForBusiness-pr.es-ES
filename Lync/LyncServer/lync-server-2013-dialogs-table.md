---
title: 'Lync Server 2013: tabla Dialogs'
description: 'Lync Server 2013: tabla DIALOGS.'
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
ms.openlocfilehash: 8c2c9cf9ec59fc48f7f5ffc6232980e3f8aa68c1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559706"
---
# <a name="dialogs-table-in-lync-server-2013"></a><span data-ttu-id="f3b38-103">Tabla de cuadros de diálogo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3b38-103">Dialogs table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3b38-104">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="f3b38-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="f3b38-105">La tabla Dialogs es una tabla de apoyo que almacena la información sobre DialogIDs para las sesiones punto a punto.</span><span class="sxs-lookup"><span data-stu-id="f3b38-105">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f3b38-106">Columna</span><span class="sxs-lookup"><span data-stu-id="f3b38-106">Column</span></span></th>
<th><span data-ttu-id="f3b38-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="f3b38-107">Data Type</span></span></th>
<th><span data-ttu-id="f3b38-108">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="f3b38-108">Key/Index</span></span></th>
<th><span data-ttu-id="f3b38-109">Detalles</span><span class="sxs-lookup"><span data-stu-id="f3b38-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f3b38-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="f3b38-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f3b38-111">datetime</span><span class="sxs-lookup"><span data-stu-id="f3b38-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="f3b38-112">Principal</span><span class="sxs-lookup"><span data-stu-id="f3b38-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="f3b38-113">Hora de la solicitud de sesión; se usa junto con SessionIDSeq para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="f3b38-113">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3b38-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f3b38-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f3b38-115">entero</span><span class="sxs-lookup"><span data-stu-id="f3b38-115">int</span></span></p></td>
<td><p><span data-ttu-id="f3b38-116">Principal</span><span class="sxs-lookup"><span data-stu-id="f3b38-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="f3b38-117">Número de identificador para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="f3b38-117">ID number to identify the session.</span></span> <span data-ttu-id="f3b38-118">Se usa junto con SessionIDTime para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="f3b38-118">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3b38-119"><strong>ExternalChecksum</strong></span><span class="sxs-lookup"><span data-stu-id="f3b38-119"><strong>ExternalChecksum</strong></span></span></p></td>
<td><p><span data-ttu-id="f3b38-120">entero</span><span class="sxs-lookup"><span data-stu-id="f3b38-120">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f3b38-121">Suma de comprobación de ExternalID.</span><span class="sxs-lookup"><span data-stu-id="f3b38-121">Checksum of the ExternalID.</span></span> <span data-ttu-id="f3b38-122">Este campo se usa para aumentar la velocidad de las búsquedas en bases de datos.</span><span class="sxs-lookup"><span data-stu-id="f3b38-122">This field is used to increase the speed of database searches.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3b38-123"><strong>ExternalId</strong></span><span class="sxs-lookup"><span data-stu-id="f3b38-123"><strong>ExternalId</strong></span></span></p></td>
<td><p><span data-ttu-id="f3b38-124">varbinary (775)</span><span class="sxs-lookup"><span data-stu-id="f3b38-124">varbinary(775)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f3b38-125">IDENTIFICADOR del cuadro de diálogo SIP, almacenado como binario.</span><span class="sxs-lookup"><span data-stu-id="f3b38-125">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="f3b38-126">El formato del binario es:</span><span class="sxs-lookup"><span data-stu-id="f3b38-126">The format of the binary is:</span></span></p>
<p><span data-ttu-id="f3b38-127">Dialog; from-Tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="f3b38-127">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="f3b38-128">Estos datos pueden convertirse en formato de texto con esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="f3b38-128">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(ExternalId as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

