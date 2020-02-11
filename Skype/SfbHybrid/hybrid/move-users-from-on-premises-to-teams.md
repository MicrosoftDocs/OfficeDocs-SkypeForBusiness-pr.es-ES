---
title: Mover usuarios de Skype empresarial Server 2019 a teams
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 'Resumen: Obtenga información sobre cómo migrar la configuración de usuario y mover usuarios a Microsoft Teams.'
ms.openlocfilehash: af5281faffa9bd9439e045dc40f67283bb740cb5
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888779"
---
# <a name="move-users-from-on-premises-to-teams"></a>Mover usuarios de local a teams

Cuando un usuario se mueve de local a Microsoft Teams, la Página principal de Skype empresarial del usuario se mueve de local a en línea y se le asigna TeamsUpgradePolicy con MODE = TeamsOnly.  Después de que un usuario se haya movido del modo local al modo TeamsOnly:

- Todas las llamadas entrantes y chats de otros usuarios (ya sean enviados desde Skype empresarial o Teams) estarán en el cliente de Teams del usuario.
- El usuario podrá interactuar con otros usuarios que usan Skype empresarial (ya sea en línea o local).
- El usuario podrá comunicarse con los usuarios de organizaciones federadas.
- Las reuniones programadas por el usuario son nuevas reuniones de Microsoft Teams.
- El usuario todavía puede unirse a cualquier reunión de Skype empresarial.
- Las reuniones ya existentes del usuario programadas para el futuro se migrarán de local a teams.
- Los contactos que existían localmente están disponibles en Teams poco después de que el usuario inicie sesión por primera vez.
- Los usuarios no pueden iniciar llamadas o chats desde Skype empresarial, ni pueden programar nuevas reuniones en Skype empresarial. Si intentan abrir el cliente de Skype empresarial, se le redirigirá para usar Teams, como se muestra a continuación. Si el cliente de Microsoft Teams no está instalado, se le dirigirá a la versión Web de Teams mediante su explorador.<br><br>
    ![Mensaje que redirige a un usuario a Microsoft Teams](../media/go-to-teams-page.png)

Antes de mover los usuarios, asegúrese de revisar los [requisitos previos](move-users-between-on-premises-and-cloud.md#prerequisites) para mover usuarios a la nube. Además, asegúrese de revisar [las instrucciones de migración e interoperabilidad para las organizaciones que usan Teams junto con Skype empresarial](/microsoftteams/migration-interop-guidance-for-teams-with-skype).


> [!NOTE]
> El almacén de contactos unificado debe estar deshabilitado en la cuenta de SfB local para que el contacto se mueva a Microsoft Teams.


Hay dos métodos para mover un usuario de local a teams:

- Si utiliza una versión anterior a Skype empresarial Server 2015 CU8, el traslado requiere dos pasos (que se pueden convertir en scripts para realizarlos juntos como un solo paso, si así lo desea):
  - [Mueva el usuario de Skype empresarial Server (local) a Skype empresarial online](move-users-from-on-premises-to-skype-for-business-online.md).
  - Una vez que el usuario se hospeda en Skype empresarial online, asigne el usuario TeamsUpgradePolicy con MODE = TeamsOnly. Para conceder el modo TeamsOnly, ejecute el siguiente cmdlet desde una ventana de PowerShell de Skype empresarial online:`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`
- Si tiene herramientas de administración de Skype empresarial Server 2015 CU8 o posterior, puede usar el método anterior o puede hacerlo en un solo paso, como se describe a continuación. Además, puede proporcionar opcionalmente una notificación dentro del cliente de Skype empresarial antes de moverlos a Microsoft Teams y, opcionalmente, hacer que el cliente de Microsoft Teams Descargue silenciosamente el cliente de Skype empresarial.

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a>Mover un usuario directamente desde Skype empresarial a Microsoft Teams solo

Las herramientas de administración locales de Skype empresarial Server 2015 con CU8, así como de Skype empresarial Server 2019, permiten mover a los usuarios del modo local a teams en un solo paso mediante el cmdlet Move-CsUser en PowerShell o en el entorno de Skype empresarial se rVer panel de control, como se describe a continuación.

### <a name="move-to-teams-using-move-csuser"></a>Mover a Microsoft Teams con Move-CsUser

Move-CsUser está disponible en una ventana local de PowerShell del shell de administración de Skype empresarial. Los pasos que se indican a continuación y los permisos son los mismos que para mover un usuario a Skype empresarial online, excepto que también debe especificar el modificador MoveToTeams y debe asegurarse de que también se haya concedido una licencia para Teams a los usuarios (además de Skype empresarial). En línea).

Debe tener privilegios suficientes en el entorno local y en el inquilino de Office 365, tal y como se describe en [credenciales administrativas necesarias](move-users-between-on-premises-and-cloud.md#required-administrative-credentials). Puede usar una sola cuenta que tenga privilegios en ambos entornos, o puede iniciar una ventana del shell de administración local de Skype empresarial Server con credenciales locales y usar el `-Credential` parámetro para especificar las credenciales de una cuenta de Office 365 con el rol administrativo de Office 365 necesario.

Para mover un usuario al modo de solo Teams mediante Move-CsUser:

- Especifique el usuario que se va a `Identity` mover mediante el parámetro.
- Especifique el parámetro-Target con el valor "sipfed. online. Lync. <span>com ".
- Especifique el `MoveToTeams` modificador.
- Si no tiene una cuenta con permisos suficientes en local y Office 365, use el `-credential` parámetro para proporcionar una cuenta con permisos suficientes en Office 365.
- Si la cuenta con permisos en Office 365 no termina en "en Microsoft. <span>com ", debe especificar el `-HostedMigrationOverrideUrl` parámetro con el valor correcto tal y como se describe en [las credenciales administrativas necesarias](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).

La siguiente secuencia de cmdlet se puede usar para mover un usuario a TeamsOnly y asume que la credencial Office 365 es una cuenta independiente que se proporciona como entrada para el mensaje Get-Credential.

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -Credential $cred -HostedMigrationOverrideUrl $url
  ```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a>Mover a Microsoft Teams mediante el panel de control de Skype empresarial Server

1. Abra la aplicación del panel de control de Skype empresarial Server.
2. En el panel de navegación izquierdo, elija **usuarios**.
3. Use **Buscar** para localizar al usuario o usuarios que desea mover a Microsoft Teams.
4. Seleccione los usuarios y, a continuación, en la lista desplegable **acción** situada encima de la lista, elija **mover usuarios seleccionados a Microsoft Teams**.
5. En el asistente, haga clic en **Siguiente**.
6. Si se le solicita, inicie sesión en Office 365, con una cuenta que acabe en. onmicrosoft.com y que tenga permisos suficientes.
7. Haga clic en **siguiente**y, **a continuación, otra vez** más para mover al usuario.
8. Tenga en cuenta que los mensajes de estado sobre aciertos o errores se proporcionan en la parte superior de la aplicación del panel de control principal, no en el asistente.

## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a>Notificar a los usuarios locales de Skype empresarial del próximo paso a Microsoft Teams

Las herramientas de administración locales de Skype empresarial Server 2015 con CU8, así como de Skype empresarial Server 2019, le permiten notificar a los usuarios locales de Skype empresarial de su próximo paso a Microsoft Teams. Cuando habilite estas notificaciones, los usuarios verán una notificación en su cliente de Skype empresarial (Win32, Mac, Web y móvil), tal como se muestra a continuación. Si los usuarios hacen clic en el botón **probar** , el cliente de Microsoft Teams se iniciará si está instalado; de lo contrario, los usuarios se desplazarán a la versión Web de Teams en su explorador. De forma predeterminada, cuando se habilitan las notificaciones, los clientes de Skype empresarial de Win32 descargan silenciosamente el cliente de Microsoft Teams para que el cliente enriquecido esté disponible antes de mover al usuario al modo de solo Teams; sin embargo, también puede deshabilitar este comportamiento.  Las notificaciones se configuran con la versión local `TeamsUpgradePolicy`de, y la descarga silenciosa para los clientes Win32 se controla a `TeamsUpgradeConfiguration` través del cmdlet local.

> [!TIP]
> Es posible que algunos servidores deban reiniciarse para que funcione en Skype empresarial 2015 con CU8.

![Notificación del próximo traslado a Microsoft Teams](../media/teams-upgrade-notification.png)

Para notificar a los usuarios locales que pronto se actualizarán a Microsoft Teams, cree una nueva instancia de TeamsUpgradePolicy con NotifySfBUsers = true. A continuación, asigne la Directiva a los usuarios a los que quiera notificar, ya sea asignando la Directiva directamente al usuario o estableciendo la Directiva en el nivel global, de sitio o de grupo. Los siguientes cmdlets crean y conceden una directiva de nivel de usuario:

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

La descarga automática de equipos a través del cliente Win32 de Skype empresarial se controla a través del cmdlet TeamsUpgradeConfiguration local con el parámetro DownloadTeams. Esta configuración se crea en un nivel global, de sitio o de grupo. Por ejemplo, el siguiente comando crea la configuración para el sitio Redmond1:

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

De forma predeterminada, el valor de DownloadTeams es true; sin embargo, *solo* se acepta si NotifySfbUser = true para un usuario determinado.

## <a name="see-also"></a>Vea también

[Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy
)

[Guía de migración e interoperabilidad para organizaciones que usan Teams junto con Skype empresarial](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[Coexistencia con Skype empresarial](/microsoftteams/coexistence-chat-calls-presence)
