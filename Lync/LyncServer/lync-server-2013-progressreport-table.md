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
ms.openlocfilehash: 1aae907981e04d8966bb7eac4229232056d1004e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049652"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-table-in-lync-server-2013"></a><span data-ttu-id="269cc-102">Tabla ProgressReport en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="269cc-102">ProgressReport table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="269cc-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="269cc-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="269cc-104">Los informes de progreso se basan en datos cargados por el cliente en la base de datos tras completarse una llamada o sesión.</span><span class="sxs-lookup"><span data-stu-id="269cc-104">Progress reports are based on data uploaded by the client to the database after a call or session is completed.</span></span> <span data-ttu-id="269cc-105">Solo se escribirán informes de progreso de las llamadas y sesiones que Lync Server 2013 considere que puedan resultar útiles para realizar diagnósticos.</span><span class="sxs-lookup"><span data-stu-id="269cc-105">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span>

<span data-ttu-id="269cc-106">Los campos ErrorTime, ErrorReportSeq y ProgressReportSeq no se refieren necesariamente a errores, sino a mensajes que indican el estado de las llamadas o los mensajes.</span><span class="sxs-lookup"><span data-stu-id="269cc-106">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="269cc-107">Columna</span><span class="sxs-lookup"><span data-stu-id="269cc-107">Column</span></span></th>
<th><span data-ttu-id="269cc-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="269cc-108">Data Type</span></span></th>
<th><span data-ttu-id="269cc-109">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="269cc-109">Key/Index</span></span></th>
<th><span data-ttu-id="269cc-110">Detalles</span><span class="sxs-lookup"><span data-stu-id="269cc-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="269cc-111"><strong>Campos errortime</strong></span><span class="sxs-lookup"><span data-stu-id="269cc-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="269cc-112">datetime</span><span class="sxs-lookup"><span data-stu-id="269cc-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="269cc-113">Principal, Externa</span><span class="sxs-lookup"><span data-stu-id="269cc-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="269cc-114">Fecha y hora del informe de errores de progreso que contiene este informe de progreso.</span><span class="sxs-lookup"><span data-stu-id="269cc-114">Date and time of the progress error report that contains this progress report.</span></span> <span data-ttu-id="269cc-115">Consulte la <a href="lync-server-2013-errorreport-table.md">tabla errorreport en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="269cc-115">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="269cc-116"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="269cc-116"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="269cc-117">int</span><span class="sxs-lookup"><span data-stu-id="269cc-117">int</span></span></p></td>
<td><p><span data-ttu-id="269cc-118">Principal, Externa</span><span class="sxs-lookup"><span data-stu-id="269cc-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="269cc-119">Número de identificación usado junto con ErrorTime, ProgressReportSeq para identificar de manera única un informe de progreso.</span><span class="sxs-lookup"><span data-stu-id="269cc-119">ID number used in conjunction with ErrorTime, ProgressReportSeq to uniquely identify a progress report.</span></span> <span data-ttu-id="269cc-120">Consulte la <a href="lync-server-2013-errorreport-table.md">tabla errorreport en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="269cc-120">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="269cc-121"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="269cc-121"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="269cc-122">int</span><span class="sxs-lookup"><span data-stu-id="269cc-122">int</span></span></p></td>
<td><p><span data-ttu-id="269cc-123">Principal, Exterior</span><span class="sxs-lookup"><span data-stu-id="269cc-123">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="269cc-124">Número de id. que identifica el informe de errores.</span><span class="sxs-lookup"><span data-stu-id="269cc-124">ID number that identifies the error report.</span></span> <span data-ttu-id="269cc-125">ErrorReporSeq se usa junto con ErrorTime para identificar de manera única un informe de errores.</span><span class="sxs-lookup"><span data-stu-id="269cc-125">ErrorReporSeq is used in conjunction with ErrorTime to uniquely identify an error report.</span></span> <span data-ttu-id="269cc-126">Consulte la <a href="lync-server-2013-errorreport-table.md">tabla errorreport en Lync Server 2013</a> para obtener más información</span><span class="sxs-lookup"><span data-stu-id="269cc-126">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information</span></span></p>
<p><span data-ttu-id="269cc-127">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="269cc-127">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="269cc-128"><strong>ProgressReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="269cc-128"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="269cc-129">int</span><span class="sxs-lookup"><span data-stu-id="269cc-129">int</span></span></p></td>
<td><p><span data-ttu-id="269cc-130">Principal</span><span class="sxs-lookup"><span data-stu-id="269cc-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="269cc-p105">Número de identificación usado para identificar el informe de progreso. Se utiliza junto con ErrorTime y ErrorReportSeq para identificar de manera única un informe de progreso.</span><span class="sxs-lookup"><span data-stu-id="269cc-p105">ID number to identify the progress report. Used in conjunction with ErrorTime and ErrorReportSeq to uniquely identify a progress report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="269cc-133"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="269cc-133"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="269cc-134">int</span><span class="sxs-lookup"><span data-stu-id="269cc-134">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="269cc-135">Id. de diagnóstico del informe de progreso.</span><span class="sxs-lookup"><span data-stu-id="269cc-135">Diagnostic ID of the progress report.</span></span></p>
<p><span data-ttu-id="269cc-136">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="269cc-136">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="269cc-137"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="269cc-137"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="269cc-138">int</span><span class="sxs-lookup"><span data-stu-id="269cc-138">int</span></span></p></td>
<td><p><span data-ttu-id="269cc-139">Externa</span><span class="sxs-lookup"><span data-stu-id="269cc-139">Foreign</span></span></p></td>
<td><p><span data-ttu-id="269cc-140">Servidor que ha enviado el informe de errores (si el informe se envió desde un componente de servidor).</span><span class="sxs-lookup"><span data-stu-id="269cc-140">Server that sent the error report (if the report was sent from a server component).</span></span> <span data-ttu-id="269cc-141">Consulte la <a href="lync-server-2013-servers-table.md">tabla servidores en Lync Server 2013</a> para obtener más información. Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="269cc-141">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="269cc-142"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="269cc-142"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="269cc-143">int</span><span class="sxs-lookup"><span data-stu-id="269cc-143">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="269cc-p107">El proceso de Lync Server al que se refiere el informe. Vea la tabla de aplicaciones para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="269cc-p107">The Lync Server process that the report is about. See the Application Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="269cc-146"><strong>Detalle</strong></span><span class="sxs-lookup"><span data-stu-id="269cc-146"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="269cc-147">imagen</span><span class="sxs-lookup"><span data-stu-id="269cc-147">image</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="269cc-148">Detalles del informe de progreso, almacenados en formato binario para ahorrar espacio. Estos datos pueden convertirse en formato de texto usando esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="269cc-148">Progress report details, stored in binary format to save space.This data can be converted to text format using this syntax:</span></span></p>
<p><span data-ttu-id="269cc-149">cast(cast(Detail as varbinary(max)) as varchar(max))</span><span class="sxs-lookup"><span data-stu-id="269cc-149">cast(cast(Detail as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="269cc-150"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="269cc-150"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="269cc-151">Identificador</span><span class="sxs-lookup"><span data-stu-id="269cc-151">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="269cc-152">Identificador único que correlaciona información de hora de conexión para los diferentes componentes que participan en una conferencia.</span><span class="sxs-lookup"><span data-stu-id="269cc-152">Unique identifier that correlates join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="269cc-153">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="269cc-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="269cc-154"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="269cc-154"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="269cc-155">int</span><span class="sxs-lookup"><span data-stu-id="269cc-155">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="269cc-156">Tiempo (en milisegundos) para que un componente específico se una a una conferencia.</span><span class="sxs-lookup"><span data-stu-id="269cc-156">Time (in milliseconds) for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="269cc-157">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="269cc-157">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

