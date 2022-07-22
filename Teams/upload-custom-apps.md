---
title: Cargar las aplicaciones personalizadas en el Centro de administración de Microsoft Teams
author: guptaashish
ms.author: guptaashish
manager: prkosh
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
ms.localizationpriority: medium
search.appverid: MET150
description: Obtenga información sobre cómo cargar sus aplicaciones personalizadas en la tienda de aplicaciones de su organización en el Centro de administración de Microsoft Teams.
ms.openlocfilehash: 8f7968a53b70ac8ffa871d03adacd648ec047c52
ms.sourcegitcommit: 70185cd963c5a9d539e65e302d4230018209ecae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2022
ms.locfileid: "66958055"
---
# <a name="publish-a-custom-app-by-uploading-an-app-package"></a>Publicar una aplicación personalizada cargando un paquete de aplicación

> [!NOTE]
> Al publicar una aplicación de Teams personalizada, está disponible para los usuarios de la tienda de aplicaciones de su organización. Hay dos formas de publicar una aplicación personalizada y la manera en que se usa depende de cómo se obtenga la aplicación. **Este artículo se centra en cómo publicar una aplicación personalizada cargando un paquete de aplicación (en formato de .zip) que le envíe un desarrollador**. El otro método, aprobar una aplicación personalizada, se usa cuando un desarrollador envía una aplicación directamente a la página [Administrar aplicaciones](manage-apps.md) a través de la API de envío de aplicaciones de Teams. Para obtener más información sobre ese método, consulte [Publicar una aplicación personalizada enviada a través de la API de envío de aplicaciones de Teams](submit-approve-custom-apps.md).

Este artículo proporciona instrucciones de un extremo a otro para llevar su aplicación de Teams del desarrollo a la implementación al descubrimiento. Esta guía se centra en los aspectos de Teams de la aplicación y está destinada a administradores y profesionales de TI. Para obtener más información sobre el desarrollo de aplicaciones de Teams, consulte la [documentación del desarrollador de Teams](/microsoftteams/platform/).

![Información general sobre la aplicación, desde el desarrollo hasta la implementación.](media/upload-custom-apps.png)

## <a name="create-your-app"></a>Crear la aplicación

La plataforma para desarrolladores de Microsoft Teams facilita a los desarrolladores la integración de sus propias aplicaciones y servicios para mejorar la productividad, tomar decisiones más rápidamente y crear colaboración en torno al contenido y los flujos de trabajo existentes. Las aplicaciones creadas en la plataforma Teams son puentes entre el cliente de Teams y sus servicios y flujos de trabajo, que las llevan directamente al contexto de su plataforma de colaboración. Para obtener más información, vaya a la [documentación del desarrollador de Teams](/microsoftteams/platform/).

## <a name="validate"></a>Validar

### <a name="get-the-app-package"></a>Obtener el paquete de la aplicación

Cuando la aplicación esté lista para usarse en producción, el desarrollador debe producir un paquete de aplicación. Pueden usar [App Studio](/microsoftteams/platform/concepts/build-and-test/app-studio-overview). Le enviarán el archivo en .zip formato.

Todas las aplicaciones de la tienda teams pasan una [validación de aplicación](overview-of-app-validation.md) obligatoria para cumplir con los estándares de calidad y seguridad de la tienda de aplicaciones global de Teams. Además, Microsoft recomienda encarecidamente a los desarrolladores de aplicaciones que participen en un programa opcional de [cumplimiento](overview-of-app-certification.md) de aplicaciones que indique controles mejorados de cumplimiento, seguridad y privacidad. Para obtener más información, consulte [Directrices de validación de aplicaciones de Teams](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/teams-store-validation-guidelines).

### <a name="allow-trusted-users-to-upload-custom-apps"></a>Permitir que los usuarios de confianza carguen aplicaciones personalizadas

Para validar que la aplicación funciona correctamente en su inquilino de producción, debe permitirse a sí mismo y/o a los usuarios de confianza cargar aplicaciones personalizadas en el inquilino de producción. Para ello, debe usar [directivas de configuración](teams-app-setup-policies.md) de aplicaciones.

> [!NOTE]
> Si no le resulta cómodo cargar la aplicación en su espacio empresarial de producción para validación, incluso para usted o para los usuarios de confianza, puede omitir este paso y seguir los pasos de las secciones [Cargar](#upload) y [configurar y administrar](#set-up-and-manage) para publicar la aplicación no validada en la tienda de aplicaciones de su organización. A continuación, restrinja el acceso a esa aplicación solo a usted y a los usuarios en los que confía. Después, estos usuarios pueden obtener la aplicación en la tienda de aplicaciones de su organización para realizar la validación. Una vez validada la aplicación, use las mismas directivas de permisos para abrir el acceso e implementar la aplicación para su uso en producción.

Para permitir que los usuarios de confianza carguen aplicaciones personalizadas, siga estos pasos:

1. Activa la opción **Permitir interacción con aplicaciones personalizadas** para toda la organización. Para ello:

    1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Aplicaciones** >  de Teams **Administrar aplicaciones** y, a continuación, haga clic en **Configuración de aplicaciones para toda la organización**.

    1. En **Aplicaciones personalizadas**, activa **Permitir interacción con aplicaciones personalizadas** y, a continuación, haz clic en **Guardar**.

1. Desactive la opción **Cargar aplicaciones personalizadas** en la directiva de configuración global de aplicaciones. Para ello:

    1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Directivas de configuración** de **aplicaciones** >  de Teams y haga clic en la directiva **Global (predeterminada para toda** la organización).

    1. Desactive **Cargar aplicaciones personalizadas** y, a continuación, haga clic en **Guardar**.

1. Cree una nueva directiva de configuración de aplicaciones que permita cargar aplicaciones personalizadas y asignarla a su conjunto de usuarios de confianza. Para ello:

    1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Directivas** de **configuración** de aplicaciones  >  de Teams y, a continuación, haga clic en **Agregar**. Asigne un nombre y una descripción a la nueva directiva, active **Cargar aplicaciones personalizadas** y, a continuación, haga clic en **Guardar**.

    1. Seleccione la nueva directiva que ha creado y, a continuación, haga clic en **Administrar usuarios**. Busque un usuario, haga clic en **Agregar** y, a continuación, haga clic en **Aplicar**. Repita este paso para asignar la directiva a todos los usuarios de confianza.

       ![Captura de pantalla de la página "Agregar directiva de configuración de aplicaciones"](media/manage-your-lob-apps-new-app-setup-policy.png)

Estos usuarios ahora pueden cargar el manifiesto de la aplicación para validar que la aplicación funciona correctamente en el espacio empresarial de producción.

## <a name="upload"></a>Subir

Para que la aplicación esté disponible para los usuarios de la tienda de aplicaciones de su organización, cargue la aplicación.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a Aplicaciones  > **de Teams****[Administrar aplicaciones](https://admin.teams.microsoft.com/policies/manage-apps)**.
1. Seleccione **Cargar**, haga clic en **Cargar**, seleccione el paquete de la aplicación que ha recibido del desarrollador y seleccione **Abrir**.

   ![Captura de pantalla de la carga de una aplicación en el centro de administración.](media/manage-your-lob-apps-upload-new-app.png)

## <a name="set-up-and-manage"></a>Configurar y administrar

### <a name="control-access-to-the-app"></a>Controlar el acceso a la aplicación

De forma predeterminada, todos los usuarios de su organización pueden acceder a la aplicación en la tienda de aplicaciones de su organización. Para restringir y controlar quién tiene permiso para usar la aplicación, puede crear y asignar una directiva de permisos de aplicación. Para obtener más información, consulte [Administrar configuración y directivas de aplicación personalizadas en Teams](teams-app-permission-policies.md).

### <a name="pin-and-install-the-app-for-users-to-discover"></a>Anclar e instalar la aplicación para que los usuarios la descubran

De forma predeterminada, para que los usuarios encuentren la aplicación, tienen que ir a la tienda de aplicaciones de su organización y examinarla o buscarla. Para que sea más fácil para los usuarios acceder a la aplicación, puede anclar la aplicación a la barra de la aplicación en Teams. Para ello, cree una directiva de configuración de la aplicación y asígnela a los usuarios. Para obtener más información, consulte [Administrar las directivas de configuración de aplicaciones en Teams](teams-app-setup-policies.md).

### <a name="search-the-audit-log-for-teams-app-events"></a>Buscar eventos de la aplicación Teams en el registro de auditoría

Puede buscar en el registro de auditoría para ver la actividad de las aplicaciones de Teams en su organización. Para obtener más información sobre la auditoría de actividades de Teams, consulte [Buscar eventos en Teams en el registro de auditoría](audit-app-management-activities.md).

Para que pueda buscar en el registro de auditoría, primero debe activar la característica de auditoría en el [Centro de seguridad y cumplimiento](https://sip.protection.office.com/homepage). Para obtener más información, consulte [Activar o desactivar la búsqueda de registros de auditoría](/microsoft-365/compliance/turn-audit-log-search-on-or-off). Tenga en cuenta que los datos de auditoría solo están disponibles desde el momento en que activó la característica de auditoría.

## <a name="discover-and-adopt"></a>Descubrir y adoptar

Los usuarios finales que tienen permisos para la aplicación pueden encontrarla en la tienda de aplicaciones de su organización. Vaya a **Creado para el *nombre de su organización*** en la página Aplicaciones para buscar las aplicaciones personalizadas de su organización.

:::image type="content" source="media/custom-app-lifecycle-discovery.png" alt-text="Captura de pantalla de la tienda de Teams que muestra una aplicación personalizada publicada para la organización" lightbox="media/custom-app-lifecycle-discovery.png":::

Si ha creado y asignado una directiva de configuración de aplicaciones, la aplicación se ancla a la barra de la aplicación en Teams para facilitar el acceso a los usuarios a los que se asignó la directiva.

## <a name="update"></a>Actualización

Para actualizar una aplicación, los desarrolladores siguen los pasos de las secciones [Crear la aplicación](#create-your-app) y [Validar](#validate) .

Puede actualizar la aplicación en la página Administrar aplicaciones del Centro de administración de Microsoft Teams. Para ello, en el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a Aplicaciones  > **de Teams****Administrar aplicaciones**. Haga clic en el nombre de la aplicación y, a continuación, haga clic en **Actualizar**. Al hacerlo, se reemplaza la aplicación existente, y todas las directivas de permisos y directivas de configuración de aplicaciones se aplican a la aplicación actualizada.

### <a name="end-user-update-experience"></a>Experiencia de actualización para el usuario final

En la mayoría de los casos, después de completar una actualización de aplicación, la nueva versión aparece automáticamente para los usuarios finales. Para obtener más información, consulte [experiencia de actualización para el usuario final](apps-update-experience.md).

## <a name="remove"></a>Quitar

Para quitar una aplicación, sigue estos pasos:

1. Inicie la sesión en el Centro de administración de Teams
1. Acceda a la página **[Administrar aplicaciones](https://admin.teams.microsoft.com/policies/manage-apps)** de **las aplicaciones** >  de Teams.
1. Haz clic en el nombre de la aplicación para abrir la página de detalles de la aplicación.
1. Junto al banner de la aplicación, seleccione **Eliminar acciones** > .
1. En el cuadro de diálogo, seleccione **Eliminar**.

## <a name="related-articles"></a>Artículos relacionados

* [Publicar una aplicación personalizada enviada a través de la API de envío de aplicaciones de Teams](submit-approve-custom-apps.md)
* [Administrar las aplicaciones en el Centro de administración de Microsoft Teams](manage-apps.md)
* [Administrar configuración y directivas de aplicación personalizadas en Teams](teams-custom-app-policies-and-settings.md)
* [Administrar directivas de permisos de aplicación en Teams](teams-app-permission-policies.md)
* [Administrar directivas de configuración de aplicación en Teams](teams-app-setup-policies.md)
