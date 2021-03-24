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
description: 'Summary: Read this topic to learn how to assign a voice policy for users using Phone System with on-premises PSTN connectivity.'
ms.openlocfilehash: 43e2b560cc0886bacd6faaec6c113ee1f237eff7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092968"
---
# <a name="assign-a-voice-routing-policy"></a><span data-ttu-id="ff5b1-103">Asignar una directiva de enrutado de voz</span><span class="sxs-lookup"><span data-stu-id="ff5b1-103">Assign a Voice Routing Policy</span></span>
 
> [!Important]
> <span data-ttu-id="ff5b1-104">Skype Empresarial Online se retirará el 31 de julio de 2021 después de lo cual el servicio ya no será accesible.</span><span class="sxs-lookup"><span data-stu-id="ff5b1-104">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="ff5b1-105">Además, la conectividad RTC entre el entorno local ya no se admite a través de Skype Empresarial Server o Cloud Connector Edition y Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="ff5b1-105">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="ff5b1-106">Obtenga información sobre cómo conectar la red de telefonía local a Teams mediante [enrutamiento directo.](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="ff5b1-106">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="ff5b1-107">**Resumen:** Lea este tema para obtener información sobre cómo asignar una directiva de voz para los usuarios que usan Phone System con conectividad RTC local.</span><span class="sxs-lookup"><span data-stu-id="ff5b1-107">**Summary:** Read this topic to learn how to assign a voice policy for users using Phone System with on-premises PSTN connectivity.</span></span> 
  
<span data-ttu-id="ff5b1-108">Una vez que un usuario está en Skype Empresarial Online y usa el sistema telefónico con conectividad RTC local, se les aplicarán dos directivas de voz.</span><span class="sxs-lookup"><span data-stu-id="ff5b1-108">Once a user is on Skype for Business Online and using Phone System with on-premises PSTN connectivity, two voice policies will apply to them.</span></span> <span data-ttu-id="ff5b1-109">Una es una directiva de enrutamiento de voz local que se asignará localmente.</span><span class="sxs-lookup"><span data-stu-id="ff5b1-109">One is an on-premises voice routing policy that you will assign on premises.</span></span> <span data-ttu-id="ff5b1-110">Esta directiva puede ser global o específica del usuario y define qué registros de uso de RTC están asociados con el usuario.</span><span class="sxs-lookup"><span data-stu-id="ff5b1-110">This policy can be global or user-specific and defines what PSTN usage records are associated with the user.</span></span> <span data-ttu-id="ff5b1-111">En este tema se explica cómo asignar esta directiva.</span><span class="sxs-lookup"><span data-stu-id="ff5b1-111">This topic explains how to assign this policy.</span></span>
  
<span data-ttu-id="ff5b1-112">La otra directiva de voz define qué características de llamada están disponibles para el usuario; Microsoft define esta directiva de voz y es idéntica para todos los sistemas telefónicos con usuarios de conectividad RTC locales.</span><span class="sxs-lookup"><span data-stu-id="ff5b1-112">The other voice policy defines what calling features are available to the user; this voice policy is defined by Microsoft and is identical for all Phone System with on-premises PSTN connectivity users.</span></span> <span data-ttu-id="ff5b1-113">Se asigna automáticamente a los usuarios del sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="ff5b1-113">It is automatically assigned to Phone System users.</span></span>
  
||<span data-ttu-id="ff5b1-114">**Usuario local**</span><span class="sxs-lookup"><span data-stu-id="ff5b1-114">**On-premises user**</span></span>|<span data-ttu-id="ff5b1-115">**Sistema telefónico con usuario de conectividad RTC local**</span><span class="sxs-lookup"><span data-stu-id="ff5b1-115">**Phone System with on-premises PSTN connectivity user**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ff5b1-116">Características de llamada definidas en</span><span class="sxs-lookup"><span data-stu-id="ff5b1-116">Calling features defined in</span></span>  <br/> |<span data-ttu-id="ff5b1-117">Directiva de voz</span><span class="sxs-lookup"><span data-stu-id="ff5b1-117">Voice policy</span></span>  <br/> |<span data-ttu-id="ff5b1-118">Directiva de voz predefinida, asignada automáticamente cuando el usuario tiene licencia para Sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="ff5b1-118">Pre-defined voice policy, assigned automatically when the user is licensed for Phone System.</span></span>  <br/> |
|<span data-ttu-id="ff5b1-119">Registros de uso de RTC asociados con</span><span class="sxs-lookup"><span data-stu-id="ff5b1-119">PSTN usage records associated with</span></span>  <br/> |<span data-ttu-id="ff5b1-120">Directiva de voz</span><span class="sxs-lookup"><span data-stu-id="ff5b1-120">Voice policy</span></span>  <br/> |<span data-ttu-id="ff5b1-121">Directiva de enrutamiento de voz, asignada mientras el usuario aún está interno.</span><span class="sxs-lookup"><span data-stu-id="ff5b1-121">Voice routing policy, assigned while the user is still homed on-premises.</span></span>  <br/> |
   
<span data-ttu-id="ff5b1-122">Realice los siguientes pasos con la implementación local, mientras que el usuario aún está en la implementación local.</span><span class="sxs-lookup"><span data-stu-id="ff5b1-122">You perform the following steps using your on-premises deployment, while the user is still homed in the on-premises deployment.</span></span>
  
## <a name="using-a-global-voice-routing-policy"></a><span data-ttu-id="ff5b1-123">Uso de una directiva de enrutamiento de voz global</span><span class="sxs-lookup"><span data-stu-id="ff5b1-123">Using a global voice routing policy</span></span>

<span data-ttu-id="ff5b1-124">Antes de usar una directiva de enrutamiento de voz global para el sistema telefónico con usuarios de conectividad RTC locales, debe agregar registros de uso de RTC a la directiva.</span><span class="sxs-lookup"><span data-stu-id="ff5b1-124">Before using a global voice routing policy for your Phone System with on-premises PSTN connectivity users, you must add PSTN usage records to the policy.</span></span>
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a><span data-ttu-id="ff5b1-125">Para asignar registros de uso de RTC a la directiva de enrutamiento de voz global</span><span class="sxs-lookup"><span data-stu-id="ff5b1-125">To assign PSTN usage records to the global voice routing policy</span></span>

1. <span data-ttu-id="ff5b1-126">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="ff5b1-126">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="ff5b1-127">Inicie el Shell de administración de Skype Empresarial Server: haga clic en Inicio **,** en Todos los programas **,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración **de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="ff5b1-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="ff5b1-128">Agregue los registros de uso de RTC a la directiva:</span><span class="sxs-lookup"><span data-stu-id="ff5b1-128">Add the PSTN usage records to the policy:</span></span>
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    <span data-ttu-id="ff5b1-129">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ff5b1-129">For example:</span></span>
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a><span data-ttu-id="ff5b1-130">Creación de una nueva directiva de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="ff5b1-130">Creating a new voice routing policy</span></span>

### <a name="to-create-a-new-voice-routing-policy"></a><span data-ttu-id="ff5b1-131">Para crear una nueva directiva de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="ff5b1-131">To create a new voice routing policy</span></span>

1. <span data-ttu-id="ff5b1-132">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="ff5b1-132">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="ff5b1-133">Inicie el Shell de administración de Skype Empresarial Server: haga clic en Inicio **,** en Todos los programas **,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración **de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="ff5b1-133">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="ff5b1-134">Crear una nueva directiva de enrutamiento de voz:</span><span class="sxs-lookup"><span data-stu-id="ff5b1-134">Create a new voice routing policy:</span></span>
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    <span data-ttu-id="ff5b1-135">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ff5b1-135">For example:</span></span>
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

<span data-ttu-id="ff5b1-136">En este ejemplo se crea una nueva directiva de enrutamiento de voz denominada HybridVoice, que tiene asociados dos usos de RTC.</span><span class="sxs-lookup"><span data-stu-id="ff5b1-136">This example creates a new voice routing policy called HybridVoice, which has two PSTN usages associated with it.</span></span>
  
## <a name="assigning-a-voice-routing-policy"></a><span data-ttu-id="ff5b1-137">Asignar una directiva de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="ff5b1-137">Assigning a voice routing policy</span></span>

<span data-ttu-id="ff5b1-138">Independientemente de si usa la directiva de enrutamiento de voz global o las específicas del usuario, siga estos pasos para asignar la directiva a un usuario.</span><span class="sxs-lookup"><span data-stu-id="ff5b1-138">No matter whether you use the global voice routing policy, or user-specific ones, use the following steps to assign the policy to a user.</span></span>
  
### <a name="to-assign-the-voice-routing-policy"></a><span data-ttu-id="ff5b1-139">Para asignar la directiva de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="ff5b1-139">To assign the voice routing policy</span></span>

1. <span data-ttu-id="ff5b1-140">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="ff5b1-140">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="ff5b1-141">Inicie el Shell de administración de Skype Empresarial Server: haga clic en Inicio **,** en Todos los programas **,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración **de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="ff5b1-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="ff5b1-142">Asignar una directiva de voz existente a un usuario:</span><span class="sxs-lookup"><span data-stu-id="ff5b1-142">Assign an existing voice policy to a user:</span></span>
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="ff5b1-143">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ff5b1-143">For example:</span></span>
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

<span data-ttu-id="ff5b1-144">En este ejemplo, el usuario con el nombre para mostrar Bob Kelly se asigna a la directiva de voz creada anteriormente con el nombre HybridVoice.</span><span class="sxs-lookup"><span data-stu-id="ff5b1-144">In this example, the user with the display name Bob Kelly is assigned to the previously created voice policy with the name HybridVoice.</span></span>
  
<span data-ttu-id="ff5b1-145">Para obtener más información acerca de las directivas de enrutamiento de voz, vea Create [or modify a voice policy y configure PSTN usage records in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)y [Grant-CsVoicePolicy](/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="ff5b1-145">For more details about voice routing policies, see [Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps), and [Grant-CsVoicePolicy](/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span></span>
