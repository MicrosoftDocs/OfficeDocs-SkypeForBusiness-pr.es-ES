---
title: 'Lync Server 2013: vista de ErrorReport'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorReport view
ms:assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721887(v=OCS.15)
ms:contentKeyID: 49733821
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1fe360726c94062391a4559f73a375d68b5f384
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042077"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorreport-view-in-lync-server-2013"></a><span data-ttu-id="f1680-102">Vista ErrorReport en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1680-102">ErrorReport view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1680-103">_**Última modificación del tema:** 2013-01-22_</span><span class="sxs-lookup"><span data-stu-id="f1680-103">_**Topic Last Modified:** 2013-01-22_</span></span>

<span data-ttu-id="f1680-104">La vista ErrorReport almacena información sobre los errores que se notifican.</span><span class="sxs-lookup"><span data-stu-id="f1680-104">The ErrorReport view stores information about errors reported.</span></span> <span data-ttu-id="f1680-105">Cada registro representa la aparición de un error.</span><span class="sxs-lookup"><span data-stu-id="f1680-105">Each record is one error occurrence.</span></span> <span data-ttu-id="f1680-106">Los errores se capturan con el agente del CDR que se ejecuta en el servidor front-end o los envía el cliente.</span><span class="sxs-lookup"><span data-stu-id="f1680-106">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span> <span data-ttu-id="f1680-107">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f1680-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f1680-108">Columna</span><span class="sxs-lookup"><span data-stu-id="f1680-108">Column</span></span></th>
<th><span data-ttu-id="f1680-109">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="f1680-109">Data Type</span></span></th>
<th><span data-ttu-id="f1680-110">Detalles</span><span class="sxs-lookup"><span data-stu-id="f1680-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f1680-111"><strong>Campos errortime</strong></span><span class="sxs-lookup"><span data-stu-id="f1680-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f1680-112">datetime</span><span class="sxs-lookup"><span data-stu-id="f1680-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="f1680-p102">Hora en que se produjo el error. Se usa en combinación con ErrorRportSeq para identificar el error de forma exclusiva.</span><span class="sxs-lookup"><span data-stu-id="f1680-p102">Time of error occurred. Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1680-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f1680-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f1680-116">int</span><span class="sxs-lookup"><span data-stu-id="f1680-116">int</span></span></p></td>
<td><p><span data-ttu-id="f1680-p103">Número para identificar el error. Se usa en combinación con ErrorTime para identificar el error de forma exclusiva.</span><span class="sxs-lookup"><span data-stu-id="f1680-p103">ID number to identify the error. Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1680-119"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="f1680-119"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="f1680-120">int</span><span class="sxs-lookup"><span data-stu-id="f1680-120">int</span></span></p></td>
<td><p><span data-ttu-id="f1680-121">Identificador de diagnóstico del informe de errores.</span><span class="sxs-lookup"><span data-stu-id="f1680-121">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1680-122"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="f1680-122"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="f1680-123">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="f1680-123">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="f1680-124">URI del usuario que ha originado el error.</span><span class="sxs-lookup"><span data-stu-id="f1680-124">URI of the user who originated the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1680-125"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="f1680-125"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="f1680-126">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f1680-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f1680-127">Tipo de URI del usuario que ha originado el error.</span><span class="sxs-lookup"><span data-stu-id="f1680-127">Type of URI of the user who originated the error.</span></span> <span data-ttu-id="f1680-128">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="f1680-128">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1680-129"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="f1680-129"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="f1680-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f1680-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f1680-131">Inquilino del usuario que ha originado el error.</span><span class="sxs-lookup"><span data-stu-id="f1680-131">Tenant of the user who originated the error.</span></span> <span data-ttu-id="f1680-132">Consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="f1680-132">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1680-133"><strong>ToUri</strong></span><span class="sxs-lookup"><span data-stu-id="f1680-133"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="f1680-134">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="f1680-134">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="f1680-135">URI del usuario destinatario del informe de errores.</span><span class="sxs-lookup"><span data-stu-id="f1680-135">URI of the user who was the target of the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1680-136"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="f1680-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="f1680-137">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f1680-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f1680-p106">Tipo de URI del usuario destinatario del informe de errores. Para más información, consulte la tabla UriTypes.</span><span class="sxs-lookup"><span data-stu-id="f1680-p106">Type of URI of the user who target of the error report. See the UriTypes Table for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1680-140"><strong>ToTenant</strong></span><span class="sxs-lookup"><span data-stu-id="f1680-140"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="f1680-141">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f1680-141">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f1680-142">Inquilino del usuario destinatario del informe de errores.</span><span class="sxs-lookup"><span data-stu-id="f1680-142">Tenant of the user who target of the error report.</span></span> <span data-ttu-id="f1680-143">Consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="f1680-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1680-144"><strong>Uri</strong></span><span class="sxs-lookup"><span data-stu-id="f1680-144"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="f1680-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="f1680-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="f1680-146">URI de la conferencia destinataria del informe de errores.</span><span class="sxs-lookup"><span data-stu-id="f1680-146">URI of the conference that was the target of the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1680-147"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="f1680-147"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="f1680-148">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f1680-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f1680-149">Tipo de URI de la conferencia destinataria del informe de errores.</span><span class="sxs-lookup"><span data-stu-id="f1680-149">URI type of the conference that was the target of the error report.</span></span> <span data-ttu-id="f1680-150">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="f1680-150">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1680-151"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="f1680-151"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f1680-152">datetime</span><span class="sxs-lookup"><span data-stu-id="f1680-152">datetime</span></span></p></td>
<td><p><span data-ttu-id="f1680-153">Hora de la solicitud de la sesión que originó el informe de errores.</span><span class="sxs-lookup"><span data-stu-id="f1680-153">Time of session request that originated the error report.</span></span> <span data-ttu-id="f1680-154">Se usa de forma conjunta con SessionIdseq para identificar de forma exclusiva una sesión.</span><span class="sxs-lookup"><span data-stu-id="f1680-154">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="f1680-155">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="f1680-155">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1680-156"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f1680-156"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f1680-157">int</span><span class="sxs-lookup"><span data-stu-id="f1680-157">int</span></span></p></td>
<td><p><span data-ttu-id="f1680-158">Número para identificar la solicitud de sesión que originó el informe de errores.</span><span class="sxs-lookup"><span data-stu-id="f1680-158">ID number to identify the session request that originated the error report.</span></span> <span data-ttu-id="f1680-159">Se usa de forma conjunta con SessionIdTime para identificar de forma exclusiva una sesión.</span><span class="sxs-lookup"><span data-stu-id="f1680-159">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="f1680-160">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="f1680-160">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1680-161"><strong>Identificador</strong></span><span class="sxs-lookup"><span data-stu-id="f1680-161"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="f1680-162">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="f1680-162">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="f1680-p111">Identificador de diálogo SIP que originó el error. El formato es:</span><span class="sxs-lookup"><span data-stu-id="f1680-p111">SIP dialog ID of session that originated the error. The format is:</span></span></p>
<p><span data-ttu-id="f1680-165">Dialog; from-Tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="f1680-165">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="f1680-166">Estos datos pueden convertirse en formato de texto con esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="f1680-166">This data can be converted to text format by using this syntax:</span></span></p>
<p><span data-ttu-id="f1680-167">cast(cast(ExternalId as varbinary(max)) as varchar(max))</span><span class="sxs-lookup"><span data-stu-id="f1680-167">cast(cast(ExternalId as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1680-168"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="f1680-168"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="f1680-169">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f1680-169">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f1680-170">Versión del cliente que usa el usuario que originó el error.</span><span class="sxs-lookup"><span data-stu-id="f1680-170">Version of client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1680-171"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="f1680-171"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="f1680-172">int</span><span class="sxs-lookup"><span data-stu-id="f1680-172">int</span></span></p></td>
<td><p><span data-ttu-id="f1680-173">Cliente que usa el usuario que originó el error.</span><span class="sxs-lookup"><span data-stu-id="f1680-173">Client used by the user who originated the error.</span></span> <span data-ttu-id="f1680-174">Consulte la <a href="lync-server-2013-useragentdef-table.md">tabla UserAgentDef en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="f1680-174">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1680-175"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="f1680-175"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="f1680-176">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="f1680-176">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="f1680-177">Nombre de categoría del cliente que usa el usuario que originó el error.</span><span class="sxs-lookup"><span data-stu-id="f1680-177">Name of the category of the client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1680-178"><strong>Source</strong></span><span class="sxs-lookup"><span data-stu-id="f1680-178"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="f1680-179">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f1680-179">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f1680-180">Nombre del servidor que originó el error (si el informe se envió desde un componente de servidor).</span><span class="sxs-lookup"><span data-stu-id="f1680-180">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1680-181"><strong>Application</strong></span><span class="sxs-lookup"><span data-stu-id="f1680-181"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="f1680-182">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f1680-182">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f1680-183">Nombre de la aplicación que originó el error (si el informe se envió desde un componente de servidor).</span><span class="sxs-lookup"><span data-stu-id="f1680-183">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1680-184"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="f1680-184"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="f1680-185">int</span><span class="sxs-lookup"><span data-stu-id="f1680-185">int</span></span></p></td>
<td><p><span data-ttu-id="f1680-186">Código de respuesta SIP a la sesión del mensaje SIP que contiene el informe de errores.</span><span class="sxs-lookup"><span data-stu-id="f1680-186">SIP response code to the session of the SIP message containing the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1680-187"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="f1680-187"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="f1680-188">VARCHAR (Max)</span><span class="sxs-lookup"><span data-stu-id="f1680-188">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="f1680-189">Tipo de solicitud que ha generado errores.</span><span class="sxs-lookup"><span data-stu-id="f1680-189">Type of request that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1680-190"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="f1680-190"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="f1680-191">VARCHAR (Max)</span><span class="sxs-lookup"><span data-stu-id="f1680-191">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="f1680-192">Tipo de contenido de la solicitud que ha generado errores.</span><span class="sxs-lookup"><span data-stu-id="f1680-192">Content type of the request that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1680-193"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="f1680-193"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="f1680-194">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f1680-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f1680-195">Tipo de sesión.</span><span class="sxs-lookup"><span data-stu-id="f1680-195">Type of session.</span></span> <span data-ttu-id="f1680-196">Consulte la <a href="lync-server-2013-calltype-table.md">tabla CallType en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="f1680-196">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1680-197"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="f1680-197"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="f1680-198">identificador</span><span class="sxs-lookup"><span data-stu-id="f1680-198">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="f1680-199">Identificador único que correlaciona la información de la hora de unión de los componentes que participan en una conferencia.</span><span class="sxs-lookup"><span data-stu-id="f1680-199">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1680-200"><strong>SetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="f1680-200"><strong>SetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f1680-201">int</span><span class="sxs-lookup"><span data-stu-id="f1680-201">int</span></span></p></td>
<td><p><span data-ttu-id="f1680-202">Tiempo (en milisegundos) que necesita un componente determinado para unirse a una conferencia.</span><span class="sxs-lookup"><span data-stu-id="f1680-202">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1680-203"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="f1680-203"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="f1680-204">bit</span><span class="sxs-lookup"><span data-stu-id="f1680-204">bit</span></span></p></td>
<td><p><span data-ttu-id="f1680-205">Indica si el informe de errores fue capturado por el agente del CDR que se ejecuta en el servidor front-end o si lo envió el cliente.</span><span class="sxs-lookup"><span data-stu-id="f1680-205">Indicates whether the error report was captured by the CDR agent running on the Front End server, or sent by the client.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1680-206"><strong>Flag</strong></span><span class="sxs-lookup"><span data-stu-id="f1680-206"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="f1680-207">smallint</span><span class="sxs-lookup"><span data-stu-id="f1680-207">smallint</span></span></p></td>
<td><p><span data-ttu-id="f1680-208">Reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="f1680-208">Reserved for future use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1680-209"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="f1680-209"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="f1680-210">VARCHAR (Max)</span><span class="sxs-lookup"><span data-stu-id="f1680-210">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="f1680-211">Más información sobre el error.</span><span class="sxs-lookup"><span data-stu-id="f1680-211">Additional information about the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1680-212"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="f1680-212"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="f1680-213">nvarchar</span><span class="sxs-lookup"><span data-stu-id="f1680-213">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="f1680-214">Nombre de dominio completo del servidor front-end que ha enviado el informe.</span><span class="sxs-lookup"><span data-stu-id="f1680-214">Fully qualified domain name of the Front End server that submitted the report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1680-215"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="f1680-215"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="f1680-216">nvarchar</span><span class="sxs-lookup"><span data-stu-id="f1680-216">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="f1680-217">Nombre de dominio completo del grupo de servidores que contiene el servidor front-end que ha enviado el informe.</span><span class="sxs-lookup"><span data-stu-id="f1680-217">Fully qualified domain name of the pool containing the Front End server that submitted the report.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

