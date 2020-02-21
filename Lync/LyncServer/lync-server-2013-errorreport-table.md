---
title: 'Lync Server 2013: tabla ErrorReport'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorReport table
ms:assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412826(v=OCS.15)
ms:contentKeyID: 48185129
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fad1f4138f1fae95f4e3d2ea88c8a8c72f7198a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213836"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="errorreport-table-in-lync-server-2013"></a><span data-ttu-id="78250-102">Tabla ErrorReport en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78250-102">ErrorReport table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78250-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="78250-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="78250-104">La tabla ErrorReport almacena información sobre los errores que se han producido.</span><span class="sxs-lookup"><span data-stu-id="78250-104">The ErrorReport table stores information about errors that have occurred.</span></span> <span data-ttu-id="78250-105">Cada registro representa la aparición de un error.</span><span class="sxs-lookup"><span data-stu-id="78250-105">Each record is one error occurrence.</span></span> <span data-ttu-id="78250-106">Los errores se capturan con el agente del CDR que se ejecuta en el servidor front-end o los envía el cliente.</span><span class="sxs-lookup"><span data-stu-id="78250-106">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="78250-107">Columna</span><span class="sxs-lookup"><span data-stu-id="78250-107">Column</span></span></th>
<th><span data-ttu-id="78250-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="78250-108">Data Type</span></span></th>
<th><span data-ttu-id="78250-109">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="78250-109">Key/Index</span></span></th>
<th><span data-ttu-id="78250-110">Detalles</span><span class="sxs-lookup"><span data-stu-id="78250-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="78250-111"><strong>Campos errortime</strong></span><span class="sxs-lookup"><span data-stu-id="78250-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="78250-112">datetime</span><span class="sxs-lookup"><span data-stu-id="78250-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="78250-113">Principal</span><span class="sxs-lookup"><span data-stu-id="78250-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="78250-114">Fecha y hora en que se produjo el error.</span><span class="sxs-lookup"><span data-stu-id="78250-114">Date and time the error occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78250-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="78250-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="78250-116">int</span><span class="sxs-lookup"><span data-stu-id="78250-116">int</span></span></p></td>
<td><p><span data-ttu-id="78250-117">Principal</span><span class="sxs-lookup"><span data-stu-id="78250-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="78250-118">Número de identificador para identificar el informe de errores.</span><span class="sxs-lookup"><span data-stu-id="78250-118">ID number to identify the error report.</span></span> <span data-ttu-id="78250-119">Se usa junto con <strong>campos errortime</strong> para identificar de forma exclusiva un informe de errores.</span><span class="sxs-lookup"><span data-stu-id="78250-119">Used in conjunction with <strong>ErrorTime</strong> to uniquely identify an error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78250-120"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="78250-120"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="78250-121">int</span><span class="sxs-lookup"><span data-stu-id="78250-121">int</span></span></p></td>
<td><p><span data-ttu-id="78250-122">Externa</span><span class="sxs-lookup"><span data-stu-id="78250-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="78250-123">IDENTIFICADOR único del tipo de error.</span><span class="sxs-lookup"><span data-stu-id="78250-123">Unique ID of the error type.</span></span> <span data-ttu-id="78250-124">Consulte la <a href="lync-server-2013-errordef-table.md">tabla ErrorDef en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="78250-124">See the <a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78250-125"><strong>FromUserId</strong></span><span class="sxs-lookup"><span data-stu-id="78250-125"><strong>FromUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="78250-126">int</span><span class="sxs-lookup"><span data-stu-id="78250-126">int</span></span></p></td>
<td><p><span data-ttu-id="78250-127">Externa</span><span class="sxs-lookup"><span data-stu-id="78250-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="78250-128">Usuario que originó la solicitud que causó el error.</span><span class="sxs-lookup"><span data-stu-id="78250-128">User who originated the request that caused the error.</span></span> <span data-ttu-id="78250-129">Consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="78250-129">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78250-130"><strong>ToUserId</strong></span><span class="sxs-lookup"><span data-stu-id="78250-130"><strong>ToUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="78250-131">int</span><span class="sxs-lookup"><span data-stu-id="78250-131">int</span></span></p></td>
<td><p><span data-ttu-id="78250-132">Externa</span><span class="sxs-lookup"><span data-stu-id="78250-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="78250-133">Usuario de destino de la solicitud que provocó el error.</span><span class="sxs-lookup"><span data-stu-id="78250-133">Destination user for the request that caused the error.</span></span> <span data-ttu-id="78250-134">Consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="78250-134">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78250-135"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="78250-135"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="78250-136">int</span><span class="sxs-lookup"><span data-stu-id="78250-136">int</span></span></p></td>
<td><p><span data-ttu-id="78250-137">Externa</span><span class="sxs-lookup"><span data-stu-id="78250-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="78250-138">URI de conferencia relacionado con el error.</span><span class="sxs-lookup"><span data-stu-id="78250-138">Conference URI related to the error.</span></span> <span data-ttu-id="78250-139">Consulte la <a href="lync-server-2013-conferenceuris-table.md">tabla ConferenceUris en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="78250-139">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="78250-140">Normalmente, si ConferenceUriId no es null, entonces FromUserId o ToUserId será null.</span><span class="sxs-lookup"><span data-stu-id="78250-140">Typically, if ConferenceUriId is not null, then either FromUserId or ToUserId will be null.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78250-141"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="78250-141"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="78250-142">datetime</span><span class="sxs-lookup"><span data-stu-id="78250-142">datetime</span></span></p></td>
<td><p><span data-ttu-id="78250-143">Externa</span><span class="sxs-lookup"><span data-stu-id="78250-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="78250-144">Se usa junto con <strong>SessionIdSeq</strong> para identificar una sesión de manera exclusiva.</span><span class="sxs-lookup"><span data-stu-id="78250-144">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="78250-145">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="78250-145">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78250-146"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="78250-146"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="78250-147">int</span><span class="sxs-lookup"><span data-stu-id="78250-147">int</span></span></p></td>
<td><p><span data-ttu-id="78250-148">Externa</span><span class="sxs-lookup"><span data-stu-id="78250-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="78250-149">Número con el que se identifica la sesión.</span><span class="sxs-lookup"><span data-stu-id="78250-149">ID number to identify the session.</span></span> <span data-ttu-id="78250-150">Se usa en combinación con <strong>SessionIdTime</strong> para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="78250-150">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="78250-151">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="78250-151">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78250-152"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="78250-152"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="78250-153">int</span><span class="sxs-lookup"><span data-stu-id="78250-153">int</span></span></p></td>
<td><p><span data-ttu-id="78250-154">Externa</span><span class="sxs-lookup"><span data-stu-id="78250-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="78250-155">Servidor que ha enviado el informe de errores (si el informe se está enviando desde un componente de servidor).</span><span class="sxs-lookup"><span data-stu-id="78250-155">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="78250-156">Consulte la <a href="lync-server-2013-servers-table.md">tabla servidores en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="78250-156">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="78250-157">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="78250-157">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78250-158"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="78250-158"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="78250-159">int</span><span class="sxs-lookup"><span data-stu-id="78250-159">int</span></span></p></td>
<td><p><span data-ttu-id="78250-160">Externa</span><span class="sxs-lookup"><span data-stu-id="78250-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="78250-161">Servidor que ha enviado el informe de errores (si el informe se está enviando desde un componente de servidor).</span><span class="sxs-lookup"><span data-stu-id="78250-161">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="78250-162">Consulte la <a href="lync-server-2013-application-table.md">tabla de la aplicación en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="78250-162">See the <a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="78250-163">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="78250-163">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78250-164"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="78250-164"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="78250-165">imagen</span><span class="sxs-lookup"><span data-stu-id="78250-165">image</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="78250-166">Más información sobre el error.</span><span class="sxs-lookup"><span data-stu-id="78250-166">More information about the error.</span></span></p>
<p><span data-ttu-id="78250-167">Estos datos pueden convertirse en formato de texto con esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="78250-167">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78250-168"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="78250-168"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="78250-169">int</span><span class="sxs-lookup"><span data-stu-id="78250-169">int</span></span></p></td>
<td><p><span data-ttu-id="78250-170">Externa</span><span class="sxs-lookup"><span data-stu-id="78250-170">Foreign</span></span></p></td>
<td><p><span data-ttu-id="78250-171">La versión de cliente del extremo que envía el informe de errores.</span><span class="sxs-lookup"><span data-stu-id="78250-171">The client version of endpoint that sends the error report.</span></span> <span data-ttu-id="78250-172">Consulte la <a href="lync-server-2013-clientversions-table.md">tabla ClientVersions en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="78250-172">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78250-173"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="78250-173"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="78250-174">bit</span><span class="sxs-lookup"><span data-stu-id="78250-174">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="78250-175">Es el informe de errores capturado por el agente CDR que se ejecuta en el servidor front-end o enviado por el cliente.</span><span class="sxs-lookup"><span data-stu-id="78250-175">Is the error report captured by the CDR agent running on the front-end server, or sent by the client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78250-176"><strong>Flag</strong></span><span class="sxs-lookup"><span data-stu-id="78250-176"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="78250-177">smallint</span><span class="sxs-lookup"><span data-stu-id="78250-177">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="78250-178">Reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="78250-178">Reserved for future use.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78250-179"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="78250-179"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="78250-180">Identificador</span><span class="sxs-lookup"><span data-stu-id="78250-180">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="78250-181">Identificador único que correlaciona la información de la hora de unión de los componentes que participan en una conferencia.</span><span class="sxs-lookup"><span data-stu-id="78250-181">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="78250-182">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="78250-182">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78250-183"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="78250-183"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="78250-184">int</span><span class="sxs-lookup"><span data-stu-id="78250-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="78250-185">Tiempo (en milisegundos) que necesita un componente determinado para unirse a una conferencia.</span><span class="sxs-lookup"><span data-stu-id="78250-185">Time (in milliseconds) required for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="78250-186">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="78250-186">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78250-187"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="78250-187"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="78250-188">int</span><span class="sxs-lookup"><span data-stu-id="78250-188">int</span></span></p></td>
<td><p><span data-ttu-id="78250-189">Externa</span><span class="sxs-lookup"><span data-stu-id="78250-189">Foreign</span></span></p></td>
<td><p><span data-ttu-id="78250-190">Representa el nombre de dominio completo del servidor que generó el informe de errores.</span><span class="sxs-lookup"><span data-stu-id="78250-190">Represents the fully qualified domain name of the server that generated the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78250-191"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="78250-191"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="78250-192">int</span><span class="sxs-lookup"><span data-stu-id="78250-192">int</span></span></p></td>
<td><p><span data-ttu-id="78250-193">Externa</span><span class="sxs-lookup"><span data-stu-id="78250-193">Foreign</span></span></p></td>
<td><p><span data-ttu-id="78250-194">Representa el nombre de dominio completo del grupo en el que se generó el informe de errores.</span><span class="sxs-lookup"><span data-stu-id="78250-194">Represents the fully qualified domain name of the pool where the error report was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

