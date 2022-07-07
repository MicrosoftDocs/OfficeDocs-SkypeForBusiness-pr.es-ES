---
title: Buscar eventos de administración de aplicaciones en los registros de auditoría
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
f1keywords: ''
description: Obtén información sobre cómo auditar las actividades de la aplicación Teams de los usuarios y administradores de la organización.
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 77c7ac5d80304e82f1309e3a22b21c17d106a58c
ms.sourcegitcommit: 90f03a841f8ca33092dce65c543357c7c2f7b82a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66647842"
---
# <a name="audit-for-app-management-activities-and-events"></a>Auditoría de actividades y eventos de administración de aplicaciones

La auditoría de Microsoft Purview (estándar) de Microsoft 365 permite buscar registros de auditoría de actividades realizadas en los distintos servicios de Microsoft 365 por parte de usuarios finales y administradores.

Antes de poder buscar en la auditoría, asegúrate de completar los siguientes requisitos previos:

* [Obtén la suscripción de la organización y las licencias de usuario](/microsoft-365/compliance/set-up-basic-audit).
* [Activa la auditoría en el portal de cumplimiento Microsoft Purview](/microsoft-365/compliance/turn-audit-log-search-on-or-off).
* [Asigna permisos para buscar en el registro de auditoría](/microsoft-365/compliance/set-up-basic-audit).

## <a name="search-the-audit-logs-for-app-events-in-teams"></a>Buscar eventos de aplicación en Teams en los registros de auditoría

Los registros de auditoría de los eventos de aplicación en Teams ayudan a investigar acciones específicas. Aunque puedes buscar en los registros una amplia gama de acciones, en la tabla siguiente se enumeran algunas de las acciones de aplicación de Teams que se han registrado. Además, puedes buscar actividades relacionadas con conectores, bots, pestañas, etc.

| Acción de la aplicación de Teams                  | Nombre de la actividad                | Descripción                                              |
|-----------------------------------|------------------------------|:---------------------------------------------------------|
| **Aplicación instalada**                 | `AppInstalled`               | Se instala una aplicación.                                     |
| **Aplicación actualizada**                  | `AppUpgraded`                | Una aplicación se actualiza a su última versión en el catálogo. |
| **Aplicación desinstalada**               | `AppUninstalled`             | Se desinstala una aplicación.                                   |
| **Aplicación publicada**                 | `AppPublishedToCatalog`      | Se agrega una aplicación al catálogo.                          |
| **Aplicación actualizada**                   | `AppUpdatedInCatalog`        | Una aplicación se actualiza en el catálogo.                        |
| **Aplicación eliminada**                   | `AppDeletedFromCatalog`      | Una aplicación se elimina del catálogo.                      |
| **Eliminadas todas las aplicaciones de la organización** | `DeletedAllOrganizationApps` | Se han eliminado todas las aplicaciones de la organización del catálogo.          |

Para obtener una lista completa de las actividades de Teams que se auditan, consulta [Actividades de Teams](audit-log-events.md#teams-activities) y [Turnos en las actividades de Teams](audit-log-events.md#shifts-in-teams-activities).

> [!NOTE]
> Los eventos de la aplicación de los canales privados también se registran, ya que estos son para Teams y canales estándar.

Usa la herramienta Búsqueda en el registro de auditoría en el portal de cumplimiento para buscar registros de auditoría. Para buscar registros de auditoría de eventos de la aplicación, sigue estos pasos:

1. Inicia sesión en portal de cumplimiento Microsoft Purview y ve a la **Auditoría de soluciones** > **[](https://compliance.microsoft.com/auditlogsearch)**.
1. En la página auditoría, actualiza los siguientes campos según tus requisitos:

   * **Intervalo de fecha y hora**: selecciona las fechas de inicio y finalización.
   * **Actividades**: introduce las actividades de Microsoft Teams. Selecciona una o más actividades de la aplicación en la lista. Para encontrar rápidamente las actividades de Teams, puedes buscar la palabra `Teams activities` en el campo de búsqueda **Actividades**.
   * **Archivo, carpeta o sitio**: escribe un nombre de archivo, una dirección URL o una parte de él.
   * **Usuarios**: agrega a los usuarios cuyo registro de auditoría quieras buscar.

1. Selecciona **Buscar**.

   :::image type="content" source="media/compliance-search-teams-activities-trimmed.png" alt-text="Busca las actividades de Teams en la portal de cumplimiento de Microsoft Purview para auditar los eventos de Teams." lightbox="media/compliance-search-teams-activities.png":::

Después de buscar el inicio de sesión de auditoría en el portal de cumplimiento, podrás exportar los registros de auditoría como un archivo CSV. Para obtener más información, consulta [Exportar, configurar y ver registros de auditoría](/microsoft-365/compliance/export-view-audit-log-records).

> [!NOTE]
> Cuando un usuario o un administrador realiza una de las actividades anteriores, Teams genera y almacena un registro de auditoría. En Auditoría (Estándar), los registros se conservan durante 90 días, lo que significa que puedes buscar actividades que se hayan producido en los últimos tres meses.

## <a name="see-also"></a>Vea también

* [Busca el signo de auditoría en el portal de cumplimiento](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).
* [Información general sobre Auditoría premium de Microsoft Purview](/microsoft-365/compliance/advanced-audit).
* [Activar o desactivar la auditoría](/microsoft-365/compliance/turn-audit-log-search-on-or-off).
