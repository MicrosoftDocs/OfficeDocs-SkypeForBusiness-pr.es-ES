---
title: Personalizar aplicaciones en Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
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
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo personalizar aplicaciones en Microsoft Teams.
ms.openlocfilehash: bd598bed231c0d9d6ab2a58d87f04ab2eecfad8df64d0446ee3c63a884b25e67
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54281633"
---
# <a name="customize-apps-in-microsoft-teams"></a>Personalizar aplicaciones en Microsoft Teams

 Microsoft Teams personalización de aplicaciones para mejorar Teams experiencia. Algunos desarrolladores de aplicaciones permiten que el administrador de aplicaciones personalizó una aplicación Teams aplicación. El administrador puede personalizar o cambiar el nombre de las propiedades de la aplicación en función de las necesidades de la **organización** mediante la página Administrar aplicaciones Teams centro de administración. Los detalles que puede personalizar son:

- Nombre corto
- Descripción breve
- Descripción completa
- Dirección URL de la directiva de privacidad
- Url del sitio web
- Url de términos de uso
- Icono de color
- Icono Esquema
- Color de énfeño

Vea el [Teams de manifiesto para](/microsoftteams/platform/resources/schema/manifest-schema) obtener más información sobre los campos que puede personalizar.

> [!NOTE]
> La personalización de aplicaciones no es compatible con Government Community Cloud High (GCCH) o department of defense (DoD) en este momento.
> Actualmente, esta característica no está disponible para las aplicaciones Microsoft Teams carga lateral.

## <a name="customize-the-apps-details"></a>Personalizar los detalles de la aplicación

Para empezar a personalizar una aplicación, siga estos pasos:

1. Inicie la sesión en el Centro de administración de Teams
2. Expanda **Teams aplicaciones y** seleccione Administrar **aplicaciones.**
3. Compruebe la **columna Personalizable** de la lista de aplicaciones y ordene por aplicaciones que se pueden personalizar.

   ![La columna personalizar que está ordenada](media/customize-column.png)

   Hay tres puntos de entrada para acceder a la característica de personalización:

   - Seleccione junto a la aplicación que desea personalizar y, a continuación, seleccione **Personalizar**.

     ![La opción de selección personalizar 1](media/select-app-to-customize1.png)

   - Seleccione el nombre de la aplicación y, a continuación, **Personalizable.**

     ![La opción de selección personalizar 2](media/app-details-customizable.png)

   - Seleccione el nombre de la aplicación y, a continuación, **seleccione Personalizar en** el **menú** desplegable Acciones.

     ![La opción de selección personalizar 3](media/customize-action-menu.png)

4. Expanda la **sección Detalles** y personalice los campos siguientes:

    - Nombre corto
    - Descripción breve
    - Descripción completa
    - Sitio web
    - Dirección URL de la directiva de privacidad
    - Url de términos de uso

   ![La configuración de personalización](media/customize-settings.png)

> [!Note]
> Solo estarán visibles los campos que el desarrollador de aplicaciones haya asignado como personalizables.

5. Expanda la **sección Icono.**

   a. Upload un icono. Use un icono de color completo (192x192) píxel en formato PNG.

   b. Elija un color de contorno de icono. Use un píxel de contorno transparente (32x32) en formato PNG.

   c. Seleccione un color de acento de aplicación que coincida con el icono.

    ![Personalizar las opciones de color del panel de iconos](media/customize-app-colors.png)

6. Una vez que la aplicación se haya personalizado, seleccione **Aplicar**.

7. Seleccione **Publicar** para publicar la aplicación personalizada.

   La aplicación personalizada ahora aparece en la **página Administrar aplicaciones.** Solo tendrá una versión de la aplicación, ya que personalizar las características de la aplicación no crea una copia de la aplicación.

Ahora, Teams usuarios finales pueden abrir su Teams cliente para ver la aplicación personalizada.

   ![Aplicación personalizada en Teams cliente](media/contoso-app.png)

### <a name="special-considerations-for-customizing-an-app"></a>Consideraciones especiales para personalizar una aplicación

La siguiente nota incluye detalles importantes sobre cómo personalizar una aplicación.

> [!Note]
> - Cuando personalice las aplicaciones y cualquier descripción relacionada con una aplicación, asegúrese de que sigue las directrices de personalización si lo proporciona el editor de aplicaciones en su documentación o términos de uso. También es responsable de respetar los derechos de otras personas con respecto a las imágenes de terceros que pueda usar.
> - Los datos de personalización proporcionados por el administrador se almacenan en la región más cercana.
> - Usted es responsable de garantizar que los vínculos a términos de uso o a la política de privacidad sean válidos.
> - En caso de que el editor de aplicaciones ya no permita que se pueda personalizar un campo, aparecerá un mensaje en la página de detalles de la aplicación en el que se notificará al administrador sobre los campos que ya no se pueden personalizar. Todos los cambios realizados en ese campo se revertirán a los valores originales.
> - Se recomienda probar los cambios de personalización de aplicaciones Teams inquilino de prueba antes de realizar estos cambios en el entorno de producción.
> - Los cambios en la personal de marca pueden requerir hasta 24 horas para que los usuarios vean los cambios.

## <a name="review-app-details"></a>Revisar detalles de la aplicación

Es posible que quiera ver los detalles de la aplicación para revisar la información.

1. Inicie la sesión en el Centro de administración de Teams

2. Expanda **aplicación de Teams** y seleccione **Administrar aplicaciones**.

3. Seleccione el nombre de la aplicación.

4. Ver los detalles de la aplicación, incluido el nombre original de la aplicación **Nombre corto del editor.**

   ![Personalizar el nombre de la aplicación del panel de iconos](media/original-app-version.png)

   El **campo Nombre corto del editor** solo está visible si ha cambiado el nombre corto de la aplicación.

## <a name="reset-app-details-to-default"></a>Restablecer los detalles de la aplicación de forma predeterminada

En cualquier momento, puede restablecer los detalles de la aplicación a la configuración original.

1. Inicie la sesión en el Centro de administración de Teams

2. Expanda **Teams aplicaciones y** seleccione Administrar **aplicaciones.**

3. Seleccione el nombre de la aplicación.

4. Seleccione **Restablecer de forma predeterminada** en el menú **desplegable** Acciones.

   ![Seleccionar restablecer como resaltado predeterminado](media/select-reset.png)

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

**¿Cuánto tiempo tardarán mis usuarios en ver la aplicación personalizada?**

Aunque el administrador puede ver inmediatamente los cambios en el Centro de administración de Teams, los usuarios finales pueden tardar hasta 24 horas en ver los cambios.  

**¿Puede el proveedor de aplicaciones personalizar la aplicación para sus clientes?**

 No, el administrador de un inquilino debe personalizar la aplicación para su inquilino mediante el Centro de Teams de administración.

**¿Se implementará automáticamente la aplicación personalizada para reemplazar mi aplicación personalizada actual en un espacio empresarial?**

No, los administradores de inquilinos tendrán que quitar manualmente cualquier aplicación personalizada y publicar la versión personalizada de la aplicación. Si ha personalizado una aplicación y la ha publicado como una aplicación personalizada, la nueva aplicación personalizada con la característica de personalización de la aplicación no reemplazará a la aplicación personalizada actual.  

**¿El informe de uso de la aplicación también mostrará los valores personalizados, como el nombre corto personalizado?**

 No, el informe de uso de la aplicación seguirá mostrándo el nombre original de la aplicación enviada desde el editor.

**¿Qué aplicaciones puedo personalizar con la característica de personalización de aplicaciones?**

Solo puede personalizar las aplicaciones que el editor de aplicaciones ha permitido personalizar. El editor de aplicaciones tendrá que participar para permitir a sus clientes personalizar la aplicación.

**¿Aparecerán las propiedades personalizadas en la pantalla de consentimiento de permisos de gráfico?**

No, la pantalla de consentimiento de permisos seguirá mostrándo el valor original enviado por el editor.

## <a name="related-article"></a>Artículo relacionado

- [Administrar aplicaciones](manage-apps.md)
- [Personalizar la tienda de aplicaciones](customize-your-app-store.md)
- [Cambiar el nombre de las aplicaciones](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/rebrand-apps-to-your-own-organization-s-branding-with-app/ba-p/2376296)
