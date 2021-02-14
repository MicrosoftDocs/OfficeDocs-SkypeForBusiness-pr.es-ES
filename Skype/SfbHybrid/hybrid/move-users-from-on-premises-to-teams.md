---
title: Mover usuarios de Skype Empresarial Server 2019 a Teams
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
description: 'Resumen: obtenga información sobre cómo migrar la configuración de usuario y mover usuarios a Teams.'
ms.openlocfilehash: 49763d7674946eb179188554326863f4860252c3
ms.sourcegitcommit: 7966991c398cd80f6bd0bb21e57a6b2a97c09ea9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130651"
---
# <a name="move-users-from-on-premises-to-teams"></a>Mover usuarios locales a Microsoft Teams

Cuando un usuario se mueve de local a Solo Teams, la página principal de Skype Empresarial del usuario se mueve de local a en línea y se le asigna TeamsUpgradePolicy con mode=TeamsOnly.  Después de mover un usuario del modo local al modo TeamsOnly:

- Todas las llamadas entrantes y los chats de otros usuarios (ya sean enviados desde Skype Empresarial o Teams), llegarán al cliente de Teams del usuario.
- El usuario podrá interoperar con otros usuarios que usen Skype Empresarial (ya sea en línea o local).
- El usuario podrá comunicarse con los usuarios de organizaciones federadas.
- Las nuevas reuniones programadas por ese usuario son reuniones de Teams.
- El usuario aún puede unirse a cualquier reunión de Skype Empresarial.
- Las reuniones preexistentes del usuario programadas para el futuro se migrarán de local a Teams.
- Los contactos que existían localmente están disponibles en Teams poco después de que el usuario inicie sesión por primera vez.
- Los usuarios no pueden iniciar llamadas ni chats desde Skype Empresarial, ni pueden programar nuevas reuniones en Skype Empresarial. Si intenta abrir el cliente de Skype Empresarial, se le redirigirá para que use Teams, como se muestra a continuación. Si el cliente de Teams no está instalado, se le dirigirá a la versión web de Teams mediante su explorador.<br><br>
    ![Mensaje que redirige a un usuario a Teams](../media/go-to-teams-page.png)

Antes de mover usuarios, asegúrese de revisar los [requisitos previos](move-users-between-on-premises-and-cloud.md#prerequisites) para mover usuarios a la nube. Asegúrese también de revisar la guía de migración e interoperabilidad para las [organizaciones que usan Teams junto con Skype Empresarial.](/microsoftteams/migration-interop-guidance-for-teams-with-skype)


> [!NOTE]
> El almacén de contactos unificado debe deshabilitarse en la cuenta de SfB local para que el contacto se traslade a Teams.


Hay dos métodos para mover un usuario localmente a Teams:

- Si usa una versión anterior a Skype Empresarial Server 2015 CU8, el movimiento requiere dos pasos (que se pueden ejecutar conjuntamente como un solo paso, si lo desea):
  - [Mueva el usuario de Skype Empresarial Server (local) a Skype Empresarial Online.](move-users-from-on-premises-to-skype-for-business-online.md)
  - Una vez que el usuario esté en Skype Empresarial Online, asigne al usuario TeamsUpgradePolicy con mode= TeamsOnly. Para conceder el modo TeamsOnly, ejecute el siguiente cmdlet desde una ventana de PowerShell de Skype Empresarial Online: `Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`
- Si tiene herramientas de administración de Skype Empresarial Server 2015 CU8 o posterior, puede usar el método anterior o puede realizar este movimiento en un paso como se describe a continuación. Además, puede proporcionar opcionalmente una notificación dentro del cliente de Skype Empresarial antes de moverlos a Teams solo, así como, opcionalmente, hacer que el cliente de Teams descargue silenciosamente el cliente de Skype Empresarial.

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a>Mover un usuario directamente de Skype Empresarial local a Solo Teams

Las herramientas de administración locales en Skype Empresarial Server 2015 con CU8, así como en Skype Empresarial Server 2019, permiten mover usuarios del modo local al modo de solo Teams en un solo paso mediante el cmdlet Move-CsUser en PowerShell o el Panel de control de Skype Empresarial Server, como se describe a continuación.

### <a name="move-to-teams-using-move-csuser"></a>Cambiar a Teams con Move-CsUser

Move-CsUser está disponible desde una ventana local de PowerShell del Shell de administración de Skype Empresarial. Los pasos siguientes y los permisos necesarios son los mismos que para mover un usuario a Skype Empresarial Online, excepto que también debe especificar el modificador MoveToTeams y debe asegurarse de que al usuario también se le ha concedido una licencia para Teams (además de Skype Empresarial Online).

Debe tener privilegios suficientes tanto en el entorno local como en el servicio en la nube (Microsoft 365 u Office 365), como se describe en Credenciales administrativas [necesarias.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials) Puede usar una sola cuenta que tenga privilegios en ambos entornos o puede iniciar una ventana local del Shell de administración de Skype Empresarial Server con credenciales locales y usar el parámetro para especificar las credenciales de una cuenta de `-Credential` Microsoft 365 u Office 365 con el rol administrativo necesario.

Para mover un usuario al modo solo de Teams con Move-CsUser:

- Especifique el usuario que se moverá mediante el `Identity` parámetro.
- Especifique el parámetro -Target con el valor "sipfed.online.lync. <span> com".
- Especifique el `MoveToTeams` modificador.
- Si no tiene una cuenta con permisos suficientes tanto en el servicio local como en el servicio en la nube (Microsoft 365 u Office 365), use el parámetro para proporcionar a una cuenta los permisos suficientes en `-credential` Office 365.
- Si la cuenta con permisos en Microsoft 365 u Office 365 no termina en "onmicrosoft. <span> com", debe especificar el `-HostedMigrationOverrideUrl` parámetro, con el valor correcto como se describe en [Credenciales administrativas necesarias.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)

La siguiente secuencia de cmdlets se puede usar para mover un usuario a TeamsOnly y supone que la credencial de Microsoft 365 u Office 365 es una cuenta independiente y se proporciona como entrada para el mensaje Get-Credential usuario.

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -Credential $cred -HostedMigrationOverrideUrl $url
  ```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a>Cambiar a Teams con el Panel de control de Skype Empresarial Server

1. Abra la aplicación Panel de control de Skype Empresarial Server.
2. En el panel de navegación izquierdo, elija **Usuarios.**
3. Use **Buscar** para localizar los usuarios que desea mover a Teams.
4. Seleccione los usuarios y, a  continuación, en el desplegable Acción situado encima de la lista, elija Mover usuarios seleccionados **a Teams.**
5. En el asistente, haga clic en **Siguiente**.
6. Si se le solicita, inicie sesión en Microsoft 365 u Office 365 con una cuenta que termine en .onmicrosoft.com y tenga permisos suficientes.
7. Haga **clic en** Siguiente y, a **continuación,** en Siguiente una vez más para mover el usuario.
8. Tenga en cuenta que los mensajes de estado relacionados con el éxito o el error se proporcionan en la parte superior de la aplicación principal del Panel de control, no en el asistente.

## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a>Notificar a los usuarios locales de Skype Empresarial el próximo cambio a Teams

Las herramientas de administración locales en Skype Empresarial Server 2015 con CU8, así como en Skype Empresarial Server 2019, le permiten notificar a los usuarios locales de Skype Empresarial su próximo movimiento a Teams. Al habilitar estas notificaciones, los usuarios verán una notificación en su cliente de Skype Empresarial (Win32, Mac, web y móvil) como se muestra a continuación. Si los usuarios hacen **clic en** el botón Probar, el cliente de Teams se inicia si está instalado; de lo contrario, los usuarios se desplazarán a la versión web de Teams en su explorador. De forma predeterminada, cuando las notificaciones están habilitadas, los clientes de Skype Empresarial de Win32 descargan silenciosamente el cliente de Teams para que el cliente enriquecido esté disponible antes de mover al usuario al modo solo de Teams; sin embargo, también puede deshabilitar este comportamiento.  Las notificaciones se configuran mediante la versión local de y la descarga silenciosa para clientes de Win32 se controla mediante `TeamsUpgradePolicy` el `TeamsUpgradeConfiguration` cmdlet local.

> [!TIP]
> Es posible que algunos servidores deba reiniciar para que funcione en Skype Empresarial 2015 con CU8.

![Notificación del próximo movimiento a Teams](../media/teams-upgrade-notification.png)

Para notificar a los usuarios locales que pronto se actualizarán a Teams, cree una nueva instancia de TeamsUpgradePolicy con NotifySfBUsers=true. A continuación, asigne esa directiva a los usuarios a los que desee notificar, ya sea asignando la directiva directamente al usuario o estableciendo la directiva en el sitio, grupo o nivel global. Los siguientes cmdlets crean y conceden una directiva de nivel de usuario:

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

La descarga automática de Teams a través del cliente win32 de Skype Empresarial se controla mediante el cmdlet local TeamsUpgradeConfiguration con el parámetro DownloadTeams. Esta configuración se crea en un nivel global, de sitio y de grupo. Por ejemplo, el siguiente comando crea la configuración para el sitio Redmond1:

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

De forma predeterminada, el valor de DownloadTeams es True; sin embargo, *solo se respeta* si NotifySfbUser = True para un usuario determinado.

## <a name="see-also"></a>Vea también

[Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy
)

[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[Coexistencia con Skype Empresarial](/microsoftteams/coexistence-chat-calls-presence)
