---
title: 'Lync Server 2013: vista de ProgressReport'
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
ms.openlocfilehash: 916fb459e71460249b47719ab4a4c07f8d082e4d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049622"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-view-in-lync-server-2013"></a><span data-ttu-id="d416a-102">Vista ProgressReport en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d416a-102">ProgressReport view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d416a-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="d416a-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="d416a-104">La vista ProgressReport almacena información sobre las sesiones finalizadas.</span><span class="sxs-lookup"><span data-stu-id="d416a-104">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="d416a-105">Solo se escribirán informes de progreso de las llamadas y sesiones que Lync Server 2013 considere que puedan resultar útiles para realizar diagnósticos.</span><span class="sxs-lookup"><span data-stu-id="d416a-105">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="d416a-106">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d416a-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d416a-107">Los campos ErrorTime, ErrorReportSeq y ProgressReportSeq no se refieren necesariamente a errores, sino a mensajes que indican el estado de las llamadas o los mensajes.</span><span class="sxs-lookup"><span data-stu-id="d416a-107">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d416a-108">Columna</span><span class="sxs-lookup"><span data-stu-id="d416a-108">Column</span></span></th>
<th><span data-ttu-id="d416a-109">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="d416a-109">Data Type</span></span></th>
<th><span data-ttu-id="d416a-110">Detalles</span><span class="sxs-lookup"><span data-stu-id="d416a-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d416a-111"><strong>Campos errortime</strong></span><span class="sxs-lookup"><span data-stu-id="d416a-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d416a-112">datetime</span><span class="sxs-lookup"><span data-stu-id="d416a-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="d416a-p102">Hora en que se produjo el error. Se usa en combinación con ErrorRportSeq para identificar el error de forma exclusiva.</span><span class="sxs-lookup"><span data-stu-id="d416a-p102">Time of error occurred. Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d416a-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="d416a-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d416a-116">int</span><span class="sxs-lookup"><span data-stu-id="d416a-116">int</span></span></p></td>
<td><p><span data-ttu-id="d416a-p103">Número para identificar el error. Se usa junto con ErrorTime como identificación única de un error.</span><span class="sxs-lookup"><span data-stu-id="d416a-p103">ID number to identify the error. Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d416a-119"><strong>ProgressReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="d416a-119"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d416a-120">int</span><span class="sxs-lookup"><span data-stu-id="d416a-120">int</span></span></p></td>
<td><p><span data-ttu-id="d416a-121">Identificador del informe de progreso.</span><span class="sxs-lookup"><span data-stu-id="d416a-121">ID to identify the progress report.</span></span> <span data-ttu-id="d416a-122">Se usa para diferenciar informes de progreso del mismo informe de errores.</span><span class="sxs-lookup"><span data-stu-id="d416a-122">Used to distinguish progress reports of the same error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d416a-123"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="d416a-123"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="d416a-124">int</span><span class="sxs-lookup"><span data-stu-id="d416a-124">int</span></span></p></td>
<td><p><span data-ttu-id="d416a-125">Identificador de diagnóstico del informe de errores.</span><span class="sxs-lookup"><span data-stu-id="d416a-125">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d416a-126"><strong>Source</strong></span><span class="sxs-lookup"><span data-stu-id="d416a-126"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="d416a-127">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d416a-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d416a-128">Nombre del servidor que originó el error (si el informe se envió desde un componente de servidor).</span><span class="sxs-lookup"><span data-stu-id="d416a-128">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d416a-129"><strong>Application</strong></span><span class="sxs-lookup"><span data-stu-id="d416a-129"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="d416a-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d416a-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d416a-131">Nombre de la aplicación que generó el error (si el informe se envió desde un componente de servidor).</span><span class="sxs-lookup"><span data-stu-id="d416a-131">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d416a-132"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="d416a-132"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="d416a-133">identificador</span><span class="sxs-lookup"><span data-stu-id="d416a-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="d416a-134">Identificador único que correlaciona la información de la hora de unión de los componentes que participan en una conferencia.</span><span class="sxs-lookup"><span data-stu-id="d416a-134">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d416a-135"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="d416a-135"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d416a-136">int</span><span class="sxs-lookup"><span data-stu-id="d416a-136">int</span></span></p></td>
<td><p><span data-ttu-id="d416a-137">Tiempo (en milisegundos) necesario para que un componente específico se una a las conferencias.</span><span class="sxs-lookup"><span data-stu-id="d416a-137">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d416a-138"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="d416a-138"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="d416a-139">VARCHAR (Max)</span><span class="sxs-lookup"><span data-stu-id="d416a-139">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="d416a-140">Información adicional del error.</span><span class="sxs-lookup"><span data-stu-id="d416a-140">Additional error information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

