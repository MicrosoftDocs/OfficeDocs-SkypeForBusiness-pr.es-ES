---
title: Ver las asignaciones de directivas en el registro de actividades en el centro Microsoft Teams administración
author: serdars
ms.author: serdars
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Obtenga información sobre cómo ver las actividades de asignación de directivas en el registro de actividades en el Microsoft Teams de administración.
ms.localizationpriority: medium
f1.keywords:
- CSH
- ms.teamsadmincenter.dashboard.activitylog.overview
ms.custom: ''
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 21caf6d694c201b12527b4be3f33856b887d177b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743086"
---
# <a name="view-your-policy-assignments-in-the-activity-log"></a>Ver las asignaciones de directivas en el registro de actividades

Al asignar directivas a usuarios en el centro de administración de Microsoft Teams, puede ver el estado de esas asignaciones de directivas en el registro de actividades. El registro de actividades muestra las asignaciones de directivas a lotes de más de 20 usuarios a través del centro de administración de Microsoft Teams desde los últimos 30 días. Tenga en cuenta que el registro de actividades no muestra asignaciones de paquetes de directiva, asignaciones de directivas a lotes de menos de 20 usuarios a través del centro de administración de Microsoft Teams o asignaciones de directivas a través de PowerShell.

![Captura de pantalla de la página Registro de actividades.](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a>Ver las actividades de asignación de directivas en el registro de actividades

Para ver las asignaciones de directivas en el registro de actividades:

1. En la navegación izquierda del centro de Microsoft Teams, vaya a Inicio **y,** a continuación, en Registro de actividades, seleccione Ver **detalles.**
2. Puede ver todas las asignaciones de directivas o filtrar la lista por estado para mostrar solo las tareas no iniciadas, en curso **o** **completadas.** Verá la siguiente información sobre cada tarea:
    - **Nombre:** el nombre de la asignación de directivas. Haga clic en el vínculo para ver más detalles. Esto incluye el número de usuarios a los que se asignó la directiva y el número de tareas completadas, en curso y no iniciadas. También verá la lista de usuarios en el lote, así como el estado y el resultado de cada usuario. Aquí se muestra un ejemplo:

        ![Captura de pantalla de la.](media/activity-log-policy-assignment-detail.png)

    - **Enviado:** Fecha y hora en que se envió la asignación de directiva.
    - **Hora de finalización:** fecha y hora en que se completó la asignación de directivas.
    - **Impacto en:** Número de usuarios en el lote.
    - **Estado general:** Estado de la asignación de directivas.

> [!NOTE]
> También puede acceder al registro de actividades desde la **página** Usuarios. Después de hacer **clic en Aplicar** para enviar una asignación de directiva en masa, verá un banner en la parte superior de la página. Haga clic en **el vínculo Registro** de actividades en el banner.

## <a name="related-topics"></a>Temas relacionados

- [Asignar directivas a los usuarios](policy-assignment-overview.md)
