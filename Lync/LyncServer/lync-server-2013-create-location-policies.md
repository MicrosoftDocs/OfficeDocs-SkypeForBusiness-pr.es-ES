---
title: 'Lync Server 2013: crear directivas de ubicación'
description: 'Lync Server 2013: crear directivas de ubicación.'
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
ms.openlocfilehash: 464ea9893890ab6185f180434e2dad13818123d1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562266"
---
# <a name="create-location-policies-in-lync-server-2013"></a><span data-ttu-id="f7a58-103">Crear directivas de ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7a58-103">Create location policies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7a58-104">_**Última modificación del tema:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="f7a58-104">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="f7a58-105">Lync Server usa una directiva de ubicación para habilitar clientes de Lync para E9-1-1 durante el registro de clientes.</span><span class="sxs-lookup"><span data-stu-id="f7a58-105">Lync Server uses a location policy to enable Lync clients for E9-1-1 during client registration.</span></span> <span data-ttu-id="f7a58-106">Una directiva de ubicación contiene la configuración que define cómo se implementará E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="f7a58-106">A location policy contains the settings that define how E9-1-1 will be implemented.</span></span>

<span data-ttu-id="f7a58-107">Puede editar la Directiva de ubicación global y crear nuevas directivas de ubicación con etiqueta.</span><span class="sxs-lookup"><span data-stu-id="f7a58-107">You can edit the global location policy and create new tagged location policies.</span></span> <span data-ttu-id="f7a58-108">Un cliente obtiene una directiva global cuando no se encuentra en una subred con una directiva de ubicación asociada o cuando no se ha asignado directamente una directiva de ubicación al cliente.</span><span class="sxs-lookup"><span data-stu-id="f7a58-108">A client obtains a global policy when it is not located within a subnet with an associated location policy, or when the client has not been directly assigned a location policy.</span></span> <span data-ttu-id="f7a58-109">Las directivas etiquetadas se asignan a subredes o usuarios.</span><span class="sxs-lookup"><span data-stu-id="f7a58-109">Tagged policies are assigned to subnets or users.</span></span>

<span data-ttu-id="f7a58-110">Para crear una directiva de ubicación, debe usar una cuenta que sea miembro del grupo RTCUniversalServerAdmins o que sea miembro del rol administrativo CsVoiceAdministrator o que tenga derechos y permisos de administrador equivalentes.</span><span class="sxs-lookup"><span data-stu-id="f7a58-110">To create a location policy, you must use an account that is a member of the RTCUniversalServerAdmins group, or is a member of the CsVoiceAdministrator administrative role, or has equivalent administrator rights and permissions.</span></span>

<span data-ttu-id="f7a58-111">Para obtener una descripción completa de las directivas de ubicación, consulte [Defining The location Policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="f7a58-111">For a complete description of Location policies, see [Defining the location policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span></span> <span data-ttu-id="f7a58-112">Los cmdlets de este procedimiento usan una directiva de ubicación definida con los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="f7a58-112">Cmdlets in this procedure use a location policy defined using the following values:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f7a58-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="f7a58-113">Element</span></span></th>
<th><span data-ttu-id="f7a58-114">Valor</span><span class="sxs-lookup"><span data-stu-id="f7a58-114">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f7a58-115">EnhancedEmergencyServicesEnabled</span><span class="sxs-lookup"><span data-stu-id="f7a58-115">EnhancedEmergencyServicesEnabled</span></span></p></td>
<td><p><span data-ttu-id="f7a58-116"><strong>True</strong></span><span class="sxs-lookup"><span data-stu-id="f7a58-116"><strong>True</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7a58-117">LocationRequired</span><span class="sxs-lookup"><span data-stu-id="f7a58-117">LocationRequired</span></span></p></td>
<td><p><span data-ttu-id="f7a58-118"><strong>Aviso de declinación de responsabilidades</strong></span><span class="sxs-lookup"><span data-stu-id="f7a58-118"><strong>Disclaimer</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7a58-119">EnhancedEmergencyServiceDisclaimer</span><span class="sxs-lookup"><span data-stu-id="f7a58-119">EnhancedEmergencyServiceDisclaimer</span></span></p></td>
<td><p><span data-ttu-id="f7a58-120">La Directiva de la empresa requiere que establezca una ubicación.</span><span class="sxs-lookup"><span data-stu-id="f7a58-120">Your company policy requires you to set a location.</span></span> <span data-ttu-id="f7a58-121">Si no establece una ubicación, los servicios de emergencia no podrán localizarle en caso de emergencia.</span><span class="sxs-lookup"><span data-stu-id="f7a58-121">If you do not set a location, emergency services will not be able to locate you in an emergency.</span></span> <span data-ttu-id="f7a58-122">Establezca una ubicación.</span><span class="sxs-lookup"><span data-stu-id="f7a58-122">Please set a location.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7a58-123">Uselocationfore911only era</span><span class="sxs-lookup"><span data-stu-id="f7a58-123">UseLocationForE911Only</span></span></p></td>
<td><p><span data-ttu-id="f7a58-124"><strong>False</strong></span><span class="sxs-lookup"><span data-stu-id="f7a58-124"><strong>False</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7a58-125">PstnUsage</span><span class="sxs-lookup"><span data-stu-id="f7a58-125">PstnUsage</span></span></p></td>
<td><p><span data-ttu-id="f7a58-126"><strong>EmergencyUsage</strong></span><span class="sxs-lookup"><span data-stu-id="f7a58-126"><strong>EmergencyUsage</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7a58-127">EmergencyDialString</span><span class="sxs-lookup"><span data-stu-id="f7a58-127">EmergencyDialString</span></span></p></td>
<td><p><span data-ttu-id="f7a58-128"><strong>911</strong></span><span class="sxs-lookup"><span data-stu-id="f7a58-128"><strong>911</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7a58-129">EmergencyDialMask</span><span class="sxs-lookup"><span data-stu-id="f7a58-129">EmergencyDialMask</span></span></p></td>
<td><p><span data-ttu-id="f7a58-130"><strong>112</strong></span><span class="sxs-lookup"><span data-stu-id="f7a58-130"><strong>112</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7a58-131">NotificationUri</span><span class="sxs-lookup"><span data-stu-id="f7a58-131">NotificationUri</span></span></p></td>
<td><p><span data-ttu-id="f7a58-132"><strong>sip:security@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="f7a58-132"><strong>sip:security@litwareinc.com</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7a58-133">Uri</span><span class="sxs-lookup"><span data-stu-id="f7a58-133">ConferenceUri</span></span></p></td>
<td><p><span data-ttu-id="f7a58-134"><strong>sip:+14255550123@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="f7a58-134"><strong>sip:+14255550123@litwareinc.com</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7a58-135">ConferenceMode</span><span class="sxs-lookup"><span data-stu-id="f7a58-135">ConferenceMode</span></span></p></td>
<td><p><span data-ttu-id="f7a58-136"><strong>TwoWay</strong></span><span class="sxs-lookup"><span data-stu-id="f7a58-136"><strong>twoway</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7a58-137">LocationRefreshInterval</span><span class="sxs-lookup"><span data-stu-id="f7a58-137">LocationRefreshInterval</span></span></p></td>
<td><p><span data-ttu-id="f7a58-138"><strong>2</strong></span><span class="sxs-lookup"><span data-stu-id="f7a58-138"><strong>2</strong></span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f7a58-139">Para obtener información detallada sobre cómo trabajar con directivas de ubicación, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="f7a58-139">For details about working with location policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="f7a58-140">New-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="f7a58-140">New-CsLocationPolicy</span></span>

  - <span data-ttu-id="f7a58-141">Get-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="f7a58-141">Get-CsLocationPolicy</span></span>

  - <span data-ttu-id="f7a58-142">Set-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="f7a58-142">Set-CsLocationPolicy</span></span>

  - <span data-ttu-id="f7a58-143">Remove-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="f7a58-143">Remove-CsLocationPolicy</span></span>

  - <span data-ttu-id="f7a58-144">Grant-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="f7a58-144">Grant-CsLocationPolicy</span></span>

<div>

## <a name="to-create-location-policies"></a><span data-ttu-id="f7a58-145">Para crear directivas de ubicación</span><span class="sxs-lookup"><span data-stu-id="f7a58-145">To create location policies</span></span>

1.  <span data-ttu-id="f7a58-146">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="f7a58-146">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f7a58-147">Se producirá un error en CsLocationPolicy si la configuración de <STRONG>PstnUsage</STRONG> no está ya en la lista global de PstnUsages.</span><span class="sxs-lookup"><span data-stu-id="f7a58-147">CsLocationPolicy will fail if the setting for <STRONG>PstnUsage</STRONG> is not already in the Global list of PstnUsages.</span></span>

    
    </div>

2.  <span data-ttu-id="f7a58-148">Si lo desea, puede ejecutar el cmdlet siguiente para editar la Directiva de ubicación global:</span><span class="sxs-lookup"><span data-stu-id="f7a58-148">Optionally, run the following cmdlet to edit the global Location Policy:</span></span>
    
        Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2

3.  <span data-ttu-id="f7a58-149">Ejecute lo siguiente para crear una directiva de ubicación con etiqueta.</span><span class="sxs-lookup"><span data-stu-id="f7a58-149">Run the following to create a tagged Location Policy.</span></span>
    
        New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2

4.  <span data-ttu-id="f7a58-150">Ejecute el siguiente cmdlet para aplicar la Directiva de ubicación etiquetada creada en el paso 3 a una directiva de usuario.</span><span class="sxs-lookup"><span data-stu-id="f7a58-150">Run the following cmdlet to apply the tagged Location Policy created in step 3 to a user policy.</span></span>
    
        (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond

</div>

</div>

<span> </span>

</div>

</div>

</div>

