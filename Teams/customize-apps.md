---
title: Modificar la apariencia de las aplicaciones en la tienda de Teams de su organización
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.reviewer: v-tbasra
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Obtenga información sobre cómo cambiar la apariencia de la aplicación y cambiar el nombre de una aplicación editando los detalles y los metadatos de la aplicación.
ms.openlocfilehash: 62924c6b3ffb4561427d921a4edc26d4888b4d6b
ms.sourcegitcommit: 9946c6c1faa78617ccd7bdf115457090ebce5619
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/21/2022
ms.locfileid: "66190350"
---
# <a name="customize-appearance-of-apps-in-your-organizations-teams-store"></a>Personalizar la apariencia de las aplicaciones en la tienda Teams de su organización

Microsoft Teams permite a los administradores personalizar Teams aplicación para mejorar la experiencia de store y ajustarse a la personalización de marca de su organización. Un desarrollador de aplicaciones puede permitir que un administrador de Teams personalice su aplicación. A continuación, puede actualizar las propiedades de la aplicación en función de las necesidades de la organización, en la página Administrar aplicaciones en Teams centro de administración. Los detalles que puede personalizar son:

* Nombre corto
* Descripción breve
* Descripción completa
* DIRECCIÓN URL de la directiva de privacidad
* Dirección URL del sitio web
* DIRECCIÓN URL de los términos de uso
* Icono de la aplicación
* Color de contorno del icono
* Color de énfasis

Para obtener información sobre los diversos campos de metadatos de la aplicación, consulte el [esquema de manifiesto de Teams](/microsoftteams/platform/resources/schema/manifest-schema) en la documentación del desarrollador.

> [!NOTE]
> No puedes personalizar las aplicaciones de instalación de prueba en ninguna organización. No puedes personalizar ninguna aplicación en nubes de Government Community Cloud High (GCCH) ni del Departamento de Defensa (DoD).

## <a name="customize-details-of-an-app"></a>Personalizar detalles de una aplicación

Para personalizar una aplicación, siga estos pasos:

1. Inicie la sesión en el Centro de administración de Teams

1. Expande **Teams aplicaciones** y selecciona **[Administrar aplicaciones](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Comprueba la columna **Personalizable** de la lista de aplicaciones y ordena por aplicaciones que se puedan personalizar.

   ![La columna personalizar del centro de administración le ayuda a ver las aplicaciones que se pueden personalizar.](media/customizable-apps-in-tac.png)

   Hay tres puntos de entrada para acceder a la característica de personalización:

   * Selecciona junto a la aplicación que quieras personalizar y, a continuación, **selecciona Personalizar**.

     ![Opción 1 de personalización de selección.](media/select-app-to-customize1.png)

   * Seleccione el nombre de la aplicación y, a continuación, seleccione el icono de edición en **Personalizable**.

     ![Opción 2 de personalización de selección.](media/communities-microsoft.png)

   * Selecciona el nombre de la aplicación, haz clic en el **menú de desbordamiento** del mouse en **Acciones** y selecciona Personalizar.

     ![Opción 3 de personalización de selección.](media/customize-action-menu.png)

1. Expanda la sección **Detalles** y personalice uno o varios de los siguientes campos. Los campos asignados como personalizables por el desarrollador son visibles.

    * Nombre corto
    * Descripción breve
    * Descripción completa
    * Sitio web
    * DIRECCIÓN URL de la directiva de privacidad
    * DIRECCIÓN URL de los términos de uso

   ![La configuración de personalización.](media/customize-settings.png)

1. Expanda la sección **Icono** .

1. Upload un icono. Use un icono (192 x 192) píxel en formato PNG.

1. Elija un color de contorno de icono. Use un contorno transparente (32x32) píxel en formato PNG.

1. Selecciona un color de énfasis de la aplicación que coincida con el icono.

   ![Personalice las opciones de color del panel de iconos.](media/customize-app-colors.png)

1. Después de personalizar la aplicación, selecciona **Aplicar**.

1. Seleccione **Publicar** para publicar la aplicación personalizada.

   La aplicación personalizada aparece ahora en la página **Administrar aplicaciones** . Solo tendrá una versión de la aplicación, ya que la personalización de las características de la aplicación no crea una copia de la aplicación.

Ahora sus Teams usuarios finales pueden ver la aplicación personalizada en su cliente.

   ![Aplicación personalizada en Teams cliente.](media/contoso-app.png)

Tenga en cuenta los siguientes detalles sobre cómo personalizar una aplicación:

* Al personalizar aplicaciones y cualquier descripción relacionada con una aplicación, asegúrese de seguir las instrucciones de personalización, si las proporciona el editor de la aplicación, en su documentación o términos de uso. También es responsable de respetar los derechos de otras personas con respecto a las imágenes de terceros que pueda usar.

* Administración datos de personalización proporcionados se almacenan en la región más cercana.

* Usted es responsable de asegurarse de que los vínculos a los términos de uso o a la directiva de privacidad sean válidos.

* En caso de que el editor de la aplicación ya no permita que un campo se pueda personalizar, aparecerá un mensaje en la página de detalles de la aplicación que notifica al administrador sobre los campos que ya no se pueden personalizar. Todos los cambios realizados en ese campo se revertirán a los valores originales.

* Se recomienda probar los cambios de personalización de la aplicación en un espacio empresarial de prueba Teams antes de realizar estos cambios en el entorno de producción.

* Los cambios en la personalización de marca pueden requerir hasta 24 horas para propagarse a todos los usuarios.

* Para que una aplicación se pueda personalizar, los desarrolladores pueden proporcionar una nueva versión de la aplicación. Cargue la nueva versión y quite la versión anterior de la aplicación. Si ha personalizado una aplicación y la ha publicado, la nueva aplicación personalizada con la característica de personalización de la aplicación no reemplazará a la aplicación actual.

* El [informe de uso de](teams-analytics-and-reports/app-usage-report.md) aplicaciones muestra el nombre original de la aplicación que proporciona el editor.

* El cuadro de diálogo consentimiento de Microsoft Graph permiso muestra el nombre original de la aplicación que proporciona el editor. Le ayuda a identificar con precisión una aplicación a la vez que le proporciona permisos.

## <a name="review-app-details"></a>Revisar detalles de la aplicación

Es posible que quiera ver los detalles de la aplicación para revisar la información.

1. Inicie la sesión en el Centro de administración de Teams

1. Expande **Teams aplicaciones** y selecciona **[Administrar aplicaciones](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Selecciona el nombre de la aplicación.

1. Ver los detalles de la aplicación, incluido el nombre de la aplicación original **Nombre corto del editor**.

   ![Personalizar el nombre de la aplicación del panel de iconos.](media/original-app-version.png)

   El campo **Nombre corto del editor** solo está visible si ha cambiado el nombre corto de la aplicación.

## <a name="reset-app-details-to-default-values"></a>Restablecer los detalles de la aplicación a valores predeterminados

Puede restablecer los detalles de la aplicación a los valores originales proporcionados por el desarrollador de la aplicación. La opción solo está disponible para las aplicaciones que personalice.

1. En Teams centro de administración, acceda **a Teams Aplicaciones** > **[administrar aplicaciones](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Selecciona el nombre de la aplicación.

1. Seleccione **Restablecer como predeterminado** en el menú **Acciones** .

   ![Seleccione Restablecer al valor predeterminado resaltado.](media/select-reset.png)

## <a name="related-article"></a>Artículo relacionado

* [Administrar aplicaciones](manage-apps.md)
* [Personalizar la tienda de aplicaciones de su organización](customize-your-app-store.md)
* [Cambiar el nombre de las aplicaciones](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/rebrand-apps-to-your-own-organization-s-branding-with-app/ba-p/2376296)
