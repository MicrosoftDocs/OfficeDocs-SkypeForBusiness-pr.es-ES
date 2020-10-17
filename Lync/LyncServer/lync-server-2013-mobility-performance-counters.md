---
title: 'Lync Server 2013: contadores de rendimiento de movilidad'
description: 'Lync Server 2013: contadores de rendimiento de movilidad.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobility performance counters
ms:assetid: d18ed85a-673d-4695-aa3f-ac83a38ab90a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690046(v=OCS.15)
ms:contentKeyID: 48185441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 922288f6c026f088d651dc61afdcb6ba04fed30a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550536"
---
# <a name="mobility-performance-counters-in-lync-server-2013"></a><span data-ttu-id="a9d39-103">Contadores de rendimiento de movilidad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9d39-103">Mobility performance counters in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9d39-104">_**Última modificación del tema:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="a9d39-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="a9d39-105">En las tablas siguientes se enumeran los nombres y las descripciones de los contadores de rendimiento que puede usar para supervisar los servidores que ejecutan la API Web de comunicaciones unificadas (UCWA) y el servicio de movilidad Lync Server 2013 MCX.</span><span class="sxs-lookup"><span data-stu-id="a9d39-105">The following tables list the names and descriptions of performance counters that you can use to monitor servers running the Unified Communications Web API (UCWA) and the Lync Server 2013 Mcx Mobility Service.</span></span>

<span data-ttu-id="a9d39-106">El nombre de categoría de los contadores de la tabla UCWA es **LS: Web – UCWA**.</span><span class="sxs-lookup"><span data-stu-id="a9d39-106">The category name for the counters in the UCWA table is **LS:WEB – UCWA**.</span></span>

<span data-ttu-id="a9d39-107">El nombre de categoría de los contadores de la tabla MCX Mobility Service es **LS: web-Mobile Communication Service**.</span><span class="sxs-lookup"><span data-stu-id="a9d39-107">The category name for the counters in the Mcx Mobility Service table is **LS:WEB - Mobile Communication Service**.</span></span>

<div>

## <a name="performance-counters-for-ucwa"></a><span data-ttu-id="a9d39-108">Contadores de rendimiento para UCWA</span><span class="sxs-lookup"><span data-stu-id="a9d39-108">Performance Counters for UCWA</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a9d39-109">Counter</span><span class="sxs-lookup"><span data-stu-id="a9d39-109">Counter</span></span></th>
<th><span data-ttu-id="a9d39-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="a9d39-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a9d39-111">Recuento de aplicaciones activas</span><span class="sxs-lookup"><span data-stu-id="a9d39-111">Active Application Count</span></span></p></td>
<td><p><span data-ttu-id="a9d39-112">Número actual de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="a9d39-112">The current number of applications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9d39-113">Recuento de modalidad de uso compartido de aplicaciones activas</span><span class="sxs-lookup"><span data-stu-id="a9d39-113">Active Application Sharing Modality Count</span></span></p></td>
<td><p><span data-ttu-id="a9d39-114">Número actual de modalidad de uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="a9d39-114">The current number of Application Sharing modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9d39-115">Recuento de modalidad de audio activa</span><span class="sxs-lookup"><span data-stu-id="a9d39-115">Active Audio Modality Count</span></span></p></td>
<td><p><span data-ttu-id="a9d39-116">Número actual de modalidad de audio</span><span class="sxs-lookup"><span data-stu-id="a9d39-116">The current number of Audio modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9d39-117">Recuento de modalidad de colaboración de datos activa</span><span class="sxs-lookup"><span data-stu-id="a9d39-117">Active Data Collaboration Modality Count</span></span></p></td>
<td><p><span data-ttu-id="a9d39-118">Número actual de modalidad de colaboración de datos</span><span class="sxs-lookup"><span data-stu-id="a9d39-118">The current number of Data Collaboration modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9d39-119">Latencia de la obtención de foto de Active Directory (MS)</span><span class="sxs-lookup"><span data-stu-id="a9d39-119">Active Directory Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="a9d39-120">Este contador muestra el promedio de tiempo (en milisegundos) que se tarda en recuperar una foto de Active Directory</span><span class="sxs-lookup"><span data-stu-id="a9d39-120">This counter shows the average time (in milliseconds) to retrieve a photo from active directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9d39-121">Recuento de modalidad de mensajería activa</span><span class="sxs-lookup"><span data-stu-id="a9d39-121">Active Messaging Modality Count</span></span></p></td>
<td><p><span data-ttu-id="a9d39-122">Número actual de modalidad de mensajería</span><span class="sxs-lookup"><span data-stu-id="a9d39-122">The current number of Messaging modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9d39-123">Recuento de modalidad de vídeo panorámico activo</span><span class="sxs-lookup"><span data-stu-id="a9d39-123">Active Panoramic Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="a9d39-124">Número actual de modalidad de vídeo panorámico</span><span class="sxs-lookup"><span data-stu-id="a9d39-124">The current number of Panoramic Video modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9d39-125">Recuento de Get pendientes activos</span><span class="sxs-lookup"><span data-stu-id="a9d39-125">Active Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="a9d39-126">Número de dependientes actualmente activas. conexiones de larga duración con el servidor</span><span class="sxs-lookup"><span data-stu-id="a9d39-126">The number of currently active pending gets; long-held connections to the server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9d39-127">Recuento de sesiones activas</span><span class="sxs-lookup"><span data-stu-id="a9d39-127">Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="a9d39-128">Número actual de extremos registrados en UCWA por aplicación y totales</span><span class="sxs-lookup"><span data-stu-id="a9d39-128">The current number of endpoints registered in UCWA per application and total</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9d39-129">Número de instancias de usuario activas</span><span class="sxs-lookup"><span data-stu-id="a9d39-129">Active User Instance Count</span></span></p></td>
<td><p><span data-ttu-id="a9d39-130">Número actual de instancias de usuario</span><span class="sxs-lookup"><span data-stu-id="a9d39-130">The current number of user instances</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9d39-131">Instancias de usuario activas sin aplicación</span><span class="sxs-lookup"><span data-stu-id="a9d39-131">Active User Instances without Application</span></span></p></td>
<td><p><span data-ttu-id="a9d39-132">Número actual de instancias de usuario sin aplicación</span><span class="sxs-lookup"><span data-stu-id="a9d39-132">The current number of user instances without application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9d39-133">Recuento de modalidad de vídeo activo</span><span class="sxs-lookup"><span data-stu-id="a9d39-133">Active Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="a9d39-134">Número actual de modalidad de vídeo</span><span class="sxs-lookup"><span data-stu-id="a9d39-134">The current number of Video modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9d39-135">Solicitudes de creación de aplicación recibidas/segundo</span><span class="sxs-lookup"><span data-stu-id="a9d39-135">Application Creation Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="a9d39-136">Tasa por segundo de solicitudes de creación de aplicaciones recibidas</span><span class="sxs-lookup"><span data-stu-id="a9d39-136">The per second rate of received application creation requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9d39-137">Como errores de unión de MCU</span><span class="sxs-lookup"><span data-stu-id="a9d39-137">AS MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="a9d39-138">El número de errores de Unión en MCU</span><span class="sxs-lookup"><span data-stu-id="a9d39-138">The number of AS MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9d39-139">Errores de unión a un MCU AV</span><span class="sxs-lookup"><span data-stu-id="a9d39-139">AV MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="a9d39-140">Número de errores de unión a un MCU AV</span><span class="sxs-lookup"><span data-stu-id="a9d39-140">The number of AV MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9d39-141">Tiempo medio de inicio de la aplicación (MS)</span><span class="sxs-lookup"><span data-stu-id="a9d39-141">Average Application Startup Time (ms)</span></span></p></td>
<td><p><span data-ttu-id="a9d39-142">Tiempo medio de inicio de la aplicación en milisegundos</span><span class="sxs-lookup"><span data-stu-id="a9d39-142">The average application startup time in Milliseconds</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9d39-143">Duración media de la sesión (MS)</span><span class="sxs-lookup"><span data-stu-id="a9d39-143">Average Lifetime for Session (ms)</span></span></p></td>
<td><p><span data-ttu-id="a9d39-144">Duración media de una sesión en milisegundos</span><span class="sxs-lookup"><span data-stu-id="a9d39-144">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9d39-145">Errores de unión a Data MCU</span><span class="sxs-lookup"><span data-stu-id="a9d39-145">Data MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="a9d39-146">Número de errores de unión a datos MCU</span><span class="sxs-lookup"><span data-stu-id="a9d39-146">The number of Data MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9d39-147">Latencia de búsqueda de contactos de Exchange (MS)</span><span class="sxs-lookup"><span data-stu-id="a9d39-147">Exchange Contact Search Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="a9d39-148">Este contador muestra el tiempo medio (en milisegundos) para buscar en el contacto en Exchange</span><span class="sxs-lookup"><span data-stu-id="a9d39-148">This counter shows the average time (in milliseconds) to search contact in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9d39-149">Latencia de obtención de foto HD de Exchange (MS)</span><span class="sxs-lookup"><span data-stu-id="a9d39-149">Exchange HD Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="a9d39-150">Este contador muestra el promedio de tiempo (en milisegundos) que se tarda en recuperar una foto de Exchange</span><span class="sxs-lookup"><span data-stu-id="a9d39-150">This counter shows the average time (in milliseconds) to retrieve a photo from Exchange</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9d39-151">Respuestas 4xx HTTP/segundo</span><span class="sxs-lookup"><span data-stu-id="a9d39-151">HTTP 4xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="a9d39-152">Tasa por segundo de respuestas con código 4xx HTTP</span><span class="sxs-lookup"><span data-stu-id="a9d39-152">The per second rate of responses with HTTP 4xx code</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9d39-153">Respuestas HTTP 5xx/segundo</span><span class="sxs-lookup"><span data-stu-id="a9d39-153">HTTP 5xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="a9d39-154">Tasa por segundo de respuestas con código HTTP 5xx</span><span class="sxs-lookup"><span data-stu-id="a9d39-154">The per second rate of responses with HTTP 5xx code</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9d39-155">Errores de unión de mi MCU</span><span class="sxs-lookup"><span data-stu-id="a9d39-155">IM MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="a9d39-156">Número de errores de unión de mi MCU</span><span class="sxs-lookup"><span data-stu-id="a9d39-156">The number of IM MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9d39-157">Número de errores de obtención de foto de Active Directory</span><span class="sxs-lookup"><span data-stu-id="a9d39-157">Number of Active Directory Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="a9d39-158">Número total de errores para recuperar fotos de Active Directory</span><span class="sxs-lookup"><span data-stu-id="a9d39-158">The total number of failures to retrieve photos from Active Directory</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9d39-159">Número de errores de búsqueda de contactos</span><span class="sxs-lookup"><span data-stu-id="a9d39-159">Number of Contact Search failures</span></span></p></td>
<td><p><span data-ttu-id="a9d39-160">Número total de errores en la búsqueda de contactos en Exchange</span><span class="sxs-lookup"><span data-stu-id="a9d39-160">The total number of failures to search contacts in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9d39-161">Número de errores de deserialización</span><span class="sxs-lookup"><span data-stu-id="a9d39-161">Number of Deserialization Failures</span></span></p></td>
<td><p><span data-ttu-id="a9d39-162">Número total de errores de deserialización</span><span class="sxs-lookup"><span data-stu-id="a9d39-162">The total number of deserialization failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9d39-163">Número de errores de obtención de foto HD</span><span class="sxs-lookup"><span data-stu-id="a9d39-163">Number of HD Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="a9d39-164">El número total de errores para recuperar fotos HD de Exchange</span><span class="sxs-lookup"><span data-stu-id="a9d39-164">The total number of failures to retrieve HD photos from Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9d39-165">Sobre el número máximo de suscripciones por aplicación</span><span class="sxs-lookup"><span data-stu-id="a9d39-165">Over The Maximum Subscriptions Per Application</span></span></p></td>
<td><p><span data-ttu-id="a9d39-166">El número de solicitudes de suscripción por encima del máximo permitido por aplicación</span><span class="sxs-lookup"><span data-stu-id="a9d39-166">The number of Subscription requests over the maximum allowed per application</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9d39-167">Superada la cantidad máxima de suscripciones por lote</span><span class="sxs-lookup"><span data-stu-id="a9d39-167">Over The Maximum Subscriptions Per Batch</span></span></p></td>
<td><p><span data-ttu-id="a9d39-168">El número de solicitudes de suscripción que supera el máximo permitido por lote</span><span class="sxs-lookup"><span data-stu-id="a9d39-168">The number of Subscription requests over the maximum allowed per batch</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9d39-169">Errores de suscripción de presencia</span><span class="sxs-lookup"><span data-stu-id="a9d39-169">Presence Subscription Failures</span></span></p></td>
<td><p><span data-ttu-id="a9d39-170">Número de errores para suscribir presencia</span><span class="sxs-lookup"><span data-stu-id="a9d39-170">The number of failures to subscribe presence</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9d39-171">Registro de errores de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="a9d39-171">Registering Endpoint Failures</span></span></p></td>
<td><p><span data-ttu-id="a9d39-172">Número de errores para registrar los extremos</span><span class="sxs-lookup"><span data-stu-id="a9d39-172">The number of failures to register endpoints</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9d39-173">Solicitudes recibidas/segundo</span><span class="sxs-lookup"><span data-stu-id="a9d39-173">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="a9d39-174">Ratio por segundo de solicitudes recibidas</span><span class="sxs-lookup"><span data-stu-id="a9d39-174">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9d39-175">Solicitudes correctas/segundo</span><span class="sxs-lookup"><span data-stu-id="a9d39-175">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="a9d39-176">Tasa por segundo de solicitudes correctas (códigos de respuesta HTTP 2xx/3xx)</span><span class="sxs-lookup"><span data-stu-id="a9d39-176">The per second rate of successful requests (HTTP 2xx/3xx response codes)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9d39-177">Solicitudes de aplicación creadas correctamente/segundo</span><span class="sxs-lookup"><span data-stu-id="a9d39-177">Succeeded Create Application Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="a9d39-178">Tasa por segundo de solicitudes de creación de aplicaciones correctas</span><span class="sxs-lookup"><span data-stu-id="a9d39-178">The per second rate of successful application creation requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9d39-179">Recuento de peticiones GET pendientes de tiempo de espera agotado</span><span class="sxs-lookup"><span data-stu-id="a9d39-179">Timed Out Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="a9d39-180">El número de Get pendientes que agotaron el tiempo de espera</span><span class="sxs-lookup"><span data-stu-id="a9d39-180">The number of pending gets that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9d39-181">Total de solicitudes de creación de aplicaciones recibidas</span><span class="sxs-lookup"><span data-stu-id="a9d39-181">Total Application Creation Requests Received</span></span></p></td>
<td><p><span data-ttu-id="a9d39-182">Número total de solicitudes de creación de aplicaciones recibidas desde que se inició el servicio</span><span class="sxs-lookup"><span data-stu-id="a9d39-182">The total number of application creation requests received since the service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9d39-183">Total de respuestas HTTP 4xx</span><span class="sxs-lookup"><span data-stu-id="a9d39-183">Total HTTP 4xx Responses</span></span></p></td>
<td><p><span data-ttu-id="a9d39-184">Número total de respuestas HTTP 4xx</span><span class="sxs-lookup"><span data-stu-id="a9d39-184">The total number of HTTP 4xx responses</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9d39-185">Total de respuestas HTTP 5xx</span><span class="sxs-lookup"><span data-stu-id="a9d39-185">Total HTTP 5xx Responses</span></span></p></td>
<td><p><span data-ttu-id="a9d39-186">Número total de respuestas HTTP 5xx</span><span class="sxs-lookup"><span data-stu-id="a9d39-186">The total number of HTTP 5xx responses</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9d39-187">Total de solicitudes recibidas en el canal de comandos</span><span class="sxs-lookup"><span data-stu-id="a9d39-187">Total Requests Received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="a9d39-188">Número total de solicitudes recibidas en el canal de comandos</span><span class="sxs-lookup"><span data-stu-id="a9d39-188">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9d39-189">Solicitudes correctas totales</span><span class="sxs-lookup"><span data-stu-id="a9d39-189">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="a9d39-190">Número total de solicitudes que se realizaron correctamente</span><span class="sxs-lookup"><span data-stu-id="a9d39-190">The total number of requests that succeeded</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9d39-191">Total de sesiones iniciadas</span><span class="sxs-lookup"><span data-stu-id="a9d39-191">Total Sessions Initiated</span></span></p></td>
<td><p><span data-ttu-id="a9d39-192">El número total de sesiones que se iniciaron desde que se inició el servicio</span><span class="sxs-lookup"><span data-stu-id="a9d39-192">The total number of sessions that were initiated since the service was started</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9d39-193">Total de sesiones finalizadas por un tiempo de espera inactivo</span><span class="sxs-lookup"><span data-stu-id="a9d39-193">Total Sessions Terminated Because of Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="a9d39-194">Número total de sesiones que han finalizado porque se ha agotado el tiempo de espera de inactividad del usuario</span><span class="sxs-lookup"><span data-stu-id="a9d39-194">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9d39-195">Total de aplicaciones limitadas</span><span class="sxs-lookup"><span data-stu-id="a9d39-195">Total Throttled Applications</span></span></p></td>
<td><p><span data-ttu-id="a9d39-196">El número de aplicaciones limitadas</span><span class="sxs-lookup"><span data-stu-id="a9d39-196">The number of throttled applications</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div id="sectionSection1" class="section">

### <a name="performance-counters-for-mcx-mobility-service"></a><span data-ttu-id="a9d39-197">Contadores de rendimiento para el servicio de movilidad de MCX</span><span class="sxs-lookup"><span data-stu-id="a9d39-197">Performance Counters for Mcx Mobility Service</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a9d39-198">Counter</span><span class="sxs-lookup"><span data-stu-id="a9d39-198">Counter</span></span></th>
<th><span data-ttu-id="a9d39-199">Descripción</span><span class="sxs-lookup"><span data-stu-id="a9d39-199">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a9d39-200">Duración media de una sesión en milisegundos</span><span class="sxs-lookup"><span data-stu-id="a9d39-200">Average Lifetime for a Session in Milliseconds</span></span></p></td>
<td><p><span data-ttu-id="a9d39-201">Duración media de una sesión en milisegundos</span><span class="sxs-lookup"><span data-stu-id="a9d39-201">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9d39-202">Suscripciones de notificación de inserción actuales</span><span class="sxs-lookup"><span data-stu-id="a9d39-202">Current Push Notification Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="a9d39-203">Número actual de suscripciones de notificación de inserción.</span><span class="sxs-lookup"><span data-stu-id="a9d39-203">The current number of push notification subscriptions.</span></span> <span data-ttu-id="a9d39-204">Este número, junto con el recuento de sesiones actualmente activas, representa el subconjunto de las sesiones actualmente activas registradas para dispositivos Windows Mobile o iPhone.</span><span class="sxs-lookup"><span data-stu-id="a9d39-204">This number, in conjunction with Currently Active Session Count, represents the subset of currently active sessions that are registered for Windows Mobile or iPhone devices.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9d39-205">Recuento de sondeos de tiempo de espera agotado de red actualmente activa</span><span class="sxs-lookup"><span data-stu-id="a9d39-205">Currently Active Network Timeout Poll Count</span></span></p></td>
<td><p><span data-ttu-id="a9d39-206">Número de sondeos de red cuyo tiempo de espera se ha agotado</span><span class="sxs-lookup"><span data-stu-id="a9d39-206">The number of network polls that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9d39-207">Recuento de sondeos actualmente activos</span><span class="sxs-lookup"><span data-stu-id="a9d39-207">Currently Active Poll Count</span></span></p></td>
<td><p><span data-ttu-id="a9d39-208">Número de sondeos actualmente activos (conexiones largamente mantenidas con el servidor)</span><span class="sxs-lookup"><span data-stu-id="a9d39-208">The number of currently active polls (long-held connections to the server)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9d39-209">Recuento de sesiones actualmente activas</span><span class="sxs-lookup"><span data-stu-id="a9d39-209">Currently Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="a9d39-210">Número actual de extremos registrados en el servicio de movilidad</span><span class="sxs-lookup"><span data-stu-id="a9d39-210">Current number of endpoints registered in the Mobility Service</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9d39-211">Recuento de sesiones actualmente activas con suscripciones de presencia activa</span><span class="sxs-lookup"><span data-stu-id="a9d39-211">Currently Active Session Count with Active Presence Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="a9d39-212">Número de sesiones actualmente activas con suscripciones de presencia activa</span><span class="sxs-lookup"><span data-stu-id="a9d39-212">The number of currently active sessions with active presence subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9d39-213">Solicitudes de notificación de inserción erróneas/segundo</span><span class="sxs-lookup"><span data-stu-id="a9d39-213">Push Notification Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="a9d39-214">Ratio por segundo de notificaciones de inserción erróneas</span><span class="sxs-lookup"><span data-stu-id="a9d39-214">The per second rate of failed push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9d39-215">Solicitudes de notificación de inserción correctas/segundo</span><span class="sxs-lookup"><span data-stu-id="a9d39-215">Push Notification Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="a9d39-216">Ratio por segundo de notificaciones de inserción correctas</span><span class="sxs-lookup"><span data-stu-id="a9d39-216">The per second rate of successful push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9d39-217">Solicitudes de notificación de inserción reducidas/segundo</span><span class="sxs-lookup"><span data-stu-id="a9d39-217">Push Notification Requests Throttled/Second</span></span></p></td>
<td><p><span data-ttu-id="a9d39-218">Ratio por segundo de notificaciones de inserción reducidas</span><span class="sxs-lookup"><span data-stu-id="a9d39-218">The per second rate of throttled push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9d39-219">Solicitudes de notificación de inserción/segundo</span><span class="sxs-lookup"><span data-stu-id="a9d39-219">Push Notification Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="a9d39-220">Ratio por segundo de notificaciones de inserción enviadas</span><span class="sxs-lookup"><span data-stu-id="a9d39-220">The per second rate of sent push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9d39-221">Solicitudes erróneas/segundo</span><span class="sxs-lookup"><span data-stu-id="a9d39-221">Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="a9d39-222">Ratio por segundo de solicitudes erróneas</span><span class="sxs-lookup"><span data-stu-id="a9d39-222">The per second rate of failed requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9d39-223">Solicitudes recibidas/segundo</span><span class="sxs-lookup"><span data-stu-id="a9d39-223">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="a9d39-224">Ratio por segundo de solicitudes recibidas</span><span class="sxs-lookup"><span data-stu-id="a9d39-224">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9d39-225">Solicitudes rechazadas/segundo</span><span class="sxs-lookup"><span data-stu-id="a9d39-225">Requests Rejected/Second</span></span></p></td>
<td><p><span data-ttu-id="a9d39-226">Ratio por segundo de solicitudes rechazadas</span><span class="sxs-lookup"><span data-stu-id="a9d39-226">The per second rate of rejected requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9d39-227">Solicitudes correctas/segundo</span><span class="sxs-lookup"><span data-stu-id="a9d39-227">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="a9d39-228">Ratio por segundo de solicitudes correctas</span><span class="sxs-lookup"><span data-stu-id="a9d39-228">The per second rate of successful requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9d39-229">Solicitudes de inicio de sesión correctas/segundo</span><span class="sxs-lookup"><span data-stu-id="a9d39-229">Succeeded Initiate Session Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="a9d39-p102">Ratio por segundo de solicitudes Obtener ubicación correctas. Las solicitudes para iniciar una sesión consumen la mayoría de la CPU en el servidor. La carga máxima admitida es 12/segundo. La sostenibilidad depende de otras cargas en el servidor. Iniciar una sesión normalmente significa un inicio de sesión de un usuario que ha tenido la sesión cerrada durante un período prolongado de tiempo.</span><span class="sxs-lookup"><span data-stu-id="a9d39-p102">The per second rate of successful Get Location requests. Requests to initiate a session consume the most CPU on the server. Peak supported load is 12/second. Sustainability depends on other loads on the server. Initiate a session typically means a sign-in for a user that has been signed out for an extended period of time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9d39-235">Llamadas de voz entrantes rechazadas totales</span><span class="sxs-lookup"><span data-stu-id="a9d39-235">Total Declined Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="a9d39-236">Número total de llamadas de voz entrantes que se han rechazado</span><span class="sxs-lookup"><span data-stu-id="a9d39-236">The total number of inbound voice calls that were declined</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9d39-237">Llamadas de voz entrantes erróneas totales</span><span class="sxs-lookup"><span data-stu-id="a9d39-237">Total Failed Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="a9d39-238">Número total de llamadas de voz entrantes erróneas</span><span class="sxs-lookup"><span data-stu-id="a9d39-238">The total number of inbound voice calls that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9d39-239">Llamadas de voz salientes erróneas totales</span><span class="sxs-lookup"><span data-stu-id="a9d39-239">Total Failed Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="a9d39-240">Número total de llamadas de voz salientes erróneas</span><span class="sxs-lookup"><span data-stu-id="a9d39-240">The total number of outbound voice calls that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9d39-241">Número de sesiones finalizadas por usuario</span><span class="sxs-lookup"><span data-stu-id="a9d39-241">Total number of sessions terminated by user</span></span></p></td>
<td><p><span data-ttu-id="a9d39-242">Número de sesiones finalizadas por usuarios</span><span class="sxs-lookup"><span data-stu-id="a9d39-242">The total number of sessions terminated by users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9d39-243">Solicitudes de notificación de inserción totales</span><span class="sxs-lookup"><span data-stu-id="a9d39-243">Total Push Notification Requests</span></span></p></td>
<td><p><span data-ttu-id="a9d39-244">Número total de solicitudes de notificación de inserción</span><span class="sxs-lookup"><span data-stu-id="a9d39-244">The total number of push notification requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9d39-245">Solicitudes de notificación de inserción erróneas totales</span><span class="sxs-lookup"><span data-stu-id="a9d39-245">Total Push Notification Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="a9d39-246">Número total de solicitudes de notificación de inserción erróneas</span><span class="sxs-lookup"><span data-stu-id="a9d39-246">The total number of push notification requests that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9d39-247">Solicitudes de notificación de inserción correctas totales</span><span class="sxs-lookup"><span data-stu-id="a9d39-247">Total Push Notification Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="a9d39-248">Número total de solicitudes de notificación de inserción realizadas correctamente</span><span class="sxs-lookup"><span data-stu-id="a9d39-248">The total number of push notification requests that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9d39-249">Solicitudes de notificación de inserción reducidas totales</span><span class="sxs-lookup"><span data-stu-id="a9d39-249">Total Push Notification Requests Throttled</span></span></p></td>
<td><p><span data-ttu-id="a9d39-250">Número total de solicitudes de notificación de inserción que se han reducido</span><span class="sxs-lookup"><span data-stu-id="a9d39-250">The total number of push notification requests that were throttled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9d39-251">Solicitudes erróneas totales</span><span class="sxs-lookup"><span data-stu-id="a9d39-251">Total Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="a9d39-252">Número total de solicitudes erróneas</span><span class="sxs-lookup"><span data-stu-id="a9d39-252">The total number of requests that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9d39-253">Solicitudes totales recibidas en el canal de comandos</span><span class="sxs-lookup"><span data-stu-id="a9d39-253">Total Requests received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="a9d39-254">Número total de solicitudes recibidas en el canal de comandos</span><span class="sxs-lookup"><span data-stu-id="a9d39-254">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9d39-255">Solicitudes rechazadas totales</span><span class="sxs-lookup"><span data-stu-id="a9d39-255">Total Requests Rejected</span></span></p></td>
<td><p><span data-ttu-id="a9d39-256">Número total de solicitudes que se han rechazado</span><span class="sxs-lookup"><span data-stu-id="a9d39-256">The total number of requests that were rejected</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9d39-257">Solicitudes correctas totales</span><span class="sxs-lookup"><span data-stu-id="a9d39-257">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="a9d39-258">Número total de solicitudes realizadas al servicio de movilidad correctamente</span><span class="sxs-lookup"><span data-stu-id="a9d39-258">The total number of requests made to the Mobility Service that succeeded</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9d39-259">Recuento de sesiones iniciadas totales</span><span class="sxs-lookup"><span data-stu-id="a9d39-259">Total Session Initiated Count</span></span></p></td>
<td><p><span data-ttu-id="a9d39-260">Número total de sesiones que se han iniciado desde que se inició el servicio de movilidad</span><span class="sxs-lookup"><span data-stu-id="a9d39-260">The total number of sessions that were initiated since the Mobility Service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9d39-261">Sesiones totales finalizadas debido a que se ha agotado el tiempo de espera de inactividad del usuario</span><span class="sxs-lookup"><span data-stu-id="a9d39-261">Total Sessions Terminated Because of User Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="a9d39-262">Número total de sesiones que han finalizado porque se ha agotado el tiempo de espera de inactividad del usuario</span><span class="sxs-lookup"><span data-stu-id="a9d39-262">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9d39-263">Llamadas de voz entrantes correctas totales</span><span class="sxs-lookup"><span data-stu-id="a9d39-263">Total Successful Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="a9d39-264">Número total de llamadas de voz entradas que se han realizado correctamente</span><span class="sxs-lookup"><span data-stu-id="a9d39-264">The total number of inbound voice calls that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9d39-265">Llamadas de voz salientes correctas totales</span><span class="sxs-lookup"><span data-stu-id="a9d39-265">Total Successful Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="a9d39-266">Número total de llamadas de voz salientes que se han realizado correctamente</span><span class="sxs-lookup"><span data-stu-id="a9d39-266">The total number of outbound voice calls that were successful</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

