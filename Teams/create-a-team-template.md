---
title: Crear una plantilla de equipo personalizada en Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aaglick
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo crear una plantilla de equipo personalizada en Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a596f2755434e7074c4a925f5c7c1dd8b1efbcaf
ms.sourcegitcommit: fdada65628b31e4c267c87f0100e9f046b878c12
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2021
ms.locfileid: "50831030"
---
# <a name="create-a-custom-team-template-in-microsoft-teams"></a>Crear una plantilla de equipo personalizada en Microsoft Teams

**Las plantillas personalizadas aún no son compatibles con los clientes de EDU.**

Una plantilla de equipo personalizada es una estructura de equipo predefinida con un conjunto de canales, pestañas y aplicaciones. Puede desarrollar una plantilla que le ayude a crear rápidamente el espacio de colaboración adecuado. La plantilla de equipo personalizada usa la configuración que prefiera.  

Para empezar:

1. Inicie la sesión en el Centro de administración de Teams

2. En el panel de navegación izquierdo, expanda **Plantillas de equipo** de  >  **Teams.**

3. Seleccione **Agregar**.

    ![Imagen del cuadro de diálogo Plantillas de equipo con Agregar resaltado.](media/team-templates-new.png)

4. En la **sección Plantillas de** equipo, seleccione Crear una plantilla **nueva.**

5. En la **sección Configuración de** plantilla, complete los siguientes campos y, a continuación, seleccione **Siguiente:**
    - Nombre de plantilla
    - Descripciones cortas y largas de la plantilla
    - Visibilidad de configuración regional  

    ![Imagen del cuadro de diálogo de nomenclatura De configuración de plantillas de equipo.](media/template-add-a-name.png)

6. En la **sección canales, pestañas** y aplicaciones, agregue los canales y aplicaciones que necesite su equipo.

    1. En la **sección Canales,** seleccione **Agregar**.
    2. En el **cuadro de** diálogo Agregar, asigne un nombre al canal.
    3. Agregue una descripción.
    4. Decida si el canal debe mostrarse de forma predeterminada.
    5. Busque el nombre de la aplicación que quiera agregar al canal.
    6. Seleccione **Aplicar** cuando haya terminado.

    ![Una imagen de la pantalla de canales, pestañas y aplicaciones de plantillas de equipo.](media/template-channels-tabs-apps.png)

8. Seleccione **Enviar** cuando haya finalizado.

La nueva plantilla se muestra en la lista **Plantillas de** equipo. La plantilla se puede usar para crear un equipo en Teams.

> [!Note]
> Los usuarios de equipos pueden tardar hasta 24 horas en ver una plantilla personalizada en la galería.

## <a name="customizing-website-tab-apps"></a>Personalizar aplicaciones de pestaña Sitio web

> [!Note]
> Esta característica está en versión preliminar

Es posible que desee especificar direcciones URL para pestañas de sitio web para canales en plantillas de equipo personalizadas. Los usuarios finales que creen equipos con plantillas tendrán pestañas de sitio web predefinidas en la dirección URL del sitio especificada.

Para empezar:

1. Cree una nueva plantilla de equipo o edite una plantilla de equipo existente.

2. En la sección Canales, agregue un nuevo canal o seleccione un canal existente y seleccione **Editar.**

3. En la **sección Agregar una aplicación para esta plantilla,** agregue una aplicación sitio web.

    ![agregar una aplicación para esta opción de plantilla](media/add-an-app-template.png)

4. Seleccione el icono de edición e introduzca la dirección URL que prefiera.

    ![agregar una dirección URL de la aplicación](media/add-url-app-template.png)

5. Seleccione **Guardar** para las modificaciones de la aplicación de pestaña y, a continuación, **seleccione Aplicar** para guardar los cambios.

## <a name="known-issues"></a>Problemas conocidos

**Problema:** Si ha creado un equipo a partir de una plantilla personalizada que contenía pestañas personalizadas adicionales, es posible que vea pestañas en blanco en lugar de las aplicaciones de pestaña personalizadas. Las pestañas predeterminadas (como **Publicaciones,** **Archivos** y **Wiki)** aparecerán según lo esperado.

**Solución:** Si ha creado un equipo a partir de una plantilla personalizada que contenía pestañas personalizadas adicionales, es posible que vea pestañas en blanco en lugar de las aplicaciones de pestaña personalizadas. Las pestañas predeterminadas (como Publicaciones, Archivos y Wiki) aparecerán según lo esperado.

Para solucionar este problema, quite la pestaña personalizada y agregue una nueva pestaña con la misma aplicación. Si no tiene permisos para quitar la pestaña personalizada y agregar una nueva pestaña, póngase en contacto con el propietario del equipo para obtener ayuda.

Actualmente estamos trabajando en una corrección para futuros equipos creados a partir de plantillas personalizadas.

## <a name="related-topics"></a>Temas relacionados

- [Introducción a las plantillas de equipo en el Centro de administración](get-started-with-teams-templates-in-the-admin-console.md)
- [Crear una plantilla a partir de un equipo existente](create-template-from-existing-team.md)
- [Crear una plantilla de equipo a partir de una plantilla de equipo existente](create-template-from-existing-template.md)
