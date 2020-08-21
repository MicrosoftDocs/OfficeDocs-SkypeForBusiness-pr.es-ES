---
title: Ver permisos de aplicación y conceder consentimiento de administrador en el centro de administración de Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: vaibhava
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Aprenda a ver los permisos solicitados por las aplicaciones y a conceder consentimiento de administrador a las aplicaciones en la página Administrar aplicaciones del centro de administración de Microsoft Teams.
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 6aafd5cbdd1ae44844f69b78234f10a54abe7b85
ms.sourcegitcommit: bb5229c9f7999358dcf0ba185ecfd7c881627a38
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2020
ms.locfileid: "46824911"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a>Ver permisos de aplicación y conceder consentimiento de administrador en el centro de administración de Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

La página [Manage apps](manage-apps.md) en el centro de administración de Microsoft Teams es donde se ven y administran todas las aplicaciones de Teams para su organización. Por ejemplo, puede ver el estado de organización y las propiedades de las aplicaciones, aprobar o cargar nuevas aplicaciones personalizadas en la tienda de aplicaciones de su organización, bloquear o permitir aplicaciones en el nivel de organización y administrar la configuración de la aplicación en toda la organización.

Aquí, también puede conceder el consentimiento del administrador de toda la organización a las aplicaciones que solicitan permisos para acceder a datos y ver permisos de consentimiento específico de recursos (RSC) para las aplicaciones.

## <a name="grant-org-wide-admin-consent-to-an-app"></a>Conceder el consentimiento de administrador de toda la organización a una aplicación

Si es un administrador global, puede revisar y conceder consentimiento a las aplicaciones que solicitan permisos en nombre de todos los usuarios de su organización. Haga esto para que los usuarios no tengan que revisar y aceptar los permisos solicitados por la aplicación cuando inicien la aplicación. Además, según la [configuración de consentimiento](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent) del usuario en Azure Active Directory (Azure ad), es posible que algunos usuarios no puedan conceder consentimiento a las aplicaciones que tienen acceso a los datos de la empresa.

Entre los ejemplos de permisos solicitados por las aplicaciones se incluye la capacidad de leer información almacenada en un equipo, leer el perfil de un usuario y enviar un correo electrónico en nombre de los usuarios. Para obtener más información, consulte [permisos y consentimiento en el punto de conexión de la plataforma de identidades de Microsoft](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent). 

La columna **permisos** indica si una aplicación tiene permisos que necesitan consentimiento. Verá un vínculo **Ver detalles** para cada aplicación registrada en Azure ad que tenga permisos que necesiten conceder. Tenga en cuenta que esto solo se aplica a aplicaciones personalizadas y de terceros y. No verá este vínculo o tendrá que conceder consentimiento de administrador para las aplicaciones publicadas por Microsoft.

:::image type="content" source="media/app-perm-admin-center-permissions-column.png" alt-text="Captura de pantalla de la columna permisos en la página Administrar aplicaciones":::

Para conceder el consentimiento de toda la organización a una aplicación, siga estos pasos:

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **aplicaciones de Teams**  >  **Manage apps**.
2. Realice una de las siguientes acciones:
    - Busque la aplicación que desee, haga clic en el nombre de la aplicación para ir a la página de detalles de la aplicación y, a continuación, seleccione la pestaña **permisos** .
    - Ordene la columna **permisos** en orden descendente para buscar la aplicación y, a continuación, seleccione **Ver detalles**. Esto lo llevará a la pestaña **permisos** de la página de detalles de la aplicación.

3. En **permisos de toda la organización**, seleccione **revisar permisos y consentimiento**.

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="Captura de pantalla de los permisos de toda la organización en la pestaña permisos de una aplicación":::

    Para ello, debe ser un administrador global. Esta opción no está disponible para los administradores de servicios de Teams.

4. En la pestaña **permisos** , revise los permisos solicitados por la aplicación.

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="Captura de pantalla de los permisos solicitados por una aplicación":::

    > [!IMPORTANT]
    > Conceder el consentimiento de toda la organización para una aplicación permite a la aplicación acceder a los datos de la organización. Revise detenidamente los permisos solicitados por la aplicación antes de conceder su consentimiento.
5. Si está de acuerdo con los permisos solicitados por la aplicación, haga clic en **Aceptar** para conceder consentimiento. Aparece un banner temporalmente en la parte superior de la página para informarle que se han concedido los permisos solicitados para la aplicación. La aplicación ahora tiene acceso a los recursos especificados para todos los usuarios de la organización y nadie más deberá revisar los permisos.

Después de aceptar los permisos, verá un mensaje en permisos para **toda la organización** en la página de detalles de la aplicación para informarle de que se ha otorgado el consentimiento. Para ver los detalles de los permisos de la aplicación, haga clic en el vínculo **Azure Active Directory** para ir a la página de la aplicación en el portal de Azure ad.

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted.png" alt-text="Captura de pantalla del mensaje que se muestra cuando se concede el consentimiento":::

Si los usuarios de su organización pueden conceder consentimiento y si uno o más usuarios tienen el consentimiento de una aplicación en particular, también verá el mismo mensaje para informarle que se ha otorgado el consentimiento y el vínculo de Azure Active Directory a la página de la aplicación en el portal de Azure AD.

> [!NOTE]
> Aunque la opción **revisar permisos y consentimiento** no está disponible para los administradores de servicio de Teams y no puede conceder el consentimiento del administrador de toda la organización a las aplicaciones, los administradores del servicio Teams pueden ver el contenido en la pestaña **permisos** de una aplicación. Por ejemplo, un administrador de servicios de equipo puede hacer clic en el vínculo de **Azure Active Directory** para ver los detalles de los permisos de aplicaciones en el portal de Azure ad. 

## <a name="view-resource-specific-consent-permissions-of-an-app"></a>Ver permisos de consentimiento específicos de recursos de una aplicación

Los permisos RSC permiten a los propietarios del equipo conceder el consentimiento para que una aplicación pueda acceder y modificar los datos de un equipo. Los permisos RSC son granulares, permisos específicos de teams que definen lo que una aplicación puede hacer en un equipo específico. Algunos ejemplos de permisos RSC incluyen la posibilidad de crear y eliminar canales, obtener la configuración de un equipo y crear y quitar pestañas de canal. 

Los permisos RSC se definen en el manifiesto de la aplicación y no en Azure AD. Puede conceder consentimiento a los permisos RSC al agregar la aplicación a un equipo. Para obtener más información, consulta [el consentimiento específico de recursos (RSC)](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent).

Los administradores globales y el administrador de servicios de equipos pueden ver los permisos RSC para una aplicación en la pestaña **permisos** de la página de detalles de la aplicación. 

Para ver los permisos RSC para una aplicación, siga estos pasos:

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **aplicaciones de Teams**  >  **Manage apps**.
2. Busque la aplicación que desee, haga clic en el nombre de la aplicación para ir a la página de detalles de la aplicación y, a continuación, seleccione la pestaña **permisos** .
3. En **permisos de consentimiento específico de recursos (RSC) de Microsoft Graph**, revise los permisos RSC solicitados por la aplicación.

    :::image type="content" source="media/app-perm-admin-center-rsc.png" alt-text="Captura de pantalla de permisos RSC para una aplicación":::

## <a name="known-issues"></a>Problemas conocidos

### <a name="the-view-details-link-isnt-displayed-in-the-permissions-column-for-some-third-party-apps-that-request-permissions"></a>El vínculo "ver detalles" no se muestra en la columna permisos para algunas aplicaciones de terceros que solicitan permisos

Por el momento, la capacidad de revisar los permisos y conceder consentimiento no está disponible para todas las aplicaciones de terceros registradas en Azure AD que solicitan permisos. En lugar del vínculo **Ver detalles** , verá **--** en la columna **permisos** . Estamos trabajando con los ISV para habilitar esta característica para sus aplicaciones.

## <a name="related-topics"></a>Temas relacionados

- [Administrar las aplicaciones en el centro de administración de Microsoft Teams](manage-apps.md)
- [Permisos y consentimiento en el punto de conexión de la plataforma de identidades de Microsoft](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent)
- [Consentimiento específico de recursos en Teams](resource-specific-consent.md)
- [Consentimiento específico de recursos (RSC)](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent)


