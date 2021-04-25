---
title: Actualizaciones asistidos | Actualización de Skype Empresarial Online a Teams
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
ms.openlocfilehash: 03ea21de9f8cb64b1221044babeeae335a52d8ea
ms.sourcegitcommit: 900f28c4ac12d65ccbd996028205ba183b4afb03
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/24/2021
ms.locfileid: "51995205"
---
# <a name="assisted-upgrades-from-skype-for-business-online-to-microsoft-teams"></a>Actualizaciones asistidos de Skype Empresarial Online a Microsoft Teams

Microsoft ofrece actualizaciones asistidos a Teams para ayudar a las organizaciones a realizar una transición correcta desde Skype Empresarial Online cuando el servicio se retire el 31 de julio de 2021. Las actualizaciones asistidos reducen el número de tareas técnicas que debe realizar y permiten centrarse más en la preparación de la organización, el conocimiento de los usuarios y el aprendizaje de Teams.

Le recomendamos que revise nuestras instrucciones [de actualización antes](https://aka.ms/SkypeToTeams) de la actualización. Nuestras instrucciones de actualización incluyen actividades recomendadas y recursos útiles para completar una actualización de Skype Empresarial Online a Teams. Esta guía se aplica a cualquier organización que planee una actualización a Teams, tanto si administran todos los aspectos de la actualización como si usan el proceso asistido.

> [!NOTE]
> Si está programado para una actualización asistido a Teams, puede realizar su propia actualización desde Skype Empresarial Online antes de la fecha de actualización programada. Para obtener más información sobre cómo actualizar manualmente a Teams, consulte nuestras instrucciones [de actualización.](https://aka.ms/SkypeToTeams)
>
> La actualización asistida no está disponible para implementaciones locales de Skype Empresarial Server.

## <a name="notifications-for-scheduled-customers"></a>Notificaciones para clientes programados

Los clientes de Skype Empresarial Online que estén programados para las actualizaciones asistidos a Teams recibirán una serie de notificaciones de actualización. Estas notificaciones comenzarán 90 días antes de la fecha de actualización programada. Estas notificaciones se entregarán como publicaciones de *Plan de* cambio en el Centro de mensajes de Microsoft 365, notificaciones de panel de actualización en el Centro de administración de Teams y marcas desde la aplicación a los usuarios finales.

Las notificaciones de actualización incluirán la fecha programada de la actualización asistida y se vincularán a recursos de actualización y aprendizaje para ayudar a impulsar la adopción y el uso de Teams.

## <a name="the-assisted-upgrade-experience"></a>La experiencia de actualización asistida

Las actualizaciones asistidos comenzarán en agosto de 2021 con fechas específicas del inquilino compartidas en las notificaciones de programación mencionadas anteriormente.

La duración de la actualización variará según el volumen de usuarios y las características de la implementación. Sin embargo, en la mayoría de los casos, los usuarios de un espacio empresarial se actualizarán dentro de las 24 horas siguientes al inicio de la actualización. Durante este tiempo, los usuarios finales seguirán teniendo acceso a la funcionalidad de Skype Empresarial Online. Una vez completada la actualización y los usuarios cerrarán sesión en Skype Empresarial Online, empezarán a usar Teams para mensajería, reuniones y llamadas.

## <a name="the-post-upgrade-experience"></a>La experiencia posterior a la actualización

Cuando se complete la  actualización asistido, el modo de coexistencia para los usuarios actualizados se establece en Solo Teams y Solo Microsoft puede cambiar a otro modo de coexistencia. Le recomendamos que revise las consideraciones del modo [Solo teams](teams-only-mode-considerations.md) antes de la actualización. La tabla siguiente proporciona una descripción general de alto nivel de la experiencia de usuario solo de Teams.

:::row:::
    :::column span="1":::
        **Chat y llamadas**
    :::column-end:::
    :::column span="3":::
        - Todas las llamadas y chats se inician y reciben en Teams
        - Los usuarios pueden comunicarse (chat o llamada) con cualquier usuario de Skype Empresarial
        - Las organizaciones pueden permitir que los usuarios de Teams se comuniquen con los usuarios del servicio de consumidor de Skype administrando [permisos de acceso externo](manage-external-access.md)
        - Los usuarios de Teams que intenten iniciar sesión en Skype Empresarial Online se redirigirán a Teams
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
        - Contactos existentes de Skype Empresarial Online, incluidas las federadas (pero sin listas de distribución)
        - Las reuniones existentes de Skype Empresarial Online se convierten en reuniones de Teams
    :::column-end:::
:::row-end:::

## <a name="related-content"></a>Contenido relacionado

- [Introducción a su actualización de Microsoft Teams](upgrade-start-here.md)
- [Retirada de Skype Empresarial Online](skype-for-business-online-retirement.md)
- [Get-CsTeamsUpgradeStatus](/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps&preserve-view=true)
- [Consideraciones del modo Teams solo](teams-only-mode-considerations.md)
