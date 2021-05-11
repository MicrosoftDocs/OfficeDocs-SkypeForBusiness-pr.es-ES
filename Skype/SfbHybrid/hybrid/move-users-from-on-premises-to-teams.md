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
ms.openlocfilehash: 1d2542d3c5b67e935449b4f6fee60506b9232adc
ms.sourcegitcommit: 17ad87556fb8e0de3c498e53f98f951ae3fa526b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2021
ms.locfileid: "52306024"
---
# <a name="move-users-from-on-premises-to-teams"></a>Mover usuarios locales a Microsoft Teams

Cuando un usuario se mueve de local a solo Teams, la casa de Skype Empresarial del usuario se mueve de local Skype Empresarial en línea y se le asigna TeamsUpgradePolicy con mode=TeamsOnly.  Una vez que un usuario se mueve del modo local al modo TeamsOnly:

- Todas las llamadas entrantes y los chats de otros usuarios (ya sean enviados desde Skype Empresarial o Teams), llegarán al cliente de Teams usuario.
- El usuario podrá interoperar con otros usuarios que usan Skype Empresarial (ya sea en línea o local).
- El usuario podrá comunicarse con usuarios de organizaciones federadas.
- Las nuevas reuniones programadas por ese usuario se Teams reuniones.
- El usuario aún puede unirse a Skype Empresarial reuniones.
- Las reuniones preexistentes del usuario programadas para el futuro se migrarán de local a Teams.
- Los contactos que existían localmente están disponibles en Teams poco después de que el usuario inicie sesión por primera vez.
- Los usuarios no pueden iniciar llamadas o chats desde Skype Empresarial, ni pueden programar nuevas reuniones en Skype Empresarial. Si intentan abrir el cliente Skype Empresarial, se les redirigirá para que usen Teams como se muestra a continuación. Si el Teams no está instalado, se dirigirá a la versión web de Teams el explorador.<br><br>
    ![Mensaje que redirige a un usuario a Teams](../media/go-to-teams-page.png)

Antes de mover usuarios, asegúrese de revisar los [requisitos previos](move-users-between-on-premises-and-cloud.md#prerequisites) para mover usuarios a la nube. Asegúrese también de revisar las instrucciones de migración e interoperabilidad para las organizaciones que [usan Teams junto con Skype Empresarial](/microsoftteams/migration-interop-guidance-for-teams-with-skype).


> [!NOTE]
> El Almacén de contactos unificado debe deshabilitarse en la cuenta de SfB local para que el contacto se traslade a Teams.


Actualmente hay *dos* métodos para mover un usuario de local a Teams:

- Si usa una versión anterior a Skype Empresarial Server 2015 CU8, el movimiento requiere dos pasos (que se pueden crear juntos como un solo paso, si lo desea):
  - [Mueva el usuario de Skype Empresarial Server (local) a Skype Empresarial Online](move-users-from-on-premises-to-skype-for-business-online.md).
  - Una vez que el usuario se encuentra en Skype Empresarial Online, asigne al usuario TeamsUpgradePolicy con mode= TeamsOnly. Para conceder el modo TeamsOnly, ejecute el siguiente cmdlet desde una ventana Skype Empresarial PowerShell en línea:`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`
- Si tiene herramientas de administración de Skype Empresarial Server 2015 CU8 o posterior, puede usar el método anterior o puede realizar este movimiento en un paso como se describe a continuación. Además, opcionalmente, puede proporcionar una notificación dentro del cliente de Skype Empresarial antes de moverlos a Teams Only, así como, opcionalmente, que el cliente de Teams descargue silenciosamente el cliente Skype Empresarial.

> [!NOTE]
> En preparación para la próxima retirada de Skype Empresarial Online, Microsoft simplificará la forma en que las organizaciones se mueven a Teams próximamente. Al mover un usuario de local a Teams, pronto ya no será necesario especificar el cambio para mover usuarios directamente de local a `-MoveToTeams` `Move-CsUser` TeamsOnly. Actualmente, si no se especifica este modificador, los usuarios pueden pasar de hospedarse en Skype Empresarial Server local a Skype Empresarial Online y su modo permanece sin cambios. Después de retirarse, al mover un usuario de local a la nube con , se asignará automáticamente el modo TeamsOnly a los usuarios y sus reuniones desde locales se convertirán automáticamente en reuniones de Teams, igual que si el modificador , independientemente de si el modificador se especifica `Move-CsUser` `-MoveToTeams switch had been specified` realmente. Esperamos liberar esta funcionalidad antes de la retirada real del 31 de julio de 2021.

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a>Mover un usuario directamente de Skype Empresarial local a Teams solo

Las herramientas de administración locales de Skype Empresarial Server 2015 con CU8, así como en Skype Empresarial Server 2019, permiten mover usuarios de local a modo de solo Teams en un solo paso mediante el cmdlet Move-CsUser en PowerShell o el Panel de control de Skype Empresarial Server, como se describe a continuación.

### <a name="move-to-teams-using-move-csuser"></a>Mover a Teams con Move-CsUser

Move-CsUser está disponible desde una ventana de PowerShell Skype Empresarial shell de administración local. Los pasos siguientes y los permisos necesarios son los mismos que mover un usuario a Skype Empresarial Online, excepto que también debe especificar el modificador MoveToTeams y debe asegurarse de que al usuario también se le haya concedido una licencia para Teams (además de Skype Empresarial Online).

Debe tener privilegios suficientes tanto en el entorno local como en el servicio en la nube (Microsoft 365 o Office 365), tal como se describe en [Credenciales administrativas necesarias.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials) Puede usar una sola cuenta que tenga privilegios en ambos entornos o puede iniciar una ventana local del Shell de administración de Skype Empresarial Server con credenciales locales y usar el parámetro para especificar las credenciales de una cuenta de Microsoft 365 o Office 365 con el rol administrativo `-Credential` necesario.

Para mover un usuario al modo Teams solo con Move-CsUser:

- Especifique el usuario que se moverá mediante el `Identity` parámetro.
- Especifique el parámetro -Target con el valor "sipfed.online.lync. <span> com".
- Especifique el `MoveToTeams` modificador.
- Si no tiene una cuenta con permisos suficientes tanto en el servicio local como en el servicio en la nube (Microsoft 365 o Office 365), use el parámetro para proporcionar a una cuenta permisos suficientes en `-credential` Office 365.
- Si la cuenta con permisos en Microsoft 365 o Office 365 no termina en "onmicrosoft. <span> com", debe especificar el `-HostedMigrationOverrideUrl` parámetro, con el valor correcto como se describe en [Credenciales administrativas necesarias](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).

La siguiente secuencia de cmdlets se puede usar para mover un usuario a TeamsOnly y supone que la credencial Microsoft 365 o Office 365 es una cuenta independiente y se proporciona como entrada para el mensaje de Get-Credential.

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -Credential $cred -HostedMigrationOverrideUrl $url
  ```

> [!TIP]
> Como hay diferentes circunstancias que requieren parámetros diferentes, el comando predeterminado para la mayoría de los casos es:

```powershell
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -UseOAuth -HostedMigrationOverrideUrl $url
```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a>Pasar a Teams con Skype Empresarial Server Panel de control

1. Abre la aplicación Skype Empresarial Server panel de control.
2. En la navegación izquierda, elija **Usuarios**.
3. Use **Buscar** para localizar los usuarios que desea mover a Teams.
4. Seleccione los usuarios y, a  continuación, en el desplegable Acción situado encima de la lista, elija Mover usuarios seleccionados **a Teams**.
5. En el asistente, haga clic en **Siguiente**.
6. Si se le solicita, inicie sesión Microsoft 365 o Office 365 una cuenta que termine en .onmicrosoft.com y tenga permisos suficientes.
7. Haga **clic en** Siguiente y, a continuación, en Siguiente una vez más para mover al usuario. 
8. Ten en cuenta que los mensajes de estado relacionados con el éxito o el error se proporcionan en la parte superior de la aplicación principal del Panel de control, no en el asistente.

## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a>Notifique a Skype Empresarial usuarios locales del próximo movimiento a Teams

Las herramientas de administración locales de Skype Empresarial Server 2015 con CU8, así como en Skype Empresarial Server 2019, permiten notificar a los usuarios de Skype Empresarial locales su próximo traslado a Teams. Al habilitar estas notificaciones, los usuarios verán una notificación en su cliente de Skype Empresarial (Win32, Mac, web y móvil) como se muestra a continuación. Si los usuarios hacen **clic en el** botón Pruébalo, Teams se inicia el cliente si está instalado; de lo contrario, los usuarios se navegarán a la versión web de Teams en su explorador. De forma predeterminada, cuando las notificaciones están habilitadas, los clientes de Win32 Skype Empresarial descargan el cliente de Teams de forma silenciosa para que el cliente enriquecido esté disponible antes de mover al usuario al modo de solo Teams; sin embargo, también puede deshabilitar este comportamiento.  Las notificaciones se configuran mediante la versión local de , y la descarga silenciosa para los clientes de Win32 se controla mediante el `TeamsUpgradePolicy` `TeamsUpgradeConfiguration` cmdlet local.

> [!TIP]
> Es posible que algunos servidores deba reiniciar para que esto funcione en Skype Empresarial 2015 con CU8.

![Notificación del próximo movimiento a Teams](../media/teams-upgrade-notification.png)

Para notificar a los usuarios locales que pronto se actualizarán a Teams, cree una nueva instancia de TeamsUpgradePolicy con NotifySfBUsers=true. A continuación, asigne esa directiva a los usuarios a los que desea notificar, ya sea asignando la directiva directamente al usuario o estableciendo la directiva en el sitio, grupo o nivel global. Los cmdlets siguientes crean y conceden una directiva de nivel de usuario:

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

La descarga automática de Teams a través del Skype Empresarial cliente de Win32 se controla mediante el cmdlet TeamsUpgradeConfiguration local con el parámetro DownloadTeams. Esta configuración se crea en un nivel global, de sitio y de grupo. Por ejemplo, el siguiente comando crea la configuración del sitio Redmond1:

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

De forma predeterminada, el valor de DownloadTeams es True; sin embargo, *solo se respeta* si NotifySfbUser = True para un usuario determinado.

## <a name="see-also"></a>Vea también

[Move-CsUser](/powershell/module/skype/move-csuser)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy
)

[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[Coexistencia con Skype Empresarial](/microsoftteams/coexistence-chat-calls-presence)
