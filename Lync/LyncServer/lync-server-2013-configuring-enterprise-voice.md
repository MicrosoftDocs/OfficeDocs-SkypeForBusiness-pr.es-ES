---
title: 'Lync Server 2013: configurar la telefonía IP empresarial'
description: 'Lync Server 2013: configurar la telefonía IP empresarial.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Enterprise Voice
ms:assetid: 7df179fa-d3a2-4b23-a433-b750aedf980b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994041(v=OCS.15)
ms:contentKeyID: 51803952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 49a231b92bf7b04aa3466927a79258f0cbad4e3f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548436"
---
# <a name="configuring-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="6f37e-103">Configurar la telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f37e-103">Configuring Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f37e-104">_**Última modificación del tema:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="6f37e-104">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="6f37e-105">Para implementar la telefonía IP empresarial, deberá configurar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6f37e-105">To deploy Enterprise Voice, you’ll need to configure the following:</span></span>

  - <span data-ttu-id="6f37e-106">Crear un tronco</span><span class="sxs-lookup"><span data-stu-id="6f37e-106">Create a Trunk</span></span>

  - <span data-ttu-id="6f37e-107">Definir una directiva de voz</span><span class="sxs-lookup"><span data-stu-id="6f37e-107">Define a Voice Policy</span></span>

  - <span data-ttu-id="6f37e-108">Definir una ruta de voz</span><span class="sxs-lookup"><span data-stu-id="6f37e-108">Define a Voice Route</span></span>

  - <span data-ttu-id="6f37e-109">Habilitar usuarios para Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="6f37e-109">Enable Users for Enterprise Voice</span></span>

<div>

## <a name="create-a-trunk"></a><span data-ttu-id="6f37e-110">Crear un tronco</span><span class="sxs-lookup"><span data-stu-id="6f37e-110">Create a Trunk</span></span>

<span data-ttu-id="6f37e-111">Debe definir troncos en su implementación de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="6f37e-111">You must define trunks in your Enterprise Voice deployment.</span></span> <span data-ttu-id="6f37e-112">Para Location-Based el enrutamiento, debe crear una configuración de tronco por tronco.</span><span class="sxs-lookup"><span data-stu-id="6f37e-112">For Location-Based Routing, you must create a trunk configuration per trunk.</span></span> <span data-ttu-id="6f37e-113">Use el generador de topologías de Lync Server para definir los troncos y use el comando de Windows PowerShell de Lync Server, New-CsTrunkConfiguration o el panel de control de Lync Server para definir las configuraciones de tronco correspondientes.</span><span class="sxs-lookup"><span data-stu-id="6f37e-113">Use the Lync Server Topology Builder to define your trunks, and use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, or the Lync Server Control Panel to define the corresponding trunk configurations.</span></span> <span data-ttu-id="6f37e-114">Puede encontrar más información sobre cómo habilitar el enrutamiento de Location-Based en las configuraciones de tronco en la sección, habilitar el enrutamiento de Location-Based a troncos, en el tema sobre [Cómo habilitar el enrutamiento de Location-Based en Lync Server 2013](lync-server-2013-enabling-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="6f37e-114">More information on how to enable Location-Based Routing on trunk configurations can be found in the section, Enable Location-Based Routing to Trunks, in the topic, [Enabling Location-Based Routing in Lync Server 2013](lync-server-2013-enabling-location-based-routing.md).</span></span> <span data-ttu-id="6f37e-115">En este ejemplo, en la tabla siguiente se muestran los troncos que se usan en este escenario.</span><span class="sxs-lookup"><span data-stu-id="6f37e-115">For this example, the following table illustrates the trunks used in this scenario.</span></span>

<span data-ttu-id="6f37e-116">Para obtener más información, consulte [definir troncos adicionales en el generador de topologías en Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).</span><span class="sxs-lookup"><span data-stu-id="6f37e-116">For more information, see [Define additional trunks in Topology Builder in Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).</span></span>


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6f37e-117">Nombre del tronco</span><span class="sxs-lookup"><span data-stu-id="6f37e-117">Trunk name</span></span></th>
<th><span data-ttu-id="6f37e-118">Tipo de sistema</span><span class="sxs-lookup"><span data-stu-id="6f37e-118">System type</span></span></th>
<th><span data-ttu-id="6f37e-119">Nombre</span><span class="sxs-lookup"><span data-stu-id="6f37e-119">Name</span></span></th>
<th><span data-ttu-id="6f37e-120">Ubicación</span><span class="sxs-lookup"><span data-stu-id="6f37e-120">Location</span></span></th>
<th><span data-ttu-id="6f37e-121">Servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="6f37e-121">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6f37e-122">Tronco 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="6f37e-122">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="6f37e-123">Una puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="6f37e-123">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="6f37e-124">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="6f37e-124">DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="6f37e-125">Delhi</span><span class="sxs-lookup"><span data-stu-id="6f37e-125">Delhi</span></span></p></td>
<td><p><span data-ttu-id="6f37e-126">MS1</span><span class="sxs-lookup"><span data-stu-id="6f37e-126">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f37e-127">Tronco 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="6f37e-127">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="6f37e-128">Una puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="6f37e-128">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="6f37e-129">HYD-GW</span><span class="sxs-lookup"><span data-stu-id="6f37e-129">HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="6f37e-130">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="6f37e-130">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="6f37e-131">MS1</span><span class="sxs-lookup"><span data-stu-id="6f37e-131">MS1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f37e-132">Tronco 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="6f37e-132">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="6f37e-133">PBX</span><span class="sxs-lookup"><span data-stu-id="6f37e-133">PBX</span></span></p></td>
<td><p><span data-ttu-id="6f37e-134">DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="6f37e-134">DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="6f37e-135">Delhi</span><span class="sxs-lookup"><span data-stu-id="6f37e-135">Delhi</span></span></p></td>
<td><p><span data-ttu-id="6f37e-136">MS1</span><span class="sxs-lookup"><span data-stu-id="6f37e-136">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f37e-137">Tronco 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="6f37e-137">Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="6f37e-138">PBX</span><span class="sxs-lookup"><span data-stu-id="6f37e-138">PBX</span></span></p></td>
<td><p><span data-ttu-id="6f37e-139">HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="6f37e-139">HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="6f37e-140">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="6f37e-140">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="6f37e-141">MS1</span><span class="sxs-lookup"><span data-stu-id="6f37e-141">MS1</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="defines-voice-policies"></a><span data-ttu-id="6f37e-142">Define directivas de voz</span><span class="sxs-lookup"><span data-stu-id="6f37e-142">Defines Voice Policies</span></span>

<span data-ttu-id="6f37e-143">Debe definir directivas de voz para la implementación de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="6f37e-143">You must define voice policies for your Enterprise Voice deployment.</span></span> <span data-ttu-id="6f37e-144">Definir una directiva de voz para aplicar Location-Based restricciones de enrutamiento a un subconjunto de usuarios si sólo se requiere un subconjunto de ellas para usar Location-Based enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="6f37e-144">Define a Voice Policy to enforce Location-Based Routing restrictions to a subset of users if only a subset of them is required to use Location-Based Routing.</span></span> <span data-ttu-id="6f37e-145">En este ejemplo, la tabla siguiente muestra las directivas de voz usadas en este escenario.</span><span class="sxs-lookup"><span data-stu-id="6f37e-145">For this example, the following table illustrates the voice policies used in this scenario.</span></span> <span data-ttu-id="6f37e-146">En la tabla sólo se incluye la configuración específica de Location-Based enrutamiento para fines de ilustración.</span><span class="sxs-lookup"><span data-stu-id="6f37e-146">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="6f37e-147">Para obtener más información, vea [configuración de directivas de voz y registros de uso de RTC para autorizar características y privilegios de llamada en Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span><span class="sxs-lookup"><span data-stu-id="6f37e-147">For more information, see [Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="6f37e-148">Directiva de voz 1</span><span class="sxs-lookup"><span data-stu-id="6f37e-148">Voice policy 1</span></span></th>
<th><span data-ttu-id="6f37e-149">Directiva de voz 2</span><span class="sxs-lookup"><span data-stu-id="6f37e-149">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6f37e-150">IDENTIFICADOR de la Directiva de voz</span><span class="sxs-lookup"><span data-stu-id="6f37e-150">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="6f37e-151">Directiva de voz de Delhi</span><span class="sxs-lookup"><span data-stu-id="6f37e-151">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="6f37e-152">Directiva de voz Hyderabad</span><span class="sxs-lookup"><span data-stu-id="6f37e-152">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f37e-153">Usos de RTC</span><span class="sxs-lookup"><span data-stu-id="6f37e-153">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="6f37e-154">Uso de Delhi, PBX del uso, uso de HYD de PBX</span><span class="sxs-lookup"><span data-stu-id="6f37e-154">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="6f37e-155">Uso de Hyderabad, uso de HYD de PBX, PBX del uso</span><span class="sxs-lookup"><span data-stu-id="6f37e-155">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f37e-156">PreventPSTNTollBypass</span><span class="sxs-lookup"><span data-stu-id="6f37e-156">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="6f37e-157">False</span><span class="sxs-lookup"><span data-stu-id="6f37e-157">False</span></span></p></td>
<td><p><span data-ttu-id="6f37e-158">False</span><span class="sxs-lookup"><span data-stu-id="6f37e-158">False</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-voice-routes"></a><span data-ttu-id="6f37e-159">Definir rutas de voz</span><span class="sxs-lookup"><span data-stu-id="6f37e-159">Define Voice Routes</span></span>

<span data-ttu-id="6f37e-160">Debe definir rutas de voz para la implementación de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="6f37e-160">You must define voice routes for your Enterprise Voice deployment.</span></span> <span data-ttu-id="6f37e-161">En este ejemplo, la tabla siguiente muestra las rutas de voz usadas en este escenario.</span><span class="sxs-lookup"><span data-stu-id="6f37e-161">For this example, the following table illustrates the voice routes used in this scenario.</span></span> <span data-ttu-id="6f37e-162">En la tabla sólo se incluye la configuración específica de Location-Based enrutamiento para fines de ilustración.</span><span class="sxs-lookup"><span data-stu-id="6f37e-162">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="6f37e-163">Para obtener más información, consulte [configurar rutas de voz para llamadas salientes en Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span><span class="sxs-lookup"><span data-stu-id="6f37e-163">For more information, see [Configuring voice routes for outbound calls in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span></span>


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="6f37e-164">Ruta de voz 1</span><span class="sxs-lookup"><span data-stu-id="6f37e-164">Voice route 1</span></span></th>
<th><span data-ttu-id="6f37e-165">Ruta de voz 2</span><span class="sxs-lookup"><span data-stu-id="6f37e-165">Voice route 2</span></span></th>
<th><span data-ttu-id="6f37e-166">Ruta de voz 3</span><span class="sxs-lookup"><span data-stu-id="6f37e-166">Voice route 3</span></span></th>
<th><span data-ttu-id="6f37e-167">Ruta de voz 4</span><span class="sxs-lookup"><span data-stu-id="6f37e-167">Voice route 4</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6f37e-168">Nombre</span><span class="sxs-lookup"><span data-stu-id="6f37e-168">Name</span></span></p></td>
<td><p><span data-ttu-id="6f37e-169">Ruta de Delhi</span><span class="sxs-lookup"><span data-stu-id="6f37e-169">Delhi route</span></span></p></td>
<td><p><span data-ttu-id="6f37e-170">Ruta Hyderabad</span><span class="sxs-lookup"><span data-stu-id="6f37e-170">Hyderabad route</span></span></p></td>
<td><p><span data-ttu-id="6f37e-171">PBX del camino</span><span class="sxs-lookup"><span data-stu-id="6f37e-171">PBX Del route</span></span></p></td>
<td><p><span data-ttu-id="6f37e-172">Ruta de HYD de PBX</span><span class="sxs-lookup"><span data-stu-id="6f37e-172">PBX Hyd route</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f37e-173">Usos de RTC</span><span class="sxs-lookup"><span data-stu-id="6f37e-173">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="6f37e-174">Uso de Delhi</span><span class="sxs-lookup"><span data-stu-id="6f37e-174">Delhi usage</span></span></p></td>
<td><p><span data-ttu-id="6f37e-175">Uso de Hyderabad</span><span class="sxs-lookup"><span data-stu-id="6f37e-175">Hyderabad usage</span></span></p></td>
<td><p><span data-ttu-id="6f37e-176">PBX del uso</span><span class="sxs-lookup"><span data-stu-id="6f37e-176">PBX Del usage</span></span></p></td>
<td><p><span data-ttu-id="6f37e-177">Uso de HYD de PBX</span><span class="sxs-lookup"><span data-stu-id="6f37e-177">PBX Hyd usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f37e-178">Tronco</span><span class="sxs-lookup"><span data-stu-id="6f37e-178">Trunk</span></span></p></td>
<td><p><span data-ttu-id="6f37e-179">Tronco 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="6f37e-179">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="6f37e-180">Tronco 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="6f37e-180">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="6f37e-181">Tronco 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="6f37e-181">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="6f37e-182">Tronco 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="6f37e-182">Trunk 4 HYD-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-users-for-enterprise-voice"></a><span data-ttu-id="6f37e-183">Habilitar usuarios para Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="6f37e-183">Enable Users for Enterprise Voice</span></span>

<span data-ttu-id="6f37e-184">Habilite a los usuarios para la telefonía IP empresarial y asígneles una directiva de voz que haya definido previamente.</span><span class="sxs-lookup"><span data-stu-id="6f37e-184">Enable users for Enterprise Voice and assign them a voice policy you’ve previously defined.</span></span> <span data-ttu-id="6f37e-185">En este ejemplo, en la tabla siguiente se muestra la asignación que se usa en este escenario.</span><span class="sxs-lookup"><span data-stu-id="6f37e-185">For this example, the following table illustrates the assignment used in this scenario.</span></span> <span data-ttu-id="6f37e-186">En la tabla sólo se incluye la configuración específica de Location-Based enrutamiento para fines de ilustración.</span><span class="sxs-lookup"><span data-stu-id="6f37e-186">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="6f37e-187">Para obtener más información, consulte [enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="6f37e-187">For more information, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="6f37e-188">Usuarios ubicados en Delhi</span><span class="sxs-lookup"><span data-stu-id="6f37e-188">Users located in Delhi</span></span></th>
<th><span data-ttu-id="6f37e-189">Usuarios ubicados en Hyderabad</span><span class="sxs-lookup"><span data-stu-id="6f37e-189">Users located in Hyderabad</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6f37e-190">Directiva de voz asociada</span><span class="sxs-lookup"><span data-stu-id="6f37e-190">Associated voice policy</span></span></p></td>
<td><p><span data-ttu-id="6f37e-191">Directiva de voz de Delhi</span><span class="sxs-lookup"><span data-stu-id="6f37e-191">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="6f37e-192">Directiva de voz Hyderabad</span><span class="sxs-lookup"><span data-stu-id="6f37e-192">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f37e-193">Usuarios de muestra</span><span class="sxs-lookup"><span data-stu-id="6f37e-193">Sample users</span></span></p></td>
<td><p><span data-ttu-id="6f37e-194">DEL-LYNC-1, DEL-LYNC-2, DEL-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="6f37e-194">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
<td><p><span data-ttu-id="6f37e-195">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="6f37e-195">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6f37e-196">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6f37e-196">See Also</span></span>


[<span data-ttu-id="6f37e-197">Configuración del enrutamiento de Location-Based en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f37e-197">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

