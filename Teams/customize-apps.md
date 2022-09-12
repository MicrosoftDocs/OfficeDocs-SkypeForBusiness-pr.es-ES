---
title: Usar la personalización de aplicaciones para personalizar las aplicaciones según las necesidades de su organización
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Obtenga información sobre cómo cambiar los metadatos y la apariencia de una aplicación para cambiar su nombre para una mejor adopción en su organización.
ms.openlocfilehash: 0a1ae462933768e0c5a53db6c7379e5cd8b9bf05
ms.sourcegitcommit: 41a75f1ba5ceb09f8db7d468aa41b63a89ab9c30
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2022
ms.locfileid: "67647484"
---
# <a name="use-app-customization-to-update-branding-of-apps-in-your-organizations-teams-store"></a>Usar la personalización de aplicaciones para actualizar la personalización de marca de las aplicaciones en la tienda de Teams de su organización

Los administradores de Microsoft Teams pueden modificar la apariencia de algunas aplicaciones de Teams para proporcionar una experiencia personalizada con personalización de marca a los usuarios finales de su organización. Estas modificaciones pueden mejorar la experiencia de la tienda de Teams para los usuarios finales y ayudar a ajustarse a la personalización de marca de la organización. Por ejemplo, los administradores pueden modificar la descripción y el icono de una aplicación que facilita a sus organizaciones que los usuarios finales identifiquen la aplicación, comprendan su uso y que su uso sea más destacado. Los administradores realizan estos cambios cambiando algunos metadatos o propiedades de una aplicación. Los cambios solo están disponibles en su organización. Esta funcionalidad se denomina personalización de aplicaciones.

Los administradores solo pueden personalizar las aplicaciones si el desarrollador de aplicaciones permite personalizar su aplicación. Aunque Teams ofrece una opción para personalizar algunas propiedades, los desarrolladores de aplicaciones controlan las propiedades que realmente cualquier administrador puede personalizar.

Como administrador, puede personalizar las siguientes propiedades.

* Nombre corto
* Descripción breve
* Descripción completa
* URL de la directiva de privacidad
* URL del sitio web
* Dirección URL de las condiciones de uso
* Icono de aplicación
* Color de contorno del icono
* Resaltar color

Para obtener información detallada sobre cada uno de estos campos de metadatos, consulte el [esquema de manifiesto de Teams](/microsoftteams/platform/resources/schema/manifest-schema) en la documentación del desarrollador de Teams.

> [!NOTE]
> La funcionalidad de personalización de aplicaciones no está disponible para las aplicaciones personalizadas. Los administradores no pueden personalizar ninguna aplicación en entornos de Government Community Cloud High (GCCH) y del Departamento de Defensa (DoD).

## <a name="verify-if-an-app-is-customizable"></a>Comprobar si una aplicación se puede personalizar

No se pueden personalizar todas las aplicaciones. Si un desarrollador de aplicaciones le permite personalizar su aplicación, solo entonces puede usar la funcionalidad de personalización de la aplicación para modificar la apariencia de la aplicación. Para comprobar si la aplicación de tu elección es personalizable o no, sigue estos pasos:

1. Inicie sesión en el Centro de administración de Teams y acceda a **las aplicaciones** > **[de Teams Administrar aplicaciones](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Busca en la aplicación que quieras personalizar con el nombre de la aplicación. Comprueba en la columna **Personalizable** si el desarrollador de la aplicación permite personalizar la aplicación o no. Si la columna no está visible, seleccione Editar columnas :::image type="icon" source="media/settings-icon-16px.svg"::: y active la opción **Personalizable****.**

   :::image type="content" source="media/customizable-apps-in-tac.png" alt-text="La captura de pantalla muestra que la columna personalizable del centro de administración le ayuda a comprobar si una aplicación se puede personalizar o no.":::

Para conocer todas las aplicaciones personalizables de la tienda de Teams, ordene la columna Personalizable.

## <a name="customize-the-details-of-an-app"></a>Personalizar los detalles de una aplicación

Para cambiar el aspecto de una aplicación tal como aparece en la tienda de Teams de su organización, siga estos pasos:

1. Inicie sesión en el Centro de administración de Teams y acceda a **las aplicaciones** > **[de Teams Administrar aplicaciones](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Busca en la aplicación que quieras personalizar con el nombre de la aplicación y asegúrate de que se pueda personalizar.

1. Para abrir la interfaz de usuario y personalizar campos de metadatos individuales, siga uno de estos pasos:

   * Selecciona la fila de una aplicación y luego selecciona **Personalizar** :::image type="icon" source="media/edit-pen-icon.png"::: en la barra de herramientas de la página Administrar aplicaciones.

   * Selecciona el nombre de la aplicación para abrir la página de detalles de la aplicación y, a continuación, selecciona el icono :::image type="icon" source="media/edit-pen-icon.png"::: de edición en **Personalizable**.

   * Seleccione el nombre de la aplicación, haga **clic en Acciones** y seleccione **Personalizar**.

     :::image type="content" source="media/customize-action-menu.png" alt-text="La captura de pantalla muestra una opción para personalizar una aplicación abriendo el menú Acciones y seleccionando Personalizar opción en la página de detalles de la aplicación." lightbox="media/customize-action-menu-expanded.png":::

1. Personalice uno o varios de los campos disponibles. Un desarrollador de aplicaciones puede permitir que solo se personalicen algunos de los campos de metadatos. Consulte [consideraciones y limitaciones de los campos personalizables](#considerations-and-limitations-of-app-customization).

   :::image type="content" source="media/customize-settings.png" alt-text="La captura de pantalla muestra el nombre y la descripción en la interfaz de usuario personalizar.":::

1. Después de personalizar la aplicación, seleccione **Aplicar**. Para comprobar los cambios que has realizado, consulta [los detalles de la vista previa de la aplicación](#preview-app-details). Para deshacer los cambios, consulta [restablecer los detalles de la aplicación a los valores predeterminados](#reset-app-details-to-default-values).

1. Selecciona **Publicar** para publicar la aplicación personalizada y verla enumerada en la página **Administrar aplicaciones** .

<!---
   :::image type="content" source="media/customize-app-colors.png" alt-text="Screenshot showing the icon color options that can be customized.":::
--->

## <a name="preview-app-details"></a>Vista previa de detalles de la aplicación

Para ver los cambios después de guardar la personalización, vea la página de detalles de la aplicación.

1. Inicie sesión en el Centro de administración de Teams y acceda a **las aplicaciones** > **[de Teams Administrar aplicaciones](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Para abrir la página de detalles de la aplicación, selecciona el nombre de la aplicación.

1. Ver los detalles de la aplicación, incluido el nombre original de la aplicación en el campo **Nombre corto del editor**. El campo solo está visible si ha cambiado el nombre corto de la aplicación.

   :::image type="content" source="media/original-app-version.png" alt-text="La captura de pantalla muestra el nombre corto modificado de una aplicación.":::

Los usuarios de Teams pueden ver la aplicación personalizada en la tienda de Teams de su cliente.

   :::image type="content" source="media/contoso-app.png" alt-text="La captura de pantalla muestra una aplicación personalizada en el cliente de Teams.":::

## <a name="considerations-and-limitations-of-app-customization"></a>Consideraciones y limitaciones de la personalización de aplicaciones

Tenga en cuenta los siguientes detalles sobre la funcionalidad de personalización de aplicaciones:

* Solo tendrá una versión de la aplicación, ya que la personalización de las características de la aplicación no crea una copia de la aplicación.

* Al personalizar aplicaciones y cualquier descripción relacionada con una aplicación, asegúrate de seguir las directrices que el desarrollador de aplicaciones proporciona en su documentación o términos de uso. Se adhiere a las leyes de derechos de autor al usar imágenes de terceros.

* Los datos de personalización proporcionados por el administrador se almacenan en la región más cercana.

* Es su responsabilidad asegurarse de que los vínculos a los términos de uso o a la directiva de privacidad sean válidos.

* En caso de que el desarrollador de la aplicación ya no permita que un campo sea personalizable, aparece un mensaje en la página de detalles de la aplicación que notifica al administrador sobre los campos que ya no se pueden personalizar. Todos los cambios realizados en ese campo se revertirán a los valores originales.

* Se recomienda probar los cambios de personalización de aplicaciones en un inquilino de prueba de Teams antes de realizar estos cambios en el entorno de producción. Para obtener un inquilino de prueba, sigue las instrucciones de [Crear tu inquilino de prueba](/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant).

* Los cambios tardan hasta 24 horas en propagarse a todos los usuarios.

* Para que una aplicación se pueda personalizar, los desarrolladores pueden proporcionar una nueva versión de la aplicación. Cargue la nueva versión y quite la versión anterior de la aplicación. Si ha personalizado una aplicación y la ha publicado, la nueva aplicación personalizada con la característica de personalización de la aplicación no reemplazará a la aplicación actual.

* El [informe de uso de la aplicación](teams-analytics-and-reports/app-usage-report.md) muestra el nombre original de la aplicación proporcionada por el publicador.

* El cuadro de diálogo de consentimiento de permisos de Microsoft Graph muestra el nombre original de la aplicación que proporciona el editor. Le ayuda a identificar con precisión una aplicación al mismo tiempo que le proporciona permisos.

A continuación se indican las limitaciones en los campos personalizables:

| Campo personalizable | Consideración |
|:---|:---|
| Cualquier campo de dirección URL | Asegúrate de direcciones URL válidas y seguras con `https`. |
| Descripción breve | La descripción breve debe tener menos de 80 caracteres y no repetir lo que aparece en la descripción completa. |
| Icono | Icono de contorno transparente en formato PNG con resolución de 32 x 32 píxeles. |
| Icono color | Icono de color completo en formato PNG con resolución de 192 x 192 píxeles. |
| Resaltar color | El color debe coincidir con el fondo del icono. |

## <a name="reset-app-details-to-default-values"></a>Restablecer los detalles de la aplicación con los valores predeterminados

Puede restablecer los detalles de la aplicación a los valores originales proporcionados por el desarrollador de la aplicación. La opción solo está disponible para la aplicación que personalice.

1. En el Centro de administración de Teams, acceda a **Aplicaciones de Teams** > **[Administrar aplicaciones](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Para abrir la página de detalles de la aplicación, selecciona el nombre de la aplicación.

1. En el menú **Acciones** , seleccione **Restablecer al valor predeterminado**.

   :::image type="content" source="media/reset-app-customization.png" alt-text="La captura de pantalla muestra la opción restablecer a la predeterminada para una aplicación personalizada.":::

## <a name="related-articles"></a>Artículos relacionados

* [Personalización de la tienda de aplicaciones de su organización](customize-your-app-store.md)
* [Cambiar el nombre de las aplicaciones](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/rebrand-apps-to-your-own-organization-s-branding-with-app/ba-p/2376296)
