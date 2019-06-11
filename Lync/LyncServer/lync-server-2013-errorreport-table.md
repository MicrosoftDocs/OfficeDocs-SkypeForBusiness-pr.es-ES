---
title: 'Lync Server 2013: Tabla ErrorReport'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ErrorReport table
ms:assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412826(v=OCS.15)
ms:contentKeyID: 48185129
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f0fc30d4686ffcc1d1cda0474b3b01a645c94be5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835200"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorreport-table-in-lync-server-2013"></a><span data-ttu-id="210a5-102">Tabla ErrorReport en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="210a5-102">ErrorReport table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="210a5-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="210a5-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="210a5-104">La tabla ErrorReport almacena información sobre los errores que se han producido.</span><span class="sxs-lookup"><span data-stu-id="210a5-104">The ErrorReport table stores information about errors that have occurred.</span></span> <span data-ttu-id="210a5-105">Cada registro es una aparición de error.</span><span class="sxs-lookup"><span data-stu-id="210a5-105">Each record is one error occurrence.</span></span> <span data-ttu-id="210a5-106">Los errores se capturan mediante el agente CDR que se ejecuta en el servidor front-end o se envían desde el cliente.</span><span class="sxs-lookup"><span data-stu-id="210a5-106">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="210a5-107">Columna</span><span class="sxs-lookup"><span data-stu-id="210a5-107">Column</span></span></th>
<th><span data-ttu-id="210a5-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="210a5-108">Data Type</span></span></th>
<th><span data-ttu-id="210a5-109">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="210a5-109">Key/Index</span></span></th>
<th><span data-ttu-id="210a5-110">Detalles</span><span class="sxs-lookup"><span data-stu-id="210a5-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="210a5-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="210a5-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="210a5-112">datetime</span><span class="sxs-lookup"><span data-stu-id="210a5-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="210a5-113">Primary</span><span class="sxs-lookup"><span data-stu-id="210a5-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="210a5-114">Fecha y hora en que se produjo el error.</span><span class="sxs-lookup"><span data-stu-id="210a5-114">Date and time the error occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="210a5-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="210a5-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="210a5-116">int</span><span class="sxs-lookup"><span data-stu-id="210a5-116">int</span></span></p></td>
<td><p><span data-ttu-id="210a5-117">Primary</span><span class="sxs-lookup"><span data-stu-id="210a5-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="210a5-118">Número de identificación para identificar el informe de errores.</span><span class="sxs-lookup"><span data-stu-id="210a5-118">ID number to identify the error report.</span></span> <span data-ttu-id="210a5-119">Se usa en conjunción con <strong>ErrorTime</strong> para identificar de manera exclusiva un informe de errores.</span><span class="sxs-lookup"><span data-stu-id="210a5-119">Used in conjunction with <strong>ErrorTime</strong> to uniquely identify an error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="210a5-120"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="210a5-120"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="210a5-121">int</span><span class="sxs-lookup"><span data-stu-id="210a5-121">int</span></span></p></td>
<td><p><span data-ttu-id="210a5-122">Extranjero</span><span class="sxs-lookup"><span data-stu-id="210a5-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="210a5-123">IDENTIFICADOR único del tipo de error.</span><span class="sxs-lookup"><span data-stu-id="210a5-123">Unique ID of the error type.</span></span> <span data-ttu-id="210a5-124">Para obtener más información, consulte la <a href="lync-server-2013-errordef-table.md">tabla ErrorDef en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="210a5-124">See the <a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="210a5-125"><strong>FromUserId</strong></span><span class="sxs-lookup"><span data-stu-id="210a5-125"><strong>FromUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="210a5-126">int</span><span class="sxs-lookup"><span data-stu-id="210a5-126">int</span></span></p></td>
<td><p><span data-ttu-id="210a5-127">Extranjero</span><span class="sxs-lookup"><span data-stu-id="210a5-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="210a5-128">Usuario que originó la solicitud que causó el error.</span><span class="sxs-lookup"><span data-stu-id="210a5-128">User who originated the request that caused the error.</span></span> <span data-ttu-id="210a5-129">Para obtener más información, consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="210a5-129">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="210a5-130"><strong>ToUserId</strong></span><span class="sxs-lookup"><span data-stu-id="210a5-130"><strong>ToUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="210a5-131">int</span><span class="sxs-lookup"><span data-stu-id="210a5-131">int</span></span></p></td>
<td><p><span data-ttu-id="210a5-132">Extranjero</span><span class="sxs-lookup"><span data-stu-id="210a5-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="210a5-133">Usuario de destino de la solicitud que causó el error.</span><span class="sxs-lookup"><span data-stu-id="210a5-133">Destination user for the request that caused the error.</span></span> <span data-ttu-id="210a5-134">Para obtener más información, consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="210a5-134">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="210a5-135"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="210a5-135"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="210a5-136">int</span><span class="sxs-lookup"><span data-stu-id="210a5-136">int</span></span></p></td>
<td><p><span data-ttu-id="210a5-137">Extranjero</span><span class="sxs-lookup"><span data-stu-id="210a5-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="210a5-138">URI de conferencia relacionado con el error.</span><span class="sxs-lookup"><span data-stu-id="210a5-138">Conference URI related to the error.</span></span> <span data-ttu-id="210a5-139">Para obtener más información, consulte la <a href="lync-server-2013-conferenceuris-table.md">tabla ConferenceUris en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="210a5-139">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="210a5-140">Normalmente, si ConferenceUriId no es null, FromUserId o ToUserId será null.</span><span class="sxs-lookup"><span data-stu-id="210a5-140">Typically, if ConferenceUriId is not null, then either FromUserId or ToUserId will be null.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="210a5-141"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="210a5-141"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="210a5-142">datetime</span><span class="sxs-lookup"><span data-stu-id="210a5-142">datetime</span></span></p></td>
<td><p><span data-ttu-id="210a5-143">Extranjero</span><span class="sxs-lookup"><span data-stu-id="210a5-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="210a5-144">Se usa en conjunción con <strong>SessionIdSeq</strong> para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="210a5-144">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="210a5-145">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="210a5-145">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="210a5-146"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="210a5-146"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="210a5-147">int</span><span class="sxs-lookup"><span data-stu-id="210a5-147">int</span></span></p></td>
<td><p><span data-ttu-id="210a5-148">Extranjero</span><span class="sxs-lookup"><span data-stu-id="210a5-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="210a5-149">Número de identificación para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="210a5-149">ID number to identify the session.</span></span> <span data-ttu-id="210a5-150">Se usa en conjunción con <strong>SessionIdTime</strong> para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="210a5-150">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="210a5-151">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="210a5-151">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="210a5-152"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="210a5-152"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="210a5-153">int</span><span class="sxs-lookup"><span data-stu-id="210a5-153">int</span></span></p></td>
<td><p><span data-ttu-id="210a5-154">Extranjero</span><span class="sxs-lookup"><span data-stu-id="210a5-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="210a5-155">Servidor que ha enviado el informe de errores (si el informe se está enviando desde un componente de servidor).</span><span class="sxs-lookup"><span data-stu-id="210a5-155">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="210a5-156">Para obtener más información, consulte la <a href="lync-server-2013-servers-table.md">tabla servidores en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="210a5-156">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="210a5-157">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="210a5-157">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="210a5-158"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="210a5-158"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="210a5-159">int</span><span class="sxs-lookup"><span data-stu-id="210a5-159">int</span></span></p></td>
<td><p><span data-ttu-id="210a5-160">Extranjero</span><span class="sxs-lookup"><span data-stu-id="210a5-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="210a5-161">Servidor que ha enviado el informe de errores (si el informe se está enviando desde un componente de servidor).</span><span class="sxs-lookup"><span data-stu-id="210a5-161">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="210a5-162">Para obtener más información, consulte la <a href="lync-server-2013-application-table.md">tabla de aplicaciones en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="210a5-162">See the <a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="210a5-163">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="210a5-163">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="210a5-164"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="210a5-164"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="210a5-165">imagen</span><span class="sxs-lookup"><span data-stu-id="210a5-165">image</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="210a5-166">Más información sobre el error.</span><span class="sxs-lookup"><span data-stu-id="210a5-166">More information about the error.</span></span></p>
<p><span data-ttu-id="210a5-167">Estos datos se pueden convertir a formato de texto con esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="210a5-167">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="210a5-168"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="210a5-168"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="210a5-169">int</span><span class="sxs-lookup"><span data-stu-id="210a5-169">int</span></span></p></td>
<td><p><span data-ttu-id="210a5-170">Extranjero</span><span class="sxs-lookup"><span data-stu-id="210a5-170">Foreign</span></span></p></td>
<td><p><span data-ttu-id="210a5-171">La versión de cliente del extremo que envía el informe de errores.</span><span class="sxs-lookup"><span data-stu-id="210a5-171">The client version of endpoint that sends the error report.</span></span> <span data-ttu-id="210a5-172">Para obtener más información, consulte la <a href="lync-server-2013-clientversions-table.md">tabla ClientVersions en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="210a5-172">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="210a5-173"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="210a5-173"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="210a5-174">bit</span><span class="sxs-lookup"><span data-stu-id="210a5-174">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="210a5-175">Es el informe de errores capturado por el agente CDR que se ejecuta en el servidor front-end o enviado por el cliente.</span><span class="sxs-lookup"><span data-stu-id="210a5-175">Is the error report captured by the CDR agent running on the front-end server, or sent by the client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="210a5-176"><strong>Fdisableautoindexingonschemaupdate</strong></span><span class="sxs-lookup"><span data-stu-id="210a5-176"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="210a5-177">smallint</span><span class="sxs-lookup"><span data-stu-id="210a5-177">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="210a5-178">Reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="210a5-178">Reserved for future use.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="210a5-179"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="210a5-179"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="210a5-180">Identificador</span><span class="sxs-lookup"><span data-stu-id="210a5-180">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="210a5-181">Identificador único que correlaciona información de tiempo de Unión para los distintos componentes implicados en una conferencia.</span><span class="sxs-lookup"><span data-stu-id="210a5-181">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="210a5-182">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="210a5-182">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="210a5-183"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="210a5-183"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="210a5-184">int</span><span class="sxs-lookup"><span data-stu-id="210a5-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="210a5-185">Tiempo (en milisegundos) necesario para que un componente específico se una a una conferencia.</span><span class="sxs-lookup"><span data-stu-id="210a5-185">Time (in milliseconds) required for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="210a5-186">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="210a5-186">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="210a5-187"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="210a5-187"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="210a5-188">int</span><span class="sxs-lookup"><span data-stu-id="210a5-188">int</span></span></p></td>
<td><p><span data-ttu-id="210a5-189">Extranjero</span><span class="sxs-lookup"><span data-stu-id="210a5-189">Foreign</span></span></p></td>
<td><p><span data-ttu-id="210a5-190">Representa el nombre de dominio completo del servidor que ha generado el informe de errores.</span><span class="sxs-lookup"><span data-stu-id="210a5-190">Represents the fully qualified domain name of the server that generated the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="210a5-191"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="210a5-191"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="210a5-192">int</span><span class="sxs-lookup"><span data-stu-id="210a5-192">int</span></span></p></td>
<td><p><span data-ttu-id="210a5-193">Extranjero</span><span class="sxs-lookup"><span data-stu-id="210a5-193">Foreign</span></span></p></td>
<td><p><span data-ttu-id="210a5-194">Representa el nombre de dominio completo del grupo en el que se generó el informe de errores.</span><span class="sxs-lookup"><span data-stu-id="210a5-194">Represents the fully qualified domain name of the pool where the error report was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

