---
title: 'Lync Server 2013: eventos de UCWA'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UCWA events
ms:assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945621(v=OCS.15)
ms:contentKeyID: 51541461
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0671b51e5fbd4b5f072676855d9e8f5201b3e04
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850285"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ucwa-events-in-lync-server-2013"></a><span data-ttu-id="043a1-102">Eventos de UCWA en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="043a1-102">UCWA events in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="043a1-103">_**Última modificación del tema:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="043a1-103">_**Topic Last Modified:** 2013-02-15_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="043a1-104">Lync Server 2013 usa la API Web de comunicaciones unificadas (UCWA) para una serie de propósitos, desde el acceso a Microsoft Exchange para las búsquedas de contactos hasta la actualización de presencia para clientes móviles.</span><span class="sxs-lookup"><span data-stu-id="043a1-104">Lync Server 2013 uses the Unified Communications Web API (UCWA) for a number of purposes, from accessing Microsoft Exchange for contact searches to updating presence for mobile clients.</span></span>

<span data-ttu-id="043a1-p101">UCWA escribirá los registros del comportamiento operativo como tipos de evento informativos, de advertencia y de error. En la siguiente tabla se describen los eventos que pueden escribir los componentes de UCWA.</span><span class="sxs-lookup"><span data-stu-id="043a1-p101">UCWA will write records of operational behavior as event types Informational, Warning, and Error. The following table describes the events that can be written by the UCWA components.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="043a1-107">Id. del evento</span><span class="sxs-lookup"><span data-stu-id="043a1-107">Event ID</span></span></th>
<th><span data-ttu-id="043a1-108">Tipo de evento</span><span class="sxs-lookup"><span data-stu-id="043a1-108">Event Type</span></span></th>
<th><span data-ttu-id="043a1-109">Resumen</span><span class="sxs-lookup"><span data-stu-id="043a1-109">Summary</span></span></th>
<th><span data-ttu-id="043a1-110">Causa y solución</span><span class="sxs-lookup"><span data-stu-id="043a1-110">Cause and Resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="043a1-111">20001</span><span class="sxs-lookup"><span data-stu-id="043a1-111">20001</span></span></p></td>
<td><p><span data-ttu-id="043a1-112">Informativo</span><span class="sxs-lookup"><span data-stu-id="043a1-112">Informational</span></span></p></td>
<td><p><span data-ttu-id="043a1-113">Se inicializó UCWA</span><span class="sxs-lookup"><span data-stu-id="043a1-113">UCWA initialized</span></span></p></td>
<td><p><span data-ttu-id="043a1-114">N/D</span><span class="sxs-lookup"><span data-stu-id="043a1-114">N/A</span></span></p>
<p><span data-ttu-id="043a1-115">N/D</span><span class="sxs-lookup"><span data-stu-id="043a1-115">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="043a1-116">20002</span><span class="sxs-lookup"><span data-stu-id="043a1-116">20002</span></span></p></td>
<td><p><span data-ttu-id="043a1-117">Error</span><span class="sxs-lookup"><span data-stu-id="043a1-117">Error</span></span></p></td>
<td><p><span data-ttu-id="043a1-118">UCWA encontró una excepción inesperada durante la inicialización</span><span class="sxs-lookup"><span data-stu-id="043a1-118">UCWA encountered an unexpected exception during initialization</span></span></p></td>
<td><p><span data-ttu-id="043a1-119">Se produjo un error inesperado durante la inicialización</span><span class="sxs-lookup"><span data-stu-id="043a1-119">An unexpected error has occurred during initialization</span></span></p>
<p><span data-ttu-id="043a1-120">Examine los detalles de la excepción en la entrada del registro de eventos asociada para determinar la posible causa</span><span class="sxs-lookup"><span data-stu-id="043a1-120">Examine the exception details in the associated event log entry to determine the possible cause</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="043a1-121">20003</span><span class="sxs-lookup"><span data-stu-id="043a1-121">20003</span></span></p></td>
<td><p><span data-ttu-id="043a1-122">Error</span><span class="sxs-lookup"><span data-stu-id="043a1-122">Error</span></span></p></td>
<td><p><span data-ttu-id="043a1-123">UCWA encontró una excepción no controlada</span><span class="sxs-lookup"><span data-stu-id="043a1-123">UCWA encountered an unhandled exception</span></span></p></td>
<td><p><span data-ttu-id="043a1-124">Se produjo una excepción no controlada</span><span class="sxs-lookup"><span data-stu-id="043a1-124">An unhandled exception happened</span></span></p>
<p><span data-ttu-id="043a1-p102">Reinicie el servidor. Si persiste el problema, póngase en contacto con el soporte técnico</span><span class="sxs-lookup"><span data-stu-id="043a1-p102">Restart the server. If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="043a1-127">20004</span><span class="sxs-lookup"><span data-stu-id="043a1-127">20004</span></span></p></td>
<td><p><span data-ttu-id="043a1-128">Error</span><span class="sxs-lookup"><span data-stu-id="043a1-128">Error</span></span></p></td>
<td><p><span data-ttu-id="043a1-129">No se puede obtener acceso a Exchange para fotos HD</span><span class="sxs-lookup"><span data-stu-id="043a1-129">Cannot access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="043a1-130">La conexión a Exchange no está disponible</span><span class="sxs-lookup"><span data-stu-id="043a1-130">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="043a1-131">Asegúrese de que la conexión a Exchange esté disponible</span><span class="sxs-lookup"><span data-stu-id="043a1-131">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="043a1-132">20005</span><span class="sxs-lookup"><span data-stu-id="043a1-132">20005</span></span></p></td>
<td><p><span data-ttu-id="043a1-133">Informativo</span><span class="sxs-lookup"><span data-stu-id="043a1-133">Informational</span></span></p></td>
<td><p><span data-ttu-id="043a1-134">Se recuperó el acceso a Exchange para fotos HD</span><span class="sxs-lookup"><span data-stu-id="043a1-134">Recovered from failing to access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="043a1-135">N/D</span><span class="sxs-lookup"><span data-stu-id="043a1-135">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="043a1-136">20006</span><span class="sxs-lookup"><span data-stu-id="043a1-136">20006</span></span></p></td>
<td><p><span data-ttu-id="043a1-137">Error</span><span class="sxs-lookup"><span data-stu-id="043a1-137">Error</span></span></p></td>
<td><p><span data-ttu-id="043a1-138">No se puede obtener acceso a Exchange para la búsqueda de contactos</span><span class="sxs-lookup"><span data-stu-id="043a1-138">Cannot access Exchange for contact search</span></span></p></td>
<td><p><span data-ttu-id="043a1-139">La conexión a Exchange no está disponible</span><span class="sxs-lookup"><span data-stu-id="043a1-139">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="043a1-140">Asegúrese de que la conexión a Exchange esté disponible</span><span class="sxs-lookup"><span data-stu-id="043a1-140">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="043a1-141">20007</span><span class="sxs-lookup"><span data-stu-id="043a1-141">20007</span></span></p></td>
<td><p><span data-ttu-id="043a1-142">Informativo</span><span class="sxs-lookup"><span data-stu-id="043a1-142">Informational</span></span></p></td>
<td><p><span data-ttu-id="043a1-143">Se recuperó el acceso a Exchange para la búsqueda de contactos</span><span class="sxs-lookup"><span data-stu-id="043a1-143">Recovered from failing to search contact in Exchange</span></span></p></td>
<td><p><span data-ttu-id="043a1-144">N/D</span><span class="sxs-lookup"><span data-stu-id="043a1-144">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="043a1-145">20008</span><span class="sxs-lookup"><span data-stu-id="043a1-145">20008</span></span></p></td>
<td><p><span data-ttu-id="043a1-146">Advertencia</span><span class="sxs-lookup"><span data-stu-id="043a1-146">Warning</span></span></p></td>
<td><p><span data-ttu-id="043a1-147">Se intentó un número de suscripciones de presencia mayor que el permitido por aplicación</span><span class="sxs-lookup"><span data-stu-id="043a1-147">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p></td>
<td><p><span data-ttu-id="043a1-148">Se intentó un número de suscripciones de presencia mayor que el permitido por aplicación</span><span class="sxs-lookup"><span data-stu-id="043a1-148">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p>
<p><span data-ttu-id="043a1-149">Compruebe los clientes para determinar las suscripciones innecesarias</span><span class="sxs-lookup"><span data-stu-id="043a1-149">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="043a1-150">20009</span><span class="sxs-lookup"><span data-stu-id="043a1-150">20009</span></span></p></td>
<td><p><span data-ttu-id="043a1-151">Advertencia</span><span class="sxs-lookup"><span data-stu-id="043a1-151">Warning</span></span></p></td>
<td><p><span data-ttu-id="043a1-152">Se intentó un número de suscripciones de presencia mayor que el permitido por lote</span><span class="sxs-lookup"><span data-stu-id="043a1-152">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p></td>
<td><p><span data-ttu-id="043a1-153">Se intentó un número de suscripciones de presencia mayor que el permitido por lote</span><span class="sxs-lookup"><span data-stu-id="043a1-153">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p>
<p><span data-ttu-id="043a1-154">Compruebe los clientes para determinar las suscripciones innecesarias</span><span class="sxs-lookup"><span data-stu-id="043a1-154">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="043a1-155">20010</span><span class="sxs-lookup"><span data-stu-id="043a1-155">20010</span></span></p></td>
<td><p><span data-ttu-id="043a1-156">Error</span><span class="sxs-lookup"><span data-stu-id="043a1-156">Error</span></span></p></td>
<td><p><span data-ttu-id="043a1-157">No se pueden recuperar los datos en banda</span><span class="sxs-lookup"><span data-stu-id="043a1-157">Cannot retrieve inband data</span></span></p></td>
<td><p><span data-ttu-id="043a1-158">No se pueden recuperar los datos en banda</span><span class="sxs-lookup"><span data-stu-id="043a1-158">Cannot retrieve inband data</span></span></p>
<p><span data-ttu-id="043a1-159">Si persiste el problema, póngase en contacto con el soporte técnico</span><span class="sxs-lookup"><span data-stu-id="043a1-159">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="043a1-160">20011</span><span class="sxs-lookup"><span data-stu-id="043a1-160">20011</span></span></p></td>
<td><p><span data-ttu-id="043a1-161">Error</span><span class="sxs-lookup"><span data-stu-id="043a1-161">Error</span></span></p></td>
<td><p><span data-ttu-id="043a1-162">No se puede suscribir la presencia</span><span class="sxs-lookup"><span data-stu-id="043a1-162">Cannot subscribe presence</span></span></p></td>
<td><p><span data-ttu-id="043a1-163">No se puede suscribir la presencia</span><span class="sxs-lookup"><span data-stu-id="043a1-163">Cannot subscribe presence</span></span></p>
<p><span data-ttu-id="043a1-164">Si persiste el problema, póngase en contacto con el soporte técnico</span><span class="sxs-lookup"><span data-stu-id="043a1-164">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="043a1-165">20012</span><span class="sxs-lookup"><span data-stu-id="043a1-165">20012</span></span></p></td>
<td><p><span data-ttu-id="043a1-166">Error</span><span class="sxs-lookup"><span data-stu-id="043a1-166">Error</span></span></p></td>
<td><p><span data-ttu-id="043a1-167">Error al registrar el extremo</span><span class="sxs-lookup"><span data-stu-id="043a1-167">Failed to register endpoint</span></span></p></td>
<td><p><span data-ttu-id="043a1-168">Error al registrar el extremo</span><span class="sxs-lookup"><span data-stu-id="043a1-168">Failed to register endpoint</span></span></p>
<p><span data-ttu-id="043a1-169">Si persiste el problema, póngase en contacto con el soporte técnico</span><span class="sxs-lookup"><span data-stu-id="043a1-169">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="043a1-170">20013</span><span class="sxs-lookup"><span data-stu-id="043a1-170">20013</span></span></p></td>
<td><p><span data-ttu-id="043a1-171">Error</span><span class="sxs-lookup"><span data-stu-id="043a1-171">Error</span></span></p></td>
<td><p><span data-ttu-id="043a1-172">La MCU de mensajería instantánea no está disponible</span><span class="sxs-lookup"><span data-stu-id="043a1-172">IM MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="043a1-173">La MCU de mensajería instantánea no está disponible</span><span class="sxs-lookup"><span data-stu-id="043a1-173">IM MCU is unavailable</span></span></p>
<p><span data-ttu-id="043a1-174">Compruebe si la MCU de mensajería instantánea se está ejecutando</span><span class="sxs-lookup"><span data-stu-id="043a1-174">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="043a1-175">20014</span><span class="sxs-lookup"><span data-stu-id="043a1-175">20014</span></span></p></td>
<td><p><span data-ttu-id="043a1-176">Informativo</span><span class="sxs-lookup"><span data-stu-id="043a1-176">Informational</span></span></p></td>
<td><p><span data-ttu-id="043a1-177">Se recuperó la conexión a la MCU de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="043a1-177">Recovered from failing to connect to IM MCU</span></span></p></td>
<td><p><span data-ttu-id="043a1-178">N/D</span><span class="sxs-lookup"><span data-stu-id="043a1-178">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="043a1-179">20015</span><span class="sxs-lookup"><span data-stu-id="043a1-179">20015</span></span></p></td>
<td><p><span data-ttu-id="043a1-180">Error</span><span class="sxs-lookup"><span data-stu-id="043a1-180">Error</span></span></p></td>
<td><p><span data-ttu-id="043a1-181">La MCU de audio y vídeo no está disponible</span><span class="sxs-lookup"><span data-stu-id="043a1-181">AV MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="043a1-182">La MCU de audio y vídeo no está disponible</span><span class="sxs-lookup"><span data-stu-id="043a1-182">AV MCU is unavailable</span></span></p>
<p><span data-ttu-id="043a1-183">Compruebe si la MCU de audio y vídeo se está ejecutando</span><span class="sxs-lookup"><span data-stu-id="043a1-183">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="043a1-184">20016</span><span class="sxs-lookup"><span data-stu-id="043a1-184">20016</span></span></p></td>
<td><p><span data-ttu-id="043a1-185">Informativo</span><span class="sxs-lookup"><span data-stu-id="043a1-185">Informational</span></span></p></td>
<td><p><span data-ttu-id="043a1-186">Se recuperó la conexión a la MCU de audio y vídeo</span><span class="sxs-lookup"><span data-stu-id="043a1-186">Recovered from failing to connect to AV MCU</span></span></p></td>
<td><p><span data-ttu-id="043a1-187">N/D</span><span class="sxs-lookup"><span data-stu-id="043a1-187">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="043a1-188">20017</span><span class="sxs-lookup"><span data-stu-id="043a1-188">20017</span></span></p></td>
<td><p><span data-ttu-id="043a1-189">Error</span><span class="sxs-lookup"><span data-stu-id="043a1-189">Error</span></span></p></td>
<td><p><span data-ttu-id="043a1-190">La MCU de AS no está disponible</span><span class="sxs-lookup"><span data-stu-id="043a1-190">AS MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="043a1-191">La MCU de AS no está disponible</span><span class="sxs-lookup"><span data-stu-id="043a1-191">AS MCU is unavailable</span></span></p>
<p><span data-ttu-id="043a1-192">Compruebe si la MCU de AS se está ejecutando</span><span class="sxs-lookup"><span data-stu-id="043a1-192">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="043a1-193">20018</span><span class="sxs-lookup"><span data-stu-id="043a1-193">20018</span></span></p></td>
<td><p><span data-ttu-id="043a1-194">Informativo</span><span class="sxs-lookup"><span data-stu-id="043a1-194">Informational</span></span></p></td>
<td><p><span data-ttu-id="043a1-195">Se recuperó la conexión a la MCU de AS</span><span class="sxs-lookup"><span data-stu-id="043a1-195">Recovered from failing to connect to AS MCU</span></span></p></td>
<td><p><span data-ttu-id="043a1-196">N/D</span><span class="sxs-lookup"><span data-stu-id="043a1-196">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="043a1-197">20019</span><span class="sxs-lookup"><span data-stu-id="043a1-197">20019</span></span></p></td>
<td><p><span data-ttu-id="043a1-198">Error</span><span class="sxs-lookup"><span data-stu-id="043a1-198">Error</span></span></p></td>
<td><p><span data-ttu-id="043a1-199">La MCU de datos no está disponible</span><span class="sxs-lookup"><span data-stu-id="043a1-199">Data MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="043a1-200">La MCU de datos no está disponible</span><span class="sxs-lookup"><span data-stu-id="043a1-200">Data MCU is unavailable</span></span></p>
<p><span data-ttu-id="043a1-201">Compruebe si la MCU de datos se está ejecutando</span><span class="sxs-lookup"><span data-stu-id="043a1-201">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="043a1-202">20020</span><span class="sxs-lookup"><span data-stu-id="043a1-202">20020</span></span></p></td>
<td><p><span data-ttu-id="043a1-203">Informativo</span><span class="sxs-lookup"><span data-stu-id="043a1-203">Informational</span></span></p></td>
<td><p><span data-ttu-id="043a1-204">Se recuperó la conexión a la MCU de datos</span><span class="sxs-lookup"><span data-stu-id="043a1-204">Recovered from failing to connect to Data MCU</span></span></p></td>
<td><p><span data-ttu-id="043a1-205">N/D</span><span class="sxs-lookup"><span data-stu-id="043a1-205">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="043a1-206">20021</span><span class="sxs-lookup"><span data-stu-id="043a1-206">20021</span></span></p></td>
<td><p><span data-ttu-id="043a1-207">Error</span><span class="sxs-lookup"><span data-stu-id="043a1-207">Error</span></span></p></td>
<td><p><span data-ttu-id="043a1-208">No se puede conectar la MCU de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="043a1-208">Cannot join IM MCU</span></span></p></td>
<td><p><span data-ttu-id="043a1-209">No se puede conectar la MCU de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="043a1-209">Cannot join IM MCU</span></span></p>
<p><span data-ttu-id="043a1-210">Compruebe si la MCU de mensajería instantánea se está ejecutando</span><span class="sxs-lookup"><span data-stu-id="043a1-210">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="043a1-211">20022</span><span class="sxs-lookup"><span data-stu-id="043a1-211">20022</span></span></p></td>
<td><p><span data-ttu-id="043a1-212">Error</span><span class="sxs-lookup"><span data-stu-id="043a1-212">Error</span></span></p></td>
<td><p><span data-ttu-id="043a1-213">No se puede conectar la MCU de audio y vídeo</span><span class="sxs-lookup"><span data-stu-id="043a1-213">Cannot join AV MCU</span></span></p></td>
<td><p><span data-ttu-id="043a1-214">No se puede conectar la MCU de audio y vídeo</span><span class="sxs-lookup"><span data-stu-id="043a1-214">Cannot join AV MCU</span></span></p>
<p><span data-ttu-id="043a1-215">Compruebe si la MCU de audio y vídeo se está ejecutando</span><span class="sxs-lookup"><span data-stu-id="043a1-215">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="043a1-216">20023</span><span class="sxs-lookup"><span data-stu-id="043a1-216">20023</span></span></p></td>
<td><p><span data-ttu-id="043a1-217">Error</span><span class="sxs-lookup"><span data-stu-id="043a1-217">Error</span></span></p></td>
<td><p><span data-ttu-id="043a1-218">No se puede conectar la MCU de AS</span><span class="sxs-lookup"><span data-stu-id="043a1-218">Cannot join AS MCU</span></span></p></td>
<td><p><span data-ttu-id="043a1-219">No se puede conectar la MCU de AS</span><span class="sxs-lookup"><span data-stu-id="043a1-219">Cannot join AS MCU</span></span></p>
<p><span data-ttu-id="043a1-220">Compruebe si la MCU de AS se está ejecutando</span><span class="sxs-lookup"><span data-stu-id="043a1-220">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="043a1-221">20024</span><span class="sxs-lookup"><span data-stu-id="043a1-221">20024</span></span></p></td>
<td><p><span data-ttu-id="043a1-222">Error</span><span class="sxs-lookup"><span data-stu-id="043a1-222">Error</span></span></p></td>
<td><p><span data-ttu-id="043a1-223">No se puede conectar la MCU de datos</span><span class="sxs-lookup"><span data-stu-id="043a1-223">Cannot join Data MCU</span></span></p></td>
<td><p><span data-ttu-id="043a1-224">No se puede conectar la MCU de datos</span><span class="sxs-lookup"><span data-stu-id="043a1-224">Cannot join Data MCU</span></span></p>
<p><span data-ttu-id="043a1-225">Compruebe si la MCU de datos se está ejecutando</span><span class="sxs-lookup"><span data-stu-id="043a1-225">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="043a1-226">20025</span><span class="sxs-lookup"><span data-stu-id="043a1-226">20025</span></span></p></td>
<td><p><span data-ttu-id="043a1-227">Error</span><span class="sxs-lookup"><span data-stu-id="043a1-227">Error</span></span></p></td>
<td><p><span data-ttu-id="043a1-228">No se puede obtener acceso a Active Directory para las fotos</span><span class="sxs-lookup"><span data-stu-id="043a1-228">Cannot access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="043a1-229">La conexión a Active Directory no está disponible</span><span class="sxs-lookup"><span data-stu-id="043a1-229">Connection to active directory is not available</span></span></p>
<p><span data-ttu-id="043a1-230">Asegúrese de que la conexión a Active Directory esté disponible</span><span class="sxs-lookup"><span data-stu-id="043a1-230">Make sure the connection to active directory is available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="043a1-231">20026</span><span class="sxs-lookup"><span data-stu-id="043a1-231">20026</span></span></p></td>
<td><p><span data-ttu-id="043a1-232">Informativo</span><span class="sxs-lookup"><span data-stu-id="043a1-232">Informational</span></span></p></td>
<td><p><span data-ttu-id="043a1-233">Se recuperó el acceso a Active Directory para las fotos</span><span class="sxs-lookup"><span data-stu-id="043a1-233">Recovered from failing to access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="043a1-234">N/D</span><span class="sxs-lookup"><span data-stu-id="043a1-234">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="043a1-235">20027</span><span class="sxs-lookup"><span data-stu-id="043a1-235">20027</span></span></p></td>
<td><p><span data-ttu-id="043a1-236">Advertencia</span><span class="sxs-lookup"><span data-stu-id="043a1-236">Warning</span></span></p></td>
<td><p><span data-ttu-id="043a1-237">No se puede deserializar</span><span class="sxs-lookup"><span data-stu-id="043a1-237">Cannot deserialize</span></span></p></td>
<td><p><span data-ttu-id="043a1-238">No se puede deserializar</span><span class="sxs-lookup"><span data-stu-id="043a1-238">Cannot deserialize</span></span></p>
<p><span data-ttu-id="043a1-239">Si persiste el problema, póngase en contacto con el soporte técnico</span><span class="sxs-lookup"><span data-stu-id="043a1-239">If the problem persists contact product support</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

