---
title: Establecer directivas móviles en su organización
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: beea47b2-7b9a-4b28-92d0-af65d80cd00f
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
description: Puede configurar cómo se conectan los usuarios a Skype Empresarial Online con la aplicación Skype Empresarial en dispositivos móviles, como una característica que permite a los usuarios realizar y recibir llamadas telefónicas en su teléfono móvil usando su número de teléfono del trabajo en lugar de su número de teléfono móvil. Las directivas de movilidad también se pueden usar para requerir conexiones WiFi para hacer o recibir llamadas.
ms.openlocfilehash: e29a02bddcb9ace29ebd059f8cbc42c5a85c3f12
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240072"
---
# <a name="set-up-mobile-policies-for-your-organization"></a>Establecer directivas móviles en su organización

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Puede configurar cómo se conectan los usuarios a Skype Empresarial Online con la aplicación Skype Empresarial en dispositivos móviles, como una característica que permite a los usuarios realizar y recibir llamadas telefónicas en su teléfono móvil usando su número de teléfono del trabajo en lugar de su número de teléfono móvil. Las directivas de movilidad también se pueden usar para requerir conexiones WiFi para hacer o recibir llamadas.
  
La configuración de directiva móvil se puede configurar en el momento en que se crea una directiva o puede usar el cmdlet **Set-CsMobilityPolicy** para modificar la configuración de una directiva existente.
  
## <a name="set-your-mobile-policies"></a>Establecer las directivas móviles

> [!NOTE]
> Para todas las configuraciones de directiva móvil en Skype Empresarial Online, debe  usar Windows PowerShell y no puede usar el centro de administración Skype Empresarial **móvil.** 
  
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
   
### <a name="require-a-wifi-connection-for-video-for-a-user"></a>Requerir que un usuario disponga de conexión WiFi para usar el vídeo

- Para crear una nueva directiva para esta configuración, ejecute:
   
   ```powershell
   New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
   ```
   Vea más sobre el cmdlet [New-CsMobilityPolicy.](/powershell/module/skype/New-CsMobilityPolicy)
    
- Para conceder la nueva directiva que creó a todos los usuarios de su organización, ejecute:
   
   ```powershell
   Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
   ```
   Vea más sobre el [cmdlet Grant-CsMobilityPolicy.](/powershell/module/skype/Grant-CsMobilityPolicy)
    
  Si ya ha creado una directiva, puede usar el cmdlet [Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) para realizar cambios en la directiva existente y, después, usar el cmdlet[Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) para aplicar la configuración a los usuarios.
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a>Impedir que un usuario use la aplicación Skype Empresarial

- Para crear una nueva directiva para esta configuración, ejecute:
  ```PowerShell
  New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
  ```
  Vea más sobre el cmdlet [New-CsMobilityPolicy.](/powershell/module/skype/New-CsMobilityPolicy)
    
- Para conceder la nueva directiva que creó a Amos Marble, ejecute:  
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
   ```
   Vea más sobre el [cmdlet Grant-CsMobilityPolicy.](/powershell/module/skype/Grant-CsMobilityPolicy)
    
  Si ya ha creado una directiva, puede usar el cmdlet [Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) para realizar cambios en la directiva existente y, después, usar el cmdlet [Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) para aplicar la configuración a los usuarios.
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a>Impedir que un usuario haga llamadas de voz sobre IP con un dispositivo móvil

- Para crear una nueva directiva para esta configuración, ejecute:
   
   ```powershell
   New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
   ```
   Vea más sobre el cmdlet [New-CsMobilityPolicy.](/powershell/module/skype/New-CsMobilityPolicy)
    
- Para conceder la nueva directiva que creó a todos los usuarios de su organización, ejecute:
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
   ```

  Vea más sobre el [cmdlet Grant-CsMobilityPolicy.](/powershell/module/skype/Grant-CsMobilityPolicy)
    
Si ya ha creado una directiva, puede usar el cmdlet [Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) para realizar cambios en la directiva existente y, después, usar el cmdlet[Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) para aplicar la configuración a los usuarios.
  
## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

- Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Microsoft 365 o Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario, cuando tiene varias tareas que hacer. Para empezar con Windows PowerShell, vea estos temas:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Seis motivos por los que es posible que desee usar Windows PowerShell administrar Microsoft 365 o Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell tiene muchas ventajas en velocidad, simplicidad y productividad en comparación con el uso del centro de administración de Microsoft 365, por ejemplo, cuando realiza cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  - [Las mejores formas de administrar Microsoft 365 o Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>Temas relacionados
[Crear directivas personalizadas de acceso externo](create-custom-external-access-policies.md)

[Bloquear las transferencias de archivos punto a punto](block-point-to-point-file-transfers.md)

[Establecer directivas de cliente en su organización](set-up-client-policies-for-your-organization.md)

[Configurar directivas de conferencia en su organización](set-up-conferencing-policies-for-your-organization.md)

  
