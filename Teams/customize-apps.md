---
title: Usar la personalización de aplicaciones para personalizar las aplicaciones según las necesidades de su organización
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.date: 09/20/2022
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Obtenga información sobre cómo cambiar los metadatos y la apariencia de una aplicación para cambiar su nombre para una mejor adopción en su organización.
ms.openlocfilehash: 870ee97b874b2600abf136cd045d47e9fca934d3
ms.sourcegitcommit: 22f66e314e631b3c9262c5c7dc5664472f42971e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2022
ms.locfileid: "68912659"
---
# <a name="use-app-customization-to-update-branding-of-apps-in-your-org-store"></a>Usar la personalización de aplicaciones para actualizar la personalización de marca de las aplicaciones en la tienda de la organización

Los administradores de Microsoft Teams pueden modificar la apariencia de algunas aplicaciones de Teams para proporcionar una experiencia personalizada con personalización de marca a los usuarios finales de su organización. Estas modificaciones pueden mejorar la experiencia de la tienda de Teams para los usuarios finales y ayudar a ajustarse a la personalización de marca de la organización. Por ejemplo, los administradores pueden modificar la descripción y el icono de una aplicación. La personalización facilita que los usuarios finales identifiquen la aplicación como herramientas internas, comprendan su caso de uso específico de la organización y la usen con confianza. Los administradores realizan estas actualizaciones cambiando algunos metadatos o propiedades de una aplicación. Los cambios solo están disponibles en su organización. Esta funcionalidad se denomina personalización de aplicaciones.

Los administradores solo pueden personalizar las aplicaciones si el desarrollador de aplicaciones permite personalizar su aplicación. Aunque Teams ofrece una opción para personalizar las siguientes propiedades, los desarrolladores de aplicaciones controlan qué propiedades pueden personalizar realmente cualquier administrador.

* Nombre corto
* Descripción breve
* Descripción completa
* URL de la directiva de privacidad
* URL del sitio web
* Dirección URL de las condiciones de uso
* Icono de aplicación
* Color de contorno del icono
* Resaltar color

Para obtener información detallada sobre cada una de estas propiedades, consulte el [esquema de manifiesto de Teams](/microsoftteams/platform/resources/schema/manifest-schema) en la documentación de desarrolladores de Teams.

> [!NOTE]
> Debe tener una licencia de cliente de Teams para personalizar la información de la aplicación.

## <a name="verify-if-an-app-is-customizable"></a>Comprobar si una aplicación se puede personalizar

No se pueden personalizar todas las aplicaciones. Si un desarrollador de aplicaciones permite la personalización de su aplicación, solo entonces puede modificar la apariencia de la aplicación. Para comprobar si la aplicación de tu elección es personalizable o no, sigue estos pasos:

1. Inicie sesión en el Centro de administración de Teams y acceda a **las aplicaciones** > **[de Teams Administrar aplicaciones](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Opcionalmente, si la columna **Personalizable** no está visible, seleccione Editar columnas :::image type="icon" source="media/settings-icon-16px.svg"::: y cambie **la opción Personalizable** a **Activado**.

1. Busca en la aplicación que quieras personalizar con el nombre de la aplicación. Comprueba en la columna **Personalizable** si el desarrollador de la aplicación permite personalizar la aplicación o no.

   :::image type="content" source="media/customizable-apps-in-tac.png" alt-text="La captura de pantalla muestra que la columna personalizable del centro de administración le ayuda a comprobar si una aplicación se puede personalizar o no.":::

Para conocer todas las aplicaciones personalizables de la tienda de Teams, **ordene** la columna Personalizable.

## <a name="customize-an-app"></a>Personalizar una aplicación

Para cambiar la apariencia de una aplicación en la tienda de Teams de su organización, siga estos pasos:

1. Inicie sesión en el Centro de administración de Teams y acceda a **las aplicaciones** > **[de Teams Administrar aplicaciones](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Busca en la aplicación que quieras personalizar con el nombre de la aplicación y [asegúrate de que se pueda personalizar](#verify-if-an-app-is-customizable).

1. Para abrir la interfaz de usuario y personalizar campos de metadatos individuales, siga uno de estos pasos:

   * Selecciona la fila de una aplicación y luego selecciona **Personalizar** :::image type="icon" source="media/edit-pen-icon.png"::: en la barra de herramientas de la página Administrar aplicaciones.

   * Selecciona el nombre de la aplicación para abrir la página de detalles de la aplicación y, a continuación, selecciona el icono :::image type="icon" source="media/edit-pen-icon.png"::: de edición en **Personalizable**.

   * Seleccione el nombre de la aplicación para abrir la página de detalles de la aplicación y, a continuación, seleccione **Personalizar acciones** > .

     :::image type="content" source="media/customize-action-menu.png" alt-text="La captura de pantalla muestra una opción para personalizar una aplicación abriendo el menú Acciones y seleccionando Personalizar opción en la página de detalles de la aplicación." lightbox="media/customize-action-menu-expanded.png":::

1. Personalice uno o varios de los campos disponibles. Solo se muestran esos campos de metadatos y son personalizables que el desarrollador de aplicaciones ha permitido. Para conocer las limitaciones de algunos de los campos, consulte [consideraciones y limitaciones de los campos personalizables](#considerations-and-limitations-of-app-customization).

   :::image type="content" source="media/customize-settings.png" alt-text="La captura de pantalla muestra el nombre y la descripción en la interfaz de usuario personalizar.":::

1. Después de personalizar la aplicación, seleccione **Aplicar**. Para comprobar los cambios que has realizado, consulta [los detalles de la vista previa de la aplicación](#preview-app-customizations). Para deshacer los cambios, consulta [restablecer los detalles de la aplicación a los valores predeterminados](#reset-app-details-to-default-values).

1. Seleccione **Publicar** para publicar la aplicación personalizada en la tienda de su organización.

La aplicación aparece en la página **Administrar aplicaciones** y en la tienda y el cliente de Teams (disponible a través de la web, el móvil o el cliente de escritorio) con los detalles actualizados. La modificación puede tardar unas horas en mostrarse.

## <a name="preview-app-customizations"></a>Vista previa de personalizaciones de aplicaciones

Para ver los cambios después de guardar las personalizaciones, vea la página de detalles de la aplicación.

1. Inicie sesión en el Centro de administración de Teams y acceda a **las aplicaciones** > **[de Teams Administrar aplicaciones](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Para abrir la página de detalles de la aplicación, selecciona el nombre de la aplicación.

1. Ver los detalles de la aplicación, incluido el nombre original de la aplicación en el campo **Nombre corto del editor**. El campo solo está visible si ha cambiado el nombre corto de la aplicación.

   :::image type="content" source="media/original-app-version.png" alt-text="La captura de pantalla muestra el nombre corto modificado de una aplicación.":::

Después de unas horas, los usuarios de Teams pueden ver la aplicación personalizada en la tienda de Teams en su cliente (web, móvil y de escritorio).

   :::image type="content" source="media/contoso-app.png" alt-text="La captura de pantalla muestra una aplicación personalizada en el cliente de Teams.":::

## <a name="considerations-and-limitations-of-app-customization"></a>Consideraciones y limitaciones de la personalización de aplicaciones

Tenga en cuenta los siguientes detalles sobre la funcionalidad de personalización de aplicaciones:

* Solo puedes personalizar [aplicaciones de terceros](deploy-apps-microsoft-teams-landing-page.md#third-party-apps-created-by-independent-app-developers) y no [aplicaciones personalizadas](deploy-apps-microsoft-teams-landing-page.md#custom-apps-created-within-an-organization-for-internal-use).

* No puedes personalizar ninguna aplicación en entornos de Government Community Cloud High (GCCH) ni del Departamento de Defensa (DoD).

* Una aplicación solo se puede personalizar si el desarrollador de la aplicación lo permite.

* Las modificaciones de las aplicaciones solo están disponibles en la organización.

* Solo tendrás una versión de la aplicación, ya que personalizar los detalles de la aplicación no crea una copia de la aplicación.

* Al personalizar aplicaciones y cualquier descripción relacionada con una aplicación, asegúrate de seguir las directrices que los desarrolladores de aplicaciones proporcionan en su documentación o términos de uso. Se adhiere a las leyes de derechos de autor al usar imágenes de terceros.

* Administración datos de personalización proporcionados se almacenan en la región de almacenamiento de datos más cercana.

* Es su responsabilidad asegurarse de que los vínculos a los términos de uso o a la directiva de privacidad sean válidos.

* En caso de que el desarrollador de la aplicación ya no permita que un campo se pueda personalizar, aparecerá un mensaje en la página de detalles de la aplicación que notifica al administrador sobre dicho campo. Los cambios realizados en el campo se revertirán al valor original.

* Se recomienda probar los cambios de personalización de aplicaciones en un inquilino de prueba de Teams antes de realizar estos cambios en el entorno de producción. Para obtener un inquilino de prueba, sigue las instrucciones de [Crear tu inquilino de prueba](/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant).

* Novedades tarda hasta 24 horas en mostrarse en el cliente para todos los usuarios y cuentas de administrador.

* Para que una aplicación existente se pueda personalizar, el desarrollador puede proporcionar una nueva versión de la aplicación en la tienda de Teams.

* El [informe de uso de](teams-analytics-and-reports/app-usage-report.md) aplicaciones muestra el nombre original de la aplicación que proporciona el editor, incluso si los usuarios finales usan la aplicación personalizada.

* El cuadro de diálogo de consentimiento de permisos de Microsoft Graph muestra el nombre original de la aplicación que proporciona el editor. Le ayuda a identificar con precisión una aplicación al mismo tiempo que le proporciona permisos.

* La personalización de una aplicación no cambia ninguna funcionalidad de la aplicación.

A continuación se indican las limitaciones en algunos de los campos personalizables:

| Campo personalizable | Consideración |
|:---|:---|
| Cualquier campo de dirección URL | Asegúrate de direcciones URL válidas y seguras con `https`. |
| Descripción breve | La descripción breve debe tener menos de 80 caracteres. No repita lo que aparece en la descripción completa. |
| Icono | Icono de contorno transparente en formato PNG con resolución de 32 x 32 píxeles. |
| Icono color | Icono de color completo en formato PNG con resolución de 192 x 192 píxeles. |
| Resaltar color | El color debe coincidir con el fondo del icono. |

## <a name="troubleshoot-app-customization"></a>Solucionar problemas de personalización de aplicaciones

| Errores y problemas | Posible corrección o comprensión del problema |
| --- | --- |
| Mis actualizaciones no están disponibles para mis usuarios finales. | Espere unas horas hasta que se propaguen los cambios. |
| No puedo personalizar una aplicación. | Comprueba si la [aplicación se puede personalizar o no](#verify-if-an-app-is-customizable).|
| Empecé a personalizar una aplicación, pero no puedo guardar ni aplicar mis cambios. | Respete las limitaciones de los campos. Busca errores en la interfaz de usuario y [las limitaciones de personalización de la aplicación](#considerations-and-limitations-of-app-customization). |
| La página Administrar aplicaciones no se carga correctamente. No se muestra la lista de aplicaciones. | Administración cuenta en uso debe tener asignada la licencia de Teams. |

<!--- Check ICM for error string. --->

## <a name="reset-app-details-to-default-values"></a>Restablecer los detalles de la aplicación con los valores predeterminados

Puede restablecer los detalles de la aplicación a los valores originales proporcionados por el desarrollador de la aplicación. La opción solo está disponible para la aplicación que personalice.

1. En el Centro de administración de Teams, acceda a **Aplicaciones de Teams** > **[Administrar aplicaciones](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Para abrir la página de detalles de la aplicación, selecciona el nombre de la aplicación.

1. En el menú **Acciones** , seleccione **Restablecer al valor predeterminado**.

   :::image type="content" source="media/reset-app-customization.png" alt-text="La captura de pantalla muestra la opción restablecer a la predeterminada para una aplicación personalizada.":::

## <a name="related-articles"></a>Artículos relacionados

* [Personalice la tienda de aplicaciones de su organización](customize-your-app-store.md)
* [Cambiar el nombre de la publicación de la comunidad de aplicaciones](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/rebrand-apps-to-your-own-organization-s-branding-with-app/ba-p/2376296)
