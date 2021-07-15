---
title: Herramientas para actualizar a Teams desde una Skype Empresarial implementación local
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Herramientas para actualizar de Skype Empresarial a Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 677f642bdb940706079370635a5aa9eec87241fb
ms.sourcegitcommit: e19fdedca6573110d08c7d114e05b84779e36b58
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2021
ms.locfileid: "53437637"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a>Herramientas para actualizar a Teams &mdash; para administradores de TI

En este artículo se describen las herramientas para actualizar a Teams desde Skype Empresarial. 

Antes de comenzar la actualización, Microsoft recomienda los siguientes artículos que describen conceptos de actualización importantes y comportamientos de coexistencia:

- [Coexistencia de Teams y Skype Empresarial](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Modos de coexistencia: referencia](migration-interop-guidance-for-teams-with-skype.md)
- [Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="tools-for-managing-the-upgrade"></a>Herramientas para administrar la actualización

Independientemente del método de actualización que elija, para los usuarios que ya tienen Skype Empresarial Online, administra la transición a TeamsOnly con [TeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), que controla el modo de coexistencia de un usuario. Para los usuarios con una cuenta local en Skype Empresarial Server, también se usan `Move-CsUser` para [moverlos a la nube.](/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud)  Para obtener más información sobre cada uno de los modos, vea [Modos de coexistencia.](migration-interop-guidance-for-teams-with-skype.md)

> [!NOTE]
> Si actualmente usa Skype Empresarial Online Connector para administrar sus servicios, tendrá que pasar al módulo de PowerShell de Teams y actualizar los scripts de PowerShell existentes. Vea [Mover de Skype Empresarial Online Connector al módulo Teams PowerShell para](teams-powershell-move-from-sfbo.md) obtener más información.

Tanto si realiza una transición de capacidades de selección con Skype Empresarial o simplemente actualiza al modo TeamsOnly desde la configuración predeterminada de Islas, TeamsUpgradePolicy es la herramienta principal. Como cualquier otra directiva de Teams, puede asignar TeamsUpgradePolicy directamente a un usuario. También puede establecer la directiva como predeterminada para todo el espacio empresarial. Cualquier asignación a un usuario tiene prioridad sobre la configuración predeterminada del inquilino.  Puede administrar la directiva en la Teams de administración y en PowerShell.

Puede asignar cualquier modo de TeamsUpgradePolicy, excepto el modo TeamsOnly, a los usuarios que Skype Empresarial local. Por el contrario, a los usuarios que se aloen en la nube solo se les puede asignar el modo TeamsOnly. El modo **TeamsOnly** solo se puede asignar a un usuario que ya está instalado en la nube porque la interoperabilidad y la federación con usuarios de Skype Empresarial así como la funcionalidad de Microsoft 365 Sistema telefónico solo son posibles si el usuario se encuentra en Skype Empresarial Online.  Además, no puede asignar el modo **TeamsOnly** como predeterminado para todo el espacio empresarial si tiene una implementación local de Skype Empresarial (que se detecta por la presencia de un registro DNS de detección de lync que apunta a una ubicación que no Office 365. Para obtener más información, vea [Deshabilitar la configuración híbrida para completar](/SkypeForBusiness/hybrid/cloud-consolidation-disabling-hybrid)la migración a Teams solo .

Los usuarios con Skype Empresarial cuentas locales [](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) deben moverse en línea al modo solo Teams mediante Move-CsUser en el conjunto de herramientas Skype Empresarial local. 

A diferencia de otras directivas, no es posible crear nuevas instancias de TeamsUpgradePolicy en Microsoft 365 o Office 365. Todas las instancias existentes están integradas en el servicio.  (Tenga en cuenta que el modo es una propiedad dentro de TeamsUpgradePolicy, en lugar del nombre de una instancia de directiva). En algunos casos( pero no todos), el nombre de la instancia de directiva es el mismo que el modo. En particular, para asignar el modo TeamsOnly a un usuario, concederá la instancia "UpgradeToTeams" de TeamsUpgradePolicy a ese usuario. Para ver una lista de todas las instancias, puede ejecutar el siguiente comando:

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

Para actualizar un usuario en línea al modo TeamsOnly, asigne la instancia "UpgradeToTeams": 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

Para actualizar un usuario local Skype Empresarial al modo TeamsOnly, use Move-CsUser en el conjunto de herramientas local:

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -credential $cred
```

Para cambiar el modo de todos los usuarios del espacio empresarial, excepto los que tienen una concesión explícita por usuario (que tiene prioridad), ejecute el comando siguiente:

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
>Si tiene usuarios con cuentas Skype Empresarial locales, no puede asignar el modo TeamsOnly en el nivel de inquilino. Debe mover estos usuarios individualmente al Teams solo con Move-CsUser.


## <a name="using-notifications-in-skype-for-business-clients"></a>Usar notificaciones en Skype Empresarial clientes

Los administradores tienen la opción de proporcionar notificaciones de usuario final en el cliente de Skype Empresarial para informar a los usuarios de que pronto se actualizarán Teams, como se muestra en el siguiente diagrama. Por ejemplo, una semana antes de que el administrador tenga previsto actualizar un grupo de usuarios al modo TeamsOnly, es posible que el administrador quiera activar estas notificaciones para ese grupo de usuarios. Estas notificaciones se habilitan con una instancia de TeamsUpgradePolicy con NotifySfbUsers=true.  Para todos los modos distintos de TeamsOnly, en realidad hay dos instancias por modo, correspondientes a los dos valores de NotifySfbUsers.  Para todos los modos distintos de TeamsOnly, en realidad hay dos instancias por modo, correspondientes a los dos valores de NotifySfbUsers. 

![Diagrama que muestra notificaciones](media/teams-upgrade-sfb-with-notifications.png)

Si los usuarios se encuentran en Skype Empresarial Online, simplemente asigne la instancia de directiva que tenga el mismo modo que el usuario, pero con NotifySfbUsers=true. 

Si los usuarios se encuentran en Skype Empresarial Server local, deberá usar el conjunto de herramientas local y necesitará Skype Empresarial Server 2019 o CU8 para Skype Empresarial Server 2015. Para los usuarios que Skype Empresarial Server local, se respeta la propiedad mode de la instancia en línea de TeamsUpgradePolicy, pero la propiedad NotifySfbUsers no lo es. Si se desean notificaciones, debe crear una instancia local de TeamsUpgradePolicy para controlar el comportamiento del cliente. 

En la ventana local de PowerShell, cree una nueva instancia de TeamsUpgradePolicy con NotifySfbUsers=true:

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

Después, con la misma ventana de PowerShell local, asigne esa nueva directiva a los usuarios deseados:

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a>Migración de reuniones

Cuando un usuario se migra al modo TeamsOnly, de forma predeterminada, las reuniones Skype Empresarial que hayan organizado se convertirán en Teams. Opcionalmente, puede deshabilitar el comportamiento predeterminado al asignar el modo TeamsOnly a un usuario. Al mover usuarios desde locales, las reuniones deben migrarse Skype Empresarial la nube para que funcionen con la cuenta de usuario en línea, pero si no especifica -MoveToTeams, las reuniones se migrarán como reuniones Skype Empresarial, en lugar de convertirse Teams. 

Al asignar el modo TeamsOnly en el nivel de inquilino, la migración de reuniones no se desencadena para ningún usuario. Si desea asignar el modo TeamsOnly en el nivel de inquilino y migrar reuniones, puede usar PowerShell para obtener una lista de usuarios en el espacio empresarial (por ejemplo, usar Get-CsOnlineUser con los filtros necesarios) y, a continuación, recorrer cada uno de estos usuarios para desencadenar la migración de reuniones con Start-CsExMeetingMigration. Para obtener más información, [vea Usar el servicio de migración de reuniones (MMS).](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)



## <a name="related-links"></a>Vínculos relacionados

[Modos de coexistencia: referencia](migration-interop-guidance-for-teams-with-skype.md) 

[Configurar la conectividad híbrida entre Skype Empresarial Server y Microsoft 365 o Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover usuarios entre la implementación local y la nube](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configurar su coexistencia y la configuración de actualización](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Usar el servicio de migración de reuniones (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
