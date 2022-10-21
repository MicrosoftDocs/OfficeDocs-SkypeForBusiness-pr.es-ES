---
title: Administrar las aplicaciones en el Centro de administración de Microsoft Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
ms.custom: intro-get-started
audience: admin
ms.date: 09/29/2022
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
ms.reviewer: kojika
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: Obtenga información sobre cómo administrar aplicaciones de Teams. Aprenda a permitir o bloquear aplicaciones, comprobar el estado y las propiedades de la aplicación a nivel de organización, cargar aplicaciones personalizadas y administrar la configuración de la aplicación.
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: dc7dbf1a4866fa85551d6ec46f7ea54c164ba655
ms.sourcegitcommit: 1161cddd077056a9c1e2da99a84e35be0380b1b1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68656056"
---
# <a name="overview-of-app-management-and-governance-in-teams-admin-center"></a>Información general sobre administración y gobierno de aplicaciones en el Centro de administración de Teams

Las aplicaciones se administran para su organización en la página **Aplicaciones de Teams** en el portal del centro de administración de Teams. Use la página Administrar aplicaciones para ver y administrar todas las aplicaciones de Teams en el catálogo de aplicaciones de su organización, atender casos de uso destacados para la administración de aplicaciones, definir el acceso a las aplicaciones mediante directivas y mucho más.

:::image type="content" source="media/manage-apps.png" alt-text="Captura de pantalla de la página Administrar aplicaciones." lightbox="media/manage-apps.png":::

Para administrar aplicaciones, use directivas para controlar los permisos de los usuarios, la instalación de aplicaciones y la carga de aplicaciones personalizadas creadas dentro de su organización. Para comprender las directivas, consulte [Información general sobre las directivas de aplicaciones.](app-policies.md).

Para usar el centro de administración de Teams, debe tener un rol de administrador global o administrador de Teams. Para obtener más información, consulte [ Roles de administrador de Teams](./using-admin-roles.md) y [Roles de administrador de Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles).

> [!NOTE]
> La página Administrar aplicaciones no está disponible en las implementaciones de Microsoft 365 Government Community Cloud High (GCCH) o departamento de Defensa (DoD) de Teams.

## <a name="app-management-use-cases-and-the-available-interfaces"></a>Casos de uso de administración de aplicaciones y las interfaces disponibles

Las opciones para llevar a cabo la mayoría de los casos de administración de aplicaciones están disponibles en el centro de administración de Teams. Además, ciertas opciones están disponibles en otros portales o en diferentes páginas del Centro de administración de Teams.

Las tareas de administración de aplicaciones compatibles con el Centro de administración se encuentran en la tabla siguiente.

| Casos de uso de administración de aplicaciones | Vínculo a la interfaz | Documentación |
|:----|:----|:----|
| Controle qué aplicaciones están disponibles para los usuarios de su organización permitiendo y bloqueando aplicaciones. También puede cargar y aprobar aplicaciones personalizadas. Después de administrar las aplicaciones en esta página, puede usar los permisos de la aplicación y las directivas de configuración de la aplicación para configurar qué aplicaciones están disponibles para usuarios específicos en la tienda de aplicaciones de su organización. | [Administrar aplicaciones en el Centro de administración de Teams](https://admin.teams.microsoft.com/policies/manage-apps) | Artículo actual |
| Las directivas de permisos de aplicaciones controlan qué aplicaciones desea que estén disponibles para los usuarios de Teams de su organización. Puede usar la directiva predeterminada global (de toda la organización) y personalizarla, o puede crear una o más directivas para satisfacer las necesidades de su organización. | [Directivas de permisos](https://admin.teams.microsoft.com/policies/app-permission) | [Administrar directivas de permisos de aplicación](teams-app-permission-policies.md) |
| Las directivas de configuración de aplicaciones controlan cómo las aplicaciones se ponen a disposición de un usuario con la aplicación Teams. Use la directiva Global (predeterminada para toda la organización) y personalícela o cree directivas personalizadas y asígnelas a un conjunto de usuarios. | [Directivas de configuración](https://admin.teams.microsoft.com/policies/app-setup) | [Administrar directivas de configuración de aplicaciones](teams-app-setup-policies.md) |
| Puede desarrollar y cargar aplicaciones personalizadas como paquetes de aplicaciones y ponerlas a disposición en la tienda de aplicaciones de su organización. | Configuración de aplicaciones de toda la organización en [Administrar aplicaciones](https://admin.teams.microsoft.com/policies/manage-apps) | [Administrar la configuración de directivas para aplicaciones personalizadas](teams-custom-app-policies-and-settings.md) |
| Puede personalizar la tienda de aplicaciones de Teams con el logotipo, el fondo personalizado o el color de su organización. | [Personalizar tienda](https://admin.teams.microsoft.com/policies/customize-appstore) | [Personalice la tienda de aplicaciones de su organización](customize-your-app-store.md) |
| El informe de uso de aplicaciones de Teams proporciona información sobre las aplicaciones en uso, los usuarios activos y otra información de uso de aplicaciones. | [Informes de uso](https://admin.teams.microsoft.com/analytics/reports) | [Informe de uso de la aplicación Teams](teams-analytics-and-reports/app-usage-report.md) |
| Los usuarios pueden agregar aplicaciones cuando hospedan reuniones o chats con invitados. También pueden usar aplicaciones compartidas por los invitados cuando se unen a reuniones o chats hospedados externamente. Se aplican las directivas de datos de la organización del usuario de hospedaje y las prácticas de intercambio de datos de cualquier aplicación de terceros compartida por la organización de ese usuario. | [Acceso externo](https://admin.teams.microsoft.com/company-wide-settings/external-communications) | [ Comportamiento de la aplicación en función de los tipos de usuarios](non-standard-users.md) |
| Con el acceso de invitados, puede proporcionar acceso a aplicaciones y otras funcionalidades de Teams a personas ajenas a su organización, al tiempo que mantiene el control sobre sus datos corporativos. | [Acceso de invitado](https://admin.teams.microsoft.com/company-wide-settings/guest-configuration) | [Acceso de invitado a Teams](guest-access.md) |
| Las directivas de actualización de Teams se usan para administrar Teams y los usuarios de la versión preliminar de Office que pueden ver las características preliminares o previas de la versión preliminar en la aplicación teams. | [Directivas de actualización de Teams](https://admin.teams.microsoft.com/policies/updatemanagement) | [Versión preliminar pública de Teams](public-preview-doc-updates.md) |

Las tareas de administración de aplicaciones compatibles con otros portales se encuentran en la tabla siguiente.

| Casos de uso de administración de aplicaciones | Vínculo a la interfaz | Documentación |
|:----|:----|:----|
| Administrar licencias y suscripciones de aplicaciones de terceros en el Centro de administración de Microsoft 365 | [Centro de administración de Microsoft 365](https://admin.microsoft.com/#/licenses) | [Administrar suscripciones de aplicaciones de terceros](/microsoft-365/commerce/manage-saas-apps) |
| Eventos de la aplicación Auditoría de Teams en el portal de cumplimiento de Microsoft Purview. | [Auditoría](https://compliance.microsoft.com/auditlogsearch?viewid=Async%20Search) | [Actividades de Teams](audit-app-management-activities.md) |
| A las aplicaciones se les pueden conceder permisos para su organización y sus datos mediante tres métodos: un administrador da su consentimiento a la aplicación para todos los usuarios, un usuario otorga su consentimiento a la aplicación o un administrador que integra una aplicación y habilita el acceso de autoservicio o asigna usuarios directamente a la aplicación. Compruebe los permisos de Graph para las aplicaciones. Compruebe los permisos que proporcionaron los usuarios o que delegaron los administradores. | [Portal de Azure AD](https://aad.portal.azure.com/) | [Revisar los permisos concedidos a las aplicaciones](/azure/active-directory/manage-apps/manage-application-permissions) |

<!---
| xxx | [Manage users](https://admin.teams.microsoft.com/users) | [Add users and assign licenses](/microsoft-365/admin/add-users/add-users?view=o365-worldwide) |  
--->

## <a name="allow-and-block-apps"></a>Permitir y bloquear aplicaciones

Como administrador, puede controlar el acceso a todos los tipos de aplicaciones que usan todos los usuarios en todo contexto. Teams proporciona controles granulares para configurar el acceso para cada aplicación y para cada usuario.

Para permitir una aplicación, es necesario realizar todas las siguientes opciones de configuración. Para bloquear una aplicación, bloquee la aplicación mediante cualquiera de las siguientes opciones de configuración.

* [Configuración de aplicaciones para toda](manage-apps.md#manage-org-wide-app-settings) la organización: use esta opción para permitir el uso de aplicaciones en su organización. Tú decides qué aplicaciones específicas se usan.
* [Permitir una aplicación individual](manage-apps.md#allow-and-block-apps): usa esta opción para permitir una aplicación específica de tu organización. Usted decide qué usuarios pueden usar la aplicación.
* [Directiva de permisos de](teams-app-permission-policies.md) aplicaciones: use directivas para permitir que todos los usuarios puedan usar una aplicación o permitir que determinados usuarios lo usen. Usted decide el acceso por usuario y por aplicación.

La página Administrar aplicaciones es donde se permiten o bloquean aplicaciones individuales en el nivel de organización. La página muestra todas las aplicaciones disponibles y su estado actual de la aplicación de nivel de organización. Para permitir o bloquear una aplicación, sigue estos pasos:

1. Inicie sesión en el Centro de administración de Teams y acceda a **las aplicaciones** > **[de Teams Administrar aplicaciones](https://admin.teams.microsoft.com/policies/manage-apps)**
1. Busca una aplicación y selecciónala.
1. Seleccione la opción **Permitir** o **Bloquear**.

Para permitir una aplicación para usuarios específicos, consulta [directivas de permisos de aplicaciones](teams-app-permission-policies.md).

## <a name="manage-org-wide-app-settings"></a>Administrar la configuración de la aplicación en toda la organización

Use la configuración de aplicaciones de toda la organización para controlar si los usuarios con una [licencia F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt) obtienen la experiencia de aplicación de primera línea personalizada, si los usuarios pueden instalar aplicaciones de terceros y si los usuarios pueden cargar o interactuar con aplicaciones personalizadas en su organización.

> [!NOTE]
> Para obtener información sobre cómo usar la configuración de aplicaciones para toda la organización de Microsoft 365 Government - Government Community Cloud High GCCH y del departamento de Defensa (DoD) de Teams, consulte [Administrar directivas de permisos de aplicaciones en Teams.](teams-app-permission-policies.md).

1. En la página **[Administrar aplicaciones](https://admin.teams.microsoft.com/policies/manage-apps)** , seleccione **Configuración de aplicaciones para toda la organización**. A continuación, puede configurar las opciones que desee en el panel.

    :::image type="content" source="media/manage-apps-org-wide-app-settings.png" alt-text="Captura de pantalla del panel de configuración de la aplicación de toda la organización en la página Administrar aplicaciones":::

1. En **Aplicaciones personalizadas**, desactive o active **Mostrar aplicaciones personalizadas**. Cuando esta configuración esté activada, los usuarios con una [licencia F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt) obtendrán la experiencia de la aplicación de primera línea personalizada. Esta experiencia fija las aplicaciones más relevantes en Teams para los trabajadores de primera línea. Para obtener más información, consulte [Adaptar las aplicaciones de Teams para los trabajadores de primera línea.](pin-teams-apps-based-on-license.md).

    Esta característica está disponible para las licencias F. Otros tipos de licencia serán compatibles en el futuro.
1. En **Aplicaciones de terceros**, desactive o active esta configuración para controlar el acceso a aplicaciones de terceros:

    * **Permitir aplicaciones de terceros**: esto controla si los usuarios pueden usar aplicaciones de terceros. Si desactiva esta configuración, los usuarios no podrán instalar ni usar ninguna aplicación de terceros y el estado de estas aplicaciones se mostrará como **Bloqueado en toda la organización** en la tabla.

        > [!NOTE]
        > Cuando **Permitir aplicaciones de terceros** está desactivado, [los Webhooks salientes siguen habilitados](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) para todos los usuarios, pero puede controlarlos en el nivel de usuario permitiendo o bloqueando la aplicación de Webhook saliente a través de [directivas de permisos de aplicación](teams-app-permission-policies.md). Tenga en cuenta que si tiene [directivas de permisos de aplicación](teams-app-permission-policies.md) existentes para **las aplicaciones de Microsoft** que usan la configuración **Permitir aplicaciones específicas y bloquear todas las demás**, y desea habilitar webhooks salientes para los usuarios, agregue la aplicación de Webhook saliente a la lista.

        > [!NOTE]
        > Los usuarios de Teams puede añadir aplicaciones cuando organizan reuniones o chats con personas de otras organizaciones. También pueden usar aplicaciones compartidas con personas de otras organizaciones cuando organizan reuniones o chats con estas organizaciones. Se aplican las directivas de datos de la organización del usuario anfitrión, así como las prácticas de intercambio de datos de cualquier aplicación de terceros compartida por la organización del usuario.

    * **Permitir las nuevas aplicaciones de terceros publicadas en la tienda de forma predeterminada**: esto controla si las nuevas aplicaciones de terceros publicadas en la tienda de aplicaciones de Teams están disponibles automáticamente en Teams. Solo puede establecer esta opción si permite aplicaciones de terceros.

1. En **Aplicaciones personalizadas**, desactiva o activa **Permitir interacción con aplicaciones personalizadas**. Esta configuración controla si los usuarios pueden interactuar con aplicaciones personalizadas. Para obtener más información, consulta [Administrar directivas y configuración de aplicaciones personalizadas](teams-custom-app-policies-and-settings.md).

1. Seleccione **Guardar**. La configuración surte efecto después de unas horas.

## <a name="manage-org-wide-app-settings-for-microsoft-365-government"></a>Administrar la configuración de la aplicación para toda la organización para Microsoft 365 Administración Pública  

En una implementación de Microsoft 365 Administración Pública - GCC, GCCH y DoD de Teams, todas las aplicaciones de terceros se bloquean de forma predeterminada. En las nubes GCCH y DOD, las aplicaciones de terceros no están disponibles. Además, en GCC, verá la siguiente nota sobre la administración de aplicaciones de terceros en la página de directivas de permisos de aplicación del Centro de administración de Microsoft Teams.

:::image type="content" source="media/app-permission-policies-gcc.png" alt-text="Captura de pantalla de la directiva de permisos de aplicación en GCCH y DoD.":::

Use la configuración de aplicaciones para toda la organización para controlar si los usuarios pueden instalar aplicaciones de terceros. La configuración de aplicaciones para toda la organización rige el comportamiento de todos los usuarios e invalida cualquier otra directiva de permisos de aplicación asignada a los usuarios.

<!---1. On the **Permission policies** page, select **Org-wide app settings**. You can then configure the settings you want in the panel. 
--->

### <a name="for-gcc-clouds"></a>Para nubes GCC

1. En la página **Administrar** > **[aplicaciones](https://admin.teams.microsoft.com/policies/manage-apps)** de Teams, seleccione **Configuración de aplicaciones para toda la organización**. Después, podrá configurar las opciones que desee en el panel.

   :::image type="content" source="media/app-permission-policies-gcc-org-wide.png" alt-text="Captura de pantalla que muestra la configuración de aplicaciones para toda la organización en GCC.":::

1. En **Aplicaciones de terceros**, desactive o active esta configuración para controlar el acceso a aplicaciones de terceros:

    * **Permitir aplicaciones de terceros**: esta opción controla si los usuarios pueden usar aplicaciones de terceros. Si desactiva esta configuración, los usuarios no podrán instalar ni usar aplicaciones de terceros. En una implementación de Microsoft 365 Administración Pública - GCCH y DoD de Teams, esta configuración está desactivada de manera predeterminada.
    * **Permitir las nuevas aplicaciones de terceros publicadas en la tienda de forma predeterminada**: esta opción controla si las nuevas aplicaciones de terceros publicadas en la tienda de aplicaciones de Teams están disponibles automáticamente en Teams. Solo puede establecer esta opción si permite aplicaciones de terceros.

1. En **Aplicaciones bloqueadas**, agregue las aplicaciones que quiera bloquear en toda la organización. En una implementación de Microsoft 365 Administración Pública - GCCH y DoD de Teams, todas las aplicaciones de terceros se agregan a esta lista de forma predeterminada. Si desea permitir cualquier aplicación de terceros en su organización, quítela de esta lista de aplicaciones bloqueadas. Al bloquear una aplicación en toda la organización, la aplicación se bloquea automáticamente para todos los usuarios, independientemente de si está permitida en las directivas de permisos de la aplicación.

1. Seleccione **Guardar** para que la configuración de la aplicación en toda la organización surta efecto.

Para permitir aplicaciones de terceros, edite y use la directiva global (predeterminada para toda la organización) o cree y asigne una directiva creada por un administrador.

### <a name="for-gcch-and-dod-clouds"></a>Para nubes GCCH y DoD

1. Inicie sesión en el Centro de administración de Teams y acceda a **[las](https://admin.teams.microsoft.com/policies/app-permission)** **directivas de permisos de aplicaciones** >  de Teams.

1. Seleccione **Configuración de aplicaciones para toda la organización**. En **Aplicaciones bloqueadas**, agregue las aplicaciones que quiera bloquear en toda la organización. En una implementación de Microsoft 365 Administración Pública - GCCH y DoD de Teams, todas las aplicaciones de terceros se agregan a esta lista de forma predeterminada. Al bloquear una aplicación en toda la organización, la aplicación se bloquea automáticamente para todos los usuarios, independientemente de si está permitida en las directivas de permisos de la aplicación.

   :::image type="content" source="media/app-permission-policies-gcch-dod-org-wide.png" alt-text="Captura de pantalla de la configuración de la aplicación para toda la organización en GCCH y DoD.":::

1. Seleccione **Guardar** para que la configuración de la aplicación en toda la organización surta efecto.

## <a name="allow-the-apps-that-are-blocked-by-the-developers"></a>Permitir las aplicaciones bloqueadas por los desarrolladores

Cuando un desarrollador publica una aplicación en la tienda de Teams, es posible que algunas aplicaciones necesiten de un administrador para poder configurarla. Los administradores ponen la aplicación a disposición de los usuarios finales al configurarla.

Por ejemplo, Contoso Electronics es un desarrollador de aplicaciones que creó una aplicación de servicio de asistencia para Microsoft Teams. Contoso Electronics desea que sus clientes configuren ciertas propiedades de la aplicación para que cuando los usuarios interactúen con la aplicación, funcione como se esperaba. Antes de que un administrador pueda permitir o bloquear la aplicación, se mostrará como **Bloqueada por el editor** en el Centro de administración de Teams y se oculta a los usuarios finales de forma predeterminada. Después de seguir las instrucciones del editor para configurar la aplicación, puede ponerla a disposición de los usuarios cambiando el estado a **Permitido**.

:::image type="content" source="media/blocked-by-publisher.png" alt-text="Captura de pantalla del estado bloqueado por el editor en el centro de administración de Teams.":::

Para obtener información sobre cómo los desarrolladores bloquean una aplicación de forma predeterminada, consulta [Habilitar que las aplicaciones se bloqueen hasta que un administrador lo permita](/microsoftteams/platform/concepts/design/enable-app-customization#hide-teams-app-until-admin-approves).

## <a name="related-article"></a>Artículo relacionado

* [Administrar las solicitudes de usuario para permitir aplicaciones](user-requests-approve-apps.md).
