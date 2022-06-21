---
title: Administrar directivas de configuración de aplicación en Microsoft Teams
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.reviewer: rarang
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
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
ms.openlocfilehash: 58a2b8730c4f3d02746aeb0bb3887bcd63d44918
ms.sourcegitcommit: 9946c6c1faa78617ccd7bdf115457090ebce5619
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/21/2022
ms.locfileid: "66190481"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>Administrar directivas de configuración de aplicación en Microsoft Teams

Como administrador, puede usar las directivas de configuración de aplicaciones para instalar y anclar aplicaciones y permitir que los usuarios carguen aplicaciones personalizadas. Anclar ayuda a promover la adopción de aplicaciones relevantes en su organización.

* **Anclar aplicaciones:** Las directivas de configuración de aplicaciones le permiten elegir las aplicaciones que anclar, establecer el orden en que se muestran las aplicaciones para los usuarios en la barra de la aplicación Teams o en el área de redacción de mensajes. Los administradores también pueden controlar si los usuarios finales pueden anclar sus propias aplicaciones o no. Consulta [Anclar aplicaciones](#pin-apps).
* **Instalar aplicaciones:** Las directivas de configuración de aplicaciones le permiten instalar aplicaciones en nombre de los usuarios al iniciar Teams y durante las reuniones. Para obtener más información, consulta [Instalar aplicaciones](#install-apps).
* **Upload aplicaciones personalizadas: las directivas** de configuración de aplicaciones le permiten a los usuarios cargar aplicaciones personalizadas a Teams. Para obtener más información, consulta [Upload aplicaciones personalizadas](#upload-custom-apps).

## <a name="pin-apps"></a>Anclar aplicaciones

Anclar aplicaciones te permite resaltar las aplicaciones que más necesitan los usuarios de tu organización. Anclar funciona para aplicaciones proporcionadas por Microsoft, por empresas de ISV y por desarrolladores dentro de su organización. Anclar una aplicación a través de una directiva de configuración de aplicaciones también la instala. Con una directiva de configuración de aplicaciones, puede realizar las siguientes tareas:

* Personalice Teams para destacar las aplicaciones más importantes para sus usuarios. Puedes elegir las aplicaciones que quieres anclar y establecer el orden en que aparecen.
* Controlar si los usuarios pueden anclar aplicaciones o no.

Las aplicaciones se anclan en la barra de aplicaciones del lado izquierdo del cliente de escritorio de Teams y en la parte inferior de los clientes móviles de Teams.

|Cliente de escritorio de Teams  |Cliente móvil de Teams |
|---------|---------|
|![Barra de aplicaciones en Teams cliente de escritorio.](media/app-setup-policies-desktop-app-bar.png).  |   ![Barra de aplicaciones en Teams cliente móvil.](media/mobile-app-ui.png)      |

Las extensiones de mensajería están disponibles en la parte inferior del área de redacción de mensajes.

Para crear una directiva de configuración de aplicaciones para anclar aplicaciones, sigue estos pasos:

1. Inicie sesión en [Microsoft Teams centro de administración](https://admin.teams.microsoft.com).

1. En el panel izquierdo, ve a **Teams directivas****de configuración de** aplicaciones > .

1. Seleccione **Agregar**.

1. Escriba un nombre y una descripción para la directiva.

1. Activar **anclaje de usuario**.

   > [!NOTE]
   > La configuración **anclaje de usuario** está disponible en el centro de administración de Teams en entornos de Microsoft 365 Government Community Cloud (GCC) (GCC, GCC Alto y DoD), pero actualmente no tiene ningún efecto.

1. En **Aplicaciones ancladas**, selecciona **Agregar aplicaciones**.

1. En el panel **Agregar aplicaciones ancladas** , busca las aplicaciones que quieras agregar y, a continuación, selecciona **Agregar**. También puede filtrar aplicaciones por directiva de permisos de aplicaciones.

1. Seleccione **Agregar**.

1. En la **Barra de** aplicaciones o **Extensiones** de mensajería, organiza las aplicaciones en el orden en que quieras que aparezcan en Teams.

   :::image type="content" source="media/pin-messaging-extensions.png" alt-text="la sección de aplicaciones ancladas"border="true":::

1. Seleccione **Guardar**.

> [!NOTE]
> En Teams para Educación, la aplicación Tareas está anclada de forma predeterminada en la directiva global, aunque no se muestre en la directiva global.

> [!NOTE]
> Para los trabajadores de primera línea de su organización, le recomendamos que use la experiencia de aplicación de primera línea personalizada. Esta característica ancla las aplicaciones más relevantes de Teams para los usuarios que tienen una [licencia F](https://www.microsoft.com/en-us/microsoft-365/enterprise/frontline?rtc=1#office-SKUChooser-0dbn8nt). Para obtener más información, consulte [Personalizar aplicaciones de Teams para los trabajadores de primera línea](pin-teams-apps-based-on-license.md).

## <a name="install-apps"></a>Instalar aplicaciones

Con una directiva de configuración de la aplicación, un administrador puede realizar las siguientes tareas:

* Instala aplicaciones para los usuarios finales en su entorno de Teams personal, de forma predeterminada.
* Instala aplicaciones para los usuarios finales como [extensiones de mensajería](/microsoftteams/platform/messaging-extensions/what-are-messaging-extensions).
* Instale aplicaciones en reuniones para los organizadores de reuniones.

Los usuarios finales pueden instalar aplicaciones por su cuenta si la [directiva de permisos](teams-app-permission-policies.md) de las aplicaciones lo permite.

Para crear una directiva de configuración de aplicaciones para instalar aplicaciones, sigue estos pasos:

1. Inicie sesión en Teams centro de administración y acceda a las directivas **de configuración** **de aplicaciones** >  de Teams.

2. Seleccione **Agregar**.

3. Proporcione un nombre y una descripción para la directiva.

4. En **Aplicaciones instaladas**, selecciona **Agregar aplicaciones**.

5. En el panel **Agregar aplicaciones instaladas** , busca para los usuarios las aplicaciones que quieras instalar. También puede filtrar aplicaciones por directiva de permisos de aplicaciones.

6. Seleccione **Agregar**.

![Instalar directiva de aplicación.](media/install-apps-in-meeting.png)

> [!IMPORTANT]
> Los usuarios no pueden desinstalar aplicaciones instaladas por los administradores.

## <a name="upload-custom-apps"></a>Upload aplicaciones personalizadas

Para crear una directiva personalizada que permita a los usuarios cargar aplicaciones personalizadas, siga estos pasos:

1. Inicie sesión en Teams centro de administración y acceda a las directivas **de configuración** **de aplicaciones** >  de Teams.

2. Seleccione **Agregar**.

3. Proporcione un nombre y una descripción para la directiva.

4. Activa o desactiva **Upload aplicaciones personalizadas**.

> [!NOTE]
> Para cambiar esta configuración, la configuración de aplicaciones de [toda la organización](manage-apps.md#manage-org-wide-app-settings) de tu inquilino debe permitir **las aplicaciones de terceros**.

## <a name="manage-app-setup-policies"></a>Administrar directivas de configuración de aplicaciones

Puede administrar las directivas de configuración de aplicaciones en el Microsoft Teams centro de administración. Use la directiva global (predeterminada para toda la organización) o cree y asigne directivas personalizadas. Los usuarios finales obtienen la directiva global. Si crea una directiva personalizada, esta invalida la directiva global. El administrador global o Teams administrador del servicio puede administrar estas directivas.

Edita la configuración de la directiva global para incluir las aplicaciones que quieras. Para personalizar Teams para diferentes grupos de usuarios de la organización, cree y asigne una o más directivas personalizadas.

![Página Directivas de configuración de aplicaciones para administrar directivas o agregar nuevas directivas.](media/app-setup-policies-update.png)

### <a name="edit-an-app-setup-policy"></a>Editar una directiva de configuración de aplicaciones

Puede usar el centro de administración de Microsoft Teams para editar una directiva, incluida la directiva global (predeterminada para toda la organización) y las directivas personalizadas que cree.

1. En el panel de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **Aplicaciones de Teams** > **Directivas de configuración**.

2. Elige la directiva que quieras editar y, a continuación, selecciona **Editar**.

3. Realice los cambios que desee.

4. Seleccione **Guardar**.

### <a name="assign-a-custom-app-setup-policy-to-users-and-groups"></a>Asignar una directiva de configuración de aplicación personalizada a usuarios y grupos

Para obtener más información sobre cómo asignar directivas a usuarios y grupos, vea [Asignar directivas a usuarios y grupos](assign-policies-users-and-groups.md).

## <a name="faqs"></a>Preguntas frecuentes

<!--- TBD: Incorporate these pointers in the content itself.
--->

### <a name="working-with-app-setup-policies"></a>Trabajar con directivas de configuración de aplicaciones

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a>Qué directivas de configuración de aplicaciones integradas se incluyen en el centro de administración de Microsoft Teams

* **Global (valor predeterminado para toda** la organización): esta directiva predeterminada se aplica a todos los usuarios de la organización a menos que asigne otra directiva. Edita la directiva global para anclar las aplicaciones más importantes para los usuarios.

* **FrontlineWorker**: Esta directiva es para los Frontline Workers. Puede asignarlo a los Frontline Workers de su organización. Es importante saber que, al igual que las directivas personalizadas que cree, tiene que asignar la directiva a los usuarios para que la configuración esté activa. Para obtener más información, vaya a la sección [Asignar una directiva de configuración de aplicación personalizada a los usuarios](#assign-a-custom-app-setup-policy-to-users-and-groups) de este artículo.

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>¿Por qué no encuentro una aplicación en el panel Agregar aplicaciones ancladas?

No todas las aplicaciones se pueden anclar a Teams a través de una directiva de configuración de aplicaciones. Es posible que algunas aplicaciones no admitan esta funcionalidad. Para buscar aplicaciones que se pueden anclar, busca la aplicación en el panel **Agregar aplicaciones ancladas** . Las pestañas que tienen un ámbito personal (pestañas estáticas) y los bots se pueden anclar al Teams cliente de escritorio y estas aplicaciones están disponibles en el panel **Agregar aplicaciones ancladas**.

Ten en cuenta que la tienda de aplicaciones de Teams enumera todas las aplicaciones Teams. El panel **Agregar aplicaciones ancladas** incluye solo las aplicaciones que se pueden anclar a Teams a través de una directiva.

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>Soy administrador de Teams para Educación. ¿Qué necesito saber sobre las directivas de configuración de aplicaciones en Teams para Educación

La aplicación Llamadas no está disponible en Teams para Educación. Al crear una nueva directiva de configuración de aplicaciones personalizada, la aplicación Llamadas se muestra en la lista de aplicaciones. Sin embargo, la aplicación no está anclada a Teams clientes y Teams para Educación los usuarios no verán la aplicación Llamadas en Teams.

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a>Cuántas aplicaciones ancladas se pueden agregar a una directiva

Es necesario anclar un mínimo de dos aplicaciones a los clientes móviles de Teams (iOS y Android). Si una directiva tiene menos de dos aplicaciones, los clientes móviles no reflejarán la configuración de la directiva y, en su lugar, seguirán usando la configuración existente.

No hay límite en el número de aplicaciones ancladas que puedes agregar a una directiva.

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a>¿Cuánto tardan en surtir efecto los cambios de directiva?

Después de editar o asignar una directiva, los cambios pueden tardar unas horas en tener efecto.

### <a name="user-experience"></a>Experiencia de usuario

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a>¿Cómo pueden ver los usuarios todas sus aplicaciones ancladas en Teams

Para ver todas las aplicaciones ancladas para un usuario, es posible que los usuarios tengan que hacer lo siguiente según el número de aplicaciones instaladas y el tamaño de su ventana de cliente de Teams.

|Cliente de escritorio de Teams |Cliente móvil de Teams |
|---------|---------|
|En la barra de aplicaciones del lado de Teams, selecciona **... Más aplicaciones**.| En la barra de aplicaciones cerca de la parte inferior de Teams, deslice el dedo hacia arriba.|
|![Más aplicaciones en el cliente de escritorio de Teams.](media/app-setup-policies-desktop-more-apps.png)   |![más aplicaciones en el cliente móvil de Teams](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a>Qué necesito saber sobre la experiencia móvil Teams

Los clientes móviles Teams (iOS y Android) admiten aplicaciones personales con pestañas estáticas. Las aplicaciones ancladas al cliente de escritorio Teams aparecerán en el Teams clientes móviles. Los bots personales aparecerán en Chat en clientes móviles.

Las aplicaciones de terceros (que se pueden descargar desde Teams Store) deben aprobarse antes de mostrarse en dispositivos móviles. Si un administrador ancla una aplicación, que Microsoft para móviles no ha aprobado, se mostrará en el escritorio de Teams, pero no se mostrará en el dispositivo móvil. Consulte [Clientes móviles](/microsoftteams/platform/tabs/what-are-tabs#mobile-clients) para obtener más información.

Con los clientes móviles Teams, los usuarios verán las aplicaciones Teams principales, como Actividad, Chat y Teams, y puede anclar algunas aplicaciones de origen de Microsoft, como Turnos.

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a>¿Los usuarios pueden cambiar el orden de las aplicaciones ancladas a través de una directiva?

Los usuarios pueden cambiar el orden de las aplicaciones ancladas en Teams clientes móviles y de escritorio si la opción **Anclaje de usuario** está activada. Los usuarios no pueden cambiar el orden de las aplicaciones ancladas en Teams clientes web.

#### <a name="does-user-pinning-take-precedence"></a>¿Tiene prioridad el anclaje de usuario?

Administración anclas siempre tienen prioridad. Si la opción **Anclaje de usuario** está activada, los usuarios conservarán sus aplicaciones ancladas debajo de las aplicaciones ancladas por el administrador. Si la opción **Anclaje del usuario** está desactivada, los usuarios perderán sus anclas preexisterias y solo las aplicaciones ancladas por el administrador estarán presentes en la barra de aplicaciones.

### <a name="custom-teams-apps"></a>Aplicaciones de Teams personalizadas

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a>Mi organización creó una aplicación de Teams personalizada y la publicó, ya sea en AppSource o en el catálogo de aplicaciones del inquilino, pero el icono de la aplicación no se muestra según lo esperado cuando la aplicación está anclada a la barra de la aplicación en Teams. Cómo arreglarlo?

Asegúrate de seguir las directrices del logotipo antes de enviar la aplicación. Para obtener más información, consulte [Lista de comprobación para envío de panel del vendedor](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).

## <a name="see-also"></a>Vea también

* [Configurar la administración para aplicaciones en Teams](admin-settings.md)
* [Asignar directivas a usuarios finales en Teams](assign-policies-users-and-groups.md)
