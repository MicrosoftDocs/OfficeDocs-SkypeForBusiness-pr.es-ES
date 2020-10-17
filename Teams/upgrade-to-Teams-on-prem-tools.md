---
title: Actualizar a teams desde una implementación local de Skype empresarial-Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 'Actualizar de Skype empresarial a teams: herramientas para la actualización'
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
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a>Herramientas para actualizar a teams &mdash; para administradores de ti

En este artículo se describen las herramientas para actualizar a teams. Este artículo es el tercero de varios que describen los conceptos de actualización y la implementación para administradores de ti.  

- [Información general](upgrade-to-teams-on-prem-overview.md)
- [Métodos de actualización](upgrade-to-teams-on-prem-upgrade-methods.md)
- **Herramientas para administrar la actualización**   (este artículo)
- [Consideraciones adicionales para las organizaciones con Skype empresarial local](upgrade-to-teams-on-prem-considerations.md)
- [Implementar la actualización](upgrade-to-teams-on-prem-implement.md)
- [Consideraciones sobre la red telefónica pública conmutada (RTC)](upgrade-to-teams-on-prem-pstn-considerations.md)

Además, los artículos siguientes describen los conceptos de actualización importantes y los comportamientos de coexistencia:

- [Coexistencia de Teams y Skype empresarial](upgrade-to-teams-on-prem-coexistence.md)
- [Modos de coexistencia: referencia](migration-interop-guidance-for-teams-with-skype.md)
- [Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia](teams-client-experience-and-conformance-to-coexistence-modes.md)


## <a name="tools-for-managing-the-upgrade"></a>Herramientas para administrar la actualización

Independientemente del método de actualización que elija, para los usuarios que ya tienen Skype empresarial online, puede administrar la transición a TeamsOnly con [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), que controla el modo de coexistencia de un usuario. Para los usuarios con una cuenta local en Skype empresarial Server, también puede usarlos `Move-CsUser` para [moverlos a la nube](https://docs.microsoft.com/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud).  Para obtener más información sobre cada uno de los modos, vea [modos de coexistencia](migration-interop-guidance-for-teams-with-skype.md).  

Tanto si realiza una transición de funciones seleccionadas con los modos de Skype empresarial o simplemente si actualiza el modo TeamsOnly desde la configuración de islas predeterminadas, TeamsUpgradePolicy es la principal herramienta para los usuarios que ya tienen Skype empresarial online. Como cualquier otra directiva de Teams, puede asignar TeamsUpgradePolicy directamente a un usuario. También puede establecer la Directiva como el valor predeterminado para todo el inquilino. Cualquier asignación a un usuario tiene prioridad sobre la configuración predeterminada de inquilino.  Puede administrar la Directiva en la consola de administración de Teams y en PowerShell.

También puede asignar cualquier modo de TeamsUpgradePolicy, excepto el modo TeamsOnly, a los usuarios alojados en Skype empresarial local. **El modo TeamsOnly solo se puede asignar a un usuario que ya está alojado en Skype empresarial online**. Esto se debe a que la interoperabilidad con usuarios y Federación de Skype empresarial, así como con la funcionalidad del sistema telefónico de Microsoft 365 solo es posible si el usuario se ha alojado en Skype empresarial online. Además, **no puede asignar el modo de TeamsOnly como predeterminado para todo el inquilino si tiene una implementación local de Skype empresarial** (que es detectada por presencia de un registro DNS de lyncdiscover que apunta a una ubicación distinta de Office 365.

Los usuarios con cuentas de Skype empresarial domésticas locales [deben moverse por Internet](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) (ya sea a Skype empresarial online o directamente a teams) mediante Move-CsUser en el conjunto de herramientas local de Skype empresarial. Estos usuarios se pueden mover a TeamsOnly en 1 o 2 pasos:

-   1 paso: especificar el modificador-MoveToTeams en Move-CsUser. Para ello, necesita Skype empresarial Server 2019 o Skype empresarial Server 2015 con CU8 o posterior.

-   2 pasos: después de ejecutar Move-CsUser, conceda el modo TeamsOnly al usuario mediante TeamsUpgradePolicy.

A diferencia de otras directivas, no es posible crear nuevas instancias de TeamsUpgradePolicy en Microsoft 365 u Office 365. Todas las instancias existentes están integradas en el servicio.  (Tenga en cuenta que el modo es una propiedad dentro de TeamsUpgradePolicy, en lugar del nombre de una instancia de directiva). En algunos, pero no en todos los casos, el nombre de la instancia de directiva es el mismo que el modo. En concreto, para asignar el modo de TeamsOnly a un usuario, conceda la instancia "UpgradeToTeams" de TeamsUpgradePolicy a ese usuario. Para ver una lista de todas las instancias, puede ejecutar el siguiente comando:

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

Para actualizar un usuario en línea al modo TeamsOnly, asigne la instancia "UpgradeToTeams": 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

Para actualizar un usuario local de Skype empresarial al modo TeamsOnly, use Move-CsUser en el conjunto de herramientas local:

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
```

Para cambiar el modo para todos los usuarios del espacio empresarial, excepto aquellos que tienen una concesión de conceder por usuario explícita (que tiene prioridad), ejecute el siguiente comando:

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
>Si tiene usuarios con cuentas de Skype empresarial en local, no puede asignar el modo TeamsOnly en el nivel de espacio empresarial. Debe mover estos usuarios de forma individual a la nube mediante Move-CsUser.


## <a name="using-notifications-in-skype-for-business-clients"></a>Uso de notificaciones en clientes de Skype empresarial

Los administradores tienen la opción de proporcionar notificaciones de usuario final en el cliente de Skype empresarial para informar a los usuarios de que pronto se actualizarán a Teams, tal y como se muestra en el siguiente diagrama. Por ejemplo, una semana antes de que el administrador planea actualizar un grupo de usuarios al modo TeamsOnly, es posible que el administrador desee activar estas notificaciones para ese grupo de usuarios. Estas notificaciones se habilitan mediante una instancia de TeamsUpgradePolicy con NotifySfbUsers = true.  Para todos los modos distintos de TeamsOnly, en realidad existen dos instancias por modo, que corresponden a los dos valores de NotifySfbUsers.  Para todos los modos distintos de TeamsOnly, en realidad existen dos instancias por modo, que corresponden a los dos valores de NotifySfbUsers. 

![Diagrama que muestra las notificaciones](media/teams-upgrade-sfb-with-notifications.png)

Si los usuarios están alojados en Skype empresarial online, simplemente asigne la instancia de directiva que tiene el mismo modo que el usuario, pero con NotifySfbUsers = true. 

Si los usuarios están alojados en Skype empresarial Server local, tendrá que usar el conjunto de herramientas local y necesitará Skype empresarial Server 2019 o CU8 para Skype empresarial Server 2015... Para los usuarios alojados en Skype empresarial Server local, se admite la propiedad Mode de la instancia de TeamsUpgradePolicy, pero no la propiedad NotifySfbUsers. Si deseas recibir notificaciones, deberás crear una instancia local de TeamsUpgradePolicy para controlar el comportamiento de los clientes. 

En la ventana de PowerShell local, cree una nueva instancia de TeamsUpgradePolicy con NotifySfbUsers = true:

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

Después, con la misma ventana de PowerShell local, asigne esa nueva Directiva a los usuarios que desee:

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a>Migración de reuniones

Cuando se migra un usuario al modo TeamsOnly, las reuniones de Skype empresarial existentes que organizó se convertirán en Teams de forma predeterminada. Si lo desea, puede deshabilitar el comportamiento predeterminado al asignar el modo de TeamsOnly a un usuario. Al mover usuarios de forma local, las reuniones se deben migrar a la nube para que funcione con la cuenta de usuario en línea, pero si no especifica-MoveToTeams, las reuniones se migrarán como reuniones de Skype empresarial, en lugar de convertirlas a teams. 

Al asignar el modo de TeamsOnly en el nivel de espacio empresarial, la migración de reuniones no se desencadena para ningún usuario. Si desea asignar el modo de TeamsOnly en el nivel de inquilino y migrar reuniones, puede usar PowerShell para obtener una lista de los usuarios en el inquilino (por ejemplo, usando Get-CsOnlineUser con los filtros que sean necesarios) y, a continuación, recorra cada uno de estos usuarios para desencadenar la migración de reuniones con Start-CsExMeetingMigration. Para obtener más información, vea [usar el servicio de migración de reuniones (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).



## <a name="related-links"></a>Vínculos relacionados

[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](migration-interop-guidance-for-teams-with-skype.md) 

[Configurar la conectividad híbrida entre Skype empresarial Server y Microsoft 365 u Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover usuarios entre la implementación local y la nube](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configurar su coexistencia y la configuración de actualización](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Usar el servicio de migración de reuniones (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

