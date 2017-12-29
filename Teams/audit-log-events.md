---
title: "Buscar eventos en el log de auditorías en Microsoft Teams | Soporte técnico de Microsoft"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Aprenda a recuperar datos de Microsoft Teams del registro de auditorías."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: b63f6b88d950038ec2e40e7b32eb74bc551cbdf1
ms.sourcegitcommit: 83aa84750e0bd210c24b3bd7315020a451d3f056
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2017
---
<a name="search-the-audit-log-for-events-in-microsoft-teams"></a>Buscar eventos en el log de auditorías en Microsoft Teams
==================================================

El registro de auditorías ofrece capacidades de búsqueda ad-hoc en eventos destacados en todos los servicios de Office 365. Concretamente para Microsoft Teams, aquí hay algunos ejemplos de los eventos capturados:

-   Creación de equipos

-   Eliminación de equipos

-   Canal agregado

-   Configuración cambiada

La lista de eventos completa de todo Office 365 es muy larga y puede verla [aquí](https://support.office.com/en-us/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c?ui=en-US&rs=en-US&ad=US#ID0EABAAA=Audited_activities).

Antes de profundizar en la información esencial sobre auditorías, debe habilitarlas. Para habilitar las auditorías, vaya a *Security & Compliance Admin Center* (Centro de administración de seguridad y cumplimiento). En *Search for activity* (Buscar actividad), haga clic en **Start recording now** (Iniciar grabación ahora). Transcurridas 24 horas, los datos de auditoría estarán disponibles a través de *Audit Log Search* (Búsqueda en el registro de auditorías) que se encuentra en la ficha *Search & Investigation* (Búsqueda e investigación).


> [!IMPORTANT]
> Los datos de auditoría solo están disponibles desde el momento en que se habilitó la auditoría.



![Captura de pantalla de la página de búsqueda del registro de auditorías del Centro de seguridad y cumplimiento.](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image2.png)

Veamos cómo recuperar datos de Microsoft Teams del registro de auditorías:

1.  Para recuperar información del registro de auditorías, navegue a [Security & Compliance Admin Center (Centro de administración de seguridad y cumplimiento)](https://go.microsoft.com/fwlink/?linkid=855775). En *Search & Investigation* (Búsqueda e investigación), seleccione **Audit log search** (Búsqueda en el registro de auditorías).

    a.  Microsoft Teams ha definido las actividades de auditoría que se pueden seleccionar como se muestra a continuación.

![Captura de pantalla de la página de búsqueda del registro de auditorías del Centro de seguridad y cumplimiento.](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image3.png)

2.  Tras seleccionar las actividades de interés, indique un intervalo de fechas y los usuarios de los que se recuperará información en Microsoft Teams. Haga clic en **Buscar** para obtener resultados.

3.  Esta información se puede exportar a Excel y filtrarla si es necesario.


> [!IMPORTANT]
> Si no se han habilitado las auditorías con antelación, deberá hacerlo para que los datos aparezcan en el registro de auditorías.


