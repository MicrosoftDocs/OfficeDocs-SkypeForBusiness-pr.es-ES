---
title: Personalizar aplicaciones de Teams para los trabajadores de primera línea
author: LanaChin
ms.author: v-lanachin
ms.reviewer: aaglick
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre la experiencia de aplicación adaptada para los trabajadores de primera línea en Teams.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: b526733558570e4903d9dce43094c7ffa0f7de17
ms.sourcegitcommit: 480046a53dfb6e6cf867e1920f8fb43dda9d3774
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2022
ms.locfileid: "63774189"
---
# <a name="tailor-teams-apps-for-your-frontline-workers"></a>Personalizar aplicaciones de Teams para los trabajadores de primera línea

> [!NOTE]
> [!INCLUDE [new-feature-coming-soon-section](includes/new-feature-coming-soon-section.md)]

## <a name="overview"></a>Información general

Teams proporciona una forma sencilla de anclar aplicaciones a los trabajadores de primera línea. Esta característica ancla aplicaciones basadas en licencias para ofrecer a sus trabajadores de primera línea una experiencia rápida en Teams adaptada a sus necesidades.

Con la experiencia de aplicación frontline adaptada, los trabajadores de primera línea obtienen las aplicaciones más relevantes en Teams sin que el administrador realice ninguna acción.

## <a name="tailored-frontline-app-experience"></a>Experiencia de aplicación de primera línea personalizada

Las aplicaciones se anclan a la barra de aplicaciones, que es la barra de la parte inferior de la Teams clientes móviles (iOS y Android) y en el lateral del cliente de escritorio de Teams. Las siguientes aplicaciones están ancladas para los usuarios que tienen una [licencia F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt):

- [Actividad](https://support.microsoft.com/office/explore-the-activity-feed-in-teams-91c635a1-644a-4c60-9c98-233db3e13a56)
- [Chat](https://support.microsoft.com/office/get-started-with-chat-0b506ce2-eb6d-4fca-9668-e56980ba755e)
- [Teams](https://support.microsoft.com/office/teams-and-channels-in-microsoft-teams-c6d0e61d-a61e-44a6-a972-04f2a8fa4155)
- [Walkie-talkie](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [Tareas](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070)
- [Turnos](https://support.microsoft.com/office/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821)
- [Aprobaciones](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3)

**Teams móvil**

:::image type="content" source="media/tailored-teams-apps-mobile.png" alt-text="La experiencia de aplicación de primera línea personalizada en Teams móvil" lightbox="media/tailored-teams-apps-mobile.png"::: 

**Teams escritorio**

:::image type="content" source="media/tailored-teams-apps-desktop.png" alt-text="La experiencia de aplicación frontline adaptada en Teams escritorio" lightbox="media/tailored-teams-apps-desktop.png"::: 

## <a name="admin-controls"></a>Controles de administración

> [!NOTE]
> La configuración **anclaje de usuario** debe estar activada en la [directiva de configuración](teams-app-setup-policies.md) de aplicaciones global (predeterminada para toda la organización) para que esta característica surta efecto.

La experiencia de aplicación frontline adaptada se controla mediante la configuración **Mostrar aplicaciones adaptadas** para toda la organización en la página [Administrar aplicaciones](manage-apps.md#manage-org-wide-app-settings) del centro de administración de Teams. Si la característica está activada, todos los usuarios de su organización que tengan una licencia F obtendrán la experiencia de aplicación personalizada.

Tenga en cuenta que todas [las directivas de configuración de aplicaciones](teams-app-setup-policies.md) personalizadas asignadas a los usuarios tendrán prioridad. Esto significa que, si un usuario ya tiene asignada una directiva de configuración de aplicación personalizada, el usuario obtiene la configuración que se define en la directiva de configuración de aplicación personalizada. Para obtener más información sobre cómo funciona la característica con las [directivas](#scenarios) de Teams aplicación, incluida la directiva de configuración global de aplicaciones, consulte la sección Escenarios más adelante en este artículo.

Esta característica está activada de forma predeterminada. Sin embargo, si no desea la experiencia de aplicación de primera línea adaptada proporcionada por Microsoft, puede desactivar la característica. Para activar o desactivar la característica:

1. En el panel de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **Teams** **aplicacionesAdministrar aplicaciones** >  y, después, seleccione **Configuración de aplicaciones para toda** la organización.
2. En **Aplicaciones adaptadas**, cambia el botón de alternancia **Mostrar aplicaciones adaptadas** a **Desactivado** o **Activado**.

    :::image type="content" source="media/tailored-teams-apps-admin-center.png" alt-text="Captura de pantalla de la configuración Mostrar aplicaciones adaptadas en la página Administrar aplicaciones del centro de administración de Teams" lightbox="media/tailored-teams-apps-admin-center.png":::

## <a name="scenarios"></a>Escenarios

### <a name="how-does-the-tailored-frontline-app-experience-affect-my-global-app-setup-policy"></a>¿Cómo afecta la experiencia de la aplicación frontline adaptada a mi directiva de configuración global de aplicaciones?

Obtenga información sobre cómo funciona la experiencia de aplicación frontline adaptada junto con la directiva de configuración global de aplicaciones. Los escenarios de esta tabla se aplican a los trabajadores de primera línea que tienen una licencia F y la directiva de configuración global de aplicaciones, con **anclaje de usuario** activado.

|Si... |Entonces... |
|---------|---------|
|Un trabajador de primera línea tiene la directiva de configuración global de aplicaciones y la característica está desactivada. |El trabajador de primera línea obtiene las aplicaciones definidas en la directiva de configuración global de aplicaciones.|
|Un trabajador de primera línea tiene la directiva de configuración global de la aplicación y la característica está activada.     | El trabajador de primera línea obtiene la experiencia de aplicación de primera línea personalizada. Las aplicaciones definidas en la directiva de configuración global de aplicaciones se anclan debajo de las aplicaciones adaptadas.      |
|Actualiza la directiva de configuración global de aplicaciones y la característica está activada.     |El trabajador de primera línea obtiene la experiencia de aplicación de primera línea adaptada y las aplicaciones definidas en la directiva de configuración global de aplicaciones se anclan debajo de las aplicaciones adaptadas.         |
|Un trabajador de primera línea tiene la directiva de configuración global de la aplicación y el **anclaje de usuarios** está desactivado. |El trabajador de primera línea obtiene las aplicaciones definidas en la directiva de configuración global de aplicaciones.|
|Un trabajador de primera línea tiene la directiva de configuración global de aplicaciones y la directiva de configuración global de aplicaciones se cambia para incluir una aplicación de línea de negocio (LOB) en la segunda posición en la lista de aplicaciones. |La aplicación LOB está anclada debajo de las aplicaciones adaptadas. El trabajador de primera línea puede cambiar el orden de la aplicación si **el anclaje del usuario** está activado.         |
|Un trabajador de primera línea tiene la directiva de configuración global y la directiva de configuración global de la aplicación se cambia para incluir turnos en la primera posición.  |Turnos está anclado a la sexta posición, según se define en la experiencia de aplicación de primera línea personalizada. El trabajador de primera línea puede cambiar el orden de la aplicación si **el anclaje del usuario** está activado.          |

### <a name="how-does-the-tailored-frontline-app-experience-work-with-other-teams-app-policies"></a>¿Cómo funciona la experiencia de aplicación frontline adaptada con otras directivas de aplicaciones de Teams?

Obtenga información sobre cómo funciona la experiencia de aplicación frontline adaptada con otras directivas de aplicaciones de Teams.

|Si...  |Entonces... |
|---------|---------|
La característica está desactivada.   | El trabajador de primera línea obtiene las aplicaciones definidas en la directiva de configuración global de aplicaciones o en la directiva de configuración de aplicaciones personalizada asignadas a ellas.          |
|Un trabajador de primera línea tiene una directiva de configuración de aplicación personalizada y la característica está activada.    |El trabajador de primera línea obtiene las aplicaciones definidas en la directiva de configuración de aplicaciones personalizada.          |
|Una aplicación de la experiencia de aplicación frontline adaptada está bloqueada para un usuario o para su organización.      |La experiencia de aplicación frontline adaptada respeta la [directiva de permisos](teams-app-permission-policies.md) de la aplicación. Si una aplicación está bloqueada, el trabajador de primera línea no verá la aplicación bloqueada.           |
|Una aplicación en la experiencia de aplicación frontline adaptada ya está definida en una directiva de configuración de aplicaciones y la característica está activada. |La aplicación está anclada en función del orden definido por la lista de aplicaciones adaptadas.        |
|Un usuario tiene una licencia de E, A o G y la característica está activada.   | El usuario no obtiene la experiencia de aplicación frontline adaptada. Actualmente, la experiencia solo se aplica a los usuarios que tienen una licencia F.        |

> [!NOTE]
> No puedes cambiar las aplicaciones ni el orden de las aplicaciones en la experiencia de aplicación de primera línea adaptada. Por ahora, si desea realizar cambios, puede configurar su propia experiencia personalizada. Para ello, primero desactive la característica. Después, [cree una directiva de configuración de aplicación personalizada](teams-app-setup-policies.md) y [asígnela a usuarios o grupos](assign-policies-users-and-groups.md).

## <a name="related-articles"></a>Artículos relacionados

- [Administrar la aplicación Walkie Talkie en Teams](walkie-talkie.md)
- [Administrar la aplicación Tareas en Teams](manage-tasks-app.md)
- [Administrar la aplicación Turnos en Teams](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)
- [Administrar la aplicación Aprobaciones en Teams](approval-admin.md)
- [Administrar directivas de configuración de aplicación en Teams](teams-app-setup-policies.md)
- [Administrar directivas de permisos de aplicación en Teams](teams-app-permission-policies.md)
