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
ms.openlocfilehash: a6eb6de7f2ba23d52a7b508869dbb25c9c5e3802
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514497"
---
# <a name="diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="cf7ff-102">Informe de diagnósticos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf7ff-102">Diagnostic Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf7ff-103">_**Última modificación del tema:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="cf7ff-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="cf7ff-104">El informe de diagnóstico ofrece información de diagnóstico y solución de problemas para una sesión con error.</span><span class="sxs-lookup"><span data-stu-id="cf7ff-104">The Diagnostic Report provides diagnostic and troubleshooting information for a failed session.</span></span> <span data-ttu-id="cf7ff-105">Esta información incluye el identificador de diagnóstico y el encabezado de diagnóstico que se notificaron cuando se produjo un error en la sesión.</span><span class="sxs-lookup"><span data-stu-id="cf7ff-105">This information includes both the Diagnostic ID and the Diagnostic header that were reported when the session failed.</span></span> <span data-ttu-id="cf7ff-106">El identificador de diagnóstico es un identificador único (en forma de un encabezado MS-Diagnostics) que se adjunta a un mensaje SIP, mientras que el encabezado de diagnóstico proporciona una descripción complementaria del identificador de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="cf7ff-106">The Diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) that gets attached to a SIP message, while the Diagnostic header provides an accompanying description for the Diagnostic ID.</span></span> <span data-ttu-id="cf7ff-107">El informe también puede contener detalles de solución de problemas valiosos que el componente de informes conoce.</span><span class="sxs-lookup"><span data-stu-id="cf7ff-107">The report might also contain valuable troubleshooting details that are known by the reporting component.</span></span> <span data-ttu-id="cf7ff-108">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="cf7ff-108">For example:</span></span>

  - <span data-ttu-id="cf7ff-109">El código de causa proporcionado por la puerta de enlace RTC que generó el error.</span><span class="sxs-lookup"><span data-stu-id="cf7ff-109">The cause code provided by the PSTN gateway that generated the failure.</span></span> <span data-ttu-id="cf7ff-110">Cuando se produce un error en una llamada realizada en la red RTC, se genera automáticamente un código de causa de parte del usuario RDSI (ISUP).</span><span class="sxs-lookup"><span data-stu-id="cf7ff-110">When an outgoing call fails on the PSTN network, an ISDN User Part (ISUP) cause code is automatically generated.</span></span> <span data-ttu-id="cf7ff-111">Por ejemplo, una puerta de enlace RTC podría enviar el código de causa 34 para indicar que no se disponía de ningún circuito ni canal para completar la llamada.</span><span class="sxs-lookup"><span data-stu-id="cf7ff-111">For example, a PSTN gateway might send cause code 34 to indicate that no circuit or channel was available for completing the call.</span></span>

  - <span data-ttu-id="cf7ff-112">Errores de conectividad, puerto y FQDN del mismo nivel para errores de conectividad.</span><span class="sxs-lookup"><span data-stu-id="cf7ff-112">Peer FQDN, port, and Winsock errors for connectivity failures.</span></span>

  - <span data-ttu-id="cf7ff-113">Nombres que se buscan en busca de errores de resolución DNS.</span><span class="sxs-lookup"><span data-stu-id="cf7ff-113">Names being looked up for DNS resolution failures.</span></span> <span data-ttu-id="cf7ff-114">La resolución DNS tiene su comportamiento cada vez que un cliente se pone en contacto con un servidor de nombres y solicita la dirección IP que corresponde al nombre de dispositivo especificado.</span><span class="sxs-lookup"><span data-stu-id="cf7ff-114">DNS resolution takes place any time a client contacts a name server and requests the IP address that corresponds to specified device name.</span></span>

<div>

## <a name="accessing-the-diagnostic-report"></a><span data-ttu-id="cf7ff-115">Acceso al informe de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="cf7ff-115">Accessing the Diagnostic Report</span></span>

<span data-ttu-id="cf7ff-116">Para obtener acceso al informe de diagnóstico, haga clic en la métrica informe de diagnóstico (detalle) en el [Informe de detalles de sesiones punto a punto en Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) o en el informe de detalles de conferencia.</span><span class="sxs-lookup"><span data-stu-id="cf7ff-116">The Diagnostic Report can be accessed by clicking the Diagnostic Report (Detail) metric on either the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) or the Conference Detail Report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="cf7ff-117">Filtros</span><span class="sxs-lookup"><span data-stu-id="cf7ff-117">Filters</span></span>

<span data-ttu-id="cf7ff-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="cf7ff-118">None.</span></span> <span data-ttu-id="cf7ff-119">No se puede filtrar el informe de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="cf7ff-119">You cannot filter the Diagnostic Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="cf7ff-120">Métricas</span><span class="sxs-lookup"><span data-stu-id="cf7ff-120">Metrics</span></span>

<span data-ttu-id="cf7ff-121">En la siguiente tabla se muestra la información proporcionada en el informe de diagnóstico para cada sesión.</span><span class="sxs-lookup"><span data-stu-id="cf7ff-121">The following table lists the information provided in the Diagnostic Report for each session.</span></span>

### <a name="diagnostic-report-metrics"></a><span data-ttu-id="cf7ff-122">Métricas del informe de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="cf7ff-122">Diagnostic Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cf7ff-123">Nombre</span><span class="sxs-lookup"><span data-stu-id="cf7ff-123">Name</span></span></th>
<th><span data-ttu-id="cf7ff-124">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="cf7ff-124">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="cf7ff-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="cf7ff-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf7ff-126"><strong>Hora del informe</strong></span><span class="sxs-lookup"><span data-stu-id="cf7ff-126"><strong>Report time</strong></span></span></p></td>
<td><p><span data-ttu-id="cf7ff-127">No</span><span class="sxs-lookup"><span data-stu-id="cf7ff-127">No</span></span></p></td>
<td><p><span data-ttu-id="cf7ff-128">Fecha y hora en que se registró el informe.</span><span class="sxs-lookup"><span data-stu-id="cf7ff-128">Date and time that the report was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf7ff-129"><strong>Código de respuesta</strong></span><span class="sxs-lookup"><span data-stu-id="cf7ff-129"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="cf7ff-130">No</span><span class="sxs-lookup"><span data-stu-id="cf7ff-130">No</span></span></p></td>
<td><p><span data-ttu-id="cf7ff-131">Código de respuesta SIP enviado cuando se produjo un error en la sesión.</span><span class="sxs-lookup"><span data-stu-id="cf7ff-131">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf7ff-132"><strong>Tipo de solicitud</strong></span><span class="sxs-lookup"><span data-stu-id="cf7ff-132"><strong>Request type</strong></span></span></p></td>
<td><p><span data-ttu-id="cf7ff-133">No</span><span class="sxs-lookup"><span data-stu-id="cf7ff-133">No</span></span></p></td>
<td><p><span data-ttu-id="cf7ff-134">Tipo de solicitud SIP fallida.</span><span class="sxs-lookup"><span data-stu-id="cf7ff-134">SIP request type that failed.</span></span> <span data-ttu-id="cf7ff-135">Por ejemplo, INVITE, BYE o SERVICE.</span><span class="sxs-lookup"><span data-stu-id="cf7ff-135">For example, INVITE, BYE, or SERVICE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf7ff-136"><strong>Source</strong></span><span class="sxs-lookup"><span data-stu-id="cf7ff-136"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="cf7ff-137">No</span><span class="sxs-lookup"><span data-stu-id="cf7ff-137">No</span></span></p></td>
<td><p><span data-ttu-id="cf7ff-138">Origen del error.</span><span class="sxs-lookup"><span data-stu-id="cf7ff-138">Source of the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf7ff-139"><strong>URI de usuario de remitente</strong></span><span class="sxs-lookup"><span data-stu-id="cf7ff-139"><strong>From user URI</strong></span></span></p></td>
<td><p><span data-ttu-id="cf7ff-140">No</span><span class="sxs-lookup"><span data-stu-id="cf7ff-140">No</span></span></p></td>
<td><p><span data-ttu-id="cf7ff-141">Dirección SIP del usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="cf7ff-141">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf7ff-142"><strong>Agente de remitente</strong></span><span class="sxs-lookup"><span data-stu-id="cf7ff-142"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="cf7ff-143">No</span><span class="sxs-lookup"><span data-stu-id="cf7ff-143">No</span></span></p></td>
<td><p><span data-ttu-id="cf7ff-144">Software que utiliza el extremo del usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="cf7ff-144">Software used by the endpoint of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf7ff-145"><strong>Id. de diagnóstico</strong></span><span class="sxs-lookup"><span data-stu-id="cf7ff-145"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="cf7ff-146">No</span><span class="sxs-lookup"><span data-stu-id="cf7ff-146">No</span></span></p></td>
<td><p><span data-ttu-id="cf7ff-147">Identificador único (en forma de encabezado de tipo ms-diagnostics) que se adjunta a un mensaje SIP y que suele ofrecer información de utilidad para resolver errores.</span><span class="sxs-lookup"><span data-stu-id="cf7ff-147">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf7ff-148"><strong>Tipo de contenido</strong></span><span class="sxs-lookup"><span data-stu-id="cf7ff-148"><strong>Content type</strong></span></span></p></td>
<td><p><span data-ttu-id="cf7ff-149">No</span><span class="sxs-lookup"><span data-stu-id="cf7ff-149">No</span></span></p></td>
<td><p><span data-ttu-id="cf7ff-150">Tipo de contenido multimedia con errores.</span><span class="sxs-lookup"><span data-stu-id="cf7ff-150">Type of media content that failed.</span></span> <span data-ttu-id="cf7ff-151">Por ejemplo, un tipo de contenido común es Application/SDP.</span><span class="sxs-lookup"><span data-stu-id="cf7ff-151">For example, a common content type is Application/sdp.</span></span> <span data-ttu-id="cf7ff-152">Session Description Protocol (SDP) es un protocolo estándar de Internet que se usa para anuncios de sesiones, invitaciones a sesiones y otras formas de inicio de sesión multimedia.</span><span class="sxs-lookup"><span data-stu-id="cf7ff-152">Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf7ff-153"><strong>Aplicación</strong></span><span class="sxs-lookup"><span data-stu-id="cf7ff-153"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="cf7ff-154">No</span><span class="sxs-lookup"><span data-stu-id="cf7ff-154">No</span></span></p></td>
<td><p><span data-ttu-id="cf7ff-155">Aplicación implicada en el error.</span><span class="sxs-lookup"><span data-stu-id="cf7ff-155">Application involved in the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf7ff-156"><strong>URI de usuario</strong></span><span class="sxs-lookup"><span data-stu-id="cf7ff-156"><strong>To user URI</strong></span></span></p></td>
<td><p><span data-ttu-id="cf7ff-157">No</span><span class="sxs-lookup"><span data-stu-id="cf7ff-157">No</span></span></p></td>
<td><p><span data-ttu-id="cf7ff-158">Dirección SIP del usuario invitado a la sesión.</span><span class="sxs-lookup"><span data-stu-id="cf7ff-158">SIP address of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf7ff-159">Tiempos de combinación de conferencia (MS)</span><span class="sxs-lookup"><span data-stu-id="cf7ff-159">Conference join times (ms)</span></span></p></td>
<td><p><span data-ttu-id="cf7ff-160">No</span><span class="sxs-lookup"><span data-stu-id="cf7ff-160">No</span></span></p></td>
<td><p><span data-ttu-id="cf7ff-161">Cantidad de tiempo (en milisegundos) que tardó el usuario en unirse a la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="cf7ff-161">Amount of time (in milliseconds) it took for the user to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf7ff-162"><strong>Encabezado de diagnóstico</strong></span><span class="sxs-lookup"><span data-stu-id="cf7ff-162"><strong>Diagnostic header</strong></span></span></p></td>
<td><p><span data-ttu-id="cf7ff-163">No</span><span class="sxs-lookup"><span data-stu-id="cf7ff-163">No</span></span></p></td>
<td><p><span data-ttu-id="cf7ff-164">Descripción del identificador de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="cf7ff-164">Diagnostic ID description.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="cf7ff-165">Se puede encontrar una lista de errores de diagnóstico en la [Página de encabezado de MS-Diagnostics](https://msdn.microsoft.com/library/gg132446\(v=office.12\).aspx).</span><span class="sxs-lookup"><span data-stu-id="cf7ff-165">A list of diagnostic errors can be found on the [Ms-Diagnostics Header page](https://msdn.microsoft.com/library/gg132446\(v=office.12\).aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

