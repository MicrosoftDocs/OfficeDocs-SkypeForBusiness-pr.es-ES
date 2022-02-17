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
ms.openlocfilehash: 774688012d4e70a20897cd45aa78883ba7985e68
ms.sourcegitcommit: 1190cd73656dbc9131d46e0a827e28bcd960dfc5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2022
ms.locfileid: "62864043"
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

- Actividad
- Chat
- Teams
- Turnos
- Tareas

## <a name="admin-controls"></a>Controles de administrador

> [!NOTE]
> La anclación de usuario debe estar activada en la directiva de configuración de aplicaciones global ( [predeterminada para toda](teams-app-setup-policies.md) la organización) para que esta característica suba a efecto.

La característica de experiencia de aplicación personalizada se controla mediante la configuración Mostrar aplicaciones **personalizadas basadas** en licencias de aplicaciones de toda la [](manage-apps.md#manage-org-wide-app-settings) organización en la página Administrar aplicaciones del centro de administración Teams usuarios. Si la característica está en, todos los usuarios de su organización que tengan una licencia F recibirán la experiencia de aplicación personalizada.

Tenga en cuenta que las directivas de configuración de aplicaciones personalizadas asignadas a los usuarios tienen prioridad. Esto significa que si un usuario ya tiene asignada una directiva de configuración de aplicaciones personalizada, el usuario obtiene la configuración que se define en la directiva de configuración de la aplicación personalizada. Para obtener más información sobre cómo funciona la característica con las directivas de configuración de aplicaciones existentes que ha aplicado en su organización, vea la sección [Escenarios](#scenarios) de este artículo.

Esta característica está activada de forma predeterminada. Sin embargo, si no quiere la experiencia de aplicación personalizada proporcionada por Microsoft, puede desactivar la característica. Para desactivar o activar la característica:

1. En el panel de navegación izquierdo del Microsoft Teams de administración, vaya a Teams **aplicaciones** >  **de** administración y, a continuación, seleccione Configuración de la aplicación **para toda la organización**.
2. En **Aplicaciones personalizadas**, cambie la opción Mostrar **aplicaciones personalizadas basadas en licencias** **a Desactivado** o **Encendido**.

## <a name="scenarios"></a>Escenarios

Use la información de esta tabla para obtener información sobre cómo funciona la característica de experiencia de aplicación personalizada en varios escenarios, incluso cuando haya aplicado directivas de configuración de aplicaciones existentes.

|Si...  |Después... |
|---------|---------|
|Un usuario tiene la directiva de configuración global de la aplicación y la característica está en.     | El usuario obtiene la experiencia de aplicación personalizada.        |
|Un usuario tiene una directiva de configuración de aplicaciones personalizada y la característica está en.    |El usuario obtiene la configuración que se define en la directiva de configuración de la aplicación personalizada.          |
|La característica está en y actualiza la directiva de configuración global de la aplicación.     |El usuario obtiene la experiencia de aplicación personalizada en función de su licencia. Las aplicaciones definidas en la directiva global de configuración de aplicaciones siguen ancladas y aparecen más abajo en la lista de aplicaciones ancladas.          |
|La característica está desactivada.   | El usuario obtiene la experiencia que se define en la directiva global de configuración de aplicaciones o en la directiva de configuración de aplicaciones personalizada que se les ha asignado.          |
|Un usuario tiene una licencia E, A o G y la característica está en.   | El usuario no obtiene la experiencia de aplicación personalizada. Actualmente, la experiencia de aplicación personalizada solo se aplica a los usuarios que tienen una licencia F.        |
|Una aplicación de la experiencia de aplicación personalizada está bloqueada para un usuario o para su organización.      |La experiencia de aplicación personalizada respeta la directiva de permisos de la aplicación. Si una aplicación está bloqueada, los usuarios no verán la aplicación bloqueada.           |
|Una aplicación en la experiencia de aplicación personalizada ya está definida en una directiva de configuración de la aplicación y la característica está en. |La aplicación se ancla según el orden definido por la experiencia de aplicación personalizada.        |

> [!NOTE]
> No puede cambiar las aplicaciones ni el orden de las aplicaciones en la experiencia de aplicación personalizada. Por ahora, si desea realizar cambios, puede configurar su propia experiencia personalizada. Para ello, primero desactive la característica. A [continuación, cree una directiva de configuración de aplicaciones personalizada](teams-app-setup-policies.md) y [asígnela a usuarios o grupos](assign-policies-users-and-groups.md).

## <a name="related-articles"></a>Artículos relacionados

- [Administrar directivas de configuración de aplicación en Teams](teams-app-setup-policies.md)
- [Administrar directivas de permisos de aplicación en Teams](teams-app-permission-policies.md)
