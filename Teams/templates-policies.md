---
title: Administrar plantillas de equipo en el centro de administración
author: serdars
ms.author: serdars
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
ms.localizationpriority: medium
search.appverid: MET150
description: Obtenga información sobre cómo administrar plantillas de equipo en el centro de administración
ms.openlocfilehash: c753a92205844ebade9a713a8442837039232339
ms.sourcegitcommit: 140c34f20f9cd48d7180ff03fddd60f5d1d3459f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2022
ms.locfileid: "65248942"
---
# <a name="manage-team-templates-in-the-admin-center"></a>Administrar plantillas de equipo en el centro de administración

Administre las plantillas de equipo que los usuarios finales ven creando directivas de plantillas en el centro de administración. Dentro de cada directiva de plantillas, puede designar qué plantillas se muestran u ocultan.
Asigne diferentes usuarios a diferentes directivas de plantillas para que los usuarios solo vean el subconjunto de plantillas de equipo especificado.

Vea este breve vídeo para aprender a administrar directivas de plantillas.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyXL9]

## <a name="create-templates-policies-and-assign-available-templates"></a>Crear directivas de plantillas y asignar plantillas disponibles

1. Inicie la sesión en el Centro de administración de Teams

2. Vaya a **las directivas Teams** >  **Templates**.

3. Elija **Agregar**.

    ![Se seleccionan las directivas de plantillas y se resalta Agregar.](media/template-policies-1.png)

1. Asigne un nombre a la directiva y agregue una breve descripción.

2. En la lista **Plantillas visibles** , seleccione las plantillas que desea ocultar y, a continuación, seleccione **Ocultar**.

    ![Las plantillas seleccionadas con ocultar resaltadas.](media/template-policies-2.png)

    Puede ver las plantillas que ha elegido ocultar en la lista **de plantillas ocultas** .

1. Para mostrar determinadas plantillas, vaya a la lista **De plantillas ocultas** .

2. Seleccione las plantillas que desea mostrar y, a continuación, seleccione **Mostrar**.

   ![Las plantillas seleccionadas que no están ocultas.](media/template-policies-3.png)

   Las plantillas seleccionadas aparecerán en la lista **Plantillas visibles** .
3. Elija **Guardar**.

   La nueva directiva de plantillas se muestra en la lista **Directivas de plantillas** .

## <a name="assign-templates-policies-to-users"></a>Asignar directivas de plantillas a usuarios

Puede asignar una directiva de plantillas directamente a los usuarios, ya sea de forma individual o a escala a través de una asignación por lotes. Tenga en cuenta que la nueva directiva puede tardar hasta 24 horas en surtir efecto para los usuarios.

> [!Note]
> Actualmente, no se admite la asignación de directivas de plantillas a usuarios en función de la pertenencia a grupos, como a todos los usuarios de un grupo de seguridad. Esta funcionalidad estará disponible en el futuro.

Para obtener información general sobre las formas de asignar directivas en Teams, vea [Asignar directivas en Teams](policy-assignment-overview.md).

### <a name="assign-a-templates-policy-to-individual-users"></a>Asignar una directiva de plantillas a usuarios individuales

Puede usar el centro de administración de Teams o PowerShell para asignar una directiva de plantillas a un usuario individual o a un número reducido de usuarios a la vez. Para obtener más información, vea [Asignar una directiva a usuarios individuales](assign-policies-users-and-groups.md#assign-a-policy-to-individual-users).

### <a name="assign-a-templates-policy-to-a-batch-of-users"></a>Asignar una directiva de plantillas a un lote de usuarios

Puede usar PowerShell para asignar una directiva de plantillas a grandes conjuntos de usuarios a la vez. Para ello, use el cmdlet [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) junto con TeamsTemplatePermissionPolicy como el ```PolicyType``` para enviar un lote de usuarios y la directiva de plantillas que desea asignar. Por ejemplo:

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName <Any operation name> -PolicyType TeamsTemplatePermissionPolicy -PolicyName <policy name> -Identity <users identity | list of user identities>
```

Las asignaciones se procesan como una operación de segundo plano y se genera un identificador de operación para cada lote. A continuación, puede usar el cmdlet [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) para realizar un seguimiento del progreso y el estado de las asignaciones de un lote.

Para obtener más información, vea [Asignar una directiva a un lote de usuarios con PowerShell](assign-policies-users-and-groups.md#use-powershell-method).

## <a name="size-limits-for-templates-policies"></a>Límites de tamaño para las directivas de plantillas

Puede ocultar un máximo de 100 plantillas por directiva. El botón **Ocultar** está deshabilitado si la directiva determinada ya tiene 100 plantillas ocultas.

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

**P: Si se crea una plantilla, ¿se incluirá en mis directivas?**

R: Las nuevas plantillas estarán visibles de forma predeterminada. Puede elegir ocultar la plantilla en el centro de administración en la sección Directivas de plantillas.

**P: ¿Qué sucede si se elimina una plantilla?**

R: Las plantillas eliminadas ya no estarán presentes en ninguna directiva de plantillas.

**P: ¿Puedo asignar varios usuarios a una directiva de plantillas en el centro de administración de Teams?**

R: Sí.

1. En el centro de administración de Teams, vaya a **UsuariosAdministrar** >  usuarios.
1. En la lista de usuarios, seleccione los usuarios que desea asignar a la directiva de plantillas.
1. Seleccione **Editar configuración** y, a continuación, en **Directiva de plantillas**, elija la directiva que quiera asignar.
1. Elija **Aplicar**.

Para obtener más información, vea [Asignar una directiva a usuarios individuales](assign-policies-users-and-groups.md#assign-a-policy-to-individual-users).

**P: Cómo ver todos los usuarios asignados a una directiva específica?**

R: En el centro de administración de Teams:

1. Vaya a **UsuariosAdministrar** >  usuarios.
2. Seleccione **Filtro**, establezca un filtro para la directiva de plantillas y, después, elija **Aplicar**.

    ![La directiva de plantillas seleccionada y ver los usuarios.](media/template-policies-5.png)

**P: ¿Puedo administrar directivas de plantillas a través de PowerShell?**

R: No, no se admite la administración de directivas de plantillas en PowerShell. Sin embargo, puede usar PowerShell para [asignar directivas de plantillas](#assign-templates-policies-to-users) a los usuarios.

**P: ¿Se aplican las directivas de plantillas a la educación?**

R: No, no se admiten directivas de plantillas para EDU.

## <a name="related-articles"></a>Artículos relacionados

- [Comenzar con plantillas de equipo en el centro de administración](./get-started-with-teams-templates-in-the-admin-console.md)

- [Crear una plantilla de equipo personalizada](./create-a-team-template.md)

- [Crear una plantilla a partir de un equipo existente](./create-template-from-existing-team.md)

- [Crear una plantilla de equipo a partir de una plantilla de equipo existente](./create-template-from-existing-template.md)

- [Asignar directivas a los usuarios en Microsoft Teams: Microsoft Teams \| Microsoft Docs](./policy-assignment-overview.md)

- [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation)
