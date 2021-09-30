---
title: Usar telemetría en tiempo real para solucionar problemas de mala calidad de la reunión
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, vkorlep
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
- Reporting
description: Use telemetría en tiempo real con detalles sobre dispositivos, redes y conectividad para solucionar problemas de usuario con Microsoft Teams reuniones programadas.
ms.openlocfilehash: c33e3309995d82fd16e9eb1deb2fa5fe24b04330
ms.sourcegitcommit: 5eb5acd7910724f7f4a598ecc28b003e5bbe5ea5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "60007923"
---
# <a name="use-real-time-telemetry-to-troubleshoot-poor-meeting-quality"></a>Usar telemetría en tiempo real para solucionar problemas de mala calidad de la reunión

> [!NOTE]
> Esta característica se encuentra actualmente en versión preliminar pública.

En este artículo se explica cómo usar telemetría en tiempo real para solucionar problemas de Microsoft Teams calidad de reunión para usuarios individuales. Puede ver telemetría en tiempo real si tiene uno de los siguientes roles:

- Administrador de Teams
- Teams Especialista en soporte técnico de comunicaciones
- Ingeniero de soporte en comunicaciones de Teams

Para obtener más información sobre Teams de administrador, vea Usar Microsoft Teams [de administrador para administrar Teams](/MicrosoftTeams/using-admin-roles).

La telemetría en tiempo real permite a los administradores de TI ver las reuniones programadas de sus usuarios importantes y ver audio, vídeo, uso compartido de contenido y problemas relacionados con la red. Como administrador, puede usar telemetría para investigar estos problemas durante las reuniones y solucionar problemas en tiempo real.

## <a name="what-is-real-time-telemetry"></a>¿Qué es telemetría en tiempo real?

Hoy en día, la solución de problemas de reunión individual está disponible para Teams a través del [análisis](use-call-analytics-to-troubleshoot-poor-call-quality.md) de llamadas después de que finalice la reunión. La telemetría en tiempo real permite a los administradores solucionar problemas de reuniones programadas mientras están en curso.

Telemetría en tiempo real muestra información detallada sobre Teams reuniones para cada usuario de su cuenta de Office 365 actualizada en tiempo real. Incluye información sobre los dispositivos, la red, la conectividad, el audio, el vídeo y los problemas de uso compartido de contenido, lo que ayudará a los administradores a solucionar problemas de calidad de llamadas de forma más eficaz.

Como administrador Teams, obtiene acceso completo a todos los datos de telemetría en tiempo real para cada usuario. Además, puede asignar roles Azure Active Directory al personal de soporte técnico. Para obtener más información sobre estos roles, vea Conceder permiso al personal [de soporte técnico y de soporte técnico.](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff)

## <a name="where-to-find-per-user-real-time-troubleshooting-telemetry"></a>Dónde buscar telemetría de solución de problemas en tiempo real por usuario

Para ver toda la información de la reunión y los datos de un usuario, vaya al [centro de Teams de administración.](https://admin.teams.microsoft.com) En **Usuarios**  >  **Administrar usuarios,** seleccione un usuario y abra la pestaña Reuniones **& llamadas** en la página de perfil del usuario. En **Reuniones recientes,** verá una lista de reuniones a las que ha asistido el usuario en las últimas 24 horas para las que la telemetría en tiempo *real* está disponible, incluidas las reuniones en curso. Si la reunión no está en curso o no tiene datos de telemetría en tiempo real, se mostrará en **Reuniones anteriores.**

![Captura de pantalla de la tabla reuniones recientes.](media/recent-meetings.png)

Para obtener información adicional sobre los participantes de una reunión que está en curso, incluidas  sus estadísticas de dispositivo, red y audio, busque la reunión en Reuniones recientes y seleccione el vínculo debajo de la columna **Participantes.**

![Captura de pantalla de la tabla de detalles del participante.](media/participant-details.png)

Para ver la telemetría en tiempo real de un usuario determinado para una reunión en curso, incluida la información sobre el dispositivo, la red, el audio, el vídeo y los detalles de uso compartido de contenido, seleccione el Id. de **reunión.**

![Captura de pantalla de los datos de sesión de usuario de análisis de llamadas.](media/real-time-telemetry.png)

## <a name="platforms-supported-for-real-time-telemetry"></a>Plataformas compatibles con telemetría en tiempo real

- Windows
- macOS
- Linux
- Android
- iOS

## <a name="teams-devices-support-with-real-time-telemetry"></a>Teams dispositivos compatibles con telemetría en tiempo real

- MTR: Surface Hub
- MTR: Teams pantalla
- MTR: barra de colaboración
- Dispositivos Teléfono IP

## <a name="limitations"></a>Limitaciones

- La telemetría en tiempo real solo está disponible para las reuniones programadas. Para reuniones ad hoc como Reunirse ahora, RTC, llamadas 1:1 y llamadas grupales, la telemetría en tiempo real no funcionará.
- La telemetría en tiempo real solo está disponible para los presentadores de eventos en directo programados. Actualmente no está disponible para los asistentes al evento en directo.
- Los datos de telemetría en tiempo real están disponibles para una reunión en Reuniones **recientes** durante 24 horas después de que haya finalizado la reunión. Después de 24 horas, no podrá acceder a los datos y la reunión se moverá a **Reuniones anteriores.** Si una reunión dura más de 3 horas, la telemetría en tiempo real solo estará disponible durante las *últimas 3 horas.*
- La telemetría no funciona con versiones anteriores de Teams. Si no hay telemetría disponible, intente actualizar el cliente.
- Si participantes externos o usuarios anónimos se unen a una reunión, su nombre para mostrar se mostrará como no disponible **para** conservar la privacidad entre inquilinos.

## <a name="related-topics"></a>Temas relacionados

[Configurar análisis de llamadas por usuario](set-up-call-analytics.md)

[Use Microsoft Teams de administrador para administrar Teams](/MicrosoftTeams/using-admin-roles).
