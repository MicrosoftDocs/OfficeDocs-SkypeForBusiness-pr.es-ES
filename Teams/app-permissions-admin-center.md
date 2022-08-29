---
title: Ver permisos de aplicaciones y conceder consentimiento de administrador en el Centro de administración de Microsoft Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo ver los permisos solicitados por las aplicaciones y conceder el consentimiento del administrador a las aplicaciones en la página Administrar aplicaciones del Centro de administración de Microsoft Teams.
ms.localizationpriority: medium
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f9ec44990728feac5982641ce80ff15442bcaf7d
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2022
ms.locfileid: "67396491"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a>Ver permisos de aplicaciones y conceder consentimiento de administrador en el Centro de administración de Microsoft Teams

Los administradores ven y administran todas las aplicaciones de Teams desde la página Administrar aplicaciones del Centro de administración de Teams. Puede administrar las aplicaciones personalizadas creadas dentro de su organización y disponibles solo para los usuarios finales y administrar los terceros disponibles en la tienda de aplicaciones de Teams. Por ejemplo, puede ver el estado y las propiedades de nivel de organización de las aplicaciones, aprobar o cargar nuevas aplicaciones personalizadas en la tienda de aplicaciones de su organización, permitir aplicaciones en el nivel de la organización o para usuarios finales individuales.

Aquí, también puede otorgar el consentimiento del administrador de toda la organización a las aplicaciones que solicitan permisos para acceder a los datos y ver los permisos de consentimiento específico de recursos (RSC) para las aplicaciones.

## <a name="grant-org-wide-admin-consent-to-an-app"></a>Otorgar el consentimiento del administrador de toda la organización a una aplicación

Si es un administrador global, puede revisar y dar su consentimiento a las aplicaciones que solicitan permisos en nombre de todos los usuarios de la organización. Esto se hace para que los usuarios no tengan que revisar y aceptar los permisos solicitados por la aplicación cuando inician la aplicación. Además, según la [configuración de consentimiento](/azure/active-directory/manage-apps/configure-user-consent) del usuario en Azure Active Directory (Azure AD), es posible que algunos usuarios no puedan conceder consentimiento a las aplicaciones que acceden a los datos de la empresa.

Algunos ejemplos de permisos solicitados por las aplicaciones incluyen la capacidad de leer información almacenada en un equipo, leer el perfil de un usuario y enviar un correo electrónico en nombre de los usuarios. Para obtener más información, consulte [Permisos y consentimiento en el extremo de la plataforma de identidad de Microsoft](/azure/active-directory/develop/v2-permissions-and-consent).

La columna **Permisos** indica si una aplicación tiene permisos que necesitan consentimiento. Verá un vínculo **Ver detalles** para cada aplicación registrada en Azure AD que tengan permisos que necesiten consentimiento. Tenga en cuenta que esto solo se aplica a aplicaciones personalizadas y de terceros. El vínculo no está disponible para las aplicaciones proporcionadas por Microsoft. Además, los administradores no tienen que conceder consentimiento para dichas aplicaciones.

Para conceder el consentimiento de toda la organización a una aplicación, siga estos pasos:

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Aplicaciones de Teams** > **[Administrar aplicaciones](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Realice una de las siguientes acciones:
    * Busca la aplicación que quieras, selecciona el nombre de la aplicación para ir a la página de detalles de la aplicación y, a continuación, selecciona la pestaña **Permisos** .
    * Ordene la columna **Permisos** en orden descendente para buscar la aplicación y, a continuación, seleccione **Ver detalles**. Al hacerlo, te llevará a la pestaña **Permisos** de la página de detalles de la aplicación.

1. En **Permisos de toda la organización**, seleccione **Revisar permisos y consentimiento**.

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text=" Captura de pantalla de los permisos de toda la organización en la pestaña Permisos de una aplicación.":::

    Debe ser un administrador global para hacer esto. Esta opción no está disponible para los administradores del servicio de Teams.

1. En la pestaña **Permisos**, revise los permisos solicitados por la aplicación.

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text=" Captura de pantalla de los permisos solicitados por una aplicación.":::

    > [!IMPORTANT]
    > Otorgar el consentimiento de toda la organización a una aplicación permite que la aplicación acceda a los datos de su organización. Revise cuidadosamente los permisos solicitados por la aplicación antes de otorgar el consentimiento.

1. Si estás de acuerdo con los permisos solicitados por la aplicación, selecciona **Aceptar** para conceder consentimiento. Aparecerá temporalmente una pancarta en la parte superior de la página para informarle de que se han concedido los permisos solicitados para la aplicación. La aplicación ahora tiene acceso a los recursos especificados para todos los usuarios de la organización y no se pedirá a nadie más que revise los permisos.

Después de aceptar los permisos, verá un mensaje en **Permisos de toda la organización** en la página de detalles de la aplicación para informarle de que se ha otorgado el consentimiento. Para ver detalles sobre los permisos de la aplicación, seleccione el vínculo **de Azure Active Directory** para ir a la página de la aplicación en el portal de Azure AD.

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
1. Busca la aplicación que quieras, selecciona el nombre de la aplicación para ir a la página de detalles de la aplicación y, a continuación, selecciona la pestaña **Permisos** .
1. En **Microsoft Graph permisos de consentimiento específico del recurso (RSC**), revise los permisos RSC solicitados por la aplicación.

    :::image type="content" source="media/app-perm-admin-center-rsc-new.png" alt-text=" Captura de pantalla de los permisos RSC para una aplicación.":::

## <a name="known-issues"></a>Problemas conocidos

### <a name="the-view-details-link-isnt-displayed-in-the-permissions-column-for-some-third-party-apps-that-request-permissions"></a>El vínculo "Ver detalles" no se muestra en la columna Permisos para algunas aplicaciones de terceros que solicitan permisos

La capacidad de revisar los permisos y dar consentimiento no está disponible para todas las aplicaciones de terceros. Normalmente, las aplicaciones de terceros se registran en Azure Active Directory cuando las aplicaciones solicitan permisos. En lugar del vínculo **Ver detalles**, verá `--` en la columna **Permisos**.

## <a name="related-articles"></a>Artículos relacionados

* [Administrar aplicaciones en el Centro de administración de Microsoft Teams](manage-apps.md)
* [Permisos y consentimiento en el extremo de la plataforma de identidad de Microsoft](/azure/active-directory/develop/v2-permissions-and-consent)
* [Consentimiento específico de recursos en Teams](resource-specific-consent.md)
* [Consentimiento específico de recursos (RSC)](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
* [Navegar por el ciclo de vida de la aplicación Teams](https://aka.ms/PR132) (sesión de Ignite 2020)
