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
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 'Learn how to create calling dial plans (PSTN Calling dial plans) in Office 365 and how to manage them. '
ms.openlocfilehash: a499ddb9a9788fce9bdd9bfb2a5bd6e8d1d0f687
ms.sourcegitcommit: 70d4d02a3cc894f2f197aeea459ac079cde63877
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/11/2019
ms.locfileid: "30543323"
---
# <a name="create-and-manage-dial-plans"></a><span data-ttu-id="d02da-103">Crear y administrar planes de marcado</span><span class="sxs-lookup"><span data-stu-id="d02da-103">Create and manage dial plans</span></span>

<span data-ttu-id="d02da-104">Después de que ha planeado los planes de marcado para su organización y descubrió todas las reglas de normalización que deben crearse para el enrutamiento de llamadas, debe usar Windows PowerShell para crear planes de marcado y realice los cambios de configuración.</span><span class="sxs-lookup"><span data-stu-id="d02da-104">After you have planned the dial plans for your organization and figured out all of the normalization rules that need to be created for call routing, you will need to use Windows PowerShell to create the dial plans and make any setting changes.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d02da-105">Los planes de marcado no se pueden crear y administrar en el centro de administración de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="d02da-105">The Skype for Business admin center can't be used for creating and managing dial plans.</span></span> 
  
## <a name="verifying-and-starting-remote-powershell"></a><span data-ttu-id="d02da-106">Verificar e iniciar PowerShell remoto</span><span class="sxs-lookup"><span data-stu-id="d02da-106">Verifying and starting Remote PowerShell</span></span>

 <span data-ttu-id="d02da-107">**Comprobar que está ejecutando Windows PowerShell versión 3.0 o superior**</span><span class="sxs-lookup"><span data-stu-id="d02da-107">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
  
1. <span data-ttu-id="d02da-108">Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="d02da-108">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="d02da-109">Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="d02da-109">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="d02da-p101">Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell. Vea [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para descargar y actualizar Windows PowerShell a la versión 4.0. Reinicie el equipo cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="d02da-p101">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="d02da-p102">También necesitará instalar el módulo Windows PowerShell para Skype Empresarial Online que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype Empresarial Online. Este módulo, que solo se admite en equipos de 64 bits, puede descargarse desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=294688). Reinicie el equipo cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="d02da-p102">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
<span data-ttu-id="d02da-116">Si necesita más información, consulte [Conectarse a todos los servicios de Office 365 en una única ventana de Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="d02da-116">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
  
 <span data-ttu-id="d02da-117">**Iniciar una sesión de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="d02da-117">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="d02da-118">En el **menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="d02da-118">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="d02da-119">En la ventana **Windows PowerShell**, puede conectarse a su organización de Office 365 ejecutando:</span><span class="sxs-lookup"><span data-stu-id="d02da-119">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d02da-120">Solo tiene que ejecutar el comando **Import-Module** la primera vez que use el módulo Windows PowerShell de Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="d02da-120">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
  
> 
>   ```
>     Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
>     $credential = Get-Credential
>     $session = New-CsOnlineSession -Credential $credential
>     Import-PSSession $session
>   ```

<span data-ttu-id="d02da-121">Si desea obtener más información acerca de cómo iniciar Windows PowerShell, vea [Conectar a todos los servicios de Office 365 en una sola ventana de Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) o [Connecting to Skype para profesionales en línea mediante Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="d02da-121">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
  
## <a name="creating-and-managing-your-dial-plans"></a><span data-ttu-id="d02da-122">Crear y administrar sus planes de marcado</span><span class="sxs-lookup"><span data-stu-id="d02da-122">Creating and managing your dial plans</span></span>

<span data-ttu-id="d02da-123">Para crear y administrar planes de marcado de inquilino puede utilizar un cmdlet sencillo o un script de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d02da-123">You can either use a single cmdlet or a PowerShell script to create and manage tenant dial plans.</span></span>
  
### <a name="using-single-cmdlets"></a><span data-ttu-id="d02da-124">Uso de cmdlets sencillos</span><span class="sxs-lookup"><span data-stu-id="d02da-124">Using single cmdlets</span></span>

- <span data-ttu-id="d02da-125">Para crear un nuevo plan de marcado, ejecute:</span><span class="sxs-lookup"><span data-stu-id="d02da-125">To create a new dial plan, run:</span></span>
    
  ```
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="d02da-126">Para ver otros ejemplos y parámetros, consulte [Nuevo-CsPlanMarcadoInquilinio](https://technet.microsoft.com/library/mt775026.aspx).</span><span class="sxs-lookup"><span data-stu-id="d02da-126">For other examples and parameters, see [New-CsTenantDialPlan](https://technet.microsoft.com/library/mt775026.aspx).</span></span>
    
- <span data-ttu-id="d02da-127">Para cambiar la configuración en un plan de marcado, ejecute:</span><span class="sxs-lookup"><span data-stu-id="d02da-127">To make setting changes to an existing dial plan, run:</span></span>
    
  ```
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="d02da-128">Para ver otros ejemplos y parámetros, consulte[Configurar-CsPlanMarcadoInquilino](https://technet.microsoft.com/library/mt775023.aspx).</span><span class="sxs-lookup"><span data-stu-id="d02da-128">For other examples and parameters, see [Set-CsTenantDialPlan](https://technet.microsoft.com/library/mt775023.aspx).</span></span>
    
- <span data-ttu-id="d02da-129">Para agregar usuarios a un plan de marcado, ejecute:</span><span class="sxs-lookup"><span data-stu-id="d02da-129">To add users to a dial plan, run:</span></span>
    
  ```
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    <span data-ttu-id="d02da-130">Para ver otros ejemplos y parámetros, consulte [Garantizar-CsPlanMarcadoInquilino](https://technet.microsoft.com/library/mt775021.aspx).</span><span class="sxs-lookup"><span data-stu-id="d02da-130">For other examples and parameters, see [Grant-CsTenantDialPlan](https://technet.microsoft.com/library/mt775021.aspx).</span></span>
    
- <span data-ttu-id="d02da-131">Para ver la configuración de un plan de marcado, ejecute:</span><span class="sxs-lookup"><span data-stu-id="d02da-131">To view the settings on a dial plan, run:</span></span>
    
  ```
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    <span data-ttu-id="d02da-132">Para ver otros ejemplos y parámetros, consulte[Obtener-CsPlanMarcadoInquilino](https://technet.microsoft.com/library/mt775024.aspx).</span><span class="sxs-lookup"><span data-stu-id="d02da-132">For other examples and parameters, see [Get-CsTenantDialPlan](https://technet.microsoft.com/library/mt775024.aspx).</span></span>
    
- <span data-ttu-id="d02da-133">Para eliminar un plan de marcado, ejecute:</span><span class="sxs-lookup"><span data-stu-id="d02da-133">To delete a dial plan, run:</span></span>
    
  ```
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    <span data-ttu-id="d02da-134">Para ver otros ejemplos y parámetros, consulte [Eliminar-CsPlanMarcadoInquilino](https://technet.microsoft.com/library/mt775020.aspx).</span><span class="sxs-lookup"><span data-stu-id="d02da-134">For other examples and parameters, see [Remove-CsTenantDialPlan](https://technet.microsoft.com/library/mt775020.aspx).</span></span>
    
- <span data-ttu-id="d02da-135">Para ver la configuración del plan de marcado efectivo, ejecute:</span><span class="sxs-lookup"><span data-stu-id="d02da-135">To see the settings of the effective dial plan, run:</span></span>
    
  ```
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="d02da-136">Para ver otros ejemplos y parámetros, consulte [Obtener-CsPlanMarcadoEfectivoInquilino](https://technet.microsoft.com/library/mt775022.aspx).</span><span class="sxs-lookup"><span data-stu-id="d02da-136">For other examples and parameters, see [Get-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775022.aspx).</span></span>
    
- <span data-ttu-id="d02da-137">Para evaluar la configuración efectiva de un plan de marcado, ejecute:</span><span class="sxs-lookup"><span data-stu-id="d02da-137">To test the effective settings of a dial plan, run:</span></span>
    
  ```
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255551234 -Identity 1849827b-a810-40a8-8f77-e94250d4680b_US_TenantDialPlanRedmond
  ```

    <span data-ttu-id="d02da-138">Para ver otros ejemplos y parámetros, consulte [Probar-CsPlanMarcadoEfectivoInquilino](https://technet.microsoft.com/library/mt775025.aspx).</span><span class="sxs-lookup"><span data-stu-id="d02da-138">For other examples and parameters, see [Test-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775025.aspx).</span></span>
    
### <a name="using-a-powershell-script"></a><span data-ttu-id="d02da-139">Uso de un script de PowerShell</span><span class="sxs-lookup"><span data-stu-id="d02da-139">Using a PowerShell script</span></span>

<span data-ttu-id="d02da-140">Ejecute esto para eliminar una regla de normalización que esté asociada con un plan de marcado inquilino sin que tenga que eliminar en primer lugar el plan de marcado inquilino:</span><span class="sxs-lookup"><span data-stu-id="d02da-140">Run this to delete a normalization rule that is associated with a tenant dial plan without needing to deleting the tenant dial plan first:</span></span>
```
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
<span data-ttu-id="d02da-141">Ejecute esto para agregar la siguiente regla de normalización al plan de marcado inquilino existente denominado RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="d02da-141">Run this to add the following normalization rule to the existing tenant dial plan named RedmondDialPlan.</span></span>
```
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
<span data-ttu-id="d02da-142">Ejecute esto para eliminar la siguiente regla de normalización del plan de marcado inquilino existente denominado RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="d02da-142">Run this to remove the following normalization rule from the existing tenant dial plan named RedmondDialPlan.</span></span>
```
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity DP1 -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="d02da-p103">Ejecute lo siguiente cuando desea también se examinan las reglas de normalización existente, determinar la que desea eliminar y, a continuación, usar su índice para quitarlo. La matriz de reglas de normalización se inicia con el índice 0. Nos gustaría quitar la regla de normalización de 3 dígitos, por lo que es el índice 1.</span><span class="sxs-lookup"><span data-stu-id="d02da-p103">Run the following when you want to also examine the existing normalization rules, determine which one you want to delete, and then use its index to remove it. The array of normalization rules starts with index 0. We would like to remove the 3-digit normalization rule, so that is index 1.</span></span>
  
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

<span data-ttu-id="d02da-146">Ejecute esto para buscar todos los usuarios a los que se les ha garantizado el plan de marcado inquilino RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="d02da-146">Run this to find all users who have been granted the RedmondDialPlan tenant dial plan.</span></span>
  
```
Get-CsOnlineuser | where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

<span data-ttu-id="d02da-147">Ejecute esta opción para eliminar policyname para todos los usuarios que tienen HostingProvider sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="d02da-147">Run this to delete policyname for all users who have HostingProvider sipfed.online.lync.com.</span></span>
```
Get-CsOnlineUser -Filter {HostingProvider -eq “sipfed.online.lync.com”} | Grant-CsTenantDialPlan -policyname $null
```

<span data-ttu-id="d02da-148">Ejecute estos para agregar el plan de marcado local existente denominado OPDP1 como un plan de marcado inquilino para su organización.</span><span class="sxs-lookup"><span data-stu-id="d02da-148">Run these to add the existing on-premises dial plan named OPDP1 as a tenant dial plan for your organization.</span></span> <span data-ttu-id="d02da-149">Debe primero guardar el local plan a un archivo .xml de marcado y, a continuación, usarla para crear el nuevo plan de marcado de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="d02da-149">You need to first save the on-premises dial plan to an .xml file, and then use it to create the new tenant dial plan.</span></span>
  
<span data-ttu-id="d02da-150">Ejecute para guardar el plan de marcado local en el archivo .xml.</span><span class="sxs-lookup"><span data-stu-id="d02da-150">Run this to save the on-premises dial plan to the .xml file.</span></span>
  
```
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

<span data-ttu-id="d02da-151">Ejecute esto para crear el nuevo plan de marcado inquilino.</span><span class="sxs-lookup"><span data-stu-id="d02da-151">Run this to create the new tenant dial plan.</span></span>
  
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
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="d02da-152">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="d02da-152">Want to know more about Windows Powershell?</span></span>

- <span data-ttu-id="d02da-153">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="d02da-153">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="d02da-154">Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas.</span><span class="sxs-lookup"><span data-stu-id="d02da-154">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="d02da-155">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="d02da-155">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="d02da-156">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="d02da-156">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="d02da-157">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="d02da-157">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="d02da-p106">Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="d02da-p106">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="d02da-160">Mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d02da-160">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="d02da-161">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="d02da-161">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="d02da-162">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="d02da-162">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="d02da-163">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="d02da-163">Related topics</span></span>
[<span data-ttu-id="d02da-164">Preguntas comunes sobre la transferencia de números de teléfono</span><span class="sxs-lookup"><span data-stu-id="d02da-164">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="d02da-165">Diferentes tipos de números de teléfono que se usan para Planes de llamada</span><span class="sxs-lookup"><span data-stu-id="d02da-165">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="d02da-166">Administrar los números de teléfono para su organización</span><span class="sxs-lookup"><span data-stu-id="d02da-166">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="d02da-167">Términos y condiciones de las llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="d02da-167">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

<span data-ttu-id="d02da-168">[Skype for Business Online: Etiqueta de aviso de declinación de responsabilidades de las llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="d02da-168">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
