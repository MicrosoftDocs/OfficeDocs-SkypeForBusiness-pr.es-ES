---
title: Cargar las aplicaciones personalizadas en el centro de administración de Microsoft Teams
author: lanachin
ms.author: v-lanac
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
description: Aprenda a cargar sus aplicaciones personalizadas en la tienda de aplicaciones de su organización en el centro de administración de Microsoft Teams.
ms.openlocfilehash: 68d7dbc16ca3aa6258fd5f976688240095226934
ms.sourcegitcommit: ab094058e3ffa974527fce8a331dad609ac19609
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "46552914"
---
# <a name="publish-a-custom-app-by-uploading-an-app-package"></a>Publicar una aplicación personalizada mediante la carga de un paquete de la aplicación

> [!NOTE]
> Al publicar una aplicación de Teams personalizada, esta estará disponible para los usuarios de la tienda de aplicaciones de su organización. Hay dos formas de publicar una aplicación personalizada y la forma de usarla depende de cómo obtenga la aplicación. **Este artículo se centra en cómo publicar una aplicación personalizada al cargar un paquete de la aplicación (en formato. zip) que le envía un desarrollador**. El otro método, la aprobación de una aplicación personalizada, se usa cuando un desarrollador envía una aplicación directamente a la página de <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Administración de aplicaciones</a> a través de la API de envío de la aplicación de Teams. Para obtener más información sobre ese método, vea <a href="https://docs.microsoft.com/microsoftteams/submit-approve-custom-apps" target="_blank">publicar una aplicación personalizada enviada a través de la API de envío de la aplicación de Teams</a>.

En este artículo se proporcionan instrucciones completas sobre cómo llevar la aplicación de su equipo de desarrollo a la implementación hasta su descubrimiento. Esta guía se centra en los aspectos de los equipos de la aplicación y está pensado para administradores y profesionales de ti. Para obtener más información sobre el desarrollo de aplicaciones de Teams, consulte la <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">documentación para desarrolladores de equipos</a>.

![Información general de la aplicación desde el desarrollo hasta la implementación](media/upload-custom-apps.png)

## <a name="develop"></a>Desarrollar

### <a name="create-your-app"></a>Crear la aplicación

La plataforma de desarrollo de Microsoft Teams facilita la integración de sus propias aplicaciones y servicios para mejorar la productividad, tomar decisiones más rápido y crear colaboración sobre el contenido y los flujos de trabajo existentes. Las aplicaciones integradas en la plataforma de Teams son puentes entre el cliente de Teams y los servicios y flujos de trabajo, que se incluyen directamente en el contexto de la plataforma de colaboración. Para obtener más información, vaya a la <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">documentación para desarrolladores de Teams</a>.

## <a name="validate"></a>Valide

### <a name="get-the-app-package"></a>Obtener el paquete de la aplicación

Cuando la aplicación está lista para su uso en producción, el desarrollador debe producir un paquete de la aplicación. Pueden usar <a href="https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">App Studio</a> para eso. Le enviarán el archivo con el formato. zip.

Microsoft usa <a href="https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-approval" target="_blank">estas directrices</a> para garantizar que las aplicaciones cumplan con los estándares de calidad y seguridad de la tienda de aplicaciones global de Teams.

### <a name="allow-trusted-users-to-upload-custom-apps"></a>Permitir a los usuarios de confianza cargar aplicaciones personalizadas

Para comprobar que la aplicación está funcionando correctamente en su inquilino de producción, debe permitir que usted o usuarios de confianza carguen aplicaciones personalizadas en el inquilino de producción. Use <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">las directivas de configuración</a> de la aplicación para hacerlo.

> [!NOTE]
> Si no está familiarizado con la carga de la aplicación en el inquilino de producción para su validación, incluso para usuarios de usted o de confianza, puede omitir este paso y seguir los pasos de las secciones [cargar](#upload) y [configurar y administrar](#set-up-and-manage) para publicar la aplicación no validada en la tienda de aplicaciones de su organización. Después, restrinja el acceso a esa aplicación solo a usted y a los usuarios de confianza. Estos usuarios pueden obtener la aplicación de la tienda de aplicaciones de su organización para realizar la validación. Una vez validada la aplicación, use las mismas directivas de permisos para abrir Access y desplace la aplicación para su uso en producción.

Para permitir que los usuarios de confianza carguen aplicaciones personalizadas, siga estos pasos:

1. Active la opción de aplicación **permitir la interacción con aplicaciones personalizadas** de la organización. Para ello, haga lo siguiente:
    1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **aplicaciones de Teams**  >  **Manage apps**y, a continuación, haga clic en **configuración de aplicaciones en toda la organización**.
    2. En **aplicaciones personalizadas**, Active **permitir la interacción con aplicaciones personalizadas**y, a continuación, haga clic en **Guardar**.
2. Desactive la opción **cargar aplicaciones personalizadas** en la Directiva configuración global de la aplicación. Para ello, haga lo siguiente:
    1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a directivas de configuración de las **aplicaciones de Teams**  >  **Setup policies**y, a continuación, haga clic en la directiva **global (valor predeterminado de toda la organización)** .
    2. Desactive **cargar aplicaciones personalizadas**y, a continuación, haga clic en **Guardar**.
3. Cree una nueva Directiva de configuración de aplicaciones que permita cargar aplicaciones personalizadas y asignarlas a su conjunto de usuarios de confianza. Para ello, haga lo siguiente:
    1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a directivas de configuración de las **aplicaciones de Teams**  >  **Setup policies**y, a continuación, haga clic en **Agregar**. Asigne un nombre y una descripción a la nueva Directiva, Active **cargar aplicaciones personalizadas**y, a continuación, haga clic en **Guardar**.
    2. Seleccione la nueva directiva que ha creado y, a continuación, haga clic en **administrar usuarios**. Busque un usuario, haga clic en **Agregar**y, a continuación, haga clic en **aplicar**. Repita este paso para asignar la Directiva a todos los usuarios de confianza.

        ![Captura de pantalla de la página "agregar Directiva de configuración de aplicaciones"](media/manage-your-lob-apps-new-app-setup-policy.png)

    Estos usuarios ahora pueden cargar el manifiesto de la aplicación para validar que la aplicación está funcionando correctamente en el inquilino de producción.

## <a name="upload"></a>Cargar

Para que la aplicación esté disponible para los usuarios en la tienda de aplicaciones de su organización, cargue la aplicación. Puede hacerlo en la página <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Administrar aplicaciones</a> del centro de administración de Microsoft Teams.

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **aplicaciones de Teams**  >  **Manage apps**.
2. Haga clic en **cargar**, haga clic en **seleccionar un archivo**y, a continuación, seleccione el paquete de la aplicación que ha recibido del desarrollador.

   ![Captura de pantalla de cómo cargar una aplicación en el centro de administración](media/manage-your-lob-apps-upload-new-app.png) 

## <a name="set-up-and-manage"></a>Configurar y administrar

### <a name="control-access-to-the-app"></a>Controlar el acceso a la aplicación

De forma predeterminada, todos los usuarios de su organización pueden acceder a la aplicación en la tienda de aplicaciones de su organización. Para restringir y controlar quién tiene permiso para usar la aplicación, puede crear y asignar una directiva de permisos de aplicación. Para obtener más información, vea <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">Administrar directivas de permisos de aplicaciones en Teams</a>.

### <a name="pin-and-install-the-app-for-users-to-discover"></a>Anclar e instalar la aplicación para que los usuarios puedan descubrir

De forma predeterminada, para que los usuarios encuentren la aplicación, deben ir a la tienda de aplicaciones de su organización y examinarla o buscarla. Para facilitar a los usuarios el acceso a la aplicación, puede anclar la aplicación a la barra de aplicaciones de Teams. Para ello, cree una directiva de configuración de aplicaciones y asígnela a los usuarios. Para obtener más información, vea <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">Administrar directivas de configuración de aplicaciones en Teams</a>.

## <a name="discover-and-adopt"></a>Descubrir y aprobar

Los usuarios que tienen permisos para la aplicación pueden encontrarla en la tienda de aplicaciones de su organización. Vaya a **creado para *el nombre* ** de la organización en la página aplicaciones para buscar las aplicaciones personalizadas de su organización.

![Captura de pantalla de la página de aplicaciones que muestra la aplicación publicada ](media/custom-app-lifecycle-discovery.png)

Si creó y asignó una directiva de configuración de aplicaciones, la aplicación está anclada a la barra de aplicaciones de Teams para facilitar el acceso a los usuarios que se asignaron a la Directiva.

## <a name="update"></a>Actualización

Para actualizar una aplicación, los desarrolladores deben seguir los pasos de las secciones [desarrollar](#develop) y [validar](#validate) .

Puede actualizar la aplicación en la página Manage Apps en el centro de administración de Microsoft Teams. Para ello, en el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **aplicaciones de Teams**  >  **Administrar aplicaciones**. Haga clic en el nombre de la aplicación y, a continuación, en **Actualizar**. Al hacerlo, se reemplaza la aplicación existente y todas las directivas de permisos de aplicaciones y de configuración de la aplicación siguen aplicándose para la aplicación actualizada.

### <a name="end-user-update-experience"></a>Experiencia de actualización de usuario final

En la mayoría de los casos, después de completar una actualización de la aplicación, la nueva versión aparece automáticamente para los usuarios finales. Sin embargo, hay algunas actualizaciones del <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">manifiesto de Microsoft Teams</a> que requieren la aceptación del usuario:

* Se ha agregado o eliminado un bot
* Ha cambiado la propiedad "botId" de un bot existente
* Ha cambiado la propiedad "isNotificationOnly" de un bot existente
* La propiedad "supportsFiles" del bot ha cambiado
* Se ha agregado o eliminado una extensión de mensajería
* Se agregó un nuevo conector
* Se ha agregado una nueva pestaña estática
* Se ha agregado una nueva pestaña configurable
* Las propiedades de "webApplicationInfo" han cambiado

![Captura de pantalla de la lista de aplicaciones, que muestra las aplicaciones que tienen una nueva versión disponible](media/manage-your-custom-apps-update1.png)

![Captura de pantalla de la opción de actualización de una aplicación](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a>Temas relacionados

- [Publicar una aplicación personalizada enviada a través de la API de envío de la aplicación de Teams](submit-approve-custom-apps.md)
- [Administrar las aplicaciones en el centro de administración de Microsoft Teams](manage-apps.md)
- [Administrar configuración y directivas de aplicación personalizadas en Teams](teams-custom-app-policies-and-settings.md)
- [Administrar directivas de permisos de aplicación en Teams](teams-app-permission-policies.md)
- [Administrar directivas de configuración de aplicación en Teams](teams-app-setup-policies.md)
