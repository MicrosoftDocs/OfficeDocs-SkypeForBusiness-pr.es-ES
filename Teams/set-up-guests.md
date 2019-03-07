---
title: Activar o desactivar el acceso de invitado a Microsoft Teams
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 03/06/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Active o desactive el acceso de invitado en Microsoft Teams.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: af8cb3f6c8ba764bfd813b9d65479404dfbf1983
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2019
ms.locfileid: "30462447"
---
<a name="turn-on-or-off-guest-access-to-microsoft-teams"></a>Activar o desactivar el acceso de invitado a Microsoft Teams
======================================

Como administrador de Office 365, debe habilitar la característica de invitado antes de que usted o los usuarios de su organización (específicamente, los propietarios de los equipos) puedan agregar a invitados. 

La configuración de invitado se establece en Azure Active Directory. Los cambios tardan de 2 a 24 en ser efectivos en toda la organización de Office 365. Si un usuario ve el mensaje "Póngase en contacto con el administrador" al intentar agregar un invitado a su equipo, es probable que todavía no se ha habilitado la característica de invitado o que la configuración no es efectiva todavía.

> [!IMPORTANT]
> Para habilitar la experiencia completa de la característica de acceso de invitado, es muy importante que conozca bien la dependencia de autorización principal entre Microsoft Teams, Azure Active Directory y Office 365. Para obtener más información, consulte [Autorizar el acceso de invitado en Microsoft Teams](Teams-dependencies.md).

## <a name="guest-access-vs-external-access-federation"></a>Acceso de invitado frente a acceso externo (federación de)

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="configure-guest-access-in-the-microsoft-teams-admin-center"></a>Configurar el acceso de invitado en el centro de administración de Microsoft Teams

1.  Inicie sesión en el centro de administración de Microsoft Teams.

2.  Seleccione **configuración de toda la organización** > **acceso de invitado**.

3. Configurar el conmutador de alternancia de **Permitir el acceso de invitado en los equipos de Microsoft** **activado**.

    ![Permitir modificador de acceso de Invitado activado ](media/set-up-guests-image1.png)

4.  Establecer el alterna en **mensajería** , **reunión**y **llamada**a **activado** o **desactivado**, dependiendo de las capacidades que desea permitir para los usuarios invitados.

    - **Realizar llamadas privadas** – activar esta opción **en** para permitir que los invitados realizar llamadas de punto a punto.
    - **Permitir IP vídeo** - activar esta opción **en** para permitir que los invitados a usar vídeo en sus llamadas y las reuniones.
    - **Modo de uso compartido de pantalla** : esta configuración controla la disponibilidad de pantalla de uso compartido para los usuarios invitados. 
       - Habilite esta configuración a **deshabilitado** para quitar la capacidad de los invitados a compartir sus pantallas en los equipos. 
       - Habilite esta configuración a **única aplicación** para permitir el uso compartido de aplicaciones individuales. 
       - Habilite esta configuración a **pantalla completa** para permitir el uso compartido de pantalla completa.
    - **Permitir Reunirse ahora** – activar esta opción **en** para permitir que los invitados a usar la característica Reunirse ahora en Microsoft Teams.
    - **Editar los mensajes enviados** : activar esta opción **en** para permitir que los invitados editar los mensajes envió anteriormente.
    - **Los invitados pueden eliminar los mensajes enviados** : activar esta opción **en** para permitir que los invitados eliminar los mensajes envió anteriormente.
    - **Chat** – activar esta opción **en** para dar invitados de la capacidad de usar chat en los equipos.
    - **Use Giphys en las conversaciones** – activar esta opción **en** para permitir que los invitados a usar Giphys en las conversaciones. Giphy es una base de datos en línea y un motor de búsqueda que permite a los usuarios buscar y compartir archivos GIF animados. A cada Giphy se le asigna una clasificación de contenido.
    - **Clasificación de contenido Giphy** – seleccionar una clasificación de la lista desplegable:
       - **Permitir todo el contenido** - invitados podrán insertar todos los Giphys en los chats, independientemente de la clasificación del contenido.
       - **Moderado** - invitados podrán insertar Giphys en los chats, pero se limitará moderadamente de contenido para adultos.
       - **Strict** – invitados podrán insertar Giphys en los chats, pero se limitará estrictamente de inserción de contenido para adultos.
    - **Use Memes en las conversaciones** - activar esta opción **en** para permitir que los invitados a usar Memes en las conversaciones.
    - **Usar pegatinas en conversaciones** – activar esta opción **en** para permitir que los invitados a usar pegatinas en conversaciones. 


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
