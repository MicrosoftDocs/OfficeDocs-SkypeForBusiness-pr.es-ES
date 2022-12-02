---
title: Migrar desde Skype Empresarial Conector en línea al módulo PowerShell de Teams
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Obtenga información sobre cómo pasar de Skype Empresarial Conector en línea al módulo PowerShell de Teams para administrar Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 648ce1fb69f9e1641840f2e4b92acc1b98f4bbe8
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2022
ms.locfileid: "69242294"
---
# <a name="migrating-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>Migrar desde Skype Empresarial Conector en línea al módulo PowerShell de Teams

Módulo de PowerShell de Teams proporciona un conjunto completo de cmdlets para administrar Teams directamente desde la línea de comandos de PowerShell. Los administradores no necesitan Skype Empresarial Online Connector para su administración de Teams.

> [!NOTE]
> Se notificó al administrador de Teams a través de la publicación del Centro de mensajes (MC244740, de fecha 16 de marzo de 2021; MC250940, de fecha 16 de abril de 2021) sobre este cambio.
>
> El módulo PowerShell de Teams usa autenticación moderna, pero el cliente de Administración remota de Windows (WinRM) subyacente debe configurarse para permitir la autenticación básica. Consulte [Descargar e instalar Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1) para obtener instrucciones sobre cómo habilitar WinRM para la autenticación básica.

## <a name="how-to-migrate"></a>Cómo migrar

Migrar desde el uso de Skype Empresarial conector en línea al módulo de PowerShell de Teams es fácil y sencillo. En los pasos siguientes se explica cómo hacerlo.

1. Instale el módulo de PowerShell más reciente de Teams. Para conocer los pasos, consulte [Instalar Microsoft PowerShell de Teams](teams-powershell-install.md).

2. Desinstale Skype Empresarial Online Connector. Para ello, en Panel de control, ve a **Programas y características**, selecciona **Skype Empresarial en línea, Windows PowerShell Módulo** y, a continuación, selecciona **Desinstalar**.

3. En los scripts de PowerShell, cambie el nombre del módulo al que se hace referencia desde ```Import-Module```

    `SkypeOnlineConnector` o `LyncOnlineConnector` a `MicrosoftTeams`.

    Por ejemplo, cambie `Import-Module -Name SkypeOnlineConnector` a `Import-Module -Name MicrosoftTeams`.

4. Al usar el Módulo PowerShell 2.0 de Teams o posterior, actualice los scripts que hacen referencia `New-CsOnlineSession` a `Connect-MicrosoftTeams`. `Import-PsSession`ya no es necesario establecer una Skype Empresarial sesión remota de PowerShell en línea, ya que se hace implícita al usar `Connect-MicrosoftTeams`.

    ```powershell
       # When using the Skype for Business online connector
         
         # Establishing a session
         Import-Module SkypeOnlineConnector [LyncOnlineConnector]
         $credential = Get-Credential
         $SkypeSession = New-CsOnlineSession -Credential $credential
         Import-Session $SkypeSession
    
         # Example getting tenant details
         Get-csTenant
         
         # Disconnecting and closing the Session 
         Get-PsSession $SkypeSession | Remove-PsSession
    
       # When using Teams PowerShell Module 2.0 or later
       
         # Establishing a session
         Import-Module MicrosoftTeams
         $credential = Get-Credential
         Connect-MicrosoftTeams -Credential $credential
       
         # Example getting tenant details
         Get-csTenant
         
         # Disconnecting and closing the Session  
         Disconnect-MicrosoftTeams
    ```

## <a name="related-topics"></a>Temas relacionados

[Instalar Microsoft PowerShell de Teams](teams-powershell-install.md)

[Administrar Teams con PowerShell de Teams](teams-powershell-managing-teams.md)

[Notas de la versión de PowerShell de Teams](teams-powershell-release-notes.md)

[referencia de cmdlet de Microsoft Teams](/powershell/teams/)

[referencia de cmdlet de Skype Empresarial](/powershell/skype/intro)
