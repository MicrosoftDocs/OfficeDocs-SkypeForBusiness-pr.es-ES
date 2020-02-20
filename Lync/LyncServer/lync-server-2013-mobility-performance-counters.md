---
title: 'Lync Server 2013: contadores de rendimiento de movilidad'
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
ms.openlocfilehash: cb5363ef31f44abdb9c8ea07938668f17b95c471
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149690"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mobility-performance-counters-in-lync-server-2013"></a><span data-ttu-id="0b6aa-102">Contadores de rendimiento de movilidad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b6aa-102">Mobility performance counters in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b6aa-103">_**Última modificación del tema:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="0b6aa-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="0b6aa-104">En las tablas siguientes se enumeran los nombres y las descripciones de los contadores de rendimiento que puede usar para supervisar los servidores que ejecutan la API Web de comunicaciones unificadas (UCWA) y el servicio de movilidad Lync Server 2013 MCX.</span><span class="sxs-lookup"><span data-stu-id="0b6aa-104">The following tables list the names and descriptions of performance counters that you can use to monitor servers running the Unified Communications Web API (UCWA) and the Lync Server 2013 Mcx Mobility Service.</span></span>

<span data-ttu-id="0b6aa-105">El nombre de categoría de los contadores de la tabla UCWA es **LS: Web – UCWA**.</span><span class="sxs-lookup"><span data-stu-id="0b6aa-105">The category name for the counters in the UCWA table is **LS:WEB – UCWA**.</span></span>

<span data-ttu-id="0b6aa-106">El nombre de categoría de los contadores de la tabla MCX Mobility Service es **LS: web-Mobile Communication Service**.</span><span class="sxs-lookup"><span data-stu-id="0b6aa-106">The category name for the counters in the Mcx Mobility Service table is **LS:WEB - Mobile Communication Service**.</span></span>

<div>

## <a name="performance-counters-for-ucwa"></a><span data-ttu-id="0b6aa-107">Contadores de rendimiento para UCWA</span><span class="sxs-lookup"><span data-stu-id="0b6aa-107">Performance Counters for UCWA</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0b6aa-108">Counter</span><span class="sxs-lookup"><span data-stu-id="0b6aa-108">Counter</span></span></th>
<th><span data-ttu-id="0b6aa-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="0b6aa-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0b6aa-110">Recuento de aplicaciones activas</span><span class="sxs-lookup"><span data-stu-id="0b6aa-110">Active Application Count</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-111">Número actual de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="0b6aa-111">The current number of applications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6aa-112">Recuento de modalidad de uso compartido de aplicaciones activas</span><span class="sxs-lookup"><span data-stu-id="0b6aa-112">Active Application Sharing Modality Count</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-113">Número actual de modalidad de uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="0b6aa-113">The current number of Application Sharing modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b6aa-114">Recuento de modalidad de audio activa</span><span class="sxs-lookup"><span data-stu-id="0b6aa-114">Active Audio Modality Count</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-115">Número actual de modalidad de audio</span><span class="sxs-lookup"><span data-stu-id="0b6aa-115">The current number of Audio modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6aa-116">Recuento de modalidad de colaboración de datos activa</span><span class="sxs-lookup"><span data-stu-id="0b6aa-116">Active Data Collaboration Modality Count</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-117">Número actual de modalidad de colaboración de datos</span><span class="sxs-lookup"><span data-stu-id="0b6aa-117">The current number of Data Collaboration modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b6aa-118">Latencia de la obtención de foto de Active Directory (MS)</span><span class="sxs-lookup"><span data-stu-id="0b6aa-118">Active Directory Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-119">Este contador muestra el promedio de tiempo (en milisegundos) que se tarda en recuperar una foto de Active Directory</span><span class="sxs-lookup"><span data-stu-id="0b6aa-119">This counter shows the average time (in milliseconds) to retrieve a photo from active directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6aa-120">Recuento de modalidad de mensajería activa</span><span class="sxs-lookup"><span data-stu-id="0b6aa-120">Active Messaging Modality Count</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-121">Número actual de modalidad de mensajería</span><span class="sxs-lookup"><span data-stu-id="0b6aa-121">The current number of Messaging modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b6aa-122">Recuento de modalidad de vídeo panorámico activo</span><span class="sxs-lookup"><span data-stu-id="0b6aa-122">Active Panoramic Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-123">Número actual de modalidad de vídeo panorámico</span><span class="sxs-lookup"><span data-stu-id="0b6aa-123">The current number of Panoramic Video modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6aa-124">Recuento de Get pendientes activos</span><span class="sxs-lookup"><span data-stu-id="0b6aa-124">Active Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-125">Número de dependientes actualmente activas. conexiones de larga duración con el servidor</span><span class="sxs-lookup"><span data-stu-id="0b6aa-125">The number of currently active pending gets; long-held connections to the server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b6aa-126">Recuento de sesiones activas</span><span class="sxs-lookup"><span data-stu-id="0b6aa-126">Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-127">Número actual de extremos registrados en UCWA por aplicación y totales</span><span class="sxs-lookup"><span data-stu-id="0b6aa-127">The current number of endpoints registered in UCWA per application and total</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6aa-128">Número de instancias de usuario activas</span><span class="sxs-lookup"><span data-stu-id="0b6aa-128">Active User Instance Count</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-129">Número actual de instancias de usuario</span><span class="sxs-lookup"><span data-stu-id="0b6aa-129">The current number of user instances</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b6aa-130">Instancias de usuario activas sin aplicación</span><span class="sxs-lookup"><span data-stu-id="0b6aa-130">Active User Instances without Application</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-131">Número actual de instancias de usuario sin aplicación</span><span class="sxs-lookup"><span data-stu-id="0b6aa-131">The current number of user instances without application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6aa-132">Recuento de modalidad de vídeo activo</span><span class="sxs-lookup"><span data-stu-id="0b6aa-132">Active Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-133">Número actual de modalidad de vídeo</span><span class="sxs-lookup"><span data-stu-id="0b6aa-133">The current number of Video modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b6aa-134">Solicitudes de creación de aplicación recibidas/segundo</span><span class="sxs-lookup"><span data-stu-id="0b6aa-134">Application Creation Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-135">Tasa por segundo de solicitudes de creación de aplicaciones recibidas</span><span class="sxs-lookup"><span data-stu-id="0b6aa-135">The per second rate of received application creation requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6aa-136">Como errores de unión de MCU</span><span class="sxs-lookup"><span data-stu-id="0b6aa-136">AS MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-137">El número de errores de Unión en MCU</span><span class="sxs-lookup"><span data-stu-id="0b6aa-137">The number of AS MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b6aa-138">Errores de unión a un MCU AV</span><span class="sxs-lookup"><span data-stu-id="0b6aa-138">AV MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-139">Número de errores de unión a un MCU AV</span><span class="sxs-lookup"><span data-stu-id="0b6aa-139">The number of AV MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6aa-140">Tiempo medio de inicio de la aplicación (MS)</span><span class="sxs-lookup"><span data-stu-id="0b6aa-140">Average Application Startup Time (ms)</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-141">Tiempo medio de inicio de la aplicación en milisegundos</span><span class="sxs-lookup"><span data-stu-id="0b6aa-141">The average application startup time in Milliseconds</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b6aa-142">Duración media de la sesión (MS)</span><span class="sxs-lookup"><span data-stu-id="0b6aa-142">Average Lifetime for Session (ms)</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-143">Duración media de una sesión en milisegundos</span><span class="sxs-lookup"><span data-stu-id="0b6aa-143">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6aa-144">Errores de unión a Data MCU</span><span class="sxs-lookup"><span data-stu-id="0b6aa-144">Data MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-145">Número de errores de unión a datos MCU</span><span class="sxs-lookup"><span data-stu-id="0b6aa-145">The number of Data MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b6aa-146">Latencia de búsqueda de contactos de Exchange (MS)</span><span class="sxs-lookup"><span data-stu-id="0b6aa-146">Exchange Contact Search Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-147">Este contador muestra el tiempo medio (en milisegundos) para buscar en el contacto en Exchange</span><span class="sxs-lookup"><span data-stu-id="0b6aa-147">This counter shows the average time (in milliseconds) to search contact in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6aa-148">Latencia de obtención de foto HD de Exchange (MS)</span><span class="sxs-lookup"><span data-stu-id="0b6aa-148">Exchange HD Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-149">Este contador muestra el promedio de tiempo (en milisegundos) que se tarda en recuperar una foto de Exchange</span><span class="sxs-lookup"><span data-stu-id="0b6aa-149">This counter shows the average time (in milliseconds) to retrieve a photo from Exchange</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b6aa-150">Respuestas 4xx HTTP/segundo</span><span class="sxs-lookup"><span data-stu-id="0b6aa-150">HTTP 4xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-151">Tasa por segundo de respuestas con código 4xx HTTP</span><span class="sxs-lookup"><span data-stu-id="0b6aa-151">The per second rate of responses with HTTP 4xx code</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6aa-152">Respuestas HTTP 5xx/segundo</span><span class="sxs-lookup"><span data-stu-id="0b6aa-152">HTTP 5xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-153">Tasa por segundo de respuestas con código HTTP 5xx</span><span class="sxs-lookup"><span data-stu-id="0b6aa-153">The per second rate of responses with HTTP 5xx code</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b6aa-154">Errores de unión de mi MCU</span><span class="sxs-lookup"><span data-stu-id="0b6aa-154">IM MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-155">Número de errores de unión de mi MCU</span><span class="sxs-lookup"><span data-stu-id="0b6aa-155">The number of IM MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6aa-156">Número de errores de obtención de foto de Active Directory</span><span class="sxs-lookup"><span data-stu-id="0b6aa-156">Number of Active Directory Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-157">Número total de errores para recuperar fotos de Active Directory</span><span class="sxs-lookup"><span data-stu-id="0b6aa-157">The total number of failures to retrieve photos from Active Directory</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b6aa-158">Número de errores de búsqueda de contactos</span><span class="sxs-lookup"><span data-stu-id="0b6aa-158">Number of Contact Search failures</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-159">Número total de errores en la búsqueda de contactos en Exchange</span><span class="sxs-lookup"><span data-stu-id="0b6aa-159">The total number of failures to search contacts in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6aa-160">Número de errores de deserialización</span><span class="sxs-lookup"><span data-stu-id="0b6aa-160">Number of Deserialization Failures</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-161">Número total de errores de deserialización</span><span class="sxs-lookup"><span data-stu-id="0b6aa-161">The total number of deserialization failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b6aa-162">Número de errores de obtención de foto HD</span><span class="sxs-lookup"><span data-stu-id="0b6aa-162">Number of HD Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-163">El número total de errores para recuperar fotos HD de Exchange</span><span class="sxs-lookup"><span data-stu-id="0b6aa-163">The total number of failures to retrieve HD photos from Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6aa-164">Sobre el número máximo de suscripciones por aplicación</span><span class="sxs-lookup"><span data-stu-id="0b6aa-164">Over The Maximum Subscriptions Per Application</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-165">El número de solicitudes de suscripción por encima del máximo permitido por aplicación</span><span class="sxs-lookup"><span data-stu-id="0b6aa-165">The number of Subscription requests over the maximum allowed per application</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b6aa-166">Superada la cantidad máxima de suscripciones por lote</span><span class="sxs-lookup"><span data-stu-id="0b6aa-166">Over The Maximum Subscriptions Per Batch</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-167">El número de solicitudes de suscripción que supera el máximo permitido por lote</span><span class="sxs-lookup"><span data-stu-id="0b6aa-167">The number of Subscription requests over the maximum allowed per batch</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6aa-168">Errores de suscripción de presencia</span><span class="sxs-lookup"><span data-stu-id="0b6aa-168">Presence Subscription Failures</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-169">Número de errores para suscribir presencia</span><span class="sxs-lookup"><span data-stu-id="0b6aa-169">The number of failures to subscribe presence</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b6aa-170">Registro de errores de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="0b6aa-170">Registering Endpoint Failures</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-171">Número de errores para registrar los extremos</span><span class="sxs-lookup"><span data-stu-id="0b6aa-171">The number of failures to register endpoints</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6aa-172">Solicitudes recibidas/segundo</span><span class="sxs-lookup"><span data-stu-id="0b6aa-172">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-173">Ratio por segundo de solicitudes recibidas</span><span class="sxs-lookup"><span data-stu-id="0b6aa-173">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b6aa-174">Solicitudes correctas/segundo</span><span class="sxs-lookup"><span data-stu-id="0b6aa-174">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-175">Tasa por segundo de solicitudes correctas (códigos de respuesta HTTP 2xx/3xx)</span><span class="sxs-lookup"><span data-stu-id="0b6aa-175">The per second rate of successful requests (HTTP 2xx/3xx response codes)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6aa-176">Solicitudes de aplicación creadas correctamente/segundo</span><span class="sxs-lookup"><span data-stu-id="0b6aa-176">Succeeded Create Application Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-177">Tasa por segundo de solicitudes de creación de aplicaciones correctas</span><span class="sxs-lookup"><span data-stu-id="0b6aa-177">The per second rate of successful application creation requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b6aa-178">Recuento de peticiones GET pendientes de tiempo de espera agotado</span><span class="sxs-lookup"><span data-stu-id="0b6aa-178">Timed Out Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-179">El número de Get pendientes que agotaron el tiempo de espera</span><span class="sxs-lookup"><span data-stu-id="0b6aa-179">The number of pending gets that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6aa-180">Total de solicitudes de creación de aplicaciones recibidas</span><span class="sxs-lookup"><span data-stu-id="0b6aa-180">Total Application Creation Requests Received</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-181">Número total de solicitudes de creación de aplicaciones recibidas desde que se inició el servicio</span><span class="sxs-lookup"><span data-stu-id="0b6aa-181">The total number of application creation requests received since the service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b6aa-182">Total de respuestas HTTP 4xx</span><span class="sxs-lookup"><span data-stu-id="0b6aa-182">Total HTTP 4xx Responses</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-183">Número total de respuestas HTTP 4xx</span><span class="sxs-lookup"><span data-stu-id="0b6aa-183">The total number of HTTP 4xx responses</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6aa-184">Total de respuestas HTTP 5xx</span><span class="sxs-lookup"><span data-stu-id="0b6aa-184">Total HTTP 5xx Responses</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-185">Número total de respuestas HTTP 5xx</span><span class="sxs-lookup"><span data-stu-id="0b6aa-185">The total number of HTTP 5xx responses</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b6aa-186">Total de solicitudes recibidas en el canal de comandos</span><span class="sxs-lookup"><span data-stu-id="0b6aa-186">Total Requests Received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-187">Número total de solicitudes recibidas en el canal de comandos</span><span class="sxs-lookup"><span data-stu-id="0b6aa-187">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6aa-188">Solicitudes correctas totales</span><span class="sxs-lookup"><span data-stu-id="0b6aa-188">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-189">Número total de solicitudes que se realizaron correctamente</span><span class="sxs-lookup"><span data-stu-id="0b6aa-189">The total number of requests that succeeded</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b6aa-190">Total de sesiones iniciadas</span><span class="sxs-lookup"><span data-stu-id="0b6aa-190">Total Sessions Initiated</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-191">El número total de sesiones que se iniciaron desde que se inició el servicio</span><span class="sxs-lookup"><span data-stu-id="0b6aa-191">The total number of sessions that were initiated since the service was started</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6aa-192">Total de sesiones finalizadas por un tiempo de espera inactivo</span><span class="sxs-lookup"><span data-stu-id="0b6aa-192">Total Sessions Terminated Because of Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-193">Número total de sesiones que han finalizado porque se ha agotado el tiempo de espera de inactividad del usuario</span><span class="sxs-lookup"><span data-stu-id="0b6aa-193">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b6aa-194">Total de aplicaciones limitadas</span><span class="sxs-lookup"><span data-stu-id="0b6aa-194">Total Throttled Applications</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-195">El número de aplicaciones limitadas</span><span class="sxs-lookup"><span data-stu-id="0b6aa-195">The number of throttled applications</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div id="sectionSection1" class="section">

### <a name="performance-counters-for-mcx-mobility-service"></a><span data-ttu-id="0b6aa-196">Contadores de rendimiento para el servicio de movilidad de MCX</span><span class="sxs-lookup"><span data-stu-id="0b6aa-196">Performance Counters for Mcx Mobility Service</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0b6aa-197">Counter</span><span class="sxs-lookup"><span data-stu-id="0b6aa-197">Counter</span></span></th>
<th><span data-ttu-id="0b6aa-198">Descripción</span><span class="sxs-lookup"><span data-stu-id="0b6aa-198">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0b6aa-199">Duración media de una sesión en milisegundos</span><span class="sxs-lookup"><span data-stu-id="0b6aa-199">Average Lifetime for a Session in Milliseconds</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-200">Duración media de una sesión en milisegundos</span><span class="sxs-lookup"><span data-stu-id="0b6aa-200">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6aa-201">Suscripciones de notificación de inserción actuales</span><span class="sxs-lookup"><span data-stu-id="0b6aa-201">Current Push Notification Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-202">Número actual de suscripciones de notificación de inserción.</span><span class="sxs-lookup"><span data-stu-id="0b6aa-202">The current number of push notification subscriptions.</span></span> <span data-ttu-id="0b6aa-203">Este número, junto con el recuento de sesiones actualmente activas, representa el subconjunto de las sesiones actualmente activas registradas para dispositivos Windows Mobile o iPhone.</span><span class="sxs-lookup"><span data-stu-id="0b6aa-203">This number, in conjunction with Currently Active Session Count, represents the subset of currently active sessions that are registered for Windows Mobile or iPhone devices.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b6aa-204">Recuento de sondeos de tiempo de espera agotado de red actualmente activa</span><span class="sxs-lookup"><span data-stu-id="0b6aa-204">Currently Active Network Timeout Poll Count</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-205">Número de sondeos de red cuyo tiempo de espera se ha agotado</span><span class="sxs-lookup"><span data-stu-id="0b6aa-205">The number of network polls that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6aa-206">Recuento de sondeos actualmente activos</span><span class="sxs-lookup"><span data-stu-id="0b6aa-206">Currently Active Poll Count</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-207">Número de sondeos actualmente activos (conexiones largamente mantenidas con el servidor)</span><span class="sxs-lookup"><span data-stu-id="0b6aa-207">The number of currently active polls (long-held connections to the server)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b6aa-208">Recuento de sesiones actualmente activas</span><span class="sxs-lookup"><span data-stu-id="0b6aa-208">Currently Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-209">Número actual de extremos registrados en el servicio de movilidad</span><span class="sxs-lookup"><span data-stu-id="0b6aa-209">Current number of endpoints registered in the Mobility Service</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6aa-210">Recuento de sesiones actualmente activas con suscripciones de presencia activa</span><span class="sxs-lookup"><span data-stu-id="0b6aa-210">Currently Active Session Count with Active Presence Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-211">Número de sesiones actualmente activas con suscripciones de presencia activa</span><span class="sxs-lookup"><span data-stu-id="0b6aa-211">The number of currently active sessions with active presence subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b6aa-212">Solicitudes de notificación de inserción erróneas/segundo</span><span class="sxs-lookup"><span data-stu-id="0b6aa-212">Push Notification Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-213">Ratio por segundo de notificaciones de inserción erróneas</span><span class="sxs-lookup"><span data-stu-id="0b6aa-213">The per second rate of failed push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6aa-214">Solicitudes de notificación de inserción correctas/segundo</span><span class="sxs-lookup"><span data-stu-id="0b6aa-214">Push Notification Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-215">Ratio por segundo de notificaciones de inserción correctas</span><span class="sxs-lookup"><span data-stu-id="0b6aa-215">The per second rate of successful push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b6aa-216">Solicitudes de notificación de inserción reducidas/segundo</span><span class="sxs-lookup"><span data-stu-id="0b6aa-216">Push Notification Requests Throttled/Second</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-217">Ratio por segundo de notificaciones de inserción reducidas</span><span class="sxs-lookup"><span data-stu-id="0b6aa-217">The per second rate of throttled push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6aa-218">Solicitudes de notificación de inserción/segundo</span><span class="sxs-lookup"><span data-stu-id="0b6aa-218">Push Notification Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-219">Ratio por segundo de notificaciones de inserción enviadas</span><span class="sxs-lookup"><span data-stu-id="0b6aa-219">The per second rate of sent push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b6aa-220">Solicitudes erróneas/segundo</span><span class="sxs-lookup"><span data-stu-id="0b6aa-220">Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-221">Ratio por segundo de solicitudes erróneas</span><span class="sxs-lookup"><span data-stu-id="0b6aa-221">The per second rate of failed requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6aa-222">Solicitudes recibidas/segundo</span><span class="sxs-lookup"><span data-stu-id="0b6aa-222">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-223">Ratio por segundo de solicitudes recibidas</span><span class="sxs-lookup"><span data-stu-id="0b6aa-223">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b6aa-224">Solicitudes rechazadas/segundo</span><span class="sxs-lookup"><span data-stu-id="0b6aa-224">Requests Rejected/Second</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-225">Ratio por segundo de solicitudes rechazadas</span><span class="sxs-lookup"><span data-stu-id="0b6aa-225">The per second rate of rejected requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6aa-226">Solicitudes correctas/segundo</span><span class="sxs-lookup"><span data-stu-id="0b6aa-226">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-227">Ratio por segundo de solicitudes correctas</span><span class="sxs-lookup"><span data-stu-id="0b6aa-227">The per second rate of successful requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b6aa-228">Solicitudes de inicio de sesión correctas/segundo</span><span class="sxs-lookup"><span data-stu-id="0b6aa-228">Succeeded Initiate Session Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-p102">Ratio por segundo de solicitudes Obtener ubicación correctas. Las solicitudes para iniciar una sesión consumen la mayoría de la CPU en el servidor. La carga máxima admitida es 12/segundo. La sostenibilidad depende de otras cargas en el servidor. Iniciar una sesión normalmente significa un inicio de sesión de un usuario que ha tenido la sesión cerrada durante un período prolongado de tiempo.</span><span class="sxs-lookup"><span data-stu-id="0b6aa-p102">The per second rate of successful Get Location requests. Requests to initiate a session consume the most CPU on the server. Peak supported load is 12/second. Sustainability depends on other loads on the server. Initiate a session typically means a sign-in for a user that has been signed out for an extended period of time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6aa-234">Llamadas de voz entrantes rechazadas totales</span><span class="sxs-lookup"><span data-stu-id="0b6aa-234">Total Declined Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-235">Número total de llamadas de voz entrantes que se han rechazado</span><span class="sxs-lookup"><span data-stu-id="0b6aa-235">The total number of inbound voice calls that were declined</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b6aa-236">Llamadas de voz entrantes erróneas totales</span><span class="sxs-lookup"><span data-stu-id="0b6aa-236">Total Failed Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-237">Número total de llamadas de voz entrantes erróneas</span><span class="sxs-lookup"><span data-stu-id="0b6aa-237">The total number of inbound voice calls that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6aa-238">Llamadas de voz salientes erróneas totales</span><span class="sxs-lookup"><span data-stu-id="0b6aa-238">Total Failed Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-239">Número total de llamadas de voz salientes erróneas</span><span class="sxs-lookup"><span data-stu-id="0b6aa-239">The total number of outbound voice calls that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b6aa-240">Número de sesiones finalizadas por usuario</span><span class="sxs-lookup"><span data-stu-id="0b6aa-240">Total number of sessions terminated by user</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-241">Número de sesiones finalizadas por usuarios</span><span class="sxs-lookup"><span data-stu-id="0b6aa-241">The total number of sessions terminated by users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6aa-242">Solicitudes de notificación de inserción totales</span><span class="sxs-lookup"><span data-stu-id="0b6aa-242">Total Push Notification Requests</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-243">Número total de solicitudes de notificación de inserción</span><span class="sxs-lookup"><span data-stu-id="0b6aa-243">The total number of push notification requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b6aa-244">Solicitudes de notificación de inserción erróneas totales</span><span class="sxs-lookup"><span data-stu-id="0b6aa-244">Total Push Notification Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-245">Número total de solicitudes de notificación de inserción erróneas</span><span class="sxs-lookup"><span data-stu-id="0b6aa-245">The total number of push notification requests that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6aa-246">Solicitudes de notificación de inserción correctas totales</span><span class="sxs-lookup"><span data-stu-id="0b6aa-246">Total Push Notification Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-247">Número total de solicitudes de notificación de inserción realizadas correctamente</span><span class="sxs-lookup"><span data-stu-id="0b6aa-247">The total number of push notification requests that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b6aa-248">Solicitudes de notificación de inserción reducidas totales</span><span class="sxs-lookup"><span data-stu-id="0b6aa-248">Total Push Notification Requests Throttled</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-249">Número total de solicitudes de notificación de inserción que se han reducido</span><span class="sxs-lookup"><span data-stu-id="0b6aa-249">The total number of push notification requests that were throttled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6aa-250">Solicitudes erróneas totales</span><span class="sxs-lookup"><span data-stu-id="0b6aa-250">Total Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-251">Número total de solicitudes erróneas</span><span class="sxs-lookup"><span data-stu-id="0b6aa-251">The total number of requests that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b6aa-252">Solicitudes totales recibidas en el canal de comandos</span><span class="sxs-lookup"><span data-stu-id="0b6aa-252">Total Requests received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-253">Número total de solicitudes recibidas en el canal de comandos</span><span class="sxs-lookup"><span data-stu-id="0b6aa-253">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6aa-254">Solicitudes rechazadas totales</span><span class="sxs-lookup"><span data-stu-id="0b6aa-254">Total Requests Rejected</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-255">Número total de solicitudes que se han rechazado</span><span class="sxs-lookup"><span data-stu-id="0b6aa-255">The total number of requests that were rejected</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b6aa-256">Solicitudes correctas totales</span><span class="sxs-lookup"><span data-stu-id="0b6aa-256">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-257">Número total de solicitudes realizadas al servicio de movilidad correctamente</span><span class="sxs-lookup"><span data-stu-id="0b6aa-257">The total number of requests made to the Mobility Service that succeeded</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6aa-258">Recuento de sesiones iniciadas totales</span><span class="sxs-lookup"><span data-stu-id="0b6aa-258">Total Session Initiated Count</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-259">Número total de sesiones que se han iniciado desde que se inició el servicio de movilidad</span><span class="sxs-lookup"><span data-stu-id="0b6aa-259">The total number of sessions that were initiated since the Mobility Service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b6aa-260">Sesiones totales finalizadas debido a que se ha agotado el tiempo de espera de inactividad del usuario</span><span class="sxs-lookup"><span data-stu-id="0b6aa-260">Total Sessions Terminated Because of User Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-261">Número total de sesiones que han finalizado porque se ha agotado el tiempo de espera de inactividad del usuario</span><span class="sxs-lookup"><span data-stu-id="0b6aa-261">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6aa-262">Llamadas de voz entrantes correctas totales</span><span class="sxs-lookup"><span data-stu-id="0b6aa-262">Total Successful Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-263">Número total de llamadas de voz entradas que se han realizado correctamente</span><span class="sxs-lookup"><span data-stu-id="0b6aa-263">The total number of inbound voice calls that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b6aa-264">Llamadas de voz salientes correctas totales</span><span class="sxs-lookup"><span data-stu-id="0b6aa-264">Total Successful Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="0b6aa-265">Número total de llamadas de voz salientes que se han realizado correctamente</span><span class="sxs-lookup"><span data-stu-id="0b6aa-265">The total number of outbound voice calls that were successful</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

