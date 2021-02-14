---
title: Ver las tareas de directiva en el registro de actividades del Centro de administración de Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Obtenga información sobre cómo ver las actividades de asignación de directivas en el registro de actividades del Centro de administración de Microsoft Teams.
localization_priority: Normal
f1.keywords:
- CSH
- ms.teamsadmincenter.dashboard.activitylog.overview
ms.custom: ''
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2a8d1d49d187808b768b4a92c64c4e667ca0ea8f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821320"
---
# <a name="view-your-policy-assignments-in-the-activity-log"></a>Ver las asignaciones de directivas en el registro de actividades

Al asignar directivas a usuarios en el Centro de administración de Microsoft Teams, puede ver el estado de dichas asignaciones de directiva en el registro de actividades. El registro de actividades muestra las asignaciones de directivas a lotes de más de 20 usuarios a través del Centro de administración de Microsoft Teams de los últimos 30 días. Tenga en cuenta que el registro de actividades no muestra las asignaciones del paquete de directivas, las asignaciones de directiva a lotes de menos de 20 usuarios a través del Centro de administración de Microsoft Teams o las asignaciones de directivas a través de PowerShell.

![Captura de pantalla de la página de registro de actividades](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a>Ver las actividades de asignación de directivas en el registro de actividades

Para ver las asignaciones de directivas en el registro de actividades:

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya al panel **y,** a continuación, en Registro de **actividades,** seleccione **Ver detalles.**
2. Puede ver todas las asignaciones de directiva o filtrar la lista por estado para mostrar solo las asignaciones que no se han **iniciado,** en **curso** o **completadas.** Verá la siguiente información sobre cada tarea:
    - **Nombre:** el nombre de la asignación de directiva. Haga clic en el vínculo para ver más detalles. Esto incluye el número de usuarios a los que se asignó la directiva y el número de asignaciones completadas, en curso y sin iniciar. También verá la lista de usuarios en el lote, así como el estado y el resultado de cada usuario. Aquí se muestra un ejemplo:

        ![Captura de pantalla del](media/activity-log-policy-assignment-detail.png)

    - **Enviado:** fecha y hora en que se envió la asignación de directiva.
    - **Hora de finalización:** fecha y hora en que se completó la asignación de la directiva.
    - **Impacto en**: Número de usuarios en el lote.
    - **Estado general:** estado de la asignación de la directiva.

> [!NOTE]
> También puede acceder al registro de actividades desde la **página** Usuarios. Después de hacer **clic en Aplicar** para enviar una asignación de directiva masiva, verá un banner en la parte superior de la página. Haz clic en **el vínculo del** registro de actividades en la pancarta.

## <a name="related-topics"></a>Temas relacionados

- [Asignar directivas a usuarios](assign-policies.md)
