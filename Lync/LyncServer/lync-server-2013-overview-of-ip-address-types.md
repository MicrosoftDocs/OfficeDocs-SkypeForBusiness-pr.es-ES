---
title: 'Lync Server 2013: Información general sobre los tipos de direcciones IP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of IP address types for Lync Server
ms:assetid: ee9a695f-5cf5-441e-94fb-6adeca50e8d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205363(v=OCS.15)
ms:contentKeyID: 48185759
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90d31045879c4e6f488c232687346ed0413ef62b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825516"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-ip-address-types-for-lync-server-2013"></a><span data-ttu-id="a0f55-102">Información general sobre los tipos de direcciones IP en Lync Server para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0f55-102">Overview of IP address types for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0f55-103">_**Última modificación del tema:** 2013-01-29_</span><span class="sxs-lookup"><span data-stu-id="a0f55-103">_**Topic Last Modified:** 2013-01-29_</span></span>

<span data-ttu-id="a0f55-104">Tiene tres opciones para configurar las direcciones IP en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a0f55-104">You have three options when configuring IP addresses in Lync Server 2013.</span></span> <span data-ttu-id="a0f55-105">Puede configurar Lync Server 2013 para que admita solo IP versión 4 (IPv4), solo IP versión 6 (IPv6) o una combinación de ambos (conocido como una *pila doble*).</span><span class="sxs-lookup"><span data-stu-id="a0f55-105">You can configure Lync Server 2013 to support only IP version 4 (IPv4), only IP version 6 (IPv6), or a combination of both (known as a *dual stack*).</span></span> <span data-ttu-id="a0f55-106">Cada tipo de configuración entraña varios aspectos que necesita tener en cuenta:</span><span class="sxs-lookup"><span data-stu-id="a0f55-106">There are several issues to consider with each type of configuration:</span></span>

  - <span data-ttu-id="a0f55-107">**IPv4 solo**   se creó IPv6 porque el mundo se está quedando sin direcciones IPv4.</span><span class="sxs-lookup"><span data-stu-id="a0f55-107">**IPv4 only**   IPv6 was created because the world is running out of IPv4 addresses.</span></span> <span data-ttu-id="a0f55-108">En última instancia, IPv6 será totalmente compatible en todo el mundo, pero en este momento, muchas de las compañías y dispositivos que su empresa podría necesitar para comunicarse aún no son compatibles con IPv6, y es posible que no lo hagan durante algún tiempo.</span><span class="sxs-lookup"><span data-stu-id="a0f55-108">Ultimately, IPv6 will be fully supported worldwide, but at this time, many companies and devices that your enterprise might need to communicate with do not yet support IPv6, and may not for some time.</span></span> <span data-ttu-id="a0f55-109">Una configuración de solo IPv4 le ayudará a asegurarse de que su implementación de Lync Server pueda comunicarse con la mayoría de los dispositivos existentes.</span><span class="sxs-lookup"><span data-stu-id="a0f55-109">An IPv4-only configuration will help to ensure that your Lync Server implementation can communicate with most existing devices.</span></span>

  - <span data-ttu-id="a0f55-110">**Solo IPv6 a**   la inversa, una implementación de IPv6 completa, en este momento, excluirá la comunicación con muchos dispositivos existentes.</span><span class="sxs-lookup"><span data-stu-id="a0f55-110">**IPv6 only**   Conversely, a full IPv6 implementation, at this time, will exclude communication with many existing devices.</span></span>

  - <span data-ttu-id="a0f55-111">\*\*\*\* Pila Dual Stack es una red en la que se habilitan las direcciones IPv4 e IPv6.   </span><span class="sxs-lookup"><span data-stu-id="a0f55-111">**Dual Stack**   Dual stack is a network where both IPv4 and IPv6 addresses are enabled.</span></span> <span data-ttu-id="a0f55-112">Esta configuración es compatible con Lync Server 2013 porque, en la mayoría de los casos, la transición de IPv4 completa a Full-IPv6 llevará varios años.</span><span class="sxs-lookup"><span data-stu-id="a0f55-112">This configuration is supported in Lync Server 2013 because in most cases the transition from full-IPv4 to full-IPv6 will take several years.</span></span>

<span data-ttu-id="a0f55-113">En las secciones siguientes se describe la compatibilidad entre estas tres configuraciones para varias características de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a0f55-113">The following sections outline the compatibility among these three configurations for various Lync Server features.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a0f55-p104">La configuración de tipo solo IPv6 en el cliente o el servidor solo se admite en entornos de laboratorio y con fines de validación, no se admite en implementaciones de producción.</span><span class="sxs-lookup"><span data-stu-id="a0f55-p104">Client or server configuration with IPv6 only is supported only for lab or validation purposes. IPv6 only configuration is not supported in the production deployment.</span></span>



</div>

<div>

## <a name="client-registration"></a><span data-ttu-id="a0f55-116">Registro de clientes</span><span class="sxs-lookup"><span data-stu-id="a0f55-116">Client Registration</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a0f55-117">Red de extremo de cliente</span><span class="sxs-lookup"><span data-stu-id="a0f55-117">Client endpoint network</span></span></th>
<th><span data-ttu-id="a0f55-118">Red del servidor</span><span class="sxs-lookup"><span data-stu-id="a0f55-118">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a0f55-119">IPv4</span><span class="sxs-lookup"><span data-stu-id="a0f55-119">IPv4</span></span></p></td>
<td><p><span data-ttu-id="a0f55-120">IPv4</span><span class="sxs-lookup"><span data-stu-id="a0f55-120">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0f55-121">IPv4</span><span class="sxs-lookup"><span data-stu-id="a0f55-121">IPv4</span></span></p></td>
<td><p><span data-ttu-id="a0f55-122">Pila dual</span><span class="sxs-lookup"><span data-stu-id="a0f55-122">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0f55-123">Pila dual</span><span class="sxs-lookup"><span data-stu-id="a0f55-123">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="a0f55-124">IPv4</span><span class="sxs-lookup"><span data-stu-id="a0f55-124">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0f55-125">Pila dual</span><span class="sxs-lookup"><span data-stu-id="a0f55-125">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="a0f55-126">Pila dual</span><span class="sxs-lookup"><span data-stu-id="a0f55-126">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0f55-127">Pila dual</span><span class="sxs-lookup"><span data-stu-id="a0f55-127">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="a0f55-128">IPv6</span><span class="sxs-lookup"><span data-stu-id="a0f55-128">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0f55-129">IPv6</span><span class="sxs-lookup"><span data-stu-id="a0f55-129">IPv6</span></span></p></td>
<td><p><span data-ttu-id="a0f55-130">Pila dual</span><span class="sxs-lookup"><span data-stu-id="a0f55-130">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0f55-131">IPv6</span><span class="sxs-lookup"><span data-stu-id="a0f55-131">IPv6</span></span></p></td>
<td><p><span data-ttu-id="a0f55-132">IPv6</span><span class="sxs-lookup"><span data-stu-id="a0f55-132">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="peer-to-peer-client"></a><span data-ttu-id="a0f55-133">Cliente de punto a punto</span><span class="sxs-lookup"><span data-stu-id="a0f55-133">Peer-to-Peer Client</span></span>

<span data-ttu-id="a0f55-p105">Las comunicaciones de punto a punto incluyen audio, audio y vídeo, uso compartido de aplicaciones y transferencia de archivos. Después de que se hayan registrado con éxito ambos clientes, se admiten las combinaciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="a0f55-p105">Peer-to-peer communications include audio, audio/video, application sharing, and file transfer. After both clients have successfully registered, the following combinations are supported.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a0f55-136">Extremo de cliente 1</span><span class="sxs-lookup"><span data-stu-id="a0f55-136">Client endpoint 1</span></span></th>
<th><span data-ttu-id="a0f55-137">Extremo de cliente 2</span><span class="sxs-lookup"><span data-stu-id="a0f55-137">Client endpoint 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a0f55-138">IPv4</span><span class="sxs-lookup"><span data-stu-id="a0f55-138">IPv4</span></span></p></td>
<td><p><span data-ttu-id="a0f55-139">IPv4</span><span class="sxs-lookup"><span data-stu-id="a0f55-139">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0f55-140">IPv4</span><span class="sxs-lookup"><span data-stu-id="a0f55-140">IPv4</span></span></p></td>
<td><p><span data-ttu-id="a0f55-141">Pila dual</span><span class="sxs-lookup"><span data-stu-id="a0f55-141">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0f55-142">Pila dual</span><span class="sxs-lookup"><span data-stu-id="a0f55-142">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="a0f55-143">Pila dual</span><span class="sxs-lookup"><span data-stu-id="a0f55-143">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0f55-144">IPv6</span><span class="sxs-lookup"><span data-stu-id="a0f55-144">IPv6</span></span></p></td>
<td><p><span data-ttu-id="a0f55-145">Pila dual</span><span class="sxs-lookup"><span data-stu-id="a0f55-145">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0f55-146">IPv6</span><span class="sxs-lookup"><span data-stu-id="a0f55-146">IPv6</span></span></p></td>
<td><p><span data-ttu-id="a0f55-147">IPv6</span><span class="sxs-lookup"><span data-stu-id="a0f55-147">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="conferencing"></a><span data-ttu-id="a0f55-148">Conferencia</span><span class="sxs-lookup"><span data-stu-id="a0f55-148">Conferencing</span></span>

<span data-ttu-id="a0f55-149">Las conferencias incluyen audio/vídeo, uso compartido de aplicaciones y colaboración de datos (pizarras y uso compartido de archivos).</span><span class="sxs-lookup"><span data-stu-id="a0f55-149">Conferencing includes audio/video, application sharing, and data collaboration (whiteboarding and file sharing).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a0f55-150">Red de extremo de cliente</span><span class="sxs-lookup"><span data-stu-id="a0f55-150">Client endpoint network</span></span></th>
<th><span data-ttu-id="a0f55-151">Red del servidor</span><span class="sxs-lookup"><span data-stu-id="a0f55-151">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a0f55-152">IPv4</span><span class="sxs-lookup"><span data-stu-id="a0f55-152">IPv4</span></span></p></td>
<td><p><span data-ttu-id="a0f55-153">IPv4</span><span class="sxs-lookup"><span data-stu-id="a0f55-153">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0f55-154">IPv4</span><span class="sxs-lookup"><span data-stu-id="a0f55-154">IPv4</span></span></p></td>
<td><p><span data-ttu-id="a0f55-155">Pila dual</span><span class="sxs-lookup"><span data-stu-id="a0f55-155">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0f55-156">Pila dual</span><span class="sxs-lookup"><span data-stu-id="a0f55-156">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="a0f55-157">IPv4</span><span class="sxs-lookup"><span data-stu-id="a0f55-157">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0f55-158">Pila dual</span><span class="sxs-lookup"><span data-stu-id="a0f55-158">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="a0f55-159">Pila dual</span><span class="sxs-lookup"><span data-stu-id="a0f55-159">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0f55-160">Pila dual</span><span class="sxs-lookup"><span data-stu-id="a0f55-160">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="a0f55-161">IPv6</span><span class="sxs-lookup"><span data-stu-id="a0f55-161">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0f55-162">IPv6</span><span class="sxs-lookup"><span data-stu-id="a0f55-162">IPv6</span></span></p></td>
<td><p><span data-ttu-id="a0f55-163">Pila dual</span><span class="sxs-lookup"><span data-stu-id="a0f55-163">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0f55-164">IPv6</span><span class="sxs-lookup"><span data-stu-id="a0f55-164">IPv6</span></span></p></td>
<td><p><span data-ttu-id="a0f55-165">IPv6</span><span class="sxs-lookup"><span data-stu-id="a0f55-165">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="mediation-serverpstn"></a><span data-ttu-id="a0f55-166">Servidor de mediación/RTC</span><span class="sxs-lookup"><span data-stu-id="a0f55-166">Mediation Server/PSTN</span></span>

<span data-ttu-id="a0f55-167">Lync Server 2013 no admite omisión de multimedia para llamadas de red telefónica conmutada (RTC) si el tráfico se realiza a través de una interfaz de IPv6.</span><span class="sxs-lookup"><span data-stu-id="a0f55-167">Lync Server 2013 does not support media bypass for public switched telephone network (PSTN) calls if the traffic is through an IPv6 interface.</span></span> <span data-ttu-id="a0f55-168">Si se requiere la omisión de medios, recomendamos que la puerta de enlace RTC se configure con IPv4.</span><span class="sxs-lookup"><span data-stu-id="a0f55-168">If media bypass is required, we recommend that the PSTN gateway is configured to IPv4.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a0f55-169">Interfaz principal\*</span><span class="sxs-lookup"><span data-stu-id="a0f55-169">Primary interface\*</span></span></th>
<th><span data-ttu-id="a0f55-170">Interfaz RTC (en el servidor de mediación)</span><span class="sxs-lookup"><span data-stu-id="a0f55-170">PSTN interface (on Mediation Server)</span></span></th>
<th><span data-ttu-id="a0f55-171">Configuración de la puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="a0f55-171">PSTN gateway setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a0f55-172">IPv4</span><span class="sxs-lookup"><span data-stu-id="a0f55-172">IPv4</span></span></p></td>
<td><p><span data-ttu-id="a0f55-173">Pila dual</span><span class="sxs-lookup"><span data-stu-id="a0f55-173">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="a0f55-174">IPv4</span><span class="sxs-lookup"><span data-stu-id="a0f55-174">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0f55-175">Pila dual</span><span class="sxs-lookup"><span data-stu-id="a0f55-175">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="a0f55-176">Pila dual</span><span class="sxs-lookup"><span data-stu-id="a0f55-176">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="a0f55-177">IPv4</span><span class="sxs-lookup"><span data-stu-id="a0f55-177">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0f55-178">Pila dual</span><span class="sxs-lookup"><span data-stu-id="a0f55-178">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="a0f55-179">Pila dual</span><span class="sxs-lookup"><span data-stu-id="a0f55-179">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="a0f55-180">IPv6</span><span class="sxs-lookup"><span data-stu-id="a0f55-180">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a0f55-181">\*La interfaz principal es la interfaz que se comunica con los componentes de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a0f55-181">\* The primary interface is the interface that communicates with the Lync Server components.</span></span>

</div>

<div>

## <a name="remote-user-peer-to-peer-communications"></a><span data-ttu-id="a0f55-182">Comunicaciones de punto a punto de usuarios remotos</span><span class="sxs-lookup"><span data-stu-id="a0f55-182">Remote User Peer-to-Peer Communications</span></span>

<span data-ttu-id="a0f55-183">Las comunicaciones de punto a punto con usuarios remotos incluyen mensajería instantánea, audio y vídeo, uso compartido de aplicaciones y transferencia de archivos.</span><span class="sxs-lookup"><span data-stu-id="a0f55-183">Peer-to-peer communications with remote users include instant messaging, audio/video, application sharing, and file transfer.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a0f55-184">Red de usuarios remotos</span><span class="sxs-lookup"><span data-stu-id="a0f55-184">Remote user network</span></span></th>
<th><span data-ttu-id="a0f55-185">Servidor perimetral (perímetro externo)</span><span class="sxs-lookup"><span data-stu-id="a0f55-185">Edge server (External edge)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a0f55-186">IPv4</span><span class="sxs-lookup"><span data-stu-id="a0f55-186">IPv4</span></span></p></td>
<td><p><span data-ttu-id="a0f55-187">IPv4</span><span class="sxs-lookup"><span data-stu-id="a0f55-187">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0f55-188">Pila dual</span><span class="sxs-lookup"><span data-stu-id="a0f55-188">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="a0f55-189">IPv4</span><span class="sxs-lookup"><span data-stu-id="a0f55-189">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0f55-190">Pila dual</span><span class="sxs-lookup"><span data-stu-id="a0f55-190">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="a0f55-191">Pila dual</span><span class="sxs-lookup"><span data-stu-id="a0f55-191">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0f55-192">IPv6</span><span class="sxs-lookup"><span data-stu-id="a0f55-192">IPv6</span></span></p></td>
<td><p><span data-ttu-id="a0f55-193">Pila dual</span><span class="sxs-lookup"><span data-stu-id="a0f55-193">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0f55-194">IPv6</span><span class="sxs-lookup"><span data-stu-id="a0f55-194">IPv6</span></span></p></td>
<td><p><span data-ttu-id="a0f55-195">IPv6</span><span class="sxs-lookup"><span data-stu-id="a0f55-195">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-pool-and-edge-pool-configuration"></a><span data-ttu-id="a0f55-196">Configuración del grupo de servidores front-end y del grupo de servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="a0f55-196">Front End Pool and Edge Pool Configuration</span></span>

<span data-ttu-id="a0f55-197">En la tabla siguiente se muestra la matriz de soporte técnico entre el grupo de servidores front-end y el grupo de servidores perimetrales internos.</span><span class="sxs-lookup"><span data-stu-id="a0f55-197">The following table shows the support matrix between the Front End Server pool and the internal Edge Server pool.</span></span>

### <a name="front-end-pool-and-edge-pool-internal-edge-matrix"></a><span data-ttu-id="a0f55-198">Matriz del grupo de servidores front-end y del grupo de servidores perimetrales (perímetro interno)</span><span class="sxs-lookup"><span data-stu-id="a0f55-198">Front End Pool and Edge Pool (Internal Edge) Matrix</span></span>

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
<td><p><span data-ttu-id="a0f55-199"><strong>Grupo de servidores perimetrales: IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="a0f55-199"><strong>Edge Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="a0f55-200"><strong>Grupo de servidores perimetrales: pila dual</strong></span><span class="sxs-lookup"><span data-stu-id="a0f55-200"><strong>Edge Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="a0f55-201"><strong>Grupo de servidores perimetrales: IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="a0f55-201"><strong>Edge Pool: IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0f55-202"><strong>Grupo de servidores front-end: IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="a0f55-202"><strong>Front End Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="a0f55-203">Sí</span><span class="sxs-lookup"><span data-stu-id="a0f55-203">Yes</span></span></p></td>
<td><p><span data-ttu-id="a0f55-204">Sí</span><span class="sxs-lookup"><span data-stu-id="a0f55-204">Yes</span></span></p></td>
<td><p><span data-ttu-id="a0f55-205">No</span><span class="sxs-lookup"><span data-stu-id="a0f55-205">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0f55-206"><strong>Grupo de servidores front-end: pila dual</strong></span><span class="sxs-lookup"><span data-stu-id="a0f55-206"><strong>Front End Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="a0f55-207">Sí </span><span class="sxs-lookup"><span data-stu-id="a0f55-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="a0f55-208">Sí</span><span class="sxs-lookup"><span data-stu-id="a0f55-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="a0f55-209">No</span><span class="sxs-lookup"><span data-stu-id="a0f55-209">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0f55-210"><strong>Grupo de servidores front-end: IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="a0f55-210"><strong>Front End Pool: IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="a0f55-211">No</span><span class="sxs-lookup"><span data-stu-id="a0f55-211">No</span></span></p></td>
<td><p><span data-ttu-id="a0f55-212">Página de invitación a la reunión con números de teléfono de acceso telefónico predeterminados</span><span class="sxs-lookup"><span data-stu-id="a0f55-212">No</span></span></p></td>
<td><p><span data-ttu-id="a0f55-213">Sí\*</span><span class="sxs-lookup"><span data-stu-id="a0f55-213">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a0f55-214">\*Use esta combinación solo en un entorno de laboratorio.</span><span class="sxs-lookup"><span data-stu-id="a0f55-214">\* Use this combination only in a lab environment.</span></span>

<span data-ttu-id="a0f55-215">La tabla siguiente es una matriz de combinaciones admitidas de las interfaces perimetrales interna y externa.</span><span class="sxs-lookup"><span data-stu-id="a0f55-215">The following table is a matrix of the supported combinations of internal and external edge interfaces.</span></span>

### <a name="edge-pool-internal-edge-and-edge-pool-external-edge-matrix"></a><span data-ttu-id="a0f55-216">Matriz del grupo de servidores perimetrales (perímetro interno) y del grupo de servidores perimetrales (perímetro externo)</span><span class="sxs-lookup"><span data-stu-id="a0f55-216">Edge Pool (Internal Edge) and Edge pool (External Edge) Matrix</span></span>

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
<td><p><span data-ttu-id="a0f55-217"><strong>Grupo de servidores perimetrales (perímetro externo): IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="a0f55-217"><strong>Edge Pool (External Edge) : IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="a0f55-218"><strong>Grupo de servidores perimetrales (perímetro externo): pila dual</strong></span><span class="sxs-lookup"><span data-stu-id="a0f55-218"><strong>Edge Pool (External Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="a0f55-219"><strong>Grupo de servidores perimetrales (perímetro externo): IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="a0f55-219"><strong>Edge Pool (External Edge): IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0f55-220"><strong>Grupo de servidores perimetrales (perímetro interno): IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="a0f55-220"><strong>Edge Pool (Internal Edge): IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="a0f55-221">Sí</span><span class="sxs-lookup"><span data-stu-id="a0f55-221">Yes</span></span></p></td>
<td><p><span data-ttu-id="a0f55-222">Sí</span><span class="sxs-lookup"><span data-stu-id="a0f55-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="a0f55-223">No</span><span class="sxs-lookup"><span data-stu-id="a0f55-223">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0f55-224"><strong>Grupo de servidores perimetrales (perímetro interno): pila dual</strong></span><span class="sxs-lookup"><span data-stu-id="a0f55-224"><strong>Edge Pool (Internal Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="a0f55-225">No</span><span class="sxs-lookup"><span data-stu-id="a0f55-225">No</span></span></p></td>
<td><p><span data-ttu-id="a0f55-226">Sí</span><span class="sxs-lookup"><span data-stu-id="a0f55-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="a0f55-227">No</span><span class="sxs-lookup"><span data-stu-id="a0f55-227">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0f55-228"><strong>Grupo de servidores perimetrales (perímetro interno): IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="a0f55-228"><strong>Edge Pool (Internal Edge): IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="a0f55-229">No</span><span class="sxs-lookup"><span data-stu-id="a0f55-229">No</span></span></p></td>
<td><p><span data-ttu-id="a0f55-230">Página de invitación a la reunión con números de teléfono de acceso telefónico predeterminados</span><span class="sxs-lookup"><span data-stu-id="a0f55-230">No</span></span></p></td>
<td><p><span data-ttu-id="a0f55-231">Sí\*</span><span class="sxs-lookup"><span data-stu-id="a0f55-231">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a0f55-232">\*Use esta combinación solo en un entorno de laboratorio.</span><span class="sxs-lookup"><span data-stu-id="a0f55-232">\* Use this combination only in a lab environment.</span></span>

</div>

<div>

## <a name="advanced-enterprise-voice-support-for-ipv6"></a><span data-ttu-id="a0f55-233">Compatibilidad avanzada de Telefonía IP empresarial para IPv6</span><span class="sxs-lookup"><span data-stu-id="a0f55-233">Advanced Enterprise Voice Support for IPv6</span></span>

<span data-ttu-id="a0f55-234">Las implementaciones que incluyen el control de admisión de llamadas (CAC), Enhanced 9-1-1 (E9-1-1) o la omisión de medios se deben configurar como implementaciones de solo IPv4 o de pila dual.</span><span class="sxs-lookup"><span data-stu-id="a0f55-234">Deployments that include call admission control (CAC), Enhanced 9-1-1 (E9-1-1), or media bypass must be configured as IPv4 only or as a dual-stacked implementation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a0f55-235">En una implementación con dos pilas, incluso si un cliente de Lync se conecta a un servidor de Lync mediante IPv6, Lync hará todo lo posible para asignar una dirección IPv4 adecuada para admitir E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="a0f55-235">In a dual-stacked deployment, even if a Lync client connects to a Lync Server by using IPv6, Lync will make a best effort to map an appropriate IPv4 address to support E9-1-1.</span></span>



</div>

<span data-ttu-id="a0f55-236">No se admite el servicio de información de ubicación con direcciones IPv6.</span><span class="sxs-lookup"><span data-stu-id="a0f55-236">Location Information service with IPv6 addresses is not supported.</span></span>

<span data-ttu-id="a0f55-p107">La mensajería unificada (MU) de Exchange no admite IPv6. Para la MU de Exchange, asegúrese de que la resolución de DNS no devuelve una dirección IPv6. El uso de IPv6 puede provocar un fallo cuando se envían las llamadas al correo de voz.</span><span class="sxs-lookup"><span data-stu-id="a0f55-p107">Exchange Unified Messaging (UM) does not support IPv6. For Exchange UM, be sure that DNS resolution does not return an IPv6 address. Using IPv6 may cause failure when calls are sent to voice mail.</span></span>

</div>

<div>

## <a name="other-lync-server-2013-feature-support-for-ipv6"></a><span data-ttu-id="a0f55-240">Otra compatibilidad con características de Lync Server 2013 para IPv6</span><span class="sxs-lookup"><span data-stu-id="a0f55-240">Other Lync Server 2013 Feature Support for IPv6</span></span>

<span data-ttu-id="a0f55-241">Además de las características y componentes mencionados anteriormente, Lync Server 2013 admite IPv6 para las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="a0f55-241">In addition to the features and components mentioned previously, Lync Server 2013 supports IPv6 for the following features:</span></span>

  - <span data-ttu-id="a0f55-242">**Chat persistente**</span><span class="sxs-lookup"><span data-stu-id="a0f55-242">**Persistent Chat**</span></span>
    
    <span data-ttu-id="a0f55-243">Para configurar IPv6 para la conversación persistente, use el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="a0f55-243">You configure IPv6 for Persistent Chat by using Topology Builder.</span></span> <span data-ttu-id="a0f55-244">Para obtener más información sobre cómo configurar una conversación persistente, consulte la documentación de implementación del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="a0f55-244">For details about configuring Persistent Chat, see the Deploying Persistent Chat Server documentation.</span></span>

  - <span data-ttu-id="a0f55-245">**Informes de Calidad de la experiencia (QoE) y registro detallado de llamadas (CDR)**</span><span class="sxs-lookup"><span data-stu-id="a0f55-245">**Quality of Experience (QoE) and call detail recording (CDR) reports**</span></span>
    
    <span data-ttu-id="a0f55-246">Los informes de supervisión incluyen la dirección IP cuando se guarda en la base de datos del servidor de supervisión, tanto del tipo IPv4 como IPv6.</span><span class="sxs-lookup"><span data-stu-id="a0f55-246">Monitoring reports include the IP address as it is stored in the Monitoring Server database, whether of type IPv4 or IPv6.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

