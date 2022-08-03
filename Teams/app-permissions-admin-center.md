---
title: Ver permisos de aplicaciones y conceder consentimiento de administrador en el Centro de administración de Microsoft Teams
author: guptaashish
ms.author: guptaashish
ms.reviewer: vaibhava
manager: prkosh
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo ver los permisos solicitados por las aplicaciones y conceder el consentimiento del administrador a las aplicaciones en la página Administrar aplicaciones del Centro de administración de Microsoft Teams.
ms.localizationpriority: high
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1e3d7ca4f86660080cb387a9d4cd80927f296040
ms.sourcegitcommit: a64574da14969a33a77c7d979ffde452b5b3a531
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/02/2022
ms.locfileid: "67175654"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a>Ver permisos de aplicaciones y conceder consentimiento de administrador en el Centro de administración de Microsoft Teams

La página [Administrar aplicaciones](manage-apps.md) del Centro de administración de Microsoft Teams es donde puede ver y administrar todas las aplicaciones de Teams para su organización. Por ejemplo, puede ver el estado y las propiedades de las aplicaciones a nivel de organización, aprobar o cargar nuevas aplicaciones personalizadas en la tienda de aplicaciones de su organización, bloquear o permitir aplicaciones en el nivel de organización y administrar la configuración de aplicaciones de toda la organización.

Aquí, también puede otorgar el consentimiento del administrador de toda la organización a las aplicaciones que solicitan permisos para acceder a los datos y ver los permisos de consentimiento específico de recursos (RSC) para las aplicaciones.

## <a name="grant-org-wide-admin-consent-to-an-app"></a>Otorgar el consentimiento del administrador de toda la organización a una aplicación

Si es un administrador global, puede revisar y conceder consentimiento a las aplicaciones que solicitan permisos en nombre de todos los usuarios de su organización. Esto se hace para que los usuarios no tengan que revisar y aceptar los permisos solicitados por la aplicación cuando inician la aplicación. Además, según la [configuración de consentimiento](/azure/active-directory/manage-apps/configure-user-consent) del usuario en Azure Active Directory (Azure AD), es posible que algunos usuarios no puedan conceder consentimiento a las aplicaciones que acceden a los datos de la empresa.

Algunos ejemplos de permisos solicitados por las aplicaciones incluyen la capacidad de leer información almacenada en un equipo, leer el perfil de un usuario y enviar un correo electrónico en nombre de los usuarios. Para obtener más información, consulte [Permisos y consentimiento en el extremo de la plataforma de identidad de Microsoft](/azure/active-directory/develop/v2-permissions-and-consent).

La columna **Permisos** indica si una aplicación tiene permisos que necesitan consentimiento. Verá un vínculo **Ver detalles** para cada aplicación registrada en Azure AD que tengan permisos que necesiten consentimiento. Tenga en cuenta que esto solo se aplica a aplicaciones personalizadas y de terceros. El vínculo no está disponible para las aplicaciones proporcionadas por Microsoft. Además, los administradores no tienen que otorgar su consentimiento para dichas aplicaciones.

Para conceder el consentimiento de toda la organización a una aplicación, siga estos pasos:

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Aplicaciones de Teams** > **[Administrar aplicaciones](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Realice una de las siguientes acciones:
    * Busque la aplicación que desee, haga clic en el nombre de la aplicación para ir a la página de detalles de la aplicación y, a continuación, seleccione la pestaña **Permisos**.
    * Ordene la columna **Permisos** en orden descendente para buscar la aplicación y, a continuación, seleccione **Ver detalles**. Al hacerlo, te llevará a la pestaña **Permisos** de la página de detalles de la aplicación.

1. En **Permisos de toda la organización**, seleccione **Revisar permisos y consentimiento**.

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text=" Captura de pantalla de los permisos de toda la organización en la pestaña Permisos de una aplicación.":::

    Debe ser un administrador global para hacer esto. Esta opción no está disponible para los administradores del servicio de Teams.

1. En la pestaña **Permisos**, revise los permisos solicitados por la aplicación.

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text=" Captura de pantalla de los permisos solicitados por una aplicación.":::

    > [!IMPORTANT]
    > Otorgar el consentimiento de toda la organización a una aplicación permite que la aplicación acceda a los datos de su organización. Revise cuidadosamente los permisos solicitados por la aplicación antes de otorgar el consentimiento.

1. Si está de acuerdo con los permisos solicitados por la aplicación, seleccione **Aceptar** para otorgar el consentimiento. Aparecerá temporalmente una pancarta en la parte superior de la página para informarle de que se han concedido los permisos solicitados para la aplicación. La aplicación ahora tiene acceso a los recursos especificados para todos los usuarios de la organización y no se pedirá a nadie más que revise los permisos.

Después de aceptar los permisos, verá un mensaje en **Permisos de toda la organización** en la página de detalles de la aplicación para informarle de que se ha otorgado el consentimiento. Para ver detalles sobre los permisos de la aplicación, seleccione el vínculo **Azure Active Directory** para ir a la página de la aplicación en el portal Azure AD.

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted-new.png" alt-text="Captura de pantalla del mensaje que se muestra cuando se otorga el consentimiento.":::

Si a los usuarios de su organización se les permite otorgar consentimiento y si uno o más usuarios dieron su consentimiento a una aplicación en particular, también verá el mismo mensaje para informarle de que se otorgó el consentimiento y el vínculo de Azure Active Directory a la página de la aplicación en el portal de Azure AD.

> [!NOTE]
> Aunque, la opción **Revisar permisos y consentimiento** no está disponible para los administradores del servicio de Teams y no pueden conceder el consentimiento del administrador de toda la organización a las aplicaciones, los administradores del servicio de Teams pueden ver el contenido en la pestaña **Permissions** de una aplicación. Por ejemplo, un administrador de servicios de Teams puede hacer clic en el vínculo **Azure Active Directory** para ver los detalles de permisos de la aplicación en el portal de Azure AD.

## <a name="view-resource-specific-consent-permissions-of-an-app"></a>Vista de permisos de consentimiento específicos de recursos de una aplicación

Los permisos RSC permiten a los propietarios de equipos otorgar consentimiento para que una aplicación acceda a los datos de un equipo y los modifique. Los permisos RSC son permisos granulares específicos de Teams que definen lo que una aplicación puede hacer en un equipo específico. Algunos ejemplos de permisos de RSC incluyen la capacidad de crear y eliminar canales, obtener la configuración de un equipo y crear y eliminar pestañas de canal.

Los permisos RSC se definen en el manifiesto de la aplicación y no en Azure AD. Concede el consentimiento a los permisos RSC cuando agrega la aplicación a un equipo. Para obtener más información, consulte [ Consentimiento específico del recurso (RSC)](/microsoftteams/platform/graph-api/rsc/resource-specific-consent).

Los administradores globales y el administrador de servicios de Teams pueden ver los permisos de RSC para una aplicación en la pestaña **Permisos** de la página de detalles de la aplicación.

Para ver los permisos de RSC para una aplicación, siga estos pasos:

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Aplicaciones de Teams** > **Administrar aplicaciones**.
1. Busque la aplicación que desee, haga clic en el nombre de la aplicación para ir a la página de detalles de la aplicación y, a continuación, seleccione la pestaña **Permisos**.
1. En **Microsoft Graph permisos de consentimiento específico del recurso (RSC**), revise los permisos RSC solicitados por la aplicación.

    :::image type="content" source="media/app-perm-admin-center-rsc-new.png" alt-text=" Captura de pantalla de los permisos RSC para una aplicación.":::

## <a name="known-issues"></a>Problemas conocidos

### <a name="the-view-details-link-isnt-displayed-in-the-permissions-column-for-some-third-party-apps-that-request-permissions"></a>El vínculo "Ver detalles" no se muestra en la columna Permisos para algunas aplicaciones de terceros que solicitan permisos

Actualmente, la capacidad de revisar permisos y conceder consentimiento no está disponible para todas las aplicaciones de terceros registradas en Azure AD que solicitan permisos. En lugar del vínculo **Ver detalles**, verá **--** en la columna **Permisos**. Estamos trabajando con ISV para habilitar esta función para sus aplicaciones.

## <a name="related-topics"></a>Temas relacionados

* [Administre las aplicaciones en el Centro de administración de Microsoft Teams](manage-apps.md)
* [Permisos y consentimiento en el extremo de la plataforma de identidad de Microsoft](/azure/active-directory/develop/v2-permissions-and-consent)
* [Consentimiento específico de recursos en Teams](resource-specific-consent.md)
* [Consentimiento específico de recursos (RSC)](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
* [Navegar por el ciclo de vida de la aplicación Teams](https://aka.ms/PR132) (sesión de Ignite 2020)
