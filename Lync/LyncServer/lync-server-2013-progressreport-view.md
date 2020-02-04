---
title: 'Lync Server 2013: vista ProgressReport'
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
ms.openlocfilehash: 4fa8d73981490503b26b77b79be6f42aab77703e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747250"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-view-in-lync-server-2013"></a><span data-ttu-id="4a6eb-102">Vista ProgressReport en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a6eb-102">ProgressReport view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a6eb-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="4a6eb-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="4a6eb-104">La vista ProgressReport almacena información sobre las sesiones completadas.</span><span class="sxs-lookup"><span data-stu-id="4a6eb-104">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="4a6eb-105">Los informes de progreso solo se escribirán para las llamadas y las sesiones que la 2013 determina Lync Server puede resultar útil para propósitos de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="4a6eb-105">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="4a6eb-106">Esta vista se presentó en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4a6eb-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4a6eb-107">Los campos ErrorTime, ErrorReportSeq y ProgressReportSeq no hacen referencia a errores sino a mensajes que indican el estado de las llamadas o los mensajes.</span><span class="sxs-lookup"><span data-stu-id="4a6eb-107">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4a6eb-108">Columna</span><span class="sxs-lookup"><span data-stu-id="4a6eb-108">Column</span></span></th>
<th><span data-ttu-id="4a6eb-109">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="4a6eb-109">Data Type</span></span></th>
<th><span data-ttu-id="4a6eb-110">Detalles</span><span class="sxs-lookup"><span data-stu-id="4a6eb-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4a6eb-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="4a6eb-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4a6eb-112">datetime</span><span class="sxs-lookup"><span data-stu-id="4a6eb-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="4a6eb-113">Hora de error.</span><span class="sxs-lookup"><span data-stu-id="4a6eb-113">Time of error occurred.</span></span> <span data-ttu-id="4a6eb-114">Se usa junto con ErrorReportSeq para identificar de forma única un error.</span><span class="sxs-lookup"><span data-stu-id="4a6eb-114">Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a6eb-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="4a6eb-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="4a6eb-116">int</span><span class="sxs-lookup"><span data-stu-id="4a6eb-116">int</span></span></p></td>
<td><p><span data-ttu-id="4a6eb-117">Número de identificación para identificar el error.</span><span class="sxs-lookup"><span data-stu-id="4a6eb-117">ID number to identify the error.</span></span> <span data-ttu-id="4a6eb-118">Se usa junto con ErrorTime para identificar de forma única un error.</span><span class="sxs-lookup"><span data-stu-id="4a6eb-118">Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a6eb-119"><strong>ProgressReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="4a6eb-119"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="4a6eb-120">int</span><span class="sxs-lookup"><span data-stu-id="4a6eb-120">int</span></span></p></td>
<td><p><span data-ttu-id="4a6eb-121">IDENTIFICADOR para identificar el informe de progreso.</span><span class="sxs-lookup"><span data-stu-id="4a6eb-121">ID to identify the progress report.</span></span> <span data-ttu-id="4a6eb-122">Se usa para distinguir los informes de progreso del mismo informe de errores.</span><span class="sxs-lookup"><span data-stu-id="4a6eb-122">Used to distinguish progress reports of the same error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a6eb-123"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="4a6eb-123"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="4a6eb-124">int</span><span class="sxs-lookup"><span data-stu-id="4a6eb-124">int</span></span></p></td>
<td><p><span data-ttu-id="4a6eb-125">IDENTIFICADOR de diagnóstico del informe de errores.</span><span class="sxs-lookup"><span data-stu-id="4a6eb-125">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a6eb-126"><strong>Origen</strong></span><span class="sxs-lookup"><span data-stu-id="4a6eb-126"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="4a6eb-127">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="4a6eb-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4a6eb-128">Nombre del servidor que originó el error (si el informe fue enviado desde un componente de servidor).</span><span class="sxs-lookup"><span data-stu-id="4a6eb-128">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a6eb-129"><strong>Aplicación</strong></span><span class="sxs-lookup"><span data-stu-id="4a6eb-129"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="4a6eb-130">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="4a6eb-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4a6eb-131">Nombre de la aplicación que originó el error (si el informe fue enviado desde un componente de servidor).</span><span class="sxs-lookup"><span data-stu-id="4a6eb-131">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a6eb-132"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="4a6eb-132"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="4a6eb-133">identificador</span><span class="sxs-lookup"><span data-stu-id="4a6eb-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="4a6eb-134">Identificador único que correlaciona información de tiempo de Unión para los distintos componentes implicados en una conferencia.</span><span class="sxs-lookup"><span data-stu-id="4a6eb-134">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a6eb-135"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="4a6eb-135"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4a6eb-136">int</span><span class="sxs-lookup"><span data-stu-id="4a6eb-136">int</span></span></p></td>
<td><p><span data-ttu-id="4a6eb-137">Tiempo (en milisegundos) necesario para que un componente específico se una a una conferencia.</span><span class="sxs-lookup"><span data-stu-id="4a6eb-137">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a6eb-138"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="4a6eb-138"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="4a6eb-139">VARCHAR (Max)</span><span class="sxs-lookup"><span data-stu-id="4a6eb-139">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="4a6eb-140">Información de error adicional.</span><span class="sxs-lookup"><span data-stu-id="4a6eb-140">Additional error information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

