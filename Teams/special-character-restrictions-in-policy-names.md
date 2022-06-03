---
title: Restricciones de caracteres especiales en directivas de Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policies.naming.error
- seo-marvel-mar2020
description: Vea qué problemas hay con caracteres especiales en los nombres de directivas y qué puede hacer para corregirlo.
ms.openlocfilehash: c304e292aa10508e7c8b02fe2825b83897f22e38
ms.sourcegitcommit: 1788f852508208a01f230f6f68a5a81ec8594c47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860083"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>¿Cuáles son las restricciones de caracteres especiales en directivas de Teams?

**No puede crear o editar directivas (por mensajería, reuniones, etc.) que tengan un carácter especial en el nombre del centro de administración de Microsoft Teams**. 

Si un nombre de directiva contiene caracteres especiales, se le limitará la administración de estas directivas en el centro de administración de Microsoft Teams. **Por lo tanto, recomendamos encarecidamente que los nombres de directiva no incluyan caracteres especiales**. 

Los nombres de directiva que se han creado con PowerShell para reuniones y mensajería en Teams pueden tener caracteres especiales, como @,#,$. Sin embargo, si desea realizar cambios en la directiva en el centro de administración de Microsoft Teams, no podrá hacerlo. 

Si tiene una directiva con caracteres especiales, tendrá que editarla con Windows PowerShell (para siempre) o crear una directiva en el centro de administración de Microsoft Teams con la misma configuración que la directiva anterior y asignarla al mismo grupo de usuarios.

## <a name="to-remove-special-characters"></a>Para quitar caracteres especiales

**Paso 1: realizar una conexión remota con PowerShell.**
> [!NOTE]
> Skype Empresarial Online Connector forma parte actualmente del módulo de PowerShell de Teams más reciente.
>
> Si usa la versión pública más reciente [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/), no es necesario instalar el conector en línea de Skype Empresarial.

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```


**Paso 2: Obtener la configuración de la directiva antigua y capturar la salida.**

> [!NOTE]
> Este ejemplo es para una directiva [de mensajes](/powershell/module/skype/get-csteamsmessagingpolicy) .  Los pasos serían los mismos para otros tipos de directiva, pero debe usar el cmdlet correcto. 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


**Paso 3: Crear una nueva directiva.**

Puede crear la nueva directiva con la misma configuración mediante el centro de administración de Microsoft Teams o PowerShell.

Ejecutar esto creará una nueva directiva para usted, pero tendrá que agregar la configuración correcta viendo [Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy) y luego ejecutándola:

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
**Paso 4: asignar la directiva.**
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
Consulte [Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy) para obtener más información sobre este cmdlet.

**Paso 5: eliminar la directiva anterior.**

Esto eliminará la directiva anterior con los caracteres especiales.
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
Consulte [Remove-CsTeamsMessagingPolicy](/powershell/module/skype/remove-csteamsmessagingpolicy) para obtener más información sobre este cmdlet.

Si este comando se ejecuta correctamente, habrá terminado. Si el comando anterior devuelve un error, es porque la directiva anterior se asigna a los usuarios, por lo que deberá ejecutarla para quitar todos los usuarios asignados de la directiva:

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Microsoft 365 o Office 365 con un único punto de administración que puede simplificar su trabajo diario cuando tenga que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:
    
  - [¿Por qué necesita usar Office 365 PowerShell?](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Las mejores formas de administrar Microsoft 365 o Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell tiene muchas ventajas en velocidad, simplicidad y productividad con respecto al uso solo de los Centro de administración de Microsoft 365, como cuando se realizan cambios en la configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    [Usar Windows PowerShell para administrar Skype Empresarial Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    > [!NOTE]
    > El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta a Skype Empresarial Online y Microsoft Teams. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)
