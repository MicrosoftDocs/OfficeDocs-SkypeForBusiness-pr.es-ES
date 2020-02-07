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
description: Aprenda a crear y administrar planes de marcado de llamada (planes de marcado de llamadas RTC) y a administrarlos.
ms.openlocfilehash: 774b0a78f39b91b634ed0833be3497935cb25c4f
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41826928"
---
# <a name="create-and-manage-dial-plans"></a><span data-ttu-id="6c3ab-103">Crear y administrar planes de marcado</span><span class="sxs-lookup"><span data-stu-id="6c3ab-103">Create and manage dial plans</span></span>

<span data-ttu-id="6c3ab-104">Después de planear los planes de marcado de su organización y de haber averiguado todas las reglas de normalización que deben crearse para el enrutamiento de llamadas, ya está listo para crear los planes de marcado.</span><span class="sxs-lookup"><span data-stu-id="6c3ab-104">After you plan the dial plans for your organization and figured out all the normalization rules that need to be created for call routing, you're ready to create the dial plans.</span></span> <span data-ttu-id="6c3ab-105">Puede usar el centro de administración de Microsoft Teams o Windows PowerShell para crear y administrar planes de marcado.</span><span class="sxs-lookup"><span data-stu-id="6c3ab-105">You can use the Microsoft Teams admin center or Windows PowerShell to create and manage dial plans.</span></span>  

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="6c3ab-106">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6c3ab-106">Using the Microsoft Teams admin center</span></span>

### <a name="create-a-dial-plan"></a><span data-ttu-id="6c3ab-107">Crear un plan de marcado</span><span class="sxs-lookup"><span data-stu-id="6c3ab-107">Create a dial plan</span></span>

1. <span data-ttu-id="6c3ab-108">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a**plan de marcado**de **voz** > .</span><span class="sxs-lookup"><span data-stu-id="6c3ab-108">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="6c3ab-109">Haga clic en **Agregar**y, a continuación, escriba un nombre y una descripción para el plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="6c3ab-109">Click **Add**, and then enter a name and description for the dial plan.</span></span>
    <span data-ttu-id="6c3ab-110">![Captura de pantalla que muestra la página Agregar para crear un plan de marcado](media/create-dial-plan.png)</span><span class="sxs-lookup"><span data-stu-id="6c3ab-110">![Screenshot showing the Add page for creating a dial plan](media/create-dial-plan.png)</span></span>
3. <span data-ttu-id="6c3ab-111">En **detalles del plan de marcado**, especifique un prefijo de marcado externo si los usuarios necesitan marcar uno o varios dígitos iniciales adicionales (por ejemplo, 9) para obtener una línea externa.</span><span class="sxs-lookup"><span data-stu-id="6c3ab-111">Under **Dial plan details**, specify an external dialing prefix if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span> <span data-ttu-id="6c3ab-112">Para ello, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6c3ab-112">To do this:</span></span>
    1. <span data-ttu-id="6c3ab-113">En el cuadro **Prefijo de marcado externo** , escriba un prefijo de marcado externo.</span><span class="sxs-lookup"><span data-stu-id="6c3ab-113">In the **External dialing prefix** box, enter an external dialing prefix.</span></span> <span data-ttu-id="6c3ab-114">El prefijo puede tener un máximo de cuatro caracteres (#, \* y 0-9).</span><span class="sxs-lookup"><span data-stu-id="6c3ab-114">The prefix can be up to four characters (#,\*, and 0-9).</span></span>
    2. <span data-ttu-id="6c3ab-115">Activar el **marcado de dispositivo optimizado**.</span><span class="sxs-lookup"><span data-stu-id="6c3ab-115">Turn on **Optimized device dialing**.</span></span> <span data-ttu-id="6c3ab-116">Si especifica un prefijo de marcado externo, también debe activar esta opción para aplicar el prefijo, de modo que las llamadas se hagan fuera de su organización.</span><span class="sxs-lookup"><span data-stu-id="6c3ab-116">If you specify an external dialing prefix, you must also turn on this setting to apply the prefix so calls can be made outside your organization.</span></span>
4. <span data-ttu-id="6c3ab-117">En **reglas de normalización**, configure y asocie una o más [reglas de normalización](what-are-dial-plans.md#normalization-rules) para el plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="6c3ab-117">Under **Normalization rules**, configure and associate one or more [normalization rules](what-are-dial-plans.md#normalization-rules) for the dial plan.</span></span> <span data-ttu-id="6c3ab-118">Cada plan de marcado debe tener al menos una regla de normalización asociada.</span><span class="sxs-lookup"><span data-stu-id="6c3ab-118">Each dial plan must have at least one normalization rule associated with it.</span></span>  <span data-ttu-id="6c3ab-119">Para ello, siga uno o varios de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="6c3ab-119">To do this, do one or more of the following:</span></span>
    - <span data-ttu-id="6c3ab-120">Para crear una nueva regla de normalización y asociarla con el plan de marcado, haga clic en **Agregar**y, a continuación, defina la regla.</span><span class="sxs-lookup"><span data-stu-id="6c3ab-120">To create a new normalization rule and associate it with the dial plan, click **Add**, and then define the rule.</span></span>
    - <span data-ttu-id="6c3ab-121">Para editar una regla de normalización que ya está asociada con el plan de marcado, seleccione la regla haciendo clic a la izquierda del nombre de la regla y, a continuación, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="6c3ab-121">To edit a normalization rule that's already associated with the dial plan, select the rule by clicking to the left of the rule name, and then click **Edit**.</span></span> <span data-ttu-id="6c3ab-122">Realice los cambios que desee y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6c3ab-122">Make the changes you want, and then click **Save**.</span></span>
    - <span data-ttu-id="6c3ab-123">Para quitar una regla de normalización del plan de marcado, seleccione la regla haciendo clic a la izquierda del nombre de la regla y, a continuación, haga clic en **quitar**.</span><span class="sxs-lookup"><span data-stu-id="6c3ab-123">To remove a normalization rule from the dial plan, select the rule by clicking to the left of the rule name, and then click **Remove**.</span></span>
5. <span data-ttu-id="6c3ab-124">Organice las reglas de normalización en el orden que desee.</span><span class="sxs-lookup"><span data-stu-id="6c3ab-124">Arrange the normalization rules in the order that you want.</span></span> <span data-ttu-id="6c3ab-125">Haga clic en **subir** o **bajar** para cambiar la posición de las reglas de la lista.</span><span class="sxs-lookup"><span data-stu-id="6c3ab-125">Click **Move up** or **Move down** to change the position of rules in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6c3ab-126">Teams recorre la lista de reglas de normalización de la parte superior hacia abajo y usa la primera regla que coincida con el número marcado.</span><span class="sxs-lookup"><span data-stu-id="6c3ab-126">Teams traverses the list of normalization rules from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="6c3ab-127">Si configura un plan de marcado para que un número marcado pueda coincidir con más de una regla de normalización, asegúrese de que las reglas más restrictivas se ordenan por encima de las menos restrictivas.</span><span class="sxs-lookup"><span data-stu-id="6c3ab-127">If you set up a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span>

6. <span data-ttu-id="6c3ab-128">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="6c3ab-128">Click **Save**.</span></span>
7. <span data-ttu-id="6c3ab-129">Si desea probar el plan de marcado, en **plan de marcado de prueba**, escriba un número de teléfono y, a continuación, haga clic en **prueba**.</span><span class="sxs-lookup"><span data-stu-id="6c3ab-129">If you want to test the dial plan, under **Test dial plan**, enter a phone number, and then click **Test**.</span></span>

### <a name="edit-a-dial-plan"></a><span data-ttu-id="6c3ab-130">Editar un plan de marcado</span><span class="sxs-lookup"><span data-stu-id="6c3ab-130">Edit a dial plan</span></span>

1. <span data-ttu-id="6c3ab-131">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a**plan de marcado**de **voz** > .</span><span class="sxs-lookup"><span data-stu-id="6c3ab-131">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="6c3ab-132">Seleccione el plan de marcado haciendo clic a la izquierda del nombre del plan de marcado y, a continuación, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="6c3ab-132">Select the dial plan by clicking to the left of the dial plan name, and then click **Edit**.</span></span>
3. <span data-ttu-id="6c3ab-133">Realice los cambios que desee y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6c3ab-133">Make the changes that you want, and then click **Save**.</span></span>

### <a name="add-users-to-a-dial-plan"></a><span data-ttu-id="6c3ab-134">Agregar usuarios a un plan de marcado</span><span class="sxs-lookup"><span data-stu-id="6c3ab-134">Add users to a dial plan</span></span>

1. <span data-ttu-id="6c3ab-135">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a**plan de marcado**de **voz** > .</span><span class="sxs-lookup"><span data-stu-id="6c3ab-135">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="6c3ab-136">Seleccione el plan de marcado haciendo clic a la izquierda del nombre del plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="6c3ab-136">Select the dial plan by clicking to the left of the dial plan name.</span></span>
3. <span data-ttu-id="6c3ab-137">Seleccione **administrar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="6c3ab-137">Select **Manage users**.</span></span>
4. <span data-ttu-id="6c3ab-138">En el panel **administrar usuarios** , busque el usuario por nombre para mostrar o por nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="6c3ab-138">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="6c3ab-139">Repita este paso para cada usuario que desee agregar.</span><span class="sxs-lookup"><span data-stu-id="6c3ab-139">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="6c3ab-140">Cuando haya terminado de agregar usuarios, seleccione **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="6c3ab-140">When you're finished adding users, select **Apply**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="6c3ab-141">Usar PowerShell</span><span class="sxs-lookup"><span data-stu-id="6c3ab-141">Using PowerShell</span></span>
  
### <a name="verify-and-start-remote-powershell"></a><span data-ttu-id="6c3ab-142">Comprobar e iniciar PowerShell remoto</span><span class="sxs-lookup"><span data-stu-id="6c3ab-142">Verify and start Remote PowerShell</span></span>

 <span data-ttu-id="6c3ab-143">**Comprobar que está ejecutando Windows PowerShell versión 3,0 o posterior**</span><span class="sxs-lookup"><span data-stu-id="6c3ab-143">**Check that you are running Windows PowerShell version 3.0 or later**</span></span>
  
1. <span data-ttu-id="6c3ab-144">Para comprobar que está ejecutando la versión 3,0 o superior: **menú** > inicio de**Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="6c3ab-144">To verify that you're running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="6c3ab-145">Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="6c3ab-145">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="6c3ab-146">Si no tiene la versión 3,0 o posterior, descargue e instale las actualizaciones de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6c3ab-146">If you don't have version 3.0 or later, download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="6c3ab-147">Vea [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) para descargar y actualizar Windows PowerShell a la versión 4,0.</span><span class="sxs-lookup"><span data-stu-id="6c3ab-147">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="6c3ab-148">Reinicie el equipo cuando se le pida.</span><span class="sxs-lookup"><span data-stu-id="6c3ab-148">Restart your computer when you're prompted.</span></span>
    
4. <span data-ttu-id="6c3ab-149">También tendrá que instalar el módulo Windows PowerShell para Skype empresarial online que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="6c3ab-149">You'll also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="6c3ab-150">Puede descargar este módulo, que solo se admite en equipos de 64 de bits, en el [módulo de Windows PowerShell para Skype empresarial online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="6c3ab-150">You can download this module, which is supported only on 64-bit computers, at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="6c3ab-151">Reinicie el equipo si se le pide.</span><span class="sxs-lookup"><span data-stu-id="6c3ab-151">Restart your computer if you're prompted.</span></span>
    
<span data-ttu-id="6c3ab-152">Para obtener más información, vea [conectarse a todos los servicios de Office 365 en una sola ventana de Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="6c3ab-152">To learn more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>
  
 <span data-ttu-id="6c3ab-153">**Iniciar una sesión de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="6c3ab-153">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="6c3ab-154">Haga clic en **iniciar** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="6c3ab-154">Click **Start** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="6c3ab-155">En la ventana **Windows PowerShell**, puede conectarse a su organización de Office 365 ejecutando:</span><span class="sxs-lookup"><span data-stu-id="6c3ab-155">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6c3ab-156">Solo tiene que ejecutar el comando **Import-Module** la primera vez que use el módulo Windows PowerShell de Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="6c3ab-156">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
  

    ```PowerShell
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
    ```
  
### <a name="create-and-manage-your-dial-plans"></a><span data-ttu-id="6c3ab-157">Crear y administrar los planes de marcado</span><span class="sxs-lookup"><span data-stu-id="6c3ab-157">Create and manage your dial plans</span></span>

<span data-ttu-id="6c3ab-158">Para crear y administrar planes de marcado de inquilino puede utilizar un cmdlet sencillo o un script de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6c3ab-158">You can either use a single cmdlet or a PowerShell script to create and manage tenant dial plans.</span></span>
  
#### <a name="using-single-cmdlets"></a><span data-ttu-id="6c3ab-159">Uso de cmdlets sencillos</span><span class="sxs-lookup"><span data-stu-id="6c3ab-159">Using single cmdlets</span></span>

- <span data-ttu-id="6c3ab-160">Para crear un nuevo plan de marcado, ejecute:</span><span class="sxs-lookup"><span data-stu-id="6c3ab-160">To create a new dial plan, run:</span></span>
    
  ```PowerShell
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="6c3ab-161">Para ver otros ejemplos y parámetros, consulte [Nuevo-CsPlanMarcadoInquilinio](https://docs.microsoft.com/powershell/module/skype/new-cstenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="6c3ab-161">For other examples and parameters, see [New-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/new-cstenantdialplan).</span></span>
    
- <span data-ttu-id="6c3ab-162">Para editar la configuración de un plan de marcado existente, ejecute:</span><span class="sxs-lookup"><span data-stu-id="6c3ab-162">To edit the settings of an existing dial plan, run:</span></span>
    
  ```PowerShell
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="6c3ab-163">Para ver otros ejemplos y parámetros, consulte[Configurar-CsPlanMarcadoInquilino](https://docs.microsoft.com/powershell/module/skype/set-cstenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="6c3ab-163">For other examples and parameters, see [Set-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/set-cstenantdialplan).</span></span>
    
- <span data-ttu-id="6c3ab-164">Para agregar usuarios a un plan de marcado, ejecute:</span><span class="sxs-lookup"><span data-stu-id="6c3ab-164">To add users to a dial plan, run:</span></span>
    
  ```PowerShell
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    <span data-ttu-id="6c3ab-165">Para ver otros ejemplos y parámetros, consulte [Garantizar-CsPlanMarcadoInquilino](https://docs.microsoft.com/powershell/module/skype/grant-cstenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="6c3ab-165">For other examples and parameters, see [Grant-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-cstenantdialplan).</span></span>
    
- <span data-ttu-id="6c3ab-166">Para ver la configuración de un plan de marcado, ejecute:</span><span class="sxs-lookup"><span data-stu-id="6c3ab-166">To view the settings on a dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    <span data-ttu-id="6c3ab-167">Para ver otros ejemplos y parámetros, consulte[Obtener-CsPlanMarcadoInquilino](https://docs.microsoft.com/powershell/module/skype/get-cstenantdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="6c3ab-167">For other examples and parameters, see [Get-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="6c3ab-168">Para eliminar un plan de marcado, ejecute:</span><span class="sxs-lookup"><span data-stu-id="6c3ab-168">To delete a dial plan, run:</span></span>
    
  ```PowerShell
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    <span data-ttu-id="6c3ab-169">Para ver otros ejemplos y parámetros, consulte [Eliminar-CsPlanMarcadoInquilino](https://docs.microsoft.com/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="6c3ab-169">For other examples and parameters, see [Remove-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="6c3ab-170">Para ver la configuración del plan de marcado efectivo, ejecute:</span><span class="sxs-lookup"><span data-stu-id="6c3ab-170">To see the settings of the effective dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="6c3ab-171">Para ver otros ejemplos y parámetros, consulte [Obtener-CsPlanMarcadoEfectivoInquilino](https://docs.microsoft.com/powershell/module/skype/get-cseffectivetenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="6c3ab-171">For other examples and parameters, see [Get-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cseffectivetenantdialplan).</span></span>
    
- <span data-ttu-id="6c3ab-172">Para evaluar la configuración efectiva de un plan de marcado, ejecute:</span><span class="sxs-lookup"><span data-stu-id="6c3ab-172">To test the effective settings of a dial plan, run:</span></span>
    
  ```PowerShell
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="6c3ab-173">Para ver otros ejemplos y parámetros, consulte [Probar-CsPlanMarcadoEfectivoInquilino](https://docs.microsoft.com/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="6c3ab-173">For other examples and parameters, see [Test-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).</span></span>
    
#### <a name="using-a-powershell-script"></a><span data-ttu-id="6c3ab-174">Uso de un script de PowerShell</span><span class="sxs-lookup"><span data-stu-id="6c3ab-174">Using a PowerShell script</span></span>

<span data-ttu-id="6c3ab-175">Ejecute esto para eliminar una regla de normalización asociada a un plan de marcado de inquilino sin necesidad de eliminar primero el plan de marcado de inquilino:</span><span class="sxs-lookup"><span data-stu-id="6c3ab-175">Run this to delete a normalization rule that is associated with a tenant dial plan without needing to delete the tenant dial plan first:</span></span>
```PowerShell
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
<span data-ttu-id="6c3ab-176">Ejecute esto para agregar la siguiente regla de normalización al plan de marcado inquilino existente denominado RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="6c3ab-176">Run this to add the following normalization rule to the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
<span data-ttu-id="6c3ab-177">Ejecute esto para eliminar la siguiente regla de normalización del plan de marcado inquilino existente denominado RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="6c3ab-177">Run this to remove the following normalization rule from the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="6c3ab-178">Ejecute lo siguiente cuando desee examinar también las reglas de normalización existentes, determinar la que desea eliminar y, a continuación, usar su índice para quitarla.</span><span class="sxs-lookup"><span data-stu-id="6c3ab-178">Run the following when you want to also examine the existing normalization rules, determine which one you want to delete, and then use its index to remove it.</span></span> <span data-ttu-id="6c3ab-179">La matriz de reglas de normalización comienza con el índice 0.</span><span class="sxs-lookup"><span data-stu-id="6c3ab-179">The array of normalization rules starts with index 0.</span></span> <span data-ttu-id="6c3ab-180">Nos gustaría eliminar la regla de normalización de tres dígitos, por lo que se trata del índice 1.</span><span class="sxs-lookup"><span data-stu-id="6c3ab-180">We would like to remove the 3-digit normalization rule, so that is index 1.</span></span>
  
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

<span data-ttu-id="6c3ab-181">Ejecute esto para buscar todos los usuarios a los que se les ha garantizado el plan de marcado inquilino RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="6c3ab-181">Run this to find all users who have been granted the RedmondDialPlan tenant dial plan.</span></span>
  
```PowerShell
Get-CsOnlineUser | Where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

<span data-ttu-id="6c3ab-182">Ejecute esto para quitar todos los TenantDialPlan asignados de todos los usuarios que tienen una Hostingprovider manda de sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="6c3ab-182">Run this to remove any assigned TenantDialPlan from all users who have a HostingProvider of sipfed.online.lync.com.</span></span>
```PowerShell
Get-CsOnlineUser -Filter {HostingProvider -eq “sipfed.online.lync.com”} | Grant-CsTenantDialPlan -policyname $null
```

<span data-ttu-id="6c3ab-183">Ejecute estos para agregar el plan de marcado local existente denominado OPDP1 como un plan de marcado inquilino para su organización.</span><span class="sxs-lookup"><span data-stu-id="6c3ab-183">Run these to add the existing on-premises dial plan named OPDP1 as a tenant dial plan for your organization.</span></span> <span data-ttu-id="6c3ab-184">Primero debe guardar el plan de marcado local en un archivo. XML y, a continuación, usarlo para crear el nuevo plan de marcado de inquilino.</span><span class="sxs-lookup"><span data-stu-id="6c3ab-184">You need to first save the on-premises dial plan to an .xml file, and then use it to create the new tenant dial plan.</span></span>
  
<span data-ttu-id="6c3ab-185">Ejecute esto para guardar el plan de marcado local en el archivo. Xml.</span><span class="sxs-lookup"><span data-stu-id="6c3ab-185">Run this to save the on-premises dial plan to the .xml file.</span></span>
  
```PowerShell
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

<span data-ttu-id="6c3ab-186">Ejecute esto para crear el nuevo plan de marcado inquilino.</span><span class="sxs-lookup"><span data-stu-id="6c3ab-186">Run this to create the new tenant dial plan.</span></span>
  
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
    
## <a name="related-topics"></a><span data-ttu-id="6c3ab-187">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="6c3ab-187">Related topics</span></span>

- [<span data-ttu-id="6c3ab-188">¿Qué son los planes de marcado?</span><span class="sxs-lookup"><span data-stu-id="6c3ab-188">What are dial plans?</span></span>](what-are-dial-plans.md)
- [<span data-ttu-id="6c3ab-189">Preguntas comunes sobre la transferencia de números de teléfono</span><span class="sxs-lookup"><span data-stu-id="6c3ab-189">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)
- [<span data-ttu-id="6c3ab-190">Diferentes tipos de números de teléfono que se usan para Planes de llamada</span><span class="sxs-lookup"><span data-stu-id="6c3ab-190">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [<span data-ttu-id="6c3ab-191">Administrar los números de teléfono para su organización</span><span class="sxs-lookup"><span data-stu-id="6c3ab-191">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [<span data-ttu-id="6c3ab-192">Términos y condiciones de las llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="6c3ab-192">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)
- <span data-ttu-id="6c3ab-193">[Etiqueta de renuncia para llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="6c3ab-193">[Emergency calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
- [<span data-ttu-id="6c3ab-194">Descripción de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="6c3ab-194">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
