---
title: Establecer directivas de cliente en su organización
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 0326b19f-4fd1-4b74-8791-df4c09a964b9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: '[] Las directivas de cliente ayudan a determinar las funciones de Skype Empresarial Online que estarán disponibles para los usuarios. Por ejemplo, puede dar a algunos usuarios permiso para transferir archivos, pero no a otros.'
ms.openlocfilehash: 5f5d0d0cb6f404c7c1bb26f763ba15a402db966fd07c4471d0d7ce115cfbf791
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54282383"
---
# <a name="set-up-client-policies-for-your-organization"></a>Establecer directivas de cliente en su organización

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

[] Las directivas de cliente ayudan a determinar las funciones de Skype Empresarial Online que estarán disponibles para los usuarios. Por ejemplo, puede dar a algunos usuarios permiso para transferir archivos, pero no a otros.
  
La configuración de directiva de cliente se puede configurar en el momento en que se crea una directiva o puede usar el cmdlet **Set-CsClientPolicy** para modificar la configuración de una directiva existente.
  
## <a name="set-your-client-policies"></a>Establecer las directivas de cliente

> [!NOTE]
> Para toda la configuración de directiva de cliente en Skype Empresarial Online,  debe usar Windows PowerShell y no puede usar el centro de administración **Skype Empresarial cliente.** 
  
### <a name="start-windows-powershell"></a>Iniciar Windows PowerShell

> [!NOTE]
> El conector en línea del cliente de Skype® Empresarial actualmente forma parte del módulo más reciente de Windows PowerShell de Teams. Si usa la versión pública más reciente de Teams PowerShell, no es necesario que instale el conector en línea de cliente de Skype® Empresarial.
1. Instale el [Teams PowerShell](/microsoftteams/teams-powershell-install).
    
2. Abra un Windows PowerShell de comandos y ejecute los siguientes comandos: 

    ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   Si desea obtener más información sobre cómo iniciar Windows PowerShell, vea Conectar todos los servicios de Microsoft 365 o Office 365 en una única ventana de [Windows PowerShell](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) o Configurar el equipo para [Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
 
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a>Deshabilitar emoticonos y notificaciones de presencia y evitar el guardado de MENSAJES

- Para crear una nueva directiva para esta configuración, ejecute:
    
 
   ```powershell
   New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
   ```

  Más información sobre el cmdlet [New-CsClientPolicy.](/powershell/module/skype/New-CsClientPolicy)
    
- Para conceder la nueva directiva que creó a todos los usuarios de su organización, ejecute:
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
   ```

  Vea más sobre el cmdlet [Grant-CsClientPolicy.](/powershell/module/skype/Grant-CsClientPolicy)
    
Si ya ha creado una directiva, puede usar el cmdlet [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) para realizar cambios en la directiva existente y, después, usar el cmdlet [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) para aplicar la configuración a los usuarios.
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a>Permitir que se pueda hacer clic en las URL y los hiperenlaces en MI

- Para crear una nueva directiva para esta configuración, ejecute:
    
 
   ```powershell
   New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
   ```

  Más información sobre el cmdlet [New-CsClientPolicy.](/powershell/module/skype/New-CsClientPolicy)
    
- Para conceder la nueva directiva que creó a todos los usuarios de su organización, ejecute:
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
   ```

  Vea más sobre el cmdlet [Grant-CsClientPolicy.](/powershell/module/skype/Grant-CsClientPolicy)
    
Si ya ha creado una directiva, puede usar el cmdlet [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) para realizar cambios en la directiva existente y, después, usar el cmdlet [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) para aplicar la configuración a los usuarios.
  
### <a name="prevent-showing-recent-contacts"></a>Impedir que se muestren los contactos recientes

- Para crear una nueva directiva para esta configuración, ejecute:
   
   ```powershell
   New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
   ```

  Más información sobre el cmdlet [New-CsClientPolicy.](/powershell/module/skype/New-CsClientPolicy)
    
- Para conceder la nueva directiva que creó a Amos Marble, ejecute:
   
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
   ```

  Vea más sobre el cmdlet [Grant-CsClientPolicy.](/powershell/module/skype/Grant-CsClientPolicy)
    
  Si ya ha creado una directiva, puede usar el cmdlet [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) para realizar cambios en la directiva existente y, después, usar el cmdlet [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) para aplicar la configuración a los usuarios.
  
## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

- Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Microsoft 365 o Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario, cuando tiene varias tareas que hacer. Para empezar con Windows PowerShell, vea estos temas:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Seis motivos por los que es posible que desee usar Windows PowerShell administrar Microsoft 365 o Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell tiene muchas ventajas en la velocidad, la simplicidad y la productividad en lugar de usar solo el Centro de administración de Microsoft 365 como cuando realiza cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  - [Las mejores formas de administrar Microsoft 365 o Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>Temas relacionados
[Crear directivas personalizadas de acceso externo](create-custom-external-access-policies.md)

[Bloquear las transferencias de archivos punto a punto](block-point-to-point-file-transfers.md)

[Configurar directivas de conferencia en su organización](set-up-conferencing-policies-for-your-organization.md)

  
