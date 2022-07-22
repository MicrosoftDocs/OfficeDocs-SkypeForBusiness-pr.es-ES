---
title: Administrar las aplicaciones en el Centro de administración de Microsoft Teams
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
ms.custom: intro-get-started
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: vaibhava
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: Obtenga información sobre cómo administrar las aplicaciones de Teams. Obtenga información sobre cómo permitir o bloquear aplicaciones, comprobar el estado de nivel de organización y las propiedades de las aplicaciones, cargar aplicaciones personalizadas y administrar la configuración de las aplicaciones.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 5e1b5f53ba648d1096460572562b91397b74ab3b
ms.sourcegitcommit: 70185cd963c5a9d539e65e302d4230018209ecae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2022
ms.locfileid: "66958065"
---
# <a name="manage-teams-apps-in-the-microsoft-teams-admin-center"></a>Administrar aplicaciones de Teams en el Centro de administración de Microsoft Teams

Puede administrar las aplicaciones de su organización en la página **de aplicaciones de Teams** en el portal del Centro de administración de Teams. Use la página Administrar aplicaciones para ver y administrar todas las aplicaciones de Teams en el catálogo de aplicaciones de su organización, atender casos de uso destacados para la administración de aplicaciones, definir el acceso a las aplicaciones mediante directivas y mucho más.

:::image type="content" source="media/manage-apps.png" alt-text="Captura de pantalla de la página Administrar aplicaciones." lightbox="media/manage-apps.png":::

Para administrar aplicaciones, use directivas para controlar los permisos de los usuarios, la instalación de aplicaciones y la carga de aplicaciones personalizadas creadas dentro de su organización. Para comprender las directivas, consulte [Información general sobre directivas de aplicaciones](app-policies.md).

Para usar el Centro de administración de Teams, debe tener un rol de Administración global o administrador de Teams. Para obtener más información, consulte [Roles de administrador de Teams y Roles](./using-admin-roles.md) de [administrador de Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles).

> [!NOTE]
> La página Administrar aplicaciones no está disponible en las implementaciones de Microsoft 365 Government Community Cloud High (GCCH) ni del Departamento de defensa (DoD) de Teams.

Durante la creación de una aplicación, los desarrolladores crean y agregan un id. de aplicación al archivo de manifiesto. Puede ver este id. de aplicación externa en la página Administrar aplicaciones después de habilitar la columna `External app ID` en la configuración de columna. También puede verlo en la página de detalles de la aplicación de una aplicación personalizada. El id. solo se aplica a las aplicaciones personalizadas.

## <a name="app-management-use-cases-and-the-available-interfaces"></a>Casos de uso de administración de aplicaciones y las interfaces disponibles

Las opciones para lograr la mayoría de los casos de uso de administración de aplicaciones están disponibles en el Centro de administración de Teams. Además, algunas opciones están disponibles en otros portales o páginas de diferentes centros de administración en el mismo portal.

| Casos de uso de administración de aplicaciones | Vincular a la interfaz | Documentación |
|:----|:----|:----|
| **En el Centro de administración de Teams** | | |
| Controle qué aplicaciones están disponibles para los usuarios de su organización al permitir y bloquear aplicaciones. También puede cargar y aprobar aplicaciones personalizadas. Después de administrar aplicaciones en esta página, puede usar permisos de aplicaciones y directivas de configuración de aplicaciones para configurar qué aplicaciones están disponibles para usuarios específicos en la tienda de aplicaciones de su organización. | [Administrar aplicaciones en el Centro de administración de Teams](https://admin.teams.microsoft.com/policies/manage-apps) | Artículo actual |
| Las directivas de permisos de aplicaciones controlan qué aplicaciones quiere que estén disponibles para los usuarios de Teams de su organización. Puede usar la directiva predeterminada Global (para toda la organización) y personalizarla, o bien puede crear una o más directivas para satisfacer las necesidades de su organización. | [Directivas de permisos](https://admin.teams.microsoft.com/policies/app-permission) | [Administrar directivas de permisos de aplicaciones](teams-app-permission-policies.md) |
| Las directivas de configuración de aplicaciones controlan cómo las aplicaciones están disponibles para un usuario con la aplicación de Teams. Use la directiva Global (predeterminada para toda la organización) y personalícela o cree directivas personalizadas y asígnelas a un conjunto de usuarios. | [Directivas de configuración](https://admin.teams.microsoft.com/policies/app-setup) | [Administrar directivas de configuración de aplicaciones](teams-app-setup-policies.md) |
| Puedes desarrollar y cargar aplicaciones personalizadas como paquetes de aplicaciones y hacer que estén disponibles en la tienda de aplicaciones de tu organización. | Configuración de aplicaciones para toda la organización en [Administrar aplicaciones](https://admin.teams.microsoft.com/policies/manage-apps) | [Administrar directivas de aplicaciones personalizadas](teams-custom-app-policies-and-settings.md) |
| Puede personalizar la tienda de aplicaciones de Teams con el logotipo, el fondo personalizado o el color de su organización. | [Personalizar tienda](https://admin.teams.microsoft.com/policies/customize-appstore) | [Personalizar la tienda de aplicaciones de su organización](customize-your-app-store.md) |
| El informe de uso de aplicaciones de Teams proporciona información sobre las aplicaciones que se usan, los usuarios activos y otra información sobre el uso de las aplicaciones. | [Informes de uso](https://admin.teams.microsoft.com/analytics/reports) | [Informe de uso de aplicaciones de Teams](teams-analytics-and-reports/app-usage-report.md) |
| Los usuarios pueden agregar aplicaciones cuando hospeden reuniones o chats con invitados. También pueden usar aplicaciones compartidas por invitados cuando se unan a reuniones o chats hospedados externamente. Se aplican las directivas de datos de la organización del usuario de hospedaje y las prácticas de uso compartido de datos de cualquier aplicación de terceros compartida por la organización de ese usuario. | [Acceso externo](https://admin.teams.microsoft.com/company-wide-settings/external-communications) | [Comportamiento de las aplicaciones en función de los tipos de usuarios](non-standard-users.md) |
| Con el acceso de invitado, puede proporcionar acceso a las aplicaciones y a otras funciones de Teams a personas de fuera de su organización, a la vez que mantiene el control sobre sus datos corporativos. | [Acceso de invitado](https://admin.teams.microsoft.com/company-wide-settings/guest-configuration) | [Acceso de invitado a Teams](guest-access.md) |
| Las directivas de actualización se usan para administrar Teams y los usuarios de la versión preliminar de Office que verán las características de versión preliminar o versión preliminar en la aplicación teams.  | [Directivas de actualización de Teams](https://admin.teams.microsoft.com/policies/updatemanagement) | [Versión preliminar pública de Teams](public-preview-doc-updates.md) |
| **Centro de administración de Teams externo** | | |
| Administrar licencias y suscripciones de aplicaciones de terceros en Centro de administración de Microsoft 365 | [Centro de administración de Microsoft 365](https://admin.microsoft.com/#/licenses) | [Administrar suscripciones a aplicaciones de terceros](/microsoft-365/commerce/manage-saas-apps) |
| Auditar eventos de la aplicación Teams en portal de cumplimiento Microsoft Purview. | [Auditoría](https://compliance.microsoft.com/auditlogsearch?viewid=Async%20Search) | [Actividades de Teams](audit-app-management-activities.md) |
| Se pueden conceder permisos a las aplicaciones a su organización y a sus datos mediante tres métodos: un administrador da su consentimiento a la aplicación para todos los usuarios, un usuario concede su consentimiento a la aplicación o un administrador integra una aplicación y habilita el acceso de autoservicio o asigna usuarios directamente a la aplicación. Compruebe los permisos de Graph para las aplicaciones. Compruebe los permisos que proporcionaron los usuarios o que los administradores delegó. | [Portal de Azure AD](https://aad.portal.azure.com/) | [Revisar los permisos concedidos a las aplicaciones](/azure/active-directory/manage-apps/manage-application-permissions) |

<!---
| xxx | [Manage users](https://admin.teams.microsoft.com/users) | [Add users and assign licenses](/microsoft-365/admin/add-users/add-users?view=o365-worldwide) |  
--->

## <a name="allow-and-block-apps"></a>Permitir y bloquear aplicaciones

La página Administrar aplicaciones es donde permites o bloqueas aplicaciones individuales en el nivel de organización. La página muestra toda la aplicación disponible y el estado actual de la aplicación a nivel de organización. La lista de aplicaciones incluye aplicaciones proporcionadas por Microsoft, por desarrolladores de terceros y por desarrolladores de tu organización.

Para permitir o bloquear una aplicación:

1. Inicie sesión en el Centro de administración de Teams.
1. Acceda a la página **[Administrar aplicaciones](https://admin.teams.microsoft.com/policies/manage-apps)** de **las aplicaciones** >  de Teams.
1. Selecciona una aplicación de la lista de aplicaciones. Puedes buscar por el nombre de la aplicación y luego seleccionarla.
1. Selecciona **la opción Permitir** o **Bloquear** .

Al permitir (o bloquear) una aplicación en la página [Administrar aplicaciones](https://admin.teams.microsoft.com/policies/manage-apps) del Centro de administración de Teams, se permite (o bloquea) la aplicación en particular para todos los usuarios de la organización. Este método difiere de la directiva de permisos de la aplicación en el contexto que permite (o bloquea) una aplicación a través de la directiva de permisos, afecta solo a los usuarios específicos que tienen asignada la directiva.

Un usuario puede instalar y usar una aplicación solo cuando se permite la aplicación a través de la configuración del inquilino y se permite para el usuario a través de la directiva de permisos.

## <a name="manage-user-requests-to-unblock-apps"></a>Administrar las solicitudes de usuario para desbloquear aplicaciones

Puedes ver las solicitudes para hacer que una aplicación bloqueada esté disponible para su uso. La solicitud se envía al administrador de TI, que puede ver y administrar las solicitudes de usuario en el Centro de administración de Teams.

  :::image type="content" source="media/user-request.png" alt-text="Realizar una solicitud de aprobación de aplicaciones bloqueadas":::

### <a name="view-a-request"></a>Ver una solicitud

 1. Inicie sesión en el Centro de administración de Teams y seleccione [Administrar aplicaciones](https://admin.teams.microsoft.com/policies/manage-apps)

    :::image type="content" source="media/requested-apps1.png" alt-text="Las solicitudes de usuario final para aplicaciones bloqueadas se muestran en el Centro de administración de Teams, en la columna denominada Solicitudes de usuarios." lightbox="media/requested-apps.png":::

 1. Para ver y comprobar el número de solicitudes de cada aplicación, ordene las solicitudes en la columna **Solicitudes por usuario** .
 1. Selecciona el nombre de la aplicación que quieras desbloquear y se abrirá la página de detalles de la aplicación.
 1. Seleccione **Administrar solicitudes** y complete los pasos mostrados en el cuadro de diálogo emergente. Los pasos para aprobar una aplicación varían en función del método usado para bloquearla.

    * Si la aplicación se bloquea mediante directivas de permisos, modifique las [directivas de permisos](teams-app-permission-policies.md) para permitir la aplicación.
    * Si la aplicación está bloqueada para todos los usuarios, [permita la aplicación](#allow-and-block-apps).
    * Si todas las aplicaciones están bloqueadas para todos los usuarios, modifique la [configuración de toda la organización](#manage-org-wide-app-settings).

 Si un administrador permite una aplicación, no informa al usuario final de que su solicitud se debe a ello. El usuario debe visitar la aplicación en la Store para comprobar si la aplicación está desbloqueada o no.

### <a name="dismiss-a-user-request"></a>Descartar una solicitud de usuario

 1. Seleccione el nombre de la aplicación para la que desea descartar las solicitudes de usuario.
 1. Seleccione **Administrar solicitudes** y seleccione **Descartar todas las solicitudes** en el cuadro de diálogo.
 1. Cuando se descarta una solicitud, se restablecen las solicitudes de usuario a cero.

  :::image type="content" source="media/reject.png" alt-text="rechazo de aplicaciones bloqueadas."border="true":::

Si un administrador descarta una solicitud, no informa al usuario final de que se ha actuado en consecuencia. El usuario debe visitar la aplicación en la Store para comprobar si la aplicación está desbloqueada o no.

## <a name="allow-the-apps-that-are-blocked-by-the-developers"></a>Permitir las aplicaciones que bloquean los desarrolladores

Cuando un desarrollador publica una aplicación en la tienda de aplicaciones de Teams, es posible que necesite administradores para configurar o personalizar la experiencia de la aplicación. Los administradores hacen que la experiencia esté disponible para los usuarios finales cuando se configure la aplicación.

Por ejemplo, Contoso Electronics es un ISV que ha creado una aplicación de asistencia para Microsoft Teams. Contoso Electronics quiere que sus clientes configuren determinadas propiedades de la aplicación para que, cuando los usuarios interactúen con la aplicación, funcione según lo esperado. Antes de que un administrador pueda permitir o bloquear la aplicación, se mostrará como **Bloqueada por el editor** en el Centro de administración de Teams y está oculta a los usuarios finales de forma predeterminada. Después de seguir las instrucciones del editor para configurar la aplicación, puede hacer que esté disponible para los usuarios cambiando el estado a **Permitido**.

:::image type="content" source="media/blocked-by-publisher.png" alt-text="Captura de pantalla del estado bloqueado por el editor en el Centro de administración de Teams.":::

## <a name="manage-org-wide-app-settings"></a>Administrar la configuración de aplicaciones para toda la organización

Use la configuración de aplicaciones para toda la organización para controlar si los usuarios con una [licencia F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt) obtienen la experiencia de aplicación de primera línea adaptada, si los usuarios pueden instalar aplicaciones de terceros y si los usuarios pueden cargar o interactuar con aplicaciones personalizadas en su organización. La configuración de aplicaciones para toda la organización rige el comportamiento de todos los usuarios e invalida cualquier otra directiva de permisos de aplicación asignada a los usuarios. Puede usarla para controlar las aplicaciones malintencionadas o problemáticas.

> [!NOTE]
> Para obtener información sobre cómo usar la configuración de aplicaciones para toda la organización en Microsoft 365 Administración pública: implementaciones de Microsoft 365 Government Community Cloud High GCCH y del Departamento de Defensa (DoD) de Teams, consulte [Administrar directivas de permisos de aplicaciones en Teams](teams-app-permission-policies.md).

1. En la página Administrar aplicaciones, seleccione **Configuración de aplicaciones para toda la organización**. A continuación, puede configurar las opciones que desee en el panel.

    :::image type="content" source="media/manage-apps-org-wide-app-settings.png" alt-text="Captura de pantalla del panel Configuración de aplicaciones para toda la organización en la página Administrar aplicaciones":::

1. En **Aplicaciones adaptadas**, desactiva o activa **Mostrar aplicaciones adaptadas**. Cuando esta configuración está activada, los usuarios con una [licencia F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt) obtienen la experiencia de aplicación de primera línea personalizada. Esta experiencia ancla las aplicaciones más relevantes de Teams para los trabajadores de primera línea. Para obtener más información, consulte [Personalizar aplicaciones de Teams para los trabajadores de primera línea](pin-teams-apps-based-on-license.md).

    Esta característica está disponible para licencias F. En el futuro se admitirán otros tipos de licencia.
1. En **Aplicaciones de terceros**, desactive o active esta configuración para controlar el acceso a aplicaciones de terceros:

    * **Permitir aplicaciones de terceros**: esto controla si los usuarios pueden usar aplicaciones de terceros. Si desactivas esta configuración, los usuarios no podrán instalar ni usar aplicaciones de terceros y el estado de la aplicación de estas aplicaciones se mostrará como Bloqueado en toda la **organización** en la tabla.

        > [!NOTE]
        > Cuando **Permitir aplicaciones de terceros** está desactivado, [los webhooks salientes](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) siguen estando habilitados para todos los usuarios, pero puede controlarlos en el nivel de usuario al permitir o bloquear la aplicación De webhook saliente a través de [directivas de permisos de aplicaciones](teams-app-permission-policies.md). Tenga en cuenta que si tiene directivas de [permisos de aplicaciones](teams-app-permission-policies.md) existentes para **aplicaciones de Microsoft** que usan la opción **Permitir aplicaciones específicas y bloquear todas las demás** , y desea habilitar los webhooks salientes para los usuarios, agregue la aplicación de webhook saliente a la lista.

        > [!NOTE]
        > Los usuarios de Teams puede añadir aplicaciones cuando organizan reuniones o chats con personas de otras organizaciones. También pueden usar aplicaciones compartidas con personas de otras organizaciones cuando organizan reuniones o chats con estas organizaciones. Se aplican las directivas de datos de la organización del usuario anfitrión, así como las prácticas de intercambio de datos de cualquier aplicación de terceros compartida por la organización del usuario.

    * **Permitir las nuevas aplicaciones de terceros publicadas en la tienda de forma predeterminada**: esto controla si las nuevas aplicaciones de terceros publicadas en la tienda de aplicaciones de Teams están disponibles automáticamente en Teams. Solo puede establecer esta opción si permite aplicaciones de terceros.

1. En **Aplicaciones personalizadas**, desactiva o activa **Permitir interacción con aplicaciones personalizadas**. Esta configuración controla si los usuarios pueden interactuar con aplicaciones personalizadas. Para obtener más información, consulte [Administrar configuración y directivas de aplicación personalizadas en Teams](teams-custom-app-policies-and-settings.md).
1. Seleccione **Guardar** para que la configuración de aplicaciones de toda la organización surta efecto.

## <a name="related-article"></a>Artículo relacionado

* [Administrar Teams durante la transición desde Skype Empresarial centro de administración](manage-teams-skypeforbusiness-admin-center.md)
