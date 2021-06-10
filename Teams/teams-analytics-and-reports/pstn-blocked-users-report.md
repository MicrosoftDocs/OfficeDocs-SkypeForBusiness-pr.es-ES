---
title: Microsoft Teams Informe de usuarios bloqueados rtc
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
MS.collection:
- M365-voice
description: Use el informe usuarios bloqueados RTC en el centro de administración de Microsoft Teams para obtener información general sobre los usuarios de Teams de su organización que están bloqueados para realizar llamadas RTC.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ed775c3796e40a775b3be2b78f22e162a047bf78
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809340"
---
# <a name="microsoft-teams-pstn-blocked-users-report"></a>Microsoft Teams Informe de usuarios bloqueados rtc

El informe usuarios bloqueados rtc en el centro de administración de Microsoft Teams muestra los usuarios de su organización que están bloqueados para realizar llamadas RTC en Teams. Puede ver más información sobre cada usuario bloqueado, incluido su número de teléfono asignado y la razón por la que se les bloqueó realizar llamadas.

## <a name="view-the-pstn-blocked-users-report"></a>Ver el informe de usuarios bloqueados de RTC

En el panel de navegación izquierdo del centro Microsoft Teams administración, haga clic **en Análisis & informes de**  >  **uso.** En la pestaña **Ver informes,** **en** Informe, seleccione Usuarios bloqueados por **RTC** y, a continuación, haga clic en **Ejecutar informe.**

![Captura de pantalla del informe de usuarios bloqueados rtc en el centro de administración](../media/teams-reports-pstn-blocked-users-with-callouts.png "Captura de pantalla del informe de usuarios bloqueados rtc en el Microsoft Teams de administración con llamadas numeradas")

## <a name="interpret-the-report"></a>Interpretar el informe

|Globo |Descripción  |
|--------|-------------|
|**1**   |Cada informe tiene una fecha para cuándo se generó. Normalmente, el informe refleja una latencia de 24 a 48 horas desde el momento de actividad. |
|**2**   |El eje X es la fecha. El eje Y es el número de usuarios. <br>Mantenga el puntero sobre el punto en una fecha determinada para ver el número de usuarios bloqueados en esa fecha. |
|**3**   |La tabla proporciona un desglose de todos los usuarios que están bloqueados para realizar llamadas RTC.  Muestra todos los usuarios que tienen Sistema telefónico o Audioconferencia asignadas y le proporciona más información sobre cada usuario. <ul><li>**Nombre para mostrar** es el nombre para mostrar del usuario. Puede hacer clic en el nombre para mostrar para ir a la página de configuración del usuario en el Microsoft Teams de administración. </li> <li>**Teléfono** es el número asignado al usuario.</li> <li>**El motivo bloqueado** es la razón por la que el usuario está bloqueado para realizar llamadas.</li><li>**La acción bloqueada** le indica si el usuario está bloqueado o desbloqueado para realizar llamadas RTC en Teams.</li> <li>**Hora bloqueada** es la fecha y hora (UTC) en las que el usuario no ha hecho llamadas.</li></li> </ul>Para ver la información que quiera en la tabla, asegúrese de agregar las columnas a la tabla. |
|**4**   |Seleccione **Editar columnas** para agregar o quitar columnas en la tabla.|
|**5**   |Seleccione **Pantalla completa** para ver el informe en modo de pantalla completa.|

## <a name="related-topics"></a>Temas relacionados

- [Análisis e informes de Teams](teams-reporting-reference.md)