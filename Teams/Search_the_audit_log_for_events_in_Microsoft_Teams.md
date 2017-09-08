---
title: "Buscar eventos en el log de auditorías en Microsoft Teams | Soporte técnico de Microsoft"
author: LolaJacobsen
ms.author: lolaj
manager: serdar
ms.date: 08/10/2017
ms.topic: tutorial
ms.prod: teams
description: "Aprenda a recuperar datos de Microsoft Teams del registro de auditorías."
ms.openlocfilehash: 165f9188280ca4482cb46c9f1cc316093eb38e62
ms.sourcegitcommit: 3b9b3f07f4f67cd5f43da68f48d62222d7e49167
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2017
---
<a name="search-the-audit-log-for-events-in-microsoft-teams"></a>Buscar eventos en el log de auditorías en Microsoft Teams
==================================================

El registro de auditorías ofrece capacidades de búsqueda ad-hoc en eventos destacados en todos los servicios de Office 365. Concretamente para Microsoft Teams, aquí hay algunos ejemplos de los eventos capturados:

-   Creación de equipos

-   Eliminación de equipos

-   Canal agregado

-   Configuración cambiada

La lista de eventos completa de todo Office 365 es muy larga y puede verla [aquí](https://support.office.com/en-us/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c?ui=en-US&rs=en-US&ad=US#ID0EABAAA=Audited_activities).

Antes de profundizar en la información esencial sobre auditorías, debe habilitarlas. Para habilitar las auditorías, navegue a *Security & Compliance Admin Center* (Centro de administración de seguridad y cumplimiento). En *Search for activity* (Buscar actividad), haga clic en **Start recording now** (Iniciar grabación ahora). Transcurridas 24 horas, los datos de auditoría estarán disponibles a través de *Audit Log Search* (Búsqueda en el registro de auditorías) que se encuentra en la ficha *Search & Investigation* (Búsqueda e investigación).


| |  |
|---------|---------|
|![](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image1.png)<br></br>Importante     |Los datos de auditoría solo están disponibles desde el momento en que se habilitó la auditoría.         |

![](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image2.png)

Veamos cómo recuperar datos de Microsoft Teams del registro de auditorías:

1.  Para recuperar información del registro de auditorías, navegue a [Security & Compliance Admin Center (Centro de administración de seguridad y cumplimiento)](https://go.microsoft.com/fwlink/?linkid=855775). En *Search & Investigation* (Búsqueda e investigación), seleccione **Audit log search** (Búsqueda en el registro de auditorías).

    a.  Microsoft Teams ha definido las actividades de auditoría que se pueden seleccionar como se muestra a continuación.

![](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image3.png)

2.  Tras seleccionar las actividades de interés, indique un intervalo de fechas y los usuarios de los que se recuperará información en Microsoft Teams. Haga clic en **Buscar** para obtener resultados.

3.  Esta información se puede exportar a Excel y filtrarla si es necesario.


|  | |
|---------|---------|
|![](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image1.png)<br></br>Importante |Si no se han habilitado las auditorías con antelación, deberá hacerlo antes de que los datos aparezcan en el registro de auditorías.         |
