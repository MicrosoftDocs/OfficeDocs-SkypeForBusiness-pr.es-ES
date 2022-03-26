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
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8becd4a83bb544747fa59a823bae37461c3642c3
ms.sourcegitcommit: d3d3d5a70a69359fc71f072ad6c651556f4eda00
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2022
ms.locfileid: "63783899"
---
# <a name="assisted-upgrades-from-skype-for-business-online-to-microsoft-teams"></a>Actualizaciones asistidos de Skype Empresarial Online a Microsoft Teams

Microsoft se retiró Skype Empresarial Online el 31 de julio de 2021.  Microsoft proporciona un proceso de actualización asistido para ayudar a las organizaciones a Skype Empresarial usuarios en línea restantes a Teams solo.  Las actualizaciones asistidos por Microsoft reducen el número de tareas técnicas y simplifican la transición a un mundo sin Skype Empresarial Online si su organización es:
 - Una organización en línea pura que necesita actualizar desde *Skype Empresarial Online* para convertirse en Teams solo o
 - Una organización híbrida con usuarios en *Skype Empresarial Online*  y un entorno de Skype Empresarial Server local, que necesita actualizar solo h los usuarios de Skype Empresarial *Online* *a* Teams Solo.

Le recomendamos que revise nuestras instrucciones [de actualización antes](https://aka.ms/SkypeToTeams) de la actualización. Nuestras instrucciones de actualización incluyen actividades recomendadas y recursos útiles para completar una actualización de Skype Empresarial Online a Teams. Esta guía se aplica a cualquier organización que planee una actualización a Teams, ya sea que administren todos los aspectos de la actualización o usen el proceso asistido.

## <a name="the-assisted-upgrade-experience"></a>La experiencia de actualización asistida
Skype Empresarial Los clientes en línea que están programados para las actualizaciones asistidos Teams recibirán varias formas de *notificaciones: Planear* publicaciones de cambio en el Centro de mensajes de Microsoft 365, actualizar notificaciones de panel en el centro de administración de Teams y marcas desde la aplicación a los usuarios finales. La notificación de actualización en el Centro de mensajes y el centro de administración de Teams incluyen la fecha programada de la actualización asistida, así como un vínculo para actualizar recursos y aprendizaje para ayudar a impulsar la adopción y el uso de Teams.

La experiencia de actualización asistida varía ligeramente en función de si su organización tiene usuarios ubicados en un entorno Skype Empresarial Server local:
- **Organizaciones en línea puras** Para las *organizaciones que* no tienen Skype local para usuarios de Busineess Server, `TeamsUpgradeOverridePolicy` el proceso de actualización asistida aplica la directiva a su organización. Cuando se aplique esta directiva, todos los usuarios de Skype Empresarial Online se colocarán en Teams solo.
- **Organizaciones híbridas con usuarios** Skype Empresarial locales Esto incluye organizaciones con cualquier usuario ubicado en Skype Empresarial Server, independientemente de si se ha configurado híbrido. Es posible que estas organizaciones tengan usuarios que se resalten en una de las siguientes categorías:

  - Los usuarios locales se alocuban en Skype Empresarial Server (que pueden o no usar Teams, pero no solo Teams usuarios)
  - Teams Solo los usuarios que se han alo Skype Empresarial Online
  - No Teams solo los usuarios que se encuentran en Skype Empresarial Online

El proceso de actualización asistido solo afectará a la última categoría de usuarios: no Teams Solo los usuarios que se aloten en Skype Empresarial Online se actualizarán Teams modo solo. Los Skype Empresarial locales y los usuarios existentes de TeamsOnly los usuarios no se verán afectados por el proceso de actualización asistida.

> [!NOTE]
> Su organización puede seguir usando Skype Empresarial Online hasta que se complete la actualización. Si está programado para que una actualización asistido Teams, puede realizar su propia actualización desde Skype Empresarial Online antes de la fecha de actualización programada. Para obtener más información sobre cómo actualizar manualmente a Teams, consulte nuestras instrucciones [de actualización](https://aka.ms/SkypeToTeams).

La duración de la actualización variará según el volumen de usuarios y las características de la implementación. En la mayoría de los casos, los usuarios de un espacio empresarial se actualizarán dentro de las 24 horas siguientes al inicio de la actualización. Durante este tiempo, los usuarios finales seguirán teniendo acceso a Skype Empresarial en línea. Una vez completada la actualización y los usuarios cerrarán sesión en Skype Empresarial Online, empezarán a usar Teams para mensajería, reuniones y llamadas.

## <a name="the-post-upgrade-experience"></a>La experiencia posterior a la actualización

Cuando se complete la actualización asistido, el modo **de coexistencia** para los usuarios actualizados se establece en Teams solo. Le recomendamos que revise las [Teams de modo solo antes](teams-only-mode-considerations.md) de la actualización. La tabla siguiente proporciona una descripción general de alto nivel de la Teams de usuario.

:::row:::
    :::column span="1":::
        **Chat y llamadas**
    :::column-end:::
    :::column span="3":::
        - Todas las llamadas y chats se inician y se reciben en Teams
        - Los usuarios pueden comunicarse (chat o llamada) con cualquier Skype Empresarial usuario
        - Las organizaciones pueden permitir que Teams usuarios se comuniquen con los usuarios del Skype de consumidores mediante la administración de [permisos de acceso externo](manage-external-access.md)
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
        - Contactos existentes desde Skype Empresarial Online, incluidas las federadas (pero sin listas de distribución)
        - Los contactos se migran cuando los usuarios inician sesión Teams por primera vez.
            > [!IMPORTANT]
            >Los contactos deben migrarse dentro de los 90 días posteriores a la finalización de la actualización.
        - Las Skype Empresarial en línea existentes se convierten en Teams reuniones
            > [!IMPORTANT]
            > Los clientes con configuraciones Skype Empresarial Online necesitan usar el Servicio de migración de reuniones (MMS) para migrar las reuniones Skype Empresarial online existentes a Teams reuniones. Se recomienda usar MMS antes de la fecha de actualización asistida. Para obtener más información sobre MMS, vea [Usar el servicio de migración de reuniones (MMS).](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
    :::column-end:::
:::row-end:::

Si tiene una implementación híbrida Skype Empresarial Server y una actualización a Teams, puede mover usuarios entre Skype Empresarial Server y Teams una vez completada la actualización.

## <a name="related-content"></a>Contenido relacionado

- [Introducción a su actualización de Microsoft Teams](upgrade-start-here.md)
- [Retirada de Skype Empresarial Online](skype-for-business-online-retirement.md)
- [Get-CsTeamsUpgradeStatus](/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps&preserve-view=true)
- [Consideraciones del modo Teams solo](teams-only-mode-considerations.md)
