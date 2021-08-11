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
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policies.naming.error
- seo-marvel-mar2020
description: Vea qué problemas hay con caracteres especiales en los nombres de las directivas y qué puede hacer para solucionarlo.
ms.openlocfilehash: b8a628ee261ba813b50d58531ab1255a2f121dc4e4719ff4249de70517215cc3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54292977"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>¿Cuáles son las restricciones de caracteres especiales en directivas de Teams?

No puede crear ni editar directivas **(para mensajería, reuniones, etc.)** que tengan un carácter especial en el nombre del centro de administración Microsoft Teams correo electrónico. 

Si un nombre de directiva contiene caracteres especiales, se le limitará la administración de estas directivas en el centro Microsoft Teams administración. **Por lo tanto, recomendamos encarecidamente que los nombres de directiva no incluyan caracteres especiales.** 

Los nombres de directiva que se han creado con PowerShell para reuniones y mensajería en Teams pueden tener caracteres especiales como @,#,$. Sin embargo, si desea realizar cambios en la directiva en el centro de administración de Microsoft Teams, no podrá hacerlo. 

Si tiene una directiva con caracteres especiales, tendrá que editar la directiva con Windows PowerShell (para siempre) o crear una nueva directiva en el centro de administración de Microsoft Teams con la misma configuración que la directiva anterior y asignarla al mismo grupo de usuarios.

## <a name="to-remove-special-characters"></a>Para quitar caracteres especiales

**Paso 1: realizar una conexión remota con PowerShell.**
> [!NOTE]
> Skype Empresarial Online Connector forma parte actualmente de la versión Teams módulo de PowerShell.
>
> Si usa la versión pública más [reciente Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)no es necesario instalar el Skype Empresarial Online Connector.

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```


**Paso 2: obtenga la configuración de la directiva anterior y capture el resultado.**

> [!NOTE]
> Este ejemplo es para una [directiva de](/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) mensajería.  Los pasos serían los mismos para otros tipos de directiva, pero debe usar el cmdlet correcto. 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


**Paso 3: crear una directiva nueva.**

Puede crear la nueva directiva con la misma configuración mediante el centro de Microsoft Teams o PowerShell.

Al ejecutar esto, se creará una nueva directiva, pero tendrá que agregar la configuración correcta si ve [Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) y, a continuación, ejecutó:

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
**Paso 4: Asignar la directiva.**
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
Vea [Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) para obtener más información sobre este cmdlet.

**Paso 5: eliminar la directiva anterior.**

Esto eliminará la directiva anterior con los caracteres especiales.
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
Vea [Remove-CsTeamsMessagingPolicy](/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) para obtener más información sobre este cmdlet.

Si este comando se realiza correctamente, ya ha terminado. Si el comando anterior devuelve un error, se debe a que la directiva anterior está asignada a los usuarios, por lo que debe ejecutar para quitar todos los usuarios asignados de la directiva:

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Microsoft 365 o Office 365 mediante un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas que hacer. Para empezar con Windows PowerShell, vea estos temas:
    
  - [¿Por qué necesita usar Office 365 PowerShell?](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Las mejores formas de administrar Microsoft 365 o Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell tiene muchas ventajas en velocidad, simplicidad y productividad con respecto al uso de la Centro de administración de Microsoft 365, por ejemplo, cuando realiza cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los temas siguientes:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    [Usar Windows PowerShell para administrar Skype Empresarial Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    > [!NOTE]
    > El Windows PowerShell de Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta a Skype Empresarial Online y Microsoft Teams. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
