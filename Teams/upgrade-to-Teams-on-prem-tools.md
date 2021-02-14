---
title: 'Actualizar a Teams desde una implementación local de Skype Empresarial: Microsoft Teams'
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 'Actualizar de Skype Empresarial a Teams: herramientas para actualizar'
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 952214d615b62d0175841e2c7b24b45f1ae2d2b1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533577"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a>Herramientas para actualizar a Teams para &mdash; administradores de TI

En este artículo se describen las herramientas para actualizar a Teams. Este artículo es el tercero de varios que describen los conceptos de actualización y la implementación para los administradores de TI.  

- [Información general](upgrade-to-teams-on-prem-overview.md)
- [Métodos de actualización](upgrade-to-teams-on-prem-upgrade-methods.md)
- **Herramientas para administrar la actualización**   (este artículo)
- [Consideraciones adicionales para las organizaciones con Skype Empresarial local](upgrade-to-teams-on-prem-considerations.md)
- [Implementar la actualización](upgrade-to-teams-on-prem-implement.md)
- [Consideraciones de la red telefónica conmutada (RTC)](upgrade-to-teams-on-prem-pstn-considerations.md)

Además, en los artículos siguientes se describen conceptos importantes de actualización y comportamientos de coexistencia:

- [Coexistencia de Teams y Skype Empresarial](upgrade-to-teams-on-prem-coexistence.md)
- [Modos de coexistencia - Referencia](migration-interop-guidance-for-teams-with-skype.md)
- [Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia](teams-client-experience-and-conformance-to-coexistence-modes.md)


## <a name="tools-for-managing-the-upgrade"></a>Herramientas para administrar la actualización

Independientemente del método de actualización que elija, para los usuarios que ya tienen Skype Empresarial Online, administre la transición a TeamsOnly con [TeamsUpgradePolicy,](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)que controla el modo de coexistencia de un usuario. Para los usuarios con una cuenta local en Skype Empresarial Server, también puede usarlos para `Move-CsUser` [moverlos a la nube.](https://docs.microsoft.com/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud)  Para obtener más información sobre cada uno de los modos, vea Modos [de coexistencia.](migration-interop-guidance-for-teams-with-skype.md)  

Tanto si realiza la transición de funciones específicas con los modos de Skype Empresarial como si simplemente actualiza al modo TeamsOnly desde la configuración predeterminada de las Islas, TeamsUpgradePolicy es la herramienta principal para los usuarios que ya tienen Skype Empresarial Online. Como cualquier otra directiva de Teams, puede asignar TeamsUpgradePolicy directamente a un usuario. También puede establecer la directiva como predeterminada para todo el inquilino. Cualquier asignación a un usuario tiene prioridad sobre la configuración predeterminada del inquilino.  Puede administrar la directiva en la Consola de administración de Teams y en PowerShell.

También puede asignar cualquier modo de TeamsUpgradePolicy, excepto el modo TeamsOnly, a los usuarios que están en Skype Empresarial local. **El modo TeamsOnly solo puede asignarse a un usuario que ya** esté en Skype Empresarial Online. Esto se debe a que la interoperabilidad con los usuarios y la federación de Skype Empresarial y la funcionalidad del Sistema telefónico de Microsoft 365 solo son posibles si el usuario está en Skype Empresarial Online. Además, no puede asignar el modo **TeamsOnly** como el valor predeterminado de todo el espacio empresarial si tiene una implementación local de Skype Empresarial (que se detecta por la presencia de un registro DNS de lyncdiscover que apunta a una ubicación diferente a Office 365.

Los usuarios con cuentas de Skype Empresarial locales deben moverse en línea [(ya](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) sea a Skype Empresarial Online o directamente a Teams) con Move-CsUser en el conjunto de herramientas local de Skype Empresarial. Estos usuarios se pueden mover a TeamsOnly en uno o dos pasos:

-   1 paso: Especificar el modificador -MoveToTeams en Move-CsUser. Esto requiere Skype Empresarial Server 2019 o Skype Empresarial Server 2015 con CU8 o posterior.

-   2 pasos: Después de ejecutar Move-CsUser, conceda el modo TeamsOnly al usuario mediante TeamsUpgradePolicy.

A diferencia de otras directivas, no es posible crear nuevas instancias de TeamsUpgradePolicy en Microsoft 365 u Office 365. Todas las instancias existentes están integradas en el servicio.  (Tenga en cuenta que el modo es una propiedad dentro de TeamsUpgradePolicy, en lugar del nombre de una instancia de directiva). En algunos casos (aunque no todos), el nombre de la instancia de directiva es el mismo que el modo. En particular, para asignar el modo TeamsOnly a un usuario, concederá la instancia "UpgradeToTeams" de TeamsUpgradePolicy a ese usuario. Para ver una lista de todas las instancias, puede ejecutar el comando siguiente:

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

Para actualizar un usuario en línea al modo TeamsOnly, asigne la instancia "UpgradeToTeams": 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

Para actualizar un usuario local de Skype Empresarial al modo TeamsOnly, use Move-CsUser el conjunto de herramientas local:

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
```

Para cambiar el modo de todos los usuarios del espacio empresarial, excepto los que tienen una concesión explícita por usuario (que tiene prioridad), ejecute el siguiente comando:

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
>Si tiene usuarios con cuentas de Skype Empresarial locales, no puede asignar el modo TeamsOnly en el nivel de inquilino. Debe mover estos usuarios individualmente a la nube mediante Move-CsUser.


## <a name="using-notifications-in-skype-for-business-clients"></a>Usar notificaciones en clientes de Skype Empresarial

Los administradores tienen la opción de proporcionar notificaciones de usuario final en el cliente de Skype Empresarial para informar a los usuarios de que pronto se actualizarán a Teams, tal como se muestra en el siguiente diagrama. Por ejemplo, una semana antes de que el administrador tenga previsto actualizar un grupo de usuarios al modo TeamsOnly, es posible que el administrador quiera activar estas notificaciones para ese grupo de usuarios. Estas notificaciones están habilitadas usando una instancia de TeamsUpgradePolicy con NotifySfbUsers=true.  Para todos los modos distintos de TeamsOnly, realmente hay dos instancias por modo, que corresponde a los dos valores de NotifySfbUsers.  Para todos los modos distintos de TeamsOnly, realmente hay dos instancias por modo, que corresponde a los dos valores de NotifySfbUsers. 

![Diagrama que muestra notificaciones](media/teams-upgrade-sfb-with-notifications.png)

Si los usuarios están en Skype Empresarial Online, simplemente asigne la instancia de directiva que tenga el mismo modo que el usuario, pero con NotifySfbUsers=true. 

Si los usuarios están en Skype Empresarial Server local, necesitará usar el conjunto de herramientas local y necesitará Skype Empresarial Server 2019 o CU8 para Skype Empresarial Server 2015. Para los usuarios que están en Skype Empresarial Server local, se respeta la propiedad mode de la instancia en línea de TeamsUpgradePolicy, pero no la propiedad NotifySfbUsers. Si quiere recibir notificaciones, debe crear una instancia local de TeamsUpgradePolicy para controlar el comportamiento del cliente. 

En la ventana de PowerShell local, cree una nueva instancia de TeamsUpgradePolicy con NotifySfbUsers=true:

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

Después, con la misma ventana de PowerShell local, asigne esa nueva directiva a los usuarios que quiera:

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a>Migración de reuniones

Cuando se migra un usuario al modo TeamsOnly, sus reuniones existentes de Skype Empresarial que han organizado se convierten en Teams de forma predeterminada. Opcionalmente, puede deshabilitar el comportamiento predeterminado al asignar el modo TeamsOnly a un usuario. Al mover usuarios desde local, las reuniones deben migrarse a la nube para que funcionen con la cuenta de usuario en línea, pero si no especifica -MoveToTeams, las reuniones se migrarán como reuniones de Skype Empresarial, en lugar de convertirse a Teams. 

Al asignar el modo TeamsOnly en el nivel de inquilino, no se activa la migración de reuniones para los usuarios. Si desea asignar el modo TeamsOnly en el nivel de inquilino y migrar reuniones, puede usar PowerShell para obtener una lista de usuarios en el inquilino (por ejemplo, usando Get-CsOnlineUser con los filtros que sean necesarios) y, después, recorrer cada uno de estos usuarios para desencadenar la migración de reuniones con Start-CsExMeetingMigration. Para obtener más información, [consulte Usar el servicio de migración de reuniones (MMS).](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)



## <a name="related-links"></a>Vínculos relacionados

[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](migration-interop-guidance-for-teams-with-skype.md) 

[Configurar la conectividad híbrida entre Skype Empresarial Server y Microsoft 365 u Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover usuarios entre la implementación local y la nube](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configurar su coexistencia y la configuración de actualización](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Usar el servicio de migración de reuniones (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

