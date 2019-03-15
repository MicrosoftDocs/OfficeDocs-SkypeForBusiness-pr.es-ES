---
title: Buscar eventos en el registro de auditoría en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: Aprenda a recuperar datos de Microsoft Teams del registro de auditoría de Office 365.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 028d01a2ed05f3596cfe7cca299a1b8e35a15721
ms.sourcegitcommit: bc2b227b4ac0a9521993f808a1361b4f9bc7faad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2019
ms.locfileid: "30568499"
---
<a name="search-the-audit-log-for-events-in-microsoft-teams"></a>Buscar eventos en el registro de auditoría en Microsoft Teams
==================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

El registro de auditoría puede ayudarle a investigar actividades específicas en los servicios de Office 365. Estas son algunas de las actividades que se auditan en Microsoft Teams:

-   Creación de equipos

-   Eliminación de equipos

-   Agregación de canales

-   Cambios en la configuración

Para ver la lista completa de actividades auditadas en Office 365, consulte [Buscar en el registro de auditoría del Centro de seguridad y cumplimiento de Office 365](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c).

## <a name="turn-on-auditing-in-teams"></a>Activar la auditoría en Microsoft Teams

Antes de que puede buscar en los datos de auditoría, tiene que activar el primer de auditoría en el **& centro de cumplimiento de seguridad**(https://protection.office.com). Para obtener ayuda para activar la auditoría, consulte [Activar o desactivar la búsqueda de registros de auditoría de Office 365](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).


> [!IMPORTANT]
> Los datos de auditoría solo están disponibles desde el momento en que se habilitó la auditoría.



## <a name="retrieve-teams-data-from-the-audit-log"></a>Recuperar datos de Microsoft Teams del registro de auditoría

1.  Para recuperar los registros de auditoría, vaya al [Centro de seguridad y cumplimiento](https://go.microsoft.com/fwlink/?linkid=855775). En **Search & Investigation** (Búsqueda e investigación), seleccione **Audit log search** (Búsqueda en el registro de auditorías).![Captura de pantalla de la página de búsqueda del registro de auditorías del Centro de seguridad y cumplimiento.](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image3.png)

2.  Use **Buscar** para filtrar por las actividades, las fechas y los usuarios que desee auditar.

3.  Exporte los resultados a Excel para continuar el análisis.


> [!IMPORTANT]
> Los datos de auditoría solo están visibles en el registro de auditoría si está activada la auditoría.

## <a name="video-techtip-using-audit-log-search-in-teams"></a>Vídeo: TechTip: Usar la búsqueda en el registro de auditoría en Microsoft Teams

Observe cómo Ansuman Acharya, un director de proyectos de Microsoft Teams, realiza una búsqueda en el registro de auditoría para Microsoft Teams en el Centro de seguridad y cumplimiento de Office 365. 


> [!VIDEO https://www.youtube.com/embed/UBxaRySAxyE]






