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
description: 'El servicio de conferencias es una parte importante de Skype Empresarial Online: mediante las conferencias, los grupos de usuarios pueden reunirse en línea para ver diapositivas y vídeo, compartir aplicaciones, cederse archivos, y colaborar y comunicarse de otros modos.'
ms.openlocfilehash: f5b420b9a5f288a0c733d3dfdc7ebc45fb323f32
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814759"
---
# <a name="set-up-conferencing-policies-for-your-organization"></a>Establecer directivas de conferencia en su organización

[] El servicio de conferencias es una parte importante de Skype Empresarial Online: mediante las conferencias, los grupos de usuarios pueden reunirse en línea para ver diapositivas y vídeo, compartir aplicaciones, cederse archivos, y colaborar y comunicarse de otros modos.
  
Es importante que mantenga el control sobre las conferencias y la configuración de conferencias. En algunos casos, puede haber problemas de seguridad: de forma predeterminada, todos los usuarios, incluidos los usuarios no autenticados, pueden participar en las reuniones y guardar cualquiera de las diapositivas o los folletos distribuidos durante esas reuniones. Además, puede haber problemas legales ocasionales. Por ejemplo, de forma predeterminada, los participantes de la reunión pueden hacer anotaciones en el contenido compartido; sin embargo, estas anotaciones no se guardan al archivar la reunión. Si su organización necesita mantener un registro de todas las comunicaciones electrónicas, es posible que desee deshabilitar las anotaciones. 
  
En Skype Empresarial Online, las conferencias se administran mediante directivas de conferencia. Las directivas de conferencia determinan las características y capacidades que se pueden usar en una conferencia, incluido todo, desde si la conferencia puede incluir audio y vídeo IP hasta el número máximo de personas que pueden asistir a una reunión. Las directivas de conferencia se pueden configurar en el ámbito global o en el ámbito por usuario. Esto ofrece a los administradores una enorme flexibilidad a la hora de decidir qué capacidades estarán disponibles para qué usuarios.
  
La configuración de la directiva se puede configurar al mismo tiempo que se crea la directiva o puede usar el cmdlet **Set-CsConferencingPolicy** para modificar la configuración de una directiva existente.
  
## <a name="set-your-conferencing-policies"></a>Establecer las directivas de conferencia

> [!NOTE]
> Para todas las configuraciones de directivas de conferencia en Skype Empresarial Online, debe usar Windows PowerShell y no puede usar el **Centro** de administración de **Skype Empresarial.** 
  
### <a name="verify-and-start-windows-powershell"></a>Verificar e iniciar Windows PowerShell

- **Comprobar que está ejecutando Windows PowerShell versión 3.0 o superior**
    
    1. Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.
        
    2. Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.
        
    3. Si no tiene la versión 3.0 o posterior, deberá descargar e instalar las actualizaciones para Windows PowerShell. Vea [Windows Management Framework 4.0 para](https://go.microsoft.com/fwlink/?LinkId=716845) descargar y actualizar Windows PowerShell a la versión 4.0. Reinicie el equipo cuando se le solicite.
        
    4. También necesitará instalar el módulo de Windows PowerShell para Teams que le permite crear una sesión de Windows PowerShell remota que se conecta a Skype Empresarial Online.
    
    Si necesita más información, vea Conectarse a todos los servicios de [Microsoft 365 u Office 365](https://technet.microsoft.com/library/dn568015.aspx)en una única Windows PowerShell ventana.
    
- **Iniciar una sesión de Windows PowerShell**
    
    1. En el **menú Inicio** > **Windows PowerShell**.
        
    2. En la **Windows PowerShell** de correo electrónico, conéctese a Su Microsoft 365 u Office 365 ejecutando:
        
     > [!NOTE]
     > Skype Empresarial Online Connector forma actualmente parte del módulo de PowerShell de Teams más reciente.
     >
     > Si usa la versión pública más reciente de PowerShell de [Teams,](https://www.powershellgallery.com/packages/MicrosoftTeams/)no es necesario instalar Skype Empresarial Online Connector.

       ```PowerShell      
        Import-Module -Name MicrosoftTeams
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   Si desea más información sobre cómo iniciar Windows PowerShell, consulte Conectarse a todos los servicios de [Microsoft 365 u Office 365](https://technet.microsoft.com/library/dn568015.aspx) en una única ventana de Windows PowerShell o Configurar el equipo para [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
### <a name="block-file-transfers-and-desktop-sharing-during-meetings"></a>Bloquear la transferencia de archivos y el uso compartido de escritorios durante las reuniones

- Para crear una nueva directiva para esta configuración, ejecute:
   
   ```powershell
   New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
   ```
   Más información sobre el [cmdlet New-CsConferencingPolicy.](https://technet.microsoft.com/library/mt779148.aspx)
    
- Para conceder la nueva directiva que ha creado a todos los usuarios de su organización, ejecute:
   
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
   ```
   Más información sobre el [cmdlet Grant-CsConferencingPolicy.](https://technet.microsoft.com/library/mt779156.aspx)
    
  Si ya ha creado una directiva, puede usar el cmdlet [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) para realizar cambios en la directiva existente y, a continuación, usar el cmdlet[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) para aplicar la configuración a los usuarios.
  
### <a name="block-recording-of-conferences-and-prevent-anonymous-meeting-participants"></a>Bloquear la grabación de conferencias y evitar que los participantes anónimos de la reunión

- Para crear una nueva directiva para esta configuración, ejecute: 
   
   ```powershell
   New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
   ```
   Más información sobre el [cmdlet New-CsConferencingPolicy.](https://technet.microsoft.com/library/mt779148.aspx)
    
- Para conceder la nueva directiva a Amos Marble, ejecute:
   
   ```powershell
    Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
   ```
   Más información sobre el [cmdlet Grant-CsConferencingPolicy.](https://technet.microsoft.com/library/mt779156.aspx)
    
Si ya ha creado una directiva, puede usar el cmdlet [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) para realizar cambios en la directiva existente y, a continuación, usar el cmdlet [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) para aplicar la configuración a los usuarios.
  
### <a name="block-anonymous-participants-from-recording-meetings-and-external-users-from-saving-meeting-content"></a>Impedir que los participantes anónimos puedan grabar reuniones y que los usuarios externos puedan guardar contenido de las reuniones

- Para crear una nueva directiva para esta configuración, ejecute:  
   
   ```powershell
   New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
   ```
   Más información sobre el [cmdlet New-CsConferencingPolicy.](https://technet.microsoft.com/library/mt779148.aspx)
    
- Para conceder la nueva directiva que ha creado a todos los usuarios de la organización, ejecute:
    
 
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
   ```

Más información sobre el [cmdlet Grant-CsConferencingPolicy.](https://technet.microsoft.com/library/mt779156.aspx)
    
Si ya ha creado una directiva, puede usar el cmdlet [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) para realizar cambios en la directiva existente y, a continuación, usar el cmdlet[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) para aplicar la configuración a los usuarios.
  
## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

- Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario cuando tenga que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Seis motivos por los que podría desear usar Windows PowerShell administrar Microsoft 365 u Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso solo del Centro de administración de Microsoft 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  - [Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Temas relacionados
[Crear directivas personalizadas de acceso externo](create-custom-external-access-policies.md)

[Bloquear las transferencias de archivos de punto a punto](block-point-to-point-file-transfers.md)

[Establecer directivas de cliente en su organización](set-up-client-policies-for-your-organization.md)

  
 
