---
title: Asignar paquetes de directiva a usuarios y grupos
author: KarliStites
ms.author: kastites
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
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre las diferentes formas de asignar paquetes de directiva a usuarios y grupos en Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: e70d5e2bf0db6cb7dfd93e35a8207fce61fa75fd
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796834"
---
# <a name="assign-policy-packages-to-users-and-groups"></a>Asignar paquetes de directiva a usuarios y grupos

En este artículo se revisan las diferentes formas de asignar paquetes de directiva a usuarios y grupos en Microsoft Teams. Antes de leer, asegúrese de que ha leído Asignar directivas [en Teams: introducción.](policy-assignment-overview.md)

> [!NOTE]
> Cada usuario necesitará el complemento Comunicaciones avanzadas para recibir una asignación de paquete de directiva personalizada. Para obtener más información, vea [Complemento comunicaciones avanzadas para Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).

## <a name="assign-a-policy-package-to-users"></a>Asignar un paquete de directiva a los usuarios

Un paquete de directivas en Teams es una colección de directivas predefinidas y configuraciones de directiva que puede asignar a usuarios que tienen los mismos roles o similares en su organización. Cada paquete de directivas está diseñado en torno a un rol de usuario e incluye directivas predefinidas y configuraciones de directiva que admiten actividades típicas de ese rol. Algunos ejemplos de paquetes de directivas son el paquete educación (profesor) y el paquete de atención sanitaria (trabajador clínico). Para obtener más información, vea [Administrar paquetes de directivas en Teams](manage-policy-packages.md).

### <a name="assign-a-policy-package-to-one-user"></a>Asignar un paquete de directiva a un usuario

1. En el panel de navegación izquierdo del Microsoft Teams de administración, vaya a **Usuarios** y, a continuación, seleccione el usuario.
2. En la página del usuario, seleccione **Directivas** y, a continuación, junto **a Paquete de directivas,** seleccione **Editar.**
3. En el **panel Asignar paquete de** directiva, seleccione el paquete que desea asignar y, a continuación, seleccione **Guardar.**

![Teams captura de pantalla del Centro de administración para la asignación de paquetes de directivas a un usuario](media/assign-policypackages-user.png)

### <a name="assign-a-policy-package-to-multiple-users"></a>Asignar un paquete de directiva a varios usuarios

1. En el panel de navegación izquierdo del centro de administración de Microsoft Teams, vaya a Paquetes de directiva y, a continuación, seleccione el paquete de directiva que desea asignar haciendo clic a la izquierda del nombre del paquete.
2. Seleccione **Administrar usuarios**.
3. En el panel **Administrar usuarios**, busque el usuario por su nombre para mostrar o por su nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**. Repita este paso por cada usuario que quiera agregar.
4. Cuando haya terminado de agregar usuarios, seleccione **Guardar**.

![Teams captura de pantalla del Centro de administración para la asignación de paquetes de directivas a varios usuarios](media/assign-policypackages-multipleusers.png)

## <a name="assign-a-policy-package-to-a-group"></a>Asignar un paquete de directivas a un grupo

La opción de asignar un paquete de directiva a grupos le permite asignar múltiples directivas a un grupo de usuarios, como un grupo de seguridad o una lista de distribución. La asignación de directiva se extiende a los miembros del grupo en función de las reglas de prioridad. A medida que se agregan o se eliminan miembros de un grupo, sus asignaciones de directivas heredadas se actualizan correspondientemente.

La asignación de paquetes de directiva a grupos se recomienda para grupos de hasta 50 000 usuarios, pero también funcionará con grupos más grandes.

Al asignar el paquete de directiva, se asigna inmediatamente al grupo. Sin embargo, la propagación de la asignación de directivas a los miembros del grupo se realiza como una operación en segundo plano y puede tardar algún tiempo, dependiendo del tamaño del grupo. Lo mismo ocurre cuando una directiva no está desasignada de un grupo o cuando se agregan o quitan miembros de un grupo.

> [!IMPORTANT]
> Antes de empezar, es importante comprender (reglas de[prioridad)](assign-policies-users-and-groups.md#precedence-rules)y (clasificación[de asignaciones de grupo).](assign-policies-users-and-groups.md#group-assignment-ranking) Asegúrese de leer y comprender los conceptos de ([Qué necesita saber](assign-policies-users-and-groups.md#what-you-need-to-know-about-policy-assignment-to-groups)acerca de la asignación de directivas a grupos) anteriormente en este artículo.

### <a name="assign-a-policy-package-to-a-group-of-users-in-the-admin-center"></a>Asignar un paquete de directiva a un grupo de usuarios en el centro de administración

1. Inicie la sesión en el Centro de administración de Teams
2. En el panel de navegación izquierdo, vaya a la página del paquete de directivas.
3. Seleccione la pestaña Asignación de directivas de grupo.
4. Seleccione **Agregar grupo** y, a continuación, en el panel Asignar un paquete de directiva al grupo, haga lo siguiente:

    a. Busque y agregue el grupo al que desea asignar el paquete de directiva.

    b. Seleccione un paquete de directiva.

    c. Establezca la clasificación para cada tipo de directiva.

    d. Seleccione **Aplicar**.

![muestra la asignación de directiva de grupo](media/group-pkg-assignment.png)

5. Para administrar la clasificación de un tipo de directiva específico, vaya a la página de directiva específica.
6. Para reasignar un paquete de directiva a un grupo, primero quite la asignación de directiva de grupo. A continuación, siga los pasos anteriores para asignar el paquete de directiva a un grupo.

### <a name="work-with-powershell"></a>Trabajar con PowerShell

#### <a name="get-the-teams-powershell-module"></a>Obtener el Teams de PowerShell

Para obtener instrucciones paso a paso, vea [Instalar Teams PowerShell](teams-powershell-install.md).

#### <a name="assign-a-policy-package-to-a-group-of-users"></a>Asignar un paquete de directiva a un grupo de usuarios

Use el cmdlet [Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) para asignar un paquete de directiva a un grupo. Puede especificar un grupo con el id. de objeto, la dirección SIP o la dirección de correo electrónico. Al asignar el paquete de directiva, especifique una ( clasificación de asignaciones de[grupo)](assign-policies-users-and-groups.md#group-assignment-ranking)para cada tipo de directiva en el paquete de directiva.

En este ejemplo, asignamos el paquete de directiva de Education_Teacher a un grupo con una clasificación de asignaciones de 1 para TeamsAppSetupPolicy y TeamsMeetingBroadcastPolicy y una clasificación de 2 para TeamsMeetingPolicy.

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a>Asignar un paquete de directiva a un lote de usuarios

Con la asignación de paquetes de directivas por lotes, puede asignar un paquete de directiva a grandes conjuntos de usuarios a la vez sin tener que usar un script. Use el cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para enviar un lote de usuarios y el paquete de directiva que desea asignar. Las asignaciones se procesan como una operación de segundo plano y se genera un identificador de operación para cada lote. A continuación, puede usar el cmdlet [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) para realizar un seguimiento del progreso y el estado de las asignaciones en un lote.

Especifique los usuarios por su id. de objeto o dirección del Protocolo de inicio de sesión (SIP). La dirección SIP de un usuario suele tener el mismo valor que el nombre principal de usuario (UPN) o la dirección de correo electrónico, pero esto no es necesario. Si se especifica un usuario con su UPN o correo electrónico, pero tiene un valor diferente de su dirección SIP, la asignación de directivas no se realizará correctamente para el usuario. Si un lote incluye usuarios duplicados, los duplicados se quitarán del lote antes de procesar y el estado solo se proporciona para los usuarios únicos que permanecen en el lote.

Un lote contiene hasta 5 000 usuarios. Para obtener los mejores resultados, no envíe más de unos pocos lotes a la vez. Permitir que los lotes completen el procesamiento antes de enviar más lotes.

### <a name="use-the-teams-powershell-module"></a>Usar el Teams PowerShell

Ejecute lo siguiente para instalar el [Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (si aún no lo ha hecho). Asegúrese de instalar la versión 1.0.5 o posterior.

```powershell
Install-Module -Name MicrosoftTeams
```

Ejecute lo siguiente para conectarse a Teams e iniciar una sesión.

```powershell
Connect-MicrosoftTeams
```

Cuando se le solicite, inicie sesión con sus credenciales de administrador.

### <a name="assign-policy-packages-to-a-batch-of-users"></a>Asignar paquetes de directiva a un lote de usuarios

En este ejemplo, usamos el cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para asignar el paquete de directiva Education_PrimaryStudent un lote de usuarios.

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="see-the-status-of-a-batch-assignment"></a>Ver el estado de una asignación por lotes

Ejecute lo siguiente para obtener el estado de una asignación por lotes, donde OperationId es el id. de operación devuelto por el ```New-CsBatchPolicyAssignmentOperation``` cmdlet para un lote determinado.

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

Si el resultado muestra que se ha producido un error, ejecute lo siguiente para obtener más información sobre los errores, que se encuentran en la ```UserState``` propiedad.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

Para obtener más información, [vea Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).

## <a name="related-topics"></a>Temas relacionados

- [Administrar Teams con directivas](manage-teams-with-policies.md)
- [Administrar paquetes de directivas en Microsoft Teams](manage-policy-packages.md)
- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
- [Asignar directivas en Teams: introducción](policy-assignment-overview.md)
