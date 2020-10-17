---
title: 'Lync Server 2013: tabla ErrorReport'
description: 'Lync Server 2013: tabla ErrorReport.'
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
ms.openlocfilehash: 9c1cc65c396c16dc137255438f7ef7c32b2d0b78
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572016"
---
# <a name="errorreport-table-in-lync-server-2013"></a><span data-ttu-id="45ad8-103">Tabla ErrorReport en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45ad8-103">ErrorReport table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45ad8-104">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="45ad8-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="45ad8-105">La tabla ErrorReport almacena información sobre los errores que se han producido.</span><span class="sxs-lookup"><span data-stu-id="45ad8-105">The ErrorReport table stores information about errors that have occurred.</span></span> <span data-ttu-id="45ad8-106">Cada registro representa la aparición de un error.</span><span class="sxs-lookup"><span data-stu-id="45ad8-106">Each record is one error occurrence.</span></span> <span data-ttu-id="45ad8-107">Los errores se capturan con el agente del CDR que se ejecuta en el servidor front-end o los envía el cliente.</span><span class="sxs-lookup"><span data-stu-id="45ad8-107">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="45ad8-108">Columna</span><span class="sxs-lookup"><span data-stu-id="45ad8-108">Column</span></span></th>
<th><span data-ttu-id="45ad8-109">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="45ad8-109">Data Type</span></span></th>
<th><span data-ttu-id="45ad8-110">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="45ad8-110">Key/Index</span></span></th>
<th><span data-ttu-id="45ad8-111">Detalles</span><span class="sxs-lookup"><span data-stu-id="45ad8-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="45ad8-112"><strong>Campos errortime</strong></span><span class="sxs-lookup"><span data-stu-id="45ad8-112"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="45ad8-113">datetime</span><span class="sxs-lookup"><span data-stu-id="45ad8-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="45ad8-114">Principal</span><span class="sxs-lookup"><span data-stu-id="45ad8-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="45ad8-115">Fecha y hora en que se produjo el error.</span><span class="sxs-lookup"><span data-stu-id="45ad8-115">Date and time the error occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45ad8-116"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="45ad8-116"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="45ad8-117">entero</span><span class="sxs-lookup"><span data-stu-id="45ad8-117">int</span></span></p></td>
<td><p><span data-ttu-id="45ad8-118">Principal</span><span class="sxs-lookup"><span data-stu-id="45ad8-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="45ad8-119">Número de identificador para identificar el informe de errores.</span><span class="sxs-lookup"><span data-stu-id="45ad8-119">ID number to identify the error report.</span></span> <span data-ttu-id="45ad8-120">Se usa junto con <strong>campos errortime</strong> para identificar de forma exclusiva un informe de errores.</span><span class="sxs-lookup"><span data-stu-id="45ad8-120">Used in conjunction with <strong>ErrorTime</strong> to uniquely identify an error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45ad8-121"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="45ad8-121"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="45ad8-122">entero</span><span class="sxs-lookup"><span data-stu-id="45ad8-122">int</span></span></p></td>
<td><p><span data-ttu-id="45ad8-123">Externa</span><span class="sxs-lookup"><span data-stu-id="45ad8-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="45ad8-124">IDENTIFICADOR único del tipo de error.</span><span class="sxs-lookup"><span data-stu-id="45ad8-124">Unique ID of the error type.</span></span> <span data-ttu-id="45ad8-125">Consulte la <a href="lync-server-2013-errordef-table.md">tabla ErrorDef en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="45ad8-125">See the <a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45ad8-126"><strong>FromUserId</strong></span><span class="sxs-lookup"><span data-stu-id="45ad8-126"><strong>FromUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="45ad8-127">entero</span><span class="sxs-lookup"><span data-stu-id="45ad8-127">int</span></span></p></td>
<td><p><span data-ttu-id="45ad8-128">Externa</span><span class="sxs-lookup"><span data-stu-id="45ad8-128">Foreign</span></span></p></td>
<td><p><span data-ttu-id="45ad8-129">Usuario que originó la solicitud que causó el error.</span><span class="sxs-lookup"><span data-stu-id="45ad8-129">User who originated the request that caused the error.</span></span> <span data-ttu-id="45ad8-130">Consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="45ad8-130">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45ad8-131"><strong>ToUserId</strong></span><span class="sxs-lookup"><span data-stu-id="45ad8-131"><strong>ToUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="45ad8-132">entero</span><span class="sxs-lookup"><span data-stu-id="45ad8-132">int</span></span></p></td>
<td><p><span data-ttu-id="45ad8-133">Externa</span><span class="sxs-lookup"><span data-stu-id="45ad8-133">Foreign</span></span></p></td>
<td><p><span data-ttu-id="45ad8-134">Usuario de destino de la solicitud que provocó el error.</span><span class="sxs-lookup"><span data-stu-id="45ad8-134">Destination user for the request that caused the error.</span></span> <span data-ttu-id="45ad8-135">Consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="45ad8-135">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45ad8-136"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="45ad8-136"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="45ad8-137">entero</span><span class="sxs-lookup"><span data-stu-id="45ad8-137">int</span></span></p></td>
<td><p><span data-ttu-id="45ad8-138">Externa</span><span class="sxs-lookup"><span data-stu-id="45ad8-138">Foreign</span></span></p></td>
<td><p><span data-ttu-id="45ad8-139">URI de conferencia relacionado con el error.</span><span class="sxs-lookup"><span data-stu-id="45ad8-139">Conference URI related to the error.</span></span> <span data-ttu-id="45ad8-140">Consulte la <a href="lync-server-2013-conferenceuris-table.md">tabla ConferenceUris en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="45ad8-140">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="45ad8-141">Normalmente, si ConferenceUriId no es null, entonces FromUserId o ToUserId será null.</span><span class="sxs-lookup"><span data-stu-id="45ad8-141">Typically, if ConferenceUriId is not null, then either FromUserId or ToUserId will be null.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45ad8-142"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="45ad8-142"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="45ad8-143">datetime</span><span class="sxs-lookup"><span data-stu-id="45ad8-143">datetime</span></span></p></td>
<td><p><span data-ttu-id="45ad8-144">Externa</span><span class="sxs-lookup"><span data-stu-id="45ad8-144">Foreign</span></span></p></td>
<td><p><span data-ttu-id="45ad8-145">Se usa junto con <strong>SessionIdSeq</strong> para identificar una sesión de manera exclusiva.</span><span class="sxs-lookup"><span data-stu-id="45ad8-145">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="45ad8-146">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="45ad8-146">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45ad8-147"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="45ad8-147"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="45ad8-148">entero</span><span class="sxs-lookup"><span data-stu-id="45ad8-148">int</span></span></p></td>
<td><p><span data-ttu-id="45ad8-149">Externa</span><span class="sxs-lookup"><span data-stu-id="45ad8-149">Foreign</span></span></p></td>
<td><p><span data-ttu-id="45ad8-150">Número con el que se identifica la sesión.</span><span class="sxs-lookup"><span data-stu-id="45ad8-150">ID number to identify the session.</span></span> <span data-ttu-id="45ad8-151">Se usa en combinación con <strong>SessionIdTime</strong> para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="45ad8-151">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="45ad8-152">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="45ad8-152">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45ad8-153"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="45ad8-153"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="45ad8-154">entero</span><span class="sxs-lookup"><span data-stu-id="45ad8-154">int</span></span></p></td>
<td><p><span data-ttu-id="45ad8-155">Externa</span><span class="sxs-lookup"><span data-stu-id="45ad8-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="45ad8-156">Servidor que ha enviado el informe de errores (si el informe se está enviando desde un componente de servidor).</span><span class="sxs-lookup"><span data-stu-id="45ad8-156">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="45ad8-157">Consulte la <a href="lync-server-2013-servers-table.md">tabla servidores en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="45ad8-157">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="45ad8-158">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="45ad8-158">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45ad8-159"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="45ad8-159"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="45ad8-160">entero</span><span class="sxs-lookup"><span data-stu-id="45ad8-160">int</span></span></p></td>
<td><p><span data-ttu-id="45ad8-161">Externa</span><span class="sxs-lookup"><span data-stu-id="45ad8-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="45ad8-162">Servidor que ha enviado el informe de errores (si el informe se está enviando desde un componente de servidor).</span><span class="sxs-lookup"><span data-stu-id="45ad8-162">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="45ad8-163">Consulte la <a href="lync-server-2013-application-table.md">tabla de la aplicación en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="45ad8-163">See the <a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="45ad8-164">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="45ad8-164">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45ad8-165"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="45ad8-165"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="45ad8-166">imagen</span><span class="sxs-lookup"><span data-stu-id="45ad8-166">image</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="45ad8-167">Más información sobre el error.</span><span class="sxs-lookup"><span data-stu-id="45ad8-167">More information about the error.</span></span></p>
<p><span data-ttu-id="45ad8-168">Estos datos pueden convertirse en formato de texto con esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="45ad8-168">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45ad8-169"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="45ad8-169"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="45ad8-170">entero</span><span class="sxs-lookup"><span data-stu-id="45ad8-170">int</span></span></p></td>
<td><p><span data-ttu-id="45ad8-171">Externa</span><span class="sxs-lookup"><span data-stu-id="45ad8-171">Foreign</span></span></p></td>
<td><p><span data-ttu-id="45ad8-172">La versión de cliente del extremo que envía el informe de errores.</span><span class="sxs-lookup"><span data-stu-id="45ad8-172">The client version of endpoint that sends the error report.</span></span> <span data-ttu-id="45ad8-173">Consulte la <a href="lync-server-2013-clientversions-table.md">tabla ClientVersions en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="45ad8-173">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45ad8-174"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="45ad8-174"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="45ad8-175">bit</span><span class="sxs-lookup"><span data-stu-id="45ad8-175">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="45ad8-176">Es el informe de errores capturado por el agente CDR que se ejecuta en el servidor front-end o enviado por el cliente.</span><span class="sxs-lookup"><span data-stu-id="45ad8-176">Is the error report captured by the CDR agent running on the front-end server, or sent by the client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45ad8-177"><strong>Flag</strong></span><span class="sxs-lookup"><span data-stu-id="45ad8-177"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="45ad8-178">smallint</span><span class="sxs-lookup"><span data-stu-id="45ad8-178">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="45ad8-179">Reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="45ad8-179">Reserved for future use.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45ad8-180"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="45ad8-180"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="45ad8-181">Identificador</span><span class="sxs-lookup"><span data-stu-id="45ad8-181">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="45ad8-182">Identificador único que correlaciona la información de la hora de unión de los componentes que participan en una conferencia.</span><span class="sxs-lookup"><span data-stu-id="45ad8-182">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="45ad8-183">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="45ad8-183">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45ad8-184"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="45ad8-184"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="45ad8-185">entero</span><span class="sxs-lookup"><span data-stu-id="45ad8-185">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="45ad8-186">Tiempo (en milisegundos) que necesita un componente determinado para unirse a una conferencia.</span><span class="sxs-lookup"><span data-stu-id="45ad8-186">Time (in milliseconds) required for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="45ad8-187">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="45ad8-187">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45ad8-188"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="45ad8-188"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="45ad8-189">entero</span><span class="sxs-lookup"><span data-stu-id="45ad8-189">int</span></span></p></td>
<td><p><span data-ttu-id="45ad8-190">Externa</span><span class="sxs-lookup"><span data-stu-id="45ad8-190">Foreign</span></span></p></td>
<td><p><span data-ttu-id="45ad8-191">Representa el nombre de dominio completo del servidor que generó el informe de errores.</span><span class="sxs-lookup"><span data-stu-id="45ad8-191">Represents the fully qualified domain name of the server that generated the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45ad8-192"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="45ad8-192"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="45ad8-193">entero</span><span class="sxs-lookup"><span data-stu-id="45ad8-193">int</span></span></p></td>
<td><p><span data-ttu-id="45ad8-194">Externa</span><span class="sxs-lookup"><span data-stu-id="45ad8-194">Foreign</span></span></p></td>
<td><p><span data-ttu-id="45ad8-195">Representa el nombre de dominio completo del grupo en el que se generó el informe de errores.</span><span class="sxs-lookup"><span data-stu-id="45ad8-195">Represents the fully qualified domain name of the pool where the error report was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

