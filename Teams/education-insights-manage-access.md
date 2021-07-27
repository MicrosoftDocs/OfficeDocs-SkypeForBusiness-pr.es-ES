---
title: Administrar el acceso de usuarios a Insights para Educación
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Administrar el acceso a Insights para Educación en Microsoft Teams
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7980b062d864b7354a329ce5743b0209d9a54e2a
ms.sourcegitcommit: e3bc5418025780207b05766cd817ef01c014a809
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2021
ms.locfileid: "53565706"
---
# <a name="manage-user-access-to-education-insights"></a>Administrar el acceso de usuarios a Insights para Educación

Este documento proporciona los pasos necesarios para administrar el acceso de usuarios a [Insights para Educación en Microsoft Teams](class-insights.md).

Debe proporcionar permisos para los líderes educativos, líderes de distrito, directores de escuela, profesores en jefe, consejeros, directores de áreas de aprendizaje, directores de programa, trabajadores sociales y psicólogos. A los formadores se les concede permiso *automáticamente* cuando son propietarios de un equipo de clase.

Para emplear Insights a nivel de la organización, es necesario [importar los datos del Sistema de información de estudiantes (SIS)](education-insights-sis-data-sync.md) para que Insights tenga la estructura jerárquica del sistema educativo asignada correctamente.

> [!NOTE]
> Solo el Administrador global puede administrar el acceso de los usuarios a Insights.

> [!TIP]
> Le recomendamos que habilite Insights para todos los líderes educativos. Así, tendrán los datos necesarios para comprender cada centro educativo y podrán identificar rápidamente los problemas y dar soporte técnico a los educadores. Incluso si decide realizar un piloto, podría ser útil mantener Insights habilitado para todos los líderes educativos, mientras centra las comunicaciones en el grupo piloto de usuarios.



## <a name="manange-permissions"></a>Administrar permisos

* Abra la aplicación Insights, haga clic en **Configuración** y, después, seleccione **Permisos de usuario**

:::image type="content" source="media/insights-user-permissions.png" alt-text="Configuración":::

> [!NOTE]
> Cuando se proporcionan permisos para un nivel organizativo, el usuario puede ver todas las unidades organizativas debajo de él. Solo proporcione permisos a los líderes educativos que los necesiten.
> 
> Proporcione solo permisos a los líderes educativos que los necesiten y solo para las unidades organizativas de las que sean responsables. Si no está seguro de si se requiere un permiso de usuario para una organización específica, consulte a los expertos en temas de privacidad de su institución, como personal de recursos humanos o jurídicos.

## <a name="role-based-permissions"></a>Permisos basados en roles

Si usa el [formato de archivo SDS V2.1](/schooldatasync/sds-v2.1-csv-file-format) o [formato de archivo SDS V2](/schooldatasync/sds-v2-csv-file-format), puede importar todos los roles y la jerarquía completa de las escuelas dentro del sistema educativo. Esta asignación completa le permite asignar permisos a roles. 

> [!NOTE]
> Cuando se asigna un rol a un usuario, recibe automáticamente los permisos correctos para ver los datos relevantes para él.

* Si es necesario, haga clic en la pestaña **Permisos basados en roles**.

  Verá una lista de los roles de la organización educativa, el nivel de esa jerarquía para cada uno, cuántos usuarios tienen asignado ese rol y el nivel de permisos del rol. 
  
  :::image type="content" source="media/insights-role-based-permissions.png" alt-text="Permisos basados en roles":::
  
  Si hay un rol en más de un nivel de organización, ese rol aparece varias veces, una vez para cada nivel. En la captura de pantalla, tenemos directores en el nivel de la escuela y en el de distrito, por lo que hay dos líneas para "director".
  
* Para cada rol, haga clic en el icono de lápiz para seleccionar el nivel de permisos. El valor predeterminado es que el rol no tiene permiso para ver Conclusiones.
* Seleccione el nivel de permisos: **Ver datos de la organización** o **Ninguno**.
* Haga clic en **Guardar cambios**.

  Este nivel de permisos ahora se asigna automáticamente a cualquier usuario nuevo con este rol y nivel de organización. El usuario verá los datos de todas las unidades organizativas en su nivel de la jerarquía y debajo de ella.
  
  Si ve un usuario en la lista que necesita un nivel de permisos más matizado, ajústelo en Permisos individuales.
  
  Si un usuario ya no está en un rol, su permiso para ese rol se revoca automáticamente (aunque puede seguir teniendo permisos individuales).


## <a name="individual-permissions"></a>Permisos individuales

Use permisos individuales para ajustar el permiso de un usuario o para asignar permisos para cada usuario si no ha usado SDS V2 para importar datos de SIS para la organización.

* Haga clic en la pestaña **Permisos individuales**.
  
  Verá que los usuarios de la organización educativa han concedido un permiso individual. 
  
  :::image type="content" source="media/insights-individual-permissions.png" alt-text="Permisos individuales":::
  
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
* Haga clic en **Guardar cambios** para guardar.
