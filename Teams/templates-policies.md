---
title: Administrar plantillas de equipo en el Centro de administración
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: yinchang
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
description: Obtenga información sobre cómo administrar plantillas de equipo en el Centro de administración
ms.openlocfilehash: a8fa2833f00c1d943bfa1b935492a80bd98444d1780eff1382b0952781aa471e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54310409"
---
# <a name="manage-team-templates-in-the-admin-center"></a>Administrar plantillas de equipo en el Centro de administración

Administre las plantillas de equipo que ven los usuarios finales creando directivas de plantillas en el Centro de administración. Dentro de cada directiva de plantilla, puede designar qué plantillas se muestran u ocultan.
Asigne diferentes usuarios a distintas directivas de plantilla para que los usuarios solo puedan ver el subconjunto de plantillas de equipo especificadas.

Vea este breve vídeo para obtener información sobre cómo administrar directivas de plantilla.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyXL9]

## <a name="create-template-policies-and-assign-available-templates"></a>Crear directivas de plantilla y asignar plantillas disponibles

1. Inicie la sesión en el Centro de administración de Teams

2. Expanda **Teams**  >  **de plantillas**.

3. Seleccione **Agregar**.

    ![Las directivas de plantilla están seleccionadas y Agregar está resaltada](media/template-policies-1.png)

1. En la **sección Directivas Configuración** plantillas, complete los siguientes campos:

    - Nombre de la directiva de plantillas

    - Descripción breve de la directiva de plantillas

2. En la **tabla Plantillas visualizables,** seleccione las plantillas que desea ocultar y seleccione **Ocultar.**

    ![Las plantillas seleccionadas con ocultar resaltadas](media/template-policies-2.png)

    Puede ver las plantillas que ha seleccionado para ocultar en la **tabla Plantillas ocultas.**

1. Para mostrar determinadas plantillas, desplácese hasta la **tabla Plantillas ocultas.**

2. Seleccione las plantillas que desea mostrar y, a continuación, **seleccione Mostrar.**

   ![Las plantillas seleccionadas que no están ocultas](media/template-policies-3.png)

   Las plantillas seleccionadas aparecerán en la **tabla Plantillas visualizables.**
3. Seleccione **Guardar**.

   La nueva directiva de plantilla se muestra en la **lista Directivas de** plantillas.

## <a name="assign-users-to-the-template-policies"></a>Asignar usuarios a las directivas de plantilla

Los usuarios asignados a una directiva solo podrán ver las plantillas que se pueden ver dentro de esa directiva.

1. En **Directivas de plantillas,** seleccione una directiva y, a continuación, **seleccione Administrar usuarios.**

2. Escriba los usuarios que desea asignar a esta directiva.

   ![asignar usuarios a una directiva de plantilla](media/template-policies-4.png)

3. Seleccione **Aplicar**.

> [!Note]
> La nueva directiva puede tardar hasta 24 horas en tener efecto para los usuarios finales.

## <a name="size-limits-for-template-policies"></a>Límites de tamaño para directivas de plantilla

Puede ocultar un máximo de 100 plantillas por directiva. El **botón** Ocultar está deshabilitado si la directiva dada ya tiene 100 plantillas ocultas.

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

**P: ¿Puedo asignar usuarios por lotes a directivas de plantillas de equipo?**
  
A: Sí, se admite la asignación por lotes para la directiva de plantilla en PowerShell. El tipo de directiva para esta acción es TeamsTemplatePermissionPolicy. [Aprende más](/powershell/module/teams/new-csbatchpolicyassignmentoperation)

**P: ¿Se pueden asignar grupos a directivas de plantillas de equipo?**

A: Actualmente no. Esta funcionalidad estará disponible en el futuro.

**P: Si se crea una plantilla nueva, ¿se incluirá la plantilla en mis directivas?**

A: Las plantillas nuevas estarán visibles de forma predeterminada. Puede elegir ocultar la plantilla en el Centro de administración en la sección Directivas de plantillas.

**P: ¿Qué sucede si se elimina una plantilla?**

A: Las plantillas eliminadas ya no estarán presentes en las directivas de plantillas.

**P: ¿Puedo asignar varios usuarios a una directiva de plantilla en el centro de Teams administración?**

A: Sí.

1. En el Centro de administración, vaya a **Usuarios.**
1. En la tabla de lista Usuarios, seleccione los usuarios que desea asignar a una directiva de plantillas determinada.
1. Seleccione Editar configuración y cambie el campo Directivas de plantillas.
1. Seleccione Aplicar.
   Más información [Asignar directivas a los usuarios en Microsoft Teams - Microsoft Teams Microsoft \| Docs](./assign-policies.md#assign-a-policy-to-a-batch-of-users).

**P: ¿Cómo puedo ver todos los usuarios asignados a una directiva específica?**

A: En el Centro de administración:

1. Vaya a la **sección** Usuarios.
2. Seleccione el filtro en la tabla de lista Usuarios y filtre para la directiva de plantilla de equipo.
3. Seleccione **Aplicar**.

![Directiva de plantilla seleccionada y ver usuarios](media/template-policies-5.png)

**P: ¿Puedo administrar directivas de plantillas a través de PowerShell?**

A: No, no se admite la administración de plantillas en PowerShell.

**P: ¿Son aplicables las directivas de plantillas a EDU?**

A: No, no se admiten las directivas de plantilla para EDU.

## <a name="related-topics"></a>Temas relacionados

- [Introducción a las plantillas de equipo en el Centro de administración](./get-started-with-teams-templates-in-the-admin-console.md)

- [Crear una plantilla de equipo personalizada](./create-a-team-template.md)

- [Crear una plantilla a partir de un equipo existente](./create-template-from-existing-team.md)

- [Crear una plantilla de equipo a partir de una plantilla de equipo existente](./create-template-from-existing-template.md)

- [Asignar directivas a los usuarios en Microsoft Teams: Microsoft Teams \| Microsoft Docs](./assign-policies.md)

- [Asignar usuarios por lotes a una directiva](/powershell/module/teams/new-csbatchpolicyassignmentoperation)
