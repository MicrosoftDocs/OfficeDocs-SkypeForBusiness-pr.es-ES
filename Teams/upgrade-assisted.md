---
title: Actualizaciones asistidos | Skype Business Online para Teams actualización
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: billkau
audience: admin
description: Información general sobre las actualizaciones asistidos de Skype Empresarial Online a Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5c9183ffd67455e93f4d22306dbb26a66af65a81b2cc01bc44024ba124f1d671
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54300776"
---
# <a name="assisted-upgrades-from-skype-for-business-online-to-microsoft-teams"></a>Actualizaciones asistidos de Skype Empresarial Online a Microsoft Teams

Microsoft ofrece actualizaciones asistidos a Teams ayudar a las organizaciones a realizar una transición correcta desde Skype Empresarial Online cuando el servicio se retire el 31 de julio de 2021. Tanto si su organización está actualizando desde un entorno *Skype Empresarial Online* o *Skype Empresarial Online* con entorno híbrido (usuarios en Skype Empresarial **Online** y Skype Empresarial Server), las actualizaciones asistidos reducen el número de tareas técnicas que necesita realizar y permiten centrarse más en la preparación de la organización, el conocimiento de los usuarios y el aprendizaje Teams.

Le recomendamos que revise nuestras instrucciones [de actualización antes](https://aka.ms/SkypeToTeams) de la actualización. Nuestras instrucciones de actualización incluyen actividades recomendadas y recursos útiles para completar una actualización de Skype Empresarial Online a Teams. Esta guía se aplica a cualquier organización que planee una actualización a Teams, ya sea que administren todos los aspectos de la actualización o usen el proceso asistido.

> [!NOTE]
> Si está programado para que una actualización asistido Teams, puede realizar su propia actualización desde Skype Empresarial Online antes de la fecha de actualización programada. Para obtener más información sobre cómo actualizar manualmente a Teams, consulte nuestras instrucciones [de actualización.](https://aka.ms/SkypeToTeams)
>
> Las actualizaciones asistidos no están disponibles para implementaciones locales de Skype Empresarial Server.

## <a name="notifications-for-scheduled-customers"></a>Notificaciones para clientes programados

Skype Empresarial Los clientes en línea que están programados para las actualizaciones asistidos Teams recibirán una serie de notificaciones de actualización. Estas notificaciones comenzarán 90 días antes de la fecha de actualización programada. Estas notificaciones se entregarán como publicaciones de *Plan de* cambio en el Centro de mensajes de Microsoft 365, notificaciones de panel de actualización en el centro de administración de Teams y marcas desde la aplicación a los usuarios finales.

Las notificaciones de actualización incluirán la fecha programada de la actualización asistida y se vincularán a recursos de actualización y aprendizaje para ayudar a impulsar la adopción y el uso de Teams.

## <a name="the-assisted-upgrade-experience"></a>La experiencia de actualización asistida

Las actualizaciones asistidos comenzarán en agosto de 2021 con fechas específicas del inquilino compartidas en las notificaciones de programación mencionadas anteriormente.

La experiencia de actualización asistido variará ligeramente dependiendo de si tiene un Skype Empresarial solo en línea o un Skype Empresarial Online con entorno híbrido:

- **Skype Empresarial solo en línea** El proceso de actualización asistida aplicará la `TeamsUpgradeOverridePolicy` directiva a su organización. Cuando se aplique esta directiva, todos los usuarios Skype Empresarial online se colocarán en Teams solo.
- **Skype Empresarial Online con híbrido** Los entornos híbridos pueden tener usuarios que están en una de las siguientes categorías:

  - Los usuarios locales se alocuban en Skype Empresarial Server
  - Skype Empresarial Usuarios en línea que están en Teams modo solo para usuarios
  - Skype Empresarial Usuarios en línea que **no están** en Teams modo Solo para usuarios

  Si tiene una combinación de usuarios en cada una de las categorías enumeradas anteriormente, el proceso de actualización asistida solo cambiará Skype Empresarial los usuarios en línea Teams modo solo si aún no están en ese modo. Los usuarios Skype Empresarial local no se verán afectados por el proceso de actualización asistida.

> [!NOTE]
> No se preocupe si la actualización asistido está programada para una fecha posterior al 31 de julio de 2021. Su organización podrá usar Skype Empresarial Online hasta que se complete la actualización.

La duración de la actualización variará según el volumen de usuarios y las características de la implementación. En la mayoría de los casos, los usuarios de un espacio empresarial se actualizarán dentro de las 24 horas siguientes al inicio de la actualización. Durante este tiempo, los usuarios finales seguirán teniendo acceso a Skype Empresarial en línea. Una vez completada la actualización y los usuarios cerrarán sesión en Skype Empresarial Online, empezarán a usar Teams para mensajería, reuniones y llamadas.

## <a name="the-post-upgrade-experience"></a>La experiencia posterior a la actualización

Cuando se complete la actualización asistido, el modo **de coexistencia** para los usuarios actualizados se establece en Teams solo. Le recomendamos que revise las [Teams de modo solo antes](teams-only-mode-considerations.md) de la actualización. En la tabla siguiente se proporciona información general de alto nivel sobre la Teams solo para el usuario.

:::row:::
    :::column span="1":::
        **Chat y llamadas**
    :::column-end:::
    :::column span="3":::
        - Todas las llamadas y chats se inician y se reciben en Teams
        - Los usuarios pueden comunicarse (chat o llamada) con cualquier Skype Empresarial usuario
        - Las organizaciones pueden permitir que Teams usuarios se comuniquen con los usuarios del Skype de [consumidores](manage-external-access.md) mediante la administración de permisos de acceso externo
        - Teams usuarios que intentan iniciar sesión en Skype Empresarial Online se redirigen a Teams
    :::column-end:::
:::row-end:::
:::row:::
    :::column span="1":::
        **Reuniones**
    :::column-end:::
    :::column span="3":::
        - Los usuarios programan todas las reuniones nuevas en Teams (complemento reemplazado)
    :::column-end:::
:::row-end:::
:::row:::
    :::column span="1":::
        **Datos migrados**
    :::column-end:::
    :::column span="3":::
        - Contactos existentes desde Skype Empresarial Online, incluidos federados (pero sin listas de distribución)
        - Los contactos se migran cuando los usuarios inician sesión Teams por primera vez.
            > [!IMPORTANT]
            >Los contactos deben migrarse dentro de los 90 días posteriores a la finalización de la actualización.
        - Las Skype Empresarial en línea existentes se convierten en Teams reuniones
            > [!IMPORTANT]
            > Los clientes con configuraciones Skype Empresarial Online necesitan usar el Servicio de migración de reuniones (MMS) para migrar las reuniones Skype Empresarial online existentes a Teams reuniones. Se recomienda usar MMS antes de la fecha de actualización asistida. Para obtener más información sobre MMS, vea [Usar el servicio de migración de reuniones (MMS).](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
    :::column-end:::
:::row-end:::

Si tiene una implementación Skype Empresarial Server y una actualización a Teams, puede mover usuarios entre Skype Empresarial Server y Teams una vez completada la actualización.

## <a name="related-content"></a>Contenido relacionado

- [Introducción a su actualización de Microsoft Teams](upgrade-start-here.md)
- [Retirada de Skype Empresarial Online](skype-for-business-online-retirement.md)
- [Get-CsTeamsUpgradeStatus](/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps&preserve-view=true)
- [Consideraciones del modo Teams solo](teams-only-mode-considerations.md)
