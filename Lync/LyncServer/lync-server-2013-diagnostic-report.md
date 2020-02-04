---
title: 'Lync Server 2013: informe de diagnóstico'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Diagnostic Report
ms:assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615445(v=OCS.15)
ms:contentKeyID: 48185159
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14a2fa69e0e2397b970850a91042f0241060f839
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762348"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="71132-102">Informe de diagnóstico en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71132-102">Diagnostic Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71132-103">_**Última modificación del tema:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="71132-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="71132-104">El informe de diagnóstico ofrece información de diagnóstico y solución de problemas para las sesiones con errores.</span><span class="sxs-lookup"><span data-stu-id="71132-104">The Diagnostic Report provides diagnostic and troubleshooting information for a failed session.</span></span> <span data-ttu-id="71132-105">Esta información incluye el identificador de diagnóstico y el encabezado de diagnóstico que se notificaron cuando se produjo el error en la sesión.</span><span class="sxs-lookup"><span data-stu-id="71132-105">This information includes both the Diagnostic ID and the Diagnostic header that were reported when the session failed.</span></span> <span data-ttu-id="71132-106">El identificador de diagnóstico es un identificador único (con formato de encabezado ms-diagnostics) que se adjunta a un mensaje SIP, mientras que el encabezado de diagnóstico proporciona una descripción que acompaña al identificador de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="71132-106">The Diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) that gets attached to a SIP message, while the Diagnostic header provides an accompanying description for the Diagnostic ID.</span></span> <span data-ttu-id="71132-107">El informe también puede contener detalles valiosos sobre la solución de problemas conocidos por el componente del informe.</span><span class="sxs-lookup"><span data-stu-id="71132-107">The report might also contain valuable troubleshooting details that are known by the reporting component.</span></span> <span data-ttu-id="71132-108">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="71132-108">For example:</span></span>

  - <span data-ttu-id="71132-p102">El código de causa proporcionado por la puerta de enlace RTC que generó el error. Cuando una llamada saliente presenta errores en la red RTC, se genera automáticamente un código de causa ISUP (ISDN User Part). Por ejemplo, una puerta de enlace RTC puede enviar un código de causa 34 para indicar que no hay ningún canal o circuito disponible para completar la llamada.</span><span class="sxs-lookup"><span data-stu-id="71132-p102">The cause code provided by the PSTN gateway that generated the failure. When an outgoing call fails on the PSTN network, an ISDN User Part (ISUP) cause code is automatically generated. For example, a PSTN gateway might send cause code 34 to indicate that no circuit or channel was available for completing the call.</span></span>

  - <span data-ttu-id="71132-112">Errores de Winsock, puerto y FQDN del mismo nivel para detectar errores de conectividad.</span><span class="sxs-lookup"><span data-stu-id="71132-112">Peer FQDN, port, and Winsock errors for connectivity failures.</span></span>

  - <span data-ttu-id="71132-p103">Comprobación de nombres para detectar errores de resolución DNS. La resolución DNS tiene lugar cada vez que un cliente establece contacto con un servidor de nombres y solicita la dirección IP correspondiente al nombre de dispositivo especificado.</span><span class="sxs-lookup"><span data-stu-id="71132-p103">Names being looked up for DNS resolution failures. DNS resolution takes place any time a client contacts a name server and requests the IP address that corresponds to specified device name.</span></span>

<div>

## <a name="accessing-the-diagnostic-report"></a><span data-ttu-id="71132-115">Obtener acceso al informe de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="71132-115">Accessing the Diagnostic Report</span></span>

<span data-ttu-id="71132-116">Para acceder al informe de diagnóstico, haga clic en la métrica informe de diagnóstico (detalles) en el [informe detallado de sesión de punto a punto de Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) o en el informe detalles de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="71132-116">The Diagnostic Report can be accessed by clicking the Diagnostic Report (Detail) metric on either the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) or the Conference Detail Report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="71132-117">Filtros</span><span class="sxs-lookup"><span data-stu-id="71132-117">Filters</span></span>

<span data-ttu-id="71132-p104">Ninguno. No se puede filtrar el informe de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="71132-p104">None. You cannot filter the Diagnostic Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="71132-120">Métricas</span><span class="sxs-lookup"><span data-stu-id="71132-120">Metrics</span></span>

<span data-ttu-id="71132-121">En la siguiente tabla se detalla la información proporcionada en el informe de diagnóstico para cada sesión.</span><span class="sxs-lookup"><span data-stu-id="71132-121">The following table lists the information provided in the Diagnostic Report for each session.</span></span>

### <a name="diagnostic-report-metrics"></a><span data-ttu-id="71132-122">Métricas del informe de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="71132-122">Diagnostic Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="71132-123">Nombre</span><span class="sxs-lookup"><span data-stu-id="71132-123">Name</span></span></th>
<th><span data-ttu-id="71132-124">¿Se pueden ordenar los datos por este elemento?</span><span class="sxs-lookup"><span data-stu-id="71132-124">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="71132-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="71132-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="71132-126"><strong>Hora del informe</strong></span><span class="sxs-lookup"><span data-stu-id="71132-126"><strong>Report time</strong></span></span></p></td>
<td><p><span data-ttu-id="71132-127">No</span><span class="sxs-lookup"><span data-stu-id="71132-127">No</span></span></p></td>
<td><p><span data-ttu-id="71132-128">Fecha y hora en que se registró el informe.</span><span class="sxs-lookup"><span data-stu-id="71132-128">Date and time that the report was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71132-129"><strong>Código de respuesta</strong></span><span class="sxs-lookup"><span data-stu-id="71132-129"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="71132-130">No</span><span class="sxs-lookup"><span data-stu-id="71132-130">No</span></span></p></td>
<td><p><span data-ttu-id="71132-131">Código de respuesta SIP enviado cuando se produjo un error en la sesión.</span><span class="sxs-lookup"><span data-stu-id="71132-131">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71132-132"><strong>Tipo de solicitud</strong></span><span class="sxs-lookup"><span data-stu-id="71132-132"><strong>Request type</strong></span></span></p></td>
<td><p><span data-ttu-id="71132-133">No</span><span class="sxs-lookup"><span data-stu-id="71132-133">No</span></span></p></td>
<td><p><span data-ttu-id="71132-p105">Tipo de solicitud SIP que presentó errores. Por ejemplo, INVITE, BYE o SERVICE.</span><span class="sxs-lookup"><span data-stu-id="71132-p105">SIP request type that failed. For example, INVITE, BYE, or SERVICE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71132-136"><strong>Origen</strong></span><span class="sxs-lookup"><span data-stu-id="71132-136"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="71132-137">No</span><span class="sxs-lookup"><span data-stu-id="71132-137">No</span></span></p></td>
<td><p><span data-ttu-id="71132-138">Origen del error.</span><span class="sxs-lookup"><span data-stu-id="71132-138">Source of the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71132-139"><strong>URI de remitente</strong></span><span class="sxs-lookup"><span data-stu-id="71132-139"><strong>From user URI</strong></span></span></p></td>
<td><p><span data-ttu-id="71132-140">No</span><span class="sxs-lookup"><span data-stu-id="71132-140">No</span></span></p></td>
<td><p><span data-ttu-id="71132-141">Dirección SIP del usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="71132-141">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71132-142"><strong>Agente de remitente</strong></span><span class="sxs-lookup"><span data-stu-id="71132-142"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="71132-143">No</span><span class="sxs-lookup"><span data-stu-id="71132-143">No</span></span></p></td>
<td><p><span data-ttu-id="71132-144">Software usado por el extremo del usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="71132-144">Software used by the endpoint of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71132-145"><strong>Id. de diagnóstico</strong></span><span class="sxs-lookup"><span data-stu-id="71132-145"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="71132-146">No</span><span class="sxs-lookup"><span data-stu-id="71132-146">No</span></span></p></td>
<td><p><span data-ttu-id="71132-147">Identificador único (con formato de encabezado de ms-diagnostics) adjunto a un mensaje SIP que a menudo aporta información útil para solucionar errores.</span><span class="sxs-lookup"><span data-stu-id="71132-147">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71132-148"><strong>Tipo de contenido</strong></span><span class="sxs-lookup"><span data-stu-id="71132-148"><strong>Content type</strong></span></span></p></td>
<td><p><span data-ttu-id="71132-149">No</span><span class="sxs-lookup"><span data-stu-id="71132-149">No</span></span></p></td>
<td><p><span data-ttu-id="71132-p106">Tipo de contenido multimedia que presentó errores. Un ejemplo de tipo de contenido habitual es Application/sdp. Session Description Protocol (SDP) es un protocolo estándar de Internet que se usa para anuncios e invitaciones de sesiones, y otras formas de iniciar sesiones multimedia.</span><span class="sxs-lookup"><span data-stu-id="71132-p106">Type of media content that failed. For example, a common content type is Application/sdp. Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71132-153"><strong>Aplicación</strong></span><span class="sxs-lookup"><span data-stu-id="71132-153"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="71132-154">No</span><span class="sxs-lookup"><span data-stu-id="71132-154">No</span></span></p></td>
<td><p><span data-ttu-id="71132-155">Aplicación a la que corresponde el error.</span><span class="sxs-lookup"><span data-stu-id="71132-155">Application involved in the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71132-156"><strong>URI de destinatario</strong></span><span class="sxs-lookup"><span data-stu-id="71132-156"><strong>To user URI</strong></span></span></p></td>
<td><p><span data-ttu-id="71132-157">No</span><span class="sxs-lookup"><span data-stu-id="71132-157">No</span></span></p></td>
<td><p><span data-ttu-id="71132-158">Dirección SIP del usuario invitado a la sesión.</span><span class="sxs-lookup"><span data-stu-id="71132-158">SIP address of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71132-159">Tiempo en unirse a conferencia (ms)</span><span class="sxs-lookup"><span data-stu-id="71132-159">Conference join times (ms)</span></span></p></td>
<td><p><span data-ttu-id="71132-160">No</span><span class="sxs-lookup"><span data-stu-id="71132-160">No</span></span></p></td>
<td><p><span data-ttu-id="71132-161">Cantidad de tiempo (en milisegundos) que tardó el usuario en unirse a la conferencia.</span><span class="sxs-lookup"><span data-stu-id="71132-161">Amount of time (in milliseconds) it took for the user to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71132-162"><strong>Encabezado de diagnóstico</strong></span><span class="sxs-lookup"><span data-stu-id="71132-162"><strong>Diagnostic header</strong></span></span></p></td>
<td><p><span data-ttu-id="71132-163">No</span><span class="sxs-lookup"><span data-stu-id="71132-163">No</span></span></p></td>
<td><p><span data-ttu-id="71132-164">Descripción del identificador de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="71132-164">Diagnostic ID description.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="71132-165">Puede encontrar una lista de errores de diagnóstico en la [Página de encabezado de MS-Diagnostics](http://msdn.microsoft.com/en-us/library/gg132446\(v=office.12\).aspx).</span><span class="sxs-lookup"><span data-stu-id="71132-165">A list of diagnostic errors can be found on the [Ms-Diagnostics Header page](http://msdn.microsoft.com/en-us/library/gg132446\(v=office.12\).aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

