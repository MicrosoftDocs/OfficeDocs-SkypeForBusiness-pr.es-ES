---
title: 'Lync Server 2013: información general sobre los tipos de direcciones IP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of IP address types for Lync Server
ms:assetid: ee9a695f-5cf5-441e-94fb-6adeca50e8d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205363(v=OCS.15)
ms:contentKeyID: 48185759
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 975aa4a81b4e44cc20fdbfda946f901610a1b484
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153200"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-ip-address-types-for-lync-server-2013"></a><span data-ttu-id="460a1-102">Información general sobre los tipos de direcciones IP para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="460a1-102">Overview of IP address types for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="460a1-103">_**Última modificación del tema:** 2013-01-29_</span><span class="sxs-lookup"><span data-stu-id="460a1-103">_**Topic Last Modified:** 2013-01-29_</span></span>

<span data-ttu-id="460a1-104">Tiene tres opciones para configurar las direcciones IP en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="460a1-104">You have three options when configuring IP addresses in Lync Server 2013.</span></span> <span data-ttu-id="460a1-105">Puede configurar Lync Server 2013 para que admita solo IP versión 4 (IPv4), solo IP versión 6 (IPv6) o una combinación de ambas (conocidas como *pila dual*).</span><span class="sxs-lookup"><span data-stu-id="460a1-105">You can configure Lync Server 2013 to support only IP version 4 (IPv4), only IP version 6 (IPv6), or a combination of both (known as a *dual stack*).</span></span> <span data-ttu-id="460a1-106">Cada tipo de configuración entraña varios aspectos que debe tener en cuenta:</span><span class="sxs-lookup"><span data-stu-id="460a1-106">There are several issues to consider with each type of configuration:</span></span>

  - <span data-ttu-id="460a1-107">**Solo**   se creó IPv6 de IPv4 porque el mundo se está quedando sin direcciones IPv4.</span><span class="sxs-lookup"><span data-stu-id="460a1-107">**IPv4 only**   IPv6 was created because the world is running out of IPv4 addresses.</span></span> <span data-ttu-id="460a1-108">En última instancia, IPv6 será totalmente compatible en todo el mundo, pero en este momento, muchas compañías y dispositivos que su empresa puede que necesiten comunicarse con no son compatibles con IPv6, y es posible que no lo hagan durante algún tiempo.</span><span class="sxs-lookup"><span data-stu-id="460a1-108">Ultimately, IPv6 will be fully supported worldwide, but at this time, many companies and devices that your enterprise might need to communicate with do not yet support IPv6, and may not for some time.</span></span> <span data-ttu-id="460a1-109">Una configuración de solo IPv4 le ayudará a asegurarse de que la implementación de Lync Server se puede comunicar con la mayoría de los dispositivos existentes.</span><span class="sxs-lookup"><span data-stu-id="460a1-109">An IPv4-only configuration will help to ensure that your Lync Server implementation can communicate with most existing devices.</span></span>

  - <span data-ttu-id="460a1-110">**Solo IPv6 por**   el contrario, una implementación completa de IPv6, en este momento, excluirá la comunicación con muchos dispositivos existentes.</span><span class="sxs-lookup"><span data-stu-id="460a1-110">**IPv6 only**   Conversely, a full IPv6 implementation, at this time, will exclude communication with many existing devices.</span></span>

  - <span data-ttu-id="460a1-111">**Stack dual**stack es una red donde están habilitadas las direcciones IPv4 e IPv6.   </span><span class="sxs-lookup"><span data-stu-id="460a1-111">**Dual Stack**   Dual stack is a network where both IPv4 and IPv6 addresses are enabled.</span></span> <span data-ttu-id="460a1-112">Esta configuración se admite en Lync Server 2013 porque, en la mayoría de los casos, la transición de Full-IPv4 a Full-IPv6 tardará varios años.</span><span class="sxs-lookup"><span data-stu-id="460a1-112">This configuration is supported in Lync Server 2013 because in most cases the transition from full-IPv4 to full-IPv6 will take several years.</span></span>

<span data-ttu-id="460a1-113">En las secciones siguientes se resume la compatibilidad entre estas tres configuraciones para varias características de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="460a1-113">The following sections outline the compatibility among these three configurations for various Lync Server features.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="460a1-p104">La configuración de tipo solo IPv6 en el cliente o el servidor solo se admite en entornos de ensayo y con fines de validación, no se admite en implementaciones de producción.</span><span class="sxs-lookup"><span data-stu-id="460a1-p104">Client or server configuration with IPv6 only is supported only for lab or validation purposes. IPv6 only configuration is not supported in the production deployment.</span></span>



</div>

<div>

## <a name="client-registration"></a><span data-ttu-id="460a1-116">Registro de clientes</span><span class="sxs-lookup"><span data-stu-id="460a1-116">Client Registration</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="460a1-117">Red de extremo de clientes</span><span class="sxs-lookup"><span data-stu-id="460a1-117">Client endpoint network</span></span></th>
<th><span data-ttu-id="460a1-118">Red del servidor</span><span class="sxs-lookup"><span data-stu-id="460a1-118">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="460a1-119">IPv4</span><span class="sxs-lookup"><span data-stu-id="460a1-119">IPv4</span></span></p></td>
<td><p><span data-ttu-id="460a1-120">IPv4</span><span class="sxs-lookup"><span data-stu-id="460a1-120">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="460a1-121">IPv4</span><span class="sxs-lookup"><span data-stu-id="460a1-121">IPv4</span></span></p></td>
<td><p><span data-ttu-id="460a1-122">Pila dual</span><span class="sxs-lookup"><span data-stu-id="460a1-122">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="460a1-123">Pila dual</span><span class="sxs-lookup"><span data-stu-id="460a1-123">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="460a1-124">IPv4</span><span class="sxs-lookup"><span data-stu-id="460a1-124">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="460a1-125">Pila dual</span><span class="sxs-lookup"><span data-stu-id="460a1-125">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="460a1-126">Pila dual</span><span class="sxs-lookup"><span data-stu-id="460a1-126">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="460a1-127">Pila dual</span><span class="sxs-lookup"><span data-stu-id="460a1-127">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="460a1-128">IPv6</span><span class="sxs-lookup"><span data-stu-id="460a1-128">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="460a1-129">IPv6</span><span class="sxs-lookup"><span data-stu-id="460a1-129">IPv6</span></span></p></td>
<td><p><span data-ttu-id="460a1-130">Pila dual</span><span class="sxs-lookup"><span data-stu-id="460a1-130">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="460a1-131">IPv6</span><span class="sxs-lookup"><span data-stu-id="460a1-131">IPv6</span></span></p></td>
<td><p><span data-ttu-id="460a1-132">IPv6</span><span class="sxs-lookup"><span data-stu-id="460a1-132">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="peer-to-peer-client"></a><span data-ttu-id="460a1-133">Cliente de punto a punto</span><span class="sxs-lookup"><span data-stu-id="460a1-133">Peer-to-Peer Client</span></span>

<span data-ttu-id="460a1-p105">Las comunicaciones de punto a punto incluyen audio, audio y vídeo, uso compartido de aplicaciones y transferencia de archivos. Después de que se hayan registrado con éxito ambos clientes, se admiten las combinaciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="460a1-p105">Peer-to-peer communications include audio, audio/video, application sharing, and file transfer. After both clients have successfully registered, the following combinations are supported.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="460a1-136">Extremo de cliente 1</span><span class="sxs-lookup"><span data-stu-id="460a1-136">Client endpoint 1</span></span></th>
<th><span data-ttu-id="460a1-137">Extremo de cliente 2</span><span class="sxs-lookup"><span data-stu-id="460a1-137">Client endpoint 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="460a1-138">IPv4</span><span class="sxs-lookup"><span data-stu-id="460a1-138">IPv4</span></span></p></td>
<td><p><span data-ttu-id="460a1-139">IPv4</span><span class="sxs-lookup"><span data-stu-id="460a1-139">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="460a1-140">IPv4</span><span class="sxs-lookup"><span data-stu-id="460a1-140">IPv4</span></span></p></td>
<td><p><span data-ttu-id="460a1-141">Pila dual</span><span class="sxs-lookup"><span data-stu-id="460a1-141">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="460a1-142">Pila dual</span><span class="sxs-lookup"><span data-stu-id="460a1-142">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="460a1-143">Pila dual</span><span class="sxs-lookup"><span data-stu-id="460a1-143">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="460a1-144">IPv6</span><span class="sxs-lookup"><span data-stu-id="460a1-144">IPv6</span></span></p></td>
<td><p><span data-ttu-id="460a1-145">Pila dual</span><span class="sxs-lookup"><span data-stu-id="460a1-145">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="460a1-146">IPv6</span><span class="sxs-lookup"><span data-stu-id="460a1-146">IPv6</span></span></p></td>
<td><p><span data-ttu-id="460a1-147">IPv6</span><span class="sxs-lookup"><span data-stu-id="460a1-147">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="conferencing"></a><span data-ttu-id="460a1-148">Conferencia</span><span class="sxs-lookup"><span data-stu-id="460a1-148">Conferencing</span></span>

<span data-ttu-id="460a1-149">Las conferencias incluyen audio y vídeo, uso compartido de aplicaciones y colaboración de datos (pizarra y uso compartido de archivos).</span><span class="sxs-lookup"><span data-stu-id="460a1-149">Conferencing includes audio/video, application sharing, and data collaboration (whiteboarding and file sharing).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="460a1-150">Red de extremo de cliente</span><span class="sxs-lookup"><span data-stu-id="460a1-150">Client endpoint network</span></span></th>
<th><span data-ttu-id="460a1-151">Red del servidor</span><span class="sxs-lookup"><span data-stu-id="460a1-151">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="460a1-152">IPv4</span><span class="sxs-lookup"><span data-stu-id="460a1-152">IPv4</span></span></p></td>
<td><p><span data-ttu-id="460a1-153">IPv4</span><span class="sxs-lookup"><span data-stu-id="460a1-153">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="460a1-154">IPv4</span><span class="sxs-lookup"><span data-stu-id="460a1-154">IPv4</span></span></p></td>
<td><p><span data-ttu-id="460a1-155">Pila dual</span><span class="sxs-lookup"><span data-stu-id="460a1-155">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="460a1-156">Pila dual</span><span class="sxs-lookup"><span data-stu-id="460a1-156">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="460a1-157">IPv4</span><span class="sxs-lookup"><span data-stu-id="460a1-157">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="460a1-158">Pila dual</span><span class="sxs-lookup"><span data-stu-id="460a1-158">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="460a1-159">Pila dual</span><span class="sxs-lookup"><span data-stu-id="460a1-159">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="460a1-160">Pila dual</span><span class="sxs-lookup"><span data-stu-id="460a1-160">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="460a1-161">IPv6</span><span class="sxs-lookup"><span data-stu-id="460a1-161">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="460a1-162">IPv6</span><span class="sxs-lookup"><span data-stu-id="460a1-162">IPv6</span></span></p></td>
<td><p><span data-ttu-id="460a1-163">Pila dual</span><span class="sxs-lookup"><span data-stu-id="460a1-163">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="460a1-164">IPv6</span><span class="sxs-lookup"><span data-stu-id="460a1-164">IPv6</span></span></p></td>
<td><p><span data-ttu-id="460a1-165">IPv6</span><span class="sxs-lookup"><span data-stu-id="460a1-165">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="mediation-serverpstn"></a><span data-ttu-id="460a1-166">Servidor de mediación/RTC</span><span class="sxs-lookup"><span data-stu-id="460a1-166">Mediation Server/PSTN</span></span>

<span data-ttu-id="460a1-167">Lync Server 2013 no admite el desvío de medios para llamadas de red telefónica conmutada (RTC) si el tráfico se realiza a través de una interfaz IPv6.</span><span class="sxs-lookup"><span data-stu-id="460a1-167">Lync Server 2013 does not support media bypass for public switched telephone network (PSTN) calls if the traffic is through an IPv6 interface.</span></span> <span data-ttu-id="460a1-168">Si se requiere la omisión de medios, se recomienda que la puerta de enlace RTC se configure con IPv4.</span><span class="sxs-lookup"><span data-stu-id="460a1-168">If media bypass is required, we recommend that the PSTN gateway is configured to IPv4.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="460a1-169">Interfaz principal\*</span><span class="sxs-lookup"><span data-stu-id="460a1-169">Primary interface\*</span></span></th>
<th><span data-ttu-id="460a1-170">Interfaz RTC (en el servidor de mediación)</span><span class="sxs-lookup"><span data-stu-id="460a1-170">PSTN interface (on Mediation Server)</span></span></th>
<th><span data-ttu-id="460a1-171">Configuración de la puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="460a1-171">PSTN gateway setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="460a1-172">IPv4</span><span class="sxs-lookup"><span data-stu-id="460a1-172">IPv4</span></span></p></td>
<td><p><span data-ttu-id="460a1-173">Pila dual</span><span class="sxs-lookup"><span data-stu-id="460a1-173">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="460a1-174">IPv4</span><span class="sxs-lookup"><span data-stu-id="460a1-174">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="460a1-175">Pila dual</span><span class="sxs-lookup"><span data-stu-id="460a1-175">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="460a1-176">Pila dual</span><span class="sxs-lookup"><span data-stu-id="460a1-176">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="460a1-177">IPv4</span><span class="sxs-lookup"><span data-stu-id="460a1-177">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="460a1-178">Pila dual</span><span class="sxs-lookup"><span data-stu-id="460a1-178">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="460a1-179">Pila dual</span><span class="sxs-lookup"><span data-stu-id="460a1-179">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="460a1-180">IPv6</span><span class="sxs-lookup"><span data-stu-id="460a1-180">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="460a1-181">\*La interfaz principal es la interfaz que se comunica con los componentes de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="460a1-181">\* The primary interface is the interface that communicates with the Lync Server components.</span></span>

</div>

<div>

## <a name="remote-user-peer-to-peer-communications"></a><span data-ttu-id="460a1-182">Comunicaciones de punto a punto de usuarios remotos</span><span class="sxs-lookup"><span data-stu-id="460a1-182">Remote User Peer-to-Peer Communications</span></span>

<span data-ttu-id="460a1-183">Las comunicaciones de punto a punto con usuarios remotos incluyen mensajería instantánea, audio y vídeo, uso compartido de aplicaciones y transferencia de archivos.</span><span class="sxs-lookup"><span data-stu-id="460a1-183">Peer-to-peer communications with remote users include instant messaging, audio/video, application sharing, and file transfer.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="460a1-184">Red de usuarios remotos</span><span class="sxs-lookup"><span data-stu-id="460a1-184">Remote user network</span></span></th>
<th><span data-ttu-id="460a1-185">Servidor perimetral (perímetro externo)</span><span class="sxs-lookup"><span data-stu-id="460a1-185">Edge server (External edge)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="460a1-186">IPv4</span><span class="sxs-lookup"><span data-stu-id="460a1-186">IPv4</span></span></p></td>
<td><p><span data-ttu-id="460a1-187">IPv4</span><span class="sxs-lookup"><span data-stu-id="460a1-187">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="460a1-188">Pila dual</span><span class="sxs-lookup"><span data-stu-id="460a1-188">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="460a1-189">IPv4</span><span class="sxs-lookup"><span data-stu-id="460a1-189">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="460a1-190">Pila dual</span><span class="sxs-lookup"><span data-stu-id="460a1-190">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="460a1-191">Pila dual</span><span class="sxs-lookup"><span data-stu-id="460a1-191">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="460a1-192">IPv6</span><span class="sxs-lookup"><span data-stu-id="460a1-192">IPv6</span></span></p></td>
<td><p><span data-ttu-id="460a1-193">Pila dual</span><span class="sxs-lookup"><span data-stu-id="460a1-193">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="460a1-194">IPv6</span><span class="sxs-lookup"><span data-stu-id="460a1-194">IPv6</span></span></p></td>
<td><p><span data-ttu-id="460a1-195">IPv6</span><span class="sxs-lookup"><span data-stu-id="460a1-195">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-pool-and-edge-pool-configuration"></a><span data-ttu-id="460a1-196">Configuración del grupo de servidores front-end y del grupo de servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="460a1-196">Front End Pool and Edge Pool Configuration</span></span>

<span data-ttu-id="460a1-197">En la siguiente tabla se muestra la matriz de compatibilidad entre el grupo de servidores front-end y el grupo de servidores perimetrales internos.</span><span class="sxs-lookup"><span data-stu-id="460a1-197">The following table shows the support matrix between the Front End Server pool and the internal Edge Server pool.</span></span>

### <a name="front-end-pool-and-edge-pool-internal-edge-matrix"></a><span data-ttu-id="460a1-198">Matriz del grupo de servidores front-end y del grupo de servidores perimetrales (perímetro interno)</span><span class="sxs-lookup"><span data-stu-id="460a1-198">Front End Pool and Edge Pool (Internal Edge) Matrix</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="460a1-199"><strong>Grupo de servidores perimetrales: IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="460a1-199"><strong>Edge Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="460a1-200"><strong>Grupo de servidores perimetrales: pila dual</strong></span><span class="sxs-lookup"><span data-stu-id="460a1-200"><strong>Edge Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="460a1-201"><strong>Grupo de servidores perimetrales: IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="460a1-201"><strong>Edge Pool: IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="460a1-202"><strong>Grupo de servidores front-end: IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="460a1-202"><strong>Front End Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="460a1-203">Sí</span><span class="sxs-lookup"><span data-stu-id="460a1-203">Yes</span></span></p></td>
<td><p><span data-ttu-id="460a1-204">Sí</span><span class="sxs-lookup"><span data-stu-id="460a1-204">Yes</span></span></p></td>
<td><p><span data-ttu-id="460a1-205">No</span><span class="sxs-lookup"><span data-stu-id="460a1-205">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="460a1-206"><strong>Grupo de servidores front-end: pila dual</strong></span><span class="sxs-lookup"><span data-stu-id="460a1-206"><strong>Front End Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="460a1-207">Sí</span><span class="sxs-lookup"><span data-stu-id="460a1-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="460a1-208">Sí</span><span class="sxs-lookup"><span data-stu-id="460a1-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="460a1-209">No</span><span class="sxs-lookup"><span data-stu-id="460a1-209">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="460a1-210"><strong>Grupo de servidores front-end: IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="460a1-210"><strong>Front End Pool: IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="460a1-211">No</span><span class="sxs-lookup"><span data-stu-id="460a1-211">No</span></span></p></td>
<td><p><span data-ttu-id="460a1-212">No</span><span class="sxs-lookup"><span data-stu-id="460a1-212">No</span></span></p></td>
<td><p><span data-ttu-id="460a1-213">Sí\*</span><span class="sxs-lookup"><span data-stu-id="460a1-213">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="460a1-214">\*Use esta combinación únicamente en un entorno de laboratorio.</span><span class="sxs-lookup"><span data-stu-id="460a1-214">\* Use this combination only in a lab environment.</span></span>

<span data-ttu-id="460a1-215">La tabla siguiente es una matriz de combinaciones admitidas de las interfaces perimetrales interna y externa.</span><span class="sxs-lookup"><span data-stu-id="460a1-215">The following table is a matrix of the supported combinations of internal and external edge interfaces.</span></span>

### <a name="edge-pool-internal-edge-and-edge-pool-external-edge-matrix"></a><span data-ttu-id="460a1-216">Matriz del grupo de servidores perimetrales (perímetro interno) y del grupo de servidores perimetrales (perímetro externo)</span><span class="sxs-lookup"><span data-stu-id="460a1-216">Edge Pool (Internal Edge) and Edge pool (External Edge) Matrix</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="460a1-217"><strong>Grupo de servidores perimetrales (perímetro externo): IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="460a1-217"><strong>Edge Pool (External Edge) : IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="460a1-218"><strong>Grupo de servidores perimetrales (perímetro externo): pila dual</strong></span><span class="sxs-lookup"><span data-stu-id="460a1-218"><strong>Edge Pool (External Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="460a1-219"><strong>Grupo de servidores perimetrales (perímetro externo): IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="460a1-219"><strong>Edge Pool (External Edge): IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="460a1-220"><strong>Grupo de servidores perimetrales (perímetro interno): IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="460a1-220"><strong>Edge Pool (Internal Edge): IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="460a1-221">Sí</span><span class="sxs-lookup"><span data-stu-id="460a1-221">Yes</span></span></p></td>
<td><p><span data-ttu-id="460a1-222">Sí</span><span class="sxs-lookup"><span data-stu-id="460a1-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="460a1-223">No</span><span class="sxs-lookup"><span data-stu-id="460a1-223">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="460a1-224"><strong>Grupo de servidores perimetrales (perímetro interno): pila dual</strong></span><span class="sxs-lookup"><span data-stu-id="460a1-224"><strong>Edge Pool (Internal Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="460a1-225">No</span><span class="sxs-lookup"><span data-stu-id="460a1-225">No</span></span></p></td>
<td><p><span data-ttu-id="460a1-226">Sí</span><span class="sxs-lookup"><span data-stu-id="460a1-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="460a1-227">No</span><span class="sxs-lookup"><span data-stu-id="460a1-227">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="460a1-228"><strong>Grupo de servidores perimetrales (perímetro interno): IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="460a1-228"><strong>Edge Pool (Internal Edge): IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="460a1-229">No</span><span class="sxs-lookup"><span data-stu-id="460a1-229">No</span></span></p></td>
<td><p><span data-ttu-id="460a1-230">No</span><span class="sxs-lookup"><span data-stu-id="460a1-230">No</span></span></p></td>
<td><p><span data-ttu-id="460a1-231">Sí\*</span><span class="sxs-lookup"><span data-stu-id="460a1-231">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="460a1-232">\*Use esta combinación únicamente en un entorno de laboratorio.</span><span class="sxs-lookup"><span data-stu-id="460a1-232">\* Use this combination only in a lab environment.</span></span>

</div>

<div>

## <a name="advanced-enterprise-voice-support-for-ipv6"></a><span data-ttu-id="460a1-233">Compatibilidad avanzada de Enterprise Voice para IPv6</span><span class="sxs-lookup"><span data-stu-id="460a1-233">Advanced Enterprise Voice Support for IPv6</span></span>

<span data-ttu-id="460a1-234">Las implementaciones que incluyen el control de admisión de llamadas (CAC), Enhanced 9-1-1 (E9-1-1) o la omisión de medios se deben configurar como implementaciones de solo IPv4 o de pila dual.</span><span class="sxs-lookup"><span data-stu-id="460a1-234">Deployments that include call admission control (CAC), Enhanced 9-1-1 (E9-1-1), or media bypass must be configured as IPv4 only or as a dual-stacked implementation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="460a1-235">En una implementación de pila dual, incluso si un cliente de Lync se conecta a un Lync Server mediante IPv6, Lync hará un mejor esfuerzo para asignar una dirección IPv4 adecuada para admitir E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="460a1-235">In a dual-stacked deployment, even if a Lync client connects to a Lync Server by using IPv6, Lync will make a best effort to map an appropriate IPv4 address to support E9-1-1.</span></span>



</div>

<span data-ttu-id="460a1-236">No se admite el servicio de información de ubicación con direcciones IPv6.</span><span class="sxs-lookup"><span data-stu-id="460a1-236">Location Information service with IPv6 addresses is not supported.</span></span>

<span data-ttu-id="460a1-p107">La mensajería unificada (MU) de Exchange no admite IPv6. Para la MU de Exchange, asegúrese de que la resolución de DNS no devuelve una dirección IPv6. El uso de IPv6 puede provocar un fallo cuando se envían las llamadas al correo de voz.</span><span class="sxs-lookup"><span data-stu-id="460a1-p107">Exchange Unified Messaging (UM) does not support IPv6. For Exchange UM, be sure that DNS resolution does not return an IPv6 address. Using IPv6 may cause failure when calls are sent to voice mail.</span></span>

</div>

<div>

## <a name="other-lync-server-2013-feature-support-for-ipv6"></a><span data-ttu-id="460a1-240">Otra compatibilidad con características de Lync Server 2013 para IPv6</span><span class="sxs-lookup"><span data-stu-id="460a1-240">Other Lync Server 2013 Feature Support for IPv6</span></span>

<span data-ttu-id="460a1-241">Además de las características y los componentes mencionados anteriormente, Lync Server 2013 admite IPv6 para las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="460a1-241">In addition to the features and components mentioned previously, Lync Server 2013 supports IPv6 for the following features:</span></span>

  - <span data-ttu-id="460a1-242">**Chat persistente**</span><span class="sxs-lookup"><span data-stu-id="460a1-242">**Persistent Chat**</span></span>
    
    <span data-ttu-id="460a1-243">Configure IPv6 para chat persistente mediante el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="460a1-243">You configure IPv6 for Persistent Chat by using Topology Builder.</span></span> <span data-ttu-id="460a1-244">Para obtener más información sobre cómo configurar chat persistente, consulte la documentación de implementación del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="460a1-244">For details about configuring Persistent Chat, see the Deploying Persistent Chat Server documentation.</span></span>

  - <span data-ttu-id="460a1-245">**Informes de Calidad de la experiencia (QoE) y registro de detalles de llamadas (CDR)**</span><span class="sxs-lookup"><span data-stu-id="460a1-245">**Quality of Experience (QoE) and call detail recording (CDR) reports**</span></span>
    
    <span data-ttu-id="460a1-246">Los informes de supervisión incluyen la dirección IP cuando se guarda en la base de datos del servidor de supervisión, tanto del tipo IPv4 como IPv6.</span><span class="sxs-lookup"><span data-stu-id="460a1-246">Monitoring reports include the IP address as it is stored in the Monitoring Server database, whether of type IPv4 or IPv6.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

