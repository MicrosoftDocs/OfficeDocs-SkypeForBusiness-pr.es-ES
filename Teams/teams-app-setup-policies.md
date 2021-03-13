---
title: Administrar directivas de configuración de aplicación en Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: rarang
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo usar y administrar directivas de configuración de aplicaciones en Microsoft Teams para los usuarios de su organización.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: 94e33421043b0cad195489d78e2eb96c95bb222e
ms.sourcegitcommit: da2a70a9b5e05d0fd7ecc150b451f5805667514c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2021
ms.locfileid: "50756186"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>Administrar directivas de configuración de aplicación en Microsoft Teams

Como administrador, puede usar directivas de configuración de aplicaciones para realizar las siguientes tareas:

- Personalice Teams para destacar las aplicaciones más importantes para sus usuarios. Elige las aplicaciones para anclar y establecer el orden en que aparecen. Las aplicaciones ancladas le permiten mostrar las aplicaciones que necesitan los usuarios de su organización, incluidas las aplicaciones creadas por terceros o por desarrolladores de su organización.
- Controle si los usuarios pueden anclar aplicaciones a Teams.
- Instale aplicaciones en nombre de los usuarios. Al iniciar Teams, puede elegir qué aplicaciones están instaladas de forma predeterminada para los usuarios. Tenga en cuenta que los usuarios [](teams-app-permission-policies.md) aún pueden instalar aplicaciones si la directiva de permisos de la aplicación que se les ha asignado lo permite.

> [!Note]
> Para las aplicaciones instaladas por los administradores, los usuarios no pueden desinstalar esas aplicaciones.

Las aplicaciones se anclan a la barra de aplicaciones, que es la barra del lado del cliente de escritorio de Teams y en la parte inferior de los clientes móviles de Teams (iOS y Android).

|Cliente de escritorio de Teams  |Cliente móvil de Teams |
|---------|---------|
|![El cliente de escritorio de Teams](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![El cliente móvil de Teams](media/mobile-app-ui.png)      |

Para ver las aplicaciones instaladas por los administradores, en la barra de aplicaciones, los usuarios seleccionan **... Más aplicaciones en** los clientes web y de escritorio de Teams y deslice el dedo hacia arriba en los clientes móviles.

Puede administrar directivas de configuración de aplicaciones en el Centro de administración de Microsoft Teams. Use la directiva global (predeterminada para toda la organización) o cree y asigne directivas personalizadas.  Los usuarios de su organización obtendrán automáticamente la directiva global, a menos que cree y asigne una directiva personalizada. Debe ser un administrador global o un administrador de servicio de Teams para administrar estas directivas.

Edita la configuración de la directiva global para incluir las aplicaciones que desee. Para personalizar Teams para diferentes grupos de usuarios de su organización, cree y asigne una o más directivas personalizadas.

![la página Directivas de configuración de aplicaciones](media/app-setup-policies.png)

> [!NOTE]
> Si tiene Teams para el ámbito educativo, es importante saber que la aplicación Asignaciones está anclada de forma predeterminada en la directiva global aunque actualmente no la vea en la directiva global. Será la cuarta aplicación de la lista de aplicaciones ancladas en clientes de Teams.

## <a name="create-a-custom-app-setup-policy"></a>Crear una directiva de configuración de aplicaciones personalizada

Puede usar el Centro de administración de Microsoft Teams para crear una directiva personalizada.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a Directivas de configuración **de aplicaciones**  >  **de** Teams.

2. Seleccione **Agregar**.

   ![página Agregar directivas de configuración de aplicaciones](media/app-setup-policies-add.png)

3. Escriba un nombre y una descripción para la directiva.

4. Activa o desactiva **Cargar** aplicaciones personalizadas, dependiendo de si quieres permitir que los usuarios carguen aplicaciones personalizadas en Teams. No puede cambiar esta configuración si Permitir aplicaciones **de terceros** está desactivada en la configuración de la aplicación para toda [la organización.](manage-apps.md#manage-org-wide-app-settings)

5. Activa o desactiva **Permitir** anclación de usuario, dependiendo de si quieres permitir que los usuarios personalicen su barra de aplicaciones anclando aplicaciones a ella.

   > [!NOTE]
   > La **configuración** Permitir anclación de usuario está disponible en el Centro de administración de Teams en entornos de Microsoft 365 Government Community Cloud (GCC) (GCC, GCC High y DoD), pero actualmente no tiene ningún efecto.

6. Para instalar aplicaciones para los usuarios, realice las siguientes tareas:

    1. En **Aplicaciones instaladas,** seleccione **Agregar aplicaciones.**

    2. En el **panel Agregar aplicaciones instaladas,** busque las aplicaciones que desea instalar automáticamente para los usuarios al iniciar Teams. También puede filtrar aplicaciones por directiva de permisos de aplicación. Cuando haya elegido la lista de aplicaciones, seleccione **Agregar**.

       ![el panel Agregar aplicaciones instaladas](media/app-setup-policies-add-installed-apps.png)

7. Para anclar aplicaciones, siga estos pasos:

    1. En **Aplicaciones ancladas,** selecciona **Agregar aplicaciones.**

    2. En el **panel Agregar aplicaciones** ancladas, busque las aplicaciones que desea agregar y, a continuación, seleccione **Agregar**. También puede filtrar aplicaciones por directiva de permisos de aplicación. Cuando haya elegido la lista de aplicaciones para anclar, seleccione **Agregar**.

       ![el panel Agregar aplicaciones ancladas](media/app-setup-policies-add-apps.png)

    3. Organice las aplicaciones en el orden en que quiera que aparezcan en Teams y, a continuación, seleccione **Guardar.**

       ![la sección Aplicaciones ancladas](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a>Editar una directiva de configuración de aplicaciones

Puede usar el Centro de administración de Microsoft Teams para editar una directiva, incluida la directiva global (predeterminada para toda la organización) y las directivas personalizadas que cree.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a Directivas de configuración **de aplicaciones**  >  **de** Teams.

2. Haga clic a la izquierda del nombre de la directiva para seleccionarla y, luego, seleccione **Editar**.

3. A partir de aquí, realice los cambios que desee.

4. Seleccione **Guardar**.

## <a name="assign-a-custom-app-setup-policy-to-users"></a>Asignar una directiva de configuración de aplicación personalizada a los usuarios

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a>Preguntas más frecuentes

### <a name="working-with-app-setup-policies"></a>Trabajar con directivas de configuración de aplicaciones

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a>Qué directivas de configuración de aplicaciones integradas se incluyen en el Centro de administración de Microsoft Teams

- **Global (predeterminado para toda** la organización): esta directiva predeterminada se aplica a todos los usuarios de su organización a menos que asigne otra directiva. Edite la directiva global para anclar aplicaciones que sean más importantes para los usuarios.

- **FrontlineWorker:** esta directiva es para trabajadores de frontline. Puede asignarlo a Trabajadores de frontline de su organización. Es importante saber que, al igual que las directivas personalizadas que cree, tiene que asignar la directiva a los usuarios para que la configuración esté activa. Para obtener más información, vaya a la sección Asignar una directiva de configuración [de aplicación personalizada a](#assign-a-custom-app-setup-policy-to-users) los usuarios de este artículo.

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>¿Por qué no puedo encontrar una aplicación en el panel Agregar aplicaciones ancladas?

No todas las aplicaciones se pueden anclar a Teams a través de una directiva de configuración de aplicaciones. Es posible que algunas aplicaciones no admitan esta funcionalidad. Para buscar aplicaciones que se pueden anclar, busque la aplicación en el panel Agregar aplicaciones **ancladas.** Las pestañas que tienen un ámbito personal (pestañas estáticas) y bots se pueden anclar al cliente de escritorio de Teams y estas aplicaciones están disponibles en el panel Agregar aplicaciones **ancladas.**

Tenga en cuenta que la tienda de aplicaciones de Teams enumera todas las aplicaciones de Teams. El **panel Agregar aplicaciones ancladas** solo incluye las aplicaciones que se pueden anclar a Teams a través de una directiva.

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>Soy administrador de Teams for Education. ¿Qué necesito saber sobre las directivas de configuración de aplicaciones en Teams para el sector educativo?

La aplicación Llamadas no está disponible en Teams para el sector educativo. Al crear una nueva directiva de configuración de aplicaciones personalizada, la aplicación Llamadas se muestra en la lista de aplicaciones. Sin embargo, la aplicación no está anclada a clientes de Teams y los usuarios de Teams para el sector educativo no verán la aplicación Llamadas en Teams.

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a>Cuántas aplicaciones ancladas se pueden agregar a una directiva

Un mínimo de dos aplicaciones deben estar ancladas a los clientes móviles de Teams (iOS y Android). Si una directiva tiene menos de dos aplicaciones, los clientes móviles no reflejarán la configuración de directiva y, en su lugar, seguirán usando la configuración existente.

No hay ningún límite en el número de aplicaciones ancladas que puede agregar a una directiva.

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a>¿Cuánto tiempo se necesita para que los cambios de directiva entren en vigor?

Después de editar o asignar una directiva, los cambios pueden tardar unas horas en tener efecto.

### <a name="user-experience"></a>Experiencia de usuario

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a>Cómo pueden los usuarios ver todas sus aplicaciones ancladas en Teams

Para ver todas las aplicaciones ancladas para un usuario, es posible que los usuarios tengan que hacer lo siguiente en función del número de aplicaciones instaladas y del tamaño de la ventana del cliente de Teams.

|Cliente de escritorio de Teams |Cliente móvil de Teams |
|---------|---------|
|En la barra de aplicaciones del lado de Teams, selecciona **... Más aplicaciones**.| En la barra de aplicaciones cerca de la parte inferior de Teams, deslice el dedo hacia arriba.|
|![Más aplicaciones en el cliente de escritorio de Teams](media/app-setup-policies-desktop-more-apps.png)<br>   |![más aplicaciones en el cliente móvil de Teams](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a>¿Qué necesito saber sobre la experiencia móvil de Teams?

Actualmente, los clientes móviles de Teams (iOS y Android) no admiten aplicaciones personales con pestañas estáticas. Según las aplicaciones establecidas en la directiva, es posible que las aplicaciones ancladas al cliente de escritorio de Teams no aparezcan en los clientes móviles de Teams. Los bots personales seguirán apareciendo en chat en clientes móviles.

Con los clientes móviles de Teams, los usuarios verán las aplicaciones principales de Teams, como Actividad, Chat y Teams, y puede anclar algunas aplicaciones de primer nivel de Microsoft, como Turnos.

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a>¿Pueden los usuarios cambiar el orden de las aplicaciones ancladas a través de una directiva?

Los usuarios pueden cambiar el orden de sus aplicaciones ancladas en clientes móviles y de escritorio de Teams si la **opción** Permitir anclar usuarios está activada. Los usuarios no pueden cambiar el orden de sus aplicaciones ancladas en clientes web de Teams.

#### <a name="does-user-pinning-take-precedence"></a>¿Tiene prioridad la anclación de usuario?

Si la directiva de configuración de la aplicación asignada al usuario se cambia para bloquear la fijación de aplicaciones de usuario, Teams quita las aplicaciones ancladas a la barra de aplicaciones. Si la directiva se cambia para permitir la fijación de aplicaciones de usuario, los usuarios deben volver a anclar sus aplicaciones ancladas anteriormente.

### <a name="custom-teams-apps"></a>Aplicaciones personalizadas de Teams

Mi organización creó una aplicación personalizada de Teams y la publicó, ya sea en AppSource o en el catálogo de aplicaciones de inquilino, pero el icono de la aplicación no se muestra como se esperaba cuando la aplicación está anclada a la barra de aplicaciones en Teams. ¿Cómo puedo corregirlo?

Asegúrese de que sigue las directrices del logotipo antes de enviar la aplicación. Para obtener más información, vea [Envío de lista de comprobación del panel de vendedores.](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)

## <a name="related-topics"></a>Temas relacionados

[Configurar la administración para aplicaciones en Teams](admin-settings.md)

[Asignar directivas a los usuarios en Teams](assign-policies.md)
