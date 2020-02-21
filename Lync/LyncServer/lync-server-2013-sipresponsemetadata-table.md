---
title: 'Lync Server 2013: tabla SIPResponseMetaData'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIPResponseMetaData table
ms:assetid: cf723737-4a75-4352-829b-f4954aa59716
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205294(v=OCS.15)
ms:contentKeyID: 48185510
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0143bdd74b955f2cba5f68540be7c969f748aa47
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181803"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sipresponsemetadata-table-in-lync-server-2013"></a><span data-ttu-id="26d58-102">Tabla SIPResponseMetaData en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="26d58-102">SIPResponseMetaData table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26d58-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="26d58-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="26d58-p101">SIPResponseMetaDataTable contiene una lista de los códigos de respuesta SIP y la clasificación y definición de cada uno de estos códigos. Estos códigos se generan como respuesta a los eventos que afectan a los dispositivos SIP y a las sesiones de comunicación SIP; por ejemplo, se genera el código de respuesta 403 cuando un dispositivo SIP realiza una solicitud, pero el servidor rechaza responderla.</span><span class="sxs-lookup"><span data-stu-id="26d58-p101">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes. These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>

<span data-ttu-id="26d58-106">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="26d58-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="26d58-107">Columna</span><span class="sxs-lookup"><span data-stu-id="26d58-107">Column</span></span></th>
<th><span data-ttu-id="26d58-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="26d58-108">Data Type</span></span></th>
<th><span data-ttu-id="26d58-109">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="26d58-109">Key/Index</span></span></th>
<th><span data-ttu-id="26d58-110">Detalles</span><span class="sxs-lookup"><span data-stu-id="26d58-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="26d58-111"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="26d58-111"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="26d58-112">int</span><span class="sxs-lookup"><span data-stu-id="26d58-112">int</span></span></p></td>
<td><p><span data-ttu-id="26d58-113">Principal</span><span class="sxs-lookup"><span data-stu-id="26d58-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="26d58-114">Valor numérico que representa el código de respuesta SIP.</span><span class="sxs-lookup"><span data-stu-id="26d58-114">Numeric value that represents the SIP response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26d58-115"><strong>Clase</strong></span><span class="sxs-lookup"><span data-stu-id="26d58-115"><strong>Class</strong></span></span></p></td>
<td><p><span data-ttu-id="26d58-116">int</span><span class="sxs-lookup"><span data-stu-id="26d58-116">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="26d58-p102">Clasificación general para el código de respuesta. Las clasificaciones incluyen:</span><span class="sxs-lookup"><span data-stu-id="26d58-p102">General classification for the response code. Classifications include:</span></span></p>
<ul>
<li><p><span data-ttu-id="26d58-119">1 – Respuestas de tipo informativo</span><span class="sxs-lookup"><span data-stu-id="26d58-119">1 – Informational Responses</span></span></p></li>
<li><p><span data-ttu-id="26d58-120">2 – Respuestas correctas</span><span class="sxs-lookup"><span data-stu-id="26d58-120">2 – Successful Responses</span></span></p></li>
<li><p><span data-ttu-id="26d58-121">3 – Respuestas de redirección</span><span class="sxs-lookup"><span data-stu-id="26d58-121">3 – Redirection Responses</span></span></p></li>
<li><p><span data-ttu-id="26d58-122">4 – Respuestas de error de cliente</span><span class="sxs-lookup"><span data-stu-id="26d58-122">4 – Client Failure Responses</span></span></p></li>
<li><p><span data-ttu-id="26d58-123">5--respuestas de error de servidor</span><span class="sxs-lookup"><span data-stu-id="26d58-123">5 -- Server Failure Responses</span></span></p></li>
<li><p><span data-ttu-id="26d58-124">6 – Respuesta de error global</span><span class="sxs-lookup"><span data-stu-id="26d58-124">6 – Global Failure Response</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26d58-125"><strong>Descripción</strong></span><span class="sxs-lookup"><span data-stu-id="26d58-125"><strong>Description</strong></span></span></p></td>
<td><p><span data-ttu-id="26d58-126">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="26d58-126">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="26d58-p103">Descripción del código de respuesta SIP. Por ejemplo, el código de respuesta 181 tiene la siguiente descripción:</span><span class="sxs-lookup"><span data-stu-id="26d58-p103">Description of the SIP response code. For example, response code 181 has the following description:</span></span></p>
<p><span data-ttu-id="26d58-129">Se está desviando la llamada</span><span class="sxs-lookup"><span data-stu-id="26d58-129">Call Is Being Forwarded</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

