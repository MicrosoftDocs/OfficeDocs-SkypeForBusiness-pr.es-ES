---
title: Administrar las aplicaciones en el centro Microsoft Teams administración
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
description: Obtenga información sobre cómo administrar sus Teams aplicaciones en la página Administrar aplicaciones del centro de Microsoft Teams administración.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: ad1dd28f4de0bc6db0ab7b2870a1cf7b2dae007a
ms.sourcegitcommit: de6eb0478a79e178c5d02cdab8cca44a88beb853
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2022
ms.locfileid: "63070229"
---
# <a name="manage-your-apps-in-the-microsoft-teams-admin-center"></a>Administrar las aplicaciones en el centro Microsoft Teams administración

Como administrador, puede ver y administrar todas las Teams aplicaciones de su organización. En la página Administrar aplicaciones del centro Teams administración, puede:

- [Permitir o bloquear aplicaciones en el nivel de organización](#allow-and-block-apps)
- [Aplicaciones bloqueadas por editores](#apps-blocked-by-publishers)
- [Agregar aplicaciones a equipos](#add-an-app-to-a-team)
- [Aprobar o cargar nuevas aplicaciones personalizadas en la tienda de aplicaciones de su organización](#publish-a-custom-app-to-your-organizations-app-store)
- [Ver permisos solicitados por aplicaciones](#view-resource-specific-consent-permissions)
- [Conceder consentimiento a aplicaciones](#grant-admin-consent-to-apps)
- [Servicio de compra para aplicaciones de terceros](#purchase-services-for-third-party-apps)
- [Ver el estado de nivel de organización y las propiedades de las aplicaciones](#view-apps)
- [Administrar la configuración de la aplicación para toda la organización](#manage-org-wide-app-settings)
- [Ver la información de seguridad y cumplimiento de Microsoft 365 aplicaciones certificadas](#view-security-and-compliance-information-for-microsoft-365-certified-apps)

La página Administrar aplicaciones le ofrece una vista de todas las aplicaciones disponibles, lo que le proporciona la información que necesita para decidir qué aplicaciones permitir o bloquear en toda la organización. A continuación, puede usar directivas de [permisos de aplicación](teams-app-permission-policies.md)[, directivas](teams-app-setup-policies.md) de configuración de aplicaciones y directivas y configuraciones de aplicaciones personalizadas para configurar la experiencia de la aplicación para usuarios específicos de su organización.[](teams-custom-app-policies-and-settings.md)

En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Aplicaciones de Teams** > **Administrar aplicaciones**. Debe ser administrador global o administrador Teams de servicio para acceder a la página.

![Captura de pantalla de la página Aplicaciones administradas.](media/manage-apps.png)

> [!NOTE]
> La página Administrar aplicaciones aún no está disponible en implementaciones de Microsoft 365 Government Community Cloud High (GCCH) o department of defense (DoD) de Teams.

## <a name="view-apps"></a>Ver aplicaciones

Puede ver todas las aplicaciones, incluida la siguiente información sobre cada aplicación.

![Captura de pantalla de la página de detalles de aplicaciones para una aplicación.](media/app-detail-page.jpg)

- **Nombre**: el nombre de la aplicación. Seleccione el nombre de la aplicación para ir a la página de detalles de la aplicación para ver más información sobre la aplicación. Esto incluye una descripción de la aplicación, ya sea permitido o bloqueado, versión, directiva de privacidad, términos de uso, categorías que se aplican a la aplicación, estado de certificación, capacidades compatibles e id. de aplicación.
- **Certificación**: Si la aplicación ha pasado por la certificación, verá Microsoft 365 **certificado** o **Publisher certificación**. Seleccione el vínculo para ver los detalles de certificación de la aplicación. Si ve , `--`no tenemos información de certificación para la aplicación. Para obtener más información sobre las aplicaciones certificadas en Teams, Microsoft 365 [programa de certificación de aplicaciones](/microsoft-365-app-certification/overview).
- **Publisher**: Nombre del editor.
- **Estado de publicación**: Estado de publicación de aplicaciones personalizadas.
- **Estado**: Estado de la aplicación en el nivel de organización, que puede ser uno de los siguientes:
  - **Permitido**: la aplicación está disponible para todos los usuarios de su organización.
  - **Bloqueado**: la aplicación está bloqueada y no está disponible para los usuarios de su organización.
  - **Bloqueado por el editor**: la aplicación está bloqueada por el editor y está oculta a los usuarios finales de forma predeterminada. Después de configurar la aplicación con las instrucciones del editor, puede permitir o bloquear la aplicación para que esté disponible para los usuarios finales.
  - **Bloqueado en toda la organización**: la aplicación está bloqueada en la configuración de la aplicación para toda la organización.
      Es importante saber que esta columna representa el estado permitido y bloqueado de las aplicaciones que anteriormente estaban en el panel **de configuración de toda la** organización. Ahora puede ver, bloquear y permitir aplicaciones en toda la organización en la **página** Administrar aplicaciones.
- **Licencias**: Indica si una aplicación ofrece una suscripción de Software como Servicio (SaaS) para la compra. Esta columna solo se aplica a aplicaciones de terceros. Cada aplicación de terceros tendrá uno de los siguientes valores:
  - **Compra**: La aplicación ofrece una suscripción SaaS y está disponible para comprar.  
  - **Comprado**: La aplicación ofrece una suscripción SaaS y ha comprado licencias para ella.
  - **- -**: La aplicación no ofrece una suscripción a SaaS.
- **Aplicación personalizada**: Si la aplicación es una aplicación personalizada.
- **Permisos**: Indica si una aplicación de terceros o personalizada que está registrada en Azure Active Directory (Azure AD) tiene permisos que necesitan consentimiento. Verá uno de los siguientes valores:
  - **Ver detalles**: la aplicación tiene permisos que requieren consentimiento para que la aplicación pueda acceder a los datos.
  - **- -**: La aplicación no tiene permisos que necesiten consentimiento.
- **Categorías**: Categorías que se aplican a la aplicación.
- **Versión**: versión de la aplicación.
- **El administrador puede instalar en reuniones**: Indica si los administradores pueden instalar una aplicación en reuniones de grupo. [Aprende más](teams-app-setup-policies.md#install-apps)

Para ver la información que desea en la tabla, seleccione **Editar** columna en la esquina superior derecha para agregar o quitar columnas a la tabla.

## <a name="publish-a-custom-app-to-your-organizations-app-store"></a>Publicar una aplicación personalizada en la tienda de aplicaciones de su organización

Use la página Administrar aplicaciones para publicar aplicaciones creadas específicamente para su organización. Después de publicar una aplicación personalizada, está disponible para los usuarios en la tienda de aplicaciones de su organización. Hay dos formas de publicar una aplicación personalizada en la tienda de aplicaciones de su organización. La forma de usar depende de cómo obtenga la aplicación.

- [Aprobar una aplicación personalizada](#approve-a-custom-app): use este método si el desarrollador envía la aplicación directamente a la página Administrar aplicaciones mediante la API Teams de envío de aplicaciones. A continuación, puede revisar y publicar (o rechazar) la aplicación directamente desde la página de detalles de la aplicación.
- [Upload un paquete de aplicación](#upload-an-app-package): Use este método si el desarrollador le envía el paquete de la aplicación .zip formato. Para publicar la aplicación, cargue el paquete de la aplicación.

### <a name="approve-a-custom-app"></a>Aprobar una aplicación personalizada

El **widget Pendientes de** aprobaciones de la página Administrar aplicaciones le notifica cuando un desarrollador envía una aplicación mediante la API de Teams de envío de aplicaciones. Una aplicación enviada recientemente aparece en la lista **con un estado de publicación** **enviado y** un **estado de** **bloqueado**. Vaya a la página de detalles de la aplicación para ver más información sobre la aplicación y, después, para publicarla, establezca **Estado de publicación** en **Publicar**.

También se le notifica cuando un desarrollador envía una actualización a una aplicación personalizada. A continuación, puede revisar y publicar (o rechazar) la actualización en la página de detalles de la aplicación. Todas las directivas de permisos de la aplicación y las directivas de configuración de la aplicación siguen siendo obligatorias para la aplicación actualizada.

Para obtener más información, vea [Publicar una aplicación personalizada enviada a través Teams API de envío de aplicaciones](submit-approve-custom-apps.md).

### <a name="upload-an-app-package"></a>Upload un paquete de aplicación

El desarrollador crea un paquete Teams aplicación con [Teams App Studio](/microsoftteams/platform/get-started/get-started-app-studio) y, a continuación, se lo envía en .zip formato. Cuando tenga el paquete de la aplicación, puede cargarlo en la tienda de aplicaciones de su organización.

Para cargar una nueva aplicación personalizada, selecciona **Upload** para cargar el paquete de la aplicación. La aplicación no se resalta después de cargarla, por lo que tendrá que buscar en la lista de aplicaciones de la página Administrar aplicaciones para encontrarla.

Para actualizar una aplicación después de cargarla, en la lista de aplicaciones de la página Administrar aplicaciones, seleccione el nombre de la aplicación y, a continuación, **seleccione Actualizar**. Al hacerlo, se reemplaza la aplicación existente y todas las directivas de permisos de la aplicación y las directivas de configuración de aplicaciones se mantienen vigentes para la aplicación actualizada.

Para obtener más información, vea [Publicar una aplicación personalizada cargando un paquete de aplicación](upload-custom-apps.md).

## <a name="allow-and-block-apps"></a>Permitir y bloquear aplicaciones

La página Administrar aplicaciones es donde permite o bloquea aplicaciones individuales en el nivel de la organización. Muestra todas las aplicaciones disponibles y el estado actual de la aplicación a nivel de organización. (Bloquear y permitir aplicaciones en el nivel de organización se ha movido desde **el panel de** configuración de aplicaciones para toda la organización hasta aquí).

Para permitir o bloquear una aplicación, selecciónelo y, a continuación, **seleccione Permitir** o **Bloquear**. Al bloquear una aplicación, todas las interacciones con esa aplicación se deshabilitan y la aplicación no aparece en Teams para los usuarios de su organización.

Al bloquear o permitir una aplicación en la página Administrar aplicaciones, esa aplicación está bloqueada o permitida para todos los usuarios de su organización.  Al bloquear o permitir una aplicación en una Teams de permisos de aplicación, se bloquea o se permite para los usuarios que tienen asignada esa directiva. Para que un usuario pueda instalar e interactuar con cualquier aplicación, debe permitir la aplicación en el nivel de organización en la página Administrar aplicaciones y en la directiva de permisos de la aplicación asignada al usuario.

 > [!NOTE]
 > Para desinstalar una aplicación, haga clic con el botón derecho en la aplicación y, a continuación, haga clic en **Desinstalar o use** el **menú** Más aplicaciones en el lado izquierdo.

## <a name="apps-blocked-by-publishers"></a>Aplicaciones bloqueadas por editores

Cuando un ISV publica una aplicación en la tienda global de aplicaciones, es posible que necesiten administradores para configurar o personalizar la experiencia de la aplicación. El administrador puede hacer que esté disponible para los usuarios finales cuando la aplicación esté completamente configurada.

Por ejemplo, Contoso Electronics es un ISV que ha creado una aplicación de servicio de ayuda para Microsoft Teams. Contoso Electronics quiere que sus clientes configuren determinadas propiedades de la aplicación para que, cuando los usuarios interactúan con la aplicación, funcione según lo esperado. Antes de que un administrador pueda permitir o bloquear la aplicación, se mostrará  como Bloqueada por el editor en el centro de administración de Teams y se ocultará de forma predeterminada a los usuarios finales. Después de seguir las instrucciones del editor para configurar la aplicación, puede hacer que esté disponible para los usuarios cambiando a estado a **Permitido o bloquear** el uso de la aplicación cambiando el estado a **Bloqueado**.

![Captura de pantalla del estado del editor bloqueado en el Centro de administración de teams.](media/blocked-by-publisher.png)

## <a name="add-an-app-to-a-team"></a>Agregar una aplicación a un equipo

Use el botón **Agregar al equipo** para instalar una aplicación en un equipo. Tenga en cuenta que esto es solo para aplicaciones que se pueden instalar en un ámbito de grupo. El **botón Agregar al** equipo no está disponible para aplicaciones que solo se pueden instalar en el ámbito personal.

![Captura de pantalla del botón Agregar al equipo.](media/manage-apps-add-app-team.png)

1. Busque la aplicación que quiera y, a continuación, seleccione la aplicación haciendo clic a la izquierda del nombre de la aplicación.
2. Seleccione **Agregar al equipo**.
3. En el **panel Agregar al** equipo, busque el equipo al que desea agregar la aplicación, seleccione el equipo y, a continuación, **seleccione Aplicar**.

## <a name="customize-an-app"></a>Personalizar una aplicación

Ahora puede personalizar una aplicación para incluir un aspecto específico según las necesidades de su organización. Vea [Personalizar aplicaciones en Teams](customize-apps.md).

## <a name="purchase-services-for-third-party-apps"></a>Comprar servicios para aplicaciones de terceros

Puede buscar y comprar licencias para los servicios ofrecidos por aplicaciones de terceros para los usuarios de su organización directamente desde la página Administrar aplicaciones. La **columna Licencias** de la tabla indica si una aplicación ofrece una suscripción saas de pago. Seleccione **Comprar ahora para** ver la información de planes y precios y comprar licencias para los usuarios. Para obtener más información, vea [Comprar servicios para Teams aplicaciones de terceros en el centro de Microsoft Teams administración](purchase-third-party-apps.md).

## <a name="grant-admin-consent-to-apps"></a>Conceder el consentimiento del administrador a las aplicaciones

Puede revisar y conceder consentimiento a las aplicaciones que soliciten permisos en nombre de todos los usuarios de su organización. Haga esto para que los usuarios no tengan que revisar y aceptar los permisos solicitados por la aplicación al iniciar la aplicación. La **columna Permisos** indica si una aplicación tiene permisos que necesitan consentimiento. Verá un **vínculo Ver detalles** para cada aplicación registrada en Azure AD que tenga permisos que necesiten consentimiento. Para obtener más información, vea [Ver permisos de aplicación y conceder consentimiento de administrador en el Microsoft Teams de administración](app-permissions-admin-center.md).

## <a name="view-resource-specific-consent-permissions"></a>Ver permisos de consentimiento específicos de recursos

Los permisos de consentimiento específico de recursos (RSC) permiten a los propietarios de equipos conceder consentimiento para que una aplicación acceda y modifique los datos de un equipo. Los permisos RSC son permisos granulares Teams específicos que definen lo que una aplicación puede hacer en un equipo específico. Puede ver los permisos de RSC en la **pestaña Permisos** de la página de detalles de la aplicación para una aplicación. Para obtener más información, vea [Ver permisos de aplicación y conceder consentimiento de administrador en el Microsoft Teams de administración](app-permissions-admin-center.md).

## <a name="manage-org-wide-app-settings"></a>Administrar la configuración de la aplicación para toda la organización

Use la configuración de aplicaciones de toda la organización para controlar si los usuarios obtienen una experiencia de aplicación personalizada en función de la licencia (próximamente), si los usuarios pueden instalar aplicaciones de terceros y si los usuarios pueden cargar o interactuar con aplicaciones personalizadas en su organización. La configuración de aplicaciones para toda la organización rige el comportamiento de todos los usuarios e invalida cualquier otra directiva de permisos de aplicación asignada a los usuarios. Puede usarla para controlar las aplicaciones malintencionadas o problemáticas.

> [!NOTE]
> Para obtener información sobre cómo usar la configuración de aplicaciones para toda la organización en Microsoft 365 Government - Government Community Cloud High GCCH and Department of Defense (DoD) deployments of Teams, vea Administrar directivas de permisos de aplicaciones [en Teams](teams-app-permission-policies.md).

1. En la página Administrar aplicaciones, seleccione **Configuración de la aplicación para toda la organización**. Después, podrá configurar las opciones que desee en el panel.

1. (Próximamente) En **Aplicaciones personalizadas**, desactive o active **Mostrar aplicaciones personalizadas basadas en licencias**. Cuando esta configuración está en, los usuarios obtienen una experiencia en la que las aplicaciones se anclan en función de su licencia. Para obtener más información, vea [Personalizar Teams aplicaciones basadas en licencia](pin-teams-apps-based-on-license.md).

    Esta característica está disponible para licencias F. Otros tipos de licencia serán compatibles en el futuro.
1. En **Aplicaciones de terceros**, desactive o active esta configuración para controlar el acceso a aplicaciones de terceros:

    - **Permitir aplicaciones de terceros**: esto controla si los usuarios pueden usar aplicaciones de terceros. Si desactiva esta configuración, los usuarios no podrán instalar ni usar aplicaciones de terceros y el estado de la aplicación de estas aplicaciones se muestra como Bloqueado en toda la organización en la  tabla.

        > [!NOTE]
        > Cuando **Permitir** aplicaciones de terceros está desactivado, los [webhooks salientes siguen habilitados](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) para todos los usuarios, pero puede controlarlas en el nivel de usuario al permitir o bloquear la aplicación Webhook saliente a través de directivas de permisos de [aplicación.](teams-app-permission-policies.md) <br><br>Tenga en cuenta que si tiene [](teams-app-permission-policies.md) directivas de permisos de aplicaciones existentes para aplicaciones  **de Microsoft** que usan la configuración Permitir aplicaciones específicas y bloquean todas las demás, y desea habilitar los webhooks salientes para los usuarios, agregue la aplicación Webhook saliente a la lista.

        > [!NOTE]
        > Los usuarios de Teams puede añadir aplicaciones cuando organizan reuniones o chats con personas de otras organizaciones. También pueden usar aplicaciones compartidas con personas de otras organizaciones cuando organizan reuniones o chats con estas organizaciones. Se aplican las directivas de datos de la organización del usuario anfitrión, así como las prácticas de intercambio de datos de cualquier aplicación de terceros compartida por la organización del usuario.

    - **Permitir las nuevas aplicaciones de terceros publicadas en la tienda de forma predeterminada**: esto controla si las nuevas aplicaciones de terceros publicadas en la tienda de aplicaciones de Teams están disponibles automáticamente en Teams. Solo puede establecer esta opción si permite aplicaciones de terceros.

1. En **Aplicaciones personalizadas**, desactive o active **Permitir interacción con aplicaciones personalizadas**. Esta configuración controla si los usuarios pueden interactuar con aplicaciones personalizadas. Para obtener más información, consulte [Administrar configuración y directivas de aplicación personalizadas en Teams](teams-custom-app-policies-and-settings.md).
1. Seleccione **Guardar para** la configuración de la aplicación de toda la organización para que su efecto se haga efectivo.

## <a name="view-security-and-compliance-information-for-microsoft-365-certified-apps"></a>Ver la información de seguridad y cumplimiento de Microsoft 365 aplicaciones certificadas

Al evaluar una aplicación para su organización, los administradores pueden usar agentes de seguridad de Acceso a la nube (CASB) independientes, como Microsoft Cloud App Security (MCAS), para buscar información sobre la seguridad y los comportamientos de una aplicación. El Teams de administración incluye información de seguridad y cumplimiento de MCAS para aplicaciones certificadas de Microsoft 365 para que tenga más información sobre si la aplicación cumple o no sus necesidades.

> [!NOTE]
> Esta característica está disponible para todos los administradores, independientemente de si su organización tiene o no una licencia compatible con MCAS.

Para obtener acceso a la información de MCAS, siga estos pasos:

1. En el Teams de administración, seleccione **Administrar aplicaciones en** **Teams aplicaciones**.
1. Seleccione **Certificación** para ordenar aplicaciones y Microsoft 365 aplicaciones certificadas en la parte superior de la tabla.
1. Elija una aplicación Microsoft 365 certificado.
1. Seleccione la **pestaña Seguridad y** cumplimiento.

![Captura de pantalla de Teams de seguridad y cumplimiento del centro de administración.](media/mcas.png)

En esta pestaña, encontrará información sobre seguridad, cumplimiento y protección de datos. También puede expandir cada lista desplegable para obtener más detalles sobre qué capacidades son compatibles con la aplicación seleccionada.

## <a name="related-topics"></a>Temas relacionados

- [Configurar la administración para aplicaciones en Teams](admin-settings.md)
