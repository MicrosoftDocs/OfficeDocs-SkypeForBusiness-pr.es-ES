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
description: Obtenga información sobre cómo ver los permisos solicitados por las aplicaciones y conceder consentimiento de administrador a las aplicaciones en la página Administrar aplicaciones del centro de administración de Microsoft Teams.
ms.localizationpriority: medium
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 54fbd67fffa666e7f07719305075be264f077976
ms.sourcegitcommit: f3c380f745af4c3aaa2720234860b45696a0c333
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2022
ms.locfileid: "63442276"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a>Ver permisos de aplicaciones y conceder consentimiento de administrador en el Centro de administración de Microsoft Teams

La página [Administrar aplicaciones](manage-apps.md) del centro de administración de Microsoft Teams es donde puede ver y administrar todas las aplicaciones Teams de su organización. Por ejemplo, puede ver el estado y las propiedades de nivel de organización de las aplicaciones, aprobar o cargar nuevas aplicaciones personalizadas en la tienda de aplicaciones de su organización, bloquear o permitir aplicaciones en el nivel de la organización y administrar la configuración de aplicaciones de toda la organización.

Aquí, también puede conceder consentimiento de administrador para toda la organización a las aplicaciones que solicitan permisos para acceder a datos y ver permisos de consentimiento específico de recursos (RSC) para las aplicaciones.

## <a name="grant-org-wide-admin-consent-to-an-app"></a>Conceder consentimiento de administrador para toda la organización a una aplicación

Si es administrador global, puede revisar y dar su consentimiento a las aplicaciones que solicitan permisos en nombre de todos los usuarios de su organización. Esto se hace para que los usuarios no tengan que revisar ni aceptar los permisos solicitados por la aplicación cuando inicien la aplicación. Además, en función de la [configuración de consentimiento](/azure/active-directory/manage-apps/configure-user-consent) del usuario en Azure Active Directory (Azure AD), es posible que algunos usuarios no puedan dar su consentimiento a las aplicaciones que tienen acceso a los datos de la compañía.

Algunos ejemplos de permisos solicitados por las aplicaciones son la capacidad de leer la información almacenada en un equipo, leer el perfil de un usuario y enviar un correo electrónico en nombre de los usuarios. Para obtener más información, consulte [Permisos y consentimiento en el punto de conexión de Plataforma de identidad de Microsoft](/azure/active-directory/develop/v2-permissions-and-consent).

La columna **Permisos** indica si una aplicación tiene permisos que necesitan consentimiento. Verá un vínculo **Ver detalles** para cada aplicación registrada en Azure AD que tenga permisos que necesiten consentimiento. Ten en cuenta que esto solo se aplica a aplicaciones personalizadas y de terceros. No verá este vínculo ni tendrá que conceder consentimiento de administrador para las aplicaciones publicadas por Microsoft.

:::image type="content" source="media/app-perm-admin-center-permissions-column.png" alt-text="Captura de pantalla de la columna Permisos en la página Administrar aplicaciones.":::

Para conceder el consentimiento de toda la organización a una aplicación, siga estos pasos:

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Aplicaciones de Teams** > **Administrar aplicaciones**.
2. Realice una de las siguientes acciones:
    - Busca la aplicación que quieras, haz clic en el nombre de la aplicación para ir a la página de detalles de la aplicación y, a continuación, selecciona la pestaña **Permisos** .
    - Ordene la columna **Permisos** en orden descendente para buscar la aplicación y, después, seleccione **Ver detalles**. Esto le lleva a la pestaña **Permisos** de la página de detalles de la aplicación.

3. En **Permisos para toda la organización**, seleccione **Revisar permisos y consentimiento**.

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="Captura de pantalla de permisos para toda la organización en la pestaña Permisos de una aplicación.":::

    Para ello, debe ser administrador global. Esta opción no está disponible para Teams administradores de servicios.

4. En la pestaña **Permisos** , revise los permisos solicitados por la aplicación.

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="Captura de pantalla de los permisos solicitados por una aplicación.":::

    > [!IMPORTANT]
    > Conceder el consentimiento de toda la organización a una aplicación permite a la aplicación acceder a los datos de su organización. Revise cuidadosamente los permisos solicitados por la aplicación antes de conceder el consentimiento.
5. Si está de acuerdo con los permisos solicitados por la aplicación, haga clic en **Aceptar** para conceder el consentimiento. Aparece temporalmente un banner en la parte superior de la página para informarte de que se han concedido los permisos solicitados para la aplicación. La aplicación ahora tiene acceso a los recursos especificados para todos los usuarios de la organización y se le pedirá a nadie más que revise los permisos.

Después de aceptar los permisos, verás un mensaje en **Permisos para toda** la organización en la página de detalles de la aplicación para informarte de que se ha concedido el consentimiento. Para ver detalles sobre los permisos de la aplicación, haga clic en el vínculo **Azure Active Directory** para ir a la página de la aplicación en el portal de Azure AD.

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted-new.png" alt-text="Captura de pantalla del mensaje que se muestra cuando se concede el consentimiento.":::

Si los usuarios de su organización tienen permiso para conceder consentimiento y uno o más usuarios han concedido el consentimiento a una aplicación en particular, también verá el mismo mensaje para informarle de que se ha concedido el consentimiento y el vínculo de Azure Active Directory a la página de la aplicación en el portal de Azure AD.

> [!NOTE]
> Aunque la opción **Revisar permisos y consentimiento** no está disponible para los administradores de Teams servicio y no pueden conceder consentimiento de administrador a aplicaciones para toda la organización, Teams los administradores del servicio pueden ver el contenido en la pestaña **Permisos** de una aplicación. Por ejemplo, un administrador de servicio de Teams puede hacer clic en el vínculo **Azure Active Directory** para ver los detalles de los permisos de las aplicaciones en el portal de Azure AD.

## <a name="view-resource-specific-consent-permissions-of-an-app"></a>Ver permisos de consentimiento específicos de recursos de una aplicación

Los permisos de RSC permiten a los propietarios del equipo conceder el consentimiento a una aplicación para acceder a los datos de un equipo y modificarlos. Los permisos RSC son permisos granulares Teams específicos que definen lo que una aplicación puede hacer en un equipo específico. Algunos ejemplos de permisos de RSC son la capacidad de crear y eliminar canales, obtener la configuración de un equipo y crear y quitar pestañas de canales.

Los permisos RSC se definen en el manifiesto de la aplicación y no en Azure AD. Concedes el consentimiento a RSC al agregar la aplicación a un equipo. Para obtener más información, consulta [Consentimiento específico de recursos (RSC).](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)

Los administradores globales y Teams administrador del servicio pueden ver los permisos de RSC para una aplicación en la pestaña **Permisos** de la página de detalles de la aplicación.

Para ver los permisos de RSC para una aplicación, siga estos pasos:

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Aplicaciones de Teams** > **Administrar aplicaciones**.
2. Busca la aplicación que quieras, haz clic en el nombre de la aplicación para ir a la página de detalles de la aplicación y, a continuación, selecciona la pestaña **Permisos** .
3. En **Microsoft Graph permisos de consentimiento específico de recursos (RSC**), revise los permisos de RSC solicitados por la aplicación.

    :::image type="content" source="media/app-perm-admin-center-rsc-new.png" alt-text="Captura de pantalla de permisos de RSC para una aplicación.":::

## <a name="known-issues"></a>Problemas conocidos

### <a name="the-view-details-link-isnt-displayed-in-the-permissions-column-for-some-third-party-apps-that-request-permissions"></a>El vínculo "Ver detalles" no se muestra en la columna Permisos para algunas aplicaciones de terceros que solicitan permisos

Actualmente, la capacidad de revisar los permisos y conceder consentimiento no está disponible para todas las aplicaciones de terceros registradas en Azure AD que solicitan permisos. En lugar del vínculo **Ver detalles** , verá **--** en la columna **Permisos** . Estamos trabajando con isvs para habilitar esta característica para sus aplicaciones.

## <a name="related-topics"></a>Temas relacionados

- [Administrar las aplicaciones en el centro de administración de Microsoft Teams](manage-apps.md)
- [Permisos y consentimiento en el punto de conexión de Plataforma de identidad de Microsoft](/azure/active-directory/develop/v2-permissions-and-consent)
- [Consentimiento específico de recursos en Teams](resource-specific-consent.md)
- [Consentimiento específico de recursos (RSC)](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
- [Navegación por el ciclo de vida de la aplicación Teams](https://aka.ms/PR132) (sesión de Ignite 2020)
