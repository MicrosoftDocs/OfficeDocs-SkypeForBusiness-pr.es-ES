---
title: Buscar eventos de administración de aplicaciones en los registros de auditoría
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.date: 12/02/2022
ms.collection:
- M365-collaboration
search.appverid: MET150
f1keywords: ''
description: Obtén información sobre cómo auditar las actividades de la aplicación Teams de los usuarios y administradores de la organización.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 9114bae9fa24a546aec2629f1f347af193b10fd5
ms.sourcegitcommit: 339a35e461c84ee309ade1a53299ba12231df7a3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/29/2022
ms.locfileid: "69677510"
---
# <a name="search-audit-logs-for-app-management-activities-and-events"></a>Buscar registros de auditoría para actividades y eventos de administración de aplicaciones

La auditoría de Microsoft Purview (estándar) de Microsoft 365 permite buscar registros de auditoría de actividades realizadas en los distintos servicios de Microsoft 365 por parte de usuarios finales y administradores.

Antes de poder buscar en los registros de auditoría, asegúrese de completar los siguientes requisitos previos:

* [Obtenga la suscripción de la organización y las licencias de usuario](/microsoft-365/compliance/set-up-basic-audit).
* [Activa la auditoría en el portal de cumplimiento Microsoft Purview](/microsoft-365/compliance/turn-audit-log-search-on-or-off).
* [Asigna permisos para buscar en el registro de auditoría](/microsoft-365/compliance/set-up-basic-audit).

## <a name="search-the-audit-logs-for-app-events-in-teams"></a>Buscar eventos de aplicación en Teams en los registros de auditoría

Los registros de auditoría de los eventos de la aplicación en Teams le ayudan a investigar acciones específicas relacionadas con la administración de aplicaciones por parte de los administradores. Aunque puede buscar en los registros una amplia gama de acciones, en la tabla siguiente se enumeran algunas de estas acciones que se registran.

| Acción de la aplicación de Teams | Nombre de la actividad en el portal | Descripción  |
|-------|-------|:-------|
| **Aplicación instalada**                 | `AppInstalled`               | Se instala una aplicación o se agrega a un cliente de Teams. |
| **Aplicación actualizada**                  | `AppUpgraded`                | Una aplicación se actualiza a su última versión en el catálogo. |
| **Aplicación desinstalada**               | `AppUninstalled`             | Una aplicación se desinstala o se quita de un cliente de Teams.                                   |
| **Aplicación publicada**                 | `AppPublishedToCatalog`      | Se agrega una aplicación al catálogo.                          |
| **Aplicación actualizada**                   | `AppUpdatedInCatalog`        | Una aplicación se actualiza en el catálogo.                        |
| **Aplicación eliminada**                   | `AppDeletedFromCatalog`      | Una aplicación se elimina del catálogo.                      |
| **Eliminadas todas las aplicaciones de la organización** | `DeletedAllOrganizationApps` | Se han eliminado todas las aplicaciones de la organización del catálogo.          |

<!--- organization apps = custom or 3p --->

Para obtener una lista completa de las actividades de Teams que se auditan, consulta [Actividades de Teams](audit-log-events.md#teams-activities) y [Turnos en las actividades de Teams](audit-log-events.md#shifts-in-teams-activities).

> [!NOTE]
> Los eventos de la aplicación de canales privados también se registran a medida que esos eventos se realizan en Teams y en los canales estándar.

Para buscar en los registros de auditoría de las actividades de la aplicación Teams, siga estos pasos:

1. Inicia sesión en portal de cumplimiento Microsoft Purview y ve a la **Auditoría de soluciones** > **[](https://compliance.microsoft.com/auditlogsearch)**.
1. En la página **Auditoría** , actualice los siguientes campos según sea necesario:

   * **Intervalo de fecha y hora**: seleccione las fechas de inicio y finalización del período de tiempo para el que desea comprobar los registros de auditoría.
   * **Actividades**: introduce las actividades de Microsoft Teams. Selecciona una o más actividades de la aplicación en la lista. Para encontrar rápidamente las actividades de Teams, puedes buscar la palabra `Teams activities` en el campo de búsqueda **Actividades**.
   * **Archivo, carpeta o sitio**: escribe un nombre de archivo, una dirección URL o una parte de él.
   * **Usuarios**: agrega a los usuarios cuyo registro de auditoría quieras buscar.

1. Selecciona **Buscar**.

   :::image type="content" source="media/compliance-search-teams-activities-trimmed.png" alt-text="Busca las actividades de Teams en la portal de cumplimiento de Microsoft Purview para auditar los eventos de Teams." lightbox="media/compliance-search-teams-activities.png":::

Puede exportar los registros de auditoría buscados como un archivo CSV. Para obtener más información, consulta [Exportar, configurar y ver registros de auditoría](/microsoft-365/compliance/export-view-audit-log-records).

> [!NOTE]
> Cuando un usuario o un administrador realiza una de las actividades anteriores, Teams genera y almacena un registro de auditoría. En Auditoría (Estándar), los registros se conservan durante 90 días, lo que significa que puedes buscar actividades que se hayan producido en los últimos tres meses.

> [!TIP]
> Como administrador, si desea crear un informe por usuario para saber si un usuario ha bloqueado o silenciado un bot, consulte [Comprender quién ha bloqueado, silenciado o desinstalado un bot](/microsoftteams/platform/bots/how-to/conversations/send-proactive-messages?#understand-who-blocked-muted-or-uninstalled-a-bot).

## <a name="related-articles"></a>Artículos relacionados

* [Use registros de auditoría para investigar Microsoft actividad de instalación de Power Platform](manage-power-platform-apps.md#use-audit-logs-to-check-microsoft-power-platform-installation-activity).
* [Busca el signo de auditoría en el portal de cumplimiento](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).
* [Información general sobre Auditoría premium de Microsoft Purview](/microsoft-365/compliance/advanced-audit).
* [Activar o desactivar la auditoría](/microsoft-365/compliance/turn-audit-log-search-on-or-off).
