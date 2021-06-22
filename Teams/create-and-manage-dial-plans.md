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
# <a name="create-and-manage-dial-plans"></a>Crear y administrar planes de marcado

Después de planear los planes de marcado para su organización y de averiguar todas las reglas de normalización que deben crearse para el enrutamiento de llamadas, estará listo para crear los planes de marcado. Con una cuenta de administrador que tenga una licencia de Teams válida, puede usar el centro de administración de Microsoft Teams o Windows PowerShell para crear y administrar planes de marcado.  

## <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

### <a name="create-a-dial-plan"></a>Crear un plan de marcado

1. En el panel de navegación izquierdo del Microsoft Teams de administración, vaya a Plan **de marcado**  >  **de voz.**
2. Haga **clic en** Agregar y escriba un nombre y una descripción para el plan de marcado.
    ![Captura de pantalla que muestra la página Agregar para crear un plan de marcado](media/create-dial-plan.png)
3. En **Detalles del plan de** marcado, especifique un prefijo de marcado externo si los usuarios necesitan marcar uno o más dígitos iniciales adicionales (por ejemplo, 9) para obtener una línea externa. Para ello:
    1. En el **cuadro Prefijo de marcado externo,** escriba un prefijo de marcado externo. El prefijo puede tener hasta cuatro caracteres (#,*y 0-9).
    2. Activar la **marcación de dispositivo optimizada**. Si especifica un prefijo de marcado externo, también debe activar esta configuración para aplicar el prefijo para que las llamadas se puedan realizar fuera de su organización.
4. En **Reglas de normalización,** configure y asocie una o más reglas de [normalización](what-are-dial-plans.md#normalization-rules) para el plan de marcado. Cada plan de marcado debe tener al menos una regla de normalización asociada.  Para ello, realice una o varias de las siguientes acciones:
    - Para crear una nueva regla de normalización y asociarla al plan de marcado, haga clic en **Agregar** y, a continuación, defina la regla.
    - Para editar una regla de normalización que ya está asociada al plan de marcado, seleccione la regla haciendo clic a la izquierda del nombre de la regla y, a continuación, haga clic en **Editar.** Realice los cambios que desee y, a continuación, haga clic **en Guardar.**
    - Para quitar una regla de normalización del plan de marcado, seleccione la regla haciendo clic a la izquierda del nombre de la regla y, a continuación, haga clic en **Quitar**.
5. Organice las reglas de normalización en el orden que desee. Haga **clic en Subir** o **Bajar** para cambiar la posición de las reglas de la lista.

    > [!NOTE]
    > Teams atraviesa la lista de reglas de normalización desde arriba hacia abajo y usa la primera regla que coincide con el número marcado. Si configura un plan de marcado para que un número marcado pueda coincidir con más de una regla de normalización, asegúrese de que las reglas más restrictivas se ordenan por encima de las menos restrictivas. Si configura un plan de marcado que normaliza un número marcado sin un "+", el servicio de llamadas intentará normalizar el número de nuevo con las reglas del inquilino y del plan de marcado regional. Para evitar la doble normalización, se recomienda que todas las reglas de normalización den como resultado números empezando por un "+". Los clientes de Enrutamiento directo pueden usar [reglas de traducción troncal](direct-routing-translate-numbers.md) para quitar el "+" si es necesario. 

6. Haga clic en **Guardar**.
7. Si desea probar el plan de marcado, en Plan de marcado de **prueba,** escriba un número de teléfono y, a continuación, haga clic en **Probar.**

### <a name="edit-a-dial-plan"></a>Editar un plan de marcado

1. En el panel de navegación izquierdo del Microsoft Teams de administración, vaya a Plan **de marcado**  >  **de voz.**
2. Seleccione el plan de marcado haciendo clic a la izquierda del nombre del plan de marcado y, a continuación, haga clic en **Editar.**
3. Realice los cambios que desee y, a continuación, haga clic en **Guardar.**

### <a name="assign-a-dial-plan-to-users"></a>Asignar un plan de marcado a los usuarios

Asigne un plan de marcado de la misma manera que asigna directivas. [!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="using-powershell"></a>Con PowerShell
  
### <a name="start-powershell"></a>Iniciar PowerShell
- Abra un Windows PowerShell de comandos y ejecute los siguientes comandos:

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```
  
### <a name="create-and-manage-your-dial-plans"></a>Crear y administrar los planes de marcado

Para crear y administrar planes de marcado de inquilino puede utilizar un cmdlet sencillo o un script de PowerShell.
  
#### <a name="using-single-cmdlets"></a>Uso de cmdlets sencillos

- Para crear un nuevo plan de marcado, ejecute:
    
  ```PowerShell
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    Para ver otros ejemplos y parámetros, consulte [Nuevo-CsPlanMarcadoInquilinio](/powershell/module/skype/new-cstenantdialplan).
    
- Para editar la configuración de un plan de marcado existente, ejecute:
    
  ```PowerShell
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    Para ver otros ejemplos y parámetros, consulte[Configurar-CsPlanMarcadoInquilino](/powershell/module/skype/set-cstenantdialplan).
    
- Para agregar usuarios a un plan de marcado, ejecute:
    
  ```PowerShell
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    Para ver otros ejemplos y parámetros, consulte [Garantizar-CsPlanMarcadoInquilino](/powershell/module/skype/grant-cstenantdialplan).
    
- Para ver la configuración de un plan de marcado, ejecute:
    
  ```PowerShell
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    Para ver otros ejemplos y parámetros, consulte[Obtener-CsPlanMarcadoInquilino](/powershell/module/skype/get-cstenantdialplan?view=skype-ps).
    
- Para eliminar un plan de marcado, ejecute:
    
  ```PowerShell
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    Para ver otros ejemplos y parámetros, consulte [Eliminar-CsPlanMarcadoInquilino](/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).
    
- Para ver la configuración del plan de marcado efectivo, ejecute:
    
  ```PowerShell
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    Para ver otros ejemplos y parámetros, consulte [Obtener-CsPlanMarcadoEfectivoInquilino](/powershell/module/skype/get-cseffectivetenantdialplan).
    
- Para evaluar la configuración efectiva de un plan de marcado, ejecute:
    
  ```PowerShell
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    Para ver otros ejemplos y parámetros, consulte [Probar-CsPlanMarcadoEfectivoInquilino](/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).
    
#### <a name="using-a-powershell-script"></a>Uso de un script de PowerShell

Ejecute esto para eliminar una regla de normalización asociada a un plan de marcado de inquilino sin tener que eliminar primero el plan de marcado de inquilino:
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

Ejecute lo siguiente cuando desee examinar también las reglas de normalización existentes, determine cuál desea eliminar y, a continuación, use su índice para quitarlo. La matriz de reglas de normalización comienza con el índice 0. Nos gustaría eliminar la regla de normalización de tres dígitos, por lo que se trata del índice 1.
  
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

Ejecute esto para quitar cualquier TenantDialPlan asignado de todos los usuarios que tienen un HostProvider de sipfed.online.lync.com.
```PowerShell
Get-CsOnlineUser -Filter {HostingProvider -eq "sipfed.online.lync.com"} | Grant-CsTenantDialPlan -policyname $null
```

Ejecute estos para agregar el plan de marcado local existente denominado OPDP1 como un plan de marcado inquilino para su organización. Primero debe guardar el plan de marcado local en un archivo .xml local y, a continuación, usarlo para crear el nuevo plan de marcado de inquilino.
  
Ejecute esto para guardar el plan de marcado local en el .xml local.
  
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
- [Preguntas comunes sobre la transferencia de números de teléfono](./phone-number-calling-plans/port-order-overview.md)
- [Diferentes tipos de números de teléfono que se usan para Planes de llamada](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Administrar los números de teléfono para su organización](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [Términos y condiciones de las llamadas de emergencia](emergency-calling-terms-and-conditions.md)
- [Etiqueta de declinación de responsabilidades de llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
