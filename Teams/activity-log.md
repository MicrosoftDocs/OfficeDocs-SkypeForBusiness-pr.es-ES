---
title: Ver las asignaciones de directivas en el registro de actividades del Centro de administración de Microsoft Teams
ms.author: mabond
author: mkbond007
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Obtenga información sobre cómo ver las actividades de asignación de directivas en el registro de actividades del Centro de administración de Microsoft Teams.
ms.localizationpriority: medium
f1.keywords:
- CSH
- ms.teamsadmincenter.dashboard.activitylog.overview
ms.custom: ''
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e8243d60a2aca31a8b9158b922126c7c80a486eb
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562219"
---
# <a name="view-your-policy-assignments-in-the-activity-log"></a>Ver las asignaciones de directivas en el registro de actividades

Al asignar directivas a usuarios en el Centro de administración de Microsoft Teams, puede ver el estado de esas asignaciones de directivas en el registro de actividades. El registro de actividades muestra las asignaciones de directivas a lotes de más de 20 usuarios a través del Centro de administración de Microsoft Teams de los últimos 30 días. Tenga en cuenta que el registro de actividades no muestra asignaciones de paquetes de directivas, asignaciones de directivas a lotes de menos de 20 usuarios a través del Centro de administración de Microsoft Teams ni asignaciones de directivas a través de PowerShell.

![Captura de pantalla de la página del registro de actividades.](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a>Ver las actividades de asignación de directivas en el registro de actividades

Para ver las asignaciones de directivas en el registro de actividades:

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Inicio** y, a continuación, en **Registro** de actividades, seleccione **Ver detalles**.
2. Puede ver todas las asignaciones de directiva o filtrar la lista por estado para mostrar solo las asignaciones que **no se han iniciado**, **En curso** o **Completadas**. Verá la siguiente información sobre cada tarea:
    - **Nombre**: el nombre de la asignación de directiva. Haga clic en el vínculo para ver más detalles. Esto incluye el número de usuarios a los que se asignó la directiva y el número de asignaciones completadas, en curso y no iniciadas. También verá la lista de usuarios del lote y el estado y el resultado de cada usuario. Aquí se muestra un ejemplo:

        ![Captura de pantalla de.](media/activity-log-policy-assignment-detail.png)

    - **Enviado**: fecha y hora en que se envió la asignación de directiva.
    - **Tiempo de finalización**: fecha y hora en que se completó la asignación de directiva.
    - **Impacto en**: Número de usuarios en el lote.
    - **Estado general**: estado de la asignación de directiva.

> [!NOTE]
> También puede acceder al registro de actividades desde la página **Usuarios** . Después de hacer clic en **Aplicar** para enviar una asignación de directiva masiva, verá un banner en la parte superior de la página. Haga clic en el vínculo **Registro de** actividades en la pancarta.

## <a name="related-topics"></a>Temas relacionados

- [Asignar directivas a usuarios](policy-assignment-overview.md)
