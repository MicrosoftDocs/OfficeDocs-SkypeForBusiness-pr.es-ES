---
title: 'Lync Server 2013: Tabla ProgressReport'
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
ms.openlocfilehash: 2e1cb7c8e764097af96981220ee74d481b379341
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724820"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-table-in-lync-server-2013"></a><span data-ttu-id="f0c69-102">Tabla ProgressReport en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0c69-102">ProgressReport table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0c69-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="f0c69-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="f0c69-104">Los informes de progreso se basan en los datos cargados por el cliente en la base de datos después de completarse una llamada o sesión.</span><span class="sxs-lookup"><span data-stu-id="f0c69-104">Progress reports are based on data uploaded by the client to the database after a call or session is completed.</span></span> <span data-ttu-id="f0c69-105">Los informes de progreso solo se escribirán para las llamadas y las sesiones que la 2013 determina Lync Server puede resultar útil para propósitos de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="f0c69-105">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span>

<span data-ttu-id="f0c69-106">Los campos ErrorTime, ErrorReportSeq y ProgressReportSeq no hacen referencia a errores sino a mensajes que indican el estado de las llamadas o los mensajes.</span><span class="sxs-lookup"><span data-stu-id="f0c69-106">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f0c69-107">Columna</span><span class="sxs-lookup"><span data-stu-id="f0c69-107">Column</span></span></th>
<th><span data-ttu-id="f0c69-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="f0c69-108">Data Type</span></span></th>
<th><span data-ttu-id="f0c69-109">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="f0c69-109">Key/Index</span></span></th>
<th><span data-ttu-id="f0c69-110">Detalles</span><span class="sxs-lookup"><span data-stu-id="f0c69-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f0c69-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="f0c69-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f0c69-112">datetime</span><span class="sxs-lookup"><span data-stu-id="f0c69-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="f0c69-113">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="f0c69-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="f0c69-114">Fecha y hora del informe de errores de progreso que contiene este informe de progreso.</span><span class="sxs-lookup"><span data-stu-id="f0c69-114">Date and time of the progress error report that contains this progress report.</span></span> <span data-ttu-id="f0c69-115">Para obtener más información, consulte la <a href="lync-server-2013-errorreport-table.md">tabla errorreport en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f0c69-115">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0c69-116"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="f0c69-116"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="f0c69-117">int</span><span class="sxs-lookup"><span data-stu-id="f0c69-117">int</span></span></p></td>
<td><p><span data-ttu-id="f0c69-118">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="f0c69-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="f0c69-119">Número de identificación usado en conjunción con ErrorTime, ProgressReportSeq para identificar de manera exclusiva un informe de progreso.</span><span class="sxs-lookup"><span data-stu-id="f0c69-119">ID number used in conjunction with ErrorTime, ProgressReportSeq to uniquely identify a progress report.</span></span> <span data-ttu-id="f0c69-120">Para obtener más información, consulte la <a href="lync-server-2013-errorreport-table.md">tabla errorreport en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f0c69-120">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0c69-121"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f0c69-121"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f0c69-122">int</span><span class="sxs-lookup"><span data-stu-id="f0c69-122">int</span></span></p></td>
<td><p><span data-ttu-id="f0c69-123">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="f0c69-123">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="f0c69-124">Número de identificación que identifica el informe de errores.</span><span class="sxs-lookup"><span data-stu-id="f0c69-124">ID number that identifies the error report.</span></span> <span data-ttu-id="f0c69-125">ErrorReporSeq se usa junto con ErrorTime para identificar de forma exclusiva un informe de errores.</span><span class="sxs-lookup"><span data-stu-id="f0c69-125">ErrorReporSeq is used in conjunction with ErrorTime to uniquely identify an error report.</span></span> <span data-ttu-id="f0c69-126">Para obtener más información, consulte la <a href="lync-server-2013-errorreport-table.md">tabla errorreport en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0c69-126">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information</span></span></p>
<p><span data-ttu-id="f0c69-127">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0c69-127">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0c69-128"><strong>ProgressReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f0c69-128"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f0c69-129">int</span><span class="sxs-lookup"><span data-stu-id="f0c69-129">int</span></span></p></td>
<td><p><span data-ttu-id="f0c69-130">Primary</span><span class="sxs-lookup"><span data-stu-id="f0c69-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="f0c69-131">Número de identificación para identificar el informe de progreso.</span><span class="sxs-lookup"><span data-stu-id="f0c69-131">ID number to identify the progress report.</span></span> <span data-ttu-id="f0c69-132">Se usa junto con ErrorTime y ErrorReportSeq para identificar de manera única un informe de progreso.</span><span class="sxs-lookup"><span data-stu-id="f0c69-132">Used in conjunction with ErrorTime and ErrorReportSeq to uniquely identify a progress report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0c69-133"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="f0c69-133"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="f0c69-134">int</span><span class="sxs-lookup"><span data-stu-id="f0c69-134">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0c69-135">IDENTIFICADOR de diagnóstico del informe de progreso.</span><span class="sxs-lookup"><span data-stu-id="f0c69-135">Diagnostic ID of the progress report.</span></span></p>
<p><span data-ttu-id="f0c69-136">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0c69-136">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0c69-137"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="f0c69-137"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="f0c69-138">int</span><span class="sxs-lookup"><span data-stu-id="f0c69-138">int</span></span></p></td>
<td><p><span data-ttu-id="f0c69-139">Extranjero</span><span class="sxs-lookup"><span data-stu-id="f0c69-139">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f0c69-140">Servidor que ha enviado el informe de errores (si el informe se envió desde un componente de servidor).</span><span class="sxs-lookup"><span data-stu-id="f0c69-140">Server that sent the error report (if the report was sent from a server component).</span></span> <span data-ttu-id="f0c69-141">Para obtener más información, consulte la <a href="lync-server-2013-servers-table.md">tabla servidores en Lync Server 2013</a> . Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0c69-141">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0c69-142"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="f0c69-142"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="f0c69-143">int</span><span class="sxs-lookup"><span data-stu-id="f0c69-143">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0c69-144">El proceso de Lync Server sobre el que se encuentra el informe.</span><span class="sxs-lookup"><span data-stu-id="f0c69-144">The Lync Server process that the report is about.</span></span> <span data-ttu-id="f0c69-145">Para obtener más información, consulte la tabla de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f0c69-145">See the Application Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0c69-146"><strong>Detalle</strong></span><span class="sxs-lookup"><span data-stu-id="f0c69-146"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="f0c69-147">imagen</span><span class="sxs-lookup"><span data-stu-id="f0c69-147">image</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0c69-148">Detalles del informe de progreso, almacenado en formato binario, para ahorrar espacio. Estos datos se pueden convertir a formato de texto con esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="f0c69-148">Progress report details, stored in binary format to save space.This data can be converted to text format using this syntax:</span></span></p>
<p><span data-ttu-id="f0c69-149">CAST (detallar como varbinary (Max)) como varchar (Max))</span><span class="sxs-lookup"><span data-stu-id="f0c69-149">cast(cast(Detail as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0c69-150"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="f0c69-150"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="f0c69-151">Identificador</span><span class="sxs-lookup"><span data-stu-id="f0c69-151">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0c69-152">Identificador único que correlaciona la información de tiempo de Unión para los distintos componentes implicados en una conferencia.</span><span class="sxs-lookup"><span data-stu-id="f0c69-152">Unique identifier that correlates join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="f0c69-153">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0c69-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0c69-154"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="f0c69-154"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f0c69-155">int</span><span class="sxs-lookup"><span data-stu-id="f0c69-155">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0c69-156">Tiempo (en milisegundos) para que un componente específico se una a una conferencia.</span><span class="sxs-lookup"><span data-stu-id="f0c69-156">Time (in milliseconds) for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="f0c69-157">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0c69-157">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

