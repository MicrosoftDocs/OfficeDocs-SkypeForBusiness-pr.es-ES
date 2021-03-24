---
title: Establecer directivas de conferencia en su organización
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9957722b-b542-49ad-8ec8-5569df7fb08b
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
description: '[] El servicio de conferencias es una parte importante de Skype Empresarial Online: mediante las conferencias, los grupos de usuarios pueden reunirse en línea para ver diapositivas y vídeo, compartir aplicaciones, cederse archivos, y colaborar y comunicarse de otros modos.'
ms.openlocfilehash: f4c8831408ed5c17073456306c0f48add73161ff
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100526"
---
# <a name="set-up-conferencing-policies-for-your-organization"></a>Establecer directivas de conferencia en su organización

[] El servicio de conferencias es una parte importante de Skype Empresarial Online: mediante las conferencias, los grupos de usuarios pueden reunirse en línea para ver diapositivas y vídeo, compartir aplicaciones, cederse archivos, y colaborar y comunicarse de otros modos.
  
Es importante que mantenga el control sobre las conferencias y su configuración. En algunos casos puede ser necesario cierto grado de seguridad, pues, de forma predeterminada, todos los usuarios, incluidos los no autenticados, pueden participar en las reuniones, y guardar las diapositivas y documentos informativos que se distribuyan en ellas. Además, es posible que deban tenerse en cuenta aspectos legales. Por ejemplo, de forma predeterminada, los participantes de la reunión pueden realizar anotaciones en contenido compartido; sin embargo, estas anotaciones no se guardan cuando se archiva la reunión. Si su organización debe conservar un registro de toda la comunicación electrónica, es posible que prefiera desactivar las anotaciones. 
  
En Skype Empresarial Online, las conferencias se administran mediante directivas de conferencia. Las directivas de conferencia determinan las funcionalidades y características que se pueden usar en una conferencia y cubren todos los aspectos, desde si la conferencia puede incluir o no audio y vídeo IP, hasta el número máximo de personas que pueden asistir a una reunión. Las directivas de conferencia se pueden configurar para que tengan aplicación global o por usuario. Esto ofrece a los administradores una enorme flexibilidad a la hora de decidir qué características podrán usar qué usuarios.
  
La configuración de directiva se puede configurar en el momento en que se crea una directiva o puede usar el cmdlet **Set-CsConferencingPolicy** para modificar la configuración de una directiva existente.
  
## <a name="set-your-conferencing-policies"></a>Establecer las directivas de conferencia

> [!NOTE]
> Para todas las configuraciones de directiva de conferencia en Skype Empresarial  Online, debe usar Windows PowerShell y no puede usar el Centro de administración **de Skype Empresarial.** 

### <a name="start-windows-powershell"></a>Iniciar Windows PowerShell

 > [!Note]
> El conector en línea del cliente de Skype® Empresarial actualmente forma parte del módulo más reciente de Windows PowerShell de Teams. Si usa la versión pública más reciente de Teams PowerShell, no es necesario que instale el conector en línea de cliente de Skype® Empresarial.
1. Instale el [módulo de PowerShell de Teams.](/microsoftteams/teams-powershell-install)
    
2. Abra un Windows PowerShell de comandos y ejecute los siguientes comandos: 

   ```powershell
   # When using Teams PowerShell Module 
   
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   Si desea obtener más información sobre cómo iniciar Windows PowerShell, vea Conectarse a todos los servicios de [Microsoft 365 u Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) en una sola ventana de Windows PowerShell o Configurar el equipo para [Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
      
### <a name="block-file-transfers-and-desktop-sharing-during-meetings"></a>Bloquear la transferencia de archivos y el uso compartido de escritorios durante las reuniones

- Para crear una nueva directiva para esta configuración, ejecute:
   
   ```powershell
   New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
   ```
   Vea más sobre el cmdlet [New-CsConferencingPolicy.](/powershell/module/skype/New-CsConferencingPolicy)
    
- Para conceder la nueva directiva que creó a todos los usuarios de su organización, ejecute:
   
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
   ```
   Vea más sobre el cmdlet [Grant-CsConferencingPolicy.](/powershell/module/skype/Grant-CsConferencingPolicy)
    
  Si ya ha creado una directiva, puede usar el cmdlet [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) para realizar cambios en la directiva existente y, después, usar el cmdlet[Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) para aplicar la configuración a los usuarios.
  
### <a name="block-recording-of-conferences-and-prevent-anonymous-meeting-participants"></a>Bloquear la grabación de conferencias y evitar participantes anónimos de la reunión

- Para crear una nueva directiva para esta configuración, ejecute: 
   
   ```powershell
   New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
   ```
   Vea más sobre el cmdlet [New-CsConferencingPolicy.](/powershell/module/skype/New-CsConferencingPolicy)
    
- Para conceder la nueva directiva que creó a Amos Marble, ejecute:
   
   ```powershell
    Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
   ```
   Vea más sobre el cmdlet [Grant-CsConferencingPolicy.](/powershell/module/skype/Grant-CsConferencingPolicy)
    
Si ya ha creado una directiva, puede usar el cmdlet [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) para realizar cambios en la directiva existente y, después, usar el cmdlet [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) para aplicar la configuración a los usuarios.
  
### <a name="block-anonymous-participants-from-recording-meetings-and-external-users-from-saving-meeting-content"></a>Impedir que los participantes anónimos puedan grabar reuniones y que los usuarios externos puedan guardar contenido de las reuniones

- Para crear una nueva directiva para esta configuración, ejecute:  
   
   ```powershell
   New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
   ```
   Vea más sobre el cmdlet [New-CsConferencingPolicy.](/powershell/module/skype/New-CsConferencingPolicy)
    
- Para conceder la nueva directiva que creó a todos los usuarios de su organización, ejecute:
    
 
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
   ```

Vea más sobre el cmdlet [Grant-CsConferencingPolicy.](/powershell/module/skype/Grant-CsConferencingPolicy)
    
Si ya ha creado una directiva, puede usar el cmdlet [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) para realizar cambios en la directiva existente y, después, usar el cmdlet[Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) para aplicar la configuración a los usuarios.
  
## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

- Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario, cuando tiene varias tareas que hacer. Para empezar con Windows PowerShell, vea estos temas:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Seis razones por las que es posible que desee usar Windows PowerShell administrar Microsoft 365 u Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell tiene muchas ventajas en velocidad, sencillez y productividad sobre el uso solo del Centro de administración de Microsoft 365, como cuando realiza cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  - [Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a>Temas relacionados
[Crear directivas personalizadas de acceso externo](create-custom-external-access-policies.md)

[Bloquear las transferencias de archivos punto a punto](block-point-to-point-file-transfers.md)

[Establecer directivas de cliente en su organización](set-up-client-policies-for-your-organization.md)

  
