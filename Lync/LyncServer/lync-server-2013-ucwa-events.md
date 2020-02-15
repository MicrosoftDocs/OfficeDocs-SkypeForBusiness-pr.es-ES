---
title: 'Lync Server 2013: eventos de UCWA'
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
ms.openlocfilehash: 4d42dbd967f90b6e2a905b92558c88fe52ef62d7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029171"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ucwa-events-in-lync-server-2013"></a><span data-ttu-id="fabdc-102">Eventos de UCWA en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fabdc-102">UCWA events in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fabdc-103">_**Última modificación del tema:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="fabdc-103">_**Topic Last Modified:** 2013-02-15_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="fabdc-104">Lync Server 2013 usa la API Web de comunicaciones unificadas (UCWA) para una serie de propósitos, desde el acceso a Microsoft Exchange para las búsquedas de contactos hasta la actualización de presencia para los clientes móviles.</span><span class="sxs-lookup"><span data-stu-id="fabdc-104">Lync Server 2013 uses the Unified Communications Web API (UCWA) for a number of purposes, from accessing Microsoft Exchange for contact searches to updating presence for mobile clients.</span></span>

<span data-ttu-id="fabdc-105">UCWA escribirá los registros de comportamiento operativo como tipos de evento informativos, de advertencia y de error.</span><span class="sxs-lookup"><span data-stu-id="fabdc-105">UCWA will write records of operational behavior as event types Informational, Warning, and Error.</span></span> <span data-ttu-id="fabdc-106">En la tabla siguiente se describen los eventos que pueden escribir los componentes de UCWA.</span><span class="sxs-lookup"><span data-stu-id="fabdc-106">The following table describes the events that can be written by the UCWA components.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fabdc-107">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="fabdc-107">Event ID</span></span></th>
<th><span data-ttu-id="fabdc-108">Tipo de evento</span><span class="sxs-lookup"><span data-stu-id="fabdc-108">Event Type</span></span></th>
<th><span data-ttu-id="fabdc-109">Resumen</span><span class="sxs-lookup"><span data-stu-id="fabdc-109">Summary</span></span></th>
<th><span data-ttu-id="fabdc-110">Causa y solución</span><span class="sxs-lookup"><span data-stu-id="fabdc-110">Cause and Resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fabdc-111">20001</span><span class="sxs-lookup"><span data-stu-id="fabdc-111">20001</span></span></p></td>
<td><p><span data-ttu-id="fabdc-112">Informativo</span><span class="sxs-lookup"><span data-stu-id="fabdc-112">Informational</span></span></p></td>
<td><p><span data-ttu-id="fabdc-113">UCWA inicializado</span><span class="sxs-lookup"><span data-stu-id="fabdc-113">UCWA initialized</span></span></p></td>
<td><p><span data-ttu-id="fabdc-114">N/D</span><span class="sxs-lookup"><span data-stu-id="fabdc-114">N/A</span></span></p>
<p><span data-ttu-id="fabdc-115">N/D</span><span class="sxs-lookup"><span data-stu-id="fabdc-115">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fabdc-116">20002</span><span class="sxs-lookup"><span data-stu-id="fabdc-116">20002</span></span></p></td>
<td><p><span data-ttu-id="fabdc-117">Error</span><span class="sxs-lookup"><span data-stu-id="fabdc-117">Error</span></span></p></td>
<td><p><span data-ttu-id="fabdc-118">UCWA encontró una excepción inesperada durante la inicialización</span><span class="sxs-lookup"><span data-stu-id="fabdc-118">UCWA encountered an unexpected exception during initialization</span></span></p></td>
<td><p><span data-ttu-id="fabdc-119">Se ha producido un error inesperado durante la inicialización</span><span class="sxs-lookup"><span data-stu-id="fabdc-119">An unexpected error has occurred during initialization</span></span></p>
<p><span data-ttu-id="fabdc-120">Examine los detalles de la excepción en la entrada del registro de eventos asociada para determinar la causa posible</span><span class="sxs-lookup"><span data-stu-id="fabdc-120">Examine the exception details in the associated event log entry to determine the possible cause</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fabdc-121">20003</span><span class="sxs-lookup"><span data-stu-id="fabdc-121">20003</span></span></p></td>
<td><p><span data-ttu-id="fabdc-122">Error</span><span class="sxs-lookup"><span data-stu-id="fabdc-122">Error</span></span></p></td>
<td><p><span data-ttu-id="fabdc-123">UCWA encontró una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="fabdc-123">UCWA encountered an unhandled exception</span></span></p></td>
<td><p><span data-ttu-id="fabdc-124">Se ha producido una excepción no controlada</span><span class="sxs-lookup"><span data-stu-id="fabdc-124">An unhandled exception happened</span></span></p>
<p><span data-ttu-id="fabdc-125">Reinicie el servidor.</span><span class="sxs-lookup"><span data-stu-id="fabdc-125">Restart the server.</span></span> <span data-ttu-id="fabdc-126">Si el problema continúa, póngase en contacto con el soporte técnico</span><span class="sxs-lookup"><span data-stu-id="fabdc-126">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fabdc-127">20004</span><span class="sxs-lookup"><span data-stu-id="fabdc-127">20004</span></span></p></td>
<td><p><span data-ttu-id="fabdc-128">Error</span><span class="sxs-lookup"><span data-stu-id="fabdc-128">Error</span></span></p></td>
<td><p><span data-ttu-id="fabdc-129">No se puede tener acceso a Exchange para fotos HD</span><span class="sxs-lookup"><span data-stu-id="fabdc-129">Cannot access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="fabdc-130">La conexión con Exchange no está disponible</span><span class="sxs-lookup"><span data-stu-id="fabdc-130">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="fabdc-131">Asegurarse de que la conexión a Exchange está disponible</span><span class="sxs-lookup"><span data-stu-id="fabdc-131">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fabdc-132">20005</span><span class="sxs-lookup"><span data-stu-id="fabdc-132">20005</span></span></p></td>
<td><p><span data-ttu-id="fabdc-133">Informativo</span><span class="sxs-lookup"><span data-stu-id="fabdc-133">Informational</span></span></p></td>
<td><p><span data-ttu-id="fabdc-134">Se recuperó el acceso a Exchange para fotos HD</span><span class="sxs-lookup"><span data-stu-id="fabdc-134">Recovered from failing to access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="fabdc-135">N/D</span><span class="sxs-lookup"><span data-stu-id="fabdc-135">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fabdc-136">20006</span><span class="sxs-lookup"><span data-stu-id="fabdc-136">20006</span></span></p></td>
<td><p><span data-ttu-id="fabdc-137">Error</span><span class="sxs-lookup"><span data-stu-id="fabdc-137">Error</span></span></p></td>
<td><p><span data-ttu-id="fabdc-138">No se puede obtener acceso a Exchange para la búsqueda de contactos</span><span class="sxs-lookup"><span data-stu-id="fabdc-138">Cannot access Exchange for contact search</span></span></p></td>
<td><p><span data-ttu-id="fabdc-139">La conexión con Exchange no está disponible</span><span class="sxs-lookup"><span data-stu-id="fabdc-139">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="fabdc-140">Asegurarse de que la conexión a Exchange está disponible</span><span class="sxs-lookup"><span data-stu-id="fabdc-140">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fabdc-141">20007</span><span class="sxs-lookup"><span data-stu-id="fabdc-141">20007</span></span></p></td>
<td><p><span data-ttu-id="fabdc-142">Informativo</span><span class="sxs-lookup"><span data-stu-id="fabdc-142">Informational</span></span></p></td>
<td><p><span data-ttu-id="fabdc-143">Se recuperó del error de búsqueda en el contacto de Exchange</span><span class="sxs-lookup"><span data-stu-id="fabdc-143">Recovered from failing to search contact in Exchange</span></span></p></td>
<td><p><span data-ttu-id="fabdc-144">N/D</span><span class="sxs-lookup"><span data-stu-id="fabdc-144">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fabdc-145">20008</span><span class="sxs-lookup"><span data-stu-id="fabdc-145">20008</span></span></p></td>
<td><p><span data-ttu-id="fabdc-146">Advertencia</span><span class="sxs-lookup"><span data-stu-id="fabdc-146">Warning</span></span></p></td>
<td><p><span data-ttu-id="fabdc-147">Intento de suscribir más de las suscripciones de presencia permitidas por aplicación</span><span class="sxs-lookup"><span data-stu-id="fabdc-147">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p></td>
<td><p><span data-ttu-id="fabdc-148">Intento de suscribir más de las suscripciones de presencia permitidas por aplicación</span><span class="sxs-lookup"><span data-stu-id="fabdc-148">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p>
<p><span data-ttu-id="fabdc-149">Comprobar si los clientes tienen suscripciones innecesarias</span><span class="sxs-lookup"><span data-stu-id="fabdc-149">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fabdc-150">20009</span><span class="sxs-lookup"><span data-stu-id="fabdc-150">20009</span></span></p></td>
<td><p><span data-ttu-id="fabdc-151">Advertencia</span><span class="sxs-lookup"><span data-stu-id="fabdc-151">Warning</span></span></p></td>
<td><p><span data-ttu-id="fabdc-152">Intento de suscribir más de las suscripciones de presencia permitidas por lote</span><span class="sxs-lookup"><span data-stu-id="fabdc-152">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p></td>
<td><p><span data-ttu-id="fabdc-153">Intento de suscribir más de las suscripciones de presencia permitidas por lote</span><span class="sxs-lookup"><span data-stu-id="fabdc-153">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p>
<p><span data-ttu-id="fabdc-154">Comprobar si los clientes tienen suscripciones innecesarias</span><span class="sxs-lookup"><span data-stu-id="fabdc-154">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fabdc-155">20010</span><span class="sxs-lookup"><span data-stu-id="fabdc-155">20010</span></span></p></td>
<td><p><span data-ttu-id="fabdc-156">Error</span><span class="sxs-lookup"><span data-stu-id="fabdc-156">Error</span></span></p></td>
<td><p><span data-ttu-id="fabdc-157">No se pueden recuperar los datos en banda</span><span class="sxs-lookup"><span data-stu-id="fabdc-157">Cannot retrieve inband data</span></span></p></td>
<td><p><span data-ttu-id="fabdc-158">No se pueden recuperar los datos en banda</span><span class="sxs-lookup"><span data-stu-id="fabdc-158">Cannot retrieve inband data</span></span></p>
<p><span data-ttu-id="fabdc-159">Si el problema continúa, póngase en contacto con el soporte técnico</span><span class="sxs-lookup"><span data-stu-id="fabdc-159">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fabdc-160">20011</span><span class="sxs-lookup"><span data-stu-id="fabdc-160">20011</span></span></p></td>
<td><p><span data-ttu-id="fabdc-161">Error</span><span class="sxs-lookup"><span data-stu-id="fabdc-161">Error</span></span></p></td>
<td><p><span data-ttu-id="fabdc-162">No se puede suscribir la presencia</span><span class="sxs-lookup"><span data-stu-id="fabdc-162">Cannot subscribe presence</span></span></p></td>
<td><p><span data-ttu-id="fabdc-163">No se puede suscribir la presencia</span><span class="sxs-lookup"><span data-stu-id="fabdc-163">Cannot subscribe presence</span></span></p>
<p><span data-ttu-id="fabdc-164">Si el problema continúa, póngase en contacto con el soporte técnico</span><span class="sxs-lookup"><span data-stu-id="fabdc-164">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fabdc-165">20012</span><span class="sxs-lookup"><span data-stu-id="fabdc-165">20012</span></span></p></td>
<td><p><span data-ttu-id="fabdc-166">Error</span><span class="sxs-lookup"><span data-stu-id="fabdc-166">Error</span></span></p></td>
<td><p><span data-ttu-id="fabdc-167">No se pudo registrar el extremo</span><span class="sxs-lookup"><span data-stu-id="fabdc-167">Failed to register endpoint</span></span></p></td>
<td><p><span data-ttu-id="fabdc-168">No se pudo registrar el extremo</span><span class="sxs-lookup"><span data-stu-id="fabdc-168">Failed to register endpoint</span></span></p>
<p><span data-ttu-id="fabdc-169">Si el problema continúa, póngase en contacto con el soporte técnico</span><span class="sxs-lookup"><span data-stu-id="fabdc-169">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fabdc-170">20013</span><span class="sxs-lookup"><span data-stu-id="fabdc-170">20013</span></span></p></td>
<td><p><span data-ttu-id="fabdc-171">Error</span><span class="sxs-lookup"><span data-stu-id="fabdc-171">Error</span></span></p></td>
<td><p><span data-ttu-id="fabdc-172">La MCU de mensajería instantánea no está disponible</span><span class="sxs-lookup"><span data-stu-id="fabdc-172">IM MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="fabdc-173">La MCU de mensajería instantánea no está disponible</span><span class="sxs-lookup"><span data-stu-id="fabdc-173">IM MCU is unavailable</span></span></p>
<p><span data-ttu-id="fabdc-174">Ver si la MCU de mensajería instantánea se está ejecutando</span><span class="sxs-lookup"><span data-stu-id="fabdc-174">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fabdc-175">20014</span><span class="sxs-lookup"><span data-stu-id="fabdc-175">20014</span></span></p></td>
<td><p><span data-ttu-id="fabdc-176">Informativo</span><span class="sxs-lookup"><span data-stu-id="fabdc-176">Informational</span></span></p></td>
<td><p><span data-ttu-id="fabdc-177">Se recuperó el error de conexión a la MCU de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="fabdc-177">Recovered from failing to connect to IM MCU</span></span></p></td>
<td><p><span data-ttu-id="fabdc-178">N/D</span><span class="sxs-lookup"><span data-stu-id="fabdc-178">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fabdc-179">20015</span><span class="sxs-lookup"><span data-stu-id="fabdc-179">20015</span></span></p></td>
<td><p><span data-ttu-id="fabdc-180">Error</span><span class="sxs-lookup"><span data-stu-id="fabdc-180">Error</span></span></p></td>
<td><p><span data-ttu-id="fabdc-181">La MCU antivirus no está disponible</span><span class="sxs-lookup"><span data-stu-id="fabdc-181">AV MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="fabdc-182">La MCU antivirus no está disponible</span><span class="sxs-lookup"><span data-stu-id="fabdc-182">AV MCU is unavailable</span></span></p>
<p><span data-ttu-id="fabdc-183">Ver si la MCU AV está en funcionamiento</span><span class="sxs-lookup"><span data-stu-id="fabdc-183">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fabdc-184">20016</span><span class="sxs-lookup"><span data-stu-id="fabdc-184">20016</span></span></p></td>
<td><p><span data-ttu-id="fabdc-185">Informativo</span><span class="sxs-lookup"><span data-stu-id="fabdc-185">Informational</span></span></p></td>
<td><p><span data-ttu-id="fabdc-186">Se recuperó la conexión a un MCU AV</span><span class="sxs-lookup"><span data-stu-id="fabdc-186">Recovered from failing to connect to AV MCU</span></span></p></td>
<td><p><span data-ttu-id="fabdc-187">N/D</span><span class="sxs-lookup"><span data-stu-id="fabdc-187">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fabdc-188">20017</span><span class="sxs-lookup"><span data-stu-id="fabdc-188">20017</span></span></p></td>
<td><p><span data-ttu-id="fabdc-189">Error</span><span class="sxs-lookup"><span data-stu-id="fabdc-189">Error</span></span></p></td>
<td><p><span data-ttu-id="fabdc-190">COMO la MCU no está disponible</span><span class="sxs-lookup"><span data-stu-id="fabdc-190">AS MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="fabdc-191">COMO la MCU no está disponible</span><span class="sxs-lookup"><span data-stu-id="fabdc-191">AS MCU is unavailable</span></span></p>
<p><span data-ttu-id="fabdc-192">Ver si se está ejecutando la MCU</span><span class="sxs-lookup"><span data-stu-id="fabdc-192">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fabdc-193">20018</span><span class="sxs-lookup"><span data-stu-id="fabdc-193">20018</span></span></p></td>
<td><p><span data-ttu-id="fabdc-194">Informativo</span><span class="sxs-lookup"><span data-stu-id="fabdc-194">Informational</span></span></p></td>
<td><p><span data-ttu-id="fabdc-195">Se recuperó el error de conexión a como MCU</span><span class="sxs-lookup"><span data-stu-id="fabdc-195">Recovered from failing to connect to AS MCU</span></span></p></td>
<td><p><span data-ttu-id="fabdc-196">N/D</span><span class="sxs-lookup"><span data-stu-id="fabdc-196">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fabdc-197">20019</span><span class="sxs-lookup"><span data-stu-id="fabdc-197">20019</span></span></p></td>
<td><p><span data-ttu-id="fabdc-198">Error</span><span class="sxs-lookup"><span data-stu-id="fabdc-198">Error</span></span></p></td>
<td><p><span data-ttu-id="fabdc-199">La MCU de datos no está disponible</span><span class="sxs-lookup"><span data-stu-id="fabdc-199">Data MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="fabdc-200">La MCU de datos no está disponible</span><span class="sxs-lookup"><span data-stu-id="fabdc-200">Data MCU is unavailable</span></span></p>
<p><span data-ttu-id="fabdc-201">Ver si Data MCU se está ejecutando</span><span class="sxs-lookup"><span data-stu-id="fabdc-201">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fabdc-202">20020</span><span class="sxs-lookup"><span data-stu-id="fabdc-202">20020</span></span></p></td>
<td><p><span data-ttu-id="fabdc-203">Informativo</span><span class="sxs-lookup"><span data-stu-id="fabdc-203">Informational</span></span></p></td>
<td><p><span data-ttu-id="fabdc-204">Se recuperó el error de conexión a la MCU de datos</span><span class="sxs-lookup"><span data-stu-id="fabdc-204">Recovered from failing to connect to Data MCU</span></span></p></td>
<td><p><span data-ttu-id="fabdc-205">N/D</span><span class="sxs-lookup"><span data-stu-id="fabdc-205">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fabdc-206">20021</span><span class="sxs-lookup"><span data-stu-id="fabdc-206">20021</span></span></p></td>
<td><p><span data-ttu-id="fabdc-207">Error</span><span class="sxs-lookup"><span data-stu-id="fabdc-207">Error</span></span></p></td>
<td><p><span data-ttu-id="fabdc-208">No se puede unir a mi MCU</span><span class="sxs-lookup"><span data-stu-id="fabdc-208">Cannot join IM MCU</span></span></p></td>
<td><p><span data-ttu-id="fabdc-209">No se puede unir a mi MCU</span><span class="sxs-lookup"><span data-stu-id="fabdc-209">Cannot join IM MCU</span></span></p>
<p><span data-ttu-id="fabdc-210">Ver si la MCU de mensajería instantánea se está ejecutando</span><span class="sxs-lookup"><span data-stu-id="fabdc-210">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fabdc-211">20022</span><span class="sxs-lookup"><span data-stu-id="fabdc-211">20022</span></span></p></td>
<td><p><span data-ttu-id="fabdc-212">Error</span><span class="sxs-lookup"><span data-stu-id="fabdc-212">Error</span></span></p></td>
<td><p><span data-ttu-id="fabdc-213">No se puede unir a AV MCU</span><span class="sxs-lookup"><span data-stu-id="fabdc-213">Cannot join AV MCU</span></span></p></td>
<td><p><span data-ttu-id="fabdc-214">No se puede unir a AV MCU</span><span class="sxs-lookup"><span data-stu-id="fabdc-214">Cannot join AV MCU</span></span></p>
<p><span data-ttu-id="fabdc-215">Ver si la MCU AV está en funcionamiento</span><span class="sxs-lookup"><span data-stu-id="fabdc-215">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fabdc-216">20023</span><span class="sxs-lookup"><span data-stu-id="fabdc-216">20023</span></span></p></td>
<td><p><span data-ttu-id="fabdc-217">Error</span><span class="sxs-lookup"><span data-stu-id="fabdc-217">Error</span></span></p></td>
<td><p><span data-ttu-id="fabdc-218">No se puede unir como MCU</span><span class="sxs-lookup"><span data-stu-id="fabdc-218">Cannot join AS MCU</span></span></p></td>
<td><p><span data-ttu-id="fabdc-219">No se puede unir como MCU</span><span class="sxs-lookup"><span data-stu-id="fabdc-219">Cannot join AS MCU</span></span></p>
<p><span data-ttu-id="fabdc-220">Ver si se está ejecutando la MCU</span><span class="sxs-lookup"><span data-stu-id="fabdc-220">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fabdc-221">20024</span><span class="sxs-lookup"><span data-stu-id="fabdc-221">20024</span></span></p></td>
<td><p><span data-ttu-id="fabdc-222">Error</span><span class="sxs-lookup"><span data-stu-id="fabdc-222">Error</span></span></p></td>
<td><p><span data-ttu-id="fabdc-223">No se puede unir datos MCU</span><span class="sxs-lookup"><span data-stu-id="fabdc-223">Cannot join Data MCU</span></span></p></td>
<td><p><span data-ttu-id="fabdc-224">No se puede unir datos MCU</span><span class="sxs-lookup"><span data-stu-id="fabdc-224">Cannot join Data MCU</span></span></p>
<p><span data-ttu-id="fabdc-225">Ver si Data MCU se está ejecutando</span><span class="sxs-lookup"><span data-stu-id="fabdc-225">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fabdc-226">20025</span><span class="sxs-lookup"><span data-stu-id="fabdc-226">20025</span></span></p></td>
<td><p><span data-ttu-id="fabdc-227">Error</span><span class="sxs-lookup"><span data-stu-id="fabdc-227">Error</span></span></p></td>
<td><p><span data-ttu-id="fabdc-228">No se puede obtener acceso a Active Directory para fotos</span><span class="sxs-lookup"><span data-stu-id="fabdc-228">Cannot access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="fabdc-229">La conexión a Active Directory no está disponible</span><span class="sxs-lookup"><span data-stu-id="fabdc-229">Connection to active directory is not available</span></span></p>
<p><span data-ttu-id="fabdc-230">Asegurarse de que la conexión a Active Directory está disponible</span><span class="sxs-lookup"><span data-stu-id="fabdc-230">Make sure the connection to active directory is available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fabdc-231">20026</span><span class="sxs-lookup"><span data-stu-id="fabdc-231">20026</span></span></p></td>
<td><p><span data-ttu-id="fabdc-232">Informativo</span><span class="sxs-lookup"><span data-stu-id="fabdc-232">Informational</span></span></p></td>
<td><p><span data-ttu-id="fabdc-233">Se recuperó el acceso a Active Directory para la foto</span><span class="sxs-lookup"><span data-stu-id="fabdc-233">Recovered from failing to access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="fabdc-234">N/D</span><span class="sxs-lookup"><span data-stu-id="fabdc-234">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fabdc-235">20027</span><span class="sxs-lookup"><span data-stu-id="fabdc-235">20027</span></span></p></td>
<td><p><span data-ttu-id="fabdc-236">Advertencia</span><span class="sxs-lookup"><span data-stu-id="fabdc-236">Warning</span></span></p></td>
<td><p><span data-ttu-id="fabdc-237">No se puede deserializar</span><span class="sxs-lookup"><span data-stu-id="fabdc-237">Cannot deserialize</span></span></p></td>
<td><p><span data-ttu-id="fabdc-238">No se puede deserializar</span><span class="sxs-lookup"><span data-stu-id="fabdc-238">Cannot deserialize</span></span></p>
<p><span data-ttu-id="fabdc-239">Si el problema continúa, póngase en contacto con el soporte técnico</span><span class="sxs-lookup"><span data-stu-id="fabdc-239">If the problem persists contact product support</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

