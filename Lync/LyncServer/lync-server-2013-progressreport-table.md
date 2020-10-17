---
title: 'Lync Server 2013: tabla ProgressReport'
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
ms.openlocfilehash: c92adf48a09f83c3c3dec18f91e4aadc3a3cbd39
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513237"
---
# <a name="progressreport-table-in-lync-server-2013"></a><span data-ttu-id="01212-102">Tabla ProgressReport en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01212-102">ProgressReport table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01212-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="01212-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="01212-104">Los informes de progreso se basan en datos cargados por el cliente en la base de datos tras completarse una llamada o sesión.</span><span class="sxs-lookup"><span data-stu-id="01212-104">Progress reports are based on data uploaded by the client to the database after a call or session is completed.</span></span> <span data-ttu-id="01212-105">Solo se escribirán informes de progreso de las llamadas y sesiones que Lync Server 2013 considere que puedan resultar útiles para realizar diagnósticos.</span><span class="sxs-lookup"><span data-stu-id="01212-105">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span>

<span data-ttu-id="01212-106">Los campos ErrorTime, ErrorReportSeq y ProgressReportSeq no se refieren necesariamente a errores, sino a mensajes que indican el estado de las llamadas o los mensajes.</span><span class="sxs-lookup"><span data-stu-id="01212-106">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="01212-107">Columna</span><span class="sxs-lookup"><span data-stu-id="01212-107">Column</span></span></th>
<th><span data-ttu-id="01212-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="01212-108">Data Type</span></span></th>
<th><span data-ttu-id="01212-109">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="01212-109">Key/Index</span></span></th>
<th><span data-ttu-id="01212-110">Detalles</span><span class="sxs-lookup"><span data-stu-id="01212-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="01212-111"><strong>Campos errortime</strong></span><span class="sxs-lookup"><span data-stu-id="01212-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="01212-112">datetime</span><span class="sxs-lookup"><span data-stu-id="01212-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="01212-113">Principal, Exterior</span><span class="sxs-lookup"><span data-stu-id="01212-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="01212-114">Fecha y hora del informe de errores de progreso que contiene este informe de progreso.</span><span class="sxs-lookup"><span data-stu-id="01212-114">Date and time of the progress error report that contains this progress report.</span></span> <span data-ttu-id="01212-115">Consulte la <a href="lync-server-2013-errorreport-table.md">tabla errorreport en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="01212-115">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01212-116"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="01212-116"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="01212-117">entero</span><span class="sxs-lookup"><span data-stu-id="01212-117">int</span></span></p></td>
<td><p><span data-ttu-id="01212-118">Principal, Exterior</span><span class="sxs-lookup"><span data-stu-id="01212-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="01212-119">Número de identificación usado junto con ErrorTime, ProgressReportSeq para identificar de manera única un informe de progreso.</span><span class="sxs-lookup"><span data-stu-id="01212-119">ID number used in conjunction with ErrorTime, ProgressReportSeq to uniquely identify a progress report.</span></span> <span data-ttu-id="01212-120">Consulte la <a href="lync-server-2013-errorreport-table.md">tabla errorreport en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="01212-120">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01212-121"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="01212-121"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="01212-122">entero</span><span class="sxs-lookup"><span data-stu-id="01212-122">int</span></span></p></td>
<td><p><span data-ttu-id="01212-123">Principal, Exterior</span><span class="sxs-lookup"><span data-stu-id="01212-123">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="01212-124">Número de id. que identifica el informe de errores.</span><span class="sxs-lookup"><span data-stu-id="01212-124">ID number that identifies the error report.</span></span> <span data-ttu-id="01212-125">ErrorReporSeq se usa junto con ErrorTime para identificar de manera única un informe de errores.</span><span class="sxs-lookup"><span data-stu-id="01212-125">ErrorReporSeq is used in conjunction with ErrorTime to uniquely identify an error report.</span></span> <span data-ttu-id="01212-126">Consulte la <a href="lync-server-2013-errorreport-table.md">tabla errorreport en Lync Server 2013</a> para obtener más información</span><span class="sxs-lookup"><span data-stu-id="01212-126">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information</span></span></p>
<p><span data-ttu-id="01212-127">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="01212-127">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01212-128"><strong>ProgressReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="01212-128"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="01212-129">entero</span><span class="sxs-lookup"><span data-stu-id="01212-129">int</span></span></p></td>
<td><p><span data-ttu-id="01212-130">Principal</span><span class="sxs-lookup"><span data-stu-id="01212-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="01212-p105">Número de identificación usado para identificar el informe de progreso. Se utiliza junto con ErrorTime y ErrorReportSeq para identificar de manera única un informe de progreso.</span><span class="sxs-lookup"><span data-stu-id="01212-p105">ID number to identify the progress report. Used in conjunction with ErrorTime and ErrorReportSeq to uniquely identify a progress report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01212-133"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="01212-133"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="01212-134">entero</span><span class="sxs-lookup"><span data-stu-id="01212-134">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="01212-135">Id. de diagnóstico del informe de progreso.</span><span class="sxs-lookup"><span data-stu-id="01212-135">Diagnostic ID of the progress report.</span></span></p>
<p><span data-ttu-id="01212-136">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="01212-136">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01212-137"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="01212-137"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="01212-138">entero</span><span class="sxs-lookup"><span data-stu-id="01212-138">int</span></span></p></td>
<td><p><span data-ttu-id="01212-139">Externa</span><span class="sxs-lookup"><span data-stu-id="01212-139">Foreign</span></span></p></td>
<td><p><span data-ttu-id="01212-140">Servidor que ha enviado el informe de errores (si el informe se envió desde un componente de servidor).</span><span class="sxs-lookup"><span data-stu-id="01212-140">Server that sent the error report (if the report was sent from a server component).</span></span> <span data-ttu-id="01212-141">Consulte la <a href="lync-server-2013-servers-table.md">tabla servidores en Lync Server 2013</a> para obtener más información. Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="01212-141">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01212-142"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="01212-142"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="01212-143">entero</span><span class="sxs-lookup"><span data-stu-id="01212-143">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="01212-p107">El proceso de Lync Server al que se refiere el informe. Vea la tabla de aplicaciones para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="01212-p107">The Lync Server process that the report is about. See the Application Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01212-146"><strong>Detalle</strong></span><span class="sxs-lookup"><span data-stu-id="01212-146"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="01212-147">imagen</span><span class="sxs-lookup"><span data-stu-id="01212-147">image</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="01212-148">Detalles del informe de progreso, almacenados en formato binario para ahorrar espacio. Estos datos pueden convertirse en formato de texto usando esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="01212-148">Progress report details, stored in binary format to save space.This data can be converted to text format using this syntax:</span></span></p>
<p><span data-ttu-id="01212-149">cast(cast(Detail as varbinary(max)) as varchar(max))</span><span class="sxs-lookup"><span data-stu-id="01212-149">cast(cast(Detail as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01212-150"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="01212-150"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="01212-151">Identificador</span><span class="sxs-lookup"><span data-stu-id="01212-151">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="01212-152">Identificador único que correlaciona información de hora de conexión para los diferentes componentes que participan en una conferencia.</span><span class="sxs-lookup"><span data-stu-id="01212-152">Unique identifier that correlates join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="01212-153">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="01212-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01212-154"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="01212-154"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="01212-155">entero</span><span class="sxs-lookup"><span data-stu-id="01212-155">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="01212-156">Tiempo (en milisegundos) para que un componente específico se una a una conferencia.</span><span class="sxs-lookup"><span data-stu-id="01212-156">Time (in milliseconds) for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="01212-157">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="01212-157">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

