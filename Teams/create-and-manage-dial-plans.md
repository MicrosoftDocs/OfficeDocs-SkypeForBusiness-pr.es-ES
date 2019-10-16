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
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 'Obtenga información sobre cómo crear planes de marcado de llamada (planes de marcado de llamada RTC) en Office 365 y cómo administrarlos. '
ms.openlocfilehash: 3b96c2f504096b3f77c7080feda1dac982f46e9c
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516677"
---
# <a name="create-and-manage-dial-plans"></a>Crear y administrar planes de marcado

Una vez que haya planeado los planes de marcado de su organización y haya averiguado todas las reglas de normalización que deben crearse para el enrutamiento de llamadas, tendrá que usar Windows PowerShell para crear los planes de marcado y realizar todos los cambios de configuración.
  
> [!NOTE]
> Los planes de marcado no se pueden crear y administrar en el centro de administración de Skype Empresarial. 
  
## <a name="verifying-and-starting-remote-powershell"></a>Verificar e iniciar PowerShell remoto

 **Comprobar que está ejecutando Windows PowerShell versión 3.0 o superior**
  
1. Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.
    
2. Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.
    
3. Si no tiene la versión 3,0 o superior, debe descargar e instalar las actualizaciones de Windows PowerShell. Vea [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) para descargar y actualizar Windows PowerShell a la versión 4,0. Reinicie el equipo cuando se le pida.
    
4. También necesitará instalar el módulo Windows PowerShell para Skype Empresarial Online que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype Empresarial Online. Este módulo, que solo se admite en equipos de 64 bits, puede descargarse desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=294688). Reinicie el equipo cuando se le solicite.
    
Si necesita más información, consulte [Conectarse a todos los servicios de Office 365 en una única ventana de Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).
  
 **Iniciar una sesión de Windows PowerShell**
  
1. En el **menú Inicio** > **Windows PowerShell**.
    
2. En la ventana **Windows PowerShell**, puede conectarse a su organización de Office 365 ejecutando:
    
    > [!NOTE]
    > Solo tiene que ejecutar el comando **Import-Module** la primera vez que use el módulo Windows PowerShell de Skype Empresarial Online.
  
> 
>   ```
>     Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
>     $credential = Get-Credential
>     $session = New-CsOnlineSession -Credential $credential
>     Import-PSSession $session
>   ```

Si desea obtener más información sobre cómo iniciar Windows PowerShell, vea [conectarse a todos los servicios de Office 365 en una sola ventana de Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) o [conectarse a Skype empresarial online mediante Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).
  
## <a name="creating-and-managing-your-dial-plans"></a>Crear y administrar sus planes de marcado

Para crear y administrar planes de marcado de inquilino puede utilizar un cmdlet sencillo o un script de PowerShell.
  
### <a name="using-single-cmdlets"></a>Uso de cmdlets sencillos

- Para crear un nuevo plan de marcado, ejecute:
    
  ```
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    Para ver otros ejemplos y parámetros, consulte [Nuevo-CsPlanMarcadoInquilinio](https://technet.microsoft.com/library/mt775026.aspx).
    
- Para cambiar la configuración en un plan de marcado, ejecute:
    
  ```
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    Para ver otros ejemplos y parámetros, consulte[Configurar-CsPlanMarcadoInquilino](https://technet.microsoft.com/library/mt775023.aspx).
    
- Para agregar usuarios a un plan de marcado, ejecute:
    
  ```
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    Para ver otros ejemplos y parámetros, consulte [Garantizar-CsPlanMarcadoInquilino](https://technet.microsoft.com/library/mt775021.aspx).
    
- Para ver la configuración de un plan de marcado, ejecute:
    
  ```
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    Para ver otros ejemplos y parámetros, consulte[Obtener-CsPlanMarcadoInquilino](https://technet.microsoft.com/library/mt775024.aspx).
    
- Para eliminar un plan de marcado, ejecute:
    
  ```
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    Para ver otros ejemplos y parámetros, consulte [Eliminar-CsPlanMarcadoInquilino](https://technet.microsoft.com/library/mt775020.aspx).
    
- Para ver la configuración del plan de marcado efectivo, ejecute:
    
  ```
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    Para ver otros ejemplos y parámetros, consulte [Obtener-CsPlanMarcadoEfectivoInquilino](https://technet.microsoft.com/library/mt775022.aspx).
    
- Para evaluar la configuración efectiva de un plan de marcado, ejecute:
    
  ```
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    Para ver otros ejemplos y parámetros, consulte [Probar-CsPlanMarcadoEfectivoInquilino](https://technet.microsoft.com/library/mt775025.aspx).
    
### <a name="using-a-powershell-script"></a>Uso de un script de PowerShell

Ejecute esto para eliminar una regla de normalización que esté asociada con un plan de marcado inquilino sin que tenga que eliminar en primer lugar el plan de marcado inquilino:
```
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
Ejecute esto para agregar la siguiente regla de normalización al plan de marcado inquilino existente denominado RedmondDialPlan.
```
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
Ejecute esto para eliminar la siguiente regla de normalización del plan de marcado inquilino existente denominado RedmondDialPlan.
```
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity DP1 -NormalizationRules @{remove=$nr1}
```

Run the following when you want to also examine the existing normalization rules, determine which one you want to delete, and then use its index to remove it. The array of normalization rules starts with index 0. We would like to remove the 3-digit normalization rule, so that is index 1.
  
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

Ejecute esto para buscar todos los usuarios a los que se les ha garantizado el plan de marcado inquilino RedmondDialPlan.
  
```
Get-CsOnlineuser | where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

Ejecútelo para eliminar el PolicyName de todos los usuarios que tengan Hostingprovider manda sipfed.online.lync.com.
```
Get-CsOnlineUser -Filter {HostingProvider -eq “sipfed.online.lync.com”} | Grant-CsTenantDialPlan -policyname $null
```

Ejecute estos para agregar el plan de marcado local existente denominado OPDP1 como un plan de marcado inquilino para su organización. Primero debe guardar el plan de marcado local en un archivo. XML y, a continuación, usarlo para crear el nuevo plan de marcado de inquilino.
  
Ejecute esto para guardar el plan de marcado local en el archivo. Xml.
  
```
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

Ejecute esto para crear el nuevo plan de marcado inquilino.
  
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
## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

- Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell tiene muchas ventajas en cuanto a velocidad, simplicidad y productividad en lugar de usar únicamente el centro de administración de Microsoft 365, como cuando se hacen los cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  - [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Temas relacionados
[Preguntas comunes sobre la transferencia de números de teléfono](transferring-phone-numbers-common-questions.md)

[Diferentes tipos de números de teléfono que se usan para Planes de llamada](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Administrar los números de teléfono para su organización](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Términos y condiciones de las llamadas de emergencia](emergency-calling-terms-and-conditions.md)

[Skype Empresarial Online: Etiqueta de aviso de declinación de responsabilidades de las llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 
