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
- Teams_ITAdmin_Help
search.appverid: MET150
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords:
- ms.teamsadmincenter.policies.naming.error
description: Vea ¿qué problemas hay con caracteres especiales en los nombres de las directivas y qué puede hacer para solucionarlo.
ms.openlocfilehash: 40cf70b61c8e939c2a1096825e83c676083b9950
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32204533"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>¿Cuáles son las restricciones de caracteres especiales en directivas de Teams?

**No puede crear o editar directivas (para mensajería, reuniones, etc.) que tienen un carácter especial en el nombre de la administración de equipos de Microsoft centro**. 

Si un nombre de directiva contiene caracteres especiales, estará limitado en la administración de estas directivas en el centro de administración de Microsoft Teams. **Por lo tanto, se recomienda encarecidamente que los nombres de directiva no incluir caracteres especiales**. 

Nombres de directiva que se han creado mediante PowerShell para las reuniones y mensajería en los equipos pueden tener caracteres especiales, como @, #, $. Sin embargo, si desea realizar cambios en la directiva en el centro de administración de Microsoft Teams, no podrá a. 

Si tiene una directiva con caracteres especiales, debe editar la directiva de uso de Windows PowerShell (siempre) o crear una nueva directiva en el centro de administración de Microsoft Teams con la misma configuración que la directiva antigua y asignar al mismo grupo de usuarios.

## <a name="to-remove-special-characters"></a>Para quitar los caracteres especiales

**Paso 1: establecer una conexión remota con PowerShell.** 
 [Configurar el equipo de Windows PowerShell](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) si no lo ha hecho todavía.
```
 Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
 $credential = Get-Credential
 $session = New-CsOnlineSession -Credential $credential
 Import-PSSession $session
```


**Paso 2: obtener la configuración de la directiva anterior y capturar el resultado.**

> [!NOTE]
> En este ejemplo es para una directiva de [mensajería](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) .  Los pasos sería el mismo para otros tipos de directiva, pero debe usar el cmdlet correcto. 

  ```
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


**Paso 3: crear una nueva directiva.**

Puede crear la nueva directiva con la misma configuración mediante el centro de administración de Microsoft Teams o PowerShell.

Ejecuta Esto creará una nueva directiva de pero necesita agregar la configuración correcta, vean [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) y, a continuación, si lo ejecuta:

  ```
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
**Paso 4: asignar la directiva.**
 ```
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
Vea, [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) para obtener más información sobre este cmdlet.

**Paso 5: eliminar la directiva anterior.**

Esta acción eliminará la directiva anterior con los caracteres especiales.
  ```
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
Vea, [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) para obtener más información sobre este cmdlet.

Si este comando se ejecuta correctamente, haya terminado. Si el comando anterior devuelve un error, es debido a que la directiva anterior se asigna a los usuarios por lo que necesita ejecutar para quitar todos los usuarios asignados de la directiva:

```
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [¿Por qué necesita usar Office 365 PowerShell?](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:
    
  - [An introduction to Windows PowerShell and Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > El módulo de Windows PowerShell para Skype para profesionales en línea le permite crear una sesión remota de Windows PowerShell que se conecta a Skype para profesionales en línea y Microsoft Teams. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  

