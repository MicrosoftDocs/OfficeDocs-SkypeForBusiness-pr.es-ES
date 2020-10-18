---
title: 'Lync Server 2013: vista de ProgressReport'
description: 'Lync Server 2013: vista de ProgressReport.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ProgressReport view
ms:assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721857(v=OCS.15)
ms:contentKeyID: 49733790
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b95086012f254499644e778e43cafdf70ffc8f9c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579796"
---
# <a name="progressreport-view-in-lync-server-2013"></a><span data-ttu-id="0ee3f-103">Vista ProgressReport en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ee3f-103">ProgressReport view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ee3f-104">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="0ee3f-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="0ee3f-105">La vista ProgressReport almacena información sobre las sesiones finalizadas.</span><span class="sxs-lookup"><span data-stu-id="0ee3f-105">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="0ee3f-106">Solo se escribirán informes de progreso de las llamadas y sesiones que Lync Server 2013 considere que puedan resultar útiles para realizar diagnósticos.</span><span class="sxs-lookup"><span data-stu-id="0ee3f-106">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="0ee3f-107">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0ee3f-107">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0ee3f-108">Los campos ErrorTime, ErrorReportSeq y ProgressReportSeq no se refieren necesariamente a errores, sino a mensajes que indican el estado de las llamadas o los mensajes.</span><span class="sxs-lookup"><span data-stu-id="0ee3f-108">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0ee3f-109">Columna</span><span class="sxs-lookup"><span data-stu-id="0ee3f-109">Column</span></span></th>
<th><span data-ttu-id="0ee3f-110">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="0ee3f-110">Data Type</span></span></th>
<th><span data-ttu-id="0ee3f-111">Detalles</span><span class="sxs-lookup"><span data-stu-id="0ee3f-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0ee3f-112"><strong>Campos errortime</strong></span><span class="sxs-lookup"><span data-stu-id="0ee3f-112"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0ee3f-113">datetime</span><span class="sxs-lookup"><span data-stu-id="0ee3f-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="0ee3f-p102">Hora en que se produjo el error. Se usa en combinación con ErrorRportSeq para identificar el error de forma exclusiva.</span><span class="sxs-lookup"><span data-stu-id="0ee3f-p102">Time of error occurred. Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ee3f-116"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="0ee3f-116"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="0ee3f-117">entero</span><span class="sxs-lookup"><span data-stu-id="0ee3f-117">int</span></span></p></td>
<td><p><span data-ttu-id="0ee3f-p103">Número para identificar el error. Se usa junto con ErrorTime como identificación única de un error.</span><span class="sxs-lookup"><span data-stu-id="0ee3f-p103">ID number to identify the error. Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ee3f-120"><strong>ProgressReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="0ee3f-120"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="0ee3f-121">entero</span><span class="sxs-lookup"><span data-stu-id="0ee3f-121">int</span></span></p></td>
<td><p><span data-ttu-id="0ee3f-122">Identificador del informe de progreso.</span><span class="sxs-lookup"><span data-stu-id="0ee3f-122">ID to identify the progress report.</span></span> <span data-ttu-id="0ee3f-123">Se usa para diferenciar informes de progreso del mismo informe de errores.</span><span class="sxs-lookup"><span data-stu-id="0ee3f-123">Used to distinguish progress reports of the same error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ee3f-124"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="0ee3f-124"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="0ee3f-125">entero</span><span class="sxs-lookup"><span data-stu-id="0ee3f-125">int</span></span></p></td>
<td><p><span data-ttu-id="0ee3f-126">Identificador de diagnóstico del informe de errores.</span><span class="sxs-lookup"><span data-stu-id="0ee3f-126">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ee3f-127"><strong>Source</strong></span><span class="sxs-lookup"><span data-stu-id="0ee3f-127"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="0ee3f-128">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0ee3f-128">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0ee3f-129">Nombre del servidor que originó el error (si el informe se envió desde un componente de servidor).</span><span class="sxs-lookup"><span data-stu-id="0ee3f-129">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ee3f-130"><strong>Aplicación</strong></span><span class="sxs-lookup"><span data-stu-id="0ee3f-130"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="0ee3f-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0ee3f-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0ee3f-132">Nombre de la aplicación que generó el error (si el informe se envió desde un componente de servidor).</span><span class="sxs-lookup"><span data-stu-id="0ee3f-132">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ee3f-133"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="0ee3f-133"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="0ee3f-134">identificador</span><span class="sxs-lookup"><span data-stu-id="0ee3f-134">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="0ee3f-135">Identificador único que correlaciona la información de la hora de unión de los componentes que participan en una conferencia.</span><span class="sxs-lookup"><span data-stu-id="0ee3f-135">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ee3f-136"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="0ee3f-136"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0ee3f-137">entero</span><span class="sxs-lookup"><span data-stu-id="0ee3f-137">int</span></span></p></td>
<td><p><span data-ttu-id="0ee3f-138">Tiempo (en milisegundos) necesario para que un componente específico se una a las conferencias.</span><span class="sxs-lookup"><span data-stu-id="0ee3f-138">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ee3f-139"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="0ee3f-139"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="0ee3f-140">VARCHAR (Max)</span><span class="sxs-lookup"><span data-stu-id="0ee3f-140">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="0ee3f-141">Información adicional del error.</span><span class="sxs-lookup"><span data-stu-id="0ee3f-141">Additional error information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

