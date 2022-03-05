---
title: Personalizar las aplicaciones Teams basadas en la licencia
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaglick
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo anclar Teams aplicaciones para usuarios de su organización en función de la licencia.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 34614a6c1b45ea9660552b77b7c91d87e5c30d5f
ms.sourcegitcommit: 2d4dab7a6436e53db9475d67695504753896ca86
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2022
ms.locfileid: "63065248"
---
# <a name="tailor-your-teams-apps-based-on-license"></a>Personalizar las aplicaciones Teams basadas en la licencia

> [!NOTE]
> [!INCLUDE [new-feature-coming-soon-section](includes/new-feature-coming-soon-section.md)]

> [!NOTE]
> Actualmente, esta característica se aplica a las licencias F. Por lo tanto, este artículo se centra en la experiencia del trabajador en primera línea. Otros tipos de licencia serán compatibles en el futuro.

## <a name="overview"></a>Información general

Teams proporciona una forma de anclar aplicaciones basadas en licencia. Cuando un usuario inicia sesión Teams con la experiencia de aplicación personalizada habilitada, el usuario obtiene una experiencia de aplicación que se adapta según su licencia.

Esta característica proporciona a los usuarios las aplicaciones más relevantes Teams sin ninguna acción necesaria del administrador.

## <a name="tailored-app-experience"></a>Experiencia de aplicación personalizada

Las aplicaciones se anclan a la barra de aplicaciones, que es la barra del lado del cliente de escritorio de Teams y en la parte inferior de los clientes móviles de Teams (iOS y Android).

Aplicaciones ancladas para usuarios que tienen una licencia F:

- [Actividad](https://support.microsoft.com/office/explore-the-activity-feed-in-teams-91c635a1-644a-4c60-9c98-233db3e13a56)
- [Chat](https://support.microsoft.com/office/get-started-with-chat-0b506ce2-eb6d-4fca-9668-e56980ba755e)
- [Teams](https://support.microsoft.com/office/teams-and-channels-in-microsoft-teams-c6d0e61d-a61e-44a6-a972-04f2a8fa4155)
- [Walkie-talkie](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [Tareas](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070)
- [Turnos](https://support.microsoft.com/office/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821)
- [Aprobaciones](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3)

## <a name="admin-controls"></a>Controles de administrador

> [!NOTE]
> La anclación de usuario debe estar activada en la directiva de configuración de aplicaciones global ( [predeterminada para toda](teams-app-setup-policies.md) la organización) para que esta característica suba a efecto.

La característica de experiencia de aplicación personalizada se controla mediante la configuración Mostrar aplicaciones **personalizadas basadas** en licencias de aplicaciones de toda la [](manage-apps.md#manage-org-wide-app-settings) organización en la página Administrar aplicaciones del centro de administración de Teams. Si la característica está en, todos los usuarios de su organización que tengan una licencia F recibirán la experiencia de aplicación personalizada.

Tenga en cuenta que las directivas de configuración de aplicaciones personalizadas asignadas a los usuarios tienen prioridad. Esto significa que si un usuario ya tiene asignada una directiva de configuración de aplicaciones personalizada, el usuario obtiene la configuración que se define en la directiva de configuración de la aplicación personalizada. Para obtener más información sobre cómo funciona la característica con las directivas de configuración de aplicaciones existentes que ha aplicado en su organización, vea la sección [Escenarios](#scenarios) de este artículo.

Esta característica está activada de forma predeterminada. Sin embargo, si no quiere la experiencia de aplicación personalizada proporcionada por Microsoft, puede desactivar la característica. Para desactivar o activar la característica:

1. En el panel de navegación izquierdo del Microsoft Teams de administración, vaya a Teams **aplicaciones** >  **de** administración y, a continuación, seleccione Configuración de la aplicación para toda **la organización**.
2. En **Aplicaciones personalizadas**, cambie la opción Mostrar **aplicaciones personalizadas basadas en licencias** **a Desactivado** o **Encendido**.

## <a name="scenarios"></a>Escenarios

Use la información de esta tabla para obtener información sobre cómo funciona la experiencia de aplicación personalizada en varios escenarios, incluso cuando haya aplicado directivas de configuración de aplicaciones existentes.

|Si...  |Después... |
|---------|---------|
|Un usuario tiene la directiva de configuración global de la aplicación y la característica está en.     | El usuario obtiene la experiencia de aplicación personalizada. Las aplicaciones definidas en la directiva global de configuración de aplicaciones siguen ancladas y aparecen más abajo en la lista de aplicaciones ancladas.      |
|Un usuario tiene una directiva de configuración de aplicaciones personalizada y la característica está en.    |El usuario obtiene la configuración que se define en la directiva de configuración de la aplicación personalizada.          |
|La característica está en y actualiza la directiva de configuración global de la aplicación.     |El usuario obtiene la experiencia de aplicación personalizada en función de su licencia. Las aplicaciones definidas en la directiva global de configuración de aplicaciones siguen ancladas y aparecen más abajo en la lista de aplicaciones ancladas.          |
|La característica está desactivada.   | El usuario obtiene la experiencia que se define en la directiva global de configuración de aplicaciones o en la directiva de configuración de aplicaciones personalizada que se les ha asignado.          |
|Un usuario tiene una licencia E, A o G y la característica está en.   | El usuario no obtiene la experiencia de aplicación personalizada. Actualmente, la experiencia de aplicación personalizada solo se aplica a los usuarios que tienen una licencia F.        |
|Una aplicación de la experiencia de aplicación personalizada está bloqueada para un usuario o para su organización.      |La experiencia de aplicación personalizada respeta la directiva de permisos de la aplicación. Si una aplicación está bloqueada, los usuarios no verán la aplicación bloqueada.           |
|Una aplicación en la experiencia de aplicación personalizada ya está definida en una directiva de configuración de la aplicación y la característica está en. |La aplicación se ancla según el orden definido por la experiencia de aplicación personalizada.        |

> [!NOTE]
> No puede cambiar las aplicaciones ni el orden de las aplicaciones en la experiencia de aplicación personalizada. Por ahora, si desea realizar cambios, puede configurar su propia experiencia personalizada. Para ello, primero desactive la característica. A [continuación, cree una directiva de configuración de aplicaciones personalizada](teams-app-setup-policies.md) y [asígnela a usuarios o grupos](assign-policies-users-and-groups.md).

## <a name="related-articles"></a>Artículos relacionados

- [Administrar la aplicación Walkie Talkie en Teams](walkie-talkie.md)
- [Administrar la aplicación Tareas en Teams](manage-tasks-app.md)
- [Administrar la aplicación Turnos en Teams](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)
- [Administrar la aplicación Aprobaciones en Teams](approval-admin.md)
- [Administrar directivas de configuración de aplicación en Teams](teams-app-setup-policies.md)
- [Administrar directivas de permisos de aplicación en Teams](teams-app-permission-policies.md)
