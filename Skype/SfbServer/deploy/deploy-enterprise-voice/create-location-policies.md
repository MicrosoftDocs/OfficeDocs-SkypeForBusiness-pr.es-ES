---
title: Crear directivas de ubicación en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
description: Lea este tema para obtener información sobre cómo configurar las directivas de ubicación de servicio de emergencia mejorado (E9-1-1) en Skype empresarial Enterprise Voice.
ms.openlocfilehash: d06e22850b1556e4c7d9143b49176aff23bb6640
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767943"
---
# <a name="create-location-policies-in-skype-for-business-server"></a><span data-ttu-id="804fd-103">Crear directivas de ubicación en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="804fd-103">Create location policies in Skype for Business Server</span></span>

<span data-ttu-id="804fd-104">Lea este tema para obtener información sobre cómo configurar las directivas de ubicación de servicio de emergencia mejorado (E9-1-1) en Skype empresarial Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="804fd-104">Read this topic to learn how to configure enhanced emergency service (E9-1-1) location policies in Skype for Business Server Enterprise Voice.</span></span> 

<span data-ttu-id="804fd-105">Skype empresarial Server usa una directiva de ubicación para habilitar los clientes de Skype empresarial para E9-1-1 durante el registro del cliente.</span><span class="sxs-lookup"><span data-stu-id="804fd-105">Skype for Business Server uses a location policy to enable Skype for Business clients for E9-1-1 during client registration.</span></span> <span data-ttu-id="804fd-106">Una directiva de ubicación contiene la configuración que define cómo se implementará E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="804fd-106">A location policy contains the settings that define how E9-1-1 will be implemented.</span></span> <span data-ttu-id="804fd-107">Para obtener más información, consulte [planear directivas de ubicación para Skype empresarial Server](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).</span><span class="sxs-lookup"><span data-stu-id="804fd-107">For more information, see [Plan location policies for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).</span></span>

<span data-ttu-id="804fd-108">Las directivas de ubicación se definen con el panel de control de Skype para empresas o mediante el cmdlet [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="804fd-108">You define location policies by using the Skype for Business Control Panel or by using the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="804fd-109">Skype empresarial Server ahora es compatible con la configuración de varios números de emergencia para un cliente.</span><span class="sxs-lookup"><span data-stu-id="804fd-109">Skype for Business Server now supports the configuration of multiple emergency numbers for a client.</span></span> <span data-ttu-id="804fd-110">Si desea configurar varios números de emergencia, debe seguir la información de [plan para varios números de emergencia en Skype empresarial Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md) y [configurar varios números de emergencia en Skype empresarial](configure-multiple-emergency-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="804fd-110">If you want to configure multiple emergency numbers, you must follow the information in [Plan for multiple emergency numbers in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md) and [Configure multiple emergency numbers in Skype for Business](configure-multiple-emergency-numbers.md).</span></span> 

<span data-ttu-id="804fd-p103">La directiva de ubicación global puede editarse y crear otras directivas de ubicación con etiqueta. Un cliente obtiene una directiva global si no se ubica en una subred que tenga asociada una directiva de ubicación o, bien, si el cliente no tiene asignada directamente una directiva de ubicación. Las directivas con etiquetas se asignan a subredes o usuarios.  </span><span class="sxs-lookup"><span data-stu-id="804fd-p103">You can edit the global location policy and create new tagged location policies. A client obtains a global policy when it is not located within a subnet with an associated location policy, or when the client has not been directly assigned a location policy. Tagged policies are assigned to subnets or users.</span></span> 

<span data-ttu-id="804fd-114">Para crear una directiva de ubicación, debe usar una cuenta que pertenezca al grupo RTCUniversalServerAdmins, o bien que tenga el rol administrativo CsVoiceAdministrator o derechos y permisos de administrador equivalentes.</span><span class="sxs-lookup"><span data-stu-id="804fd-114">To create a location policy, you must use an account that is a member of the RTCUniversalServerAdmins group, or is a member of the CsVoiceAdministrator administrative role, or has equivalent administrator rights and permissions.</span></span>

<span data-ttu-id="804fd-115">Para obtener más información, consulte [planear directivas de ubicación para Skype empresarial Server](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).</span><span class="sxs-lookup"><span data-stu-id="804fd-115">For more information, see [Plan location policies for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).</span></span> <span data-ttu-id="804fd-116">Los cmdlets de este procedimiento usan una directiva de ubicación definida mediante los siguientes valores.</span><span class="sxs-lookup"><span data-stu-id="804fd-116">Cmdlets in this procedure use a location policy defined using the following values.</span></span> <span data-ttu-id="804fd-117">Para obtener una descripción completa de los parámetros y valores del cmdlet, vea [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="804fd-117">For a complete description of cmdlet parameters and values, see [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps).</span></span>


| <span data-ttu-id="804fd-118">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="804fd-118">**Element**</span></span>                               | <span data-ttu-id="804fd-119">**Valor**</span><span class="sxs-lookup"><span data-stu-id="804fd-119">**Value**</span></span>                                                                                                                                                                          |
|:------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="804fd-120">EnhancedEmergencyServicesEnabled</span><span class="sxs-lookup"><span data-stu-id="804fd-120">EnhancedEmergencyServicesEnabled</span></span>  <br/>   | <span data-ttu-id="804fd-121">**True**</span><span class="sxs-lookup"><span data-stu-id="804fd-121">**True**</span></span> <br/>                                                                                                                                                                     |
| <span data-ttu-id="804fd-122">LocationRequired</span><span class="sxs-lookup"><span data-stu-id="804fd-122">LocationRequired</span></span>  <br/>                   | <span data-ttu-id="804fd-123">**Disclaimer**</span><span class="sxs-lookup"><span data-stu-id="804fd-123">**Disclaimer**</span></span> <br/>                                                                                                                                                               |
| <span data-ttu-id="804fd-124">EnhancedEmergencyServiceDisclaimer</span><span class="sxs-lookup"><span data-stu-id="804fd-124">EnhancedEmergencyServiceDisclaimer</span></span>  <br/> | <span data-ttu-id="804fd-p105">La directiva de compañía le exige que indique una ubicación. Si no define una ubicación, los servicios de emergencia no podrán localizarle en caso de emergencia. Especifique una ubicación.</span><span class="sxs-lookup"><span data-stu-id="804fd-p105">Your company policy requires you to set a location. If you do not set a location, emergency services will not be able to locate you in an emergency. Please set a location.</span></span>  <br/> |
| <span data-ttu-id="804fd-128">UseLocationForE911Only</span><span class="sxs-lookup"><span data-stu-id="804fd-128">UseLocationForE911Only</span></span>  <br/>             | <span data-ttu-id="804fd-129">**False**</span><span class="sxs-lookup"><span data-stu-id="804fd-129">**False**</span></span> <br/>                                                                                                                                                                    |
| <span data-ttu-id="804fd-130">PstnUsage</span><span class="sxs-lookup"><span data-stu-id="804fd-130">PstnUsage</span></span>  <br/>                          | <span data-ttu-id="804fd-131">**EmergencyUsage**</span><span class="sxs-lookup"><span data-stu-id="804fd-131">**EmergencyUsage**</span></span> <br/>                                                                                                                                                           |
| <span data-ttu-id="804fd-132">EmergencyDialString</span><span class="sxs-lookup"><span data-stu-id="804fd-132">EmergencyDialString</span></span>  <br/>                | <span data-ttu-id="804fd-133">**911**</span><span class="sxs-lookup"><span data-stu-id="804fd-133">**911**</span></span> <br/>                                                                                                                                                                      |
| <span data-ttu-id="804fd-134">EmergencyDialMask</span><span class="sxs-lookup"><span data-stu-id="804fd-134">EmergencyDialMask</span></span>  <br/>                  | <span data-ttu-id="804fd-135">**112**</span><span class="sxs-lookup"><span data-stu-id="804fd-135">**112**</span></span> <br/>                                                                                                                                                                      |
| <span data-ttu-id="804fd-136">NotificationUri</span><span class="sxs-lookup"><span data-stu-id="804fd-136">NotificationUri</span></span>  <br/>                    | <span data-ttu-id="804fd-137"><strong>sip:security@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="804fd-137"><strong>sip:security@litwareinc.com</strong></span></span> <br/>                                                                                                                                 |
| <span data-ttu-id="804fd-138">ConferenceUri</span><span class="sxs-lookup"><span data-stu-id="804fd-138">ConferenceUri</span></span>  <br/>                      | <span data-ttu-id="804fd-139"><strong>sip:+14255550123@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="804fd-139"><strong>sip:+14255550123@litwareinc.com</strong></span></span> <br/>                                                                                                                             |
| <span data-ttu-id="804fd-140">ConferenceMode</span><span class="sxs-lookup"><span data-stu-id="804fd-140">ConferenceMode</span></span>  <br/>                     | <span data-ttu-id="804fd-141">**twoway**</span><span class="sxs-lookup"><span data-stu-id="804fd-141">**twoway**</span></span> <br/>                                                                                                                                                                   |
| <span data-ttu-id="804fd-142">LocationRefreshInterval</span><span class="sxs-lookup"><span data-stu-id="804fd-142">LocationRefreshInterval</span></span>  <br/>            | <span data-ttu-id="804fd-143">**2**</span><span class="sxs-lookup"><span data-stu-id="804fd-143">**2**</span></span> <br/>                                                                                                                                                                        |

### <a name="to-create-location-policies"></a><span data-ttu-id="804fd-144">Para crear directivas de ubicación</span><span class="sxs-lookup"><span data-stu-id="804fd-144">To create location policies</span></span>

1. <span data-ttu-id="804fd-145">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="804fd-145">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="804fd-146">CsLocationPolicy no funcionará correctamente si el valor de **PstnUsage** no está ya presente en la lista global de PstnUsages.</span><span class="sxs-lookup"><span data-stu-id="804fd-146">CsLocationPolicy will fail if the setting for **PstnUsage** is not already in the Global list of PstnUsages.</span></span>

2. <span data-ttu-id="804fd-147">También puede ejecutar el cmdlet siguiente para editar la directiva de ubicación global:</span><span class="sxs-lookup"><span data-stu-id="804fd-147">Optionally, run the following cmdlet to edit the global Location Policy:</span></span>

   ```powershell
   Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2
   ```

3. <span data-ttu-id="804fd-148">Ejecute el cmdlet siguiente para crear una directiva de ubicación con etiqueta.</span><span class="sxs-lookup"><span data-stu-id="804fd-148">Run the following to create a tagged Location Policy.</span></span>

   ```powershell
   New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2
   ```

4. <span data-ttu-id="804fd-149">Ejecute el cmdlet siguiente para aplicar la directiva de ubicación con etiqueta que se ha creado en el paso 3 en una directiva de usuario.</span><span class="sxs-lookup"><span data-stu-id="804fd-149">Run the following cmdlet to apply the tagged Location Policy created in step 3 to a user policy.</span></span>

   ```powershell
   (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond
   ```
