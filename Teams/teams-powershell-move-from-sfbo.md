---
title: Migrar desde Skype Empresarial Online Connector al módulo Teams PowerShell
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Obtenga información sobre cómo pasar de Skype Empresarial Online Connector al módulo Teams PowerShell para administrar Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: e788fc8cd31bd6e8754e410132e02829eaa2cad8
ms.sourcegitcommit: 50ec59b454e751d952cde9fd13c8017529d0e1d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2021
ms.locfileid: "52469722"
---
# <a name="migrating-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>Migrar desde Skype Empresarial Online Connector al módulo Teams PowerShell

Teams El módulo de PowerShell proporciona un conjunto completo de cmdlets para administrar Teams directamente desde la línea de comandos de PowerShell. Los administradores no necesitan Skype For Business Online Connector para su Teams administración.

> [!NOTE]
> Teams a través de la publicación del Centro de mensajes (MC244740, fechada el 16 de marzo de 2021; MC250940, fechado el 16 de abril de 2021) sobre este cambio.
>
> Teams El módulo de PowerShell usa la autenticación moderna, pero el Windows de administración remota (WinRM) subyacente debe configurarse para permitir la autenticación básica. Vea [Descargar e instalar Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1) instrucciones sobre cómo habilitar WinRM para autenticación básica.

> [!WARNING]
> Skype Empresarial Las conexiones de Conector en línea se rechazarán a partir del 17 de mayo de 2021. Póngase en contacto con el soporte técnico de Microsoft para obtener ayuda y soporte técnico para migrar a Teams módulo de PowerShell.

## <a name="how-to-migrate"></a>Cómo migrar

Migrar desde el Skype Empresarial Online Connector a Teams módulo de PowerShell es fácil y sencillo. En los pasos siguientes se explica cómo hacerlo.

1. Instale la versión Teams módulo de PowerShell. Para ver los pasos, [vea Instalar Microsoft Teams Powershell](teams-powershell-install.md).
2. Desinstale Skype Para Empresas Online Connector. Para ello, en el Panel de control, vaya a Programas y **características,** seleccione **Skype Empresarial En línea, Windows PowerShell Módulo** y, a continuación, seleccione **Desinstalar**.
3. En los scripts de PowerShell, cambie el nombre del módulo al que se hace referencia ```Import-Module``` desde

    `SkypeOnlineConnector` o `LyncOnlineConnector` `MicrosoftTeams` para .

    Por ejemplo, cambie `Import-Module -Name SkypeOnlineConnector` a `Import-Module -Name MicrosoftTeams` .

4. Al usar Teams módulo de PowerShell 2.0 o posterior, actualice los scripts que se `New-CsOnlineSession` refieren a `Connect-MicrosoftTeams` . `Import-PsSession`ya no es necesario establecer un Skype Empresarial sesión remota de PowerShell en línea, ya que se realiza de forma implícita al usar `Connect-MicrosoftTeams` .

    ```powershell
       # When using the Skype for Business online connector
         Import-Module SkypeForBusinessConnector [LyncOnlineConnector]
         $credential = Get-Credential
         $SkypeSession = New-CsOnlineSession -Credential $credential
         Import-Session $SkypeSession
    
       # Example getting tenant details
         Get-csTenant
    
       # When using Teams PowerShell Module 2.0 or later
         Import-Module MicrosoftTeams
         $credential = Get-Credential
         Connect-MicrosoftTeams -Credential $credential
       
       # Example getting tenant details
         Get-csTenant
    
       # Closing the Session when using the Skype for Business online connector
         Get-PsSession $SkypeSession | Remove-PsSession
    
       # Disconnecting from Teams PowerShell Module 
         Disconnect-MicrosoftTeams
    ```

## <a name="online-support"></a>Soporte técnico en línea

Ahorre tiempo iniciando la solicitud de servicio en línea. Te ayudaremos a encontrar una solución o a conectarte con el soporte técnico.
1.  Vaya al Centro de administración en [https://admin.microsoft.com](https://admin.microsoft.com) . Si recibe un mensaje que indica que no tiene permiso para acceder a esta página o realizar esta acción, entonces no es administrador. Quién tiene permisos de administrador en mi empresa?
2.  Seleccione **¿Necesita ayuda?** botón.
3.  ¿Necesita **ayuda?** panel, díganos con qué necesita ayuda y, a continuación, presione Entrar.
4.  Si los resultados no le ayudan, seleccione **Ponerse en contacto con el soporte técnico.**
5.  Escriba una descripción del problema, confirme su número de contacto y su dirección de correo electrónico, seleccione el método de contacto que prefiera y, a continuación, seleccione **Contacto.** El tiempo de espera esperado se indica en el cuadro ¿Necesita ayuda? panel.

## <a name="related-topics"></a>Temas relacionados

[Instalar Microsoft Teams Powershell](teams-powershell-install.md)

[Administrar Teams con Teams PowerShell](teams-powershell-managing-teams.md)

[Teams Notas de la versión de PowerShell](teams-powershell-release-notes.md)

[Microsoft Teams referencia de cmdlet](/powershell/teams/?view=teams-ps)

[Skype Empresarial referencia de cmdlet](/powershell/skype/intro?view=skype-ps)
