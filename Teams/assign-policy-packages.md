---
title: Asignar paquetes de directivas a usuarios y grupos
author: mkbond007
ms.author: mabond
ms.reviewer: tomkau, saragava, ritikag, jastark
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Obtenga información sobre las diferentes formas de asignar paquetes de directivas a usuarios y grupos en Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: cd6cbaab900ce1e9e5f4a2bd19731573c66ab7eb
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272055"
---
# <a name="assign-policy-packages-to-users-and-groups"></a>Asignar paquetes de directivas a usuarios y grupos

En este artículo se revisan las diferentes formas de asignar paquetes de directivas a usuarios y grupos en Microsoft Teams. Antes de leer, asegúrese de que ha leído [Asignar directivas en Teams: introducción](policy-assignment-overview.md).

> [!NOTE]
> Cada usuario necesitará el complemento de Comunicaciones avanzadas para recibir una tarea de paquete personalizado de directiva. Para más información, consulte [Complemento de Comunicaciones avanzadas para Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).

## <a name="assign-a-policy-package-to-users"></a>Asignar un paquete de directiva a los usuarios

Un paquete de directivas en Teams es una colección de directivas predefinidas y configuraciones de directiva que puede asignar a los usuarios que tienen los mismos roles o similares en su organización. Cada paquete de directivas está diseñado en torno a un rol de usuario e incluye directivas predefinidas y configuraciones de directiva que admiten actividades típicas para ese rol. Algunos ejemplos de paquetes de directivas son el paquete de educación (profesor) y el paquete de atención médica (trabajador clínico). Para obtener más información, consulte [Administrar paquetes de directivas en Teams](manage-policy-packages.md).

### <a name="assign-a-policy-package-to-one-user"></a>Asignar un paquete de directivas a un usuario

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Usuarios** y seleccione el usuario.

2. En la página del usuario, selecciona **Directivas** y, a continuación, junto a **Paquete de directivas**, selecciona **Editar**.

3. En el panel **Asignar paquete de directiva** , selecciona el paquete que quieras asignar y, a continuación, selecciona **Aplicar**.

    :::image type="content" source="media/assign-policy-package-one-user.png" alt-text="Captura de pantalla que muestra el Centro de administración de Teams para la asignación de paquetes de directivas a un usuario." lightbox="media/assign-policy-package-one-user-expanded.png":::

### <a name="assign-a-policy-package-to-multiple-users"></a>Asignar un paquete de directiva a varios usuarios

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Paquetes** de directivas y, a continuación, seleccione el paquete de directivas que quiera asignar haciendo clic a la izquierda del nombre del paquete.

2. Seleccione **Administrar usuarios**.

3. En el panel **Administrar usuarios**, busque el usuario por su nombre para mostrar o por su nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**. Repita este paso por cada usuario que quiera agregar.

4. Cuando termine de agregar usuarios, seleccione **Aplicar**.

    :::image type="content" source="media/assign-policy-package-multiple-users.png" alt-text="Captura de pantalla que muestra la asignación del paquete de directivas del Centro de administración de Teams a varios usuarios." lightbox="media/assign-policy-package-multiple-users-expanded.png":::

## <a name="assign-a-policy-package-to-a-group"></a>Asignar un paquete de directivas a un grupo

La opción de asignar un paquete de directiva a grupos le permite asignar múltiples directivas a un grupo de usuarios, como un grupo de seguridad o una lista de distribución. La asignación de directiva se extiende a los miembros del grupo en función de las reglas de prioridad. A medida que se agregan o se eliminan miembros de un grupo, sus asignaciones de directivas heredadas se actualizan correspondientemente.

Se recomienda asignar un paquete de directivas a grupos de hasta 50 000 usuarios, pero también funcionará con grupos más grandes.

Al asignar el paquete de directivas, se asigna inmediatamente al grupo. Sin embargo, la propagación de la asignación de directiva a los miembros del grupo se realiza como una operación en segundo plano y puede tardar algún tiempo, dependiendo del tamaño del grupo. Lo mismo ocurre cuando una directiva no está asignada a un grupo o cuando los miembros se agregan o quitan de un grupo.

> [!IMPORTANT]
> Antes de empezar, es importante comprender ([reglas de prioridad](assign-policies-users-and-groups.md#precedence-rules)) y ([clasificación de asignaciones de grupo](assign-policies-users-and-groups.md#group-assignment-ranking)). Asegúrese de leer y comprender los conceptos de ([Lo que debe saber sobre la asignación de directivas a grupos](assign-policies-users-and-groups.md#what-you-need-to-know-about-policy-assignment-to-groups)) anteriormente en este artículo.

### <a name="assign-a-policy-package-to-a-group-of-users-in-the-admin-center"></a>Asignar un paquete de directivas a un grupo de usuarios en el centro de administración

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a la página **Paquetes de directivas** .

2. Seleccione la pestaña **Agrupar asignación de paquete** .

3. Selecciona **Agregar** y, a continuación, en el panel **Asignar paquete de directivas a un grupo** , haz lo siguiente:

    1. Busque y agregue el grupo al que desea asignar el paquete de directivas.

    1. Seleccione un paquete de directivas.

    1. Establezca la clasificación para cada tipo de directiva.

    1. Seleccione **Aplicar**.

       :::image type="content" source="media/assign-policy-package-group.png" alt-text="Captura de pantalla de Asignar un paquete de directiva a un panel de grupo." lightbox="media/assign-policy-package-group-expanded.png":::

4. Para administrar la clasificación de un tipo de directiva específico, vaya a la página de directiva específica.

5. Para reasignar un paquete de directivas a un grupo, quite primero la asignación de directiva de grupo. A continuación, siga los pasos anteriores para asignar el paquete de directivas a un grupo.

### <a name="work-with-powershell"></a>Trabajar con PowerShell

#### <a name="get-the-teams-powershell-module"></a>Obtener el módulo de PowerShell de Teams

Para obtener instrucciones detalladas, consulte [Instalar PowerShell de Teams](teams-powershell-install.md).

#### <a name="assign-a-policy-package-to-a-group-of-users"></a>Asignar un paquete de directivas a un grupo de usuarios

Use el cmdlet [Grant-CsGroupPolicyPackageAssignment](/powershell/module/teams/grant-csgrouppolicypackageassignment) para asignar un paquete de directivas a un grupo. Puede especificar un grupo mediante el id. de objeto, la dirección SIP o la dirección de correo electrónico. Al asignar el paquete de directivas, especifique un ([clasificación de asignación de grupo](assign-policies-users-and-groups.md#group-assignment-ranking)) para cada tipo de directiva del paquete de directivas.

En este ejemplo, asignamos el paquete de directivas de Education_Teacher a un grupo con una clasificación de asignación de 1 para TeamsAppSetupPolicy y TeamsMeetingBroadcastPolicy y una clasificación de 2 para TeamsMeetingPolicy.

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a>Asignar un paquete de directivas a un lote de usuarios

Con la asignación de paquetes de directivas por lotes, puede asignar un paquete de directivas a grandes conjuntos de usuarios a la vez sin tener que usar un script. Use el cmdlet [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) para enviar un lote de usuarios y el paquete de directivas que desea asignar. Las asignaciones se procesan como una operación de segundo plano y se genera un identificador de operación para cada lote. A continuación, puede usar el cmdlet [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) para realizar un seguimiento del progreso y el estado de las asignaciones de un lote.

Especifique los usuarios por su id. de objeto o dirección SIP (Protocolo de inicio de sesión). La dirección SIP de un usuario suele tener el mismo valor que el Nombre principal de usuario (UPN) o la dirección de correo electrónico, pero no es necesario. Si un usuario se especifica mediante su UPN o correo electrónico, pero tiene un valor diferente a su dirección SIP, se producirá un error en la asignación de directivas para el usuario. Si un lote incluye usuarios duplicados, los duplicados se quitarán del lote antes de procesarse y el estado solo se proporcionará para los usuarios únicos que quedan en el lote.

Un lote contiene hasta 5000 usuarios. Para obtener los mejores resultados, no envíe más de unos pocos lotes a la vez. Permita que los lotes completen el procesamiento antes de enviar más lotes.

### <a name="use-the-teams-powershell-module"></a>Usar el módulo de PowerShell de Teams

Ejecute lo siguiente para instalar el [módulo Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (si aún no lo ha hecho). Asegúrate de instalar la versión 1.0.5 o posterior.

```powershell
Install-Module -Name MicrosoftTeams
```

Ejecute lo siguiente para conectarse a Teams e iniciar una sesión.

```powershell
Connect-MicrosoftTeams
```

Cuando se le solicite, inicie sesión con sus credenciales de administrador.

### <a name="assign-policy-packages-to-a-batch-of-users"></a>Asignar paquetes de directivas a un lote de usuarios

En este ejemplo, usamos el cmdlet [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) para asignar el paquete de directivas de Education_PrimaryStudent a un lote de usuarios.

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="see-the-status-of-a-batch-assignment"></a>Ver el estado de una asignación por lotes

Ejecute lo siguiente para obtener el estado de una asignación de lote, donde OperationId es el id. de operación devuelto por el `New-CsBatchPolicyAssignmentOperation` cmdlet para un lote determinado.

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

Si el resultado muestra que se ha producido un error, ejecute lo siguiente para obtener más información sobre los errores, que están en la `UserState` propiedad.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

Para obtener más información, consulte [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation).

## <a name="related-topics"></a>Temas relacionados

- [Administrar Teams con directivas](manage-teams-with-policies.md)
- [Administrar paquetes de directivas en Microsoft Teams](manage-policy-packages.md)
- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
- [Asignar directivas en Teams: introducción](policy-assignment-overview.md)
