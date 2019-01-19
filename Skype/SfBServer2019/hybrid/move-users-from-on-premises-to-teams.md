---
title: Mover usuarios de Skype para Business Server 2019 a los equipos
ms.author: crowe
author: CarolynRowe
manager: serdars--
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: 'Resumen: Obtenga información sobre cómo migrar la configuración de usuario y mover los usuarios a los equipos.'
ms.openlocfilehash: 75af7109de60c3d978914585105e4d2fbaad9302
ms.sourcegitcommit: 716d39077784417c3545a91e501ae26ff56ebdf4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2019
ms.locfileid: "29348916"
---
# <a name="move-users-from-on-premises-to-teams"></a>Mover usuarios de local a los equipos

Cuando un usuario se mueve de local a sólo los equipos, el usuario de Skype para la página principal de Business se mueve de local a en línea y el usuario esté asignado TeamsUpgradePolicy con el modo = TeamsOnly.  Después de que un usuario se mueve de local al modo de TeamsOnly:

- Entrante todas las llamadas y charlas de otros usuarios (si se envió desde Skype para profesionales o equipos), va a abrir en el cliente de los equipos del usuario.
- El usuario podrán interoperar con otros usuarios que usan Skype para la empresa (ya sea en línea o local).
- El usuario podrá comunicarse con los usuarios de organizaciones federadas.
- Nuevas reuniones programadas por ese usuario son las reuniones de los equipos.
- Usuario todavía puede unirse a cualquier Skype para reuniones de negocios.
- Programado para el futuro de reuniones existentes del usuario se van a migrar desde local a Skype para profesionales en línea.
- Los contactos que se encontraba en local que están disponibles en los equipos poco después de que el usuario inicia sesión por primera vez.
- Los usuarios no pueden iniciar llamadas o conversaciones de Skype para la empresa, ni tampoco pueden programar las reuniones nuevas en Skype para la empresa. Si intentan abrir el Skype para clientes empresariales, se redirigirán para usar los equipos tal y como se muestra a continuación. Si no está instalado el cliente de los equipos, se dirigirá a la versión de web de los equipos mediante su explorador.<br><br>
    ![Redirigir a un usuario a los equipos de mensaje](../media/go-to-teams-page.png)

Antes de mover los usuarios, asegúrese de revisar los [requisitos previos](move-users-between-on-premises-and-cloud.md#prerequisites) para mover los usuarios a la nube. Asimismo, asegúrese de revisar [migración e instrucciones de interoperabilidad para las organizaciones que utilizan los equipos junto con Skype para la empresa](/microsoftteams/migration-interop-guidance-for-teams-with-skype).

Existen dos métodos para mover un usuario desde local a los equipos:

- Si usa una versión anterior a Skype para Business Server 2015 CU8, el movimiento requiere dos pasos (que se pueden crear scripts para que se realice conjuntamente como un solo paso, si así lo desea):
  - [Mover el usuario de Skype para Business Server (local) para Skype para profesionales en línea](move-users-from-on-premises-to-skype-for-business-online.md).
  - Una vez que el usuario está hospedado en Skype para negocios en línea, asigne al usuario TeamsUpgradePolicy con el modo = TeamsOnly. Para conceder el modo TeamsOnly, ejecute el siguiente cmdlet desde un Skype para la ventana de PowerShell en línea de negocio:`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`
- Si dispone de herramientas de administración de Skype para Business Server 2015 CU8 o posterior, puede usar el método anterior, o puede hacer este cambio en un solo paso tal y como se describe a continuación. Además, puede proporcionar opcionalmente una notificación dentro de la Skype para cliente de negocio antes de moverlos a sólo los equipos, así como tener, opcionalmente, el cliente de los equipos que se descarga en modo silencioso por la Skype para clientes empresariales.

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a>Mover un usuario directamente de Skype para la empresa local a sólo los equipos

Las herramientas de administración local en Skype para Business Server 2015 con CU8, así como en Skype para 2019 de servidor empresarial, le permiten mover los usuarios desde local al modo de sólo los equipos en un solo paso mediante el cmdlet Move-CsUser en PowerShell o el Skype para empresarial Se servidor de Panel de Control, tal y como se describe a continuación.

### <a name="move-to-teams-using-move-csuser"></a>Mover a los equipos con Move-CsUser

Move-CsUser está disponible desde un Skype local para la ventana de PowerShell de Shell de administración de negocio. Los pasos descritos a continuación y los permisos necesarios son los mismos que mover un usuario a Skype para en línea de negocio, excepto que también debe especificar el modificador MoveToTeams y debe asegurarse de que el usuario también ha concedido una licencia para los equipos (además de Skype para la empresa En línea).

Debe tener privilegios suficientes en el entorno local y el inquilino de Office 365, tal como se describe en [requiere credenciales administrativas](move-users-between-on-premises-and-cloud.md#required-administrative-credentials). Puede usar una única cuenta que tiene privilegios en ambos entornos, o puede iniciar un Skype local para la ventana de Shell de administración de servidor empresarial con credenciales locales y usar la `-Credential` parámetro para especificar las credenciales para una Office 365 cuenta con la función administrativa de Office 365 es necesaria.

Para mover un usuario a modo de equipos sólo con Move-CsUser:

- Especificar el usuario para mover mediante el `Identity` parámetro.
- Especifique el destino parámetro - con el valor "sipfed.online.lync. <span>com ".
- Especificar el `MoveToTeams` cambiar.
- Si no tiene una cuenta con permisos suficientes en ambos en local y Office 365, use la `-credential` parámetro para proporcionar una cuenta con permisos suficientes en Office 365.
- Si la cuenta con permisos en Office 365 no termina en "on.microsoft. <span>com ", debe especificar el `-HostedMigrationOverrideUrl` parámetro, con el valor correcto como se describe en [requiere credenciales administrativas](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).

La siguiente secuencia de cmdlet puede usarse para mover un usuario a TeamsOnly y se da por supuesto la credencial de Office 365 es una cuenta independiente y se proporciona como entrada para el símbolo del sistema de Get-Credential.

    ```
    $cred=Get-Credential
    $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -Credential $cred -HostedMigrationOverrideUrl $url
    ```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a>Mover a los equipos con Skype para el Panel de Control de servidor empresarial

1. Abra el Skype para el Control de servidor empresarial aplicación de Panel.
2. En el panel de navegación izquierdo, elija **usuarios**.
3. Use **Buscar** para buscar el usuario o usuarios que le gustaría mover a los equipos.
4. Seleccione los usuarios y, a continuación, en la lista desplegable **acción** encima de la lista, elija **mover usuarios seleccionados a los equipos**.
5. En el asistente, haga clic en **siguiente**.
6. Si se le solicita, inicie sesión en Office 365, con una cuenta que termina en. onmicrosoft.com y tiene permisos suficientes.
7. Haga clic en **siguiente**y, a continuación, **siguiente** una vez más para mover el usuario.
8. Tenga en cuenta que los mensajes de estado sobre el éxito o el fracaso se proporcionan en la parte superior de la aplicación de Panel de Control principal, no en el asistente.

## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a>Notificar a su Skype local para usuarios de empresas del movimiento próximo a los equipos

Las herramientas de administración local en Skype para Business Server 2015 con CU8, así como en Skype para Business Server 2019, permiten notificar Skype local para los usuarios empresariales de su traspaso próxima a los equipos. Al habilitar estas notificaciones, los usuarios verán una notificación en su Skype para Business client (Win32, Mac, web y móviles) tal y como se muestra a continuación. Si los usuarios, haga clic en el botón **probar** , el cliente de los equipos se iniciará si está instalado; de lo contrario, los usuarios se desplazará a la versión de web de los equipos en su explorador. De forma predeterminada, cuando se habilitan las notificaciones, Win32 Skype para clientes empresariales en modo silencioso descargar el cliente de los equipos para que el cliente enriquecido de esté disponible antes de mover el usuario a los equipos sólo modo; Sin embargo, también puede deshabilitar este comportamiento.  Las notificaciones están configuradas con la versión local de `TeamsUpgradePolicy`, y descarga silenciosa para los clientes de Win32 se controla mediante el local `TeamsUpgradeConfiguration` cmdlet.

![Notificación de movimiento próxima a los equipos](../media/teams-upgrade-notification.png)

Para notificar a los usuarios locales que se va a ser actualizado pronto a los equipos, crear una nueva instancia de TeamsUpgradePolicy con NotifySfBUsers = true. A continuación, asignar esa directiva a los usuarios que desea notificar, mediante la asignación de la directiva de directamente al usuario o mediante la configuración de la directiva en el nivel global, el grupo de servidores o el sitio. Los cmdlets siguientes crear y conceder una directiva de nivel de usuario:

```
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

La descarga automática de los equipos a través de la Skype para cliente de Win32 de negocio se controla mediante el cmdlet de TeamsUpgradeConfiguration local con el parámetro DownloadTeams. Crear esta configuración en un global, el sitio y el nivel de grupo de servidores. Por ejemplo, el siguiente comando crea la configuración para el sitio Redmond1:

`New-CsTeamsUpgradeConfiguration -Identity “site:redmond1”`

De forma predeterminada, el valor de DownloadTeams es True; Sin embargo, *solo* garantizada si está NotifySfbUser = True para un usuario determinado.

## <a name="see-also"></a>Vea también

[Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)

[GRANT CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsupgradepolicy
)

[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[Coexistencia con Skype Empresarial](/microsoftteams/coexistence-chat-calls-presence)
