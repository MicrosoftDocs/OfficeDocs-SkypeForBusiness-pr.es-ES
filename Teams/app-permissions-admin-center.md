---
title: Ver permisos de aplicación y conceder consentimiento de administrador en el Microsoft Teams de administración
author: cichur
ms.author: v-cichur
ms.reviewer: vaibhava
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo ver los permisos solicitados por las aplicaciones y conceder el consentimiento de administrador a las aplicaciones en la página Administrar aplicaciones del centro de Microsoft Teams administración.
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2833a548ccf66b327d9feb71155f1ed33a671f1c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094662"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a>Ver permisos de aplicación y conceder consentimiento de administrador en el Microsoft Teams de administración

La [página Administrar aplicaciones](manage-apps.md) del centro Microsoft Teams administración es donde puede ver y administrar todas las Teams aplicaciones de su organización. Por ejemplo, puede ver el estado y las propiedades de las aplicaciones a nivel de organización, aprobar o cargar nuevas aplicaciones personalizadas en la tienda de aplicaciones de su organización, bloquear o permitir aplicaciones en el nivel de la organización y administrar la configuración de aplicaciones para toda la organización.

Aquí, también puede conceder consentimiento de administrador para toda la organización a las aplicaciones que solicitan permisos para obtener acceso a datos y ver permisos de consentimiento específico de recursos (RSC) para aplicaciones.

## <a name="grant-org-wide-admin-consent-to-an-app"></a>Conceder consentimiento de administrador para toda la organización a una aplicación

Si es administrador global, puede revisar y conceder consentimiento a las aplicaciones que soliciten permisos en nombre de todos los usuarios de su organización. Haga esto para que los usuarios no tengan que revisar y aceptar los permisos solicitados por la aplicación al iniciar la aplicación. Además, según la configuración [](/azure/active-directory/manage-apps/configure-user-consent) de consentimiento del usuario en Azure Active Directory (Azure AD), es posible que algunos usuarios no puedan conceder consentimiento a las aplicaciones que tienen acceso a los datos de la empresa.

Algunos ejemplos de permisos solicitados por las aplicaciones son la capacidad de leer la información almacenada en un equipo, leer el perfil de un usuario y enviar un correo electrónico en nombre de los usuarios. Para obtener más información, vea [Permisos y consentimiento en el Plataforma de identidad de Microsoft de conexión](/azure/active-directory/develop/v2-permissions-and-consent). 

La **columna Permisos** indica si una aplicación tiene permisos que necesitan consentimiento. Verá un vínculo **Ver** detalles para cada aplicación registrada en Azure AD que tenga permisos que necesiten consentimiento. Tenga en cuenta que esto solo se aplica a aplicaciones personalizadas y de terceros. No verá este vínculo ni tendrá que conceder el consentimiento de administrador para las aplicaciones publicadas por Microsoft.

:::image type="content" source="media/app-perm-admin-center-permissions-column.png" alt-text="Captura de pantalla de la columna Permisos en la página Administrar aplicaciones":::

Para conceder el consentimiento de toda la organización a una aplicación, siga estos pasos:

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Aplicaciones de Teams** > **Administrar aplicaciones**.
2. Realice una de las siguientes acciones:
    - Busque la aplicación que desee, haga clic en el nombre de la aplicación para ir a la página de detalles de la aplicación y, a continuación, seleccione la **pestaña** Permisos.
    - Ordene la **columna Permisos** en orden descendente para buscar la aplicación y, a continuación, seleccione **Ver detalles.** Esto le lleva a la **pestaña Permisos** de la página de detalles de la aplicación.

3. En **Permisos para toda la organización,** seleccione Revisar permisos y **consentimiento.**

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="Captura de pantalla de permisos de toda la organización en la pestaña Permisos de una aplicación":::

    Para ello, debe ser administrador global. Esta opción no está disponible para los Teams de servicio.

4. En la **pestaña Permisos,** revise los permisos solicitados por la aplicación.

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="Captura de pantalla de los permisos solicitados por una aplicación":::

    > [!IMPORTANT]
    > Conceder el consentimiento de toda la organización a una aplicación permite que la aplicación obtenga acceso a los datos de su organización. Revise detenidamente los permisos solicitados por la aplicación antes de conceder su consentimiento.
5. Si está de acuerdo con los permisos solicitados por la aplicación, haga clic **en Aceptar** para conceder el consentimiento. Aparece temporalmente un banner en la parte superior de la página para informarte de que se han concedido los permisos solicitados para la aplicación. La aplicación ahora tiene acceso a los recursos especificados para todos los usuarios de su organización y nadie más se le pedirá que revise los permisos.

Después de aceptar los permisos, verá un  mensaje en Permisos para toda la organización en la página de detalles de la aplicación para que sepa que se ha concedido el consentimiento. Para ver detalles sobre los permisos de la aplicación, haga clic en el vínculo Azure Active Directory para ir **a** la página de la aplicación en el portal de Azure AD.

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted.png" alt-text="Captura de pantalla del mensaje que se muestra cuando se concede el consentimiento":::

Si los usuarios de su organización pueden conceder consentimiento y si uno o varios usuarios han concedido el consentimiento a una aplicación en particular, también verá el mismo mensaje para que sepa que se ha concedido el consentimiento y el vínculo Azure Active Directory a la página de la aplicación en el portal de Azure AD.

> [!NOTE]
> Aunque la  opción Revisar permisos y consentimiento no está disponible para los administradores de servicios de Teams y no pueden conceder el consentimiento  de administrador de toda la organización a las aplicaciones, los administradores de servicios de Teams pueden ver el contenido en la pestaña Permisos de una aplicación. Por ejemplo, un Teams de servicio puede hacer clic en el vínculo **Azure Active Directory** para ver los detalles de permisos de la aplicación en el portal de Azure AD. 

## <a name="view-resource-specific-consent-permissions-of-an-app"></a>Ver permisos de consentimiento específicos de recursos de una aplicación

Los permisos de RSC permiten a los propietarios de equipos conceder consentimiento para que una aplicación acceda y modifique los datos de un equipo. Los permisos RSC son permisos granulares Teams específicos que definen lo que una aplicación puede hacer en un equipo específico. Algunos ejemplos de permisos de RSC son la posibilidad de crear y eliminar canales, obtener la configuración de un equipo y crear y quitar pestañas de canal. 

Los permisos RSC se definen en el manifiesto de la aplicación y no en Azure AD. Al agregar la aplicación a un equipo, concede su consentimiento a los permisos de RSC. Para obtener más información, vea [Consentimiento específico de recursos (RSC).](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)

Los administradores globales y Teams de servicio pueden ver los permisos  de RSC para una aplicación en la pestaña Permisos de la página de detalles de la aplicación. 

Para ver los permisos de RSC para una aplicación, siga estos pasos:

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Aplicaciones de Teams** > **Administrar aplicaciones**.
2. Busque la aplicación que desee, haga clic en el nombre de la aplicación para ir a la página de detalles de la aplicación y, a continuación, seleccione la **pestaña** Permisos.
3. En Microsoft Graph permisos de consentimiento específico de recursos **(RSC),** revise los permisos de RSC solicitados por la aplicación.

    :::image type="content" source="media/app-perm-admin-center-rsc.png" alt-text="Captura de pantalla de los permisos de RSC para una aplicación":::

## <a name="known-issues"></a>Problemas conocidos

### <a name="the-view-details-link-isnt-displayed-in-the-permissions-column-for-some-third-party-apps-that-request-permissions"></a>El vínculo "Ver detalles" no se muestra en la columna Permisos para algunas aplicaciones de terceros que solicitan permisos

Actualmente, la capacidad de revisar permisos y conceder consentimiento no está disponible para todas las aplicaciones de terceros registradas en Azure AD que soliciten permisos. En lugar del **vínculo Ver detalles,** verá **--** en la columna **Permisos.** Estamos trabajando con ISV para habilitar esta característica para sus aplicaciones.

## <a name="related-topics"></a>Temas relacionados

- [Administrar las aplicaciones en el centro Microsoft Teams administración](manage-apps.md)
- [Permisos y consentimiento en el punto de conexión Plataforma de identidad de Microsoft usuario](/azure/active-directory/develop/v2-permissions-and-consent)
- [Consentimiento específico de recursos en Teams](resource-specific-consent.md)
- [Consentimiento específico de recursos (RSC)](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
- [Navegar por el ciclo Teams de](https://aka.ms/PR132) la aplicación (sesión de Ignite 2020)