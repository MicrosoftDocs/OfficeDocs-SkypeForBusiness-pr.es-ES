---
title: Interpretación de los resultados
description: Interpretación de los resultados.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Interpreting the Results
ms:assetid: dd7f199f-7075-4d88-bb84-49a7e05eb593
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945608(v=OCS.15)
ms:contentKeyID: 51541433
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8342a1ec1e15e42852fc5293f87342e98587a60
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565346"
---
# <a name="interpreting-the-results"></a><span data-ttu-id="fd03a-103">Interpretación de los resultados</span><span class="sxs-lookup"><span data-stu-id="fd03a-103">Interpreting the Results</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd03a-104">_**Última modificación del tema:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="fd03a-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="fd03a-105">La herramienta stress and Performance (LyncPerfTool.exe) de Lync Server 2013 tiene muchos contadores que puede usar para comprender lo que hace el cliente y si se encuentra con problemas.</span><span class="sxs-lookup"><span data-stu-id="fd03a-105">The Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) has many counters that you can use to understand what the client is doing and whether it is encountering issues.</span></span>

<div>

## <a name="client-counters"></a><span data-ttu-id="fd03a-106">Contadores del cliente</span><span class="sxs-lookup"><span data-stu-id="fd03a-106">Client Counters</span></span>

<span data-ttu-id="fd03a-107">Cada instancia de LyncPerfTool.exe que se ejecuta tiene una instancia independiente de los contadores.</span><span class="sxs-lookup"><span data-stu-id="fd03a-107">Each instance of LyncPerfTool.exe that is running has a separate instance of the counters.</span></span> <span data-ttu-id="fd03a-108">Cada instancia se nombra mediante su identificador de proceso.</span><span class="sxs-lookup"><span data-stu-id="fd03a-108">Each instance is named by its process ID.</span></span>

<span data-ttu-id="fd03a-109">Si los clientes están sobrecargados, pueden producirse problemas.</span><span class="sxs-lookup"><span data-stu-id="fd03a-109">If the clients are overloaded, issues can occur.</span></span> <span data-ttu-id="fd03a-110">Para evitar estos problemas, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fd03a-110">To prevent these issues, do the following:</span></span>

1.  <span data-ttu-id="fd03a-111">Supervise la CPU y el uso de memoria en los equipos cliente.</span><span class="sxs-lookup"><span data-stu-id="fd03a-111">Monitor the CPU and the memory usage on the client computers.</span></span> <span data-ttu-id="fd03a-112">Si la CPU es constantemente superior al 90 por ciento, reduzca el número de usuarios.</span><span class="sxs-lookup"><span data-stu-id="fd03a-112">If the CPU is consistently above 90 percent, reduce the number of users.</span></span>

2.  <span data-ttu-id="fd03a-113">Si el tamaño de la memoria es alto, puede tener problemas si el archivo de paginación no es lo suficientemente grande.</span><span class="sxs-lookup"><span data-stu-id="fd03a-113">If the memory footprint is high, you could run into issues if the page file is not big enough.</span></span> <span data-ttu-id="fd03a-114">Compruebe que la carga de asignación no alcanza el límite del equipo.</span><span class="sxs-lookup"><span data-stu-id="fd03a-114">Verify that the Commit Charge is not hitting the limit on the computer.</span></span> <span data-ttu-id="fd03a-115">Si está teniendo en cuenta los límites de memoria, considere la posibilidad de aumentar el tamaño del archivo de paginación o reducir el número de usuarios.</span><span class="sxs-lookup"><span data-stu-id="fd03a-115">If you are running into memory limits, consider increasing the page file size or reducing the number of users</span></span>

<span data-ttu-id="fd03a-116">En las tablas siguientes se enumeran los contadores de rendimiento LyncPerfTool clave.</span><span class="sxs-lookup"><span data-stu-id="fd03a-116">The following tables list the key LyncPerfTool performance counters.</span></span>

<span data-ttu-id="fd03a-117">**Información general**</span><span class="sxs-lookup"><span data-stu-id="fd03a-117">**General Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fd03a-118"><strong>Contador de rendimiento</strong></span><span class="sxs-lookup"><span data-stu-id="fd03a-118"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="fd03a-119"><strong>Descripción</strong></span><span class="sxs-lookup"><span data-stu-id="fd03a-119"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd03a-120">Tiempo invertido en minutos</span><span class="sxs-lookup"><span data-stu-id="fd03a-120">Time Spent in Minutes</span></span></p></td>
<td><p><span data-ttu-id="fd03a-121">Tiempo transcurrido desde que se inició el proceso.</span><span class="sxs-lookup"><span data-stu-id="fd03a-121">Time spent since the process was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd03a-122">Puntos de conexión activos</span><span class="sxs-lookup"><span data-stu-id="fd03a-122">Active Endpoints</span></span></p></td>
<td><p><span data-ttu-id="fd03a-123">Número de extremos conectados actualmente al servidor.</span><span class="sxs-lookup"><span data-stu-id="fd03a-123">Number of endpoints currently connected to the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd03a-124">Inicios de sesión con errores</span><span class="sxs-lookup"><span data-stu-id="fd03a-124">Failed Logons</span></span></p></td>
<td><p><span data-ttu-id="fd03a-125">Número total de errores de inicio de sesión de extremo.</span><span class="sxs-lookup"><span data-stu-id="fd03a-125">Total number of endpoint sign-in failures.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd03a-126">Intentos de inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="fd03a-126">Logon Attempts</span></span></p></td>
<td><p><span data-ttu-id="fd03a-127">Número total de intentos de inicio de sesión en el extremo.</span><span class="sxs-lookup"><span data-stu-id="fd03a-127">Total number of endpoint sign-in attempts.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd03a-128">Extremos desconectados</span><span class="sxs-lookup"><span data-stu-id="fd03a-128">Endpoints Disconnected</span></span></p></td>
<td><p><span data-ttu-id="fd03a-129">Número total de puntos de conexión que se han desconectado.</span><span class="sxs-lookup"><span data-stu-id="fd03a-129">Total number of endpoints that have been disconnected.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fd03a-130">**Información de presencia**</span><span class="sxs-lookup"><span data-stu-id="fd03a-130">**Presence Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fd03a-131"><strong>Contador de rendimiento</strong></span><span class="sxs-lookup"><span data-stu-id="fd03a-131"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="fd03a-132"><strong>Descripción</strong></span><span class="sxs-lookup"><span data-stu-id="fd03a-132"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd03a-133">Llamadas SetPresence</span><span class="sxs-lookup"><span data-stu-id="fd03a-133">SetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="fd03a-134">Número total de intentos de cambio de presencia.</span><span class="sxs-lookup"><span data-stu-id="fd03a-134">Total number of presence change attempts.</span></span> <span data-ttu-id="fd03a-135">Para diferentes tipos de cambios de presencia, vea el contador de rendimiento de llamadas de SetPresence (tipo de presencia).</span><span class="sxs-lookup"><span data-stu-id="fd03a-135">For different types of presence changes, see the SetPresence (Presence Type) Calls Performance Counter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd03a-136">NNN respuestas para SetPresence</span><span class="sxs-lookup"><span data-stu-id="fd03a-136">NNN Responses for SetPresence</span></span></p></td>
<td><p><span data-ttu-id="fd03a-137">Número total de los códigos de respuesta nnn recibidos desde el servidor.</span><span class="sxs-lookup"><span data-stu-id="fd03a-137">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd03a-138">Llamadas a GetPresence</span><span class="sxs-lookup"><span data-stu-id="fd03a-138">GetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="fd03a-139">Número total de intentos de obtener solicitud de presencia.</span><span class="sxs-lookup"><span data-stu-id="fd03a-139">Total number of get presence request attempts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd03a-140">NNN respuestas para GetPresence</span><span class="sxs-lookup"><span data-stu-id="fd03a-140">NNN Responses for GetPresence</span></span></p></td>
<td><p><span data-ttu-id="fd03a-141">Número total de los códigos de respuesta nnn recibidos desde el servidor.</span><span class="sxs-lookup"><span data-stu-id="fd03a-141">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fd03a-142">**Información del servicio de libreta de direcciones**</span><span class="sxs-lookup"><span data-stu-id="fd03a-142">**Address Book service Information**</span></span>

<span data-ttu-id="fd03a-143">En esta categoría se incluyen los contadores usados para supervisar las solicitudes de servicio de descarga de archivos del servicio de libreta de direcciones (ABS) y de la libreta de direcciones web de consultas.</span><span class="sxs-lookup"><span data-stu-id="fd03a-143">This category includes counters used to monitor Address Book service (ABS) file downloads and Address Book Web Query service requests.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fd03a-144"><strong>Contador de rendimiento</strong></span><span class="sxs-lookup"><span data-stu-id="fd03a-144"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="fd03a-145"><strong>Descripción</strong></span><span class="sxs-lookup"><span data-stu-id="fd03a-145"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd03a-146">Intento de descarga de archivo completo/Delta de ABS</span><span class="sxs-lookup"><span data-stu-id="fd03a-146">ABS Full/Delta File Downloads Attempted</span></span></p></td>
<td><p><span data-ttu-id="fd03a-147">Número total de solicitudes de descarga de archivos completos o delta que se intentaron.</span><span class="sxs-lookup"><span data-stu-id="fd03a-147">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd03a-148">Descargas de archivos completos/Delta de ABS correctamente</span><span class="sxs-lookup"><span data-stu-id="fd03a-148">ABS Full/Delta File Downloads Succeeded</span></span></p></td>
<td><p><span data-ttu-id="fd03a-149">Número total de solicitudes de descarga de archivos completos o delta que se intentaron.</span><span class="sxs-lookup"><span data-stu-id="fd03a-149">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd03a-150">Contadores relacionados con el servicio de consulta Web de libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="fd03a-150">Address Book Web Query service related counters</span></span></p></td>
<td><p><span data-ttu-id="fd03a-151">Descarga de archivos de la libreta de direcciones: contadores relacionados.</span><span class="sxs-lookup"><span data-stu-id="fd03a-151">Address book file download related counters.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd03a-152">Intentos de llamadas de ABS WS</span><span class="sxs-lookup"><span data-stu-id="fd03a-152">ABS WS Calls attempted</span></span></p></td>
<td><p><span data-ttu-id="fd03a-153">Número total de solicitudes de servicio de consulta Web de libreta de direcciones que se intentaron.</span><span class="sxs-lookup"><span data-stu-id="fd03a-153">Total number of Address Book Web Query service requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd03a-154">Llamadas de ABS WS correctas</span><span class="sxs-lookup"><span data-stu-id="fd03a-154">ABS WS Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="fd03a-155">Número total de solicitudes de servicio de consulta Web de libreta de direcciones que devolvieron un código de respuesta correcto.</span><span class="sxs-lookup"><span data-stu-id="fd03a-155">Total number of Address Book Web Query service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd03a-156">Error en las llamadas de ABS WS</span><span class="sxs-lookup"><span data-stu-id="fd03a-156">ABS WS Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="fd03a-157">Número total de solicitudes de servicio de consulta Web de libreta de direcciones que devolvieron un código de respuesta de error.</span><span class="sxs-lookup"><span data-stu-id="fd03a-157">Total number of Address Book Web Query service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fd03a-158">**Información de la lista de distribución (DL)**</span><span class="sxs-lookup"><span data-stu-id="fd03a-158">**Distribution List (DL) Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fd03a-159"><strong>Contador de rendimiento</strong></span><span class="sxs-lookup"><span data-stu-id="fd03a-159"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="fd03a-160"><strong>Descripción</strong></span><span class="sxs-lookup"><span data-stu-id="fd03a-160"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd03a-161">Llamadas intentadas</span><span class="sxs-lookup"><span data-stu-id="fd03a-161">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="fd03a-162">Número total de solicitudes de servicio Web de expansión de la lista de distribución (DLX) que se intentaron.</span><span class="sxs-lookup"><span data-stu-id="fd03a-162">Total number of distribution list expansion (DLX) web service requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd03a-163">Llamadas correctas</span><span class="sxs-lookup"><span data-stu-id="fd03a-163">Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="fd03a-164">Número total de solicitudes de servicio Web de DLX que devolvieron un código de respuesta correcto.</span><span class="sxs-lookup"><span data-stu-id="fd03a-164">Total number of DLX web service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd03a-165">Llamadas fallidas</span><span class="sxs-lookup"><span data-stu-id="fd03a-165">Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="fd03a-166">Número total de solicitudes de servicio Web de DLX que devolvieron un código de respuesta de error.</span><span class="sxs-lookup"><span data-stu-id="fd03a-166">Total number of DLX web service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fd03a-167">**Información básica de VoIP**</span><span class="sxs-lookup"><span data-stu-id="fd03a-167">**VoIP Basic Information**</span></span>

<span data-ttu-id="fd03a-168">Los contadores de rendimiento que se enumeran a continuación para todas las llamadas de voz sobre IP (VoIP), incluidas las llamadas a servidor de mediación, el servidor de conferencia A/V, el servidor perimetral, la aplicación de grupo de respuesta y el operador automático de conferencia, cuando estos escenarios están habilitados.</span><span class="sxs-lookup"><span data-stu-id="fd03a-168">The performance counters listed below report numbers for all Voice over IP (VoIP) calls, including calls to Mediation Server, A/V Conferencing Server, Edge Server, Response Group application, and Conference Auto Attendant, when these scenarios are enabled.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fd03a-169"><strong>Contador de rendimiento</strong></span><span class="sxs-lookup"><span data-stu-id="fd03a-169"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="fd03a-170"><strong>Descripción</strong></span><span class="sxs-lookup"><span data-stu-id="fd03a-170"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd03a-171">Llamadas activas</span><span class="sxs-lookup"><span data-stu-id="fd03a-171">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="fd03a-172">Número total de llamadas de voz entrantes y salientes actualmente en curso.</span><span class="sxs-lookup"><span data-stu-id="fd03a-172">Total number of incoming/outgoing voice calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd03a-173">Llamadas finalizadas</span><span class="sxs-lookup"><span data-stu-id="fd03a-173">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="fd03a-174">Número total de llamadas de voz entrantes y salientes ya finalizadas.</span><span class="sxs-lookup"><span data-stu-id="fd03a-174">Total number of incoming/outgoing voice calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd03a-175">Llamadas rechazadas</span><span class="sxs-lookup"><span data-stu-id="fd03a-175">Calls Declined</span></span></p></td>
<td><p><span data-ttu-id="fd03a-176">Número total de llamadas de voz entrantes rechazadas.</span><span class="sxs-lookup"><span data-stu-id="fd03a-176">Total number of incoming voice calls declined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd03a-177">Intentos de llamadas entrantes o salientes</span><span class="sxs-lookup"><span data-stu-id="fd03a-177">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="fd03a-178">Número total de llamadas de voz entrantes y salientes que se intentaron realizar.</span><span class="sxs-lookup"><span data-stu-id="fd03a-178">Total number of incoming/outgoing voice calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd03a-179">Llamadas entrantes/salientes establecidas</span><span class="sxs-lookup"><span data-stu-id="fd03a-179">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="fd03a-180">Número total de llamadas de voz entrantes y salientes establecidas.</span><span class="sxs-lookup"><span data-stu-id="fd03a-180">Total number of incoming/outgoing voice calls established.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd03a-181">Llamadas recibidas NNN</span><span class="sxs-lookup"><span data-stu-id="fd03a-181">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="fd03a-182">Número total de los códigos de respuesta nnn recibidos desde el servidor.</span><span class="sxs-lookup"><span data-stu-id="fd03a-182">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd03a-183">Tasa de transferencia de VoIP (%)</span><span class="sxs-lookup"><span data-stu-id="fd03a-183">VoIP Pass Rate (%)</span></span></p></td>
<td><p><span data-ttu-id="fd03a-184">Total de llamadas establecidas/total de llamadas intentadas.</span><span class="sxs-lookup"><span data-stu-id="fd03a-184">Total calls established/Total calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fd03a-185">**Información de llamada del servicio de grupo de respuesta**</span><span class="sxs-lookup"><span data-stu-id="fd03a-185">**Response Group service Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fd03a-186"><strong>Contador de rendimiento</strong></span><span class="sxs-lookup"><span data-stu-id="fd03a-186"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="fd03a-187"><strong>Descripción</strong></span><span class="sxs-lookup"><span data-stu-id="fd03a-187"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd03a-188">Llamadas activas</span><span class="sxs-lookup"><span data-stu-id="fd03a-188">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="fd03a-189">Número total de llamadas activas a la aplicación del grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="fd03a-189">Total number of active calls to the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd03a-190">Llamadas intentadas</span><span class="sxs-lookup"><span data-stu-id="fd03a-190">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="fd03a-191">Número total de intentos de llamadas.</span><span class="sxs-lookup"><span data-stu-id="fd03a-191">Total number of calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fd03a-192">**Información de llamada de la mensajería instantánea (mi)**</span><span class="sxs-lookup"><span data-stu-id="fd03a-192">**Instant Messaging (IM) Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fd03a-193"><strong>Contador de rendimiento</strong></span><span class="sxs-lookup"><span data-stu-id="fd03a-193"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="fd03a-194"><strong>Descripción</strong></span><span class="sxs-lookup"><span data-stu-id="fd03a-194"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd03a-195">Llamadas activas</span><span class="sxs-lookup"><span data-stu-id="fd03a-195">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="fd03a-196">Número total de llamadas entrantes o salientes de mensajería instantánea en curso.</span><span class="sxs-lookup"><span data-stu-id="fd03a-196">Total number of ongoing incoming/outgoing instant messaging calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd03a-197">Llamadas finalizadas</span><span class="sxs-lookup"><span data-stu-id="fd03a-197">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="fd03a-198">Número total de llamadas de mensajería instantánea entrantes o salientes que ya han finalizado.</span><span class="sxs-lookup"><span data-stu-id="fd03a-198">Total number of incoming/outgoing instant messaging calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd03a-199">Llamadas recibidas NNN</span><span class="sxs-lookup"><span data-stu-id="fd03a-199">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="fd03a-200">Número total de los códigos de respuesta nnn recibidos desde el servidor.</span><span class="sxs-lookup"><span data-stu-id="fd03a-200">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd03a-201">Mensajes de mensajería instantánea recibidos o enviados</span><span class="sxs-lookup"><span data-stu-id="fd03a-201">IM Messages Received/Sent</span></span></p></td>
<td><p><span data-ttu-id="fd03a-202">Número total de mensajes recibidos o enviados para todas las sesiones.</span><span class="sxs-lookup"><span data-stu-id="fd03a-202">Total number of messages received or sent for all sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd03a-203">Intentos de llamadas entrantes o salientes</span><span class="sxs-lookup"><span data-stu-id="fd03a-203">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="fd03a-204">Número total de llamadas entrantes o salientes de mensajería instantánea que se intentaron.</span><span class="sxs-lookup"><span data-stu-id="fd03a-204">Total number of incoming/outgoing instant messaging calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd03a-205">Llamadas entrantes/salientes establecidas</span><span class="sxs-lookup"><span data-stu-id="fd03a-205">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="fd03a-206">Número total de llamadas entrantes o salientes de mensajes instantáneos establecidas.</span><span class="sxs-lookup"><span data-stu-id="fd03a-206">Total number of incoming/outgoing instant message calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fd03a-207">**Información de llamadas de uso compartido de aplicaciones**</span><span class="sxs-lookup"><span data-stu-id="fd03a-207">**App Sharing Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fd03a-208"><strong>Contador de rendimiento</strong></span><span class="sxs-lookup"><span data-stu-id="fd03a-208"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="fd03a-209"><strong>Descripción</strong></span><span class="sxs-lookup"><span data-stu-id="fd03a-209"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd03a-210">Llamadas activas</span><span class="sxs-lookup"><span data-stu-id="fd03a-210">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="fd03a-211">Número total de llamadas de uso compartido de aplicaciones entrantes o salientes en curso.</span><span class="sxs-lookup"><span data-stu-id="fd03a-211">Total number of ongoing incoming/outgoing application sharing calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd03a-212">Llamadas finalizadas</span><span class="sxs-lookup"><span data-stu-id="fd03a-212">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="fd03a-213">Número total de llamadas entrantes o salientes de uso compartido de aplicaciones ya finalizadas.</span><span class="sxs-lookup"><span data-stu-id="fd03a-213">Total number of incoming/outgoing application sharing calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd03a-214">Llamadas recibidas NNN</span><span class="sxs-lookup"><span data-stu-id="fd03a-214">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="fd03a-215">Número total de los códigos de respuesta nnn recibidos desde el servidor.</span><span class="sxs-lookup"><span data-stu-id="fd03a-215">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd03a-216">Intentos de llamadas entrantes o salientes</span><span class="sxs-lookup"><span data-stu-id="fd03a-216">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="fd03a-217">Número total de llamadas de uso compartido de aplicaciones entrantes o salientes que se intentaron.</span><span class="sxs-lookup"><span data-stu-id="fd03a-217">Total number of incoming/outgoing application sharing calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd03a-218">Llamadas entrantes/salientes establecidas</span><span class="sxs-lookup"><span data-stu-id="fd03a-218">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="fd03a-219">Número total de llamadas de uso compartido de aplicaciones entrantes/salientes establecidas.</span><span class="sxs-lookup"><span data-stu-id="fd03a-219">Total number of incoming/outgoing application sharing calls established.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fd03a-220">**Información de llamada de CAA**</span><span class="sxs-lookup"><span data-stu-id="fd03a-220">**CAA Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fd03a-221"><strong>Contador de rendimiento</strong></span><span class="sxs-lookup"><span data-stu-id="fd03a-221"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="fd03a-222"><strong>Descripción</strong></span><span class="sxs-lookup"><span data-stu-id="fd03a-222"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd03a-223">Llamadas activas</span><span class="sxs-lookup"><span data-stu-id="fd03a-223">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="fd03a-224">Número total de llamadas de red telefónica conmutada (RTC) entrantes y salientes actualmente en curso.</span><span class="sxs-lookup"><span data-stu-id="fd03a-224">Total number of incoming/outgoing public switched telephone network (PSTN) calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd03a-225">Llamadas finalizadas</span><span class="sxs-lookup"><span data-stu-id="fd03a-225">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="fd03a-226">Número total de llamadas RTC entrantes o salientes que ya han finalizado.</span><span class="sxs-lookup"><span data-stu-id="fd03a-226">Total number of incoming/outgoing PSTN calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd03a-227">Intentos de llamadas entrantes o salientes</span><span class="sxs-lookup"><span data-stu-id="fd03a-227">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="fd03a-228">Número total de llamadas RTC entrantes o salientes que se intentaron.</span><span class="sxs-lookup"><span data-stu-id="fd03a-228">Total number of incoming/outgoing PSTN calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd03a-229">Llamadas entrantes/salientes establecidas</span><span class="sxs-lookup"><span data-stu-id="fd03a-229">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="fd03a-230">Número total de llamadas RTC entrantes y salientes establecidas.</span><span class="sxs-lookup"><span data-stu-id="fd03a-230">Total number of incoming/outgoing PSTN calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fd03a-231">**Información de conferencia**</span><span class="sxs-lookup"><span data-stu-id="fd03a-231">**Conference Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fd03a-232"><strong>Contador de rendimiento</strong></span><span class="sxs-lookup"><span data-stu-id="fd03a-232"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="fd03a-233"><strong>Descripción</strong></span><span class="sxs-lookup"><span data-stu-id="fd03a-233"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd03a-234">Conferencias de mensajería instantánea activas</span><span class="sxs-lookup"><span data-stu-id="fd03a-234">Active Instant Messaging Conferences</span></span></p></td>
<td><p><span data-ttu-id="fd03a-235">Número total de conferencias de mensajería instantánea en curso.</span><span class="sxs-lookup"><span data-stu-id="fd03a-235">Total number of ongoing instant messaging conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd03a-236">Conferencias de audio y vídeo activas</span><span class="sxs-lookup"><span data-stu-id="fd03a-236">Active Audio/Video Conferences</span></span></p></td>
<td><p><span data-ttu-id="fd03a-237">Número total de conferencias de audio/vídeo (A/V) en curso.</span><span class="sxs-lookup"><span data-stu-id="fd03a-237">Total number of ongoing audio/video (A/V) conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd03a-238">Conferencias de uso compartido de aplicaciones activas</span><span class="sxs-lookup"><span data-stu-id="fd03a-238">Active Application Sharing Conferences</span></span></p></td>
<td><p><span data-ttu-id="fd03a-239">Número total de conferencias de uso compartido de aplicaciones en curso.</span><span class="sxs-lookup"><span data-stu-id="fd03a-239">Total number of ongoing application sharing conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd03a-240">Número de participantes</span><span class="sxs-lookup"><span data-stu-id="fd03a-240">Number of Participants</span></span></p></td>
<td><p><span data-ttu-id="fd03a-241">Número total de participantes actualmente conectados a conferencias.</span><span class="sxs-lookup"><span data-stu-id="fd03a-241">Total number of participants currently connected to conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd03a-242">Error de programación de conferencia</span><span class="sxs-lookup"><span data-stu-id="fd03a-242">Conference Schedule Failure</span></span></p></td>
<td><p><span data-ttu-id="fd03a-243">Número total de errores al intentar programar una conferencia.</span><span class="sxs-lookup"><span data-stu-id="fd03a-243">Total number of failures while trying to schedule a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd03a-244">Error al unirse a la Conferencia</span><span class="sxs-lookup"><span data-stu-id="fd03a-244">Join Conference Failure</span></span></p></td>
<td><p><span data-ttu-id="fd03a-245">Número total de errores al intentar conectarse a una conferencia.</span><span class="sxs-lookup"><span data-stu-id="fd03a-245">Total number of failures while trying to connect to a conference.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fd03a-246">**Contadores de cliente de UCWA**</span><span class="sxs-lookup"><span data-stu-id="fd03a-246">**UCWA Client Counters**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fd03a-247"><strong>Contador de rendimiento</strong></span><span class="sxs-lookup"><span data-stu-id="fd03a-247"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="fd03a-248"><strong>Descripción</strong></span><span class="sxs-lookup"><span data-stu-id="fd03a-248"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd03a-249">Número total de combinaciones IMMCU correctas</span><span class="sxs-lookup"><span data-stu-id="fd03a-249">Total Number of IMMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="fd03a-250">Número total de conferencias de mensajería instantánea Unidas.</span><span class="sxs-lookup"><span data-stu-id="fd03a-250">Total number of instant messaging conferences joined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd03a-251">Número total de combinaciones DMCU correctas</span><span class="sxs-lookup"><span data-stu-id="fd03a-251">Total Number of DMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="fd03a-252">Número total de conferencias A/V combinadas.</span><span class="sxs-lookup"><span data-stu-id="fd03a-252">Total number of A/V conferences joined.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

