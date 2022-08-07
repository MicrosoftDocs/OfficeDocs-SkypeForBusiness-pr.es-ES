---
title: Informe de usuarios bloqueados de Rtc de Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Use el informe Usuarios bloqueados de RTC en el Centro de administración de Microsoft Teams para obtener información general sobre los usuarios de Teams de su organización que no pueden realizar llamadas RTC.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-voice
ms.openlocfilehash: 8f723a9aca6cc57510aaf526297f60966a27bcda
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267385"
---
# <a name="microsoft-teams-pstn-blocked-users-report"></a>Informe de usuarios bloqueados de Rtc de Microsoft Teams

El informe Usuarios bloqueados de RTC del Centro de administración de Microsoft Teams muestra los usuarios de su organización que no pueden realizar llamadas RTC en Teams. Puede ver más información sobre cada usuario bloqueado, incluido su número de teléfono asignado y el motivo por el que se bloquearon las llamadas.

## <a name="view-the-pstn-blocked-users-report"></a>Ver el informe usuarios bloqueados de RTC

En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, haga clic en **Análisis & informes** > **de uso**. En la pestaña **Ver informes** , en **Informe**, seleccione **Usuarios bloqueados de RTC** y, a continuación, haga clic en **Ejecutar informe**.

![Captura de pantalla del informe de usuarios bloqueados de RTC en el centro de administración.](../media/teams-reports-pstn-blocked-users-with-callouts.png "Captura de pantalla del informe usuarios bloqueados de RTC en el Centro de administración de Microsoft Teams con llamadas numeradas")

## <a name="interpret-the-report"></a>Interpretar el informe

|Globo |Descripción  |
|--------|-------------|
|**1**   |Cada informe tiene una fecha en la que se generó. Normalmente, el informe refleja una latencia de 24 a 48 horas desde el momento de actividad. |
|**2**   |El eje X es la fecha. El eje Y es el número de usuarios. <br>Desplace el puntero sobre el punto de una fecha determinada para ver el número de usuarios bloqueados en esa fecha. |
|**3**   |En la tabla se proporciona un desglose de todos los usuarios a los que se bloquea la realización de llamadas RTC.  Muestra todos los usuarios que tienen sistema telefónico o audioconferencia asignados y le proporciona más información sobre cada usuario. <ul><li>**Nombre para** mostrar es el nombre para mostrar del usuario. Puede hacer clic en el nombre para mostrar para ir a la página de configuración del usuario en el Centro de administración de Microsoft Teams. </li> <li>**Teléfono** es el número asignado al usuario.</li> <li>**Motivo de bloqueo** es el motivo por el que se bloquea al usuario para que no pueda realizar llamadas.</li><li>**La acción Bloqueada**  indica si el usuario está bloqueado o desbloqueado para poder realizar llamadas RTC en Teams.</li> <li>**Hora bloqueada** es la fecha y hora (UTC) en la que se bloqueó al usuario para que no realizara llamadas.</li></li> </ul>Para ver la información que quiera en la tabla, asegúrese de agregar las columnas a la tabla. |
|**4**   |Seleccione **Editar columnas** para agregar o quitar columnas en la tabla.|
|**5**   |Seleccione **Pantalla completa** para ver el informe en modo de pantalla completa.|

## <a name="related-topics"></a>Temas relacionados

- [Análisis e informes de Teams](teams-reporting-reference.md)