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
description: 'Resumen: lea este tema para obtener información sobre cómo asignar una directiva de voz para los usuarios que usan sistema telefónico con conectividad RTC local.'
ms.openlocfilehash: 5d56d4f88e30b605276296b35cd9f316348342ca
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359326"
---
# <a name="assign-a-voice-routing-policy"></a><span data-ttu-id="e1c3c-103">Asignar una directiva de enrutado de voz</span><span class="sxs-lookup"><span data-stu-id="e1c3c-103">Assign a Voice Routing Policy</span></span>
 
> [!Important]
> <span data-ttu-id="e1c3c-104">Skype Empresarial Online se retirará el 31 de julio de 2021, tras lo cual el servicio ya no será accesible.</span><span class="sxs-lookup"><span data-stu-id="e1c3c-104">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="e1c3c-105">Además, ya no se admite la conectividad rtc entre su entorno local, ya sea a través de Skype Empresarial Server o Cloud Connector Edition y Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="e1c3c-105">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="e1c3c-106">Obtenga información sobre cómo conectar la red de telefonía local a Teams mediante [enrutamiento directo.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="e1c3c-106">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="e1c3c-107">**Resumen:** Lea este tema para obtener información sobre cómo asignar una directiva de voz para los usuarios que usan el Sistema telefónico con conectividad RTC local.</span><span class="sxs-lookup"><span data-stu-id="e1c3c-107">**Summary:** Read this topic to learn how to assign a voice policy for users using Phone System with on-premises PSTN connectivity.</span></span> 
  
<span data-ttu-id="e1c3c-108">Una vez que un usuario está en Skype Empresarial Online y usa el Sistema telefónico con conectividad RTC local, se le aplicarán dos directivas de voz.</span><span class="sxs-lookup"><span data-stu-id="e1c3c-108">Once a user is on Skype for Business Online and using Phone System with on-premises PSTN connectivity, two voice policies will apply to them.</span></span> <span data-ttu-id="e1c3c-109">Una es una directiva de enrutamiento de voz local que se asignará localmente.</span><span class="sxs-lookup"><span data-stu-id="e1c3c-109">One is an on-premises voice routing policy that you will assign on premises.</span></span> <span data-ttu-id="e1c3c-110">Esta directiva puede ser global o específica del usuario y define qué registros de uso de RTC están asociados con el usuario.</span><span class="sxs-lookup"><span data-stu-id="e1c3c-110">This policy can be global or user-specific and defines what PSTN usage records are associated with the user.</span></span> <span data-ttu-id="e1c3c-111">En este tema se explica cómo asignar esta directiva.</span><span class="sxs-lookup"><span data-stu-id="e1c3c-111">This topic explains how to assign this policy.</span></span>
  
<span data-ttu-id="e1c3c-112">La otra directiva de voz define qué características de llamada están disponibles para el usuario; Microsoft define esta directiva de voz y es idéntica para todos los sistemas telefónicos con usuarios de conectividad RTC locales.</span><span class="sxs-lookup"><span data-stu-id="e1c3c-112">The other voice policy defines what calling features are available to the user; this voice policy is defined by Microsoft and is identical for all Phone System with on-premises PSTN connectivity users.</span></span> <span data-ttu-id="e1c3c-113">Se asigna automáticamente a los usuarios del sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="e1c3c-113">It is automatically assigned to Phone System users.</span></span>
  
||<span data-ttu-id="e1c3c-114">**Usuario local**</span><span class="sxs-lookup"><span data-stu-id="e1c3c-114">**On-premises user**</span></span>|<span data-ttu-id="e1c3c-115">**Sistema telefónico con usuario de conectividad RTC local**</span><span class="sxs-lookup"><span data-stu-id="e1c3c-115">**Phone System with on-premises PSTN connectivity user**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e1c3c-116">Características de llamada definidas en</span><span class="sxs-lookup"><span data-stu-id="e1c3c-116">Calling features defined in</span></span>  <br/> |<span data-ttu-id="e1c3c-117">Directiva de voz</span><span class="sxs-lookup"><span data-stu-id="e1c3c-117">Voice policy</span></span>  <br/> |<span data-ttu-id="e1c3c-118">Directiva de voz predefinida, asignada automáticamente cuando el usuario tiene licencia para Sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="e1c3c-118">Pre-defined voice policy, assigned automatically when the user is licensed for Phone System.</span></span>  <br/> |
|<span data-ttu-id="e1c3c-119">Registros de uso de RTC asociados con</span><span class="sxs-lookup"><span data-stu-id="e1c3c-119">PSTN usage records associated with</span></span>  <br/> |<span data-ttu-id="e1c3c-120">Directiva de voz</span><span class="sxs-lookup"><span data-stu-id="e1c3c-120">Voice policy</span></span>  <br/> |<span data-ttu-id="e1c3c-121">Directiva de enrutamiento de voz, asignada mientras el usuario aún está en el entorno local.</span><span class="sxs-lookup"><span data-stu-id="e1c3c-121">Voice routing policy, assigned while the user is still homed on-premises.</span></span>  <br/> |
   
<span data-ttu-id="e1c3c-122">Realice los siguientes pasos con la implementación local, mientras que el usuario aún se encuentra en la implementación local.</span><span class="sxs-lookup"><span data-stu-id="e1c3c-122">You perform the following steps using your on-premises deployment, while the user is still homed in the on-premises deployment.</span></span>
  
## <a name="using-a-global-voice-routing-policy"></a><span data-ttu-id="e1c3c-123">Uso de una directiva de enrutamiento de voz global</span><span class="sxs-lookup"><span data-stu-id="e1c3c-123">Using a global voice routing policy</span></span>

<span data-ttu-id="e1c3c-124">Antes de usar una directiva de enrutamiento de voz global para su sistema telefónico con usuarios de conectividad RTC locales, debe agregar registros de uso de RTC a la directiva.</span><span class="sxs-lookup"><span data-stu-id="e1c3c-124">Before using a global voice routing policy for your Phone System with on-premises PSTN connectivity users, you must add PSTN usage records to the policy.</span></span>
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a><span data-ttu-id="e1c3c-125">Para asignar registros de uso de RTC a la directiva global de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="e1c3c-125">To assign PSTN usage records to the global voice routing policy</span></span>

1. <span data-ttu-id="e1c3c-126">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="e1c3c-126">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="e1c3c-127">Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** en Skype Empresarial **2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**</span><span class="sxs-lookup"><span data-stu-id="e1c3c-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="e1c3c-128">Agregue los registros de uso de RTC a la directiva:</span><span class="sxs-lookup"><span data-stu-id="e1c3c-128">Add the PSTN usage records to the policy:</span></span>
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    <span data-ttu-id="e1c3c-129">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e1c3c-129">For example:</span></span>
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a><span data-ttu-id="e1c3c-130">Creación de una nueva directiva de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="e1c3c-130">Creating a new voice routing policy</span></span>

### <a name="to-create-a-new-voice-routing-policy"></a><span data-ttu-id="e1c3c-131">Para crear una nueva directiva de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="e1c3c-131">To create a new voice routing policy</span></span>

1. <span data-ttu-id="e1c3c-132">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="e1c3c-132">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="e1c3c-133">Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** en Skype Empresarial **2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**</span><span class="sxs-lookup"><span data-stu-id="e1c3c-133">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="e1c3c-134">Cree una nueva directiva de enrutamiento de voz:</span><span class="sxs-lookup"><span data-stu-id="e1c3c-134">Create a new voice routing policy:</span></span>
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    <span data-ttu-id="e1c3c-135">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e1c3c-135">For example:</span></span>
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

<span data-ttu-id="e1c3c-136">En este ejemplo se crea una nueva directiva de enrutamiento de voz denominada HybridVoice, que tiene dos usos de RTC asociados.</span><span class="sxs-lookup"><span data-stu-id="e1c3c-136">This example creates a new voice routing policy called HybridVoice, which has two PSTN usages associated with it.</span></span>
  
## <a name="assigning-a-voice-routing-policy"></a><span data-ttu-id="e1c3c-137">Asignación de una directiva de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="e1c3c-137">Assigning a voice routing policy</span></span>

<span data-ttu-id="e1c3c-138">Independientemente de si usa la directiva de enrutamiento de voz global o la directiva específica del usuario, siga estos pasos para asignar la directiva a un usuario.</span><span class="sxs-lookup"><span data-stu-id="e1c3c-138">No matter whether you use the global voice routing policy, or user-specific ones, use the following steps to assign the policy to a user.</span></span>
  
### <a name="to-assign-the-voice-routing-policy"></a><span data-ttu-id="e1c3c-139">Para asignar la directiva de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="e1c3c-139">To assign the voice routing policy</span></span>

1. <span data-ttu-id="e1c3c-140">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="e1c3c-140">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="e1c3c-141">Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** en Skype Empresarial **2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**</span><span class="sxs-lookup"><span data-stu-id="e1c3c-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="e1c3c-142">Asignar una directiva de voz existente a un usuario:</span><span class="sxs-lookup"><span data-stu-id="e1c3c-142">Assign an existing voice policy to a user:</span></span>
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="e1c3c-143">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e1c3c-143">For example:</span></span>
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

<span data-ttu-id="e1c3c-144">En este ejemplo, el usuario con el nombre para mostrar Bob Kelly se asigna a la directiva de voz creada anteriormente con el nombre HybridVoice.</span><span class="sxs-lookup"><span data-stu-id="e1c3c-144">In this example, the user with the display name Bob Kelly is assigned to the previously created voice policy with the name HybridVoice.</span></span>
  
<span data-ttu-id="e1c3c-145">Para obtener más información sobre las directivas de enrutamiento de voz, vea Crear o modificar una directiva de voz y configurar registros de uso de RTC en Skype Empresarial [2015,](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md) [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)y [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="e1c3c-145">For more details about voice routing policies, see [Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps), and [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span></span>
  

