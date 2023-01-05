---
title: Administrar el acceso de usuarios a Insights para Educación
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Administrar el acceso a Insights para Educación en Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7203c9bda1a6e5c2bf9d90b490492fe7bbc3f64c
ms.sourcegitcommit: 78fbfcf4a1aafce5d39eea79c9461a9fc1bb3d38
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/05/2023
ms.locfileid: "69707812"
---
# <a name="manage-user-access-to-education-insights"></a>Administrar el acceso de usuarios a Insights para Educación

Este documento proporciona los pasos necesarios para administrar el acceso de usuarios a [Insights para Educación en Microsoft Teams](class-insights.md).

You need to provide permissions for education leaders, district leaders, school principals, head teachers, counselors, heads of learning areas, program directors, social workers, and psychologists. Educators are *automatically* given permission when they own a class team.

Para emplear Insights a nivel de la organización, es necesario [importar los datos del Sistema de información de estudiantes (SIS)](education-insights-sis-data-sync.md) para que Insights tenga la estructura jerárquica del sistema educativo asignada correctamente.

> [!NOTE]
> Solo el Administrador global puede administrar el acceso de los usuarios a Insights.

> [!TIP]
> Le recomendamos que habilite Insights para todos los líderes educativos. Así, tendrán los datos necesarios para comprender cada centro educativo y podrán identificar rápidamente los problemas y dar soporte técnico a los educadores. Incluso si decide realizar un piloto, podría ser útil mantener Insights habilitado para todos los líderes educativos, mientras centra las comunicaciones en el grupo piloto de usuarios.

## <a name="manage-permissions"></a>Administrar permisos

* Abra la aplicación Insights, haga clic en **Configuración** y, después, seleccione **Permisos de usuario**

:::image type="content" source="media/insights-user-permissions.png" alt-text="Configuración.":::

> [!NOTE]
> Cuando se proporcionan permisos para un nivel organizativo, el usuario puede ver todas las unidades organizativas debajo de él.
> 
> Proporcione solo permisos a los líderes educativos que los necesiten y solo para las unidades organizativas de las que sean responsables. Si no está seguro de si se requiere un permiso de usuario para una organización específica, consulte a los expertos en temas de privacidad de su institución, como personal de recursos humanos o jurídicos.

> [!IMPORTANT]
> Después de asignar permisos por primera vez, los usuarios podrán ver los datos dentro de la aplicación solo si al menos **dos** usuarios han tenido acceso a la aplicación. Este requisito ayuda a garantizar que la zona horaria de los datos esté configurada correctamente y que los datos se muestren con precisión para todos los usuarios. Si los usuarios experimentan problemas de acceso a los datos después de conceder permisos, compruebe si al menos dos usuarios han tenido acceso a la aplicación.

## <a name="role-based-permissions"></a>Permisos basados en roles

If you use [SDS V2.1 file format](/schooldatasync/sds-v2.1-csv-file-format) or [SDS V2 file format](/schooldatasync/sds-v2-csv-file-format), you can import all roles and the full hierarchy of schools within the education system. This complete mapping enables you to assign permissions to roles. 

> [!NOTE]
> Cuando se asigna un rol a un usuario, recibe automáticamente los permisos correctos para ver los datos relevantes para él.
>
> Si un usuario ya no está en un rol, su permiso para ese rol se revoca automáticamente (aunque puede seguir teniendo permisos individuales).

* Si es necesario, haga clic en la pestaña **Permisos basados en roles**.

  Verá una lista de los roles de la organización educativa, el nivel de esa jerarquía para cada uno, cuántos usuarios tienen asignado ese rol y el nivel de permisos del rol. 
  
  :::image type="content" source="media/insights-role-based-permissions.png" alt-text="Permisos basados en roles.":::
  
  Si hay un rol en más de un nivel de organización, ese rol aparece varias veces, una vez para cada nivel. En la captura de pantalla, tenemos directores de escuela, a nivel de distrito y departamento, por lo que hay tres líneas para "director".
  
* Para cada rol, haga clic en el icono de lápiz para seleccionar el nivel de permisos. El valor predeterminado es que el rol no tiene permiso para ver Conclusiones.
* Seleccione el nivel de permisos: **Ver datos de la organización** o **Ninguno**.

  :::image type="content" source="media/insights-role-based-permissions-panel.png" alt-text="Panel de permisos basados en roles":::
  
  Si ve un usuario en la lista que necesita un nivel de permisos más específico, ajuste su rol u organización en los [datos importados de SIS](education-insights-sis-data-sync.md) y [concédales permisos individuales](#grant-individual-permission-to-a-user) (si es necesario).

* Haga clic en **Guardar cambios**.

  Este nivel de permisos ahora se asigna automáticamente a cualquier usuario nuevo con este rol y nivel de organización. El usuario verá los datos de todas las unidades organizativas en su nivel de la jerarquía y debajo de ella.  


## <a name="individual-permissions"></a>Permisos individuales

Use permisos individuales para ajustar el permiso de un usuario o para asignar permisos para cada usuario si no ha usado SDS V2 para importar datos de SIS para la organización.

* Haga clic en la pestaña **Permisos individuales**.
  
  Verá que los usuarios de la organización educativa han concedido un permiso individual. 
  
  :::image type="content" source="media/insights-individual-permissions.png" alt-text="Permisos individuales.":::
  
### <a name="grant-individual-permission-to-a-user"></a>Conceder permisos individuales a un usuario
* Haga clic en **Conceder permisos individuales** en la parte superior izquierda de la pantalla.
* Escriba el nombre de usuario o la dirección de correo electrónico de cada usuario.
* Seleccione el nivel de permisos:
  * **Todo** significa que el usuario ve todas las unidades de la organización en todos los niveles. Esto rara vez se usa.
  * **Organización específica** significa que el usuario ve la unidad organizativa seleccionada y todas las unidades organizativas debajo de ella. Comience a escribir y seleccione la unidad organizativa de la lista.
* Haga clic en **Conceder permisos** para guardar.

### <a name="change-the-individual-permission-of-a-user"></a>Cambiar el permiso individual de un usuario
* Para el usuario correspondiente, haga clic en el icono de lápiz para seleccionar el nivel de permisos individual.
* Seleccione el nivel de permisos:
  * **Todo** significa que el usuario ve todas las unidades de la organización en todos los niveles. Esto rara vez se usa.
  * **Organización específica** significa que el usuario ve la unidad organizativa seleccionada y todas las unidades organizativas debajo de ella. Comience a escribir y seleccione la unidad organizativa de la lista.
  * **Ninguna** significa que el usuario solo ve las unidades organizativas asignadas automáticamente por su rol (si las hay).
  
  :::image type="content" source="media/insights-individual-permissions-panel.png" alt-text="Panel de permisos individuales.":::

* Haga clic en **Guardar cambios** para guardar.
