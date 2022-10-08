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
ms.localizationpriority: medium
search.appverid: MET150
description: Obtenga información sobre cómo crear, editar y administrar directivas de configuración de aplicaciones para anclar aplicaciones, instalar aplicaciones y permitir que los usuarios carguen aplicaciones personalizadas.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: dc84bc7be43182194af3a072edb875a6a257a9d5
ms.sourcegitcommit: 6e85f3f70f8488ab827ac352c0f324b6dfd4b856
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2022
ms.locfileid: "68377338"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>Administrar directivas de configuración de aplicación en Microsoft Teams

Como administrador, puede usar directivas de configuración de aplicaciones para instalar y anclar aplicaciones, y permitir que los usuarios carguen aplicaciones personalizadas. El anclaje ayuda a promover la adopción de aplicaciones relevantes en su organización.

* **Anclar aplicaciones:** Las directivas de configuración de aplicaciones le permiten elegir las aplicaciones que desea anclar, establecer el orden en que se muestran las aplicaciones para los usuarios en la barra de aplicaciones de Teams o en el área de redacción de mensajes. Los administradores también pueden controlar si los usuarios finales pueden anclar sus propias aplicaciones o no. Consulte [Anclar aplicaciones](#pin-apps).
* **Instalar las aplicaciones:** Las directivas de configuración de aplicaciones le permiten instalar las aplicaciones permitidas en nombre de los usuarios cuando inician Teams y durante las reuniones. Para obtener más información, consulte [Instalación de aplicaciones](#install-apps).
* **Cargar aplicaciones personalizadas:** Las directivas de configuración de aplicaciones le permiten a los usuarios cargar aplicaciones personalizadas en Teams. Para obtener más información, consulte [Cargar aplicaciones personalizadas](teams-custom-app-policies-and-settings.md).

Las siguientes directivas de configuración de aplicaciones integradas están disponibles en el Centro de administración de Microsoft Teams de forma predeterminada:

* **Global (valor predeterminado para toda la organización)**: esta directiva predeterminada se aplica a todos los usuarios de la organización a menos que asigne otra directiva. Edite la directiva global para anclar las aplicaciones más importantes para los usuarios.

* **FirstlineWorker**: esta directiva es para personal de primera línea. No se puede personalizar la directiva. Puede asignarla a los trabajadores de primera línea de su organización.

## <a name="pin-apps"></a>Anclar aplicaciones

El anclaje de aplicaciones le permite resaltar las aplicaciones que más necesitan los usuarios de su organización. Anclar funciona para todos los tipos de aplicaciones en Teams: aplicaciones principales, aplicaciones proporcionadas por Microsoft, aplicaciones de terceros y personalizadas desarrolladas dentro de su organización. Al anclar una aplicación a través de una directiva de configuración de la aplicación, también se instala, si la aplicación está permitida para el usuario. Con una directiva de configuración de aplicaciones, puede realizar las siguientes tareas:

* Personalizar Microsoft Teams para que los usuarios finales destaquen las aplicaciones más importantes para ellos. Elegir las aplicaciones que se quieren anclar y el orden en que se muestran las aplicaciones.
* Controlar si los usuarios pueden o no anclar aplicaciones.

La aplicaciones se anclan a la barra de aplicaciones situada en el lateral izquierdo del cliente de escritorio de Teams y en la parte inferior de los clientes móviles.

|Cliente de escritorio de Teams  |Cliente móvil de Teams |
|---------|---------|
|![Captura de pantalla que muestra la barra de la aplicación en el cliente de escritorio de Teams.](media/app-setup-policies-desktop-app-bar.png).  |   ![Captura de pantalla que muestra la barra de la aplicación en el cliente móvil de Teams.](media/mobile-app-ui.png)      |

Las extensiones de mensajería están disponibles en la parte inferior del área de redacción de mensajes.

Para anclar aplicaciones mediante una directiva de configuración de aplicaciones, siga estos pasos:

1. Inicie sesión en el Centro de administración de Teams y acceda a **Aplicaciones de Teams** > **[ Directivas de instalación](https://admin.teams.microsoft.com/policies/app-setup)**.

1. Seleccione **Agregar**.

1. Escriba un nombre y una descripción para la directiva.

1. Active **Aplicaciones ancladas por el usuario**.

   > [!NOTE]
   > La configuración **Aplicaciones ancladas por el usuario** está disponible en el Centro de administración de Teams en entornos de Government Community Cloud (GCC) de Microsoft 365 (GCC, GCC High y DoD), pero no tiene ningún efecto.

1. En **Aplicaciones ancladas**, seleccione **Agregar aplicaciones**.

1. En el panel **Agregar aplicaciones ancladas**, busque las aplicaciones que quiera agregar y, luego, seleccione **Agregar**. También puede filtrar las aplicaciones por directiva de permisos de aplicaciones.

1. Seleccione **Agregar**.

1. En **Barra de aplicaciones** o **Extensiones de mensajería**, organice las aplicaciones en el orden en que desea que aparezcan en Teams.

   :::image type="content" source="media/pin-messaging-extensions.png" alt-text="Un recorte de pantalla de las aplicaciones ancladas y las extensiones de mensajería ancladas en la directiva de configuración.":::

1. Seleccione **Guardar**.

> [!NOTE]
> En Teams para el ámbito educativo, la aplicación Tareas está anclada de forma predeterminada en la directiva global, aunque no la vea en la directiva global.

> [!NOTE]
> Para el personal de primera línea de su organización, se recomienda usar la experiencia de aplicación de primera línea personalizada. Esta característica ancla las aplicaciones más relevantes en Teams para los usuarios que tienen una [licencia F](https://www.microsoft.com/en-us/microsoft-365/enterprise/frontline?rtc=1#office-SKUChooser-0dbn8nt). Para obtener más información, consulte [Adaptar las aplicaciones de Teams para los trabajadores de primera línea.](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json).

## <a name="install-apps"></a>Instalar aplicaciones

Con una directiva de configuración de aplicaciones, un administrador puede realizar las siguientes tareas:

* Instalar aplicaciones para los usuarios finales en su entorno personal de Teams.
* Instalar aplicaciones para los usuarios finales como [extensiones de mensajería](/microsoftteams/platform/messaging-extensions/what-are-messaging-extensions).

Los usuarios finales pueden instalar aplicaciones por su cuenta si la [directiva de permisos](teams-app-permission-policies.md) de la aplicación les permite y el administrador de Teams permite la aplicación. En su lugar, si una aplicación está bloqueada para un usuario o para una organización, los usuarios finales pueden [solicitar la aprobación del administrador](user-requests-approve-apps.md).

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

### <a name="assign-a-custom-app-setup-policy-to-users-and-groups"></a>Asignar a los usuarios y los grupos una directiva de configuración de aplicaciones personalizada

Para saber cómo asignar directivas a los usuarios finales y grupos, consulte [Cómo asignar directivas a usuarios y grupos](assign-policies-users-and-groups.md).

## <a name="considerations-and-limitations"></a>Consideraciones y limitaciones

* No se pueden instalar aplicaciones personalizadas con pestañas configurables mediante directivas de configuración de aplicaciones.
* Los usuarios finales no pueden desinstalar una aplicación instalada por un administrador.
* El usuario puede desanclar las aplicaciones que se anclan a través de la directiva de configuración de aplicaciones (si se permite el anclaje de aplicaciones por parte de los usuarios en la directiva de configuración).
* En Teams para el ámbito educativo, la aplicación Tareas está anclada de forma predeterminada en la directiva global, aunque no la vea en la directiva global.
* No hay ningún límite en el número máximo de aplicaciones ancladas que puede agregar a una directiva. Sin embargo, al menos dos aplicaciones deben estar ancladas a los clientes móviles de Teams (iOS y Android). Si una directiva tiene menos de dos aplicaciones, los clientes móviles no reflejarán la configuración de directiva y, en su lugar, seguirán usando la configuración existente.
* Después de editar o asignar una directiva, los cambios pueden tardar unas horas en tener efecto.

## <a name="faqs"></a>Preguntas frecuentes

### <a name="working-with-app-setup-policies"></a>Trabajar con directivas de configuración de aplicaciones

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>¿Por qué no puedo encontrar una aplicación en el panel Agregar aplicaciones ancladas?

No todas las aplicaciones se pueden anclar a Teams a través de una directiva de configuración de aplicaciones. Es posible que algunas aplicaciones no admitan esta funcionalidad. Para buscar aplicaciones que se puedan anclar, busque la aplicación en el panel **Agregar aplicaciones ancladas**. Las pestañas que tienen un ámbito personal (pestañas estáticas) y los bots se pueden anclar al cliente de escritorio de Teams, y estas aplicaciones están disponibles en el panel **Agregar aplicaciones ancladas**.

Tenga en cuenta que la tienda de aplicaciones de Teams enumera todas las aplicaciones de Teams. El panel **Agregar aplicaciones ancladas** incluye solo las aplicaciones que se pueden anclar a Teams a través de una directiva.

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>Soy administrador de Teams para el ámbito educativo. ¿Qué necesito saber sobre las directivas de configuración de aplicaciones en Teams para el ámbito educativo?

La aplicación Llamadas no está disponible en Teams para el ámbito educativo. Al crear una nueva directiva de configuración de aplicaciones personalizada, la aplicación que realiza la llamada se muestra en la lista de aplicaciones. Sin embargo, la aplicación no está anclada en los clientes de Teams y los usuarios de Teams para el ámbito educativo no verán la aplicación Llamadas en Teams.

### <a name="user-experience"></a>Experiencia de usuario

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a>¿Cómo pueden ver los usuarios todas sus aplicaciones ancladas en Teams?

Para ver todas las aplicaciones que están ancladas para un usuario, es posible que los usuarios tengan que hacer lo siguiente según el número de aplicaciones instaladas y el tamaño de la ventana de cliente de Teams.

|Cliente de escritorio de Teams |Cliente móvil de Teams |
|---------|---------|
|En la barra de aplicaciones lateral de Teams, seleccione **... Más aplicaciones**.| En la barra de aplicaciones cerca de la parte inferior de Teams, deslice el dedo hacia arriba.|
|![Captura de pantalla que muestra más aplicaciones ancladas en el cliente de escritorio de Teams.](media/app-setup-policies-desktop-more-apps.png)   |![Captura de pantalla que muestra más aplicaciones ancladas en el cliente móvil de Teams](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a>¿Qué necesito saber sobre la experiencia móvil de Teams?

Los clientes móviles de Teams (iOS y Android) admiten aplicaciones personales con pestañas estáticas. Las aplicaciones ancladas en el cliente de escritorio de Teams aparecerán en los clientes móviles de Teams. Los bots personales aparecerán en Chat en clientes móviles.

Las aplicaciones de terceros (que se pueden descargar desde la Tienda de Teams) deben aprobarse antes de que aparezcan en el móvil. Si un administrador ancla una aplicación que Microsoft para móviles no ha aprobado, se mostrará en el escritorio de Teams, pero no en el móvil. Para obtener más información, consulte [ Clientes móviles](/microsoftteams/platform/tabs/what-are-tabs#mobile-clients).

Con los clientes móviles de Teams, los usuarios verán las principales aplicaciones de Teams, como Actividad, Chat y Teams, y puede anclar algunas de las aplicaciones proporcionadas por Microsoft.

#### <a name="order-of-apps-pinned-through-a-policy"></a>Orden de las aplicaciones ancladas a través de una directiva

Los usuarios pueden cambiar el orden de sus aplicaciones ancladas en los clientes móviles y de escritorio de Teams si la opción **Anclaje de aplicaciones por el usuario** está activada. Los usuarios no pueden cambiar el orden de sus aplicaciones ancladas en los clientes web de Teams.

#### <a name="does-user-pinning-take-precedence"></a>¿Tiene prioridad el anclaje del usuario?

Los anclajes del administrador siempre tienen prioridad. Si la opción **Anclaje de usuario** está activada, las aplicaciones ancladas por los usuarios se muestran debajo de las aplicaciones ancladas por los administradores. Si la opción **Anclaje de usuario** está desactivada, los usuarios perderán los pin existentes y solo las aplicaciones ancladas por los administradores estarán disponibles en la barra de la aplicación.

### <a name="custom-teams-apps"></a>Aplicaciones personalizadas de Teams

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a>Mi organización creó una aplicación personalizada de Teams y la publicó, ya sea en AppSource o en el catálogo de aplicaciones de inquilino, pero el icono de la aplicación no se muestra como debería cuando la aplicación está anclada a la barra de aplicaciones en Teams. ¿Cómo corrijo este error?

Asegúrese de seguir las directrices del logotipo antes de enviar la aplicación. Para obtener más información, consulte [Lista de comprobación para el envío de aplicaciones en el Panel de vendedores](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).

## <a name="related-articles"></a>Artículos relacionados

* [Configurar la administración para aplicaciones en Teams](admin-settings.md)
* [Asignar directivas a los usuarios finales en Teams](assign-policies-users-and-groups.md)
