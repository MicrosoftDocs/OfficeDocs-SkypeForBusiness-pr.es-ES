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
f1keywords: None
ms.custom:
- Calling Plans
description: Aprenda a crear y administrar planes de marcado de llamada (planes de marcado de llamadas RTC) y a administrarlos.
ms.openlocfilehash: c9623073cd5660a67bc2ba77b9c07a356d636520
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991665"
---
# <a name="create-and-manage-dial-plans"></a>Crear y administrar planes de marcado

Después de planear los planes de marcado de su organización y de haber averiguado todas las reglas de normalización que deben crearse para el enrutamiento de llamadas, ya está listo para crear los planes de marcado. Puede usar el centro de administración de Microsoft Teams o Windows PowerShell para crear y administrar planes de marcado.  

## <a name="using-the-microsoft-teams-admin-center"></a>Usar el centro de administración de Microsoft Teams

### <a name="create-a-dial-plan"></a>Crear un plan de marcado

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a**plan de marcado**de **voz** > .
2. Haga clic en **Agregar**y, a continuación, escriba un nombre y una descripción para el plan de marcado.
    ![Captura de pantalla que muestra la página Agregar para crear un plan de marcado](media/create-dial-plan.png)
3. En **detalles del plan de marcado**, especifique un prefijo de marcado externo si los usuarios necesitan marcar uno o varios dígitos iniciales adicionales (por ejemplo, 9) para obtener una línea externa. Para ello, haga lo siguiente:
    1. En el cuadro **Prefijo de marcado externo** , escriba un prefijo de marcado externo. El prefijo puede tener un máximo de cuatro caracteres (#, * y 0-9).
    2. Activar el **marcado de dispositivo optimizado**. Si especifica un prefijo de marcado externo, también debe activar esta opción para aplicar el prefijo, de modo que las llamadas se hagan fuera de su organización.
4. En **reglas de normalización**, configure y asocie una o más [reglas de normalización](what-are-dial-plans.md#normalization-rules) para el plan de marcado. Cada plan de marcado debe tener al menos una regla de normalización asociada.  Para ello, siga uno o varios de estos procedimientos:
    - Para crear una nueva regla de normalización y asociarla con el plan de marcado, haga clic en **Agregar**y, a continuación, defina la regla.
    - Para editar una regla de normalización que ya está asociada con el plan de marcado, seleccione la regla haciendo clic a la izquierda del nombre de la regla y, a continuación, haga clic en **Editar**. Realice los cambios que desee y, a continuación, haga clic en **Guardar**.
    - Para quitar una regla de normalización del plan de marcado, seleccione la regla haciendo clic a la izquierda del nombre de la regla y, a continuación, haga clic en **quitar**.
5. Organice las reglas de normalización en el orden que desee. Haga clic en **subir** o **bajar** para cambiar la posición de las reglas de la lista.

    > [!NOTE]
    > Teams recorre la lista de reglas de normalización de la parte superior hacia abajo y usa la primera regla que coincida con el número marcado. Si configura un plan de marcado para que un número marcado pueda coincidir con más de una regla de normalización, asegúrese de que las reglas más restrictivas se ordenan por encima de las menos restrictivas.

6. Haga clic en **Guardar **.
7. Si desea probar el plan de marcado, en **plan de marcado de prueba**, escriba un número de teléfono y, a continuación, haga clic en **prueba**.

### <a name="edit-a-dial-plan"></a>Editar un plan de marcado

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a**plan de marcado**de **voz** > .
2. Seleccione el plan de marcado haciendo clic a la izquierda del nombre del plan de marcado y, a continuación, haga clic en **Editar**.
3. Realice los cambios que desee y, a continuación, haga clic en **Guardar**.

### <a name="add-users-to-a-dial-plan"></a>Agregar usuarios a un plan de marcado

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a**plan de marcado**de **voz** > .
2. Seleccione el plan de marcado haciendo clic a la izquierda del nombre del plan de marcado.
3. Seleccione **administrar usuarios**.
4. En el panel **administrar usuarios** , busque el usuario por nombre para mostrar o por nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**. Repita este paso para cada usuario que desee agregar.
5. Cuando haya terminado de agregar usuarios, seleccione **aplicar**.

## <a name="using-powershell"></a>Usar PowerShell
  
### <a name="verify-and-start-remote-powershell"></a>Comprobar e iniciar PowerShell remoto

 **Comprobar que está ejecutando Windows PowerShell versión 3,0 o posterior**
  
1. Para comprobar que está ejecutando la versión 3,0 o superior: **menú** > inicio de**Windows PowerShell**.
    
2. Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.
    
3. Si no tiene la versión 3,0 o posterior, descargue e instale las actualizaciones de Windows PowerShell. Vea [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) para descargar y actualizar Windows PowerShell a la versión 4,0. Reinicie el equipo cuando se le pida.
    
4. También tendrá que instalar el módulo Windows PowerShell para Skype empresarial online que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype empresarial online. Puede descargar este módulo, que solo se admite en equipos de 64 de bits, en el [módulo de Windows PowerShell para Skype empresarial online](https://go.microsoft.com/fwlink/?LinkId=294688). Reinicie el equipo si se le pide.
    
Para obtener más información, vea [conectarse a todos los servicios de Office 365 en una sola ventana de Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).
  
 **Iniciar una sesión de Windows PowerShell**
  
1. Haga clic en **iniciar** > **Windows PowerShell**.
    
2. En la ventana **Windows PowerShell**, puede conectarse a su organización de Office 365 ejecutando:
    
    > [!NOTE]
    > Solo tiene que ejecutar el comando **Import-Module** la primera vez que use el módulo Windows PowerShell de Skype Empresarial Online.
  

    ```PowerShell
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
    ```
  
### <a name="create-and-manage-your-dial-plans"></a>Crear y administrar los planes de marcado

Para crear y administrar planes de marcado de inquilino puede utilizar un cmdlet sencillo o un script de PowerShell.
  
#### <a name="using-single-cmdlets"></a>Uso de cmdlets sencillos

- Para crear un nuevo plan de marcado, ejecute:
    
  ```PowerShell
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    Para ver otros ejemplos y parámetros, consulte [Nuevo-CsPlanMarcadoInquilinio](https://docs.microsoft.com/powershell/module/skype/new-cstenantdialplan).
    
- Para editar la configuración de un plan de marcado existente, ejecute:
    
  ```PowerShell
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    Para ver otros ejemplos y parámetros, consulte[Configurar-CsPlanMarcadoInquilino](https://docs.microsoft.com/powershell/module/skype/set-cstenantdialplan).
    
- Para agregar usuarios a un plan de marcado, ejecute:
    
  ```PowerShell
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    Para ver otros ejemplos y parámetros, consulte [Garantizar-CsPlanMarcadoInquilino](https://docs.microsoft.com/powershell/module/skype/grant-cstenantdialplan).
    
- Para ver la configuración de un plan de marcado, ejecute:
    
  ```PowerShell
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    Para ver otros ejemplos y parámetros, consulte[Obtener-CsPlanMarcadoInquilino](https://docs.microsoft.com/powershell/module/skype/get-cstenantdialplan?view=skype-ps).
    
- Para eliminar un plan de marcado, ejecute:
    
  ```PowerShell
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    Para ver otros ejemplos y parámetros, consulte [Eliminar-CsPlanMarcadoInquilino](https://docs.microsoft.com/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).
    
- Para ver la configuración del plan de marcado efectivo, ejecute:
    
  ```PowerShell
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    Para ver otros ejemplos y parámetros, consulte [Obtener-CsPlanMarcadoEfectivoInquilino](https://docs.microsoft.com/powershell/module/skype/get-cseffectivetenantdialplan).
    
- Para evaluar la configuración efectiva de un plan de marcado, ejecute:
    
  ```PowerShell
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    Para ver otros ejemplos y parámetros, consulte [Probar-CsPlanMarcadoEfectivoInquilino](https://docs.microsoft.com/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).
    
#### <a name="using-a-powershell-script"></a>Uso de un script de PowerShell

Ejecute esto para eliminar una regla de normalización asociada a un plan de marcado de inquilino sin necesidad de eliminar primero el plan de marcado de inquilino:
```PowerShell
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
Ejecute esto para agregar la siguiente regla de normalización al plan de marcado inquilino existente denominado RedmondDialPlan.
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
Ejecute esto para eliminar la siguiente regla de normalización del plan de marcado inquilino existente denominado RedmondDialPlan.
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

Ejecute lo siguiente cuando desee examinar también las reglas de normalización existentes, determinar la que desea eliminar y, a continuación, usar su índice para quitarla. La matriz de reglas de normalización comienza con el índice 0. Nos gustaría eliminar la regla de normalización de tres dígitos, por lo que se trata del índice 1.
  
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

Ejecute esto para buscar todos los usuarios a los que se les ha garantizado el plan de marcado inquilino RedmondDialPlan.
  
```PowerShell
Get-CsOnlineUser | Where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

Ejecute esto para quitar todos los TenantDialPlan asignados de todos los usuarios que tienen una Hostingprovider manda de sipfed.online.lync.com.
```PowerShell
Get-CsOnlineUser -Filter {HostingProvider -eq “sipfed.online.lync.com”} | Grant-CsTenantDialPlan -policyname $null
```

Ejecute estos para agregar el plan de marcado local existente denominado OPDP1 como un plan de marcado inquilino para su organización. Primero debe guardar el plan de marcado local en un archivo. XML y, a continuación, usarlo para crear el nuevo plan de marcado de inquilino.
  
Ejecute esto para guardar el plan de marcado local en el archivo. Xml.
  
```PowerShell
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

Ejecute esto para crear el nuevo plan de marcado inquilino.
  
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
    
## <a name="related-topics"></a>Temas relacionados

- [¿Qué son los planes de marcado?](what-are-dial-plans.md)
- [Preguntas comunes sobre la transferencia de números de teléfono](transferring-phone-numbers-common-questions.md)
- [Diferentes tipos de números de teléfono que se usan para Planes de llamada](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Administrar los números de teléfono para su organización](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [Términos y condiciones de las llamadas de emergencia](emergency-calling-terms-and-conditions.md)
- [Etiqueta de renuncia para llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
