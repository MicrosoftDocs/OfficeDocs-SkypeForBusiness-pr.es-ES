---
title: 'Lync Server 2013: vista ErrorReport'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ErrorReport view
ms:assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721887(v=OCS.15)
ms:contentKeyID: 49733821
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b50a2615fe83ed481d9642ac6895120f20b9fd0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835209"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorreport-view-in-lync-server-2013"></a><span data-ttu-id="cbe8b-102">Vista ErrorReport en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cbe8b-102">ErrorReport view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cbe8b-103">_**Última modificación del tema:** 2013-01-22_</span><span class="sxs-lookup"><span data-stu-id="cbe8b-103">_**Topic Last Modified:** 2013-01-22_</span></span>

<span data-ttu-id="cbe8b-104">La vista ErrorReport almacena información sobre los errores notificados.</span><span class="sxs-lookup"><span data-stu-id="cbe8b-104">The ErrorReport view stores information about errors reported.</span></span> <span data-ttu-id="cbe8b-105">Cada registro es una aparición de error.</span><span class="sxs-lookup"><span data-stu-id="cbe8b-105">Each record is one error occurrence.</span></span> <span data-ttu-id="cbe8b-106">Los errores se capturan mediante el agente CDR que se ejecuta en el servidor front-end o se envían desde el cliente.</span><span class="sxs-lookup"><span data-stu-id="cbe8b-106">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span> <span data-ttu-id="cbe8b-107">Esta vista se presentó en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cbe8b-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cbe8b-108">Columna</span><span class="sxs-lookup"><span data-stu-id="cbe8b-108">Column</span></span></th>
<th><span data-ttu-id="cbe8b-109">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="cbe8b-109">Data Type</span></span></th>
<th><span data-ttu-id="cbe8b-110">Detalles</span><span class="sxs-lookup"><span data-stu-id="cbe8b-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cbe8b-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="cbe8b-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="cbe8b-112">datetime</span><span class="sxs-lookup"><span data-stu-id="cbe8b-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="cbe8b-113">Hora de error.</span><span class="sxs-lookup"><span data-stu-id="cbe8b-113">Time of error occurred.</span></span> <span data-ttu-id="cbe8b-114">Se usa junto con ErrorReportSeq para identificar de forma única un error.</span><span class="sxs-lookup"><span data-stu-id="cbe8b-114">Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbe8b-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="cbe8b-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="cbe8b-116">int</span><span class="sxs-lookup"><span data-stu-id="cbe8b-116">int</span></span></p></td>
<td><p><span data-ttu-id="cbe8b-117">Número de identificación para identificar el error.</span><span class="sxs-lookup"><span data-stu-id="cbe8b-117">ID number to identify the error.</span></span> <span data-ttu-id="cbe8b-118">Se usa junto con ErrorTime para identificar de forma única un error.</span><span class="sxs-lookup"><span data-stu-id="cbe8b-118">Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbe8b-119"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="cbe8b-119"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="cbe8b-120">int</span><span class="sxs-lookup"><span data-stu-id="cbe8b-120">int</span></span></p></td>
<td><p><span data-ttu-id="cbe8b-121">IDENTIFICADOR de diagnóstico del informe de errores.</span><span class="sxs-lookup"><span data-stu-id="cbe8b-121">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbe8b-122"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="cbe8b-122"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="cbe8b-123">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="cbe8b-123">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="cbe8b-124">Identificador URI del usuario que originó el error.</span><span class="sxs-lookup"><span data-stu-id="cbe8b-124">URI of the user who originated the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbe8b-125"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="cbe8b-125"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="cbe8b-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="cbe8b-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="cbe8b-127">Tipo de URI del usuario que originó el error.</span><span class="sxs-lookup"><span data-stu-id="cbe8b-127">Type of URI of the user who originated the error.</span></span> <span data-ttu-id="cbe8b-128">Para obtener más información, consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cbe8b-128">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbe8b-129"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="cbe8b-129"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="cbe8b-130">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="cbe8b-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="cbe8b-131">Espacio empresarial del usuario que originó el error.</span><span class="sxs-lookup"><span data-stu-id="cbe8b-131">Tenant of the user who originated the error.</span></span> <span data-ttu-id="cbe8b-132">Para obtener más información, consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos de Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cbe8b-132">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbe8b-133"><strong>ToUr</strong></span><span class="sxs-lookup"><span data-stu-id="cbe8b-133"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="cbe8b-134">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="cbe8b-134">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="cbe8b-135">Identificador URI del usuario que era el destino del informe de errores.</span><span class="sxs-lookup"><span data-stu-id="cbe8b-135">URI of the user who was the target of the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbe8b-136"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="cbe8b-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="cbe8b-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="cbe8b-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="cbe8b-138">Tipo de URI del usuario que se dirige al informe de errores.</span><span class="sxs-lookup"><span data-stu-id="cbe8b-138">Type of URI of the user who target of the error report.</span></span> <span data-ttu-id="cbe8b-139">Para obtener más información, consulte la tabla UriTypes.</span><span class="sxs-lookup"><span data-stu-id="cbe8b-139">See the UriTypes Table for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbe8b-140"><strong>ToTenant</strong></span><span class="sxs-lookup"><span data-stu-id="cbe8b-140"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="cbe8b-141">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="cbe8b-141">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="cbe8b-142">Espacio empresarial del usuario que se dirige al informe de errores.</span><span class="sxs-lookup"><span data-stu-id="cbe8b-142">Tenant of the user who target of the error report.</span></span> <span data-ttu-id="cbe8b-143">Para obtener más información, consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos de Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cbe8b-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbe8b-144"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="cbe8b-144"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="cbe8b-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="cbe8b-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="cbe8b-146">URI de la Conferencia que era el destino del informe de errores.</span><span class="sxs-lookup"><span data-stu-id="cbe8b-146">URI of the conference that was the target of the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbe8b-147"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="cbe8b-147"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="cbe8b-148">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="cbe8b-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="cbe8b-149">Tipo de URI de la Conferencia que era el destino del informe de errores.</span><span class="sxs-lookup"><span data-stu-id="cbe8b-149">URI type of the conference that was the target of the error report.</span></span> <span data-ttu-id="cbe8b-150">Para obtener más información, consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cbe8b-150">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbe8b-151"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="cbe8b-151"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="cbe8b-152">datetime</span><span class="sxs-lookup"><span data-stu-id="cbe8b-152">datetime</span></span></p></td>
<td><p><span data-ttu-id="cbe8b-153">Hora de la solicitud de sesión que originó el informe de errores.</span><span class="sxs-lookup"><span data-stu-id="cbe8b-153">Time of session request that originated the error report.</span></span> <span data-ttu-id="cbe8b-154">Se usa en conjunción con SessionIdSeq para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="cbe8b-154">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="cbe8b-155">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cbe8b-155">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbe8b-156"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="cbe8b-156"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="cbe8b-157">int</span><span class="sxs-lookup"><span data-stu-id="cbe8b-157">int</span></span></p></td>
<td><p><span data-ttu-id="cbe8b-158">Número de identificación para identificar la solicitud de sesión que originó el informe de errores.</span><span class="sxs-lookup"><span data-stu-id="cbe8b-158">ID number to identify the session request that originated the error report.</span></span> <span data-ttu-id="cbe8b-159">Se usa en conjunción con SessionIdTime para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="cbe8b-159">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="cbe8b-160">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cbe8b-160">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbe8b-161"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="cbe8b-161"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="cbe8b-162">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="cbe8b-162">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="cbe8b-163">IDENTIFICADOR del cuadro de diálogo SIP de la sesión que originó el error.</span><span class="sxs-lookup"><span data-stu-id="cbe8b-163">SIP dialog ID of session that originated the error.</span></span> <span data-ttu-id="cbe8b-164">El formato es:</span><span class="sxs-lookup"><span data-stu-id="cbe8b-164">The format is:</span></span></p>
<p><span data-ttu-id="cbe8b-165">cuadro de diálogo; desde: etiqueta; to-Tag</span><span class="sxs-lookup"><span data-stu-id="cbe8b-165">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="cbe8b-166">Estos datos se pueden convertir a formato de texto con esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="cbe8b-166">This data can be converted to text format by using this syntax:</span></span></p>
<p><span data-ttu-id="cbe8b-167">CAST (Cast) (ExternalId as varbinary (Max)) as VARCHAR (Max))</span><span class="sxs-lookup"><span data-stu-id="cbe8b-167">cast(cast(ExternalId as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbe8b-168"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="cbe8b-168"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="cbe8b-169">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="cbe8b-169">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="cbe8b-170">Versión del cliente utilizada por el usuario que originó el error.</span><span class="sxs-lookup"><span data-stu-id="cbe8b-170">Version of client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbe8b-171"><strong>Tipocliente</strong></span><span class="sxs-lookup"><span data-stu-id="cbe8b-171"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="cbe8b-172">int</span><span class="sxs-lookup"><span data-stu-id="cbe8b-172">int</span></span></p></td>
<td><p><span data-ttu-id="cbe8b-173">Cliente usado por el usuario que originó el error.</span><span class="sxs-lookup"><span data-stu-id="cbe8b-173">Client used by the user who originated the error.</span></span> <span data-ttu-id="cbe8b-174">Para obtener más información, consulte la <a href="lync-server-2013-useragentdef-table.md">tabla UserAgentDef en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cbe8b-174">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbe8b-175"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="cbe8b-175"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="cbe8b-176">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="cbe8b-176">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="cbe8b-177">Nombre de la categoría del cliente que ha usado el usuario que originó el error.</span><span class="sxs-lookup"><span data-stu-id="cbe8b-177">Name of the category of the client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbe8b-178"><strong>Origen</strong></span><span class="sxs-lookup"><span data-stu-id="cbe8b-178"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="cbe8b-179">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="cbe8b-179">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="cbe8b-180">Nombre del servidor que originó el error (si el informe fue enviado desde un componente de servidor).</span><span class="sxs-lookup"><span data-stu-id="cbe8b-180">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbe8b-181"><strong>Aplicación</strong></span><span class="sxs-lookup"><span data-stu-id="cbe8b-181"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="cbe8b-182">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="cbe8b-182">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="cbe8b-183">Nombre de la aplicación que originó el error (si el informe fue enviado desde un componente de servidor).</span><span class="sxs-lookup"><span data-stu-id="cbe8b-183">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbe8b-184"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="cbe8b-184"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="cbe8b-185">int</span><span class="sxs-lookup"><span data-stu-id="cbe8b-185">int</span></span></p></td>
<td><p><span data-ttu-id="cbe8b-186">Código de respuesta SIP a la sesión del mensaje SIP que contiene el informe de errores.</span><span class="sxs-lookup"><span data-stu-id="cbe8b-186">SIP response code to the session of the SIP message containing the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbe8b-187"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="cbe8b-187"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="cbe8b-188">VARCHAR (Max)</span><span class="sxs-lookup"><span data-stu-id="cbe8b-188">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="cbe8b-189">Tipo de solicitud en la que se produjo un error.</span><span class="sxs-lookup"><span data-stu-id="cbe8b-189">Type of request that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbe8b-190"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="cbe8b-190"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="cbe8b-191">VARCHAR (Max)</span><span class="sxs-lookup"><span data-stu-id="cbe8b-191">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="cbe8b-192">Tipo de contenido de la solicitud en la que se produjo un error.</span><span class="sxs-lookup"><span data-stu-id="cbe8b-192">Content type of the request that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbe8b-193"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="cbe8b-193"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="cbe8b-194">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="cbe8b-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="cbe8b-195">Tipo de sesión.</span><span class="sxs-lookup"><span data-stu-id="cbe8b-195">Type of session.</span></span> <span data-ttu-id="cbe8b-196">Para obtener más información, consulte la <a href="lync-server-2013-calltype-table.md">tabla CallType en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cbe8b-196">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbe8b-197"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="cbe8b-197"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="cbe8b-198">identificador</span><span class="sxs-lookup"><span data-stu-id="cbe8b-198">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="cbe8b-199">Identificador único que correlaciona información de tiempo de Unión para los distintos componentes implicados en una conferencia.</span><span class="sxs-lookup"><span data-stu-id="cbe8b-199">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbe8b-200"><strong>SetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="cbe8b-200"><strong>SetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="cbe8b-201">int</span><span class="sxs-lookup"><span data-stu-id="cbe8b-201">int</span></span></p></td>
<td><p><span data-ttu-id="cbe8b-202">Tiempo (en milisegundos) necesario para que un componente específico se una a una conferencia.</span><span class="sxs-lookup"><span data-stu-id="cbe8b-202">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbe8b-203"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="cbe8b-203"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="cbe8b-204">bit</span><span class="sxs-lookup"><span data-stu-id="cbe8b-204">bit</span></span></p></td>
<td><p><span data-ttu-id="cbe8b-205">Indica si el informe de errores fue capturado por el agente CDR que se ejecuta en el servidor front-end o enviado por el cliente.</span><span class="sxs-lookup"><span data-stu-id="cbe8b-205">Indicates whether the error report was captured by the CDR agent running on the Front End server, or sent by the client.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbe8b-206"><strong>Fdisableautoindexingonschemaupdate</strong></span><span class="sxs-lookup"><span data-stu-id="cbe8b-206"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="cbe8b-207">smallint</span><span class="sxs-lookup"><span data-stu-id="cbe8b-207">smallint</span></span></p></td>
<td><p><span data-ttu-id="cbe8b-208">Reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="cbe8b-208">Reserved for future use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbe8b-209"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="cbe8b-209"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="cbe8b-210">VARCHAR (Max)</span><span class="sxs-lookup"><span data-stu-id="cbe8b-210">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="cbe8b-211">Información adicional sobre el error.</span><span class="sxs-lookup"><span data-stu-id="cbe8b-211">Additional information about the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbe8b-212"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="cbe8b-212"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="cbe8b-213">nvarchar</span><span class="sxs-lookup"><span data-stu-id="cbe8b-213">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="cbe8b-214">Nombre de dominio completo del servidor front-end que ha enviado el informe.</span><span class="sxs-lookup"><span data-stu-id="cbe8b-214">Fully qualified domain name of the Front End server that submitted the report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbe8b-215"><strong>Grupo</strong></span><span class="sxs-lookup"><span data-stu-id="cbe8b-215"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="cbe8b-216">nvarchar</span><span class="sxs-lookup"><span data-stu-id="cbe8b-216">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="cbe8b-217">Nombre de dominio completo del grupo que contiene el servidor front-end que ha enviado el informe.</span><span class="sxs-lookup"><span data-stu-id="cbe8b-217">Fully qualified domain name of the pool containing the Front End server that submitted the report.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

