---
title: Activar o desactivar el acceso de invitado a Microsoft Teams
author: LaithAlShamri
ms.author: lolaj
manager: serdars
ms.date: 10/11/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: sbhatta
search.appverid: MET150
description: Active o desactive el acceso de invitado en Microsoft Teams.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3ab67b3fa9ad58c1aa3e8fdd254e3b3515743b4c
ms.sourcegitcommit: 9dd5d8fe6888f0c7d2df1e40fdd8b4c80512f8f9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/11/2018
ms.locfileid: "25498124"
---
<a name="turn-on-or-off-guest-access-to-microsoft-teams"></a>Activar o desactivar el acceso de invitado a Microsoft Teams
======================================

Como administrador de Office 365, debe habilitar la característica de invitado antes de que usted o los usuarios de su organización (específicamente, los propietarios de los equipos) puedan agregar a invitados. 

La configuración de invitado se establece en Azure Active Directory. Los cambios tardan de 2 a 24 en ser efectivos en toda la organización de Office 365. Si un usuario ve el mensaje "Póngase en contacto con su administrador" cuando intenta agregar un invitado a su equipo, es muy probable que la característica de invitado no esté habilitada o que la configuración no haya entrado aún en vigor.


> [!IMPORTANT]
> Para habilitar la experiencia completa de la característica de acceso de invitado, es muy importante que conozca bien la dependencia de autorización principal entre Microsoft Teams, Azure Active Directory y Office 365. Para obtener más información, consulte [Autorizar el acceso de invitado en Microsoft Teams](Teams-dependencies.md).

## <a name="configure-guest-access-in-the-teams--skype-for-business-admin-center"></a>Configurar el acceso de invitado en los equipos & Skype para centro de administración de negocio

1.  Inicie sesión en los equipos de & Skype para el centro de administración de negocio.

2.  Seleccione **configuración de toda la organización** > **acceso de invitado**.

3. Configurar el conmutador de alternancia de **Permitir el acceso de invitado en los equipos de Microsoft** **activado**.

    ![Permitir modificador de acceso de Invitado activado ](media/set-up-guests-image1.png)

4.  Establecer el alterna para **llamar a**, **reuniones**y **mensajería** a **activado** o **desactivado**, según el acceso que desea permitir.

5.  Haga clic en **Guardar**.

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a>Uso de PowerShell para activar o desactivar el acceso de invitado

1.  Descargar el Skype para el módulo de PowerShell en línea de negocio dehttps://www.microsoft.com/en-us/download/details.aspx?id=39366
 
2.  Conectar una sesión de PowerShell para la Skype de extremo de negocio en línea.

    ```
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.  Compruebe la configuración y si `AllowGuestUser` es `$False`, use el cmdlet [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) para establecer en `$True`.

    ```
    Get-CsTeamsClientConfiguration

    Identity                         : Global
    AllowEmailIntoChannel            : True
    RestrictedSenderList             :
    AllowDropBox                     : True
    AllowBox                         : True
    AllowGoogleDrive                 : True
    AllowShareFile                   : True
    AllowOrganizationTab             : True
    AllowSkypeBusinessInterop        : True
    AllowTBotProactiveMessaging      : False
    ContentPin                       : RequiredOutsideScheduleMeeting
    AllowResourceAccountSendMessage  : True
    ResourceAccountContentAccess     : NoAccess
    AllowGuestUser                   : True
    AllowScopedPeopleSearchandAccess : False
    
    Set-CsTeamsClientConfiguration -AllowGuestUser $True -Identity Global
    ```
Ahora puede tener los usuarios invitados en los equipos de la organización.

## <a name="more-information"></a>Más información

Vea el siguiente vídeo para obtener más detalles sobre el acceso de invitado.

|  |  |
|---------|---------|
| Agregar invitados en Microsoft Teams   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
