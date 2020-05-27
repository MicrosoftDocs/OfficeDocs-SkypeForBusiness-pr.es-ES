---
title: Ver las asignaciones de directivas en el registro de actividades del centro de administración de Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Obtenga información sobre cómo ver las actividades de asignación de directivas en el registro de actividades en el centro de administración de Microsoft Teams.
localization_priority: Normal
f1.keywords:
- CSH
- ms.teamsadmincenter.dashboard.activitylog.overview
ms.custom: ''
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5f85899869a8578df59516d0e0d702f8e36bd951
ms.sourcegitcommit: 47637ed816b471fe689e7bdac27b73e6efced60c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44374298"
---
# <a name="view-your-policy-assignments-in-the-activity-log"></a>Ver las asignaciones de directivas en el registro de actividades

Al asignar directivas a usuarios en el centro de administración de Microsoft Teams, puede ver el estado de esas asignaciones de directiva en el registro de actividades. En el registro de actividades se muestran asignaciones de directivas de los lotes de más de 20 usuarios a través del centro de administración de Microsoft Teams desde los últimos 30 días. Tenga en cuenta que el registro de actividades no muestra asignaciones de paquetes de directivas, asignaciones de directiva a lotes de menos de 20 usuarios a través del centro de administración de Microsoft Teams o asignación de directivas a través de PowerShell.

![Captura de pantalla de la página Registro de actividades](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a>Ver las actividades de asignación de directivas en el registro de actividades

Para ver las asignaciones de directivas en el registro de actividades:

1. En el panel de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **Panel**y, a continuación, en **registro de actividades**, seleccione **Ver detalles**.
2. Puede ver todas las asignaciones de directivas o filtrar la lista por estado para que solo se muestren las asignaciones que **no estén iniciadas**, estén **en curso**o **completadas**. Verá la siguiente información sobre cada asignación:
    - **Nombre**: el nombre de la asignación de directiva. Haga clic en el vínculo para ver más detalles. Esto incluye el número de usuarios a los que se asignó la Directiva y el número de tareas completadas, en curso y no iniciadas. También verá la lista de usuarios en el lote, así como el estado y el resultado de cada usuario. Aquí se muestra un ejemplo:

        ![Captura de pantalla de la](media/activity-log-policy-assignment-detail.png)

    - **Enviado**: fecha y hora en que se envió la asignación de directiva.
    - **Hora de finalización**: fecha y hora en que se completó la asignación de directiva.
    - **Impacto en**: número de usuarios en el lote.
    - **Estado general**: estado de la asignación de directiva.

> [!NOTE]
> También puede acceder al registro de actividades desde la página **usuarios** . Después de hacer clic en **aplicar** para enviar una asignación de directiva masiva, verá una pancarta en la parte superior de la página. Haga clic en el vínculo **registro de actividades** de la pancarta.

## <a name="related-topics"></a>Temas relacionados

- [Asignar directivas a usuarios](assign-policies.md)
