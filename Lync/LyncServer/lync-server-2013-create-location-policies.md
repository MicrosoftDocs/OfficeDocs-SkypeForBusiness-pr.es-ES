---
title: 'Lync Server 2013: crear directivas de ubicación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create location policies
ms:assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413006(v=OCS.15)
ms:contentKeyID: 48185794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55c10244bb3a70f7218dc3967e7f4f134048024f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726320"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-location-policies-in-lync-server-2013"></a><span data-ttu-id="93321-102">Crear directivas de ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93321-102">Create location policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93321-103">_**Última modificación del tema:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="93321-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="93321-104">Lync Server usa una directiva de ubicación para habilitar los clientes de Lync para E9-1-1 durante el registro de clientes.</span><span class="sxs-lookup"><span data-stu-id="93321-104">Lync Server uses a location policy to enable Lync clients for E9-1-1 during client registration.</span></span> <span data-ttu-id="93321-105">Una directiva de ubicación contiene la configuración que define cómo se implementará E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="93321-105">A location policy contains the settings that define how E9-1-1 will be implemented.</span></span>

<span data-ttu-id="93321-p102">La directiva de ubicación global puede editarse y crear otras directivas de ubicación con etiqueta. Un cliente obtiene una directiva global si no se ubica en una subred que tenga asociada una directiva de ubicación o, bien, si el cliente no tiene asignada directamente una directiva de ubicación. Las directivas con etiquetas se asignan a subredes o usuarios.  </span><span class="sxs-lookup"><span data-stu-id="93321-p102">You can edit the global location policy and create new tagged location policies. A client obtains a global policy when it is not located within a subnet with an associated location policy, or when the client has not been directly assigned a location policy. Tagged policies are assigned to subnets or users.</span></span>

<span data-ttu-id="93321-109">Para crear una directiva de ubicación, debe usar una cuenta que pertenezca al grupo RTCUniversalServerAdmins, o bien que tenga el rol administrativo CsVoiceAdministrator o derechos y permisos de administrador equivalentes.</span><span class="sxs-lookup"><span data-stu-id="93321-109">To create a location policy, you must use an account that is a member of the RTCUniversalServerAdmins group, or is a member of the CsVoiceAdministrator administrative role, or has equivalent administrator rights and permissions.</span></span>

<span data-ttu-id="93321-110">Para obtener una descripción completa de las directivas de ubicación, consulte [definir la Directiva de ubicación de Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="93321-110">For a complete description of Location policies, see [Defining the location policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span></span> <span data-ttu-id="93321-111">Cmdlets de este procedimiento use una directiva de ubicación definida con los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="93321-111">Cmdlets in this procedure use a location policy defined using the following values:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="93321-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="93321-112">Element</span></span></th>
<th><span data-ttu-id="93321-113">Valor</span><span class="sxs-lookup"><span data-stu-id="93321-113">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="93321-114">EnhancedEmergencyServicesEnabled</span><span class="sxs-lookup"><span data-stu-id="93321-114">EnhancedEmergencyServicesEnabled</span></span></p></td>
<td><p><span data-ttu-id="93321-115"><strong>True</strong></span><span class="sxs-lookup"><span data-stu-id="93321-115"><strong>True</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93321-116">LocationRequired</span><span class="sxs-lookup"><span data-stu-id="93321-116">LocationRequired</span></span></p></td>
<td><p><span data-ttu-id="93321-117"><strong>Disclaimer</strong></span><span class="sxs-lookup"><span data-stu-id="93321-117"><strong>Disclaimer</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93321-118">EnhancedEmergencyServiceDisclaimer</span><span class="sxs-lookup"><span data-stu-id="93321-118">EnhancedEmergencyServiceDisclaimer</span></span></p></td>
<td><p><span data-ttu-id="93321-p104">La directiva de compañía le exige que indique una ubicación. Si no define una ubicación, los servicios de emergencia no podrán localizarle en caso de emergencia. Especifique una ubicación.</span><span class="sxs-lookup"><span data-stu-id="93321-p104">Your company policy requires you to set a location. If you do not set a location, emergency services will not be able to locate you in an emergency. Please set a location.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93321-122">UseLocationForE911Only</span><span class="sxs-lookup"><span data-stu-id="93321-122">UseLocationForE911Only</span></span></p></td>
<td><p><span data-ttu-id="93321-123"><strong>False</strong></span><span class="sxs-lookup"><span data-stu-id="93321-123"><strong>False</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93321-124">PstnUsage</span><span class="sxs-lookup"><span data-stu-id="93321-124">PstnUsage</span></span></p></td>
<td><p><span data-ttu-id="93321-125"><strong>EmergencyUsage</strong></span><span class="sxs-lookup"><span data-stu-id="93321-125"><strong>EmergencyUsage</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93321-126">EmergencyDialString</span><span class="sxs-lookup"><span data-stu-id="93321-126">EmergencyDialString</span></span></p></td>
<td><p><span data-ttu-id="93321-127"><strong>911</strong></span><span class="sxs-lookup"><span data-stu-id="93321-127"><strong>911</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93321-128">EmergencyDialMask</span><span class="sxs-lookup"><span data-stu-id="93321-128">EmergencyDialMask</span></span></p></td>
<td><p><span data-ttu-id="93321-129"><strong>112</strong></span><span class="sxs-lookup"><span data-stu-id="93321-129"><strong>112</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93321-130">NotificationUri</span><span class="sxs-lookup"><span data-stu-id="93321-130">NotificationUri</span></span></p></td>
<td><p><span data-ttu-id="93321-131"><strong>sip:security@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="93321-131"><strong>sip:security@litwareinc.com</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93321-132">ConferenceUri</span><span class="sxs-lookup"><span data-stu-id="93321-132">ConferenceUri</span></span></p></td>
<td><p><span data-ttu-id="93321-133"><strong>sip:+14255550123@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="93321-133"><strong>sip:+14255550123@litwareinc.com</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93321-134">ConferenceMode</span><span class="sxs-lookup"><span data-stu-id="93321-134">ConferenceMode</span></span></p></td>
<td><p><span data-ttu-id="93321-135"><strong>twoway</strong></span><span class="sxs-lookup"><span data-stu-id="93321-135"><strong>twoway</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93321-136">LocationRefreshInterval</span><span class="sxs-lookup"><span data-stu-id="93321-136">LocationRefreshInterval</span></span></p></td>
<td><p><span data-ttu-id="93321-137"><strong>2</strong></span><span class="sxs-lookup"><span data-stu-id="93321-137"><strong>2</strong></span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="93321-138">Para obtener más información sobre cómo trabajar con directivas de ubicación, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="93321-138">For details about working with location policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="93321-139">New-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="93321-139">New-CsLocationPolicy</span></span>

  - <span data-ttu-id="93321-140">Get-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="93321-140">Get-CsLocationPolicy</span></span>

  - <span data-ttu-id="93321-141">Set-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="93321-141">Set-CsLocationPolicy</span></span>

  - <span data-ttu-id="93321-142">Remove-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="93321-142">Remove-CsLocationPolicy</span></span>

  - <span data-ttu-id="93321-143">Grant-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="93321-143">Grant-CsLocationPolicy</span></span>

<div>

## <a name="to-create-location-policies"></a><span data-ttu-id="93321-144">Para crear directivas de ubicación</span><span class="sxs-lookup"><span data-stu-id="93321-144">To create location policies</span></span>

1.  <span data-ttu-id="93321-145">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="93321-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="93321-146">CsLocationPolicy no funcionará correctamente si el valor de <STRONG>PstnUsage</STRONG> no está ya presente en la lista global de PstnUsages.</span><span class="sxs-lookup"><span data-stu-id="93321-146">CsLocationPolicy will fail if the setting for <STRONG>PstnUsage</STRONG> is not already in the Global list of PstnUsages.</span></span>

    
    </div>

2.  <span data-ttu-id="93321-147">También puede ejecutar el cmdlet siguiente para editar la directiva de ubicación global:</span><span class="sxs-lookup"><span data-stu-id="93321-147">Optionally, run the following cmdlet to edit the global Location Policy:</span></span>
    
        Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2

3.  <span data-ttu-id="93321-148">Ejecute el cmdlet siguiente para crear una directiva de ubicación con etiqueta.</span><span class="sxs-lookup"><span data-stu-id="93321-148">Run the following to create a tagged Location Policy.</span></span>
    
        New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2

4.  <span data-ttu-id="93321-149">Ejecute el cmdlet siguiente para aplicar la directiva de ubicación con etiqueta que se ha creado en el paso 3 en una directiva de usuario.</span><span class="sxs-lookup"><span data-stu-id="93321-149">Run the following cmdlet to apply the tagged Location Policy created in step 3 to a user policy.</span></span>
    
        (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond

</div>

</div>

<span> </span>

</div>

</div>

</div>

