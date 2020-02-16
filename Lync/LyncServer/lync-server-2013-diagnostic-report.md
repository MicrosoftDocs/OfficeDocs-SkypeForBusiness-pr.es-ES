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
ms.openlocfilehash: a906e131329df1b59c4ac6067a4696871f0bebfc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044842"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="c54c5-102">Informe de diagnósticos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c54c5-102">Diagnostic Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c54c5-103">_**Última modificación del tema:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="c54c5-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="c54c5-104">El informe de diagnóstico ofrece información de diagnóstico y solución de problemas para una sesión con error.</span><span class="sxs-lookup"><span data-stu-id="c54c5-104">The Diagnostic Report provides diagnostic and troubleshooting information for a failed session.</span></span> <span data-ttu-id="c54c5-105">Esta información incluye el identificador de diagnóstico y el encabezado de diagnóstico que se notificaron cuando se produjo un error en la sesión.</span><span class="sxs-lookup"><span data-stu-id="c54c5-105">This information includes both the Diagnostic ID and the Diagnostic header that were reported when the session failed.</span></span> <span data-ttu-id="c54c5-106">El identificador de diagnóstico es un identificador único (en forma de un encabezado MS-Diagnostics) que se adjunta a un mensaje SIP, mientras que el encabezado de diagnóstico proporciona una descripción complementaria del identificador de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="c54c5-106">The Diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) that gets attached to a SIP message, while the Diagnostic header provides an accompanying description for the Diagnostic ID.</span></span> <span data-ttu-id="c54c5-107">El informe también puede contener detalles de solución de problemas valiosos que el componente de informes conoce.</span><span class="sxs-lookup"><span data-stu-id="c54c5-107">The report might also contain valuable troubleshooting details that are known by the reporting component.</span></span> <span data-ttu-id="c54c5-108">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c54c5-108">For example:</span></span>

  - <span data-ttu-id="c54c5-109">El código de causa proporcionado por la puerta de enlace RTC que generó el error.</span><span class="sxs-lookup"><span data-stu-id="c54c5-109">The cause code provided by the PSTN gateway that generated the failure.</span></span> <span data-ttu-id="c54c5-110">Cuando se produce un error en una llamada realizada en la red RTC, se genera automáticamente un código de causa de parte del usuario RDSI (ISUP).</span><span class="sxs-lookup"><span data-stu-id="c54c5-110">When an outgoing call fails on the PSTN network, an ISDN User Part (ISUP) cause code is automatically generated.</span></span> <span data-ttu-id="c54c5-111">Por ejemplo, una puerta de enlace RTC podría enviar el código de causa 34 para indicar que no se disponía de ningún circuito ni canal para completar la llamada.</span><span class="sxs-lookup"><span data-stu-id="c54c5-111">For example, a PSTN gateway might send cause code 34 to indicate that no circuit or channel was available for completing the call.</span></span>

  - <span data-ttu-id="c54c5-112">Errores de conectividad, puerto y FQDN del mismo nivel para errores de conectividad.</span><span class="sxs-lookup"><span data-stu-id="c54c5-112">Peer FQDN, port, and Winsock errors for connectivity failures.</span></span>

  - <span data-ttu-id="c54c5-113">Nombres que se buscan en busca de errores de resolución DNS.</span><span class="sxs-lookup"><span data-stu-id="c54c5-113">Names being looked up for DNS resolution failures.</span></span> <span data-ttu-id="c54c5-114">La resolución DNS tiene su comportamiento cada vez que un cliente se pone en contacto con un servidor de nombres y solicita la dirección IP que corresponde al nombre de dispositivo especificado.</span><span class="sxs-lookup"><span data-stu-id="c54c5-114">DNS resolution takes place any time a client contacts a name server and requests the IP address that corresponds to specified device name.</span></span>

<div>

## <a name="accessing-the-diagnostic-report"></a><span data-ttu-id="c54c5-115">Acceso al informe de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="c54c5-115">Accessing the Diagnostic Report</span></span>

<span data-ttu-id="c54c5-116">Para obtener acceso al informe de diagnóstico, haga clic en la métrica informe de diagnóstico (detalle) en el [Informe de detalles de sesiones punto a punto en Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) o en el informe de detalles de conferencia.</span><span class="sxs-lookup"><span data-stu-id="c54c5-116">The Diagnostic Report can be accessed by clicking the Diagnostic Report (Detail) metric on either the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) or the Conference Detail Report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="c54c5-117">Filtros</span><span class="sxs-lookup"><span data-stu-id="c54c5-117">Filters</span></span>

<span data-ttu-id="c54c5-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c54c5-118">None.</span></span> <span data-ttu-id="c54c5-119">No se puede filtrar el informe de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="c54c5-119">You cannot filter the Diagnostic Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="c54c5-120">Métricas</span><span class="sxs-lookup"><span data-stu-id="c54c5-120">Metrics</span></span>

<span data-ttu-id="c54c5-121">En la siguiente tabla se muestra la información proporcionada en el informe de diagnóstico para cada sesión.</span><span class="sxs-lookup"><span data-stu-id="c54c5-121">The following table lists the information provided in the Diagnostic Report for each session.</span></span>

### <a name="diagnostic-report-metrics"></a><span data-ttu-id="c54c5-122">Métricas del informe de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="c54c5-122">Diagnostic Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c54c5-123">Nombre</span><span class="sxs-lookup"><span data-stu-id="c54c5-123">Name</span></span></th>
<th><span data-ttu-id="c54c5-124">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="c54c5-124">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c54c5-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="c54c5-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c54c5-126"><strong>Hora del informe</strong></span><span class="sxs-lookup"><span data-stu-id="c54c5-126"><strong>Report time</strong></span></span></p></td>
<td><p><span data-ttu-id="c54c5-127">No</span><span class="sxs-lookup"><span data-stu-id="c54c5-127">No</span></span></p></td>
<td><p><span data-ttu-id="c54c5-128">Fecha y hora en que se registró el informe.</span><span class="sxs-lookup"><span data-stu-id="c54c5-128">Date and time that the report was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c54c5-129"><strong>Código de respuesta</strong></span><span class="sxs-lookup"><span data-stu-id="c54c5-129"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="c54c5-130">No</span><span class="sxs-lookup"><span data-stu-id="c54c5-130">No</span></span></p></td>
<td><p><span data-ttu-id="c54c5-131">Código de respuesta SIP enviado cuando se produjo un error en la sesión.</span><span class="sxs-lookup"><span data-stu-id="c54c5-131">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c54c5-132"><strong>Tipo de solicitud</strong></span><span class="sxs-lookup"><span data-stu-id="c54c5-132"><strong>Request type</strong></span></span></p></td>
<td><p><span data-ttu-id="c54c5-133">No</span><span class="sxs-lookup"><span data-stu-id="c54c5-133">No</span></span></p></td>
<td><p><span data-ttu-id="c54c5-134">Tipo de solicitud SIP fallida.</span><span class="sxs-lookup"><span data-stu-id="c54c5-134">SIP request type that failed.</span></span> <span data-ttu-id="c54c5-135">Por ejemplo, INVITE, BYE o SERVICE.</span><span class="sxs-lookup"><span data-stu-id="c54c5-135">For example, INVITE, BYE, or SERVICE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c54c5-136"><strong>Source</strong></span><span class="sxs-lookup"><span data-stu-id="c54c5-136"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="c54c5-137">No</span><span class="sxs-lookup"><span data-stu-id="c54c5-137">No</span></span></p></td>
<td><p><span data-ttu-id="c54c5-138">Origen del error.</span><span class="sxs-lookup"><span data-stu-id="c54c5-138">Source of the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c54c5-139"><strong>URI de usuario de remitente</strong></span><span class="sxs-lookup"><span data-stu-id="c54c5-139"><strong>From user URI</strong></span></span></p></td>
<td><p><span data-ttu-id="c54c5-140">No</span><span class="sxs-lookup"><span data-stu-id="c54c5-140">No</span></span></p></td>
<td><p><span data-ttu-id="c54c5-141">Dirección SIP del usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="c54c5-141">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c54c5-142"><strong>Agente de remitente</strong></span><span class="sxs-lookup"><span data-stu-id="c54c5-142"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="c54c5-143">No</span><span class="sxs-lookup"><span data-stu-id="c54c5-143">No</span></span></p></td>
<td><p><span data-ttu-id="c54c5-144">Software que utiliza el extremo del usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="c54c5-144">Software used by the endpoint of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c54c5-145"><strong>Id. de diagnóstico</strong></span><span class="sxs-lookup"><span data-stu-id="c54c5-145"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="c54c5-146">No</span><span class="sxs-lookup"><span data-stu-id="c54c5-146">No</span></span></p></td>
<td><p><span data-ttu-id="c54c5-147">Identificador único (en forma de encabezado de tipo ms-diagnostics) que se adjunta a un mensaje SIP y que suele ofrecer información de utilidad para resolver errores.</span><span class="sxs-lookup"><span data-stu-id="c54c5-147">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c54c5-148"><strong>Tipo de contenido</strong></span><span class="sxs-lookup"><span data-stu-id="c54c5-148"><strong>Content type</strong></span></span></p></td>
<td><p><span data-ttu-id="c54c5-149">No</span><span class="sxs-lookup"><span data-stu-id="c54c5-149">No</span></span></p></td>
<td><p><span data-ttu-id="c54c5-150">Tipo de contenido multimedia con errores.</span><span class="sxs-lookup"><span data-stu-id="c54c5-150">Type of media content that failed.</span></span> <span data-ttu-id="c54c5-151">Por ejemplo, un tipo de contenido común es Application/SDP.</span><span class="sxs-lookup"><span data-stu-id="c54c5-151">For example, a common content type is Application/sdp.</span></span> <span data-ttu-id="c54c5-152">Session Description Protocol (SDP) es un protocolo estándar de Internet que se usa para anuncios de sesiones, invitaciones a sesiones y otras formas de inicio de sesión multimedia.</span><span class="sxs-lookup"><span data-stu-id="c54c5-152">Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c54c5-153"><strong>Aplicación</strong></span><span class="sxs-lookup"><span data-stu-id="c54c5-153"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="c54c5-154">No</span><span class="sxs-lookup"><span data-stu-id="c54c5-154">No</span></span></p></td>
<td><p><span data-ttu-id="c54c5-155">Aplicación implicada en el error.</span><span class="sxs-lookup"><span data-stu-id="c54c5-155">Application involved in the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c54c5-156"><strong>URI de usuario</strong></span><span class="sxs-lookup"><span data-stu-id="c54c5-156"><strong>To user URI</strong></span></span></p></td>
<td><p><span data-ttu-id="c54c5-157">No</span><span class="sxs-lookup"><span data-stu-id="c54c5-157">No</span></span></p></td>
<td><p><span data-ttu-id="c54c5-158">Dirección SIP del usuario invitado a la sesión.</span><span class="sxs-lookup"><span data-stu-id="c54c5-158">SIP address of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c54c5-159">Tiempos de combinación de conferencia (MS)</span><span class="sxs-lookup"><span data-stu-id="c54c5-159">Conference join times (ms)</span></span></p></td>
<td><p><span data-ttu-id="c54c5-160">No</span><span class="sxs-lookup"><span data-stu-id="c54c5-160">No</span></span></p></td>
<td><p><span data-ttu-id="c54c5-161">Cantidad de tiempo (en milisegundos) que tardó el usuario en unirse a la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="c54c5-161">Amount of time (in milliseconds) it took for the user to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c54c5-162"><strong>Encabezado de diagnóstico</strong></span><span class="sxs-lookup"><span data-stu-id="c54c5-162"><strong>Diagnostic header</strong></span></span></p></td>
<td><p><span data-ttu-id="c54c5-163">No</span><span class="sxs-lookup"><span data-stu-id="c54c5-163">No</span></span></p></td>
<td><p><span data-ttu-id="c54c5-164">Descripción del identificador de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="c54c5-164">Diagnostic ID description.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c54c5-165">Se puede encontrar una lista de errores de diagnóstico en la [Página de encabezado de MS-Diagnostics](http://msdn.microsoft.com/library/gg132446\(v=office.12\).aspx).</span><span class="sxs-lookup"><span data-stu-id="c54c5-165">A list of diagnostic errors can be found on the [Ms-Diagnostics Header page](http://msdn.microsoft.com/library/gg132446\(v=office.12\).aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

