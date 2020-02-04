---
title: 'Lync Server 2013: Tabla ErrorReport'
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
ms.openlocfilehash: 8de4163f94d5848808c5b01c34b1676d3a0bbcff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735390"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorreport-table-in-lync-server-2013"></a><span data-ttu-id="9ef95-102">Tabla ErrorReport en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9ef95-102">ErrorReport table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ef95-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="9ef95-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="9ef95-104">La tabla ErrorReport almacena información sobre los errores que se han producido.</span><span class="sxs-lookup"><span data-stu-id="9ef95-104">The ErrorReport table stores information about errors that have occurred.</span></span> <span data-ttu-id="9ef95-105">Cada registro es una aparición de error.</span><span class="sxs-lookup"><span data-stu-id="9ef95-105">Each record is one error occurrence.</span></span> <span data-ttu-id="9ef95-106">Los errores se capturan mediante el agente CDR que se ejecuta en el servidor front-end o se envían desde el cliente.</span><span class="sxs-lookup"><span data-stu-id="9ef95-106">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9ef95-107">Columna</span><span class="sxs-lookup"><span data-stu-id="9ef95-107">Column</span></span></th>
<th><span data-ttu-id="9ef95-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="9ef95-108">Data Type</span></span></th>
<th><span data-ttu-id="9ef95-109">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="9ef95-109">Key/Index</span></span></th>
<th><span data-ttu-id="9ef95-110">Detalles</span><span class="sxs-lookup"><span data-stu-id="9ef95-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ef95-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="9ef95-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef95-112">datetime</span><span class="sxs-lookup"><span data-stu-id="9ef95-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="9ef95-113">Primary</span><span class="sxs-lookup"><span data-stu-id="9ef95-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="9ef95-114">Fecha y hora en que se produjo el error.</span><span class="sxs-lookup"><span data-stu-id="9ef95-114">Date and time the error occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ef95-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="9ef95-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef95-116">int</span><span class="sxs-lookup"><span data-stu-id="9ef95-116">int</span></span></p></td>
<td><p><span data-ttu-id="9ef95-117">Primary</span><span class="sxs-lookup"><span data-stu-id="9ef95-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="9ef95-118">Número de identificación para identificar el informe de errores.</span><span class="sxs-lookup"><span data-stu-id="9ef95-118">ID number to identify the error report.</span></span> <span data-ttu-id="9ef95-119">Se usa en conjunción con <strong>ErrorTime</strong> para identificar de manera exclusiva un informe de errores.</span><span class="sxs-lookup"><span data-stu-id="9ef95-119">Used in conjunction with <strong>ErrorTime</strong> to uniquely identify an error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ef95-120"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="9ef95-120"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef95-121">int</span><span class="sxs-lookup"><span data-stu-id="9ef95-121">int</span></span></p></td>
<td><p><span data-ttu-id="9ef95-122">Extranjero</span><span class="sxs-lookup"><span data-stu-id="9ef95-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9ef95-123">IDENTIFICADOR único del tipo de error.</span><span class="sxs-lookup"><span data-stu-id="9ef95-123">Unique ID of the error type.</span></span> <span data-ttu-id="9ef95-124">Para obtener más información, consulte la <a href="lync-server-2013-errordef-table.md">tabla ErrorDef en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9ef95-124">See the <a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ef95-125"><strong>FromUserId</strong></span><span class="sxs-lookup"><span data-stu-id="9ef95-125"><strong>FromUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef95-126">int</span><span class="sxs-lookup"><span data-stu-id="9ef95-126">int</span></span></p></td>
<td><p><span data-ttu-id="9ef95-127">Extranjero</span><span class="sxs-lookup"><span data-stu-id="9ef95-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9ef95-128">Usuario que originó la solicitud que causó el error.</span><span class="sxs-lookup"><span data-stu-id="9ef95-128">User who originated the request that caused the error.</span></span> <span data-ttu-id="9ef95-129">Para obtener más información, consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9ef95-129">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ef95-130"><strong>ToUserId</strong></span><span class="sxs-lookup"><span data-stu-id="9ef95-130"><strong>ToUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef95-131">int</span><span class="sxs-lookup"><span data-stu-id="9ef95-131">int</span></span></p></td>
<td><p><span data-ttu-id="9ef95-132">Extranjero</span><span class="sxs-lookup"><span data-stu-id="9ef95-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9ef95-133">Usuario de destino de la solicitud que causó el error.</span><span class="sxs-lookup"><span data-stu-id="9ef95-133">Destination user for the request that caused the error.</span></span> <span data-ttu-id="9ef95-134">Para obtener más información, consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9ef95-134">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ef95-135"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="9ef95-135"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef95-136">int</span><span class="sxs-lookup"><span data-stu-id="9ef95-136">int</span></span></p></td>
<td><p><span data-ttu-id="9ef95-137">Extranjero</span><span class="sxs-lookup"><span data-stu-id="9ef95-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9ef95-138">URI de conferencia relacionado con el error.</span><span class="sxs-lookup"><span data-stu-id="9ef95-138">Conference URI related to the error.</span></span> <span data-ttu-id="9ef95-139">Para obtener más información, consulte la <a href="lync-server-2013-conferenceuris-table.md">tabla ConferenceUris en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9ef95-139">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="9ef95-140">Normalmente, si ConferenceUriId no es null, FromUserId o ToUserId será null.</span><span class="sxs-lookup"><span data-stu-id="9ef95-140">Typically, if ConferenceUriId is not null, then either FromUserId or ToUserId will be null.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ef95-141"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="9ef95-141"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef95-142">datetime</span><span class="sxs-lookup"><span data-stu-id="9ef95-142">datetime</span></span></p></td>
<td><p><span data-ttu-id="9ef95-143">Extranjero</span><span class="sxs-lookup"><span data-stu-id="9ef95-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9ef95-144">Se usa en conjunción con <strong>SessionIdSeq</strong> para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="9ef95-144">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="9ef95-145">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9ef95-145">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ef95-146"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="9ef95-146"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef95-147">int</span><span class="sxs-lookup"><span data-stu-id="9ef95-147">int</span></span></p></td>
<td><p><span data-ttu-id="9ef95-148">Extranjero</span><span class="sxs-lookup"><span data-stu-id="9ef95-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9ef95-149">Número de identificación para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="9ef95-149">ID number to identify the session.</span></span> <span data-ttu-id="9ef95-150">Se usa en conjunción con <strong>SessionIdTime</strong> para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="9ef95-150">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="9ef95-151">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9ef95-151">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ef95-152"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="9ef95-152"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef95-153">int</span><span class="sxs-lookup"><span data-stu-id="9ef95-153">int</span></span></p></td>
<td><p><span data-ttu-id="9ef95-154">Extranjero</span><span class="sxs-lookup"><span data-stu-id="9ef95-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9ef95-155">Servidor que ha enviado el informe de errores (si el informe se está enviando desde un componente de servidor).</span><span class="sxs-lookup"><span data-stu-id="9ef95-155">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="9ef95-156">Para obtener más información, consulte la <a href="lync-server-2013-servers-table.md">tabla servidores en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9ef95-156">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="9ef95-157">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9ef95-157">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ef95-158"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="9ef95-158"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef95-159">int</span><span class="sxs-lookup"><span data-stu-id="9ef95-159">int</span></span></p></td>
<td><p><span data-ttu-id="9ef95-160">Extranjero</span><span class="sxs-lookup"><span data-stu-id="9ef95-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9ef95-161">Servidor que ha enviado el informe de errores (si el informe se está enviando desde un componente de servidor).</span><span class="sxs-lookup"><span data-stu-id="9ef95-161">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="9ef95-162">Para obtener más información, consulte la <a href="lync-server-2013-application-table.md">tabla de aplicaciones en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9ef95-162">See the <a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="9ef95-163">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9ef95-163">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ef95-164"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="9ef95-164"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef95-165">imagen</span><span class="sxs-lookup"><span data-stu-id="9ef95-165">image</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9ef95-166">Más información sobre el error.</span><span class="sxs-lookup"><span data-stu-id="9ef95-166">More information about the error.</span></span></p>
<p><span data-ttu-id="9ef95-167">Estos datos se pueden convertir a formato de texto con esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="9ef95-167">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ef95-168"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="9ef95-168"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef95-169">int</span><span class="sxs-lookup"><span data-stu-id="9ef95-169">int</span></span></p></td>
<td><p><span data-ttu-id="9ef95-170">Extranjero</span><span class="sxs-lookup"><span data-stu-id="9ef95-170">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9ef95-171">La versión de cliente del extremo que envía el informe de errores.</span><span class="sxs-lookup"><span data-stu-id="9ef95-171">The client version of endpoint that sends the error report.</span></span> <span data-ttu-id="9ef95-172">Para obtener más información, consulte la <a href="lync-server-2013-clientversions-table.md">tabla ClientVersions en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9ef95-172">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ef95-173"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="9ef95-173"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef95-174">bit</span><span class="sxs-lookup"><span data-stu-id="9ef95-174">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9ef95-175">Es el informe de errores capturado por el agente CDR que se ejecuta en el servidor front-end o enviado por el cliente.</span><span class="sxs-lookup"><span data-stu-id="9ef95-175">Is the error report captured by the CDR agent running on the front-end server, or sent by the client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ef95-176"><strong>Fdisableautoindexingonschemaupdate</strong></span><span class="sxs-lookup"><span data-stu-id="9ef95-176"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef95-177">smallint</span><span class="sxs-lookup"><span data-stu-id="9ef95-177">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9ef95-178">Reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="9ef95-178">Reserved for future use.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ef95-179"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="9ef95-179"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef95-180">Identificador</span><span class="sxs-lookup"><span data-stu-id="9ef95-180">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9ef95-181">Identificador único que correlaciona información de tiempo de Unión para los distintos componentes implicados en una conferencia.</span><span class="sxs-lookup"><span data-stu-id="9ef95-181">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="9ef95-182">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9ef95-182">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ef95-183"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="9ef95-183"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef95-184">int</span><span class="sxs-lookup"><span data-stu-id="9ef95-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9ef95-185">Tiempo (en milisegundos) necesario para que un componente específico se una a una conferencia.</span><span class="sxs-lookup"><span data-stu-id="9ef95-185">Time (in milliseconds) required for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="9ef95-186">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9ef95-186">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ef95-187"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="9ef95-187"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef95-188">int</span><span class="sxs-lookup"><span data-stu-id="9ef95-188">int</span></span></p></td>
<td><p><span data-ttu-id="9ef95-189">Extranjero</span><span class="sxs-lookup"><span data-stu-id="9ef95-189">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9ef95-190">Representa el nombre de dominio completo del servidor que ha generado el informe de errores.</span><span class="sxs-lookup"><span data-stu-id="9ef95-190">Represents the fully qualified domain name of the server that generated the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ef95-191"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="9ef95-191"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef95-192">int</span><span class="sxs-lookup"><span data-stu-id="9ef95-192">int</span></span></p></td>
<td><p><span data-ttu-id="9ef95-193">Extranjero</span><span class="sxs-lookup"><span data-stu-id="9ef95-193">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9ef95-194">Representa el nombre de dominio completo del grupo en el que se generó el informe de errores.</span><span class="sxs-lookup"><span data-stu-id="9ef95-194">Represents the fully qualified domain name of the pool where the error report was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

