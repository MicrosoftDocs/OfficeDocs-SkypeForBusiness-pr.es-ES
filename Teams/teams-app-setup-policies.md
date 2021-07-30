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
description: Obtenga información sobre cómo usar y administrar directivas de configuración de aplicaciones Microsoft Teams para los usuarios de su organización.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: bbad8813d9f417643d48a0f1807c2e4c2ccb39cf
ms.sourcegitcommit: 5c59f9bf5a9477607b378c23fa3c8670930dc428
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2021
ms.locfileid: "53646311"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>Administrar directivas de configuración de aplicación en Microsoft Teams

Como administrador, puede usar directivas de configuración de aplicaciones para instalar y anclar aplicaciones para promover las aplicaciones más usadas de su organización y decidir si desea que los usuarios carguen aplicaciones personalizadas a Teams.

- Anclar **aplicaciones:** las directivas de configuración de aplicaciones le permiten elegir aplicaciones para anclar, establecer el orden en que se muestran para los usuarios y controlar si los usuarios pueden anclar o no sus propias aplicaciones a la barra de aplicaciones Teams aplicación. Para obtener más información, vea [Anclar aplicaciones.](#pin-apps)
- **Instalar aplicaciones: las** directivas de configuración de aplicaciones le permiten instalar aplicaciones en nombre de los usuarios al iniciar Teams y durante las reuniones. Para obtener más información, vea [Instalar aplicaciones.](#install-apps)
- **Upload aplicaciones personalizadas: las** directivas de configuración de aplicaciones le permiten a los usuarios cargar aplicaciones personalizadas Teams. Para obtener más información, [vea Upload aplicaciones personalizadas.](#upload-custom-apps)

## <a name="pin-apps"></a>Anclar aplicaciones

Las aplicaciones ancladas le permiten mostrar las aplicaciones que necesitan los usuarios de su organización, incluidas las aplicaciones creadas por terceros o por desarrolladores de su organización.

Con una directiva de configuración de aplicaciones, puede realizar las siguientes tareas:

- Personalice Teams para destacar las aplicaciones más importantes para sus usuarios. Elige las aplicaciones para anclar y establecer el orden en que aparecen.
- Controle si los usuarios pueden anclar aplicaciones a Teams.

Las aplicaciones se anclan a la barra de aplicaciones, que es la barra del lado del cliente de escritorio de Teams y en la parte inferior de los clientes móviles de Teams (iOS y Android).

|Cliente de escritorio de Teams  |Cliente móvil de Teams |
|---------|---------|
|![El Teams de escritorio](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![El Teams móvil](media/mobile-app-ui.png)      |

> [!NOTE]
> Si tiene Teams para Educación, es importante saber que la aplicación Asignaciones está anclada de forma predeterminada en la directiva global aunque actualmente no la vea en la directiva global. Será la cuarta aplicación de la lista de aplicaciones ancladas en Teams clientes.

Para crear una directiva de configuración de aplicaciones para anclar aplicaciones, siga estos pasos:

1. En el panel de navegación izquierdo del Microsoft Teams de administración, vaya a Teams **directivas**  >  **de configuración de aplicaciones.**

2. Seleccione **Agregar**.

3. Escriba un nombre y una descripción para la directiva.

4. Activa o desactiva **Permitir** anclación de usuario, dependiendo de si quieres permitir que los usuarios personalicen su barra de aplicaciones anclando aplicaciones a ella.

   > [!NOTE]
   > La **configuración** Permitir anclación de usuario está disponible en el Centro de administración de Teams en entornos de Microsoft 365 Government Community Cloud (GCC) (GCC, GCC High y DoD), pero actualmente no tiene ningún efecto.

5. En **Aplicaciones ancladas,** selecciona **Agregar aplicaciones.**

6. En el **panel Agregar aplicaciones** ancladas, busque las aplicaciones que desea agregar y, a continuación, seleccione **Agregar**. También puede filtrar aplicaciones por directiva de permisos de aplicación.

7. Seleccione **Agregar**.

8. Organice las aplicaciones en el orden en que desea que aparezcan en Teams.

   ![la sección Aplicaciones ancladas](media/app-setup-policies-new-policy-setup.png)

9. Seleccione **Guardar**.

## <a name="install-apps"></a>Instalar aplicaciones

Puede elegir qué aplicaciones están instaladas de forma predeterminada para los usuarios [](/microsoftteams/platform/messaging-extensions/what-are-messaging-extensions)en su entorno personal de Teams, instalar aplicaciones como extensiones de mensajería y designar las aplicaciones que se instalarán en las reuniones.

Con una directiva de configuración de aplicaciones, puede realizar las siguientes tareas:

- Instalar aplicaciones para usuarios en su entorno Teams personal
- Instalar aplicaciones para usuarios como extensiones de mensajería
- Instalar aplicaciones en reuniones para organizadores de reuniones

> [!NOTE]
> Los usuarios aún pueden instalar aplicaciones si [la](teams-app-permission-policies.md) directiva de permisos de la aplicación que se les ha asignado lo permite.

Para crear una directiva de configuración de aplicaciones para instalar aplicaciones, siga estos pasos:

1. En el panel de navegación izquierdo del Microsoft Teams de administración, vaya a Teams **directivas**  >  **de configuración de aplicaciones.**

2. Seleccione **Agregar**.

3. Escriba un nombre y una descripción para la directiva.

4. En **Aplicaciones instaladas,** seleccione **Agregar aplicaciones.**

5. En el **panel Agregar aplicaciones instaladas,** busque las aplicaciones que desea instalar automáticamente para los usuarios. También puede filtrar aplicaciones por directiva de permisos de aplicación.

6. Seleccione **Agregar**.

![Instalar directiva de aplicación.](media/install-apps-in-meeting.png)

> [!IMPORTANT]
> Los usuarios no pueden desinstalar las aplicaciones instaladas por los administradores.

## <a name="upload-custom-apps"></a>Upload aplicaciones personalizadas

Puede usar el centro de Microsoft Teams para crear una directiva personalizada que permita a los usuarios cargar aplicaciones personalizadas a Teams.

Para crear una directiva de configuración de aplicaciones que permita a los usuarios cargar aplicaciones personalizadas en Teams, siga estos pasos:

1. En el panel de navegación izquierdo del Microsoft Teams de administración, vaya a Teams **directivas**  >  **de configuración de aplicaciones.**

2. Seleccione **Agregar**.

3. Escriba un nombre y una descripción para la directiva.

4. Activa o desactiva las **Upload** personalizadas, dependiendo de si quieres permitir que los usuarios carguen aplicaciones personalizadas en Teams.

> [!NOTE]
> No puede cambiar esta configuración si Permitir aplicaciones **de terceros** está desactivada en la configuración de la aplicación para toda [la organización.](manage-apps.md#manage-org-wide-app-settings)

## <a name="manage-app-setup-policies"></a>Administrar directivas de configuración de aplicaciones

Puede administrar directivas de configuración de aplicaciones en el Microsoft Teams de administración. Use la directiva global (predeterminada para toda la organización) o cree y asigne directivas personalizadas.  Los usuarios de su organización obtendrán automáticamente la directiva global, a menos que cree y asigne una directiva personalizada. Debe ser un administrador global o un administrador de servicio de Teams para administrar estas directivas.

Edita la configuración de la directiva global para incluir las aplicaciones que desee. Para personalizar Teams para diferentes grupos de usuarios de su organización, cree y asigne una o más directivas personalizadas.

![la página Directivas de configuración de aplicaciones](media/app-setup-policies.png)

### <a name="edit-an-app-setup-policy"></a>Editar una directiva de configuración de aplicaciones

Puede usar el centro Microsoft Teams administración para editar una directiva, incluidas las directivas globales (predeterminadas para toda la organización) y las directivas personalizadas que cree.

1. En el panel de navegación izquierdo del Microsoft Teams de administración, vaya a Teams **directivas**  >  **de configuración de aplicaciones.**

2. Elija la directiva que desea editar y, a continuación, **seleccione Editar.**

3. Realice los cambios que desee.

4. Seleccione **Guardar**.

### <a name="assign-a-custom-app-setup-policy-to-users"></a>Asignar una directiva de configuración de aplicación personalizada a los usuarios

Para obtener más información sobre cómo asignar directivas a los usuarios, vea [Asignar directivas a usuarios y grupos.](assign-policies-users-and-groups.md)

## <a name="faq"></a>Preguntas más frecuentes

### <a name="working-with-app-setup-policies"></a>Trabajar con directivas de configuración de aplicaciones

#### <a name="can-i-assign-an-app-setup-policy-to-a-group"></a>¿Puedo asignar una directiva de configuración de aplicación a un grupo?

Las directivas de configuración de aplicaciones se pueden asignar a grupos con PowerShell. Para obtener más información sobre cómo asignar directivas a grupos con PowerShell, vea [Asignar directivas a usuarios y grupos.](assign-policies-users-and-groups.md#use-the-powershell-option)

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a>Qué directivas de configuración de aplicaciones integradas se incluyen en el centro de Microsoft Teams de administración

- **Global (predeterminado para toda** la organización): esta directiva predeterminada se aplica a todos los usuarios de su organización a menos que asigne otra directiva. Edite la directiva global para anclar aplicaciones que sean más importantes para los usuarios.

- **FrontlineWorker:** esta directiva es para trabajadores de frontline. Puede asignarlo a Trabajadores de frontline de su organización. Es importante saber que, al igual que las directivas personalizadas que cree, tiene que asignar la directiva a los usuarios para que la configuración esté activa. Para obtener más información, vaya a la sección Asignar una directiva de configuración [de aplicación personalizada a](#assign-a-custom-app-setup-policy-to-users) los usuarios de este artículo.

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>¿Por qué no puedo encontrar una aplicación en el panel Agregar aplicaciones ancladas?

No todas las aplicaciones se pueden anclar a Teams a través de una directiva de configuración de aplicaciones. Es posible que algunas aplicaciones no admitan esta funcionalidad. Para buscar aplicaciones que se pueden anclar, busque la aplicación en el panel Agregar aplicaciones **ancladas.** Las pestañas que tienen un ámbito personal (pestañas estáticas) y bots se pueden anclar al cliente de escritorio de Teams y estas aplicaciones están disponibles en el panel Agregar aplicaciones **ancladas.**

Tenga en cuenta que el Teams de aplicaciones enumera todas las Teams aplicaciones. El **panel Agregar aplicaciones ancladas** solo incluye las aplicaciones que se pueden anclar a Teams a través de una directiva.

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>Soy administrador Teams para Educación usuario. ¿Qué necesito saber sobre las directivas de configuración de aplicaciones en Teams para Educación

La aplicación Llamadas no está disponible en Teams para Educación. Al crear una nueva directiva de configuración de aplicaciones personalizada, la aplicación Llamadas se muestra en la lista de aplicaciones. Sin embargo, la aplicación no está anclada a Teams clientes y Teams para Educación usuarios no verán la aplicación Llamadas en Teams.

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a>Cuántas aplicaciones ancladas se pueden agregar a una directiva

Un mínimo de dos aplicaciones deben estar ancladas a los Teams móviles (iOS y Android). Si una directiva tiene menos de dos aplicaciones, los clientes móviles no reflejarán la configuración de directiva y, en su lugar, seguirán usando la configuración existente.

No hay ningún límite en el número de aplicaciones ancladas que puede agregar a una directiva.

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a>¿Cuánto tiempo se necesita para que los cambios de directiva entren en vigor?

Después de editar o asignar una directiva, los cambios pueden tardar unas horas en tener efecto.

### <a name="user-experience"></a>Experiencia de usuario

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a>¿Cómo pueden los usuarios ver todas sus aplicaciones ancladas en Teams

Para ver todas las aplicaciones ancladas para un usuario, es posible que los usuarios tengan que hacer lo siguiente en función del número de aplicaciones instaladas y del tamaño de su ventana de cliente Teams usuario.

|Cliente de escritorio de Teams |Cliente móvil de Teams |
|---------|---------|
|En la barra de la aplicación en el lado de Teams, seleccione **... Más aplicaciones**.| En la barra de aplicaciones cerca de la parte inferior de Teams, deslice el dedo hacia arriba.|
|![Más aplicaciones en el Teams de escritorio](media/app-setup-policies-desktop-more-apps.png)<br>   |![más aplicaciones en el Teams móvil](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a>¿Qué necesito saber sobre la Teams móvil?

Los Teams móviles (iOS y Android) admiten aplicaciones personales con pestañas estáticas. Las aplicaciones ancladas al Teams de escritorio aparecerán en los Teams móviles. Los bots personales aparecerán en Chat en clientes móviles.

Las aplicaciones de terceros (que se pueden descargar desde Teams Store) deben aprobarse antes de que se muestren en dispositivos móviles. Si un administrador ancla una aplicación, que no ha sido aprobada por Microsoft para Móviles, se mostrará en el escritorio de Teams, pero no se mostrará en dispositivos móviles. Vea [Clientes móviles](/microsoftteams/platform/tabs/what-are-tabs#mobile-clients) para obtener más información.

Con los Teams móviles, los usuarios verán aplicaciones principales de Teams como Actividad, Chat y Teams, y puede anclar algunas aplicaciones de primer nivel de Microsoft, como Turnos.

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a>¿Pueden los usuarios cambiar el orden de las aplicaciones ancladas a través de una directiva?

Los usuarios pueden cambiar el orden de sus aplicaciones ancladas  en Teams de escritorio y móviles si la opción Permitir anclación de usuario está activada. Los usuarios no pueden cambiar el orden de sus aplicaciones ancladas en Teams web.

#### <a name="does-user-pinning-take-precedence"></a>¿Tiene prioridad la anclación de usuario?

Los anclares de administrador siempre tienen prioridad. Si la **opción Permitir anclación de** usuario está activada, los usuarios conservarán sus aplicaciones ancladas debajo de las aplicaciones ancladas por el administrador. Si la **opción** Permitir anclación de usuario está desactivada, los usuarios perderán sus pasadores preexistentes y solo las aplicaciones ancladas por el administrador estarán presentes en la barra de aplicaciones.

### <a name="custom-teams-apps"></a>Aplicaciones Teams personalizadas

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a>Mi organización creó una aplicación de Teams personalizada y la publicó, ya sea en AppSource o en el catálogo de aplicaciones de inquilino, pero el icono de la aplicación no se muestra como se esperaba cuando la aplicación se ancla a la barra de aplicaciones en Teams. ¿Cómo puedo corregirlo?

Asegúrese de que sigue las directrices del logotipo antes de enviar la aplicación. Para obtener más información, vea [Envío de lista de comprobación del panel de vendedores.](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)

## <a name="related-topics"></a>Temas relacionados

[Configurar la administración para aplicaciones en Teams](admin-settings.md)

[Asignar directivas a los usuarios en Teams](assign-policies-users-and-groups.md)
