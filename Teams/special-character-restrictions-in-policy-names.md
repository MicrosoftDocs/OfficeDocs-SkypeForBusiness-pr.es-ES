---
title: ¿Cuáles son las restricciones de caracteres especiales en directivas de Teams?
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
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords:
- ms.teamsadmincenter.policies.naming.error
description: Vea qué problemas hay con caracteres especiales en los nombres de las directivas y qué puede hacer para corregirlo.
ms.openlocfilehash: a3e7bccc78641a07b7e2f2b02e12b6fe501f2405
ms.sourcegitcommit: 1de5e4d829405b75c0a87918cc7c8fa7227e0ad6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "40952763"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>¿Cuáles son las restricciones de caracteres especiales en directivas de Teams?

**No puede crear o editar directivas (de mensajería, reuniones, etc.) que tengan un carácter especial en el nombre en el centro de administración de Microsoft Teams**. 

Si un nombre de Directiva contiene caracteres especiales, tendrá limitaciones para administrar estas directivas en el centro de administración de Microsoft Teams. **Como tal, recomendamos encarecidamente que los nombres de las directivas no incluyan caracteres especiales**. 

Los nombres de directiva que se han creado con PowerShell para reuniones y mensajería en Teams pueden tener caracteres especiales como @, #, $. Sin embargo, si desea realizar cambios en la Directiva en el centro de administración de Microsoft Teams, no podrá. 

Si tiene una directiva con caracteres especiales, tendrá que editar la Directiva con Windows PowerShell (para siempre) o crear una nueva Directiva en el centro de administración de Microsoft Teams con la misma configuración que la directiva anterior y asignarla al mismo grupo de usuarios.

## <a name="to-remove-special-characters"></a>Para quitar caracteres especiales

**Paso 1: establecer una conexión remota con PowerShell.** 
 [Configure su equipo para Windows PowerShell](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) si todavía no lo ha hecho.
```PowerShell
 Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
 $credential = Get-Credential
 $session = New-CsOnlineSession -Credential $credential
 Import-PSSession $session
```


**Paso 2: obtenga la configuración de la directiva anterior y Capture la salida.**

> [!NOTE]
> Este ejemplo es para una directiva de [Mensajería](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) .  Los pasos serían iguales para otros tipos de directivas, pero debe usar el cmdlet correcto. 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


**Paso 3: crear una nueva Directiva.**

Puede crear la nueva directiva con la misma configuración con el centro de administración de Microsoft Teams o PowerShell.

Si se ejecuta, se creará una nueva Directiva, pero tendrá que agregar la configuración correcta si ve [set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) y, a continuación, lo ejecuta:

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
**Paso 4: asignar la Directiva.**
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
Para obtener más información sobre este cmdlet, consulte [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) .

**Paso 5: eliminar la directiva anterior.**

Esto eliminará la directiva anterior con los caracteres especiales.
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
Para obtener más información sobre este cmdlet, consulte [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) .

Si este comando se ejecuta correctamente, ya habrá terminado. Si el comando anterior devuelve un error, esto se debe a que la Directiva antigua se asigna a los usuarios, por lo que necesita ejecutar para quitar todos los usuarios asignados de la Directiva:

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [¿Por qué necesita usar Office 365 PowerShell?](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell tiene muchas ventajas en cuanto a velocidad, simplicidad y productividad en lugar de usar únicamente el centro de administración de Microsoft 365, por ejemplo, cuando está realizando cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los temas siguientes:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > El módulo Windows PowerShell para Skype empresarial online le permite crear una sesión remota de Windows PowerShell que se conecta a Skype empresarial online y Microsoft Teams. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  

