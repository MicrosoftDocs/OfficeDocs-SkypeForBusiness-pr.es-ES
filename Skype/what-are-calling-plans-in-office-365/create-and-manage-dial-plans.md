---
title: Crear y administrar planes de marcado
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 7af17c94-5f8f-4452-ae1d-01f495b4dc94
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Calling Plans
- Strat_SB_PSTN
description: "Aprenda cómo crear planes de marcación de llamada (llamada RTC planes de marcado) en Office 365 y cómo administrarlos. "
ms.openlocfilehash: 890ea8193f72301aef9ef0d4feacd2d259bba2b4
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="create-and-manage-dial-plans"></a><span data-ttu-id="c424f-103">Crear y administrar planes de marcado</span><span class="sxs-lookup"><span data-stu-id="c424f-103">Create and manage dial plans</span></span>

<span data-ttu-id="c424f-104">Después de haber planeado los planes de marcado para su organización e imaginado todas las reglas de normalización que deben crearse para el enrutamiento de llamadas, debe usar Windows PowerShell para crear los planes de marcado y realice los cambios de configuración.</span><span class="sxs-lookup"><span data-stu-id="c424f-104">After you have planned the dial plans for your organization and figured out all of the normalization rules that need to be created for call routing, you will need to use Windows PowerShell to create the dial plans and make any setting changes.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c424f-105">No se puede utilizar el Skype para el centro de administración de negocios para crear y administrar planes de marcado.</span><span class="sxs-lookup"><span data-stu-id="c424f-105">The Skype for Business admin center can't be used for creating and managing dial plans.</span></span> 
  
## <a name="verifying-and-starting-remote-powershell"></a><span data-ttu-id="c424f-106">Comprobar e iniciar PowerShell remoto</span><span class="sxs-lookup"><span data-stu-id="c424f-106">Verifying and starting Remote PowerShell</span></span>

 <span data-ttu-id="c424f-107">**Comprobar que está ejecutando Windows PowerShell versión 3.0 o superior**</span><span class="sxs-lookup"><span data-stu-id="c424f-107">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
  
1. <span data-ttu-id="c424f-108">Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="c424f-108">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="c424f-109">Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="c424f-109">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="c424f-p101">Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell. Vea [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para descargar y actualizar Windows PowerShell a la versión 4.0. Reinicie el equipo cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="c424f-p101">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="c424f-p102">También necesitará instalar el módulo Windows PowerShell para Skype Empresarial Online que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype Empresarial Online. Este módulo, que solo se admite en equipos de 64 bits, puede descargarse desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=294688). Reinicie el equipo cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="c424f-p102">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
<span data-ttu-id="c424f-116">Si necesita más información, consulte [Conectarse a todos los servicios de Office 365 en una única ventana de Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="c424f-116">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
  
 <span data-ttu-id="c424f-117">**Iniciar una sesión de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="c424f-117">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="c424f-118">En el **menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="c424f-118">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="c424f-119">En la ventana **Windows PowerShell**, puede conectarse a su organización de Office 365 ejecutando:</span><span class="sxs-lookup"><span data-stu-id="c424f-119">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c424f-120">Solo tiene que ejecutar el comando **Import-Module** la primera vez que use el módulo Windows PowerShell de Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="c424f-120">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
  
> 
  ```
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

<span data-ttu-id="c424f-121">Si desea obtener más información acerca de cómo iniciar Windows PowerShell, vea [Conectar con todos los servicios de Office 365 en una sola ventana de Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) o [conectarse a Skype para los negocios en línea mediante el uso de Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="c424f-121">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
  
## <a name="creating-and-managing-your-dial-plans"></a><span data-ttu-id="c424f-122">Creación y administración de los planes de marcado</span><span class="sxs-lookup"><span data-stu-id="c424f-122">Creating and managing your dial plans</span></span>

<span data-ttu-id="c424f-123">Puede utilizar un cmdlet único o un script de PowerShell para crear y administrar planes de marcado de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="c424f-123">You can either use a single cmdlet or a PowerShell script to create and manage tenant dial plans.</span></span>
  
### <a name="using-single-cmdlets"></a><span data-ttu-id="c424f-124">Uso de cmdlets único</span><span class="sxs-lookup"><span data-stu-id="c424f-124">Using single cmdlets</span></span>

- <span data-ttu-id="c424f-125">Para crear un nuevo plan de marcado, ejecute:</span><span class="sxs-lookup"><span data-stu-id="c424f-125">To create a new dial plan, run:</span></span>
    
  ```
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="c424f-126">Otros parámetros y ejemplos, vea [New-CsTenantDialPlan](https://technet.microsoft.com/library/mt775026.aspx).</span><span class="sxs-lookup"><span data-stu-id="c424f-126">For other examples and parameters, see [New-CsTenantDialPlan](https://technet.microsoft.com/library/mt775026.aspx).</span></span>
    
- <span data-ttu-id="c424f-127">Para realizar cambios de configuración en un plan de marcado existente, ejecute:</span><span class="sxs-lookup"><span data-stu-id="c424f-127">To make setting changes to an existing dial plan, run:</span></span>
    
  ```
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="c424f-128">Para otros ejemplos y parámetros, consulte [Set-CsTenantDialPlan](https://technet.microsoft.com/library/mt775023.aspx).</span><span class="sxs-lookup"><span data-stu-id="c424f-128">For other examples and parameters, see [Set-CsTenantDialPlan](https://technet.microsoft.com/library/mt775023.aspx).</span></span>
    
- <span data-ttu-id="c424f-129">Para agregar usuarios a un plan de marcado, ejecute:</span><span class="sxs-lookup"><span data-stu-id="c424f-129">To add users to a dial plan, run:</span></span>
    
  ```
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    <span data-ttu-id="c424f-130">Otros parámetros y ejemplos, vea [CsTenantDialPlan de concesión](https://technet.microsoft.com/library/mt775021.aspx).</span><span class="sxs-lookup"><span data-stu-id="c424f-130">For other examples and parameters, see [Grant-CsTenantDialPlan](https://technet.microsoft.com/library/mt775021.aspx).</span></span>
    
- <span data-ttu-id="c424f-131">Para ver la configuración de un plan de marcado, ejecute:</span><span class="sxs-lookup"><span data-stu-id="c424f-131">To view the settings on a dial plan, run:</span></span>
    
  ```
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    <span data-ttu-id="c424f-132">Otros parámetros y ejemplos, vea [Get-CsTenantDialPlan](https://technet.microsoft.com/library/mt775024.aspx).</span><span class="sxs-lookup"><span data-stu-id="c424f-132">For other examples and parameters, see [Get-CsTenantDialPlan](https://technet.microsoft.com/library/mt775024.aspx).</span></span>
    
- <span data-ttu-id="c424f-133">Para eliminar un plan de marcado, ejecute:</span><span class="sxs-lookup"><span data-stu-id="c424f-133">To delete a dial plan, run:</span></span>
    
  ```
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    <span data-ttu-id="c424f-134">Otros parámetros y ejemplos, vea [Quitar CsTenantDialPlan](https://technet.microsoft.com/library/mt775020.aspx).</span><span class="sxs-lookup"><span data-stu-id="c424f-134">For other examples and parameters, see [Remove-CsTenantDialPlan](https://technet.microsoft.com/library/mt775020.aspx).</span></span>
    
- <span data-ttu-id="c424f-135">Para ver la configuración del plan de marcado eficaz, ejecute:</span><span class="sxs-lookup"><span data-stu-id="c424f-135">To see the settings of the effective dial plan, run:</span></span>
    
  ```
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="c424f-136">Otros parámetros y ejemplos, vea [Get-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775022.aspx).</span><span class="sxs-lookup"><span data-stu-id="c424f-136">For other examples and parameters, see [Get-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775022.aspx).</span></span>
    
- <span data-ttu-id="c424f-137">Para probar la configuración efectiva de un plan de marcado, ejecute:</span><span class="sxs-lookup"><span data-stu-id="c424f-137">To test the effective settings of a dial plan, run:</span></span>
    
  ```
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255551234 -Identity 1849827b-a810-40a8-8f77-e94250d4680b_US_TenantDialPlanRedmond
  ```

    <span data-ttu-id="c424f-138">Otros parámetros y ejemplos, vea [CsEffectiveTenantDialPlan de prueba](https://technet.microsoft.com/library/mt775025.aspx).</span><span class="sxs-lookup"><span data-stu-id="c424f-138">For other examples and parameters, see [Test-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775025.aspx).</span></span>
    
### <a name="using-a-powershell-script"></a><span data-ttu-id="c424f-139">Mediante un script de PowerShell</span><span class="sxs-lookup"><span data-stu-id="c424f-139">Using a PowerShell script</span></span>

<span data-ttu-id="c424f-140">Para eliminar una regla de normalización que se asocia con un arrendatario Ejecutar plan de marcado sin necesidad de eliminar el plan de marcado de inquilinos primero:</span><span class="sxs-lookup"><span data-stu-id="c424f-140">Run this to delete a normalization rule that is associated with a tenant dial plan without needing to deleting the tenant dial plan first:</span></span>
```
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
<span data-ttu-id="c424f-141">Ejecute para agregar la siguiente regla de normalización para el plan de marcado de inquilinos existente denominado RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="c424f-141">Run this to add the following normalization rule to the existing tenant dial plan named RedmondDialPlan.</span></span>
```
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
<span data-ttu-id="c424f-142">Ejecutar esto para quitar la siguiente regla de normalización del plan de marcado existente de inquilinos denominado RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="c424f-142">Run this to remove the following normalization rule from the existing tenant dial plan named RedmondDialPlan.</span></span>
```
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity DP1 -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="c424f-143">Ejecute lo siguiente cuando desee examinar también las reglas de normalización existentes, determinar cuál de ellos desea eliminar y, a continuación, utilice su índice para quitarlo.</span><span class="sxs-lookup"><span data-stu-id="c424f-143">Run the following when you want to also examine the existing normalization rules, determine which one you want to delete, and then use its index to remove it.</span></span> <span data-ttu-id="c424f-144">La matriz de reglas de normalización se inicia con el índice 0.</span><span class="sxs-lookup"><span data-stu-id="c424f-144">The array of normalization rules starts with index 0.</span></span> <span data-ttu-id="c424f-145">Nos gustaría quitar la regla de normalización de 3 dígitos, por lo que es índice 1.</span><span class="sxs-lookup"><span data-stu-id="c424f-145">We would like to remove the 3-digit normalization rule, so that is index 1.</span></span>
  
```
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

$nr1=(Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules[Number 1]
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="c424f-146">Ejecute esto para encontrar todos los usuarios que han recibido al inquilino RedmondDialPlan plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="c424f-146">Run this to find all users who have been granted the RedmondDialPlan tenant dial plan.</span></span>
  
```
Get-CsOnlineuser | where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

<span data-ttu-id="c424f-147">Ejecutar estos para agregar que denominada OPDP1 como un plan de marcado de inquilinos de la organización de plan de marcado de las instalaciones existentes.</span><span class="sxs-lookup"><span data-stu-id="c424f-147">Run these to add the existing on-premises dial plan named OPDP1 as a tenant dial plan for your organization.</span></span> <span data-ttu-id="c424f-148">Debe primero guardar los locales plan a un archivo .xml de marcado y, a continuación, utilizarlo para crear el nuevo plan de marcado de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="c424f-148">You need to first save the on-premises dial plan to an .xml file, and then use it to create the new tenant dial plan.</span></span>
  
<span data-ttu-id="c424f-149">Ejecutar para guardar el plan de marcado local en el archivo .xml.</span><span class="sxs-lookup"><span data-stu-id="c424f-149">Run this to save the on-premises dial plan to the .xml file.</span></span>
  
```
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

<span data-ttu-id="c424f-150">Ejecute esto para crear el nuevo plan de marcado de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="c424f-150">Run this to create the new tenant dial plan.</span></span>
  
```
$DPFileName = "dialplan.xml"
$DP = Import-Clixml $DPFileName
$NormRules = @()
ForEach($nr in $dp.NormalizationRules)
{
 $id1 = "Global/" +$nr.Name
$nr2 = New-CsVoiceNormalizationRule -Identity $id1 -Description $nr.Description -Pattern $nr.Pattern -Translation $nr.Translation  -IsInternalExtension $nr.IsInternalExtension -InMemory
$NormRules += $nr2
}
New-CsTenantDialPlan -Identity $dp.SimpleName -ExternalAccessPrefix $dp.ExternalAccessPrefix -Description $dp.Description -OptimizeDeviceDialing $dp.OptimizeDeviceDialing -SimpleName $dp.SimpleName -NormalizationRules $NormRules
```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="c424f-151">¿Desea saber más acerca de Windows Powershell?</span><span class="sxs-lookup"><span data-stu-id="c424f-151">Want to know more about Windows Powershell?</span></span>

- <span data-ttu-id="c424f-p105">En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="c424f-p105">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="c424f-155">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="c424f-155">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - <span data-ttu-id="c424f-156">Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="c424f-156">[Why you need to use Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)</span></span>
    
- <span data-ttu-id="c424f-p106">Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="c424f-p106">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="c424f-159">Mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c424f-159">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="c424f-160">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="c424f-160">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="c424f-161">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="c424f-161">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="c424f-162">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="c424f-162">Related topics</span></span>
[<span data-ttu-id="c424f-163">Transferencia de preguntas habituales de los números de teléfono</span><span class="sxs-lookup"><span data-stu-id="c424f-163">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="c424f-164">Diferentes tipos de números de teléfono utilizados para llamar a planes</span><span class="sxs-lookup"><span data-stu-id="c424f-164">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="c424f-165">Administrar números de teléfono de la organización</span><span class="sxs-lookup"><span data-stu-id="c424f-165">Manage phone numbers for your organization</span></span>](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="c424f-166">Términos y condiciones de las llamadas de emergencias</span><span class="sxs-lookup"><span data-stu-id="c424f-166">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

[<span data-ttu-id="c424f-167">Skype para los negocios en línea: etiqueta de descargo de responsabilidad llamada de emergencia</span><span class="sxs-lookup"><span data-stu-id="c424f-167">Skype for Business Online: Emergency Calling disclaimer label</span></span>](https://go.microsoft.com/fwlink/?LinkID=692099)

