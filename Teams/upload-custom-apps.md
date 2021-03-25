---
title: Cargar las aplicaciones personalizadas en el Centro de administración de Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: joglocke, vaibhava
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo cargar las aplicaciones personalizadas en la tienda de aplicaciones de su organización en el Centro de administración de Microsoft Teams.
ms.openlocfilehash: 9473c8e2fc4284c4ca205666152ef183b0210841
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115528"
---
# <a name="publish-a-custom-app-by-uploading-an-app-package"></a>Publicar una aplicación personalizada cargando un paquete de aplicación

> [!NOTE]
> Cuando publica una aplicación personalizada de Teams, está disponible para los usuarios en la tienda de aplicaciones de su organización. Hay dos formas de publicar una aplicación personalizada y la forma en que se usa depende de cómo obtenga la aplicación. Este artículo se centra en cómo publicar una aplicación personalizada cargando un paquete de aplicación **(en formato .zip)** que un desarrollador le envía. El otro método, la aprobación de una aplicación personalizada, se <a href="/microsoftteams/manage-apps" target="_blank"></a> usa cuando un desarrollador envía una aplicación directamente a la página Administrar aplicaciones a través de la API de envío de aplicaciones de Teams. Para obtener más información sobre ese método, vea Publicar una aplicación personalizada enviada a través de la API de envío de aplicaciones <a href="/microsoftteams/submit-approve-custom-apps" target="_blank">de Teams.</a>

En este artículo se proporcionan instrucciones de un extremo a otro sobre cómo llevar la aplicación de Teams desde el desarrollo hasta la implementación hasta la detección. Esta guía se centra en los aspectos de Teams de la aplicación y está destinada a administradores y profesionales de TI. Para obtener más información sobre el desarrollo de aplicaciones de Teams, vea la <a href="/microsoftteams/platform" target="_blank">documentación para desarrolladores de Teams.</a>

![Información general sobre la aplicación desde el desarrollo hasta la implementación](media/upload-custom-apps.png)

## <a name="develop"></a>Desarrollar

### <a name="create-your-app"></a>Crear la aplicación

La plataforma de desarrolladores de Microsoft Teams facilita a los desarrolladores la integración de sus propias aplicaciones y servicios para mejorar la productividad, tomar decisiones más rápidamente y crear colaboración en torno al contenido y flujos de trabajo existentes. Las aplicaciones integradas en la plataforma de Teams son puentes entre el cliente de Teams y sus servicios y flujos de trabajo, lo que las lleva directamente al contexto de su plataforma de colaboración. Para obtener más información, vaya a la documentación <a href="/microsoftteams/platform" target="_blank">del desarrollador de Teams.</a>

## <a name="validate"></a>Validar

### <a name="get-the-app-package"></a>Obtener el paquete de la aplicación

Cuando la aplicación esté lista para su uso en producción, el desarrollador debe producir un paquete de aplicación. Para ello, <a href="/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">pueden usar App Studio.</a> Le enviarán el archivo en formato .zip.

Microsoft usa <a href="/microsoftteams/platform/publishing/office-store-approval" target="_blank">estas directrices para</a> garantizar que las aplicaciones cumplan los estándares de calidad y seguridad de la tienda global de aplicaciones de Teams.

### <a name="allow-trusted-users-to-upload-custom-apps"></a>Permitir que los usuarios de confianza carguen aplicaciones personalizadas

Para validar que la aplicación funciona correctamente en el espacio empresarial de producción, debe permitir que usted mismo o los usuarios de confianza carguen aplicaciones personalizadas en el espacio empresarial de producción. Para <a href="/microsoftteams/teams-app-setup-policies" target="_blank">ello, use directivas de configuración</a> de aplicaciones.

> [!NOTE]
> Si no le resulta cómodo cargar la aplicación en el espacio empresarial de producción para su validación, incluso [](#upload) para usted o usuarios de confianza, puede omitir este paso y seguir los pasos de las secciones Cargar y Configurar [y](#set-up-and-manage) administrar para publicar la aplicación no validada en la tienda de aplicaciones de su organización. A continuación, restrinja el acceso a esa aplicación solo a usted mismo y a los usuarios en los que confía. Estos usuarios pueden obtener la aplicación desde la tienda de aplicaciones de su organización para realizar la validación. Después de validar la aplicación, use las mismas directivas de permisos para abrir el acceso y la implementación de la aplicación para su uso en producción.

Para permitir que los usuarios de confianza carguen aplicaciones personalizadas, siga estos pasos:

1. Activa la configuración **Permitir interacción con aplicaciones** personalizadas para toda la organización. Para ello:
    1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a Aplicaciones de **Teams** Administrar aplicaciones y, a continuación, haga clic en Configuración de aplicaciones  >  para toda la **organización.**
    2. En **Aplicaciones personalizadas,** activa **Permitir interacción con aplicaciones** personalizadas y, a continuación, haz clic en **Guardar.**
2. Desactive la configuración **Cargar aplicaciones personalizadas** en la directiva de configuración global de aplicaciones. Para ello:
    1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a Directivas de configuración de aplicaciones de **Teams** y, a continuación, haga clic en la  >  directiva **Global (predeterminada** para toda la organización).
    2. Desactive Cargar **aplicaciones personalizadas** y, a continuación, haga clic **en Guardar.**
3. Cree una nueva directiva de configuración de aplicaciones que permita cargar aplicaciones personalizadas y asignarla a su conjunto de usuarios de confianza. Para ello:
    1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a Directivas de configuración de aplicaciones de **Teams** y, a continuación, haga  >  clic en **Agregar**. Asigne un nombre y una descripción a la nueva directiva, active Cargar aplicaciones **personalizadas** y, a continuación, haga clic en **Guardar.**
    2. Seleccione la nueva directiva que creó y, a continuación, haga clic **en Administrar usuarios.** Busque un usuario, haga clic **en Agregar** y, a continuación, haga clic en **Aplicar.** Repita este paso para asignar la directiva a todos los usuarios de confianza.

        ![Captura de pantalla de la página "Agregar directiva de configuración de aplicaciones"](media/manage-your-lob-apps-new-app-setup-policy.png)

    Estos usuarios ahora pueden cargar el manifiesto de la aplicación para validar que la aplicación funciona correctamente en el espacio empresarial de producción.

## <a name="upload"></a>Cargar

Para que la aplicación esté disponible para los usuarios de la tienda de aplicaciones de su organización, cargue la aplicación. Puede hacerlo en la página Administrar <a href="/microsoftteams/manage-apps" target="_blank">aplicaciones</a> del Centro de administración de Microsoft Teams.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Aplicaciones de Teams** > **Administrar aplicaciones**.
2. Haga **clic en Cargar,** **haga clic en** Seleccionar un archivo y, a continuación, seleccione el paquete de aplicación que recibió del desarrollador.

   ![Captura de pantalla de carga de una aplicación en el centro de administración](media/manage-your-lob-apps-upload-new-app.png) 

## <a name="set-up-and-manage"></a>Configurar y administrar

### <a name="control-access-to-the-app"></a>Controlar el acceso a la aplicación

De forma predeterminada, todos los usuarios de su organización pueden acceder a la aplicación en la tienda de aplicaciones de su organización. Para restringir y controlar quién tiene permiso para usar la aplicación, puede crear y asignar una directiva de permisos de aplicación. Para obtener más información, consulte <a href="/microsoftteams/teams-app-permission-policies" target="_blank">Administrar configuración y directivas de aplicación personalizadas en Teams</a>.

### <a name="pin-and-install-the-app-for-users-to-discover"></a>Anclar e instalar la aplicación para que los usuarios lo descubran

De forma predeterminada, para que los usuarios encuentren la aplicación que tienen que ir a la tienda de aplicaciones de su organización y examinarla o buscarla. Para que sea más fácil para los usuarios acceder a la aplicación, puede anclar la aplicación a la barra de aplicaciones en Teams. Para ello, cree una directiva de configuración de la aplicación y asígnela a los usuarios. Para obtener más información, consulte <a href="/microsoftteams/teams-app-setup-policies" target="_blank">Administrar las directivas de configuración de aplicaciones en Teams</a>.

### <a name="search-the-audit-log-for-teams-app-events"></a>Buscar eventos de la aplicación Teams en el registro de auditoría

Puede buscar en el registro de auditoría para ver la actividad de las aplicaciones de Teams en su organización. Para obtener más información sobre cómo buscar en el registro de auditoría y ver una lista de las actividades de Teams que se registran en el registro de auditoría, vea Buscar eventos en teams en el registro de <a href="/microsoftteams/audit-log-events" target="_blank">auditoría.</a>

Para que pueda buscar en el registro de auditoría, primero debe activar la característica de auditoría en el <a href="https://protection.office.com" target="_blank">Centro de seguridad y cumplimiento</a>. Para obtener más información, consulte <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">Activar o desactivar la búsqueda de registros de auditoría</a>. Tenga en cuenta que los datos de auditoría solo están disponibles desde el momento en que activó la característica de auditoría.

## <a name="discover-and-adopt"></a>Descubrir y adoptar

Los usuarios que tengan permisos para la aplicación pueden encontrarla en la tienda de aplicaciones de su organización. Vaya a **Nombre de la organización *integrado*** en la página Aplicaciones para buscar las aplicaciones personalizadas de su organización.

![Captura de pantalla de la página Aplicaciones que muestra la aplicación publicada ](media/custom-app-lifecycle-discovery.png)

Si creó y asignó una directiva de configuración de aplicaciones, la aplicación se ancla a la barra de aplicaciones de Teams para facilitar el acceso a los usuarios a los que se les asignó la directiva.

## <a name="update"></a>Actualización

Para actualizar una aplicación, los desarrolladores deben seguir los pasos de [las](#develop) secciones Desarrollar [y](#validate) validar.

Puede actualizar la aplicación en la página Administrar aplicaciones del Centro de administración de Microsoft Teams. Para ello, en el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a Aplicaciones de **Teams Administrar**  >  **aplicaciones.** Haga clic en el nombre de la aplicación y, a continuación, haga clic **en Actualizar.** Al hacerlo, se reemplaza la aplicación existente y todas las directivas de permisos de la aplicación y las directivas de configuración de la aplicación permanecen vigentes para la aplicación actualizada.

### <a name="end-user-update-experience"></a>Experiencia de actualización del usuario final

En la mayoría de los casos, después de completar una actualización de la aplicación, la nueva versión aparece automáticamente para los usuarios finales. Sin embargo, hay algunas actualizaciones del manifiesto de <a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams</a> que requieren la aceptación del usuario para completar:

* Se ha agregado o quitado un bot
* Se ha cambiado la propiedad "botId" de un bot existente
* Se ha cambiado la propiedad "isNotificationOnly" de un bot existente
* La propiedad "supportsFiles" del bot ha cambiado
* Se ha agregado o quitado una extensión de mensajería
* Se ha agregado un nuevo conector
* Se ha agregado una nueva pestaña estática
* Se ha agregado una nueva pestaña configurable
* Se han cambiado las propiedades dentro de "webApplicationInfo"

![Captura de pantalla de la lista de aplicaciones, que muestra las aplicaciones que tienen una nueva versión disponible](media/manage-your-custom-apps-update1.png)

![Captura de pantalla de la opción de actualización de una aplicación](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a>Temas relacionados

- [Publicar una aplicación personalizada enviada a través de la API de envío de aplicaciones de Teams](submit-approve-custom-apps.md)
- [Administrar las aplicaciones en el Centro de administración de Microsoft Teams](manage-apps.md)
- [Administrar configuración y directivas de aplicación personalizadas en Teams](teams-custom-app-policies-and-settings.md)
- [Administrar directivas de permisos de aplicación en Teams](teams-app-permission-policies.md)
- [Administrar directivas de configuración de aplicación en Teams](teams-app-setup-policies.md)