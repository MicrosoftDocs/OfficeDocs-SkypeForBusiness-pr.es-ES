---
title: Crear y administrar planes de marcado
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 7af17c94-5f8f-4452-ae1d-01f495b4dc94
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-apr2020
description: Obtenga información sobre cómo usar el Microsoft Teams de administración o Windows PowerShell para crear y administrar planes de marcado (planes de marcado de llamadas RTC).
ms.openlocfilehash: 59867dfe49436635f690ff9f5d56a2be36e553ec
ms.sourcegitcommit: 127f9fdf05b93ee3af4244224e1c32a45d73d3ee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/21/2021
ms.locfileid: "53046237"
---
# <a name="create-and-manage-dial-plans"></a><span data-ttu-id="2b6ee-103">Crear y administrar planes de marcado</span><span class="sxs-lookup"><span data-stu-id="2b6ee-103">Create and manage dial plans</span></span>

<span data-ttu-id="2b6ee-104">Después de planear los planes de marcado para su organización y de averiguar todas las reglas de normalización que deben crearse para el enrutamiento de llamadas, estará listo para crear los planes de marcado.</span><span class="sxs-lookup"><span data-stu-id="2b6ee-104">After you plan the dial plans for your organization and figured out all the normalization rules that need to be created for call routing, you're ready to create the dial plans.</span></span> <span data-ttu-id="2b6ee-105">Con una cuenta de administrador que tenga una licencia de Teams válida, puede usar el centro de administración de Microsoft Teams o Windows PowerShell para crear y administrar planes de marcado.</span><span class="sxs-lookup"><span data-stu-id="2b6ee-105">With an administrator account that has a valid Teams license, you can use the Microsoft Teams admin center or Windows PowerShell to create and manage dial plans.</span></span>  

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="2b6ee-106">Usar el Centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2b6ee-106">Using the Microsoft Teams admin center</span></span>

### <a name="create-a-dial-plan"></a><span data-ttu-id="2b6ee-107">Crear un plan de marcado</span><span class="sxs-lookup"><span data-stu-id="2b6ee-107">Create a dial plan</span></span>

1. <span data-ttu-id="2b6ee-108">En el panel de navegación izquierdo del Microsoft Teams de administración, vaya a Plan **de marcado**  >  **de voz.**</span><span class="sxs-lookup"><span data-stu-id="2b6ee-108">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="2b6ee-109">Haga **clic en** Agregar y escriba un nombre y una descripción para el plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="2b6ee-109">Click **Add**, and then enter a name and description for the dial plan.</span></span>
    <span data-ttu-id="2b6ee-110">![Captura de pantalla que muestra la página Agregar para crear un plan de marcado](media/create-dial-plan.png)</span><span class="sxs-lookup"><span data-stu-id="2b6ee-110">![Screenshot showing the Add page for creating a dial plan](media/create-dial-plan.png)</span></span>
3. <span data-ttu-id="2b6ee-111">En **Detalles del plan de** marcado, especifique un prefijo de marcado externo si los usuarios necesitan marcar uno o más dígitos iniciales adicionales (por ejemplo, 9) para obtener una línea externa.</span><span class="sxs-lookup"><span data-stu-id="2b6ee-111">Under **Dial plan details**, specify an external dialing prefix if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span> <span data-ttu-id="2b6ee-112">Para ello:</span><span class="sxs-lookup"><span data-stu-id="2b6ee-112">To do this:</span></span>
    1. <span data-ttu-id="2b6ee-113">En el **cuadro Prefijo de marcado externo,** escriba un prefijo de marcado externo.</span><span class="sxs-lookup"><span data-stu-id="2b6ee-113">In the **External dialing prefix** box, enter an external dialing prefix.</span></span> <span data-ttu-id="2b6ee-114">El prefijo puede tener hasta cuatro caracteres (#,\*y 0-9).</span><span class="sxs-lookup"><span data-stu-id="2b6ee-114">The prefix can be up to four characters (#,\*, and 0-9).</span></span>
    2. <span data-ttu-id="2b6ee-115">Activar la **marcación de dispositivo optimizada**.</span><span class="sxs-lookup"><span data-stu-id="2b6ee-115">Turn on **Optimized device dialing**.</span></span> <span data-ttu-id="2b6ee-116">Si especifica un prefijo de marcado externo, también debe activar esta configuración para aplicar el prefijo para que las llamadas se puedan realizar fuera de su organización.</span><span class="sxs-lookup"><span data-stu-id="2b6ee-116">If you specify an external dialing prefix, you must also turn on this setting to apply the prefix so calls can be made outside your organization.</span></span>
4. <span data-ttu-id="2b6ee-117">En **Reglas de normalización,** configure y asocie una o más reglas de [normalización](what-are-dial-plans.md#normalization-rules) para el plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="2b6ee-117">Under **Normalization rules**, configure and associate one or more [normalization rules](what-are-dial-plans.md#normalization-rules) for the dial plan.</span></span> <span data-ttu-id="2b6ee-118">Cada plan de marcado debe tener al menos una regla de normalización asociada.</span><span class="sxs-lookup"><span data-stu-id="2b6ee-118">Each dial plan must have at least one normalization rule associated with it.</span></span>  <span data-ttu-id="2b6ee-119">Para ello, realice una o varias de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="2b6ee-119">To do this, do one or more of the following:</span></span>
    - <span data-ttu-id="2b6ee-120">Para crear una nueva regla de normalización y asociarla al plan de marcado, haga clic en **Agregar** y, a continuación, defina la regla.</span><span class="sxs-lookup"><span data-stu-id="2b6ee-120">To create a new normalization rule and associate it with the dial plan, click **Add**, and then define the rule.</span></span>
    - <span data-ttu-id="2b6ee-121">Para editar una regla de normalización que ya está asociada al plan de marcado, seleccione la regla haciendo clic a la izquierda del nombre de la regla y, a continuación, haga clic en **Editar.**</span><span class="sxs-lookup"><span data-stu-id="2b6ee-121">To edit a normalization rule that's already associated with the dial plan, select the rule by clicking to the left of the rule name, and then click **Edit**.</span></span> <span data-ttu-id="2b6ee-122">Realice los cambios que desee y, a continuación, haga clic **en Guardar.**</span><span class="sxs-lookup"><span data-stu-id="2b6ee-122">Make the changes you want, and then click **Save**.</span></span>
    - <span data-ttu-id="2b6ee-123">Para quitar una regla de normalización del plan de marcado, seleccione la regla haciendo clic a la izquierda del nombre de la regla y, a continuación, haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="2b6ee-123">To remove a normalization rule from the dial plan, select the rule by clicking to the left of the rule name, and then click **Remove**.</span></span>
5. <span data-ttu-id="2b6ee-124">Organice las reglas de normalización en el orden que desee.</span><span class="sxs-lookup"><span data-stu-id="2b6ee-124">Arrange the normalization rules in the order that you want.</span></span> <span data-ttu-id="2b6ee-125">Haga **clic en Subir** o **Bajar** para cambiar la posición de las reglas de la lista.</span><span class="sxs-lookup"><span data-stu-id="2b6ee-125">Click **Move up** or **Move down** to change the position of rules in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2b6ee-126">Teams atraviesa la lista de reglas de normalización desde arriba hacia abajo y usa la primera regla que coincide con el número marcado.</span><span class="sxs-lookup"><span data-stu-id="2b6ee-126">Teams traverses the list of normalization rules from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="2b6ee-127">Si configura un plan de marcado para que un número marcado pueda coincidir con más de una regla de normalización, asegúrese de que las reglas más restrictivas se ordenan por encima de las menos restrictivas.</span><span class="sxs-lookup"><span data-stu-id="2b6ee-127">If you set up a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span> <span data-ttu-id="2b6ee-128">Si configura un plan de marcado que normaliza un número marcado sin un "+", el servicio de llamadas intentará normalizar el número de nuevo con las reglas del inquilino y del plan de marcado regional.</span><span class="sxs-lookup"><span data-stu-id="2b6ee-128">If you set up a dial plan that normalizes a dialed number without a "+", the calling service will attempt to normalize the number again using Tenant and regional dial plan rules.</span></span> <span data-ttu-id="2b6ee-129">Para evitar la doble normalización, se recomienda que todas las reglas de normalización den como resultado números empezando por un "+".</span><span class="sxs-lookup"><span data-stu-id="2b6ee-129">To avoid double normalization, it's recommended that all normalization rules result in numbers starting with a "+".</span></span> <span data-ttu-id="2b6ee-130">Los clientes de Enrutamiento directo pueden usar [reglas de traducción troncal](direct-routing-translate-numbers.md) para quitar el "+" si es necesario.</span><span class="sxs-lookup"><span data-stu-id="2b6ee-130">Direct Routing customers can use [trunk translation](direct-routing-translate-numbers.md) rules to remove the "+" if required.</span></span> 

6. <span data-ttu-id="2b6ee-131">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2b6ee-131">Click **Save**.</span></span>
7. <span data-ttu-id="2b6ee-132">Si desea probar el plan de marcado, en Plan de marcado de **prueba,** escriba un número de teléfono y, a continuación, haga clic en **Probar.**</span><span class="sxs-lookup"><span data-stu-id="2b6ee-132">If you want to test the dial plan, under **Test dial plan**, enter a phone number, and then click **Test**.</span></span>

### <a name="edit-a-dial-plan"></a><span data-ttu-id="2b6ee-133">Editar un plan de marcado</span><span class="sxs-lookup"><span data-stu-id="2b6ee-133">Edit a dial plan</span></span>

1. <span data-ttu-id="2b6ee-134">En el panel de navegación izquierdo del Microsoft Teams de administración, vaya a Plan **de marcado**  >  **de voz.**</span><span class="sxs-lookup"><span data-stu-id="2b6ee-134">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="2b6ee-135">Seleccione el plan de marcado haciendo clic a la izquierda del nombre del plan de marcado y, a continuación, haga clic en **Editar.**</span><span class="sxs-lookup"><span data-stu-id="2b6ee-135">Select the dial plan by clicking to the left of the dial plan name, and then click **Edit**.</span></span>
3. <span data-ttu-id="2b6ee-136">Realice los cambios que desee y, a continuación, haga clic en **Guardar.**</span><span class="sxs-lookup"><span data-stu-id="2b6ee-136">Make the changes that you want, and then click **Save**.</span></span>

### <a name="assign-a-dial-plan-to-users"></a><span data-ttu-id="2b6ee-137">Asignar un plan de marcado a los usuarios</span><span class="sxs-lookup"><span data-stu-id="2b6ee-137">Assign a dial plan to users</span></span>

<span data-ttu-id="2b6ee-138">Asigne un plan de marcado de la misma manera que asigna directivas.</span><span class="sxs-lookup"><span data-stu-id="2b6ee-138">You assign a dial plan in the same way you assign policies.</span></span> [!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="using-powershell"></a><span data-ttu-id="2b6ee-139">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="2b6ee-139">Using PowerShell</span></span>
  
### <a name="start-powershell"></a><span data-ttu-id="2b6ee-140">Iniciar PowerShell</span><span class="sxs-lookup"><span data-stu-id="2b6ee-140">Start PowerShell</span></span>
- <span data-ttu-id="2b6ee-141">Abra un Windows PowerShell de comandos y ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="2b6ee-141">Open a Windows PowerShell command prompt and run the following commands:</span></span>

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```
  
### <a name="create-and-manage-your-dial-plans"></a><span data-ttu-id="2b6ee-142">Crear y administrar los planes de marcado</span><span class="sxs-lookup"><span data-stu-id="2b6ee-142">Create and manage your dial plans</span></span>

<span data-ttu-id="2b6ee-143">Para crear y administrar planes de marcado de inquilino puede utilizar un cmdlet sencillo o un script de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2b6ee-143">You can either use a single cmdlet or a PowerShell script to create and manage tenant dial plans.</span></span>
  
#### <a name="using-single-cmdlets"></a><span data-ttu-id="2b6ee-144">Uso de cmdlets sencillos</span><span class="sxs-lookup"><span data-stu-id="2b6ee-144">Using single cmdlets</span></span>

- <span data-ttu-id="2b6ee-145">Para crear un nuevo plan de marcado, ejecute:</span><span class="sxs-lookup"><span data-stu-id="2b6ee-145">To create a new dial plan, run:</span></span>
    
  ```PowerShell
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="2b6ee-146">Para ver otros ejemplos y parámetros, consulte [Nuevo-CsPlanMarcadoInquilinio](/powershell/module/skype/new-cstenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="2b6ee-146">For other examples and parameters, see [New-CsTenantDialPlan](/powershell/module/skype/new-cstenantdialplan).</span></span>
    
- <span data-ttu-id="2b6ee-147">Para editar la configuración de un plan de marcado existente, ejecute:</span><span class="sxs-lookup"><span data-stu-id="2b6ee-147">To edit the settings of an existing dial plan, run:</span></span>
    
  ```PowerShell
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="2b6ee-148">Para ver otros ejemplos y parámetros, consulte[Configurar-CsPlanMarcadoInquilino](/powershell/module/skype/set-cstenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="2b6ee-148">For other examples and parameters, see [Set-CsTenantDialPlan](/powershell/module/skype/set-cstenantdialplan).</span></span>
    
- <span data-ttu-id="2b6ee-149">Para agregar usuarios a un plan de marcado, ejecute:</span><span class="sxs-lookup"><span data-stu-id="2b6ee-149">To add users to a dial plan, run:</span></span>
    
  ```PowerShell
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    <span data-ttu-id="2b6ee-150">Para ver otros ejemplos y parámetros, consulte [Garantizar-CsPlanMarcadoInquilino](/powershell/module/skype/grant-cstenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="2b6ee-150">For other examples and parameters, see [Grant-CsTenantDialPlan](/powershell/module/skype/grant-cstenantdialplan).</span></span>
    
- <span data-ttu-id="2b6ee-151">Para ver la configuración de un plan de marcado, ejecute:</span><span class="sxs-lookup"><span data-stu-id="2b6ee-151">To view the settings on a dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    <span data-ttu-id="2b6ee-152">Para ver otros ejemplos y parámetros, consulte[Obtener-CsPlanMarcadoInquilino](/powershell/module/skype/get-cstenantdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="2b6ee-152">For other examples and parameters, see [Get-CsTenantDialPlan](/powershell/module/skype/get-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="2b6ee-153">Para eliminar un plan de marcado, ejecute:</span><span class="sxs-lookup"><span data-stu-id="2b6ee-153">To delete a dial plan, run:</span></span>
    
  ```PowerShell
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    <span data-ttu-id="2b6ee-154">Para ver otros ejemplos y parámetros, consulte [Eliminar-CsPlanMarcadoInquilino](/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="2b6ee-154">For other examples and parameters, see [Remove-CsTenantDialPlan](/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="2b6ee-155">Para ver la configuración del plan de marcado efectivo, ejecute:</span><span class="sxs-lookup"><span data-stu-id="2b6ee-155">To see the settings of the effective dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="2b6ee-156">Para ver otros ejemplos y parámetros, consulte [Obtener-CsPlanMarcadoEfectivoInquilino](/powershell/module/skype/get-cseffectivetenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="2b6ee-156">For other examples and parameters, see [Get-CsEffectiveTenantDialPlan](/powershell/module/skype/get-cseffectivetenantdialplan).</span></span>
    
- <span data-ttu-id="2b6ee-157">Para evaluar la configuración efectiva de un plan de marcado, ejecute:</span><span class="sxs-lookup"><span data-stu-id="2b6ee-157">To test the effective settings of a dial plan, run:</span></span>
    
  ```PowerShell
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="2b6ee-158">Para ver otros ejemplos y parámetros, consulte [Probar-CsPlanMarcadoEfectivoInquilino](/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="2b6ee-158">For other examples and parameters, see [Test-CsEffectiveTenantDialPlan](/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).</span></span>
    
#### <a name="using-a-powershell-script"></a><span data-ttu-id="2b6ee-159">Uso de un script de PowerShell</span><span class="sxs-lookup"><span data-stu-id="2b6ee-159">Using a PowerShell script</span></span>

<span data-ttu-id="2b6ee-160">Ejecute esto para eliminar una regla de normalización asociada a un plan de marcado de inquilino sin tener que eliminar primero el plan de marcado de inquilino:</span><span class="sxs-lookup"><span data-stu-id="2b6ee-160">Run this to delete a normalization rule that is associated with a tenant dial plan without needing to delete the tenant dial plan first:</span></span>
```PowerShell
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
<span data-ttu-id="2b6ee-161">Ejecute esto para agregar la siguiente regla de normalización al plan de marcado inquilino existente denominado RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="2b6ee-161">Run this to add the following normalization rule to the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
<span data-ttu-id="2b6ee-162">Ejecute esto para eliminar la siguiente regla de normalización del plan de marcado inquilino existente denominado RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="2b6ee-162">Run this to remove the following normalization rule from the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="2b6ee-163">Ejecute lo siguiente cuando desee examinar también las reglas de normalización existentes, determine cuál desea eliminar y, a continuación, use su índice para quitarlo.</span><span class="sxs-lookup"><span data-stu-id="2b6ee-163">Run the following when you want to also examine the existing normalization rules, determine which one you want to delete, and then use its index to remove it.</span></span> <span data-ttu-id="2b6ee-164">La matriz de reglas de normalización comienza con el índice 0.</span><span class="sxs-lookup"><span data-stu-id="2b6ee-164">The array of normalization rules starts with index 0.</span></span> <span data-ttu-id="2b6ee-165">Nos gustaría eliminar la regla de normalización de tres dígitos, por lo que se trata del índice 1.</span><span class="sxs-lookup"><span data-stu-id="2b6ee-165">We would like to remove the 3-digit normalization rule, so that is index 1.</span></span>
  
```PowerShell
Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules
Description         : 4-digit
Pattern             : ^(\\d{4})$
Translation         : +1426666$1
Name                : NR2
IsInternalExtension : False

Description         : 3-digit
Pattern             : ^(\\d{3})$
Translation         : +14255551$1
Name                : NR12
IsInternalExtension : False

$nr1=(Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules[1]
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="2b6ee-166">Ejecute esto para buscar todos los usuarios a los que se les ha garantizado el plan de marcado inquilino RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="2b6ee-166">Run this to find all users who have been granted the RedmondDialPlan tenant dial plan.</span></span>
  
```PowerShell
Get-CsOnlineUser | Where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

<span data-ttu-id="2b6ee-167">Ejecute esto para quitar cualquier TenantDialPlan asignado de todos los usuarios que tienen un HostProvider de sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="2b6ee-167">Run this to remove any assigned TenantDialPlan from all users who have a HostingProvider of sipfed.online.lync.com.</span></span>
```PowerShell
Get-CsOnlineUser -Filter {HostingProvider -eq "sipfed.online.lync.com"} | Grant-CsTenantDialPlan -policyname $null
```

<span data-ttu-id="2b6ee-168">Ejecute estos para agregar el plan de marcado local existente denominado OPDP1 como un plan de marcado inquilino para su organización.</span><span class="sxs-lookup"><span data-stu-id="2b6ee-168">Run these to add the existing on-premises dial plan named OPDP1 as a tenant dial plan for your organization.</span></span> <span data-ttu-id="2b6ee-169">Primero debe guardar el plan de marcado local en un archivo .xml local y, a continuación, usarlo para crear el nuevo plan de marcado de inquilino.</span><span class="sxs-lookup"><span data-stu-id="2b6ee-169">You need to first save the on-premises dial plan to an .xml file, and then use it to create the new tenant dial plan.</span></span>
  
<span data-ttu-id="2b6ee-170">Ejecute esto para guardar el plan de marcado local en el .xml local.</span><span class="sxs-lookup"><span data-stu-id="2b6ee-170">Run this to save the on-premises dial plan to the .xml file.</span></span>
  
```PowerShell
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

<span data-ttu-id="2b6ee-171">Ejecute esto para crear el nuevo plan de marcado inquilino.</span><span class="sxs-lookup"><span data-stu-id="2b6ee-171">Run this to create the new tenant dial plan.</span></span>
  
```PowerShell
$DPFileName = "dialplan.xml"
$dp = Import-Clixml $DPFileName
$NormRules = @()
ForEach($nr in $dp.NormalizationRules)
{
 $id1 = "Global/" + $nr.Name
 $nr2 = New-CsVoiceNormalizationRule -Identity $id1 -Description $nr.Description -Pattern $nr.Pattern -Translation $nr.Translation -IsInternalExtension $nr.IsInternalExtension -InMemory
 $NormRules += $nr2
}
New-CsTenantDialPlan -Identity $dp.SimpleName -ExternalAccessPrefix $dp.ExternalAccessPrefix -Description $dp.Description -OptimizeDeviceDialing $dp.OptimizeDeviceDialing -SimpleName $dp.SimpleName -NormalizationRules $NormRules
```
    
## <a name="related-topics"></a><span data-ttu-id="2b6ee-172">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="2b6ee-172">Related topics</span></span>

- [<span data-ttu-id="2b6ee-173">¿Qué son los planes de marcado?</span><span class="sxs-lookup"><span data-stu-id="2b6ee-173">What are dial plans?</span></span>](what-are-dial-plans.md)
- [<span data-ttu-id="2b6ee-174">Preguntas comunes sobre la transferencia de números de teléfono</span><span class="sxs-lookup"><span data-stu-id="2b6ee-174">Transferring phone numbers common questions</span></span>](./phone-number-calling-plans/port-order-overview.md)
- [<span data-ttu-id="2b6ee-175">Diferentes tipos de números de teléfono que se usan para Planes de llamada</span><span class="sxs-lookup"><span data-stu-id="2b6ee-175">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [<span data-ttu-id="2b6ee-176">Administrar los números de teléfono para su organización</span><span class="sxs-lookup"><span data-stu-id="2b6ee-176">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [<span data-ttu-id="2b6ee-177">Términos y condiciones de las llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="2b6ee-177">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)
- <span data-ttu-id="2b6ee-178">[Etiqueta de declinación de responsabilidades de llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="2b6ee-178">[Emergency calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
- [<span data-ttu-id="2b6ee-179">Descripción de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="2b6ee-179">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
