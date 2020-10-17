---
title: 'Lync Server 2013: información general sobre los tipos de direcciones IP'
description: 'Lync Server 2013: información general sobre los tipos de direcciones IP.'
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
ms.openlocfilehash: 81492b2e006a6f44f6deb78e6a0560f6e319992f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559226"
---
# <a name="overview-of-ip-address-types-for-lync-server-2013"></a><span data-ttu-id="adc17-103">Información general sobre los tipos de direcciones IP para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="adc17-103">Overview of IP address types for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="adc17-104">_**Última modificación del tema:** 2013-01-29_</span><span class="sxs-lookup"><span data-stu-id="adc17-104">_**Topic Last Modified:** 2013-01-29_</span></span>

<span data-ttu-id="adc17-105">Tiene tres opciones para configurar las direcciones IP en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="adc17-105">You have three options when configuring IP addresses in Lync Server 2013.</span></span> <span data-ttu-id="adc17-106">Puede configurar Lync Server 2013 para que admita solo IP versión 4 (IPv4), solo IP versión 6 (IPv6) o una combinación de ambas (conocidas como *pila dual*).</span><span class="sxs-lookup"><span data-stu-id="adc17-106">You can configure Lync Server 2013 to support only IP version 4 (IPv4), only IP version 6 (IPv6), or a combination of both (known as a *dual stack*).</span></span> <span data-ttu-id="adc17-107">Cada tipo de configuración entraña varios aspectos que debe tener en cuenta:</span><span class="sxs-lookup"><span data-stu-id="adc17-107">There are several issues to consider with each type of configuration:</span></span>

  - <span data-ttu-id="adc17-108">**Solo IPv4**     IPv6 se creó porque el mundo se está quedando sin direcciones IPv4.</span><span class="sxs-lookup"><span data-stu-id="adc17-108">**IPv4 only**   IPv6 was created because the world is running out of IPv4 addresses.</span></span> <span data-ttu-id="adc17-109">En última instancia, IPv6 será totalmente compatible en todo el mundo, pero en este momento, muchas compañías y dispositivos que su empresa puede que necesiten comunicarse con no son compatibles con IPv6, y es posible que no lo hagan durante algún tiempo.</span><span class="sxs-lookup"><span data-stu-id="adc17-109">Ultimately, IPv6 will be fully supported worldwide, but at this time, many companies and devices that your enterprise might need to communicate with do not yet support IPv6, and may not for some time.</span></span> <span data-ttu-id="adc17-110">Una configuración de solo IPv4 le ayudará a asegurarse de que la implementación de Lync Server se puede comunicar con la mayoría de los dispositivos existentes.</span><span class="sxs-lookup"><span data-stu-id="adc17-110">An IPv4-only configuration will help to ensure that your Lync Server implementation can communicate with most existing devices.</span></span>

  - <span data-ttu-id="adc17-111">**Solo IPv6**     Por el contrario, una implementación completa de IPv6, en este momento, excluirá la comunicación con muchos dispositivos existentes.</span><span class="sxs-lookup"><span data-stu-id="adc17-111">**IPv6 only**   Conversely, a full IPv6 implementation, at this time, will exclude communication with many existing devices.</span></span>

  - <span data-ttu-id="adc17-112">**Pila dual**     Pila dual es una red donde están habilitadas las direcciones IPv4 e IPv6.</span><span class="sxs-lookup"><span data-stu-id="adc17-112">**Dual Stack**   Dual stack is a network where both IPv4 and IPv6 addresses are enabled.</span></span> <span data-ttu-id="adc17-113">Esta configuración se admite en Lync Server 2013 porque, en la mayoría de los casos, la transición de Full-IPv4 a Full-IPv6 tardará varios años.</span><span class="sxs-lookup"><span data-stu-id="adc17-113">This configuration is supported in Lync Server 2013 because in most cases the transition from full-IPv4 to full-IPv6 will take several years.</span></span>

<span data-ttu-id="adc17-114">En las secciones siguientes se resume la compatibilidad entre estas tres configuraciones para varias características de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="adc17-114">The following sections outline the compatibility among these three configurations for various Lync Server features.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="adc17-p104">La configuración de tipo solo IPv6 en el cliente o el servidor solo se admite en entornos de ensayo y con fines de validación, no se admite en implementaciones de producción.</span><span class="sxs-lookup"><span data-stu-id="adc17-p104">Client or server configuration with IPv6 only is supported only for lab or validation purposes. IPv6 only configuration is not supported in the production deployment.</span></span>



</div>

<div>

## <a name="client-registration"></a><span data-ttu-id="adc17-117">Registro de clientes</span><span class="sxs-lookup"><span data-stu-id="adc17-117">Client Registration</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="adc17-118">Red de extremo de clientes</span><span class="sxs-lookup"><span data-stu-id="adc17-118">Client endpoint network</span></span></th>
<th><span data-ttu-id="adc17-119">Red del servidor</span><span class="sxs-lookup"><span data-stu-id="adc17-119">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="adc17-120">IPv4</span><span class="sxs-lookup"><span data-stu-id="adc17-120">IPv4</span></span></p></td>
<td><p><span data-ttu-id="adc17-121">IPv4</span><span class="sxs-lookup"><span data-stu-id="adc17-121">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="adc17-122">IPv4</span><span class="sxs-lookup"><span data-stu-id="adc17-122">IPv4</span></span></p></td>
<td><p><span data-ttu-id="adc17-123">Pila dual</span><span class="sxs-lookup"><span data-stu-id="adc17-123">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="adc17-124">Pila dual</span><span class="sxs-lookup"><span data-stu-id="adc17-124">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="adc17-125">IPv4</span><span class="sxs-lookup"><span data-stu-id="adc17-125">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="adc17-126">Pila dual</span><span class="sxs-lookup"><span data-stu-id="adc17-126">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="adc17-127">Pila dual</span><span class="sxs-lookup"><span data-stu-id="adc17-127">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="adc17-128">Pila dual</span><span class="sxs-lookup"><span data-stu-id="adc17-128">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="adc17-129">IPv6</span><span class="sxs-lookup"><span data-stu-id="adc17-129">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="adc17-130">IPv6</span><span class="sxs-lookup"><span data-stu-id="adc17-130">IPv6</span></span></p></td>
<td><p><span data-ttu-id="adc17-131">Pila dual</span><span class="sxs-lookup"><span data-stu-id="adc17-131">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="adc17-132">IPv6</span><span class="sxs-lookup"><span data-stu-id="adc17-132">IPv6</span></span></p></td>
<td><p><span data-ttu-id="adc17-133">IPv6</span><span class="sxs-lookup"><span data-stu-id="adc17-133">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="peer-to-peer-client"></a><span data-ttu-id="adc17-134">Cliente de punto a punto</span><span class="sxs-lookup"><span data-stu-id="adc17-134">Peer-to-Peer Client</span></span>

<span data-ttu-id="adc17-p105">Las comunicaciones de punto a punto incluyen audio, audio y vídeo, uso compartido de aplicaciones y transferencia de archivos. Después de que se hayan registrado con éxito ambos clientes, se admiten las combinaciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="adc17-p105">Peer-to-peer communications include audio, audio/video, application sharing, and file transfer. After both clients have successfully registered, the following combinations are supported.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="adc17-137">Extremo de cliente 1</span><span class="sxs-lookup"><span data-stu-id="adc17-137">Client endpoint 1</span></span></th>
<th><span data-ttu-id="adc17-138">Extremo de cliente 2</span><span class="sxs-lookup"><span data-stu-id="adc17-138">Client endpoint 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="adc17-139">IPv4</span><span class="sxs-lookup"><span data-stu-id="adc17-139">IPv4</span></span></p></td>
<td><p><span data-ttu-id="adc17-140">IPv4</span><span class="sxs-lookup"><span data-stu-id="adc17-140">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="adc17-141">IPv4</span><span class="sxs-lookup"><span data-stu-id="adc17-141">IPv4</span></span></p></td>
<td><p><span data-ttu-id="adc17-142">Pila dual</span><span class="sxs-lookup"><span data-stu-id="adc17-142">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="adc17-143">Pila dual</span><span class="sxs-lookup"><span data-stu-id="adc17-143">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="adc17-144">Pila dual</span><span class="sxs-lookup"><span data-stu-id="adc17-144">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="adc17-145">IPv6</span><span class="sxs-lookup"><span data-stu-id="adc17-145">IPv6</span></span></p></td>
<td><p><span data-ttu-id="adc17-146">Pila dual</span><span class="sxs-lookup"><span data-stu-id="adc17-146">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="adc17-147">IPv6</span><span class="sxs-lookup"><span data-stu-id="adc17-147">IPv6</span></span></p></td>
<td><p><span data-ttu-id="adc17-148">IPv6</span><span class="sxs-lookup"><span data-stu-id="adc17-148">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="conferencing"></a><span data-ttu-id="adc17-149">Conferencia</span><span class="sxs-lookup"><span data-stu-id="adc17-149">Conferencing</span></span>

<span data-ttu-id="adc17-150">Las conferencias incluyen audio y vídeo, uso compartido de aplicaciones y colaboración de datos (pizarra y uso compartido de archivos).</span><span class="sxs-lookup"><span data-stu-id="adc17-150">Conferencing includes audio/video, application sharing, and data collaboration (whiteboarding and file sharing).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="adc17-151">Red de extremo de cliente</span><span class="sxs-lookup"><span data-stu-id="adc17-151">Client endpoint network</span></span></th>
<th><span data-ttu-id="adc17-152">Red del servidor</span><span class="sxs-lookup"><span data-stu-id="adc17-152">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="adc17-153">IPv4</span><span class="sxs-lookup"><span data-stu-id="adc17-153">IPv4</span></span></p></td>
<td><p><span data-ttu-id="adc17-154">IPv4</span><span class="sxs-lookup"><span data-stu-id="adc17-154">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="adc17-155">IPv4</span><span class="sxs-lookup"><span data-stu-id="adc17-155">IPv4</span></span></p></td>
<td><p><span data-ttu-id="adc17-156">Pila dual</span><span class="sxs-lookup"><span data-stu-id="adc17-156">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="adc17-157">Pila dual</span><span class="sxs-lookup"><span data-stu-id="adc17-157">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="adc17-158">IPv4</span><span class="sxs-lookup"><span data-stu-id="adc17-158">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="adc17-159">Pila dual</span><span class="sxs-lookup"><span data-stu-id="adc17-159">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="adc17-160">Pila dual</span><span class="sxs-lookup"><span data-stu-id="adc17-160">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="adc17-161">Pila dual</span><span class="sxs-lookup"><span data-stu-id="adc17-161">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="adc17-162">IPv6</span><span class="sxs-lookup"><span data-stu-id="adc17-162">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="adc17-163">IPv6</span><span class="sxs-lookup"><span data-stu-id="adc17-163">IPv6</span></span></p></td>
<td><p><span data-ttu-id="adc17-164">Pila dual</span><span class="sxs-lookup"><span data-stu-id="adc17-164">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="adc17-165">IPv6</span><span class="sxs-lookup"><span data-stu-id="adc17-165">IPv6</span></span></p></td>
<td><p><span data-ttu-id="adc17-166">IPv6</span><span class="sxs-lookup"><span data-stu-id="adc17-166">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="mediation-serverpstn"></a><span data-ttu-id="adc17-167">Servidor de mediación/RTC</span><span class="sxs-lookup"><span data-stu-id="adc17-167">Mediation Server/PSTN</span></span>

<span data-ttu-id="adc17-168">Lync Server 2013 no admite el desvío de medios para llamadas de red telefónica conmutada (RTC) si el tráfico se realiza a través de una interfaz IPv6.</span><span class="sxs-lookup"><span data-stu-id="adc17-168">Lync Server 2013 does not support media bypass for public switched telephone network (PSTN) calls if the traffic is through an IPv6 interface.</span></span> <span data-ttu-id="adc17-169">Si se requiere la omisión de medios, se recomienda que la puerta de enlace RTC se configure con IPv4.</span><span class="sxs-lookup"><span data-stu-id="adc17-169">If media bypass is required, we recommend that the PSTN gateway is configured to IPv4.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="adc17-170">Interfaz principal\*</span><span class="sxs-lookup"><span data-stu-id="adc17-170">Primary interface\*</span></span></th>
<th><span data-ttu-id="adc17-171">Interfaz RTC (en el servidor de mediación)</span><span class="sxs-lookup"><span data-stu-id="adc17-171">PSTN interface (on Mediation Server)</span></span></th>
<th><span data-ttu-id="adc17-172">Configuración de la puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="adc17-172">PSTN gateway setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="adc17-173">IPv4</span><span class="sxs-lookup"><span data-stu-id="adc17-173">IPv4</span></span></p></td>
<td><p><span data-ttu-id="adc17-174">Pila dual</span><span class="sxs-lookup"><span data-stu-id="adc17-174">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="adc17-175">IPv4</span><span class="sxs-lookup"><span data-stu-id="adc17-175">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="adc17-176">Pila dual</span><span class="sxs-lookup"><span data-stu-id="adc17-176">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="adc17-177">Pila dual</span><span class="sxs-lookup"><span data-stu-id="adc17-177">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="adc17-178">IPv4</span><span class="sxs-lookup"><span data-stu-id="adc17-178">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="adc17-179">Pila dual</span><span class="sxs-lookup"><span data-stu-id="adc17-179">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="adc17-180">Pila dual</span><span class="sxs-lookup"><span data-stu-id="adc17-180">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="adc17-181">IPv6</span><span class="sxs-lookup"><span data-stu-id="adc17-181">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="adc17-182">\* La interfaz principal es la interfaz que se comunica con los componentes de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="adc17-182">\* The primary interface is the interface that communicates with the Lync Server components.</span></span>

</div>

<div>

## <a name="remote-user-peer-to-peer-communications"></a><span data-ttu-id="adc17-183">Comunicaciones de punto a punto de usuarios remotos</span><span class="sxs-lookup"><span data-stu-id="adc17-183">Remote User Peer-to-Peer Communications</span></span>

<span data-ttu-id="adc17-184">Las comunicaciones de punto a punto con usuarios remotos incluyen mensajería instantánea, audio y vídeo, uso compartido de aplicaciones y transferencia de archivos.</span><span class="sxs-lookup"><span data-stu-id="adc17-184">Peer-to-peer communications with remote users include instant messaging, audio/video, application sharing, and file transfer.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="adc17-185">Red de usuarios remotos</span><span class="sxs-lookup"><span data-stu-id="adc17-185">Remote user network</span></span></th>
<th><span data-ttu-id="adc17-186">Servidor perimetral (perímetro externo)</span><span class="sxs-lookup"><span data-stu-id="adc17-186">Edge server (External edge)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="adc17-187">IPv4</span><span class="sxs-lookup"><span data-stu-id="adc17-187">IPv4</span></span></p></td>
<td><p><span data-ttu-id="adc17-188">IPv4</span><span class="sxs-lookup"><span data-stu-id="adc17-188">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="adc17-189">Pila dual</span><span class="sxs-lookup"><span data-stu-id="adc17-189">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="adc17-190">IPv4</span><span class="sxs-lookup"><span data-stu-id="adc17-190">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="adc17-191">Pila dual</span><span class="sxs-lookup"><span data-stu-id="adc17-191">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="adc17-192">Pila dual</span><span class="sxs-lookup"><span data-stu-id="adc17-192">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="adc17-193">IPv6</span><span class="sxs-lookup"><span data-stu-id="adc17-193">IPv6</span></span></p></td>
<td><p><span data-ttu-id="adc17-194">Pila dual</span><span class="sxs-lookup"><span data-stu-id="adc17-194">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="adc17-195">IPv6</span><span class="sxs-lookup"><span data-stu-id="adc17-195">IPv6</span></span></p></td>
<td><p><span data-ttu-id="adc17-196">IPv6</span><span class="sxs-lookup"><span data-stu-id="adc17-196">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-pool-and-edge-pool-configuration"></a><span data-ttu-id="adc17-197">Configuración del grupo de servidores front-end y del grupo de servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="adc17-197">Front End Pool and Edge Pool Configuration</span></span>

<span data-ttu-id="adc17-198">En la siguiente tabla se muestra la matriz de compatibilidad entre el grupo de servidores front-end y el grupo de servidores perimetrales internos.</span><span class="sxs-lookup"><span data-stu-id="adc17-198">The following table shows the support matrix between the Front End Server pool and the internal Edge Server pool.</span></span>

### <a name="front-end-pool-and-edge-pool-internal-edge-matrix"></a><span data-ttu-id="adc17-199">Matriz del grupo de servidores front-end y del grupo de servidores perimetrales (perímetro interno)</span><span class="sxs-lookup"><span data-stu-id="adc17-199">Front End Pool and Edge Pool (Internal Edge) Matrix</span></span>

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
<td><p><span data-ttu-id="adc17-200"><strong>Grupo de servidores perimetrales: IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="adc17-200"><strong>Edge Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="adc17-201"><strong>Grupo de servidores perimetrales: pila dual</strong></span><span class="sxs-lookup"><span data-stu-id="adc17-201"><strong>Edge Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="adc17-202"><strong>Grupo de servidores perimetrales: IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="adc17-202"><strong>Edge Pool: IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="adc17-203"><strong>Grupo de servidores front-end: IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="adc17-203"><strong>Front End Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="adc17-204">Sí</span><span class="sxs-lookup"><span data-stu-id="adc17-204">Yes</span></span></p></td>
<td><p><span data-ttu-id="adc17-205">Sí</span><span class="sxs-lookup"><span data-stu-id="adc17-205">Yes</span></span></p></td>
<td><p><span data-ttu-id="adc17-206">No</span><span class="sxs-lookup"><span data-stu-id="adc17-206">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="adc17-207"><strong>Grupo de servidores front-end: pila dual</strong></span><span class="sxs-lookup"><span data-stu-id="adc17-207"><strong>Front End Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="adc17-208">Sí</span><span class="sxs-lookup"><span data-stu-id="adc17-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="adc17-209">Sí</span><span class="sxs-lookup"><span data-stu-id="adc17-209">Yes</span></span></p></td>
<td><p><span data-ttu-id="adc17-210">No</span><span class="sxs-lookup"><span data-stu-id="adc17-210">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="adc17-211"><strong>Grupo de servidores front-end: IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="adc17-211"><strong>Front End Pool: IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="adc17-212">No</span><span class="sxs-lookup"><span data-stu-id="adc17-212">No</span></span></p></td>
<td><p><span data-ttu-id="adc17-213">No</span><span class="sxs-lookup"><span data-stu-id="adc17-213">No</span></span></p></td>
<td><p><span data-ttu-id="adc17-214">Sí\*</span><span class="sxs-lookup"><span data-stu-id="adc17-214">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="adc17-215">\* Use esta combinación únicamente en un entorno de laboratorio.</span><span class="sxs-lookup"><span data-stu-id="adc17-215">\* Use this combination only in a lab environment.</span></span>

<span data-ttu-id="adc17-216">La tabla siguiente es una matriz de combinaciones admitidas de las interfaces perimetrales interna y externa.</span><span class="sxs-lookup"><span data-stu-id="adc17-216">The following table is a matrix of the supported combinations of internal and external edge interfaces.</span></span>

### <a name="edge-pool-internal-edge-and-edge-pool-external-edge-matrix"></a><span data-ttu-id="adc17-217">Matriz del grupo de servidores perimetrales (perímetro interno) y del grupo de servidores perimetrales (perímetro externo)</span><span class="sxs-lookup"><span data-stu-id="adc17-217">Edge Pool (Internal Edge) and Edge pool (External Edge) Matrix</span></span>

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
<td><p><span data-ttu-id="adc17-218"><strong>Grupo de servidores perimetrales (perímetro externo): IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="adc17-218"><strong>Edge Pool (External Edge) : IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="adc17-219"><strong>Grupo de servidores perimetrales (perímetro externo): pila dual</strong></span><span class="sxs-lookup"><span data-stu-id="adc17-219"><strong>Edge Pool (External Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="adc17-220"><strong>Grupo de servidores perimetrales (perímetro externo): IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="adc17-220"><strong>Edge Pool (External Edge): IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="adc17-221"><strong>Grupo de servidores perimetrales (perímetro interno): IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="adc17-221"><strong>Edge Pool (Internal Edge): IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="adc17-222">Sí</span><span class="sxs-lookup"><span data-stu-id="adc17-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="adc17-223">Sí</span><span class="sxs-lookup"><span data-stu-id="adc17-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="adc17-224">No</span><span class="sxs-lookup"><span data-stu-id="adc17-224">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="adc17-225"><strong>Grupo de servidores perimetrales (perímetro interno): pila dual</strong></span><span class="sxs-lookup"><span data-stu-id="adc17-225"><strong>Edge Pool (Internal Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="adc17-226">No</span><span class="sxs-lookup"><span data-stu-id="adc17-226">No</span></span></p></td>
<td><p><span data-ttu-id="adc17-227">Sí</span><span class="sxs-lookup"><span data-stu-id="adc17-227">Yes</span></span></p></td>
<td><p><span data-ttu-id="adc17-228">No</span><span class="sxs-lookup"><span data-stu-id="adc17-228">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="adc17-229"><strong>Grupo de servidores perimetrales (perímetro interno): IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="adc17-229"><strong>Edge Pool (Internal Edge): IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="adc17-230">No</span><span class="sxs-lookup"><span data-stu-id="adc17-230">No</span></span></p></td>
<td><p><span data-ttu-id="adc17-231">No</span><span class="sxs-lookup"><span data-stu-id="adc17-231">No</span></span></p></td>
<td><p><span data-ttu-id="adc17-232">Sí\*</span><span class="sxs-lookup"><span data-stu-id="adc17-232">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="adc17-233">\* Use esta combinación únicamente en un entorno de laboratorio.</span><span class="sxs-lookup"><span data-stu-id="adc17-233">\* Use this combination only in a lab environment.</span></span>

</div>

<div>

## <a name="advanced-enterprise-voice-support-for-ipv6"></a><span data-ttu-id="adc17-234">Compatibilidad avanzada de Enterprise Voice para IPv6</span><span class="sxs-lookup"><span data-stu-id="adc17-234">Advanced Enterprise Voice Support for IPv6</span></span>

<span data-ttu-id="adc17-235">Las implementaciones que incluyen el control de admisión de llamadas (CAC), Enhanced 9-1-1 (E9-1-1) o la omisión de medios se deben configurar como implementaciones de solo IPv4 o de pila dual.</span><span class="sxs-lookup"><span data-stu-id="adc17-235">Deployments that include call admission control (CAC), Enhanced 9-1-1 (E9-1-1), or media bypass must be configured as IPv4 only or as a dual-stacked implementation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="adc17-236">En una implementación de pila dual, incluso si un cliente de Lync se conecta a un Lync Server mediante IPv6, Lync hará un mejor esfuerzo para asignar una dirección IPv4 adecuada para admitir E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="adc17-236">In a dual-stacked deployment, even if a Lync client connects to a Lync Server by using IPv6, Lync will make a best effort to map an appropriate IPv4 address to support E9-1-1.</span></span>



</div>

<span data-ttu-id="adc17-237">No se admite el servicio de información de ubicación con direcciones IPv6.</span><span class="sxs-lookup"><span data-stu-id="adc17-237">Location Information service with IPv6 addresses is not supported.</span></span>

<span data-ttu-id="adc17-p107">La mensajería unificada (MU) de Exchange no admite IPv6. Para la MU de Exchange, asegúrese de que la resolución de DNS no devuelve una dirección IPv6. El uso de IPv6 puede provocar un fallo cuando se envían las llamadas al correo de voz.</span><span class="sxs-lookup"><span data-stu-id="adc17-p107">Exchange Unified Messaging (UM) does not support IPv6. For Exchange UM, be sure that DNS resolution does not return an IPv6 address. Using IPv6 may cause failure when calls are sent to voice mail.</span></span>

</div>

<div>

## <a name="other-lync-server-2013-feature-support-for-ipv6"></a><span data-ttu-id="adc17-241">Otra compatibilidad con características de Lync Server 2013 para IPv6</span><span class="sxs-lookup"><span data-stu-id="adc17-241">Other Lync Server 2013 Feature Support for IPv6</span></span>

<span data-ttu-id="adc17-242">Además de las características y los componentes mencionados anteriormente, Lync Server 2013 admite IPv6 para las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="adc17-242">In addition to the features and components mentioned previously, Lync Server 2013 supports IPv6 for the following features:</span></span>

  - <span data-ttu-id="adc17-243">**Chat persistente**</span><span class="sxs-lookup"><span data-stu-id="adc17-243">**Persistent Chat**</span></span>
    
    <span data-ttu-id="adc17-244">Configure IPv6 para chat persistente mediante el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="adc17-244">You configure IPv6 for Persistent Chat by using Topology Builder.</span></span> <span data-ttu-id="adc17-245">Para obtener más información sobre cómo configurar chat persistente, consulte la documentación de implementación del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="adc17-245">For details about configuring Persistent Chat, see the Deploying Persistent Chat Server documentation.</span></span>

  - <span data-ttu-id="adc17-246">**Informes de Calidad de la experiencia (QoE) y registro de detalles de llamadas (CDR)**</span><span class="sxs-lookup"><span data-stu-id="adc17-246">**Quality of Experience (QoE) and call detail recording (CDR) reports**</span></span>
    
    <span data-ttu-id="adc17-247">Los informes de supervisión incluyen la dirección IP cuando se guarda en la base de datos del servidor de supervisión, tanto del tipo IPv4 como IPv6.</span><span class="sxs-lookup"><span data-stu-id="adc17-247">Monitoring reports include the IP address as it is stored in the Monitoring Server database, whether of type IPv4 or IPv6.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

