---
title: 'Lync Server 2013: eventos de UCWA'
description: 'Lync Server 2013: eventos de UCWA.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UCWA events
ms:assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945621(v=OCS.15)
ms:contentKeyID: 51541461
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8104ce9c7533350f40ce194e1cde205bc3692792
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548856"
---
# <a name="ucwa-events-in-lync-server-2013"></a><span data-ttu-id="9c50f-103">Eventos de UCWA en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c50f-103">UCWA events in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c50f-104">_**Última modificación del tema:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="9c50f-104">_**Topic Last Modified:** 2013-02-15_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="9c50f-105">Lync Server 2013 usa la API Web de comunicaciones unificadas (UCWA) para una serie de propósitos, desde el acceso a Microsoft Exchange para las búsquedas de contactos hasta la actualización de presencia para los clientes móviles.</span><span class="sxs-lookup"><span data-stu-id="9c50f-105">Lync Server 2013 uses the Unified Communications Web API (UCWA) for a number of purposes, from accessing Microsoft Exchange for contact searches to updating presence for mobile clients.</span></span>

<span data-ttu-id="9c50f-106">UCWA escribirá los registros de comportamiento operativo como tipos de evento informativos, de advertencia y de error.</span><span class="sxs-lookup"><span data-stu-id="9c50f-106">UCWA will write records of operational behavior as event types Informational, Warning, and Error.</span></span> <span data-ttu-id="9c50f-107">En la tabla siguiente se describen los eventos que pueden escribir los componentes de UCWA.</span><span class="sxs-lookup"><span data-stu-id="9c50f-107">The following table describes the events that can be written by the UCWA components.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9c50f-108">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="9c50f-108">Event ID</span></span></th>
<th><span data-ttu-id="9c50f-109">Tipo de evento</span><span class="sxs-lookup"><span data-stu-id="9c50f-109">Event Type</span></span></th>
<th><span data-ttu-id="9c50f-110">Resumen</span><span class="sxs-lookup"><span data-stu-id="9c50f-110">Summary</span></span></th>
<th><span data-ttu-id="9c50f-111">Causa y solución</span><span class="sxs-lookup"><span data-stu-id="9c50f-111">Cause and Resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9c50f-112">20001</span><span class="sxs-lookup"><span data-stu-id="9c50f-112">20001</span></span></p></td>
<td><p><span data-ttu-id="9c50f-113">Informativo</span><span class="sxs-lookup"><span data-stu-id="9c50f-113">Informational</span></span></p></td>
<td><p><span data-ttu-id="9c50f-114">UCWA inicializado</span><span class="sxs-lookup"><span data-stu-id="9c50f-114">UCWA initialized</span></span></p></td>
<td><p><span data-ttu-id="9c50f-115">N/D</span><span class="sxs-lookup"><span data-stu-id="9c50f-115">N/A</span></span></p>
<p><span data-ttu-id="9c50f-116">N/D</span><span class="sxs-lookup"><span data-stu-id="9c50f-116">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c50f-117">20002</span><span class="sxs-lookup"><span data-stu-id="9c50f-117">20002</span></span></p></td>
<td><p><span data-ttu-id="9c50f-118">Error</span><span class="sxs-lookup"><span data-stu-id="9c50f-118">Error</span></span></p></td>
<td><p><span data-ttu-id="9c50f-119">UCWA encontró una excepción inesperada durante la inicialización</span><span class="sxs-lookup"><span data-stu-id="9c50f-119">UCWA encountered an unexpected exception during initialization</span></span></p></td>
<td><p><span data-ttu-id="9c50f-120">Se ha producido un error inesperado durante la inicialización</span><span class="sxs-lookup"><span data-stu-id="9c50f-120">An unexpected error has occurred during initialization</span></span></p>
<p><span data-ttu-id="9c50f-121">Examine los detalles de la excepción en la entrada del registro de eventos asociada para determinar la causa posible</span><span class="sxs-lookup"><span data-stu-id="9c50f-121">Examine the exception details in the associated event log entry to determine the possible cause</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c50f-122">20003</span><span class="sxs-lookup"><span data-stu-id="9c50f-122">20003</span></span></p></td>
<td><p><span data-ttu-id="9c50f-123">Error</span><span class="sxs-lookup"><span data-stu-id="9c50f-123">Error</span></span></p></td>
<td><p><span data-ttu-id="9c50f-124">UCWA encontró una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="9c50f-124">UCWA encountered an unhandled exception</span></span></p></td>
<td><p><span data-ttu-id="9c50f-125">Se ha producido una excepción no controlada</span><span class="sxs-lookup"><span data-stu-id="9c50f-125">An unhandled exception happened</span></span></p>
<p><span data-ttu-id="9c50f-126">Reinicie el servidor.</span><span class="sxs-lookup"><span data-stu-id="9c50f-126">Restart the server.</span></span> <span data-ttu-id="9c50f-127">Si el problema continúa, póngase en contacto con el soporte técnico</span><span class="sxs-lookup"><span data-stu-id="9c50f-127">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c50f-128">20004</span><span class="sxs-lookup"><span data-stu-id="9c50f-128">20004</span></span></p></td>
<td><p><span data-ttu-id="9c50f-129">Error</span><span class="sxs-lookup"><span data-stu-id="9c50f-129">Error</span></span></p></td>
<td><p><span data-ttu-id="9c50f-130">No se puede tener acceso a Exchange para fotos HD</span><span class="sxs-lookup"><span data-stu-id="9c50f-130">Cannot access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="9c50f-131">La conexión con Exchange no está disponible</span><span class="sxs-lookup"><span data-stu-id="9c50f-131">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="9c50f-132">Asegurarse de que la conexión a Exchange está disponible</span><span class="sxs-lookup"><span data-stu-id="9c50f-132">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c50f-133">20005</span><span class="sxs-lookup"><span data-stu-id="9c50f-133">20005</span></span></p></td>
<td><p><span data-ttu-id="9c50f-134">Informativo</span><span class="sxs-lookup"><span data-stu-id="9c50f-134">Informational</span></span></p></td>
<td><p><span data-ttu-id="9c50f-135">Se recuperó el acceso a Exchange para fotos HD</span><span class="sxs-lookup"><span data-stu-id="9c50f-135">Recovered from failing to access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="9c50f-136">N/D</span><span class="sxs-lookup"><span data-stu-id="9c50f-136">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c50f-137">20006</span><span class="sxs-lookup"><span data-stu-id="9c50f-137">20006</span></span></p></td>
<td><p><span data-ttu-id="9c50f-138">Error</span><span class="sxs-lookup"><span data-stu-id="9c50f-138">Error</span></span></p></td>
<td><p><span data-ttu-id="9c50f-139">No se puede obtener acceso a Exchange para la búsqueda de contactos</span><span class="sxs-lookup"><span data-stu-id="9c50f-139">Cannot access Exchange for contact search</span></span></p></td>
<td><p><span data-ttu-id="9c50f-140">La conexión con Exchange no está disponible</span><span class="sxs-lookup"><span data-stu-id="9c50f-140">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="9c50f-141">Asegurarse de que la conexión a Exchange está disponible</span><span class="sxs-lookup"><span data-stu-id="9c50f-141">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c50f-142">20007</span><span class="sxs-lookup"><span data-stu-id="9c50f-142">20007</span></span></p></td>
<td><p><span data-ttu-id="9c50f-143">Informativo</span><span class="sxs-lookup"><span data-stu-id="9c50f-143">Informational</span></span></p></td>
<td><p><span data-ttu-id="9c50f-144">Se recuperó del error de búsqueda en el contacto de Exchange</span><span class="sxs-lookup"><span data-stu-id="9c50f-144">Recovered from failing to search contact in Exchange</span></span></p></td>
<td><p><span data-ttu-id="9c50f-145">N/D</span><span class="sxs-lookup"><span data-stu-id="9c50f-145">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c50f-146">20008</span><span class="sxs-lookup"><span data-stu-id="9c50f-146">20008</span></span></p></td>
<td><p><span data-ttu-id="9c50f-147">Advertencia</span><span class="sxs-lookup"><span data-stu-id="9c50f-147">Warning</span></span></p></td>
<td><p><span data-ttu-id="9c50f-148">Intento de suscribir más de las suscripciones de presencia permitidas por aplicación</span><span class="sxs-lookup"><span data-stu-id="9c50f-148">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p></td>
<td><p><span data-ttu-id="9c50f-149">Intento de suscribir más de las suscripciones de presencia permitidas por aplicación</span><span class="sxs-lookup"><span data-stu-id="9c50f-149">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p>
<p><span data-ttu-id="9c50f-150">Comprobar si los clientes tienen suscripciones innecesarias</span><span class="sxs-lookup"><span data-stu-id="9c50f-150">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c50f-151">20009</span><span class="sxs-lookup"><span data-stu-id="9c50f-151">20009</span></span></p></td>
<td><p><span data-ttu-id="9c50f-152">Advertencia</span><span class="sxs-lookup"><span data-stu-id="9c50f-152">Warning</span></span></p></td>
<td><p><span data-ttu-id="9c50f-153">Intento de suscribir más de las suscripciones de presencia permitidas por lote</span><span class="sxs-lookup"><span data-stu-id="9c50f-153">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p></td>
<td><p><span data-ttu-id="9c50f-154">Intento de suscribir más de las suscripciones de presencia permitidas por lote</span><span class="sxs-lookup"><span data-stu-id="9c50f-154">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p>
<p><span data-ttu-id="9c50f-155">Comprobar si los clientes tienen suscripciones innecesarias</span><span class="sxs-lookup"><span data-stu-id="9c50f-155">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c50f-156">20010</span><span class="sxs-lookup"><span data-stu-id="9c50f-156">20010</span></span></p></td>
<td><p><span data-ttu-id="9c50f-157">Error</span><span class="sxs-lookup"><span data-stu-id="9c50f-157">Error</span></span></p></td>
<td><p><span data-ttu-id="9c50f-158">No se pueden recuperar los datos en banda</span><span class="sxs-lookup"><span data-stu-id="9c50f-158">Cannot retrieve inband data</span></span></p></td>
<td><p><span data-ttu-id="9c50f-159">No se pueden recuperar los datos en banda</span><span class="sxs-lookup"><span data-stu-id="9c50f-159">Cannot retrieve inband data</span></span></p>
<p><span data-ttu-id="9c50f-160">Si el problema continúa, póngase en contacto con el soporte técnico</span><span class="sxs-lookup"><span data-stu-id="9c50f-160">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c50f-161">20011</span><span class="sxs-lookup"><span data-stu-id="9c50f-161">20011</span></span></p></td>
<td><p><span data-ttu-id="9c50f-162">Error</span><span class="sxs-lookup"><span data-stu-id="9c50f-162">Error</span></span></p></td>
<td><p><span data-ttu-id="9c50f-163">No se puede suscribir la presencia</span><span class="sxs-lookup"><span data-stu-id="9c50f-163">Cannot subscribe presence</span></span></p></td>
<td><p><span data-ttu-id="9c50f-164">No se puede suscribir la presencia</span><span class="sxs-lookup"><span data-stu-id="9c50f-164">Cannot subscribe presence</span></span></p>
<p><span data-ttu-id="9c50f-165">Si el problema continúa, póngase en contacto con el soporte técnico</span><span class="sxs-lookup"><span data-stu-id="9c50f-165">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c50f-166">20012</span><span class="sxs-lookup"><span data-stu-id="9c50f-166">20012</span></span></p></td>
<td><p><span data-ttu-id="9c50f-167">Error</span><span class="sxs-lookup"><span data-stu-id="9c50f-167">Error</span></span></p></td>
<td><p><span data-ttu-id="9c50f-168">No se pudo registrar el extremo</span><span class="sxs-lookup"><span data-stu-id="9c50f-168">Failed to register endpoint</span></span></p></td>
<td><p><span data-ttu-id="9c50f-169">No se pudo registrar el extremo</span><span class="sxs-lookup"><span data-stu-id="9c50f-169">Failed to register endpoint</span></span></p>
<p><span data-ttu-id="9c50f-170">Si el problema continúa, póngase en contacto con el soporte técnico</span><span class="sxs-lookup"><span data-stu-id="9c50f-170">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c50f-171">20013</span><span class="sxs-lookup"><span data-stu-id="9c50f-171">20013</span></span></p></td>
<td><p><span data-ttu-id="9c50f-172">Error</span><span class="sxs-lookup"><span data-stu-id="9c50f-172">Error</span></span></p></td>
<td><p><span data-ttu-id="9c50f-173">La MCU de mensajería instantánea no está disponible</span><span class="sxs-lookup"><span data-stu-id="9c50f-173">IM MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="9c50f-174">La MCU de mensajería instantánea no está disponible</span><span class="sxs-lookup"><span data-stu-id="9c50f-174">IM MCU is unavailable</span></span></p>
<p><span data-ttu-id="9c50f-175">Ver si la MCU de mensajería instantánea se está ejecutando</span><span class="sxs-lookup"><span data-stu-id="9c50f-175">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c50f-176">20014</span><span class="sxs-lookup"><span data-stu-id="9c50f-176">20014</span></span></p></td>
<td><p><span data-ttu-id="9c50f-177">Informativo</span><span class="sxs-lookup"><span data-stu-id="9c50f-177">Informational</span></span></p></td>
<td><p><span data-ttu-id="9c50f-178">Se recuperó el error de conexión a la MCU de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="9c50f-178">Recovered from failing to connect to IM MCU</span></span></p></td>
<td><p><span data-ttu-id="9c50f-179">N/D</span><span class="sxs-lookup"><span data-stu-id="9c50f-179">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c50f-180">20015</span><span class="sxs-lookup"><span data-stu-id="9c50f-180">20015</span></span></p></td>
<td><p><span data-ttu-id="9c50f-181">Error</span><span class="sxs-lookup"><span data-stu-id="9c50f-181">Error</span></span></p></td>
<td><p><span data-ttu-id="9c50f-182">La MCU antivirus no está disponible</span><span class="sxs-lookup"><span data-stu-id="9c50f-182">AV MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="9c50f-183">La MCU antivirus no está disponible</span><span class="sxs-lookup"><span data-stu-id="9c50f-183">AV MCU is unavailable</span></span></p>
<p><span data-ttu-id="9c50f-184">Ver si la MCU AV está en funcionamiento</span><span class="sxs-lookup"><span data-stu-id="9c50f-184">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c50f-185">20016</span><span class="sxs-lookup"><span data-stu-id="9c50f-185">20016</span></span></p></td>
<td><p><span data-ttu-id="9c50f-186">Informativo</span><span class="sxs-lookup"><span data-stu-id="9c50f-186">Informational</span></span></p></td>
<td><p><span data-ttu-id="9c50f-187">Se recuperó la conexión a un MCU AV</span><span class="sxs-lookup"><span data-stu-id="9c50f-187">Recovered from failing to connect to AV MCU</span></span></p></td>
<td><p><span data-ttu-id="9c50f-188">N/D</span><span class="sxs-lookup"><span data-stu-id="9c50f-188">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c50f-189">20017</span><span class="sxs-lookup"><span data-stu-id="9c50f-189">20017</span></span></p></td>
<td><p><span data-ttu-id="9c50f-190">Error</span><span class="sxs-lookup"><span data-stu-id="9c50f-190">Error</span></span></p></td>
<td><p><span data-ttu-id="9c50f-191">COMO la MCU no está disponible</span><span class="sxs-lookup"><span data-stu-id="9c50f-191">AS MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="9c50f-192">COMO la MCU no está disponible</span><span class="sxs-lookup"><span data-stu-id="9c50f-192">AS MCU is unavailable</span></span></p>
<p><span data-ttu-id="9c50f-193">Ver si se está ejecutando la MCU</span><span class="sxs-lookup"><span data-stu-id="9c50f-193">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c50f-194">20018</span><span class="sxs-lookup"><span data-stu-id="9c50f-194">20018</span></span></p></td>
<td><p><span data-ttu-id="9c50f-195">Informativo</span><span class="sxs-lookup"><span data-stu-id="9c50f-195">Informational</span></span></p></td>
<td><p><span data-ttu-id="9c50f-196">Se recuperó el error de conexión a como MCU</span><span class="sxs-lookup"><span data-stu-id="9c50f-196">Recovered from failing to connect to AS MCU</span></span></p></td>
<td><p><span data-ttu-id="9c50f-197">N/D</span><span class="sxs-lookup"><span data-stu-id="9c50f-197">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c50f-198">20019</span><span class="sxs-lookup"><span data-stu-id="9c50f-198">20019</span></span></p></td>
<td><p><span data-ttu-id="9c50f-199">Error</span><span class="sxs-lookup"><span data-stu-id="9c50f-199">Error</span></span></p></td>
<td><p><span data-ttu-id="9c50f-200">La MCU de datos no está disponible</span><span class="sxs-lookup"><span data-stu-id="9c50f-200">Data MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="9c50f-201">La MCU de datos no está disponible</span><span class="sxs-lookup"><span data-stu-id="9c50f-201">Data MCU is unavailable</span></span></p>
<p><span data-ttu-id="9c50f-202">Ver si Data MCU se está ejecutando</span><span class="sxs-lookup"><span data-stu-id="9c50f-202">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c50f-203">20020</span><span class="sxs-lookup"><span data-stu-id="9c50f-203">20020</span></span></p></td>
<td><p><span data-ttu-id="9c50f-204">Informativo</span><span class="sxs-lookup"><span data-stu-id="9c50f-204">Informational</span></span></p></td>
<td><p><span data-ttu-id="9c50f-205">Se recuperó el error de conexión a la MCU de datos</span><span class="sxs-lookup"><span data-stu-id="9c50f-205">Recovered from failing to connect to Data MCU</span></span></p></td>
<td><p><span data-ttu-id="9c50f-206">N/D</span><span class="sxs-lookup"><span data-stu-id="9c50f-206">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c50f-207">20021</span><span class="sxs-lookup"><span data-stu-id="9c50f-207">20021</span></span></p></td>
<td><p><span data-ttu-id="9c50f-208">Error</span><span class="sxs-lookup"><span data-stu-id="9c50f-208">Error</span></span></p></td>
<td><p><span data-ttu-id="9c50f-209">No se puede unir a mi MCU</span><span class="sxs-lookup"><span data-stu-id="9c50f-209">Cannot join IM MCU</span></span></p></td>
<td><p><span data-ttu-id="9c50f-210">No se puede unir a mi MCU</span><span class="sxs-lookup"><span data-stu-id="9c50f-210">Cannot join IM MCU</span></span></p>
<p><span data-ttu-id="9c50f-211">Ver si la MCU de mensajería instantánea se está ejecutando</span><span class="sxs-lookup"><span data-stu-id="9c50f-211">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c50f-212">20022</span><span class="sxs-lookup"><span data-stu-id="9c50f-212">20022</span></span></p></td>
<td><p><span data-ttu-id="9c50f-213">Error</span><span class="sxs-lookup"><span data-stu-id="9c50f-213">Error</span></span></p></td>
<td><p><span data-ttu-id="9c50f-214">No se puede unir a AV MCU</span><span class="sxs-lookup"><span data-stu-id="9c50f-214">Cannot join AV MCU</span></span></p></td>
<td><p><span data-ttu-id="9c50f-215">No se puede unir a AV MCU</span><span class="sxs-lookup"><span data-stu-id="9c50f-215">Cannot join AV MCU</span></span></p>
<p><span data-ttu-id="9c50f-216">Ver si la MCU AV está en funcionamiento</span><span class="sxs-lookup"><span data-stu-id="9c50f-216">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c50f-217">20023</span><span class="sxs-lookup"><span data-stu-id="9c50f-217">20023</span></span></p></td>
<td><p><span data-ttu-id="9c50f-218">Error</span><span class="sxs-lookup"><span data-stu-id="9c50f-218">Error</span></span></p></td>
<td><p><span data-ttu-id="9c50f-219">No se puede unir como MCU</span><span class="sxs-lookup"><span data-stu-id="9c50f-219">Cannot join AS MCU</span></span></p></td>
<td><p><span data-ttu-id="9c50f-220">No se puede unir como MCU</span><span class="sxs-lookup"><span data-stu-id="9c50f-220">Cannot join AS MCU</span></span></p>
<p><span data-ttu-id="9c50f-221">Ver si se está ejecutando la MCU</span><span class="sxs-lookup"><span data-stu-id="9c50f-221">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c50f-222">20024</span><span class="sxs-lookup"><span data-stu-id="9c50f-222">20024</span></span></p></td>
<td><p><span data-ttu-id="9c50f-223">Error</span><span class="sxs-lookup"><span data-stu-id="9c50f-223">Error</span></span></p></td>
<td><p><span data-ttu-id="9c50f-224">No se puede unir datos MCU</span><span class="sxs-lookup"><span data-stu-id="9c50f-224">Cannot join Data MCU</span></span></p></td>
<td><p><span data-ttu-id="9c50f-225">No se puede unir datos MCU</span><span class="sxs-lookup"><span data-stu-id="9c50f-225">Cannot join Data MCU</span></span></p>
<p><span data-ttu-id="9c50f-226">Ver si Data MCU se está ejecutando</span><span class="sxs-lookup"><span data-stu-id="9c50f-226">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c50f-227">20025</span><span class="sxs-lookup"><span data-stu-id="9c50f-227">20025</span></span></p></td>
<td><p><span data-ttu-id="9c50f-228">Error</span><span class="sxs-lookup"><span data-stu-id="9c50f-228">Error</span></span></p></td>
<td><p><span data-ttu-id="9c50f-229">No se puede obtener acceso a Active Directory para fotos</span><span class="sxs-lookup"><span data-stu-id="9c50f-229">Cannot access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="9c50f-230">La conexión a Active Directory no está disponible</span><span class="sxs-lookup"><span data-stu-id="9c50f-230">Connection to active directory is not available</span></span></p>
<p><span data-ttu-id="9c50f-231">Asegurarse de que la conexión a Active Directory está disponible</span><span class="sxs-lookup"><span data-stu-id="9c50f-231">Make sure the connection to active directory is available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c50f-232">20026</span><span class="sxs-lookup"><span data-stu-id="9c50f-232">20026</span></span></p></td>
<td><p><span data-ttu-id="9c50f-233">Informativo</span><span class="sxs-lookup"><span data-stu-id="9c50f-233">Informational</span></span></p></td>
<td><p><span data-ttu-id="9c50f-234">Se recuperó el acceso a Active Directory para la foto</span><span class="sxs-lookup"><span data-stu-id="9c50f-234">Recovered from failing to access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="9c50f-235">N/D</span><span class="sxs-lookup"><span data-stu-id="9c50f-235">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c50f-236">20027</span><span class="sxs-lookup"><span data-stu-id="9c50f-236">20027</span></span></p></td>
<td><p><span data-ttu-id="9c50f-237">Advertencia</span><span class="sxs-lookup"><span data-stu-id="9c50f-237">Warning</span></span></p></td>
<td><p><span data-ttu-id="9c50f-238">No se puede deserializar</span><span class="sxs-lookup"><span data-stu-id="9c50f-238">Cannot deserialize</span></span></p></td>
<td><p><span data-ttu-id="9c50f-239">No se puede deserializar</span><span class="sxs-lookup"><span data-stu-id="9c50f-239">Cannot deserialize</span></span></p>
<p><span data-ttu-id="9c50f-240">Si el problema continúa, póngase en contacto con el soporte técnico</span><span class="sxs-lookup"><span data-stu-id="9c50f-240">If the problem persists contact product support</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

