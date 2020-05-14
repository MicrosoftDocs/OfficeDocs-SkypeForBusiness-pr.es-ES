---
title: Asignar una directiva de enrutado de voz
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: 'Resumen: Lea este tema para obtener información sobre cómo asignar una directiva de voz a los usuarios que usan sistema telefónico con conectividad con RTC local.'
ms.openlocfilehash: 141d3cca560201df921fb4195db55ac60103a3d6
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221864"
---
# <a name="assign-a-voice-routing-policy"></a><span data-ttu-id="57e81-103">Asignar una directiva de enrutado de voz</span><span class="sxs-lookup"><span data-stu-id="57e81-103">Assign a Voice Routing Policy</span></span>
 
<span data-ttu-id="57e81-104">**Resumen:** Lea este tema para obtener información sobre cómo asignar una directiva de voz a los usuarios que usan el sistema telefónico con conectividad con RTC local.</span><span class="sxs-lookup"><span data-stu-id="57e81-104">**Summary:** Read this topic to learn how to assign a voice policy for users using Phone System with on-premises PSTN connectivity.</span></span> 
  
<span data-ttu-id="57e81-105">Una vez que un usuario se encuentra en Skype empresarial online y usa el sistema telefónico con conectividad con RTC local, se le aplicarán dos directivas de voz.</span><span class="sxs-lookup"><span data-stu-id="57e81-105">Once a user is on Skype for Business Online and using Phone System with on-premises PSTN connectivity, two voice policies will apply to them.</span></span> <span data-ttu-id="57e81-106">Una es una directiva de enrutamiento de voz local que asignará de forma local.</span><span class="sxs-lookup"><span data-stu-id="57e81-106">One is an on-premises voice routing policy that you will assign on premises.</span></span> <span data-ttu-id="57e81-107">Esta Directiva puede ser global o específica del usuario y define qué registros de uso de RTC están asociados con el usuario.</span><span class="sxs-lookup"><span data-stu-id="57e81-107">This policy can be global or user-specific and defines what PSTN usage records are associated with the user.</span></span> <span data-ttu-id="57e81-108">En este tema se explica cómo asignar esta Directiva.</span><span class="sxs-lookup"><span data-stu-id="57e81-108">This topic explains how to assign this policy.</span></span>
  
<span data-ttu-id="57e81-109">La otra directiva de voz define qué características de llamada están disponibles para el usuario; esta directiva de voz está definida por Microsoft y es idéntica para todos los sistemas telefónicos con los usuarios de conectividad RTC local.</span><span class="sxs-lookup"><span data-stu-id="57e81-109">The other voice policy defines what calling features are available to the user; this voice policy is defined by Microsoft and is identical for all Phone System with on-premises PSTN connectivity users.</span></span> <span data-ttu-id="57e81-110">Se asigna automáticamente a los usuarios del sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="57e81-110">It is automatically assigned to Phone System users.</span></span>
  
||<span data-ttu-id="57e81-111">**Usuario local**</span><span class="sxs-lookup"><span data-stu-id="57e81-111">**On-premises user**</span></span>|<span data-ttu-id="57e81-112">**Sistema telefónico con usuario de conectividad con RTC local**</span><span class="sxs-lookup"><span data-stu-id="57e81-112">**Phone System with on-premises PSTN connectivity user**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="57e81-113">Llamar a características definidas en</span><span class="sxs-lookup"><span data-stu-id="57e81-113">Calling features defined in</span></span>  <br/> |<span data-ttu-id="57e81-114">Directiva de voz</span><span class="sxs-lookup"><span data-stu-id="57e81-114">Voice policy</span></span>  <br/> |<span data-ttu-id="57e81-115">Directiva de voz predefinida, asignada automáticamente cuando el usuario tiene una licencia de sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="57e81-115">Pre-defined voice policy, assigned automatically when the user is licensed for Phone System.</span></span>  <br/> |
|<span data-ttu-id="57e81-116">Registros de uso de RTC asociados con</span><span class="sxs-lookup"><span data-stu-id="57e81-116">PSTN usage records associated with</span></span>  <br/> |<span data-ttu-id="57e81-117">Directiva de voz</span><span class="sxs-lookup"><span data-stu-id="57e81-117">Voice policy</span></span>  <br/> |<span data-ttu-id="57e81-118">Directiva de enrutamiento de voz, asignada mientras el usuario sigue hospedado de forma local.</span><span class="sxs-lookup"><span data-stu-id="57e81-118">Voice routing policy, assigned while the user is still homed on-premises.</span></span>  <br/> |
   
<span data-ttu-id="57e81-119">Los pasos siguientes se realizan mediante la implementación local, mientras que el usuario sigue hospedado en la implementación local.</span><span class="sxs-lookup"><span data-stu-id="57e81-119">You perform the following steps using your on-premises deployment, while the user is still homed in the on-premises deployment.</span></span>
  
## <a name="using-a-global-voice-routing-policy"></a><span data-ttu-id="57e81-120">Uso de una directiva de enrutamiento de voz global</span><span class="sxs-lookup"><span data-stu-id="57e81-120">Using a global voice routing policy</span></span>

<span data-ttu-id="57e81-121">Antes de usar una directiva de enrutamiento de voz global para el sistema telefónico con los usuarios de conectividad RTC local, debe agregar los registros de uso de RTC a la Directiva.</span><span class="sxs-lookup"><span data-stu-id="57e81-121">Before using a global voice routing policy for your Phone System with on-premises PSTN connectivity users, you must add PSTN usage records to the policy.</span></span>
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a><span data-ttu-id="57e81-122">Para asignar registros de uso de RTC a la Directiva de enrutamiento de voz global</span><span class="sxs-lookup"><span data-stu-id="57e81-122">To assign PSTN usage records to the global voice routing policy</span></span>

1. <span data-ttu-id="57e81-123">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="57e81-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="57e81-124">Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, en **todos los programas**, en **Skype empresarial 2015**y, a continuación, haga clic en **Shell de administración de Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="57e81-124">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="57e81-125">Agregue los registros de uso de RTC a la Directiva:</span><span class="sxs-lookup"><span data-stu-id="57e81-125">Add the PSTN usage records to the policy:</span></span>
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    <span data-ttu-id="57e81-126">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="57e81-126">For example:</span></span>
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a><span data-ttu-id="57e81-127">Creación de una nueva Directiva de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="57e81-127">Creating a new voice routing policy</span></span>

### <a name="to-create-a-new-voice-routing-policy"></a><span data-ttu-id="57e81-128">Para crear una nueva Directiva de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="57e81-128">To create a new voice routing policy</span></span>

1. <span data-ttu-id="57e81-129">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="57e81-129">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="57e81-130">Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, en **todos los programas**, en **Skype empresarial 2015**y, a continuación, haga clic en **Shell de administración de Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="57e81-130">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="57e81-131">Cree una nueva Directiva de enrutamiento de voz:</span><span class="sxs-lookup"><span data-stu-id="57e81-131">Create a new voice routing policy:</span></span>
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    <span data-ttu-id="57e81-132">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="57e81-132">For example:</span></span>
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

<span data-ttu-id="57e81-133">En este ejemplo, se crea una nueva Directiva de enrutamiento de voz denominada HybridVoice, que tiene asociados dos usos de RTC.</span><span class="sxs-lookup"><span data-stu-id="57e81-133">This example creates a new voice routing policy called HybridVoice, which has two PSTN usages associated with it.</span></span>
  
## <a name="assigning-a-voice-routing-policy"></a><span data-ttu-id="57e81-134">Asignar una directiva de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="57e81-134">Assigning a voice routing policy</span></span>

<span data-ttu-id="57e81-135">Independientemente de si usa la Directiva de enrutamiento de voz global o las específicas del usuario, use los pasos siguientes para asignar la Directiva a un usuario.</span><span class="sxs-lookup"><span data-stu-id="57e81-135">No matter whether you use the global voice routing policy, or user-specific ones, use the following steps to assign the policy to a user.</span></span>
  
### <a name="to-assign-the-voice-routing-policy"></a><span data-ttu-id="57e81-136">Para asignar la Directiva de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="57e81-136">To assign the voice routing policy</span></span>

1. <span data-ttu-id="57e81-137">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="57e81-137">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="57e81-138">Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, en **todos los programas**, en **Skype empresarial 2015**y, a continuación, haga clic en **Shell de administración de Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="57e81-138">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="57e81-139">Asignar una directiva de voz existente a un usuario:</span><span class="sxs-lookup"><span data-stu-id="57e81-139">Assign an existing voice policy to a user:</span></span>
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="57e81-140">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="57e81-140">For example:</span></span>
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

<span data-ttu-id="57e81-141">En este ejemplo, el usuario con el nombre para mostrar Bob Kelly se asigna a la Directiva de voz creada anteriormente con el nombre HybridVoice.</span><span class="sxs-lookup"><span data-stu-id="57e81-141">In this example, the user with the display name Bob Kelly is assigned to the previously created voice policy with the name HybridVoice.</span></span>
  
<span data-ttu-id="57e81-142">Para obtener más información acerca de las directivas de enrutamiento de voz, consulte [crear o modificar una directiva de voz y configurar registros de uso de RTC en Skype empresarial 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)y [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="57e81-142">For more details about voice routing policies, see [Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps), and [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span></span>
  

