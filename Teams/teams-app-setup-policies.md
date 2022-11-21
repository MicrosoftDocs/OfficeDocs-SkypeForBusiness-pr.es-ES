---
title: Administrar directivas de configuración de aplicación en Microsoft Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.subservice: teams-apps
ms.service: msteams
audience: Admin
ms.date: 09/26/2022
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
description: Obtenga información sobre cómo crear, editar y administrar directivas de configuración de aplicaciones para anclar aplicaciones, instalar aplicaciones y permitir que los usuarios carguen aplicaciones personalizadas.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: 4c94f0610535fa014b0f759b104dd1aef901e055
ms.sourcegitcommit: ff161779577ce9cc892f1b6b8861ad49ff4c3ca3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2022
ms.locfileid: "69131009"
---
# <a name="use-app-setup-policies-to-pin-and-auto-install-apps-in-teams"></a>Usar directivas de configuración de aplicaciones para anclar e instalar automáticamente aplicaciones en Teams

Como administrador, puede usar las directivas de configuración de aplicaciones para instalar y anclar aplicaciones, así como controlar qué usuarios específicos pueden cargar aplicaciones personalizadas. Anclar ayuda a promover la adopción de las aplicaciones relevantes de su organización y a proporcionar acceso rápido a ellas.

* **[Anclar aplicaciones](#pin-apps):** Las directivas de configuración de aplicaciones le permiten elegir las aplicaciones que anclar, establecer el orden en que se muestran las aplicaciones para los usuarios en la barra de aplicaciones de Teams o en el área de redacción de mensajes. Los administradores también pueden controlar si los usuarios finales pueden anclar sus propias aplicaciones o no.

* **[Instalar aplicaciones](#install-apps):** Las directivas de configuración de aplicaciones le permiten instalar las aplicaciones permitidas en nombre de los usuarios cuando inician Teams y durante las reuniones.

* **Cargar aplicaciones personalizadas:** Las directivas de configuración de aplicaciones le permiten controlar qué usuarios pueden cargar aplicaciones personalizadas en Teams. Consulta [el artículo Cargar aplicaciones personalizadas](teams-custom-app-policies-and-settings.md) .

Las siguientes directivas de configuración de aplicaciones integradas están disponibles en el Centro de administración de Microsoft Teams de forma predeterminada:

* **Global (valor predeterminado para toda la organización)**: esta directiva predeterminada se aplica a todos los usuarios de la organización a menos que asigne otra directiva. Edite la directiva global para anclar las aplicaciones más importantes para los usuarios.

* **FirstlineWorker**: esta directiva es para personal de primera línea. No se puede personalizar la directiva. Puede asignarla a los trabajadores de primera línea de su organización.

## <a name="pin-apps"></a>Anclar aplicaciones

Anclar una aplicación muestra la aplicación en la barra de la aplicación en el cliente de Teams. Los administradores pueden anclar aplicaciones y pueden permitir que los usuarios lo anclen. Anclar es una forma de resaltar las aplicaciones más necesarias para los usuarios y promover la facilidad de acceso. El anclaje funciona para todos los [tipos de aplicaciones en Teams](deploy-apps-microsoft-teams-landing-page.md) : aplicaciones principales, aplicaciones proporcionadas por Microsoft, aplicaciones de terceros y aplicaciones personalizadas desarrolladas dentro de su organización.

Los administradores pueden anclar una aplicación a través de una directiva de configuración de aplicaciones. Las aplicaciones ancladas por los administradores se instalan automáticamente para los usuarios para los que se permite la aplicación. Los usuarios finales no pueden desinstalar dicha aplicación. Con una directiva de configuración de aplicaciones, puede realizar las siguientes tareas:

* Personalice Teams para los usuarios finales para resaltar las aplicaciones más importantes para ellos. Elegir las aplicaciones que se quieren anclar y el orden en que se muestran las aplicaciones.
* Controlar si los usuarios pueden o no anclar aplicaciones.

La aplicaciones se anclan a la barra de aplicaciones situada en el lateral izquierdo del cliente de escritorio de Teams y en la parte inferior de los clientes móviles. Las extensiones de mensajería están disponibles en la parte inferior del área de redacción de mensajes.

|Cliente de escritorio de Teams  |Cliente móvil de Teams |
|---------|---------|
|![Captura de pantalla que muestra la barra de la aplicación en el cliente de escritorio de Teams.](media/app-setup-policies-desktop-app-bar.png).  |   ![Captura de pantalla que muestra la barra de la aplicación en el cliente móvil de Teams.](media/mobile-app-ui.png)      |

Para anclar aplicaciones mediante una directiva de configuración de aplicaciones, siga estos pasos:

1. Inicie sesión en el Centro de administración de Teams y acceda a **Aplicaciones de Teams** > **[ Directivas de instalación](https://admin.teams.microsoft.com/policies/app-setup)**.

1. Seleccione **Agregar**.

1. Escriba un nombre y una descripción para la directiva.

1. Opcionalmente, activa **Anclaje de usuario** para permitir que los usuarios anclen aplicaciones y cambien el orden de las aplicaciones ancladas.

1. En **Aplicaciones ancladas**, seleccione **Agregar aplicaciones**.

1. En el panel **Agregar aplicaciones ancladas**, busque las aplicaciones que quiera agregar y, luego, seleccione **Agregar**.

    :::image type="content" source="media/add-pinned-apps-trimmed.png" alt-text="Capturas de pantalla que muestran cómo agregar aplicaciones ancladas en la directiva de configuración de aplicaciones." lightbox="media/add-pinned-apps-large.png":::

1. Seleccione **Agregar**.

1. En la **Barra** de aplicaciones o **Extensiones de mensajería**, organice las aplicaciones en el orden en que quiera que aparezcan en el cliente de Teams.

   :::image type="content" source="media/pin-messaging-extensions.png" alt-text="Captura de pantalla de las aplicaciones ancladas y las extensiones de mensajería ancladas en la directiva de configuración.":::

1. Seleccione **Guardar**.

> [!NOTE]
> En Teams para el ámbito educativo, la aplicación Tareas está anclada de forma predeterminada en la directiva global, aunque no la vea en la directiva global.

> [!NOTE]
> Para el personal de primera línea de su organización, se recomienda usar la experiencia de aplicación de primera línea personalizada. Esta característica ancla las aplicaciones más relevantes en Teams para los usuarios que tienen una [licencia F](https://www.microsoft.com/en-us/microsoft-365/enterprise/frontline). Para obtener más información, consulte [Adaptar las aplicaciones de Teams para los trabajadores de primera línea.](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json).

## <a name="install-apps"></a>Instalar aplicaciones

Con una directiva de configuración de aplicaciones, un administrador puede realizar las siguientes tareas:

* Instalar aplicaciones para los usuarios finales en su entorno personal de Teams.
* Instalar aplicaciones para los usuarios finales como [extensiones de mensajería](/microsoftteams/platform/messaging-extensions/what-are-messaging-extensions).

Los usuarios finales pueden instalar aplicaciones por su cuenta si la [directiva de permisos](teams-app-permission-policies.md) de la aplicación les permite instalarla y el administrador de Teams permite la aplicación. Si una aplicación está bloqueada, los usuarios finales pueden [solicitar la aprobación del administrador](user-requests-approve-apps.md).

Para instalar aplicaciones mediante una directiva de configuración de aplicaciones, sigue estos pasos:

1. Inicie sesión en el Centro de administración de Teams y acceda a **Aplicaciones de Teams** > **[ Directivas de instalación](https://admin.teams.microsoft.com/policies/app-setup)**.

1. Seleccione **Agregar**.

1. Proporcione un nombre y una descripción para la directiva.

1. En la sección **Aplicaciones instaladas**, seleccione **Agregar aplicaciones**.

1. En el panel **Agregar aplicaciones instaladas**, busque las aplicaciones que desea instalar para los usuarios. También puede filtrar las aplicaciones por directiva de permisos de aplicaciones.

1. Seleccione **Agregar**.

:::image type="content" source="media/install-apps-in-meeting.png" alt-text="Captura de pantalla de la instalación de aplicaciones a través de la directiva de aplicación.":::

## <a name="manage-app-setup-policies"></a>Administrar directivas de configuración de aplicaciones

Puede administrar directivas de configuración de aplicación en el Centro de administración de Microsoft Teams. Use la directiva global (predeterminada para toda la organización) o crear y asignar directivas personalizadas. Los usuarios finales obtienen la directiva global. Si crea una directiva personalizada, esta invalida la directiva global. El administrador global o el administrador de servicios de Teams puede administrar estas directivas.

Puede editar la configuración en la directiva global para incluir las aplicaciones que desee. Para personalizar Microsoft Teams para distintos grupos de usuarios de la organización, puede crear y asignar una o más directivas personalizadas.

:::image type="content" source="media/app-setup-policies-update.png" alt-text="Captura de pantalla que muestra la página de directivas de configuración de la aplicación con opciones para administrar directivas o agregar nuevas directivas.":::

### <a name="edit-an-app-setup-policy"></a>Editar una directiva de configuración de aplicaciones

Puede usar el Centro de administración de Microsoft Teams para editar las directivas, incluidas la directiva global (configuración predeterminada para toda la organización) y las directivas personalizadas que haya creado. Después de editar o asignar una directiva, los cambios pueden tardar unas horas en tener efecto.

1. Inicie sesión en el Centro de administración de Teams y acceda a **Aplicaciones de Teams** > **[ Directivas de instalación](https://admin.teams.microsoft.com/policies/app-setup)**.

1. Elija la directiva que desea editar y, a continuación, seleccione **Editar**.

1. Realice los cambios que desee.

1. Seleccione **Guardar**.

### <a name="assign-a-custom-policy-in-app-setup-policy-to-users-and-groups"></a>Asignar una directiva personalizada en la directiva de configuración de aplicaciones a usuarios y grupos

Para saber cómo asignar directivas a los usuarios finales y grupos, consulte [Cómo asignar directivas a usuarios y grupos](assign-policies-users-and-groups.md).

## <a name="considerations-and-limitations"></a>Consideraciones y limitaciones

* No se pueden instalar aplicaciones personalizadas con pestañas configurables mediante directivas de configuración de aplicaciones.

* Los usuarios finales no pueden desinstalar una aplicación instalada por un administrador.

* Los usuarios finales pueden desanclar una aplicación anclada a través de la directiva de configuración de la aplicación si se permite anclar al usuario en la directiva.

* Los usuarios pueden cambiar el orden de las aplicaciones ancladas en los clientes móviles y de escritorio de Teams si la opción de anclaje del usuario está activada. Los usuarios no pueden cambiar el orden de sus aplicaciones ancladas en los clientes web de Teams.

* Los anclajes del administrador siempre tienen prioridad. Si la opción Anclaje de usuario está activada, las aplicaciones ancladas por los usuarios se muestran debajo de las aplicaciones ancladas por los administradores. Si la opción Anclaje de usuario está desactivada, los usuarios perderán los pin existentes y solo las aplicaciones ancladas por los administradores estarán disponibles en la barra de la aplicación.

* La configuración de anclaje de usuario está disponible en el Centro de administración de Teams en entornos de Microsoft 365 Government Community Cloud (GCC) (GCC, GCC High y DoD), pero no tiene ningún efecto.

* En Teams para el ámbito educativo, la aplicación Tareas está anclada de forma predeterminada en la directiva global, aunque no la vea en la directiva global.

* No hay ningún límite en el número máximo de aplicaciones ancladas que puede agregar a una directiva. Sin embargo, al menos dos aplicaciones deben estar ancladas a los clientes móviles de Teams (iOS y Android). Si una directiva tiene menos de dos aplicaciones, los clientes móviles no reflejarán la configuración de directiva y, en su lugar, seguirán usando la configuración existente.

* Después de editar o asignar una directiva, los cambios pueden tardar unas horas en tener efecto.

* No todas las aplicaciones se pueden anclar a Teams a través de una directiva de configuración de aplicaciones. Es posible que algunas aplicaciones no admitan esta funcionalidad. Para buscar aplicaciones que se puedan anclar, busque la aplicación en el panel **Agregar aplicaciones ancladas**. Las pestañas que tienen un ámbito personal (pestañas estáticas) y los bots se pueden anclar al cliente de escritorio de Teams, y estas aplicaciones están disponibles en el panel **Agregar aplicaciones ancladas**. Mientras que la tienda de aplicaciones de Teams enumera todas las aplicaciones de Teams. El panel **Agregar aplicaciones ancladas** incluye solo las aplicaciones que se pueden anclar a Teams a través de una directiva.

* En Teams para Educación, la aplicación Llamadas no está disponible. Al crear una nueva directiva personalizada en la directiva de configuración de aplicaciones, la aplicación Llamadas se muestra en la lista de aplicaciones. Sin embargo, la aplicación no está anclada en los clientes de Teams y los usuarios de Teams para el ámbito educativo no verán la aplicación Llamadas en Teams.

## <a name="related-articles"></a>Artículos relacionados

* [Configurar la administración para aplicaciones en Teams](admin-settings.md)
* [Asignar directivas a los usuarios finales en Teams](assign-policies-users-and-groups.md)
