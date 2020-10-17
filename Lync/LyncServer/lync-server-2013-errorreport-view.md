---
title: 'Lync Server 2013: vista de ErrorReport'
description: 'Lync Server 2013: vista de ErrorReport.'
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
ms.openlocfilehash: 50fb0a362c71d8dfb5873157e7b1ed3d3eb680ae
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572046"
---
# <a name="errorreport-view-in-lync-server-2013"></a><span data-ttu-id="a3463-103">Vista ErrorReport en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a3463-103">ErrorReport view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3463-104">_**Última modificación del tema:** 2013-01-22_</span><span class="sxs-lookup"><span data-stu-id="a3463-104">_**Topic Last Modified:** 2013-01-22_</span></span>

<span data-ttu-id="a3463-105">La vista ErrorReport almacena información sobre los errores que se notifican.</span><span class="sxs-lookup"><span data-stu-id="a3463-105">The ErrorReport view stores information about errors reported.</span></span> <span data-ttu-id="a3463-106">Cada registro representa la aparición de un error.</span><span class="sxs-lookup"><span data-stu-id="a3463-106">Each record is one error occurrence.</span></span> <span data-ttu-id="a3463-107">Los errores se capturan con el agente del CDR que se ejecuta en el servidor front-end o los envía el cliente.</span><span class="sxs-lookup"><span data-stu-id="a3463-107">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span> <span data-ttu-id="a3463-108">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a3463-108">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a3463-109">Columna</span><span class="sxs-lookup"><span data-stu-id="a3463-109">Column</span></span></th>
<th><span data-ttu-id="a3463-110">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="a3463-110">Data Type</span></span></th>
<th><span data-ttu-id="a3463-111">Detalles</span><span class="sxs-lookup"><span data-stu-id="a3463-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a3463-112"><strong>Campos errortime</strong></span><span class="sxs-lookup"><span data-stu-id="a3463-112"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a3463-113">datetime</span><span class="sxs-lookup"><span data-stu-id="a3463-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="a3463-p102">Hora en que se produjo el error. Se usa en combinación con ErrorRportSeq para identificar el error de forma exclusiva.</span><span class="sxs-lookup"><span data-stu-id="a3463-p102">Time of error occurred. Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3463-116"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a3463-116"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a3463-117">entero</span><span class="sxs-lookup"><span data-stu-id="a3463-117">int</span></span></p></td>
<td><p><span data-ttu-id="a3463-p103">Número para identificar el error. Se usa en combinación con ErrorTime para identificar el error de forma exclusiva.</span><span class="sxs-lookup"><span data-stu-id="a3463-p103">ID number to identify the error. Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3463-120"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="a3463-120"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="a3463-121">entero</span><span class="sxs-lookup"><span data-stu-id="a3463-121">int</span></span></p></td>
<td><p><span data-ttu-id="a3463-122">Identificador de diagnóstico del informe de errores.</span><span class="sxs-lookup"><span data-stu-id="a3463-122">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3463-123"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="a3463-123"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="a3463-124">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a3463-124">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a3463-125">URI del usuario que ha originado el error.</span><span class="sxs-lookup"><span data-stu-id="a3463-125">URI of the user who originated the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3463-126"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="a3463-126"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="a3463-127">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a3463-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a3463-128">Tipo de URI del usuario que ha originado el error.</span><span class="sxs-lookup"><span data-stu-id="a3463-128">Type of URI of the user who originated the error.</span></span> <span data-ttu-id="a3463-129">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a3463-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3463-130"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="a3463-130"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="a3463-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a3463-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a3463-132">Inquilino del usuario que ha originado el error.</span><span class="sxs-lookup"><span data-stu-id="a3463-132">Tenant of the user who originated the error.</span></span> <span data-ttu-id="a3463-133">Consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a3463-133">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3463-134"><strong>ToUri</strong></span><span class="sxs-lookup"><span data-stu-id="a3463-134"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="a3463-135">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a3463-135">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a3463-136">URI del usuario destinatario del informe de errores.</span><span class="sxs-lookup"><span data-stu-id="a3463-136">URI of the user who was the target of the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3463-137"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="a3463-137"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="a3463-138">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a3463-138">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a3463-p106">Tipo de URI del usuario destinatario del informe de errores. Para más información, consulte la tabla UriTypes.</span><span class="sxs-lookup"><span data-stu-id="a3463-p106">Type of URI of the user who target of the error report. See the UriTypes Table for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3463-141"><strong>ToTenant</strong></span><span class="sxs-lookup"><span data-stu-id="a3463-141"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="a3463-142">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a3463-142">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a3463-143">Inquilino del usuario destinatario del informe de errores.</span><span class="sxs-lookup"><span data-stu-id="a3463-143">Tenant of the user who target of the error report.</span></span> <span data-ttu-id="a3463-144">Consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a3463-144">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3463-145"><strong>Uri</strong></span><span class="sxs-lookup"><span data-stu-id="a3463-145"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="a3463-146">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a3463-146">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a3463-147">URI de la conferencia destinataria del informe de errores.</span><span class="sxs-lookup"><span data-stu-id="a3463-147">URI of the conference that was the target of the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3463-148"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="a3463-148"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="a3463-149">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a3463-149">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a3463-150">Tipo de URI de la conferencia destinataria del informe de errores.</span><span class="sxs-lookup"><span data-stu-id="a3463-150">URI type of the conference that was the target of the error report.</span></span> <span data-ttu-id="a3463-151">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a3463-151">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3463-152"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="a3463-152"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a3463-153">datetime</span><span class="sxs-lookup"><span data-stu-id="a3463-153">datetime</span></span></p></td>
<td><p><span data-ttu-id="a3463-154">Hora de la solicitud de la sesión que originó el informe de errores.</span><span class="sxs-lookup"><span data-stu-id="a3463-154">Time of session request that originated the error report.</span></span> <span data-ttu-id="a3463-155">Se usa de forma conjunta con SessionIdseq para identificar de forma exclusiva una sesión.</span><span class="sxs-lookup"><span data-stu-id="a3463-155">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="a3463-156">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a3463-156">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3463-157"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a3463-157"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a3463-158">entero</span><span class="sxs-lookup"><span data-stu-id="a3463-158">int</span></span></p></td>
<td><p><span data-ttu-id="a3463-159">Número para identificar la solicitud de sesión que originó el informe de errores.</span><span class="sxs-lookup"><span data-stu-id="a3463-159">ID number to identify the session request that originated the error report.</span></span> <span data-ttu-id="a3463-160">Se usa de forma conjunta con SessionIdTime para identificar de forma exclusiva una sesión.</span><span class="sxs-lookup"><span data-stu-id="a3463-160">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="a3463-161">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a3463-161">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3463-162"><strong>Identificador</strong></span><span class="sxs-lookup"><span data-stu-id="a3463-162"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="a3463-163">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="a3463-163">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="a3463-p111">Identificador de diálogo SIP que originó el error. El formato es:</span><span class="sxs-lookup"><span data-stu-id="a3463-p111">SIP dialog ID of session that originated the error. The format is:</span></span></p>
<p><span data-ttu-id="a3463-166">Dialog; from-Tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="a3463-166">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="a3463-167">Estos datos pueden convertirse en formato de texto con esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="a3463-167">This data can be converted to text format by using this syntax:</span></span></p>
<p><span data-ttu-id="a3463-168">cast(cast(ExternalId as varbinary(max)) as varchar(max))</span><span class="sxs-lookup"><span data-stu-id="a3463-168">cast(cast(ExternalId as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3463-169"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="a3463-169"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="a3463-170">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a3463-170">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a3463-171">Versión del cliente que usa el usuario que originó el error.</span><span class="sxs-lookup"><span data-stu-id="a3463-171">Version of client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3463-172"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="a3463-172"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="a3463-173">entero</span><span class="sxs-lookup"><span data-stu-id="a3463-173">int</span></span></p></td>
<td><p><span data-ttu-id="a3463-174">Cliente que usa el usuario que originó el error.</span><span class="sxs-lookup"><span data-stu-id="a3463-174">Client used by the user who originated the error.</span></span> <span data-ttu-id="a3463-175">Consulte la <a href="lync-server-2013-useragentdef-table.md">tabla UserAgentDef en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a3463-175">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3463-176"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="a3463-176"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="a3463-177">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="a3463-177">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="a3463-178">Nombre de categoría del cliente que usa el usuario que originó el error.</span><span class="sxs-lookup"><span data-stu-id="a3463-178">Name of the category of the client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3463-179"><strong>Source</strong></span><span class="sxs-lookup"><span data-stu-id="a3463-179"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="a3463-180">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a3463-180">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a3463-181">Nombre del servidor que originó el error (si el informe se envió desde un componente de servidor).</span><span class="sxs-lookup"><span data-stu-id="a3463-181">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3463-182"><strong>Aplicación</strong></span><span class="sxs-lookup"><span data-stu-id="a3463-182"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="a3463-183">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a3463-183">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a3463-184">Nombre de la aplicación que originó el error (si el informe se envió desde un componente de servidor).</span><span class="sxs-lookup"><span data-stu-id="a3463-184">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3463-185"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="a3463-185"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="a3463-186">entero</span><span class="sxs-lookup"><span data-stu-id="a3463-186">int</span></span></p></td>
<td><p><span data-ttu-id="a3463-187">Código de respuesta SIP a la sesión del mensaje SIP que contiene el informe de errores.</span><span class="sxs-lookup"><span data-stu-id="a3463-187">SIP response code to the session of the SIP message containing the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3463-188"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="a3463-188"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="a3463-189">VARCHAR (Max)</span><span class="sxs-lookup"><span data-stu-id="a3463-189">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="a3463-190">Tipo de solicitud que ha generado errores.</span><span class="sxs-lookup"><span data-stu-id="a3463-190">Type of request that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3463-191"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="a3463-191"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="a3463-192">VARCHAR (Max)</span><span class="sxs-lookup"><span data-stu-id="a3463-192">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="a3463-193">Tipo de contenido de la solicitud que ha generado errores.</span><span class="sxs-lookup"><span data-stu-id="a3463-193">Content type of the request that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3463-194"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="a3463-194"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="a3463-195">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a3463-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a3463-196">Tipo de sesión.</span><span class="sxs-lookup"><span data-stu-id="a3463-196">Type of session.</span></span> <span data-ttu-id="a3463-197">Consulte la <a href="lync-server-2013-calltype-table.md">tabla CallType en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a3463-197">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3463-198"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="a3463-198"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="a3463-199">identificador</span><span class="sxs-lookup"><span data-stu-id="a3463-199">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="a3463-200">Identificador único que correlaciona la información de la hora de unión de los componentes que participan en una conferencia.</span><span class="sxs-lookup"><span data-stu-id="a3463-200">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3463-201"><strong>SetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="a3463-201"><strong>SetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a3463-202">entero</span><span class="sxs-lookup"><span data-stu-id="a3463-202">int</span></span></p></td>
<td><p><span data-ttu-id="a3463-203">Tiempo (en milisegundos) que necesita un componente determinado para unirse a una conferencia.</span><span class="sxs-lookup"><span data-stu-id="a3463-203">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3463-204"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="a3463-204"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="a3463-205">bit</span><span class="sxs-lookup"><span data-stu-id="a3463-205">bit</span></span></p></td>
<td><p><span data-ttu-id="a3463-206">Indica si el informe de errores fue capturado por el agente del CDR que se ejecuta en el servidor front-end o si lo envió el cliente.</span><span class="sxs-lookup"><span data-stu-id="a3463-206">Indicates whether the error report was captured by the CDR agent running on the Front End server, or sent by the client.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3463-207"><strong>Flag</strong></span><span class="sxs-lookup"><span data-stu-id="a3463-207"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="a3463-208">smallint</span><span class="sxs-lookup"><span data-stu-id="a3463-208">smallint</span></span></p></td>
<td><p><span data-ttu-id="a3463-209">Reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="a3463-209">Reserved for future use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3463-210"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="a3463-210"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="a3463-211">VARCHAR (Max)</span><span class="sxs-lookup"><span data-stu-id="a3463-211">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="a3463-212">Más información sobre el error.</span><span class="sxs-lookup"><span data-stu-id="a3463-212">Additional information about the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3463-213"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="a3463-213"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="a3463-214">nvarchar</span><span class="sxs-lookup"><span data-stu-id="a3463-214">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="a3463-215">Nombre de dominio completo del servidor front-end que ha enviado el informe.</span><span class="sxs-lookup"><span data-stu-id="a3463-215">Fully qualified domain name of the Front End server that submitted the report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3463-216"><strong>Grupo</strong></span><span class="sxs-lookup"><span data-stu-id="a3463-216"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="a3463-217">nvarchar</span><span class="sxs-lookup"><span data-stu-id="a3463-217">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="a3463-218">Nombre de dominio completo del grupo de servidores que contiene el servidor front-end que ha enviado el informe.</span><span class="sxs-lookup"><span data-stu-id="a3463-218">Fully qualified domain name of the pool containing the Front End server that submitted the report.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

