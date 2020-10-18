---
title: 'Lync Server 2013: proceso de implementación del estacionamiento de llamadas'
description: 'Lync Server 2013: proceso de implementación del estacionamiento de llamadas.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Call Park
ms:assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398283(v=OCS.15)
ms:contentKeyID: 48183586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 149252d39ba3fc0c552900c87e453c60e1651a08
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575716"
---
# <a name="deployment-process-for-call-park-in-lync-server-2013"></a><span data-ttu-id="d80d0-103">Proceso de implementación del estacionamiento de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d80d0-103">Deployment process for Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d80d0-104">_**Última modificación del tema:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="d80d0-104">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="d80d0-105">En esta sección se proporciona información general sobre los pasos necesarios para implementar la aplicación de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d80d0-105">This section provides an overview of the steps involved in deploying the Call Park application.</span></span> <span data-ttu-id="d80d0-106">Debe implementar Enterprise Edition o Standard Edition con Enterprise Voice antes de configurar el estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d80d0-106">You must deploy Enterprise Edition or Standard Edition with Enterprise Voice before you configure Call Park.</span></span> <span data-ttu-id="d80d0-107">Los componentes requeridos por el estacionamiento de llamadas se instalan y habilitan al implementar la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="d80d0-107">The components required by Call Park are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="call-park-deployment-process"></a><span data-ttu-id="d80d0-108">Proceso de implementación de estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="d80d0-108">Call Park Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d80d0-109">Fase</span><span class="sxs-lookup"><span data-stu-id="d80d0-109">Phase</span></span></th>
<th><span data-ttu-id="d80d0-110">Pasos</span><span class="sxs-lookup"><span data-stu-id="d80d0-110">Steps</span></span></th>
<th><span data-ttu-id="d80d0-111">Grupos y roles necesarios</span><span class="sxs-lookup"><span data-stu-id="d80d0-111">Required groups and roles</span></span></th>
<th><span data-ttu-id="d80d0-112">Documentación de implementación</span><span class="sxs-lookup"><span data-stu-id="d80d0-112">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d80d0-113">Configurar los intervalos de órbitas del estacionamiento de llamadas en la tabla de órbitas</span><span class="sxs-lookup"><span data-stu-id="d80d0-113">Configure the call park orbit ranges in the orbit table</span></span></p></td>
<td><p><span data-ttu-id="d80d0-114">Use el panel de control de Lync Server o el cmdlet <strong>New-CSCallParkOrbit</strong> para crear intervalos de órbitas en la tabla de órbitas de estacionamiento de llamadas y asociarlos con el servicio de aplicación que hospeda la aplicación de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d80d0-114">Use Lync Server Control Panel or the <strong>New-CSCallParkOrbit</strong> cmdlet to create the orbit ranges in the call park orbit table and associate them with the Application service that hosts the Call Park application.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="d80d0-p102">A fin de lograr una integración sin fisuras con los planes de marcado existentes, los intervalos de órbitas se suelen configurar como un bloque de extensiones virtuales. En la tabla de órbitas de estacionamiento de llamadas no se pueden asignar números de llamada directa a la extensión (DID) como números de órbita.</span><span class="sxs-lookup"><span data-stu-id="d80d0-p102">For seamless integration with existing dial plans, orbit ranges are typically configured as a block of virtual extensions. Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the call park orbit table is not supported.</span></span>


</div></td>
<td><p><span data-ttu-id="d80d0-117">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="d80d0-117">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="d80d0-118">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="d80d0-118">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="d80d0-119">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="d80d0-119">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="d80d0-120">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="d80d0-120">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="d80d0-121"><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">Crear o modificar un intervalo de órbitas de estacionamiento de llamadas en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d80d0-121"><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">Create or modify a Call Park orbit range in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d80d0-122">Configurar opciones de estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="d80d0-122">Configure Call Park settings</span></span></p></td>
<td><p><span data-ttu-id="d80d0-123">Use el cmdlet <strong>set-CsCpsConfiguration</strong> para configurar las opciones de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d80d0-123">Use the <strong>Set-CsCpsConfiguration</strong> cmdlet to configure Call Park settings.</span></span> <span data-ttu-id="d80d0-124">Como mínimo, se recomienda configurar la opción <strong>OnTimeoutURI</strong> para configurar el destino de reserva que se usará cuando se agote el tiempo de espera de una llamada estacionada. También puede configurar las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="d80d0-124">At a minimum, we recommend that you configure the <strong>OnTimeoutURI</strong> option to configure the fallback destination to use when a parked call times out. You can also configure the following settings:</span></span></p>
<ul>
<li><p><span data-ttu-id="d80d0-125"><strong>EnableMusicOnHold</strong> (opcional), con la que se habilita o deshabilita las música en espera.</span><span class="sxs-lookup"><span data-stu-id="d80d0-125">(Optional) <strong>EnableMusicOnHold</strong> to enable or disable music on hold.</span></span></p></li>
<li><p><span data-ttu-id="d80d0-126"><strong>MaxCallPickupAttempts</strong> (opcional), que determina el número de veces que una llamada estacionada llama al teléfono de destino antes de reenviar la llamada al URI (identificador uniforme de recursos) de reserva.</span><span class="sxs-lookup"><span data-stu-id="d80d0-126">(Optional) <strong>MaxCallPickupAttempts</strong> to determine the number of times a parked call rings back to the answering phone before forwarding the call to the fallback Uniform Resource Identifier (URI).</span></span></p></li>
<li><p><span data-ttu-id="d80d0-127"><strong>CallPickupTimeoutThreshold</strong> (opcional), que determina la cantidad de tiempo que transcurre desde que una llamada se aparca hasta que vuelve a llamar al teléfono que recibió la llamada.</span><span class="sxs-lookup"><span data-stu-id="d80d0-127">(Optional) <strong>CallPickupTimeoutThreshold</strong> to determine the amount of time that elapses after a call has been parked before it rings back to the phone where the call was answered.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="d80d0-128">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="d80d0-128">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="d80d0-129">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="d80d0-129">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="d80d0-130">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="d80d0-130">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="d80d0-131">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="d80d0-131">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="d80d0-132"><a href="lync-server-2013-configure-call-park-settings.md">Configurar las opciones del estacionamiento de llamadas en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d80d0-132"><a href="lync-server-2013-configure-call-park-settings.md">Configure Call Park settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d80d0-133">De manera opcional, personalice la música en espera</span><span class="sxs-lookup"><span data-stu-id="d80d0-133">Optionally, customize the music on hold</span></span></p></td>
<td><p><span data-ttu-id="d80d0-134">Use el cmdlet <strong>Set-CsCallParkServiceMusicOnHoldFile</strong> para personalizar y cargar un archivo de audio en caso de que no desee usar la música en espera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d80d0-134">Use the <strong>Set-CsCallParkServiceMusicOnHoldFile</strong> cmdlet to customize and upload an audio file, if you don't want to use the default music on hold.</span></span></p></td>
<td><p><span data-ttu-id="d80d0-135">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="d80d0-135">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="d80d0-136">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="d80d0-136">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="d80d0-137">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="d80d0-137">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="d80d0-138">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="d80d0-138">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="d80d0-139"><a href="lync-server-2013-customize-call-park-music-on-hold.md">Personalizar la música de estacionamiento de llamadas en espera en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d80d0-139"><a href="lync-server-2013-customize-call-park-music-on-hold.md">Customize Call Park music on hold in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d80d0-140">Configurar la Directiva de voz para habilitar el estacionamiento de llamadas para los usuarios</span><span class="sxs-lookup"><span data-stu-id="d80d0-140">Configure voice policy to enable Call Park for users</span></span></p></td>
<td><p><span data-ttu-id="d80d0-141">Use el panel de control de Lync Server o el cmdlet <strong>set-CSVoicePolicy</strong> con la opción <strong>EnableCallPark</strong> para habilitar el estacionamiento de llamadas para los usuarios en la Directiva de voz.</span><span class="sxs-lookup"><span data-stu-id="d80d0-141">Use Lync Server Control Panel or the <strong>Set-CSVoicePolicy</strong> cmdlet with the <strong>EnableCallPark</strong> option to enable Call Park for users in voice policy.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="d80d0-142">De forma predeterminada, el estacionamiento de llamadas está deshabilitado para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="d80d0-142">By default, Call Park is disabled for all users.</span></span>


</div>
<div>

> [!NOTE]  
> <span data-ttu-id="d80d0-143">Si existen varias directivas de voz, asegúrese de que la propiedad EnableCallPark se ha definido en todas ellas, no solo en la predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d80d0-143">If you have multiple voice policies, make sure the EnableCallPark property is set for each voice policy, not just for the default policy.</span></span>


</div></td>
<td><p><span data-ttu-id="d80d0-144">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="d80d0-144">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="d80d0-145">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="d80d0-145">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="d80d0-146">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="d80d0-146">CsUserAdministrator</span></span></p>
<p><span data-ttu-id="d80d0-147">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="d80d0-147">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="d80d0-148"><a href="lync-server-2013-enable-call-park-for-users.md">Habilitar el estacionamiento de llamadas para los usuarios en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d80d0-148"><a href="lync-server-2013-enable-call-park-for-users.md">Enable Call Park for users in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d80d0-149">Comprobar las reglas de normalización para el estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="d80d0-149">Verify normalization rules for Call Park</span></span></p></td>
<td><p><span data-ttu-id="d80d0-p104">Las órbitas de estacionamiento de llamadas no deben estar normalizadas. Por lo tanto, compruebe que las reglas de normalización no contemplan ninguno de los intervalos de órbitas existentes. Si procede, cree más reglas de normalización con objeto de evitar que las órbitas se normalicen.</span><span class="sxs-lookup"><span data-stu-id="d80d0-p104">Call park orbits must not be normalized. Verify that your normalization rules do not include any of your orbit ranges. If necessary, create additional normalization rules to prevent orbits being normalized.</span></span></p></td>
<td><p><span data-ttu-id="d80d0-153">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="d80d0-153">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="d80d0-154">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="d80d0-154">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="d80d0-155">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="d80d0-155">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="d80d0-156">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="d80d0-156">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="d80d0-157"><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">Comprobar reglas de normalización para el estacionamiento de llamadas en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d80d0-157"><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">Verify normalization rules for Call Park in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d80d0-158">Comprobar la implementación del estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="d80d0-158">Verify your Call Park deployment</span></span></p></td>
<td><p><span data-ttu-id="d80d0-159">Pruebe el estacionamiento y la recuperación de llamadas para asegurarse de que la configuración funciona según lo esperado.</span><span class="sxs-lookup"><span data-stu-id="d80d0-159">Test parking and retrieving calls to make sure that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="d80d0-160"><a href="lync-server-2013-optional-verify-call-park-deployment.md">Opcional Comprobar la implementación del estacionamiento de llamadas en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d80d0-160"><a href="lync-server-2013-optional-verify-call-park-deployment.md">(Optional) Verify Call Park deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

