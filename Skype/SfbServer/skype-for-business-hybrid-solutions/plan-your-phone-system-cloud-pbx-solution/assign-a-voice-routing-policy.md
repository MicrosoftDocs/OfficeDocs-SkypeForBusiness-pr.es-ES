---
title: Asignar una directiva de enrutamiento de voz
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: 'Resumen: Leer este tema para obtener información sobre cómo asignar una directiva de voz para usuarios que utilizan el sistema de teléfono en Office 365 con conectividad de RTC local.'
ms.openlocfilehash: bcc4102157a3689208c45d7430a7954ce9a1e3f9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="assign-a-voice-routing-policy"></a><span data-ttu-id="32062-103">Asignar una directiva de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="32062-103">Assign a Voice Routing Policy</span></span>
 
<span data-ttu-id="32062-104">**Resumen:** Lea este tema para aprender a asignar una directiva de voz para usuarios que utilizan el sistema de teléfono en Office 365 con conectividad de RTC local.</span><span class="sxs-lookup"><span data-stu-id="32062-104">**Summary:** Read this topic to learn how to assign a voice policy for users using Phone System in Office 365 with on-premises PSTN connectivity.</span></span>
  
<span data-ttu-id="32062-105">Una vez que un usuario está en Skype para los negocios en línea y utilizar el sistema telefónico en Office 365 con conectividad de RTC local, se les aplicará dos directivas de voz.</span><span class="sxs-lookup"><span data-stu-id="32062-105">Once a user is on Skype for Business Online and using Phone System in Office 365 with on-premises PSTN connectivity, two voice policies will apply to them.</span></span> <span data-ttu-id="32062-106">Uno es una directiva de enrutamiento de voz locales que asignará en locales.</span><span class="sxs-lookup"><span data-stu-id="32062-106">One is an on-premises voice routing policy that you will assign on premises.</span></span> <span data-ttu-id="32062-107">Esta directiva puede ser global o específica del usuario y define qué registros de uso PSTN están asociados con el usuario.</span><span class="sxs-lookup"><span data-stu-id="32062-107">This policy can be global or user-specific and defines what PSTN usage records are associated with the user.</span></span> <span data-ttu-id="32062-108">En este tema se explica cómo asignar esta directiva.</span><span class="sxs-lookup"><span data-stu-id="32062-108">This topic explains how to assign this policy.</span></span>
  
<span data-ttu-id="32062-109">La otra directiva de voz define qué características de llamada están disponibles para el usuario; Esta directiva de voz está definida por Microsoft y es idéntica para todo el sistema de teléfono en Office 365 con usuarios de conectividad PSTN locales.</span><span class="sxs-lookup"><span data-stu-id="32062-109">The other voice policy defines what calling features are available to the user; this voice policy is defined by Microsoft and is identical for all Phone System in Office 365 with on-premises PSTN connectivity users.</span></span> <span data-ttu-id="32062-110">Se asigna automáticamente al sistema de teléfono de los usuarios de Office 365.</span><span class="sxs-lookup"><span data-stu-id="32062-110">It is automatically assigned to Phone System in Office 365 users.</span></span>
  
||<span data-ttu-id="32062-111">**Usuario local**</span><span class="sxs-lookup"><span data-stu-id="32062-111">**On-premises user**</span></span>|<span data-ttu-id="32062-112">**Sistema de teléfono en Office 365 con usuario de conectividad RTC local**</span><span class="sxs-lookup"><span data-stu-id="32062-112">**Phone System in Office 365 with on-premises PSTN connectivity user**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="32062-113">Características de llamadas definidas en</span><span class="sxs-lookup"><span data-stu-id="32062-113">Calling features defined in</span></span>  <br/> |<span data-ttu-id="32062-114">Directiva de voz</span><span class="sxs-lookup"><span data-stu-id="32062-114">Voice policy</span></span>  <br/> |<span data-ttu-id="32062-115">Predefinidos directiva de voz, asignada de forma automática cuando el usuario tiene licencia para su sistema telefónico en Office 365.</span><span class="sxs-lookup"><span data-stu-id="32062-115">Pre-defined voice policy, assigned automatically when the user is licensed for Phone System in Office 365.</span></span>  <br/> |
|<span data-ttu-id="32062-116">Registros de uso de RTC asociados con</span><span class="sxs-lookup"><span data-stu-id="32062-116">PSTN usage records associated with</span></span>  <br/> |<span data-ttu-id="32062-117">Directiva de voz</span><span class="sxs-lookup"><span data-stu-id="32062-117">Voice policy</span></span>  <br/> |<span data-ttu-id="32062-118">Directiva de enrutamiento de voz, asignada cuando el usuario aún está hospedado de forma local.</span><span class="sxs-lookup"><span data-stu-id="32062-118">Voice routing policy, assigned while the user is still homed on-premises.</span></span>  <br/> |
   
<span data-ttu-id="32062-119">Realice los pasos siguientes con la implementación local, mientras el usuario todavía está alojado en la implementación local.</span><span class="sxs-lookup"><span data-stu-id="32062-119">You perform the following steps using your on-premises deployment, while the user is still homed in the on-premises deployment.</span></span>
  
## <a name="using-a-global-voice-routing-policy"></a><span data-ttu-id="32062-120">Usar una directiva de enrutamiento de voz global</span><span class="sxs-lookup"><span data-stu-id="32062-120">Using a global voice routing policy</span></span>

<span data-ttu-id="32062-121">Antes de utilizar una directiva de enrutamiento de voz global para su sistema telefónico en Office 365 con usuarios de conectividad RTC local, debe agregar registros de uso PSTN a la directiva.</span><span class="sxs-lookup"><span data-stu-id="32062-121">Before using a global voice routing policy for your Phone System in Office 365 with on-premises PSTN connectivity users, you must add PSTN usage records to the policy.</span></span>
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a><span data-ttu-id="32062-122">Para asignar registros de uso de RTC a la directiva de enrutamiento de voz global</span><span class="sxs-lookup"><span data-stu-id="32062-122">To assign PSTN usage records to the global voice routing policy</span></span>

1. <span data-ttu-id="32062-123">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="32062-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="32062-124">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="32062-124">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="32062-125">Agregue los registros de uso PSTN a la directiva:</span><span class="sxs-lookup"><span data-stu-id="32062-125">Add the PSTN usage records to the policy:</span></span>
    
  ```
  Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 

  ```

    <span data-ttu-id="32062-126">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="32062-126">For example:</span></span>
    
  ```
  Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 

  ```

## <a name="creating-a-new-voice-routing-policy"></a><span data-ttu-id="32062-127">Crear una directiva de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="32062-127">Creating a new voice routing policy</span></span>

### <a name="to-create-a-new-voice-routing-policy"></a><span data-ttu-id="32062-128">Para crear una directiva de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="32062-128">To create a new voice routing policy</span></span>

1. <span data-ttu-id="32062-129">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="32062-129">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="32062-130">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="32062-130">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="32062-131">Crea una directiva de enrutamiento de voz:</span><span class="sxs-lookup"><span data-stu-id="32062-131">Create a new voice routing policy:</span></span>
    
  ```
  New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
  ```

    <span data-ttu-id="32062-132">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="32062-132">For example:</span></span>
    
  ```
  New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
  ```

<span data-ttu-id="32062-133">En este ejemplo se crea una directiva de enrutamiento de voz llamada HybridVoice, que tiene asociados dos usos de RTC.</span><span class="sxs-lookup"><span data-stu-id="32062-133">This example creates a new voice routing policy called HybridVoice, which has two PSTN usages associated with it.</span></span>
  
## <a name="assigning-a-voice-routing-policy"></a><span data-ttu-id="32062-134">Asignar una directiva de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="32062-134">Assigning a voice routing policy</span></span>

<span data-ttu-id="32062-135">Siga estos pasos para asignar la directiva a un usuario, independientemente de si usa la directiva de enrutamiento de voz global o directivas específicas de usuario.</span><span class="sxs-lookup"><span data-stu-id="32062-135">No matter whether you use the global voice routing policy, or user-specific ones, use the following steps to assign the policy to a user.</span></span>
  
### <a name="to-assign-the-voice-routing-policy"></a><span data-ttu-id="32062-136">Para asignar la directiva de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="32062-136">To assign the voice routing policy</span></span>

1. <span data-ttu-id="32062-137">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="32062-137">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="32062-138">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="32062-138">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="32062-139">Asignar una directiva de voz existente a un usuario:</span><span class="sxs-lookup"><span data-stu-id="32062-139">Assign an existing voice policy to a user:</span></span>
    
  ```
  Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
  ```

    <span data-ttu-id="32062-140">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="32062-140">For example:</span></span>
    
  ```
  Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
  ```

<span data-ttu-id="32062-141">En este ejemplo, se asigna el usuario con el nombre para mostrar Guillermo Rodarte a la directiva de voz creada anteriormente con el nombre HybridVoice.</span><span class="sxs-lookup"><span data-stu-id="32062-141">In this example, the user with the display name Bob Kelly is assigned to the previously created voice policy with the name HybridVoice.</span></span>
  
<span data-ttu-id="32062-142">Para obtener más detalles acerca de las directivas de enrutamiento de voz, consulte [crear o modificar una directiva de voz y configurar registros de uso PSTN en Skype para negocios 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [CsVoiceRoutingPolicy de nuevo](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)y [CsVoicePolicy de la concesión](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="32062-142">For more details about voice routing policies, see [Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps), and [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span></span>
  

