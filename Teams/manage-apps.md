---
title: Administrar las aplicaciones en el centro de administración de Microsoft Teams
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: vaibhava
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: Obtenga información sobre cómo administrar sus aplicaciones de Teams en la página Administrar aplicaciones del Centro de administración de Microsoft Teams.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: a6e6adbfbed5e1b371655ca74aa6ca6c717490c9
ms.sourcegitcommit: 06d1c50c9b55b062d61844a856676d9837fd5abe
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2022
ms.locfileid: "65030946"
---
# <a name="manage-teams-apps-in-the-microsoft-teams-admin-center"></a>Administrar aplicaciones Teams en el centro de administración de Microsoft Teams

Puede administrar las aplicaciones de su organización en **Teams aplicaciones** en el centro de administración. Use la página [Administrar aplicaciones](https://admin.teams.microsoft.com/policies/manage-apps) para ver y administrar todas las aplicaciones de Teams en el catálogo de aplicaciones de su organización. La página Administrar aplicaciones le ofrece una vista de todas las aplicaciones disponibles en el catálogo de inquilinos, proporcionándole la información que necesita para decidir qué aplicaciones permitir o bloquear en toda la organización. Puede ver el estado y las propiedades de nivel de organización de las aplicaciones, bloquear o permitir aplicaciones en el nivel de organización, cargar nuevas aplicaciones personalizadas en el catálogo de inquilinos y administrar la configuración de aplicaciones de toda la organización.

![Captura de pantalla de la página Administrar aplicaciones.](media/manage-apps.png)

Para administrar aplicaciones, use las siguientes directivas para controlar los permisos de los usuarios, la instalación de aplicaciones y la carga de aplicaciones personalizadas creadas dentro de su organización. Para comprender las directivas, consulte [Información general sobre directivas de aplicaciones](app-policies.md).

Para obtener información sobre cómo obtener permisos y roles de administrador, consulte [Teams roles de administrador](./using-admin-roles.md).

> [!NOTE]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

> [!NOTE]
> La página Administrar aplicaciones no está disponible en Microsoft 365 Government Community Cloud High (GCCH) ni en las implementaciones del Departamento de Defensa (DoD) de Teams.

<!--- TBD: This info belongs in the app policy overview article. Title it as mentioned in the spreadsheet.

* **App permission policy**: With it, you can control what apps are available to specific users in your organization. You can allow or block all apps or specific apps published by Microsoft, third-parties, and your organization. See [Manage app permission policies in Teams](teams-app-permission-policies.md).
* **App setup policies**: It lets you customize the app experience for your users. You choose the apps that you want to pin to the app bar in the Teams clients and the order in which they appear, on web, desktop, and mobile clients. See [Manage app setup policies in Teams](teams-app-setup-policies.md).
* **Custom app policies and settings**: Teams allows developers in your organization to build, test, and deploy custom apps to other users. Custom apps can be added to Teams by uploading an app package in a .zip file directly to a team or in the personal context. You can use app setup policies to control who in your organization can upload custom apps. You can also set org-wide settings to control whether users can interact with specific custom apps. See [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings).

The following are the important use cases you can accomplish via the the Manage apps page:

* [Allow or block apps at the org level](#allow-and-block-apps)
* [Apps blocked by publishers](#apps-blocked-by-publishers)
* [Add apps to teams](#add-an-app-to-a-team)
* [Approve or upload new custom apps to your organization's app store](#publish-a-custom-app-to-your-organizations-app-store)
* [View permissions requested by apps](#view-resource-specific-consent-permissions)
* [Grant consent to apps](#grant-admin-consent-to-apps)
* [Purchase service for third-party apps](#purchase-services-for-third-party-apps)
* [See org-level status and properties of apps](#view-apps)
* [Manage org-wide app settings](#manage-org-wide-app-settings)
* [View security and compliance information for Microsoft 365 Certified apps](#view-security-and-compliance-information-for-microsoft-365-certified-apps)

<!--- TBD: Commenting for now in favor of the definition list above: 

The Manage apps page gives you a view into all available apps, providing you with the information you need to decide which apps to allow or block across your organization. You can then use [app permission policies](teams-app-permission-policies.md), [app setup policies](teams-app-setup-policies.md), and [custom app policies and settings](teams-custom-app-policies-and-settings.md) to configure the app experience for specific users in your organization.

In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**. You must be a global admin or Teams service admin to access the page.

--->

<!--- TBD: Move this view apps section to a new article about navigating and understanding TAC. It is yet to be created.

## View apps

You can view every app including the following information about each app.

![Screenshot of the apps details page for an app.](media/app-detail-page.jpg)

- **Name**: The app name. Select the app name to go to the app details page to see more information about the app. This includes a description of the app, whether it's allowed or blocked, version, privacy policy, terms of use, categories that apply to the app, certification status, supported capabilities, and app ID.
- **Certification**: If the app has gone through certification, you'll see either **Microsoft 365 certified** or **Publisher attestation**. Select the link to view certification details for the app. If you see `--`, we don't have certification information for the app. To learn more about certified apps in Teams, read [Microsoft 365 App Certification program](/microsoft-365-app-certification/overview).
- **Publisher**: Name of the publisher.
- **Publishing status**: Publishing status of custom apps.
- **Status**: Status of the app at the org level, which can be one of the following:
  - **Allowed**: The app is available for all users in your organization.
  - **Blocked**: The app is blocked and not available for any users in your organization.
  - **Blocked by publisher**: The app is blocked by the publisher and is hidden from end-users by default. After you set up the app using the publisher's guidance, you can allow or block the app to make it available to end-users.
  - **Blocked org-wide**: The app is blocked in org-wide app settings.
      It's important to know that this column represents the allowed and blocked status of apps that were formerly on the **Org-wide settings** pane. You now view, block, and allow apps at the org-wide on the **Manage apps** page.
- **Licenses**: Indicates whether an app offers a Software as a Service (SaaS) subscription for purchase. This column applies only to third-party apps. Each third-party app will have one of the following values:
  - **Purchase**: The app offers a SaaS subscription and is available to purchase.  
  - **Purchased**: The app offers a SaaS subscription and you've purchased licenses for it.
  - **- -**: The app doesn't offer a SaaS subscription.
- **Custom app**: Whether the app is a custom app.
- **Permissions**: Indicates whether a third-party or custom app that's registered in Azure Active Directory (Azure AD) has permissions that need consent. You'll see one of the following values:
  - **View details**: The app has permissions that require consent before the app can access data.
  - **- -**: The app doesn't have permissions that need consent.
- **Categories**: Categories that apply to the app.
- **Version**: App version.
- **Admin can install in meetings**: Indicates whether an app can be installed by admins in Team meetings. [Learn more](teams-app-setup-policies.md#install-apps)

To see the information that you want in the table, select **Edit Column** in the upper-right corner to add or remove columns to the table.
--->

## <a name="publish-a-custom-app-to-your-organizations-app-store"></a>Publicar una aplicación personalizada en la tienda de aplicaciones de su organización

Usa la página Administrar aplicaciones para publicar aplicaciones creadas específicamente para tu organización. Después de publicar una aplicación personalizada, está disponible para los usuarios de la tienda de aplicaciones de su organización. Hay dos formas de publicar una aplicación personalizada en la tienda de aplicaciones de su organización. La forma de usar depende de cómo obtenga la aplicación.

* [Aprobar una aplicación personalizada](#approve-a-custom-app): usa este método si el desarrollador envía la aplicación directamente a la página Administrar aplicaciones mediante la API de envío de aplicaciones Teams. A continuación, puede revisar y publicar (o rechazar) la aplicación directamente desde la página de detalles de la aplicación.
* [Upload un paquete de aplicación](#upload-an-app-package): use este método si el desarrollador le envía el paquete de la aplicación en .zip formato. Para publicar la aplicación, cargue el paquete de la aplicación.

### <a name="approve-a-custom-app"></a>Aprobar una aplicación personalizada

El widget **Aprobaciones pendientes** de la página Administrar aplicaciones te notifica cuando un desarrollador envía una aplicación mediante la API de envío de aplicaciones Teams. Una aplicación recién enviada aparece con el **estado Publicación** de **Enviado** y el **estado** de **Bloqueado**. Ve a la página de detalles de la aplicación para ver más información sobre la aplicación y, a continuación, para publicarla, establece **Estado de publicación** en **Publicar**.

También se le notificará cuando un desarrollador envíe una actualización a una aplicación personalizada. Después, puede revisar y publicar (o rechazar) la actualización en la página de detalles de la aplicación. Se siguen aplicando todas las directivas de permisos y de configuración de aplicaciones para la aplicación actualizada.

Para obtener más información, consulta [Publicar una aplicación personalizada enviada a través de la API de envío de aplicaciones de Teams](submit-approve-custom-apps.md).

### <a name="upload-an-app-package"></a>Upload un paquete de aplicación

El desarrollador crea un paquete de aplicación Teams con [Teams App Studio](/microsoftteams/platform/get-started/get-started-app-studio) y, a continuación, te lo envía en .zip formato. Cuando tengas el paquete de la aplicación, puedes cargarlo en la tienda de aplicaciones de tu organización.

Para cargar una nueva aplicación personalizada, selecciona **Upload** para cargar el paquete de la aplicación. La aplicación no se resalta después de cargarla, por lo que tendrás que buscar en la lista de aplicaciones de la página Administrar aplicaciones para encontrarla.

Para actualizar una aplicación después de cargarla, en la lista de aplicaciones de la página Administrar aplicaciones, selecciona el nombre de la aplicación y, a continuación **, actualizar.** Al hacerlo, se reemplaza la aplicación existente y se siguen aplicando todas las directivas de permisos y directivas de configuración de aplicaciones para la aplicación actualizada.

Para obtener más información, consulta [Publicar una aplicación personalizada cargando un paquete de aplicación](upload-custom-apps.md).

## <a name="allow-and-block-apps"></a>Permitir y bloquear aplicaciones

La página Administrar aplicaciones es donde permites o bloqueas aplicaciones individuales en el nivel de organización. Muestra todas las aplicaciones disponibles y su estado actual de aplicación de nivel de organización. (El bloqueo y el permiso de aplicaciones en el nivel de organización se han movido desde el panel de configuración de aplicaciones de **toda** la organización hasta aquí).

Para permitir o bloquear una aplicación, selecciónala y, a continuación, selecciona **Permitir** o **Bloquear**. Al bloquear una aplicación, se deshabilitan todas las interacciones con ella y la aplicación no aparece en Teams para los usuarios de su organización.

Al bloquear o permitir una aplicación en la página Administrar aplicaciones, esa aplicación se bloquea o se permite para todos los usuarios de la organización.  Al bloquear o permitir una aplicación en una directiva de permisos de aplicación de Teams, se bloquea o se permite para los usuarios asignados a esa directiva. Para que un usuario pueda instalar e interactuar con cualquier aplicación, debe permitir la aplicación en el nivel de organización en la página Administrar aplicaciones y en la directiva de permisos de la aplicación asignada al usuario.

 > [!NOTE]
 > Para desinstalar una aplicación, haz clic con el botón derecho en la aplicación y, a continuación, haz clic en **Desinstalar** o usa el menú **Más aplicaciones** en el lado izquierdo.

## <a name="apps-blocked-by-publishers"></a>Aplicaciones bloqueadas por editores

Cuando un ISV publica una aplicación en la tienda global de aplicaciones, es posible que necesiten administradores para configurar o personalizar la experiencia de la aplicación. El administrador puede hacer que esté disponible para los usuarios finales cuando la aplicación esté completamente configurada.

Por ejemplo, Contoso Electronics es un ISV que creó una aplicación de asistencia para Microsoft Teams. Contoso Electronics quiere que sus clientes configuren determinadas propiedades de la aplicación para que, cuando los usuarios interactúen con la aplicación, funcione según lo esperado. Antes de que un administrador pueda permitir o bloquear la aplicación, se mostrará como **Bloqueada por el editor** en el centro de administración de Teams y se ocultará a los usuarios finales de forma predeterminada. Después de seguir las instrucciones del editor para configurar la aplicación, puede hacer que esté disponible para los usuarios cambiando el estado a **Permitido**, o impedir que los usuarios usen la aplicación cambiando el estado a **Bloqueado**.

![Captura de pantalla del estado bloqueado por el editor en el Centro de administración de Teams.](media/blocked-by-publisher.png)

## <a name="add-an-app-to-a-team"></a>Agregar una aplicación a un equipo

Use el botón **Agregar al equipo** para instalar una aplicación en un equipo. Tenga en cuenta que esto es solo para las aplicaciones que se pueden instalar en un ámbito de equipo. El botón **Agregar al equipo** no está disponible para las aplicaciones que solo se pueden instalar en el ámbito personal.

![Captura de pantalla del botón Agregar al equipo.](media/manage-apps-add-app-team.png)

1. Busca la aplicación que quieras y, a continuación, selecciona la aplicación haciendo clic a la izquierda del nombre de la aplicación.
1. Seleccione **Agregar al equipo**.
1. En el panel **Agregar al equipo** , busque el equipo al que desea agregar la aplicación, seleccione el equipo y, a continuación, seleccione **Aplicar**.

## <a name="customize-an-app"></a>Personalizar una aplicación

Ahora puede personalizar una aplicación para incluir un aspecto específico según las necesidades de su organización. Consulta [Personalizar aplicaciones en Teams](customize-apps.md).

## <a name="purchase-services-for-third-party-apps"></a>Servicios de compra para aplicaciones de terceros

Puede buscar y comprar licencias de servicios ofrecidos por aplicaciones de terceros para los usuarios de su organización directamente desde la página Administrar aplicaciones. La columna **Licencias** de la tabla indica si una aplicación ofrece una suscripción SaaS de pago. Seleccione **Comprar ahora** para ver la información de planes y precios y comprar licencias para los usuarios. Para obtener más información, consulta [Comprar servicios para Teams aplicaciones de terceros en el Centro de administración de Microsoft Teams](purchase-third-party-apps.md).

## <a name="grant-admin-consent-to-apps"></a>Conceder consentimiento de administrador a las aplicaciones

Puede revisar y dar su consentimiento a las aplicaciones que solicitan permisos en nombre de todos los usuarios de su organización. Esto se hace para que los usuarios no tengan que revisar ni aceptar los permisos solicitados por la aplicación cuando inicien la aplicación. La columna **Permisos** indica si una aplicación tiene permisos que necesitan consentimiento. Verá un vínculo **Ver detalles** para cada aplicación registrada en Azure AD que tenga permisos que necesiten consentimiento. Para obtener más información, consulte [Ver permisos de aplicaciones y conceder consentimiento de administrador en el Centro de administración de Microsoft Teams](app-permissions-admin-center.md).

## <a name="view-resource-specific-consent-permissions"></a>Ver permisos de consentimiento específicos de recursos

Los permisos de consentimiento específico de recursos (RSC) permiten a los propietarios del equipo conceder el consentimiento a una aplicación para acceder a los datos de un equipo y modificarlos. Los permisos RSC son permisos granulares Teams específicos que definen lo que una aplicación puede hacer en un equipo específico. Puedes ver los permisos de RSC en la pestaña **Permisos** de la página de detalles de la aplicación de una aplicación. Para obtener más información, consulte [Ver permisos de aplicaciones y conceder consentimiento de administrador en el Centro de administración de Microsoft Teams](app-permissions-admin-center.md).

## <a name="manage-org-wide-app-settings"></a>Administrar la configuración de aplicaciones para toda la organización

Use la configuración de aplicaciones para toda la organización para controlar si los usuarios con una [licencia F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt) obtienen la experiencia de aplicación de primera línea adaptada, si los usuarios pueden instalar aplicaciones de terceros y si los usuarios pueden cargar o interactuar con aplicaciones personalizadas en su organización. La configuración de aplicaciones para toda la organización rige el comportamiento de todos los usuarios e invalida cualquier otra directiva de permisos de aplicación asignada a los usuarios. Puede usarla para controlar las aplicaciones malintencionadas o problemáticas.

> [!NOTE]
> Para obtener información sobre cómo usar la configuración de aplicaciones para toda la organización en Microsoft 365 Administración Pública Government Community Cloud implementaciones de alto GCCH y del Departamento de Defensa (DoD) de Teams, consulta [Administrar directivas de permisos de aplicaciones en Teams](teams-app-permission-policies.md).

1. En la página Administrar aplicaciones, seleccione **Configuración de aplicaciones para toda la organización**. A continuación, puede configurar las opciones que desee en el panel.

    :::image type="content" source="media/manage-apps-org-wide-app-settings.png" alt-text="Captura de pantalla del panel Configuración de aplicaciones para toda la organización en la página Administrar aplicaciones":::

1. En **Aplicaciones adaptadas**, desactiva o activa **Mostrar aplicaciones adaptadas**. Cuando esta configuración está activada, los usuarios con una [licencia F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt) obtienen la experiencia de aplicación de primera línea personalizada. Esta experiencia ancla las aplicaciones más relevantes de Teams para los trabajadores de primera línea. Para obtener más información, consulte [Personalizar aplicaciones de Teams para los trabajadores de primera línea](pin-teams-apps-based-on-license.md).

    Esta característica está disponible para licencias F. En el futuro se admitirán otros tipos de licencia.
1. En **Aplicaciones de terceros**, desactive o active esta configuración para controlar el acceso a aplicaciones de terceros:

    - **Permitir aplicaciones de terceros**: esto controla si los usuarios pueden usar aplicaciones de terceros. Si desactivas esta configuración, los usuarios no podrán instalar ni usar aplicaciones de terceros y el estado de la aplicación de estas aplicaciones se mostrará como Bloqueado en toda la **organización** en la tabla.

        > [!NOTE]
        > Cuando **Permitir aplicaciones de terceros** está desactivado, [los webhooks salientes](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) siguen estando habilitados para todos los usuarios, pero puede controlarlos en el nivel de usuario al permitir o bloquear la aplicación De webhook saliente a través de [directivas de permisos de aplicaciones](teams-app-permission-policies.md). Tenga en cuenta que si tiene directivas de [permisos de aplicaciones](teams-app-permission-policies.md) existentes para **aplicaciones de Microsoft** que usan la opción **Permitir aplicaciones específicas y bloquear todas las demás** , y desea habilitar los webhooks salientes para los usuarios, agregue la aplicación de webhook saliente a la lista.

        > [!NOTE]
        > Los usuarios de Teams puede añadir aplicaciones cuando organizan reuniones o chats con personas de otras organizaciones. También pueden usar aplicaciones compartidas con personas de otras organizaciones cuando organizan reuniones o chats con estas organizaciones. Se aplican las directivas de datos de la organización del usuario anfitrión, así como las prácticas de intercambio de datos de cualquier aplicación de terceros compartida por la organización del usuario.

    - **Permitir las nuevas aplicaciones de terceros publicadas en la tienda de forma predeterminada**: esto controla si las nuevas aplicaciones de terceros publicadas en la tienda de aplicaciones de Teams están disponibles automáticamente en Teams. Solo puede establecer esta opción si permite aplicaciones de terceros.

1. En **Aplicaciones personalizadas**, desactiva o activa **Permitir interacción con aplicaciones personalizadas**. Esta configuración controla si los usuarios pueden interactuar con aplicaciones personalizadas. Para obtener más información, consulte [Administrar configuración y directivas de aplicación personalizadas en Teams](teams-custom-app-policies-and-settings.md).
1. Seleccione **Guardar** para que la configuración de aplicaciones de toda la organización surta efecto.

<!--- TBD: Commenting this info for now. Move it later to the new article about compliance program and how/where admins can find info about compliant apps.

## View security and compliance information for Microsoft 365 Certified apps

When evaluating an app for their organization, admins can use independent Cloud Access Security Brokers (CASB), such as Microsoft Cloud App Security (MCAS), to find information about security and behaviors of an app. The Teams admin center includes security and compliance information from MCAS for Microsoft 365 Certified apps so you'll have more information on whether or not the app meets your needs.

> [!NOTE]
> This feature is available to all admins, whether or not your organization has a license that supports MCAS.

To access MCAS information, follow these steps:

1. In the Teams admin center, select **Manage apps** under **Teams apps**.
1. Select **Certification** to sort apps and push all Microsoft 365 Certified apps to the top of the table.
1. Choose a Microsoft 365 Certified app.
1. Select the **Security and compliance** tab.

![Screenshot of Teams admin center security and compliance tab.](media/mcas.png)

On this tab, you'll find information on security, compliance, and data protection. You can also expand each dropdown list to get more details about which capabilities are supported for the selected application.
--->
