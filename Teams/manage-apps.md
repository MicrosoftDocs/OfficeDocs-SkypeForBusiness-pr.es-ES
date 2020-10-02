---
title: Administrar las aplicaciones en el centro de administración de Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
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
description: Obtener información sobre cómo administrar las aplicaciones de Teams en la página Administrar aplicaciones del centro de administración de Microsoft Teams
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: d75664a6d3884529936f8adcb69a928bdd238b3d
ms.sourcegitcommit: fd7d5ba09ef30cf4594e352c36f62b950e0e41a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2020
ms.locfileid: "48336968"
---
<a name="manage-your-apps-in-the-microsoft-teams-admin-center"></a>Administrar las aplicaciones en el centro de administración de Microsoft Teams
======================================================

Como administrador, la página Manage Apps en el centro de administración de Microsoft Teams es donde ve y administra todas las aplicaciones de Teams para su organización. Aquí puede ver el estado de organización y las propiedades de las aplicaciones, aprobar o cargar nuevas aplicaciones personalizadas en la tienda de aplicaciones de su organización, bloquear o permitir aplicaciones en el nivel de organización, agregar aplicaciones a Teams (en versión preliminar), comprar servicios para aplicaciones de terceros, ver permisos solicitados por aplicaciones, conceder consentimiento de administrador a las aplicaciones y administrar la configuración de aplicaciones

La página Manage apps le ofrece una vista de todas las aplicaciones disponibles, y le proporciona la información que necesita para decidir qué aplicaciones quiere permitir o bloquear en toda la organización. Después, puede usar [las directivas de permisos](teams-app-permission-policies.md)de la aplicación, [las directivas de configuración](teams-app-setup-policies.md)de la aplicación y [las directivas de aplicaciones personalizadas y la configuración](teams-custom-app-policies-and-settings.md) para configurar la experiencia de la aplicación para usuarios específicos de su organización.

En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **aplicaciones de Teams**  >  **Manage apps**. Debe ser administrador global o administrador de servicios de equipo para poder acceder a la página.

> [!NOTE]
> La página Manage apps aún no está disponible en las implementaciones de Teams de la comunidad de Microsoft 365 pública Cloud (GCC).

## <a name="view-apps"></a>Ver aplicaciones

Puede ver todas las aplicaciones, incluida la siguiente información sobre cada aplicación.

![Captura de pantalla de la página aplicaciones administradas](media/manage-apps.png)

- **Name**: el nombre de la aplicación. Haga clic en el nombre de la aplicación para ir a la página de detalles de la aplicación para ver más información sobre la aplicación. Esto incluye una descripción de la aplicación, si está permitida o bloqueada, la versión, la política de privacidad, las condiciones de uso, las categorías que se aplican a la aplicación, el estado de la certificación, las características admitidas y el identificador de la aplicación. Aquí se muestra un ejemplo:

  ![Captura de pantalla de la página de detalles de aplicaciones de una aplicación](media/manage-apps-app-details.png)
  
- **Certificación**: Si la aplicación ha superado la certificación, verá la atestación de **Microsoft 365** o la **atestación de Publisher**. Haga clic en el vínculo para ver los detalles de certificación de la aplicación. Si ves " **--** ", no tenemos información de certificación de la aplicación. Para obtener más información sobre las aplicaciones certificadas en Teams, lea el [programa de certificación de aplicaciones de Microsoft 365](https://docs.microsoft.com/teams-app-certification/all-apps).  
- **Publisher**: nombre del editor.
- **Estado de publicación**: estado de publicación de aplicaciones personalizadas.
- **Estado**: el estado de la aplicación en el nivel de la organización, que puede ser uno de los siguientes:

    - **Permitido**: la aplicación está disponible para todos los usuarios de la organización.
    
    - **Bloqueado**: la aplicación está bloqueada y no está disponible para los usuarios de su organización.
    
    - **Organización bloqueada**: la aplicación está bloqueada en la configuración de la aplicación en toda la organización.
    
      Es importante saber que esta columna representa el estado permitido y bloqueado de las aplicaciones que anteriormente se encontraban en el panel **configuración de toda la organización** . Ahora ve, bloquea y permite aplicaciones en el ámbito de la organización en la página **Manage apps** . 
- **Licencias**: indica si una aplicación ofrece una suscripción de software como servicio (SaaS) para la compra. Esta columna solo se aplica a aplicaciones de terceros. Cada aplicación de terceros tendrá uno de los siguientes valores:
    - **Comprar ahora**: la aplicación ofrece una suscripción de SaaS y está disponible para la compra.  
    - **Comprado**: la aplicación ofrece una suscripción de SaaS y ha comprado las licencias para él.
    - **--**: La aplicación no ofrece una suscripción de SaaS.
- **Aplicación personalizada**: Si la aplicación es una aplicación personalizada.
- **Permisos**: indica si una aplicación personalizada o de terceros que está registrada en Azure Active Directory (Azure ad) tiene permisos que necesitan consentimiento. Verá uno de los siguientes valores:
    - **Ver detalles**: la aplicación tiene permisos que requieren consentimiento para que la aplicación pueda acceder a los datos. 
    - **--**: La aplicación no tiene permisos que necesiten autorización.
- **Categorías**: categorías que se aplican a la aplicación.
- **Versión**: versión de la aplicación.

Para ver la información que desea en la tabla, haga clic en **Editar columna** , en la esquina superior derecha, para agregar o quitar columnas a la tabla.

## <a name="publish-a-custom-app-to-your-organizations-app-store"></a>Publicar una aplicación personalizada en la tienda de aplicaciones de su organización

Use la página Administrar aplicaciones para publicar aplicaciones que se hayan creado específicamente para su organización. Después de publicar una aplicación personalizada, esta estará disponible para los usuarios de la tienda de aplicaciones de su organización. Hay dos formas de publicar una aplicación personalizada en la tienda de aplicaciones de su organización. La manera en que uses depende de cómo obtengas la aplicación.

- [Aprobar una aplicación personalizada](#approve-a-custom-app): Use este método si el desarrollador envía la aplicación directamente a la página de administración de aplicaciones con la API de envío de la aplicación de Teams. Después, puede revisar y publicar (o rechazar) la aplicación directamente desde la página de detalles de la aplicación.
- [Cargar un paquete](#upload-an-app-package)de la aplicación: Use este método si el desarrollador le envía el paquete de la aplicación con el formato. zip. Para publicar la aplicación, carga el paquete de la aplicación.

###  <a name="approve-a-custom-app"></a>Aprobar una aplicación personalizada

El widget **aprobaciones pendientes** en la página Administrar aplicaciones le notifica cuando un desarrollador envía una aplicación con la API de envío de aplicaciones de Teams. Una aplicación recién enviada aparece con un **Estado de publicación** de **enviado** y un **Estado** de **bloqueado**. Vaya a la página de detalles de la aplicación para ver más información sobre la aplicación y, después, para publicarla, establezca el **Estado de publicación** en **publicar**.

También recibirás una notificación cuando un desarrollador envíe una actualización a una aplicación personalizada. Después, puede revisar y publicar (o rechazar) la actualización en la página de detalles de la aplicación. Todas las directivas de permisos de aplicaciones y directivas de configuración de la aplicación siguen aplicándose para la aplicación actualizada.

Para obtener más información, vea [publicar una aplicación personalizada enviada a través de la API de envío de la aplicación de Teams](submit-approve-custom-apps.md).

### <a name="upload-an-app-package"></a>Cargar un paquete de la aplicación

El desarrollador crea un paquete de la aplicación Teams con [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)y, a continuación, lo envía en formato. zip. Cuando tenga el paquete de la aplicación, puede cargarlo en la tienda de aplicaciones de su organización.

Para cargar una nueva aplicación personalizada, seleccione **cargar** para cargar el paquete de la aplicación. La aplicación no se resalta después de cargarla, tendrá que buscar en la lista de aplicaciones en la página de administración de aplicaciones para encontrarla.

Para actualizar una aplicación después de que se cargue, en la lista de aplicaciones de la página Administrar aplicaciones, haga clic en el nombre de la aplicación y, a continuación, haga clic en **Actualizar**. Esto reemplaza la aplicación existente y todas las directivas de permisos de la aplicación y de configuración de la aplicación siguen aplicándose para la aplicación actualizada.

Para obtener más información, vea [publicar una aplicación personalizada mediante la carga de un paquete de la aplicación](upload-custom-apps.md).

## <a name="allow-and-block-apps"></a>Permitir y bloquear aplicaciones

La página Manage apps es donde permite o bloquea aplicaciones individuales en el nivel de organización. Muestra todas las aplicaciones disponibles y el estado actual de la aplicación en el nivel de organización. (El bloqueo y la autorización de aplicaciones en el nivel de organización se han movido del panel de configuración de la **aplicación de toda la organización** a aquí).

Para permitir o bloquear una aplicación, selecciónela y, a continuación, haga clic en **permitir** o en **bloquear**. Cuando bloquea una aplicación, todas las interacciones con esa aplicación se deshabilitan y la aplicación no aparece en Teams para ninguno de los usuarios de su organización.

Cuando bloquea o permite una aplicación en la página Administrar aplicaciones, la aplicación está bloqueada o está permitida para todos los usuarios de su organización.  Al bloquear o permitir una aplicación en una directiva de permisos de la aplicación de Teams, se bloquea o permite a los usuarios que tienen asignada esa Directiva. Para que un usuario pueda instalar e interactuar con cualquier aplicación, debe permitir la aplicación en el nivel de la organización en la página Administrar aplicaciones y en la Directiva de permisos de la aplicación que está asignada al usuario.

 > [!NOTE]
 > Para desinstalar una aplicación, haga clic con el botón derecho en la aplicación y, a continuación, haga clic en **desinstalar** o use el menú **más aplicaciones** en el lado izquierdo.

## <a name="add-an-app-to-a-team"></a>Agregar una aplicación a un equipo

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Use el botón **Agregar al equipo** para instalar una aplicación en un equipo. Tenga en cuenta que esto es solo para las aplicaciones que se pueden instalar en un ámbito de equipo. El botón **Agregar a equipo** no está disponible para las aplicaciones que solo se pueden instalar en el ámbito personal.

![Captura de pantalla del botón Agregar a equipo](media/manage-apps-add-app-team.png)

1. Busque la aplicación que quiera y, después, seleccione la aplicación haciendo clic a la izquierda del nombre de la aplicación.
2. Seleccione **Agregar al equipo**.
3. En el panel **Agregar a equipo** , busque el equipo al que desea agregar la aplicación, seleccione el equipo y, después, haga clic en **aplicar**.

## <a name="purchase-services-for-third-party-apps"></a>Servicios de compra para aplicaciones de terceros

Puede buscar y comprar licencias de servicios ofrecidos por aplicaciones de terceros para los usuarios de su organización directamente desde la página Manage apps. La columna **licencias** de la tabla indica si una aplicación ofrece una suscripción de SaaS de pagos. Haga clic en **comprar ahora** para ver los planes y la información de precios y comprar licencias para los usuarios. Para obtener más información, vea [servicios de compra de aplicaciones de terceros para equipos en el centro de administración de Microsoft Teams](purchase-third-party-apps.md).

## <a name="grant-admin-consent-to-apps"></a>Conceder consentimiento del administrador a las aplicaciones

Puede revisar y conceder consentimiento a las aplicaciones que solicitan permisos en nombre de todos los usuarios de su organización. Haga esto para que los usuarios no tengan que revisar y aceptar los permisos solicitados por la aplicación cuando inicien la aplicación. La columna **permisos** indica si una aplicación tiene permisos que necesitan consentimiento. Verá un vínculo **Ver detalles** para cada aplicación registrada en Azure ad que tenga permisos que necesiten conceder. Para obtener más información, consulte [ver permisos de aplicaciones y conceder consentimiento de administrador en el centro de administración de Microsoft Teams](app-permissions-admin-center.md).

## <a name="view-resource-specific-consent-permissions"></a>Ver permisos de consentimiento específicos de recursos

Los permisos de consentimiento específico de recursos (RSC) permiten a los propietarios del equipo conceder el consentimiento para que una aplicación pueda acceder y modificar los datos de un equipo. Los permisos RSC son granulares, permisos específicos de teams que definen lo que una aplicación puede hacer en un equipo específico. Puede ver los permisos RSC en la pestaña **permisos** de la página de detalles de la aplicación de una aplicación. Para obtener más información, consulte [ver permisos de aplicaciones y conceder consentimiento de administrador en el centro de administración de Microsoft Teams](app-permissions-admin-center.md).

## <a name="manage-org-wide-app-settings"></a>Administrar la configuración de la aplicación en toda la organización

Use la configuración de la aplicación en toda la organización para controlar si los usuarios pueden instalar aplicaciones de terceros y si los usuarios pueden cargar o interactuar con aplicaciones personalizadas de su organización. La configuración de la aplicación en toda la organización rige el comportamiento de todos los usuarios y anula cualquier otra directiva de permisos de aplicación asignada a los usuarios. Puede usarlos para controlar aplicaciones malintencionadas o problemáticas.

> [!NOTE]
> Para obtener información sobre cómo usar la configuración de aplicaciones en toda la organización en implementaciones de Teams gubernamentales-GCC de Microsoft 365, consulte [Administrar directivas de permisos de aplicaciones en Teams](teams-app-permission-policies.md).

1. En la página Administrar aplicaciones, seleccione **configuración**de la aplicación en toda la organización. Puede establecer la configuración que desee en el panel.

    ![Captura de pantalla de la configuración de aplicación de toda la organización](media/manage-apps-org-wide-app-settings.png)
    
2. En **aplicaciones de terceros**, desactive o Active esta configuración para controlar el acceso a las aplicaciones de terceros:

    - **Permitir aplicaciones de terceros**: controla si los usuarios pueden usar aplicaciones de terceros. Si desactiva esta configuración, los usuarios no podrán instalar ni usar ninguna aplicación de terceros y el estado de la aplicación de estas aplicaciones aparecerá **bloqueado: todo el mundo** en la tabla.

        > [!NOTE]
        > Cuando se desactivan las **aplicaciones de terceros** , los enlaces de correo [salientes](https://docs.microsoft.com/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) están deshabilitados, lo que significa que los usuarios no pueden crearlos. Cuando esta configuración está activada, los enlaces de webhook de salida están habilitados para todos los usuarios y puede controlarlos en el nivel de usuario permitiendo o bloqueando la aplicación de Hook de salida mediante [directivas de permisos](teams-app-permission-policies.md)de la aplicación. <br><br>Tenga en cuenta que si tiene [directivas de permisos de aplicaciones](teams-app-permission-policies.md) existentes para **aplicaciones de Microsoft** que usan la configuración **permitir aplicaciones específicas y bloquear a todos los** usuarios, y desea habilitar los webhooks salientes para los usuarios, agregue la aplicación de webhook saliente a la lista.
    - **Permitir que todas las aplicaciones de terceros se publiquen en la tienda de forma predeterminada**: controla si las nuevas aplicaciones de terceros publicadas en la tienda de aplicaciones de Teams se encuentran disponibles automáticamente en Teams. Solo puede establecer esta opción si permite aplicaciones de terceros.

3. En **aplicaciones personalizadas**, desactive o desactive la **opción permitir la interacción con aplicaciones personalizadas**. Esta configuración controla si los usuarios pueden interactuar con aplicaciones personalizadas. Para obtener más información, vea [administrar la configuración y las directivas de la aplicación personalizadas en Teams](teams-custom-app-policies-and-settings.md).
4. Haga clic en **Guardar** para que la configuración de la aplicación de toda la organización surta efecto.

## <a name="related-topics"></a>Temas relacionados

- [Configurar la administración para aplicaciones en Teams](admin-settings.md)