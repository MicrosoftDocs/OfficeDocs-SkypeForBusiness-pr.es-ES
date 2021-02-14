---
title: Informe de usuarios bloqueados de RTC de Microsoft Teams
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
description: Use el informe Usuarios bloqueados de RTC en el Centro de administración de Microsoft Teams para obtener información general sobre los usuarios de Teams de su organización que no pueden realizar llamadas DE RTC.
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
# <a name="microsoft-teams-pstn-blocked-users-report"></a>Informe de usuarios bloqueados de RTC de Microsoft Teams

El informe Usuarios bloqueados de RTC en el Centro de administración de Microsoft Teams muestra los usuarios de su organización que no pueden realizar llamadas RTC en Teams. Puede ver más información sobre cada usuario bloqueado, incluido el número de teléfono asignado y la razón por la que se le bloqueó para realizar llamadas.

## <a name="view-the-pstn-blocked-users-report"></a>Ver el informe Usuarios bloqueados de RTC

En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, haga clic en **& informes de**  >  **uso.** En la **pestaña Ver informes,** en **Informe,** seleccione Usuarios bloqueados de **RTC** y, a continuación, haga clic en **Ejecutar informe.**

![Captura de pantalla del informe Usuarios bloqueados de RTC en el Centro de administración](../media/teams-reports-pstn-blocked-users-with-callouts.png "Captura de pantalla del informe Usuarios bloqueados de RTC en el centro de administración de Microsoft Teams con llamadas numeradas")

## <a name="interpret-the-report"></a>Interpretar el informe

|Globo |Descripción  |
|--------|-------------|
|**1**   |Cada informe tiene la fecha del momento en que se generó. Normalmente, el informe refleja una latencia de 24 a 48 horas desde el momento de actividad. |
|**2**   |El eje X es la fecha. El eje Y es el número de usuarios. <br>Mueva el puntero sobre el punto de una fecha determinada para ver el número de usuarios bloqueados en esa fecha. |
|**3**   |En la tabla se proporciona un desglose de todos los usuarios a los que no se permite realizar llamadas RTC.  Se muestran todos los usuarios que tienen asignado Sistema telefónico o Audioconferencia y se proporciona más información sobre cada usuario. <ul><li>**Nombre para mostrar** es el nombre para mostrar del usuario. Puede hacer clic en el nombre para mostrar para ir a la página de configuración del usuario en el Centro de administración de Microsoft Teams. </li> <li>**El** teléfono es el número que se asigna al usuario.</li> <li>**El motivo del** bloqueo es el motivo por el que se bloquea al usuario para que no haga llamadas.</li><li>**La acción**  bloqueada indica si el usuario está bloqueado o desbloqueado para realizar llamadas RTC en Teams.</li> <li>**La hora** bloqueada es la fecha y hora (UTC) en la que se bloqueó al usuario para que no pueda realizar llamadas.</li></li> </ul>Para ver la información que quiera en la tabla, asegúrese de agregar las columnas a la tabla. |
|**4**   |Seleccione **Editar columnas** para agregar o quitar columnas en la tabla.|
|**5**   |Seleccione **Pantalla completa para** ver el informe en el modo de pantalla completa.|

## <a name="related-topics"></a>Temas relacionados

- [Análisis e informes de Teams](teams-reporting-reference.md)