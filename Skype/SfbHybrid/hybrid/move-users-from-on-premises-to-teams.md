---
title: Traslado de usuarios de Skype Empresarial Server 2019 a Teams
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
search.appverid: MET150
ms.custom: ''
description: 'Resumen: obtenga información sobre cómo migrar la configuración de usuario y mover usuarios a Teams.'
ms.openlocfilehash: d29fa49e3521e93cb1818c70adb37cfb5019660b
ms.sourcegitcommit: 0bf44683f5263d7bf635689b4c1d813bd9842650
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67705849"
---
# <a name="move-users-from-on-premises-to-teams"></a>Mover usuarios locales a Microsoft Teams

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Cuando un usuario se mueve de local a Solo Teams, el Skype Empresarial inicio del usuario se mueve de local a en línea y al usuario se le asigna TeamsUpgradePolicy con mode=TeamsOnly.  Después de mover un usuario del entorno local al modo TeamsOnly:

- Todas las llamadas entrantes y los chats de otros usuarios (ya sean enviados desde Skype Empresarial o Teams), llegarán al cliente de Teams del usuario.
- El usuario podrá interoperar con otros usuarios que usen Skype Empresarial (ya sea en línea o local).
- El usuario podrá comunicarse con los usuarios de organizaciones federadas.
- Las nuevas reuniones programadas por ese usuario son reuniones de Teams.
- El usuario todavía puede unirse a cualquier reunión de Skype Empresarial. Sin embargo, a partir de octubre de 2022, los usuarios de TeamsOnly en organizaciones híbridas solo podrán unirse a Skype Empresarial reuniones de forma anónima. Para obtener más información, consulte [Qué esperar después de la retirada](/microsoftteams/skype-for-business-online-retirement#what-to-expect-post-retirement).
- Las reuniones ya existentes del usuario programadas para el futuro se migrarán del entorno local a Teams.
- Los contactos que existían en el entorno local están disponibles en Teams poco después de que el usuario inicie sesión por primera vez.
- Los usuarios no pueden iniciar llamadas ni chats desde Skype Empresarial, ni tampoco pueden programar nuevas reuniones en Skype Empresarial. Si intentan abrir el cliente Skype Empresarial, se les redirigirá para que usen Teams, como se muestra a continuación. Si el cliente de Teams no está instalado, se le dirigirá a la versión web de Teams mediante su explorador.<br><br>
    ![Mensaje que redirige a un usuario a Teams.](../media/go-to-teams-page.png)

Antes de mover los usuarios, asegúrese de revisar los [requisitos previos](move-users-between-on-premises-and-cloud.md#prerequisites) para mover usuarios a la nube. Además, asegúrese de revisar las [instrucciones de migración e interoperabilidad para las organizaciones que usan Teams junto con Skype Empresarial](/microsoftteams/migration-interop-guidance-for-teams-with-skype).


> [!NOTE]
> El Almacén de contactos unificado debe deshabilitarse en la cuenta sfB local para que el contacto se mueva a Teams.

> [!IMPORTANT]
>
> - Al mover un usuario del entorno local a la nube con Move-CsUser, se asigna automáticamente el modo TeamsOnly a los usuarios y sus reuniones desde el entorno local se convierten automáticamente en reuniones de Teams, independientemente de si realmente se especifica el `-MoveToTeams` modificador. (Esto incluye las migraciones de Lync Server 2013, que nunca tuvieron el `-MoveToTeams` modificador).  Anteriormente, si no se especificaba este modificador, los usuarios pasaron de estar hospedados en Skype Empresarial Server local a Skype Empresarial En línea y su modo permaneció sin cambios. Esto cambió como preparación para la retirada de Skype Empresarial Online.
> - Mover usuarios entre la implementación local y Teams ahora *requiere* versiones mínimas actualizadas de los componentes locales Skype Empresarial Server o Lync Server que ya no se basan en la infraestructura heredada de Skype Empresarial Online. Para obtener más información, consulte [Requisitos previos](move-users-between-on-premises-and-cloud.md#prerequisites).

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a>Mover un usuario directamente de Skype Empresarial local a Solo Teams

Las herramientas de administración local de Skype Empresarial Server y Lync Server 2013 permiten mover usuarios del entorno local al modo TeamsOnly en un solo paso mediante el cmdlet Move-CsUser de PowerShell o el Skype Empresarial Server Panel de control, como se describe a continuación. Ya no es necesario especificar el `-MoveToTeams` modificador y el comportamiento para moverse directamente desde el entorno local a Solo Teams ahora es automático, independientemente de la versión de Skype Empresarial Server o Lync Server. 

Debe tener privilegios suficientes tanto en el entorno local como en el servicio en la nube (Microsoft 365 o Office 365), como se describe en [Credenciales administrativas necesarias](move-users-between-on-premises-and-cloud.md#required-administrative-credentials). Puede usar una sola cuenta que tenga privilegios en ambos entornos, o bien puede iniciar una ventana local Skype Empresarial Server Shell de administración con credenciales locales y usar el `-Credential` parámetro para especificar las credenciales de un microsoft 365 con el rol administrativo necesario.

Además, debe asegurarse de que al usuario se le ha concedido una licencia para Teams (además de Skype Empresarial En línea). No deshabilite la licencia de Skype Empresarial Online.

### <a name="move-to-teams-using-move-csuser"></a>Mover a Teams con Move-CsUser

Move-CsUser está disponible desde una ventana de PowerShell del Shell de administración de Skype Empresarial Server local o desde una ventana de PowerShell del Shell de administración de Lync Server. Para mover un usuario al modo TeamsOnly mediante Move-CsUser:
- Especifique el usuario que se va a mover mediante el `Identity` parámetro .
- Especifique el `-Target` parámetro con el valor "sipfed.online.lync.<span> com" (o un valor similar si el inquilino es la nube gubernamental).
- Si no tiene una cuenta con permisos suficientes tanto en el entorno local como en el servicio en la nube (Microsoft 365), use el `-credential` parámetro para proporcionar a una cuenta permisos suficientes en Microsoft 365.
- Si la cuenta con permisos en Microsoft 365 no termina en "onmicrosoft.<span> com", debe especificar el `-HostedMigrationOverrideUrl` parámetro , con el valor correcto como se describe en [Credenciales administrativas necesarias](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).
- Asegúrese de que el equipo que ejecuta las herramientas de administración local usa la cu más reciente para la versión de Skype Empresarial Server o Lync Server 2013, para asegurarse de que se usa OAuth para la autenticación. 

La siguiente secuencia de cmdlets se puede usar para mover un usuario a TeamsOnly y supone que la credencial de Microsoft 365 es una cuenta independiente y se proporciona como entrada para la solicitud de Get-Credential. El comportamiento es el mismo si `-MoveToTeams` se especifica switch o no.

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
  ```

> [!TIP]
> Dado que hay circunstancias diferentes que requieren parámetros diferentes, el comando predeterminado para la mayoría de los casos es:

```powershell
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -HostedMigrationOverrideUrl $url
```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a>Mover a Teams con Skype Empresarial Server Panel de control

1. Abra la aplicación Skype Empresarial Server Panel de control.
2. En el panel de navegación izquierdo, elija **Usuarios**.
3. Use **Find** para buscar los usuarios que desea mover a Teams.
4. Seleccione los usuarios y, a continuación, en la lista desplegable **Acción** encima de la lista, elija **Mueve los usuarios seleccionados a Teams** o **Mover usuarios seleccionados a Skype Empresarial Online**.   Cualquiera de las opciones ahora mueve a los usuarios directamente a TeamsOnly.
5. En el asistente, haga clic en **Siguiente**.
6. Si se le solicita, inicie sesión en Microsoft 365 con una cuenta que termine en .onmicrosoft.com y tenga permisos suficientes.
7. Haga clic en **Siguiente** y, a continuación, **Next** una vez más para mover el usuario.
8. Los mensajes de estado relacionados con el éxito o el error se proporcionan en la parte superior de la aplicación de Panel de control principal, no en el asistente.
    
    
## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a>Notificar a los usuarios locales de Skype Empresarial del próximo traslado a Teams

Las herramientas de administración local de Skype Empresarial Server 2015 con CU8 y, en Skype Empresarial Server 2019, le permiten notificar a los usuarios locales Skype Empresarial su próximo traslado a Teams. Al habilitar estas notificaciones, los usuarios verán una notificación en su cliente de Skype Empresarial (Win32, Mac, web y móvil), como se muestra a continuación. Si los usuarios hacen clic en el botón **Probar** , se iniciará el cliente de Teams si está instalado; De lo contrario, los usuarios se navegarán a la versión web de Teams en su explorador. De forma predeterminada, cuando se habilitan las notificaciones, Win32 Skype Empresarial clientes descargan silenciosamente el cliente de Teams para que el cliente enriquecido esté disponible antes de mover el usuario al modo TeamsOnly. Sin embargo, también puede deshabilitar este comportamiento.  Las notificaciones se configuran mediante la versión local de `TeamsUpgradePolicy`y la descarga silenciosa para los clientes Win32 se controla mediante el cmdlet local `TeamsUpgradeConfiguration` .


![Notificación del próximo traslado a Teams.](../media/teams-upgrade-notification.png)

Para notificar a los usuarios locales que pronto se actualizarán a Teams, cree una nueva instancia de TeamsUpgradePolicy con NotifySfBUsers=true. A continuación, asigne esa directiva a los usuarios a los que desea notificar, ya sea asignando la directiva directamente al usuario o estableciendo la directiva en el sitio, grupo o nivel global. Los siguientes cmdlets crean y conceden una directiva de nivel de usuario:

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

La descarga automática de Teams a través del Skype Empresarial cliente Win32 se controla mediante el cmdlet TeamsUpgradeConfiguration local con el parámetro DownloadTeams. Esta configuración se crea en un nivel global, de sitio y de grupo. Por ejemplo, el siguiente comando crea la configuración para el sitio Redmond1:

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

De forma predeterminada, el valor de DownloadTeams es True; sin embargo, *solo* se respeta si NotifySfbUser = True para un usuario determinado.

## <a name="see-also"></a>Vea también

[Move-CsUser](/powershell/module/skype/move-csuser)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy
)

[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[Coexistencia con Skype Empresarial](/microsoftteams/coexistence-chat-calls-presence)
