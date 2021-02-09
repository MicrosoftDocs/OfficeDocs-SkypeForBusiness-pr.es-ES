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
ms.openlocfilehash: 32bd773975ff6b67d28ab765ffa7c932e978af7d
ms.sourcegitcommit: 27bfa015413bc7742bca4ea227e0324da0c740d7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145944"
---
# <a name="manage-user-access-to-education-insights"></a>Administrar el acceso de usuarios a Insights para Educación

Este documento proporciona los pasos necesarios para administrar el acceso de usuarios a [Insights para Educación en Microsoft Teams](class-insights.md).

Debe proporcionar permisos para los líderes educativos, líderes de distrito, directores de escuela, profesores en jefe, consejeros, directores de áreas de aprendizaje, directores de programa, trabajadores sociales y psicólogos. A los formadores se les concede permiso *automáticamente* cuando son propietarios de un equipo de clase.

Para emplear Insights a nivel de la organización, es necesario [importar los datos del Sistema de información de estudiantes (SIS)](education-insights-sis-data-sync.md) para que Insights tenga la estructura jerárquica del sistema educativo asignada correctamente.

> [!NOTE]
> Solo el Administrador global puede administrar el acceso de los usuarios a Insights.

> [!TIP]
> Le recomendamos que habilite Insights para todos los líderes educativos. Así, tendrán los datos necesarios para comprender cada centro educativo y podrán identificar rápidamente los problemas y dar soporte técnico a los educadores. Incluso si decide realizar un piloto, podría ser útil mantener Insights habilitado para todos los líderes educativos, mientras centra las comunicaciones en el grupo piloto de usuarios.



## <a name="grant-permissions"></a>Conceder permisos

* Abra la aplicación Insights, haga clic en **Configuración** y, después, seleccione **Permisos de usuario**

:::image type="content" source="media/insights-user-permissions.png" alt-text="Configuración":::

* Seleccione **Agregar usuarios**.
* Escriba el nombre de usuario o la dirección de correo electrónico de cada usuario.
* Seleccione el nivel de permisos:
  * **El acceso a todas las organizaciones** significa que el usuario ve todas las unidades de la organización en todos los niveles.
  * **El acceso a escuelas específicas** quiere decir que el usuario ve las escuelas seleccionadas. Comience a escribir y seleccione la escuela de la lista. Puede agregar varias escuelas conjuntamente.
* Haga clic en **Agregar nuevos usuarios**.

:::image type="content" source="media/insights-add-users.png" alt-text="Conceder permisos":::

> [!NOTE]
> Proporcione solo permisos a los líderes educativos que los necesiten y solo para las unidades organizativas de las que sean responsables. Si no está seguro de si se requiere un permiso de usuario para una organización específica, consulte a los expertos en temas de privacidad de su institución, como personal de recursos humanos o jurídicos.

## <a name="edit-permissions"></a>Editar permisos
* Seleccione un usuario específico y, después, **Editar permisos**.
* Actualice el nivel de permisos o la lista de escuelas y haga clic en **Actualizar permisos**.

:::image type="content" source="media/insights-edit-users.png" alt-text="Editar permisos":::

## <a name="remove-permissions"></a>Eliminar permisos
* Seleccione los usuarios que quiera quitar y, después, haga clic en **Quitar usuarios**.
* Estos usuarios ya no tienen acceso a Insights a nivel de organización, pero pueden seguir accediendo a Insights a nivel de clase si son propietarios de un equipo de clase.

:::image type="content" source="media/insights-remove-users.png" alt-text="Quitar permisos":::
