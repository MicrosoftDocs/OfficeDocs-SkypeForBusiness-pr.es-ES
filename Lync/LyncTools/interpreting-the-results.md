---
title: Interpretación de los resultados
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
ms.openlocfilehash: 4d02f69f8ea1c8eb7df004e063dba39f03bbe8b7
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755474"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="interpreting-the-results"></a><span data-ttu-id="90d1d-102">Interpretación de los resultados</span><span class="sxs-lookup"><span data-stu-id="90d1d-102">Interpreting the Results</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90d1d-103">_**Última modificación del tema:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="90d1d-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="90d1d-104">La herramienta stress and Performance (LyncPerfTool.exe) de Lync Server 2013 tiene muchos contadores que puede usar para comprender lo que hace el cliente y si se encuentra con problemas.</span><span class="sxs-lookup"><span data-stu-id="90d1d-104">The Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) has many counters that you can use to understand what the client is doing and whether it is encountering issues.</span></span>

<div>

## <a name="client-counters"></a><span data-ttu-id="90d1d-105">Contadores del cliente</span><span class="sxs-lookup"><span data-stu-id="90d1d-105">Client Counters</span></span>

<span data-ttu-id="90d1d-106">Cada instancia de LyncPerfTool.exe que se ejecuta tiene una instancia independiente de los contadores.</span><span class="sxs-lookup"><span data-stu-id="90d1d-106">Each instance of LyncPerfTool.exe that is running has a separate instance of the counters.</span></span> <span data-ttu-id="90d1d-107">Cada instancia se nombra mediante su identificador de proceso.</span><span class="sxs-lookup"><span data-stu-id="90d1d-107">Each instance is named by its process ID.</span></span>

<span data-ttu-id="90d1d-108">Si los clientes están sobrecargados, pueden producirse problemas.</span><span class="sxs-lookup"><span data-stu-id="90d1d-108">If the clients are overloaded, issues can occur.</span></span> <span data-ttu-id="90d1d-109">Para evitar estos problemas, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="90d1d-109">To prevent these issues, do the following:</span></span>

1.  <span data-ttu-id="90d1d-110">Supervise la CPU y el uso de memoria en los equipos cliente.</span><span class="sxs-lookup"><span data-stu-id="90d1d-110">Monitor the CPU and the memory usage on the client computers.</span></span> <span data-ttu-id="90d1d-111">Si la CPU es constantemente superior al 90 por ciento, reduzca el número de usuarios.</span><span class="sxs-lookup"><span data-stu-id="90d1d-111">If the CPU is consistently above 90 percent, reduce the number of users.</span></span>

2.  <span data-ttu-id="90d1d-112">Si el tamaño de la memoria es alto, puede tener problemas si el archivo de paginación no es lo suficientemente grande.</span><span class="sxs-lookup"><span data-stu-id="90d1d-112">If the memory footprint is high, you could run into issues if the page file is not big enough.</span></span> <span data-ttu-id="90d1d-113">Compruebe que la carga de asignación no alcanza el límite del equipo.</span><span class="sxs-lookup"><span data-stu-id="90d1d-113">Verify that the Commit Charge is not hitting the limit on the computer.</span></span> <span data-ttu-id="90d1d-114">Si está teniendo en cuenta los límites de memoria, considere la posibilidad de aumentar el tamaño del archivo de paginación o reducir el número de usuarios.</span><span class="sxs-lookup"><span data-stu-id="90d1d-114">If you are running into memory limits, consider increasing the page file size or reducing the number of users</span></span>

<span data-ttu-id="90d1d-115">En las tablas siguientes se enumeran los contadores de rendimiento LyncPerfTool clave.</span><span class="sxs-lookup"><span data-stu-id="90d1d-115">The following tables list the key LyncPerfTool performance counters.</span></span>

<span data-ttu-id="90d1d-116">**Información general**</span><span class="sxs-lookup"><span data-stu-id="90d1d-116">**General Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="90d1d-117"><strong>Contador de rendimiento</strong></span><span class="sxs-lookup"><span data-stu-id="90d1d-117"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="90d1d-118"><strong>Descripción</strong></span><span class="sxs-lookup"><span data-stu-id="90d1d-118"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="90d1d-119">Tiempo invertido en minutos</span><span class="sxs-lookup"><span data-stu-id="90d1d-119">Time Spent in Minutes</span></span></p></td>
<td><p><span data-ttu-id="90d1d-120">Tiempo transcurrido desde que se inició el proceso.</span><span class="sxs-lookup"><span data-stu-id="90d1d-120">Time spent since the process was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90d1d-121">Puntos de conexión activos</span><span class="sxs-lookup"><span data-stu-id="90d1d-121">Active Endpoints</span></span></p></td>
<td><p><span data-ttu-id="90d1d-122">Número de extremos conectados actualmente al servidor.</span><span class="sxs-lookup"><span data-stu-id="90d1d-122">Number of endpoints currently connected to the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90d1d-123">Inicios de sesión con errores</span><span class="sxs-lookup"><span data-stu-id="90d1d-123">Failed Logons</span></span></p></td>
<td><p><span data-ttu-id="90d1d-124">Número total de errores de inicio de sesión de extremo.</span><span class="sxs-lookup"><span data-stu-id="90d1d-124">Total number of endpoint sign-in failures.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90d1d-125">Intentos de inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="90d1d-125">Logon Attempts</span></span></p></td>
<td><p><span data-ttu-id="90d1d-126">Número total de intentos de inicio de sesión en el extremo.</span><span class="sxs-lookup"><span data-stu-id="90d1d-126">Total number of endpoint sign-in attempts.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90d1d-127">Extremos desconectados</span><span class="sxs-lookup"><span data-stu-id="90d1d-127">Endpoints Disconnected</span></span></p></td>
<td><p><span data-ttu-id="90d1d-128">Número total de puntos de conexión que se han desconectado.</span><span class="sxs-lookup"><span data-stu-id="90d1d-128">Total number of endpoints that have been disconnected.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="90d1d-129">**Información de presencia**</span><span class="sxs-lookup"><span data-stu-id="90d1d-129">**Presence Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="90d1d-130"><strong>Contador de rendimiento</strong></span><span class="sxs-lookup"><span data-stu-id="90d1d-130"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="90d1d-131"><strong>Descripción</strong></span><span class="sxs-lookup"><span data-stu-id="90d1d-131"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="90d1d-132">Llamadas SetPresence</span><span class="sxs-lookup"><span data-stu-id="90d1d-132">SetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="90d1d-133">Número total de intentos de cambio de presencia.</span><span class="sxs-lookup"><span data-stu-id="90d1d-133">Total number of presence change attempts.</span></span> <span data-ttu-id="90d1d-134">Para diferentes tipos de cambios de presencia, vea el contador de rendimiento de llamadas de SetPresence (tipo de presencia).</span><span class="sxs-lookup"><span data-stu-id="90d1d-134">For different types of presence changes, see the SetPresence (Presence Type) Calls Performance Counter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90d1d-135">NNN respuestas para SetPresence</span><span class="sxs-lookup"><span data-stu-id="90d1d-135">NNN Responses for SetPresence</span></span></p></td>
<td><p><span data-ttu-id="90d1d-136">Número total de los códigos de respuesta nnn recibidos desde el servidor.</span><span class="sxs-lookup"><span data-stu-id="90d1d-136">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90d1d-137">Llamadas a GetPresence</span><span class="sxs-lookup"><span data-stu-id="90d1d-137">GetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="90d1d-138">Número total de intentos de obtener solicitud de presencia.</span><span class="sxs-lookup"><span data-stu-id="90d1d-138">Total number of get presence request attempts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90d1d-139">NNN respuestas para GetPresence</span><span class="sxs-lookup"><span data-stu-id="90d1d-139">NNN Responses for GetPresence</span></span></p></td>
<td><p><span data-ttu-id="90d1d-140">Número total de los códigos de respuesta nnn recibidos desde el servidor.</span><span class="sxs-lookup"><span data-stu-id="90d1d-140">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="90d1d-141">**Información del servicio de libreta de direcciones**</span><span class="sxs-lookup"><span data-stu-id="90d1d-141">**Address Book service Information**</span></span>

<span data-ttu-id="90d1d-142">En esta categoría se incluyen los contadores usados para supervisar las solicitudes de servicio de descarga de archivos del servicio de libreta de direcciones (ABS) y de la libreta de direcciones web de consultas.</span><span class="sxs-lookup"><span data-stu-id="90d1d-142">This category includes counters used to monitor Address Book service (ABS) file downloads and Address Book Web Query service requests.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="90d1d-143"><strong>Contador de rendimiento</strong></span><span class="sxs-lookup"><span data-stu-id="90d1d-143"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="90d1d-144"><strong>Descripción</strong></span><span class="sxs-lookup"><span data-stu-id="90d1d-144"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="90d1d-145">Intento de descarga de archivo completo/Delta de ABS</span><span class="sxs-lookup"><span data-stu-id="90d1d-145">ABS Full/Delta File Downloads Attempted</span></span></p></td>
<td><p><span data-ttu-id="90d1d-146">Número total de solicitudes de descarga de archivos completos o delta que se intentaron.</span><span class="sxs-lookup"><span data-stu-id="90d1d-146">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90d1d-147">Descargas de archivos completos/Delta de ABS correctamente</span><span class="sxs-lookup"><span data-stu-id="90d1d-147">ABS Full/Delta File Downloads Succeeded</span></span></p></td>
<td><p><span data-ttu-id="90d1d-148">Número total de solicitudes de descarga de archivos completos o delta que se intentaron.</span><span class="sxs-lookup"><span data-stu-id="90d1d-148">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90d1d-149">Contadores relacionados con el servicio de consulta Web de libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="90d1d-149">Address Book Web Query service related counters</span></span></p></td>
<td><p><span data-ttu-id="90d1d-150">Descarga de archivos de la libreta de direcciones: contadores relacionados.</span><span class="sxs-lookup"><span data-stu-id="90d1d-150">Address book file download related counters.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90d1d-151">Intentos de llamadas de ABS WS</span><span class="sxs-lookup"><span data-stu-id="90d1d-151">ABS WS Calls attempted</span></span></p></td>
<td><p><span data-ttu-id="90d1d-152">Número total de solicitudes de servicio de consulta Web de libreta de direcciones que se intentaron.</span><span class="sxs-lookup"><span data-stu-id="90d1d-152">Total number of Address Book Web Query service requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90d1d-153">Llamadas de ABS WS correctas</span><span class="sxs-lookup"><span data-stu-id="90d1d-153">ABS WS Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="90d1d-154">Número total de solicitudes de servicio de consulta Web de libreta de direcciones que devolvieron un código de respuesta correcto.</span><span class="sxs-lookup"><span data-stu-id="90d1d-154">Total number of Address Book Web Query service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90d1d-155">Error en las llamadas de ABS WS</span><span class="sxs-lookup"><span data-stu-id="90d1d-155">ABS WS Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="90d1d-156">Número total de solicitudes de servicio de consulta Web de libreta de direcciones que devolvieron un código de respuesta de error.</span><span class="sxs-lookup"><span data-stu-id="90d1d-156">Total number of Address Book Web Query service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="90d1d-157">**Información de la lista de distribución (DL)**</span><span class="sxs-lookup"><span data-stu-id="90d1d-157">**Distribution List (DL) Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="90d1d-158"><strong>Contador de rendimiento</strong></span><span class="sxs-lookup"><span data-stu-id="90d1d-158"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="90d1d-159"><strong>Descripción</strong></span><span class="sxs-lookup"><span data-stu-id="90d1d-159"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="90d1d-160">Llamadas intentadas</span><span class="sxs-lookup"><span data-stu-id="90d1d-160">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="90d1d-161">Número total de solicitudes de servicio Web de expansión de la lista de distribución (DLX) que se intentaron.</span><span class="sxs-lookup"><span data-stu-id="90d1d-161">Total number of distribution list expansion (DLX) web service requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90d1d-162">Llamadas correctas</span><span class="sxs-lookup"><span data-stu-id="90d1d-162">Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="90d1d-163">Número total de solicitudes de servicio Web de DLX que devolvieron un código de respuesta correcto.</span><span class="sxs-lookup"><span data-stu-id="90d1d-163">Total number of DLX web service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90d1d-164">Llamadas fallidas</span><span class="sxs-lookup"><span data-stu-id="90d1d-164">Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="90d1d-165">Número total de solicitudes de servicio Web de DLX que devolvieron un código de respuesta de error.</span><span class="sxs-lookup"><span data-stu-id="90d1d-165">Total number of DLX web service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="90d1d-166">**Información básica de VoIP**</span><span class="sxs-lookup"><span data-stu-id="90d1d-166">**VoIP Basic Information**</span></span>

<span data-ttu-id="90d1d-167">Los contadores de rendimiento que se enumeran a continuación para todas las llamadas de voz sobre IP (VoIP), incluidas las llamadas a servidor de mediación, el servidor de conferencia A/V, el servidor perimetral, la aplicación de grupo de respuesta y el operador automático de conferencia, cuando estos escenarios están habilitados.</span><span class="sxs-lookup"><span data-stu-id="90d1d-167">The performance counters listed below report numbers for all Voice over IP (VoIP) calls, including calls to Mediation Server, A/V Conferencing Server, Edge Server, Response Group application, and Conference Auto Attendant, when these scenarios are enabled.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="90d1d-168"><strong>Contador de rendimiento</strong></span><span class="sxs-lookup"><span data-stu-id="90d1d-168"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="90d1d-169"><strong>Descripción</strong></span><span class="sxs-lookup"><span data-stu-id="90d1d-169"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="90d1d-170">Llamadas activas</span><span class="sxs-lookup"><span data-stu-id="90d1d-170">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="90d1d-171">Número total de llamadas de voz entrantes y salientes actualmente en curso.</span><span class="sxs-lookup"><span data-stu-id="90d1d-171">Total number of incoming/outgoing voice calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90d1d-172">Llamadas finalizadas</span><span class="sxs-lookup"><span data-stu-id="90d1d-172">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="90d1d-173">Número total de llamadas de voz entrantes y salientes ya finalizadas.</span><span class="sxs-lookup"><span data-stu-id="90d1d-173">Total number of incoming/outgoing voice calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90d1d-174">Llamadas rechazadas</span><span class="sxs-lookup"><span data-stu-id="90d1d-174">Calls Declined</span></span></p></td>
<td><p><span data-ttu-id="90d1d-175">Número total de llamadas de voz entrantes rechazadas.</span><span class="sxs-lookup"><span data-stu-id="90d1d-175">Total number of incoming voice calls declined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90d1d-176">Intentos de llamadas entrantes o salientes</span><span class="sxs-lookup"><span data-stu-id="90d1d-176">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="90d1d-177">Número total de llamadas de voz entrantes y salientes que se intentaron realizar.</span><span class="sxs-lookup"><span data-stu-id="90d1d-177">Total number of incoming/outgoing voice calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90d1d-178">Llamadas entrantes/salientes establecidas</span><span class="sxs-lookup"><span data-stu-id="90d1d-178">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="90d1d-179">Número total de llamadas de voz entrantes y salientes establecidas.</span><span class="sxs-lookup"><span data-stu-id="90d1d-179">Total number of incoming/outgoing voice calls established.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90d1d-180">Llamadas recibidas NNN</span><span class="sxs-lookup"><span data-stu-id="90d1d-180">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="90d1d-181">Número total de los códigos de respuesta nnn recibidos desde el servidor.</span><span class="sxs-lookup"><span data-stu-id="90d1d-181">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90d1d-182">Tasa de transferencia de VoIP (%)</span><span class="sxs-lookup"><span data-stu-id="90d1d-182">VoIP Pass Rate (%)</span></span></p></td>
<td><p><span data-ttu-id="90d1d-183">Total de llamadas establecidas/total de llamadas intentadas.</span><span class="sxs-lookup"><span data-stu-id="90d1d-183">Total calls established/Total calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="90d1d-184">**Información de llamada del servicio de grupo de respuesta**</span><span class="sxs-lookup"><span data-stu-id="90d1d-184">**Response Group service Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="90d1d-185"><strong>Contador de rendimiento</strong></span><span class="sxs-lookup"><span data-stu-id="90d1d-185"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="90d1d-186"><strong>Descripción</strong></span><span class="sxs-lookup"><span data-stu-id="90d1d-186"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="90d1d-187">Llamadas activas</span><span class="sxs-lookup"><span data-stu-id="90d1d-187">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="90d1d-188">Número total de llamadas activas a la aplicación del grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="90d1d-188">Total number of active calls to the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90d1d-189">Llamadas intentadas</span><span class="sxs-lookup"><span data-stu-id="90d1d-189">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="90d1d-190">Número total de intentos de llamadas.</span><span class="sxs-lookup"><span data-stu-id="90d1d-190">Total number of calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="90d1d-191">**Información de llamada de la mensajería instantánea (mi)**</span><span class="sxs-lookup"><span data-stu-id="90d1d-191">**Instant Messaging (IM) Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="90d1d-192"><strong>Contador de rendimiento</strong></span><span class="sxs-lookup"><span data-stu-id="90d1d-192"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="90d1d-193"><strong>Descripción</strong></span><span class="sxs-lookup"><span data-stu-id="90d1d-193"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="90d1d-194">Llamadas activas</span><span class="sxs-lookup"><span data-stu-id="90d1d-194">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="90d1d-195">Número total de llamadas entrantes o salientes de mensajería instantánea en curso.</span><span class="sxs-lookup"><span data-stu-id="90d1d-195">Total number of ongoing incoming/outgoing instant messaging calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90d1d-196">Llamadas finalizadas</span><span class="sxs-lookup"><span data-stu-id="90d1d-196">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="90d1d-197">Número total de llamadas de mensajería instantánea entrantes o salientes que ya han finalizado.</span><span class="sxs-lookup"><span data-stu-id="90d1d-197">Total number of incoming/outgoing instant messaging calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90d1d-198">Llamadas recibidas NNN</span><span class="sxs-lookup"><span data-stu-id="90d1d-198">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="90d1d-199">Número total de los códigos de respuesta nnn recibidos desde el servidor.</span><span class="sxs-lookup"><span data-stu-id="90d1d-199">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90d1d-200">Mensajes de mensajería instantánea recibidos o enviados</span><span class="sxs-lookup"><span data-stu-id="90d1d-200">IM Messages Received/Sent</span></span></p></td>
<td><p><span data-ttu-id="90d1d-201">Número total de mensajes recibidos o enviados para todas las sesiones.</span><span class="sxs-lookup"><span data-stu-id="90d1d-201">Total number of messages received or sent for all sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90d1d-202">Intentos de llamadas entrantes o salientes</span><span class="sxs-lookup"><span data-stu-id="90d1d-202">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="90d1d-203">Número total de llamadas entrantes o salientes de mensajería instantánea que se intentaron.</span><span class="sxs-lookup"><span data-stu-id="90d1d-203">Total number of incoming/outgoing instant messaging calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90d1d-204">Llamadas entrantes/salientes establecidas</span><span class="sxs-lookup"><span data-stu-id="90d1d-204">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="90d1d-205">Número total de llamadas entrantes o salientes de mensajes instantáneos establecidas.</span><span class="sxs-lookup"><span data-stu-id="90d1d-205">Total number of incoming/outgoing instant message calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="90d1d-206">**Información de llamadas de uso compartido de aplicaciones**</span><span class="sxs-lookup"><span data-stu-id="90d1d-206">**App Sharing Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="90d1d-207"><strong>Contador de rendimiento</strong></span><span class="sxs-lookup"><span data-stu-id="90d1d-207"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="90d1d-208"><strong>Descripción</strong></span><span class="sxs-lookup"><span data-stu-id="90d1d-208"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="90d1d-209">Llamadas activas</span><span class="sxs-lookup"><span data-stu-id="90d1d-209">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="90d1d-210">Número total de llamadas de uso compartido de aplicaciones entrantes o salientes en curso.</span><span class="sxs-lookup"><span data-stu-id="90d1d-210">Total number of ongoing incoming/outgoing application sharing calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90d1d-211">Llamadas finalizadas</span><span class="sxs-lookup"><span data-stu-id="90d1d-211">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="90d1d-212">Número total de llamadas entrantes o salientes de uso compartido de aplicaciones ya finalizadas.</span><span class="sxs-lookup"><span data-stu-id="90d1d-212">Total number of incoming/outgoing application sharing calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90d1d-213">Llamadas recibidas NNN</span><span class="sxs-lookup"><span data-stu-id="90d1d-213">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="90d1d-214">Número total de los códigos de respuesta nnn recibidos desde el servidor.</span><span class="sxs-lookup"><span data-stu-id="90d1d-214">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90d1d-215">Intentos de llamadas entrantes o salientes</span><span class="sxs-lookup"><span data-stu-id="90d1d-215">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="90d1d-216">Número total de llamadas de uso compartido de aplicaciones entrantes o salientes que se intentaron.</span><span class="sxs-lookup"><span data-stu-id="90d1d-216">Total number of incoming/outgoing application sharing calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90d1d-217">Llamadas entrantes/salientes establecidas</span><span class="sxs-lookup"><span data-stu-id="90d1d-217">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="90d1d-218">Número total de llamadas de uso compartido de aplicaciones entrantes/salientes establecidas.</span><span class="sxs-lookup"><span data-stu-id="90d1d-218">Total number of incoming/outgoing application sharing calls established.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="90d1d-219">**Información de llamada de CAA**</span><span class="sxs-lookup"><span data-stu-id="90d1d-219">**CAA Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="90d1d-220"><strong>Contador de rendimiento</strong></span><span class="sxs-lookup"><span data-stu-id="90d1d-220"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="90d1d-221"><strong>Descripción</strong></span><span class="sxs-lookup"><span data-stu-id="90d1d-221"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="90d1d-222">Llamadas activas</span><span class="sxs-lookup"><span data-stu-id="90d1d-222">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="90d1d-223">Número total de llamadas de red telefónica conmutada (RTC) entrantes y salientes actualmente en curso.</span><span class="sxs-lookup"><span data-stu-id="90d1d-223">Total number of incoming/outgoing public switched telephone network (PSTN) calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90d1d-224">Llamadas finalizadas</span><span class="sxs-lookup"><span data-stu-id="90d1d-224">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="90d1d-225">Número total de llamadas RTC entrantes o salientes que ya han finalizado.</span><span class="sxs-lookup"><span data-stu-id="90d1d-225">Total number of incoming/outgoing PSTN calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90d1d-226">Intentos de llamadas entrantes o salientes</span><span class="sxs-lookup"><span data-stu-id="90d1d-226">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="90d1d-227">Número total de llamadas RTC entrantes o salientes que se intentaron.</span><span class="sxs-lookup"><span data-stu-id="90d1d-227">Total number of incoming/outgoing PSTN calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90d1d-228">Llamadas entrantes/salientes establecidas</span><span class="sxs-lookup"><span data-stu-id="90d1d-228">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="90d1d-229">Número total de llamadas RTC entrantes y salientes establecidas.</span><span class="sxs-lookup"><span data-stu-id="90d1d-229">Total number of incoming/outgoing PSTN calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="90d1d-230">**Información de conferencia**</span><span class="sxs-lookup"><span data-stu-id="90d1d-230">**Conference Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="90d1d-231"><strong>Contador de rendimiento</strong></span><span class="sxs-lookup"><span data-stu-id="90d1d-231"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="90d1d-232"><strong>Descripción</strong></span><span class="sxs-lookup"><span data-stu-id="90d1d-232"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="90d1d-233">Conferencias de mensajería instantánea activas</span><span class="sxs-lookup"><span data-stu-id="90d1d-233">Active Instant Messaging Conferences</span></span></p></td>
<td><p><span data-ttu-id="90d1d-234">Número total de conferencias de mensajería instantánea en curso.</span><span class="sxs-lookup"><span data-stu-id="90d1d-234">Total number of ongoing instant messaging conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90d1d-235">Conferencias de audio y vídeo activas</span><span class="sxs-lookup"><span data-stu-id="90d1d-235">Active Audio/Video Conferences</span></span></p></td>
<td><p><span data-ttu-id="90d1d-236">Número total de conferencias de audio/vídeo (A/V) en curso.</span><span class="sxs-lookup"><span data-stu-id="90d1d-236">Total number of ongoing audio/video (A/V) conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90d1d-237">Conferencias de uso compartido de aplicaciones activas</span><span class="sxs-lookup"><span data-stu-id="90d1d-237">Active Application Sharing Conferences</span></span></p></td>
<td><p><span data-ttu-id="90d1d-238">Número total de conferencias de uso compartido de aplicaciones en curso.</span><span class="sxs-lookup"><span data-stu-id="90d1d-238">Total number of ongoing application sharing conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90d1d-239">Número de participantes</span><span class="sxs-lookup"><span data-stu-id="90d1d-239">Number of Participants</span></span></p></td>
<td><p><span data-ttu-id="90d1d-240">Número total de participantes actualmente conectados a conferencias.</span><span class="sxs-lookup"><span data-stu-id="90d1d-240">Total number of participants currently connected to conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90d1d-241">Error de programación de conferencia</span><span class="sxs-lookup"><span data-stu-id="90d1d-241">Conference Schedule Failure</span></span></p></td>
<td><p><span data-ttu-id="90d1d-242">Número total de errores al intentar programar una conferencia.</span><span class="sxs-lookup"><span data-stu-id="90d1d-242">Total number of failures while trying to schedule a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90d1d-243">Error al unirse a la Conferencia</span><span class="sxs-lookup"><span data-stu-id="90d1d-243">Join Conference Failure</span></span></p></td>
<td><p><span data-ttu-id="90d1d-244">Número total de errores al intentar conectarse a una conferencia.</span><span class="sxs-lookup"><span data-stu-id="90d1d-244">Total number of failures while trying to connect to a conference.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="90d1d-245">**Contadores de cliente de UCWA**</span><span class="sxs-lookup"><span data-stu-id="90d1d-245">**UCWA Client Counters**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="90d1d-246"><strong>Contador de rendimiento</strong></span><span class="sxs-lookup"><span data-stu-id="90d1d-246"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="90d1d-247"><strong>Descripción</strong></span><span class="sxs-lookup"><span data-stu-id="90d1d-247"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="90d1d-248">Número total de combinaciones IMMCU correctas</span><span class="sxs-lookup"><span data-stu-id="90d1d-248">Total Number of IMMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="90d1d-249">Número total de conferencias de mensajería instantánea Unidas.</span><span class="sxs-lookup"><span data-stu-id="90d1d-249">Total number of instant messaging conferences joined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90d1d-250">Número total de combinaciones DMCU correctas</span><span class="sxs-lookup"><span data-stu-id="90d1d-250">Total Number of DMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="90d1d-251">Número total de conferencias A/V combinadas.</span><span class="sxs-lookup"><span data-stu-id="90d1d-251">Total number of A/V conferences joined.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

