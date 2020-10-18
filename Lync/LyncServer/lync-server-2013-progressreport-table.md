---
title: 'Lync Server 2013: tabla ProgressReport'
description: 'Lync Server 2013: tabla ProgressReport.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ProgressReport table
ms:assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425864(v=OCS.15)
ms:contentKeyID: 48183847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d36ee2ab75410ea2462da4b647ef5b45afefb1bb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579826"
---
# <a name="progressreport-table-in-lync-server-2013"></a><span data-ttu-id="fa9d2-103">Tabla ProgressReport en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fa9d2-103">ProgressReport table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa9d2-104">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="fa9d2-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="fa9d2-105">Los informes de progreso se basan en datos cargados por el cliente en la base de datos tras completarse una llamada o sesión.</span><span class="sxs-lookup"><span data-stu-id="fa9d2-105">Progress reports are based on data uploaded by the client to the database after a call or session is completed.</span></span> <span data-ttu-id="fa9d2-106">Solo se escribirán informes de progreso de las llamadas y sesiones que Lync Server 2013 considere que puedan resultar útiles para realizar diagnósticos.</span><span class="sxs-lookup"><span data-stu-id="fa9d2-106">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span>

<span data-ttu-id="fa9d2-107">Los campos ErrorTime, ErrorReportSeq y ProgressReportSeq no se refieren necesariamente a errores, sino a mensajes que indican el estado de las llamadas o los mensajes.</span><span class="sxs-lookup"><span data-stu-id="fa9d2-107">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fa9d2-108">Columna</span><span class="sxs-lookup"><span data-stu-id="fa9d2-108">Column</span></span></th>
<th><span data-ttu-id="fa9d2-109">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="fa9d2-109">Data Type</span></span></th>
<th><span data-ttu-id="fa9d2-110">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="fa9d2-110">Key/Index</span></span></th>
<th><span data-ttu-id="fa9d2-111">Detalles</span><span class="sxs-lookup"><span data-stu-id="fa9d2-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa9d2-112"><strong>Campos errortime</strong></span><span class="sxs-lookup"><span data-stu-id="fa9d2-112"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fa9d2-113">datetime</span><span class="sxs-lookup"><span data-stu-id="fa9d2-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="fa9d2-114">Principal, Exterior</span><span class="sxs-lookup"><span data-stu-id="fa9d2-114">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="fa9d2-115">Fecha y hora del informe de errores de progreso que contiene este informe de progreso.</span><span class="sxs-lookup"><span data-stu-id="fa9d2-115">Date and time of the progress error report that contains this progress report.</span></span> <span data-ttu-id="fa9d2-116">Consulte la <a href="lync-server-2013-errorreport-table.md">tabla errorreport en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="fa9d2-116">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa9d2-117"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="fa9d2-117"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="fa9d2-118">entero</span><span class="sxs-lookup"><span data-stu-id="fa9d2-118">int</span></span></p></td>
<td><p><span data-ttu-id="fa9d2-119">Principal, Exterior</span><span class="sxs-lookup"><span data-stu-id="fa9d2-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="fa9d2-120">Número de identificación usado junto con ErrorTime, ProgressReportSeq para identificar de manera única un informe de progreso.</span><span class="sxs-lookup"><span data-stu-id="fa9d2-120">ID number used in conjunction with ErrorTime, ProgressReportSeq to uniquely identify a progress report.</span></span> <span data-ttu-id="fa9d2-121">Consulte la <a href="lync-server-2013-errorreport-table.md">tabla errorreport en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="fa9d2-121">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa9d2-122"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="fa9d2-122"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="fa9d2-123">entero</span><span class="sxs-lookup"><span data-stu-id="fa9d2-123">int</span></span></p></td>
<td><p><span data-ttu-id="fa9d2-124">Principal, Exterior</span><span class="sxs-lookup"><span data-stu-id="fa9d2-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="fa9d2-125">Número de id. que identifica el informe de errores.</span><span class="sxs-lookup"><span data-stu-id="fa9d2-125">ID number that identifies the error report.</span></span> <span data-ttu-id="fa9d2-126">ErrorReporSeq se usa junto con ErrorTime para identificar de manera única un informe de errores.</span><span class="sxs-lookup"><span data-stu-id="fa9d2-126">ErrorReporSeq is used in conjunction with ErrorTime to uniquely identify an error report.</span></span> <span data-ttu-id="fa9d2-127">Consulte la <a href="lync-server-2013-errorreport-table.md">tabla errorreport en Lync Server 2013</a> para obtener más información</span><span class="sxs-lookup"><span data-stu-id="fa9d2-127">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information</span></span></p>
<p><span data-ttu-id="fa9d2-128">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fa9d2-128">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa9d2-129"><strong>ProgressReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="fa9d2-129"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="fa9d2-130">entero</span><span class="sxs-lookup"><span data-stu-id="fa9d2-130">int</span></span></p></td>
<td><p><span data-ttu-id="fa9d2-131">Principal</span><span class="sxs-lookup"><span data-stu-id="fa9d2-131">Primary</span></span></p></td>
<td><p><span data-ttu-id="fa9d2-p105">Número de identificación usado para identificar el informe de progreso. Se utiliza junto con ErrorTime y ErrorReportSeq para identificar de manera única un informe de progreso.</span><span class="sxs-lookup"><span data-stu-id="fa9d2-p105">ID number to identify the progress report. Used in conjunction with ErrorTime and ErrorReportSeq to uniquely identify a progress report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa9d2-134"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="fa9d2-134"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="fa9d2-135">entero</span><span class="sxs-lookup"><span data-stu-id="fa9d2-135">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa9d2-136">Id. de diagnóstico del informe de progreso.</span><span class="sxs-lookup"><span data-stu-id="fa9d2-136">Diagnostic ID of the progress report.</span></span></p>
<p><span data-ttu-id="fa9d2-137">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fa9d2-137">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa9d2-138"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="fa9d2-138"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="fa9d2-139">entero</span><span class="sxs-lookup"><span data-stu-id="fa9d2-139">int</span></span></p></td>
<td><p><span data-ttu-id="fa9d2-140">Externa</span><span class="sxs-lookup"><span data-stu-id="fa9d2-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fa9d2-141">Servidor que ha enviado el informe de errores (si el informe se envió desde un componente de servidor).</span><span class="sxs-lookup"><span data-stu-id="fa9d2-141">Server that sent the error report (if the report was sent from a server component).</span></span> <span data-ttu-id="fa9d2-142">Consulte la <a href="lync-server-2013-servers-table.md">tabla servidores en Lync Server 2013</a> para obtener más información. Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fa9d2-142">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa9d2-143"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="fa9d2-143"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="fa9d2-144">entero</span><span class="sxs-lookup"><span data-stu-id="fa9d2-144">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa9d2-p107">El proceso de Lync Server al que se refiere el informe. Vea la tabla de aplicaciones para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="fa9d2-p107">The Lync Server process that the report is about. See the Application Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa9d2-147"><strong>Detalle</strong></span><span class="sxs-lookup"><span data-stu-id="fa9d2-147"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="fa9d2-148">imagen</span><span class="sxs-lookup"><span data-stu-id="fa9d2-148">image</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa9d2-149">Detalles del informe de progreso, almacenados en formato binario para ahorrar espacio. Estos datos pueden convertirse en formato de texto usando esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="fa9d2-149">Progress report details, stored in binary format to save space.This data can be converted to text format using this syntax:</span></span></p>
<p><span data-ttu-id="fa9d2-150">cast(cast(Detail as varbinary(max)) as varchar(max))</span><span class="sxs-lookup"><span data-stu-id="fa9d2-150">cast(cast(Detail as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa9d2-151"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="fa9d2-151"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="fa9d2-152">Identificador</span><span class="sxs-lookup"><span data-stu-id="fa9d2-152">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa9d2-153">Identificador único que correlaciona información de hora de conexión para los diferentes componentes que participan en una conferencia.</span><span class="sxs-lookup"><span data-stu-id="fa9d2-153">Unique identifier that correlates join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="fa9d2-154">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fa9d2-154">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa9d2-155"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="fa9d2-155"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fa9d2-156">entero</span><span class="sxs-lookup"><span data-stu-id="fa9d2-156">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa9d2-157">Tiempo (en milisegundos) para que un componente específico se una a una conferencia.</span><span class="sxs-lookup"><span data-stu-id="fa9d2-157">Time (in milliseconds) for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="fa9d2-158">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fa9d2-158">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

