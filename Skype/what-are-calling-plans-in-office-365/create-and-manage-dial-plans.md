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
# <a name="create-and-manage-dial-plans"></a>Crear y administrar planes de marcado

Después de haber planeado los planes de marcado para su organización e imaginado todas las reglas de normalización que deben crearse para el enrutamiento de llamadas, debe usar Windows PowerShell para crear los planes de marcado y realice los cambios de configuración.
  
> [!NOTE]
> No se puede utilizar el Skype para el centro de administración de negocios para crear y administrar planes de marcado. 
  
## <a name="verifying-and-starting-remote-powershell"></a>Comprobar e iniciar PowerShell remoto

 **Comprobar que está ejecutando Windows PowerShell versión 3.0 o superior**
  
1. Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.
    
2. Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.
    
3. Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell. Vea [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para descargar y actualizar Windows PowerShell a la versión 4.0. Reinicie el equipo cuando se le solicite.
    
4. También necesitará instalar el módulo Windows PowerShell para Skype Empresarial Online que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype Empresarial Online. Este módulo, que solo se admite en equipos de 64 bits, puede descargarse desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=294688). Reinicie el equipo cuando se le solicite.
    
Si necesita más información, consulte [Conectarse a todos los servicios de Office 365 en una única ventana de Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).
  
 **Iniciar una sesión de Windows PowerShell**
  
1. En el **menú Inicio** > **Windows PowerShell**.
    
2. En la ventana **Windows PowerShell**, puede conectarse a su organización de Office 365 ejecutando:
    
    > [!NOTE]
    > Solo tiene que ejecutar el comando **Import-Module** la primera vez que use el módulo Windows PowerShell de Skype Empresarial Online.
  
> 
  ```
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

Si desea obtener más información acerca de cómo iniciar Windows PowerShell, vea [Conectar con todos los servicios de Office 365 en una sola ventana de Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) o [conectarse a Skype para los negocios en línea mediante el uso de Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).
  
## <a name="creating-and-managing-your-dial-plans"></a>Creación y administración de los planes de marcado

Puede utilizar un cmdlet único o un script de PowerShell para crear y administrar planes de marcado de inquilinos.
  
### <a name="using-single-cmdlets"></a>Uso de cmdlets único

- Para crear un nuevo plan de marcado, ejecute:
    
  ```
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    Otros parámetros y ejemplos, vea [New-CsTenantDialPlan](https://technet.microsoft.com/library/mt775026.aspx).
    
- Para realizar cambios de configuración en un plan de marcado existente, ejecute:
    
  ```
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    Para otros ejemplos y parámetros, consulte [Set-CsTenantDialPlan](https://technet.microsoft.com/library/mt775023.aspx).
    
- Para agregar usuarios a un plan de marcado, ejecute:
    
  ```
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    Otros parámetros y ejemplos, vea [CsTenantDialPlan de concesión](https://technet.microsoft.com/library/mt775021.aspx).
    
- Para ver la configuración de un plan de marcado, ejecute:
    
  ```
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    Otros parámetros y ejemplos, vea [Get-CsTenantDialPlan](https://technet.microsoft.com/library/mt775024.aspx).
    
- Para eliminar un plan de marcado, ejecute:
    
  ```
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    Otros parámetros y ejemplos, vea [Quitar CsTenantDialPlan](https://technet.microsoft.com/library/mt775020.aspx).
    
- Para ver la configuración del plan de marcado eficaz, ejecute:
    
  ```
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    Otros parámetros y ejemplos, vea [Get-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775022.aspx).
    
- Para probar la configuración efectiva de un plan de marcado, ejecute:
    
  ```
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255551234 -Identity 1849827b-a810-40a8-8f77-e94250d4680b_US_TenantDialPlanRedmond
  ```

    Otros parámetros y ejemplos, vea [CsEffectiveTenantDialPlan de prueba](https://technet.microsoft.com/library/mt775025.aspx).
    
### <a name="using-a-powershell-script"></a>Mediante un script de PowerShell

Para eliminar una regla de normalización que se asocia con un arrendatario Ejecutar plan de marcado sin necesidad de eliminar el plan de marcado de inquilinos primero:
```
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
Ejecute para agregar la siguiente regla de normalización para el plan de marcado de inquilinos existente denominado RedmondDialPlan.
```
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
Ejecutar esto para quitar la siguiente regla de normalización del plan de marcado existente de inquilinos denominado RedmondDialPlan.
```
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity DP1 -NormalizationRules @{remove=$nr1}
```

Ejecute lo siguiente cuando desee examinar también las reglas de normalización existentes, determinar cuál de ellos desea eliminar y, a continuación, utilice su índice para quitarlo. La matriz de reglas de normalización se inicia con el índice 0. Nos gustaría quitar la regla de normalización de 3 dígitos, por lo que es índice 1.
  
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

Ejecute esto para encontrar todos los usuarios que han recibido al inquilino RedmondDialPlan plan de marcado.
  
```
Get-CsOnlineuser | where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

Ejecutar estos para agregar que denominada OPDP1 como un plan de marcado de inquilinos de la organización de plan de marcado de las instalaciones existentes. Debe primero guardar los locales plan a un archivo .xml de marcado y, a continuación, utilizarlo para crear el nuevo plan de marcado de inquilinos.
  
Ejecutar para guardar el plan de marcado local en el archivo .xml.
  
```
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

Ejecute esto para crear el nuevo plan de marcado de inquilinos.
  
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
## <a name="want-to-know-more-about-windows-powershell"></a>¿Desea saber más acerca de Windows Powershell?

- En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
- Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  - [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Temas relacionados
[Transferencia de preguntas habituales de los números de teléfono](transferring-phone-numbers-common-questions.md)

[Diferentes tipos de números de teléfono utilizados para llamar a planes](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Administrar números de teléfono de la organización](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Términos y condiciones de las llamadas de emergencias](emergency-calling-terms-and-conditions.md)

[Skype para los negocios en línea: etiqueta de descargo de responsabilidad llamada de emergencia](https://go.microsoft.com/fwlink/?LinkID=692099)

