---
title: 'Lync Server 2013: configuración de telefonía IP empresarial'
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
ms.openlocfilehash: 9d6bf9f79725f1f4812ac1e1c1c3c0e3217b939b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728940"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="3d064-102">Configurar la telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d064-102">Configuring Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d064-103">_**Última modificación del tema:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="3d064-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="3d064-104">Para implementar la telefonía IP empresarial, tendrá que configurar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3d064-104">To deploy Enterprise Voice, you’ll need to configure the following:</span></span>

  - <span data-ttu-id="3d064-105">Crear un tronco</span><span class="sxs-lookup"><span data-stu-id="3d064-105">Create a Trunk</span></span>

  - <span data-ttu-id="3d064-106">Definir una directiva de voz</span><span class="sxs-lookup"><span data-stu-id="3d064-106">Define a Voice Policy</span></span>

  - <span data-ttu-id="3d064-107">Definir una ruta de voz</span><span class="sxs-lookup"><span data-stu-id="3d064-107">Define a Voice Route</span></span>

  - <span data-ttu-id="3d064-108">Enable Users for Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="3d064-108">Enable Users for Enterprise Voice</span></span>

<div>

## <a name="create-a-trunk"></a><span data-ttu-id="3d064-109">Crear un tronco</span><span class="sxs-lookup"><span data-stu-id="3d064-109">Create a Trunk</span></span>

<span data-ttu-id="3d064-110">Debe definir los troncos en su implementación de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="3d064-110">You must define trunks in your Enterprise Voice deployment.</span></span> <span data-ttu-id="3d064-111">Para el enrutamiento basado en la ubicación, debe crear una configuración troncal por tronco.</span><span class="sxs-lookup"><span data-stu-id="3d064-111">For Location-Based Routing, you must create a trunk configuration per trunk.</span></span> <span data-ttu-id="3d064-112">Use el generador de topología de Lync Server para definir sus troncos y use el comando de Windows PowerShell de Lync Server, New-CsTrunkConfiguration o el panel de control de Lync Server para definir las configuraciones de troncal correspondientes.</span><span class="sxs-lookup"><span data-stu-id="3d064-112">Use the Lync Server Topology Builder to define your trunks, and use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, or the Lync Server Control Panel to define the corresponding trunk configurations.</span></span> <span data-ttu-id="3d064-113">Para obtener más información sobre cómo habilitar el enrutamiento basado en la ubicación en las configuraciones troncales, vaya a la sección habilitar el enrutamiento basado en la ubicación para los troncos, en el tema [Habilitar el enrutamiento basado en la ubicación en Lync Server 2013](lync-server-2013-enabling-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="3d064-113">More information on how to enable Location-Based Routing on trunk configurations can be found in the section, Enable Location-Based Routing to Trunks, in the topic, [Enabling Location-Based Routing in Lync Server 2013](lync-server-2013-enabling-location-based-routing.md).</span></span> <span data-ttu-id="3d064-114">En este ejemplo, la tabla siguiente muestra las troncos que se usan en este escenario.</span><span class="sxs-lookup"><span data-stu-id="3d064-114">For this example, the following table illustrates the trunks used in this scenario.</span></span>

<span data-ttu-id="3d064-115">Para obtener más información, vea [definir más troncos en el generador de topología en Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).</span><span class="sxs-lookup"><span data-stu-id="3d064-115">For more information, see [Define additional trunks in Topology Builder in Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).</span></span>


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
<th><span data-ttu-id="3d064-116">Nombre del tronco</span><span class="sxs-lookup"><span data-stu-id="3d064-116">Trunk name</span></span></th>
<th><span data-ttu-id="3d064-117">Tipo de sistema</span><span class="sxs-lookup"><span data-stu-id="3d064-117">System type</span></span></th>
<th><span data-ttu-id="3d064-118">Nombre</span><span class="sxs-lookup"><span data-stu-id="3d064-118">Name</span></span></th>
<th><span data-ttu-id="3d064-119">Ubicación</span><span class="sxs-lookup"><span data-stu-id="3d064-119">Location</span></span></th>
<th><span data-ttu-id="3d064-120">Servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="3d064-120">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3d064-121">Tronco 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="3d064-121">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="3d064-122">Puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="3d064-122">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="3d064-123">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="3d064-123">DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="3d064-124">Delhi</span><span class="sxs-lookup"><span data-stu-id="3d064-124">Delhi</span></span></p></td>
<td><p><span data-ttu-id="3d064-125">MS1</span><span class="sxs-lookup"><span data-stu-id="3d064-125">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3d064-126">Troncal 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="3d064-126">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="3d064-127">Puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="3d064-127">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="3d064-128">HYD-GW</span><span class="sxs-lookup"><span data-stu-id="3d064-128">HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="3d064-129">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="3d064-129">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="3d064-130">MS1</span><span class="sxs-lookup"><span data-stu-id="3d064-130">MS1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3d064-131">Troncal 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="3d064-131">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="3d064-132">PBX</span><span class="sxs-lookup"><span data-stu-id="3d064-132">PBX</span></span></p></td>
<td><p><span data-ttu-id="3d064-133">DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="3d064-133">DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="3d064-134">Delhi</span><span class="sxs-lookup"><span data-stu-id="3d064-134">Delhi</span></span></p></td>
<td><p><span data-ttu-id="3d064-135">MS1</span><span class="sxs-lookup"><span data-stu-id="3d064-135">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3d064-136">Troncal 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="3d064-136">Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="3d064-137">PBX</span><span class="sxs-lookup"><span data-stu-id="3d064-137">PBX</span></span></p></td>
<td><p><span data-ttu-id="3d064-138">HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="3d064-138">HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="3d064-139">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="3d064-139">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="3d064-140">MS1</span><span class="sxs-lookup"><span data-stu-id="3d064-140">MS1</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="defines-voice-policies"></a><span data-ttu-id="3d064-141">Define directivas de voz</span><span class="sxs-lookup"><span data-stu-id="3d064-141">Defines Voice Policies</span></span>

<span data-ttu-id="3d064-142">Debe definir directivas de voz para su implementación de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="3d064-142">You must define voice policies for your Enterprise Voice deployment.</span></span> <span data-ttu-id="3d064-143">Defina una directiva de voz para aplicar restricciones de enrutamiento basado en la ubicación a un subconjunto de usuarios si solo se necesita un subconjunto de ellas para usar el enrutamiento basado en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="3d064-143">Define a Voice Policy to enforce Location-Based Routing restrictions to a subset of users if only a subset of them is required to use Location-Based Routing.</span></span> <span data-ttu-id="3d064-144">En este ejemplo, la tabla siguiente muestra las directivas de voz que se usan en este escenario.</span><span class="sxs-lookup"><span data-stu-id="3d064-144">For this example, the following table illustrates the voice policies used in this scenario.</span></span> <span data-ttu-id="3d064-145">En la tabla solo se incluyen los valores específicos del enrutamiento basado en la ubicación con fines de ilustración.</span><span class="sxs-lookup"><span data-stu-id="3d064-145">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="3d064-146">Para obtener más información, vea [configuración de directivas de voz y registros de uso de RTC para autorizar llamadas y características de Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span><span class="sxs-lookup"><span data-stu-id="3d064-146">For more information, see [Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="3d064-147">Política de voz 1</span><span class="sxs-lookup"><span data-stu-id="3d064-147">Voice policy 1</span></span></th>
<th><span data-ttu-id="3d064-148">Política de voz 2</span><span class="sxs-lookup"><span data-stu-id="3d064-148">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3d064-149">IDENTIFICADOR de la Directiva de voz</span><span class="sxs-lookup"><span data-stu-id="3d064-149">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="3d064-150">Directiva de voz de Delhi</span><span class="sxs-lookup"><span data-stu-id="3d064-150">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="3d064-151">Política de voz de Hyderabad</span><span class="sxs-lookup"><span data-stu-id="3d064-151">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3d064-152">Usos de RTC</span><span class="sxs-lookup"><span data-stu-id="3d064-152">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="3d064-153">Uso de la Delhi, PBX del uso, uso de HYD de PBX</span><span class="sxs-lookup"><span data-stu-id="3d064-153">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="3d064-154">Uso de Hyderabad, uso de HYD de PBX, PBX del uso</span><span class="sxs-lookup"><span data-stu-id="3d064-154">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3d064-155">PreventPSTNTollBypass</span><span class="sxs-lookup"><span data-stu-id="3d064-155">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="3d064-156">Falso</span><span class="sxs-lookup"><span data-stu-id="3d064-156">False</span></span></p></td>
<td><p><span data-ttu-id="3d064-157">Falso</span><span class="sxs-lookup"><span data-stu-id="3d064-157">False</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-voice-routes"></a><span data-ttu-id="3d064-158">Definir rutas de voz</span><span class="sxs-lookup"><span data-stu-id="3d064-158">Define Voice Routes</span></span>

<span data-ttu-id="3d064-159">Debe definir rutas de voz para su implementación de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="3d064-159">You must define voice routes for your Enterprise Voice deployment.</span></span> <span data-ttu-id="3d064-160">En este ejemplo, la tabla siguiente muestra las rutas de voz usadas en este escenario.</span><span class="sxs-lookup"><span data-stu-id="3d064-160">For this example, the following table illustrates the voice routes used in this scenario.</span></span> <span data-ttu-id="3d064-161">En la tabla solo se incluyen los valores específicos del enrutamiento basado en la ubicación con fines de ilustración.</span><span class="sxs-lookup"><span data-stu-id="3d064-161">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="3d064-162">Para obtener más información, consulte [configuración de rutas de voz para llamadas salientes en Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span><span class="sxs-lookup"><span data-stu-id="3d064-162">For more information, see [Configuring voice routes for outbound calls in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span></span>


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
<th><span data-ttu-id="3d064-163">Ruta de voz 1</span><span class="sxs-lookup"><span data-stu-id="3d064-163">Voice route 1</span></span></th>
<th><span data-ttu-id="3d064-164">Ruta de voz 2</span><span class="sxs-lookup"><span data-stu-id="3d064-164">Voice route 2</span></span></th>
<th><span data-ttu-id="3d064-165">Ruta de voz 3</span><span class="sxs-lookup"><span data-stu-id="3d064-165">Voice route 3</span></span></th>
<th><span data-ttu-id="3d064-166">Ruta de voz 4</span><span class="sxs-lookup"><span data-stu-id="3d064-166">Voice route 4</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3d064-167">Nombre</span><span class="sxs-lookup"><span data-stu-id="3d064-167">Name</span></span></p></td>
<td><p><span data-ttu-id="3d064-168">Ruta de Delhi</span><span class="sxs-lookup"><span data-stu-id="3d064-168">Delhi route</span></span></p></td>
<td><p><span data-ttu-id="3d064-169">Ruta de Hyderabad</span><span class="sxs-lookup"><span data-stu-id="3d064-169">Hyderabad route</span></span></p></td>
<td><p><span data-ttu-id="3d064-170">PBX del camino</span><span class="sxs-lookup"><span data-stu-id="3d064-170">PBX Del route</span></span></p></td>
<td><p><span data-ttu-id="3d064-171">Ruta de HYD PBX</span><span class="sxs-lookup"><span data-stu-id="3d064-171">PBX Hyd route</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3d064-172">Usos de RTC</span><span class="sxs-lookup"><span data-stu-id="3d064-172">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="3d064-173">Uso de Delhi</span><span class="sxs-lookup"><span data-stu-id="3d064-173">Delhi usage</span></span></p></td>
<td><p><span data-ttu-id="3d064-174">Uso de Hyderabad</span><span class="sxs-lookup"><span data-stu-id="3d064-174">Hyderabad usage</span></span></p></td>
<td><p><span data-ttu-id="3d064-175">Uso de PBX</span><span class="sxs-lookup"><span data-stu-id="3d064-175">PBX Del usage</span></span></p></td>
<td><p><span data-ttu-id="3d064-176">Uso de HYD de PBX</span><span class="sxs-lookup"><span data-stu-id="3d064-176">PBX Hyd usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3d064-177">Tronco</span><span class="sxs-lookup"><span data-stu-id="3d064-177">Trunk</span></span></p></td>
<td><p><span data-ttu-id="3d064-178">Tronco 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="3d064-178">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="3d064-179">Troncal 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="3d064-179">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="3d064-180">Troncal 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="3d064-180">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="3d064-181">Troncal 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="3d064-181">Trunk 4 HYD-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-users-for-enterprise-voice"></a><span data-ttu-id="3d064-182">Enable Users for Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="3d064-182">Enable Users for Enterprise Voice</span></span>

<span data-ttu-id="3d064-183">Habilitar a los usuarios para la telefonía IP empresarial y asignarles una directiva de voz que haya definido previamente.</span><span class="sxs-lookup"><span data-stu-id="3d064-183">Enable users for Enterprise Voice and assign them a voice policy you’ve previously defined.</span></span> <span data-ttu-id="3d064-184">En este ejemplo, la tabla siguiente muestra la asignación que se usa en este escenario.</span><span class="sxs-lookup"><span data-stu-id="3d064-184">For this example, the following table illustrates the assignment used in this scenario.</span></span> <span data-ttu-id="3d064-185">En la tabla solo se incluyen los valores específicos del enrutamiento basado en la ubicación con fines de ilustración.</span><span class="sxs-lookup"><span data-stu-id="3d064-185">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="3d064-186">Para obtener más información, consulte [Habilitar usuarios para telefonía IP empresarial en Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="3d064-186">For more information, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="3d064-187">Usuarios ubicados en Delhi</span><span class="sxs-lookup"><span data-stu-id="3d064-187">Users located in Delhi</span></span></th>
<th><span data-ttu-id="3d064-188">Usuarios que se encuentran en Hyderabad</span><span class="sxs-lookup"><span data-stu-id="3d064-188">Users located in Hyderabad</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3d064-189">Directiva de voz asociada</span><span class="sxs-lookup"><span data-stu-id="3d064-189">Associated voice policy</span></span></p></td>
<td><p><span data-ttu-id="3d064-190">Directiva de voz de Delhi</span><span class="sxs-lookup"><span data-stu-id="3d064-190">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="3d064-191">Política de voz de Hyderabad</span><span class="sxs-lookup"><span data-stu-id="3d064-191">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3d064-192">Usuarios de muestra</span><span class="sxs-lookup"><span data-stu-id="3d064-192">Sample users</span></span></p></td>
<td><p><span data-ttu-id="3d064-193">DE-LYNC-1, DE-LYNC-2, DE-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="3d064-193">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
<td><p><span data-ttu-id="3d064-194">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="3d064-194">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3d064-195">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d064-195">See Also</span></span>


[<span data-ttu-id="3d064-196">Configurar el enrutamiento basado en ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d064-196">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

