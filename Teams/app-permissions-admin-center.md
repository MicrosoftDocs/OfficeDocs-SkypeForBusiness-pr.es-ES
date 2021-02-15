---
title: Ver permisos de aplicación y conceder consentimiento de administrador en el Centro de administración de Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: vaibhava
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo ver los permisos solicitados por las aplicaciones y conceder el consentimiento del administrador para las aplicaciones en la página Administrar aplicaciones del Centro de administración de Microsoft Teams.
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6ec41760a7edd7de52d15995f39365b300cd797e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827540"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a>Ver permisos de aplicación y conceder consentimiento de administrador en el Centro de administración de Microsoft Teams

La [página Administrar](manage-apps.md) aplicaciones del Centro de administración de Microsoft Teams es el lugar donde puede ver y administrar todas las aplicaciones de Teams de su organización. Por ejemplo, puede ver el estado y las propiedades de nivel de la organización de las aplicaciones, aprobar o cargar nuevas aplicaciones personalizadas en la tienda de aplicaciones de su organización, bloquear o permitir aplicaciones en el nivel de la organización, y administrar la configuración de aplicaciones para toda la organización.

Aquí, también puede conceder consentimiento de administrador para toda la organización para las aplicaciones que solicitan permisos para obtener acceso a datos y ver permisos de consentimiento específico de recursos para aplicaciones.

## <a name="grant-org-wide-admin-consent-to-an-app"></a>Conceder consentimiento para administradores de toda la organización a una aplicación

Si es administrador global, puede revisar y conceder el consentimiento a las aplicaciones que solicitan permisos en nombre de todos los usuarios de su organización. Haga esto para que los usuarios no tengan que revisar y aceptar los permisos solicitados por la aplicación al iniciar la aplicación. Además, según la configuración [](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent) de consentimiento del usuario en Azure Active Directory (Azure AD), es posible que algunos usuarios no puedan conceder consentimiento a las aplicaciones que tienen acceso a los datos de la compañía.

Algunos ejemplos de permisos solicitados por las aplicaciones son la capacidad de leer información almacenada en un equipo, leer el perfil de un usuario y enviar un correo electrónico en nombre de los usuarios. Para obtener más información, consulte Permisos y consentimiento en el punto de conexión [de la plataforma de identidad de Microsoft.](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent) 

La **columna Permisos** indica si una aplicación tiene permisos que necesitan consentimiento. Verás un vínculo Ver detalles **para** cada aplicación registrada en Azure AD que tenga permisos que necesiten consentimiento. Tenga en cuenta que esto solo se aplica a aplicaciones personalizadas y de terceros. No verá este vínculo o necesita conceder el consentimiento del administrador para las aplicaciones publicadas por Microsoft.

:::image type="content" source="media/app-perm-admin-center-permissions-column.png" alt-text="Captura de pantalla de la columna Permisos en la página Administrar aplicaciones":::

Para conceder el consentimiento de toda la organización a una aplicación, siga estos pasos:

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Administrar aplicaciones**  >  **de** Teams.
2. Realice una de las siguientes acciones:
    - Busque la aplicación que desee, haga clic en el nombre de la aplicación para ir a la página de detalles de la aplicación y, a continuación, seleccione la **pestaña** Permisos.
    - Ordene **la columna Permisos** en orden descendente para buscar la aplicación y, a continuación, seleccione Ver **detalles.** Si lo hace, se le llevará a **la pestaña Permisos** de la página de detalles de la aplicación.

3. En **Permisos para toda la organización,** seleccione Revisar permisos y **consentimiento.**

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="Captura de pantalla de permisos para toda la organización en la pestaña Permisos para una aplicación":::

    Para ello, debe ser administrador global. Esta opción no está disponible para los administradores de servicios de Teams.

4. En la **pestaña Permisos,** revise los permisos solicitados por la aplicación.

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="Captura de pantalla de los permisos solicitados por una aplicación":::

    > [!IMPORTANT]
    > Conceder el consentimiento de toda la organización a una aplicación permite que la aplicación obtenga acceso a los datos de su organización. Revise detenidamente los permisos solicitados por la aplicación antes de conceder el consentimiento.
5. Si estás de acuerdo con los permisos solicitados por la aplicación, haz clic en **Aceptar** para conceder el consentimiento. Un banner aparece temporalmente en la parte superior de la página para informarte de que los permisos solicitados se han concedido para la aplicación. La aplicación ahora tiene acceso a los recursos especificados para todos los usuarios de su organización y nadie más se le pedirá que revise los permisos.

Después de aceptar los permisos, verá un  mensaje en permisos para toda la organización en la página de detalles de la aplicación para que sepa que se ha concedido el consentimiento. Para ver detalles sobre los permisos de la aplicación, haga clic en el vínculo de **Azure Active Directory** para ir a la página de la aplicación en el portal de Azure AD.

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted.png" alt-text="Captura de pantalla del mensaje que se muestra cuando se concede el consentimiento":::

Si los usuarios de su organización tienen permiso para conceder consentimiento y uno o más usuarios conceden el consentimiento a una aplicación en particular, también verá el mismo mensaje para que sepa que se ha concedido el consentimiento y el vínculo de Azure Active Directory a la página de la aplicación en el portal de Azure AD.

> [!NOTE]
> Aunque la  opción Revisar permisos y consentimiento no está disponible para los administradores de servicios de Teams y no pueden conceder  consentimiento para administradores de toda la organización para las aplicaciones, los administradores del servicio de Teams pueden ver el contenido en la pestaña Permisos de una aplicación. Por ejemplo, un administrador de servicios de Teams puede hacer clic en el vínculo de **Azure Active Directory** para ver los detalles de los permisos de la aplicación en el portal de Azure AD. 

## <a name="view-resource-specific-consent-permissions-of-an-app"></a>Ver permisos de consentimiento específicos de recursos de una aplicación

Los permisos de RSC permiten a los propietarios del equipo conceder el consentimiento para que una aplicación acceda a los datos de un equipo y modifique estos. Los permisos RSC son permisos específicos de Teams específicos pormenorizados que definen lo que una aplicación puede hacer en un equipo específico. Algunos ejemplos de permisos RSC son la posibilidad de crear y eliminar canales, obtener la configuración de un equipo y crear y quitar fichas de canales. 

Los permisos RSC se definen en el manifiesto de la aplicación, no en Azure AD. Al agregar la aplicación a un equipo, concede su consentimiento a los permisos de RSC. Para obtener más información, [consulte consentimiento específico de recursos (RSC).](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent)

Los administradores globales y los administradores del servicio de  Teams pueden ver los permisos RSC de una aplicación en la pestaña Permisos de la página de detalles de la aplicación. 

Para ver los permisos de RSC para una aplicación, siga estos pasos:

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Administrar aplicaciones**  >  **de** Teams.
2. Busque la aplicación que desee, haga clic en el nombre de la aplicación para ir a la página de detalles de la aplicación y, a continuación, seleccione la **pestaña** Permisos.
3. En los permisos de consentimiento específico de recursos **de Microsoft Graph (RSC),** revise los permisos RSC solicitados por la aplicación.

    :::image type="content" source="media/app-perm-admin-center-rsc.png" alt-text="Captura de pantalla de los permisos de RSC para una aplicación":::

## <a name="known-issues"></a>Problemas conocidos

### <a name="the-view-details-link-isnt-displayed-in-the-permissions-column-for-some-third-party-apps-that-request-permissions"></a>El vínculo "Ver detalles" no se muestra en la columna Permisos para algunas aplicaciones de terceros que solicitan permisos

Actualmente, la capacidad para revisar los permisos y conceder consentimiento no está disponible para todas las aplicaciones de terceros registradas en Azure AD que solicitan permisos. En lugar **del vínculo Ver** detalles, verá en la **--** **columna** Permisos. Estamos trabajando con ISV para habilitar esta característica para sus aplicaciones.

## <a name="related-topics"></a>Temas relacionados

- [Administrar las aplicaciones en el Centro de administración de Microsoft Teams](manage-apps.md)
- [Permisos y consentimiento en el punto de conexión de la plataforma de identidad de Microsoft](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent)
- [Consentimiento específico de recursos en Teams](resource-specific-consent.md)
- [Consentimiento específico de recursos (RSC)](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
- [Navegar por el ciclo de vida de la](https://aka.ms/PR132) aplicación Teams (sesión Ignite 2020)


