---
title: Asignar directivas a usuarios y grupos
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
description: Aprenda las diferentes formas de asignar directivas a usuarios y grupos en Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 60d3835a3cdda752dab0305b68b68e91446e10d7
ms.sourcegitcommit: 9532eb79310cd653010565607fa394f2b8dd182d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/23/2022
ms.locfileid: "65646439"
---
# <a name="assign-policies-to-users-and-groups"></a>Asignar directivas a usuarios y grupos

En este artículo se revisan las diferentes formas de asignar directivas a usuarios y grupos de Microsoft Teams. Antes de leer, asegúrese de que ha leído [Asignar directivas en Teams : introducción](policy-assignment-overview.md).

## <a name="assign-a-policy-to-individual-users"></a>Asignar una directiva a usuarios individuales

Siga estos pasos para asignar una directiva a un usuario individual o a un número reducido de usuarios a la vez.

### <a name="use-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

Para asignar una directiva a un usuario:

1. En el panel de navegación izquierdo del [centro de administración de Microsoft Teams](https://admin.teams.microsoft.com), vaya a **UsuariosAdministrar** >  usuarios.
2. Seleccione el usuario haciendo clic a la izquierda del nombre de usuario y, a continuación, seleccione **Editar configuración**.
3. Seleccione la directiva que quiera asignar y, a continuación, seleccione **Aplicar**.

![Asigne una directiva a un usuario en el centro de administración de Teams.](media/assign-policy-user.png)

> [!NOTE]
> Para anular la asignación de una directiva especializada a un usuario, puede establecer cada directiva en **Global (valor predeterminado para toda la organización).**

También puede hacer lo siguiente para asignar una directiva a un usuario:

1. En el panel de navegación izquierdo del Microsoft Teams centro de administración, vaya a la página de directivas.
2. Seleccione la directiva que desea asignar haciendo clic a la izquierda del nombre de la directiva.
3. Seleccione **Administrar usuarios**.
4. En el panel **Administrar usuarios**, busque el usuario por su nombre para mostrar o por su nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**. Repita este paso por cada usuario que quiera agregar.
5. Cuando termine de agregar usuarios, seleccione **Aplicar**.

![Asigne una directiva a un usuario en el centro de administración de Teams a través del segundo método.](media/assign-policy-user2.png)

### <a name="use-powershell"></a>Usar PowerShell

Cada tipo de directiva tiene su propio conjunto de cmdlets para administrarlo. Use el `Grant-` cmdlet para un tipo de directiva determinado para asignar la directiva. Por ejemplo, use el `Grant-CsTeamsMeetingPolicy` cmdlet para asignar una directiva de reunión de Teams a los usuarios. Estos cmdlets se incluyen en el módulo Teams PowerShell y se documentan en la [referencia de cmdlet de Skype Empresarial](/powershell/skype).

 Descargue e instale la [versión pública de Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) (si aún no lo ha hecho) y, a continuación, ejecute lo siguiente para conectarse.

> [!NOTE]
> El conector en línea del cliente de Skype® Empresarial actualmente forma parte del módulo más reciente de Windows PowerShell de Teams.
>
> Si usa la versión pública más reciente [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/), no es necesario instalar el conector en línea de Skype Empresarial.

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

En este ejemplo, asignamos una directiva de reunión de Teams denominada Directiva de reunión de alumnos a un usuario llamado Reda.

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

Para obtener más información, lea [Administrar directivas a través de PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).

## <a name="assign-a-policy-to-a-group"></a>Asignar una directiva a un grupo

La asignación de directivas a grupos le permite asignar una directiva a un grupo de usuarios, como un grupo de seguridad, una unidad organizativa o una lista de distribución. La asignación de directiva se extiende a los miembros del grupo en función de las reglas de prioridad. A medida que se agregan o se eliminan miembros de un grupo, sus asignaciones de directivas heredadas se actualizan correspondientemente.

La asignación de directivas a grupos se recomienda para grupos de hasta 50 000 usuarios, pero también funcionará con grupos más grandes.

Al asignar la directiva, se asigna inmediatamente al grupo. Sin embargo, la propagación de la asignación de directiva a los miembros del grupo se realiza como una operación en segundo plano y puede tardar algún tiempo, dependiendo del tamaño del grupo. Lo mismo ocurre cuando una directiva no está asignada a un grupo o cuando los miembros se agregan o quitan de un grupo.

Las asignaciones de directiva de grupo solo se propagan a los usuarios que son miembros directos del grupo. Las asignaciones no se propagan a los miembros de grupos anidados.

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a>Lo que debe saber sobre la asignación de directivas a grupos

Antes de empezar, es importante comprender las reglas de prioridad y la clasificación de las asignaciones de grupo.

#### <a name="precedence-rules"></a>Reglas de prioridad

Para un tipo de directiva determinado, la directiva efectiva de un usuario se determina de acuerdo con lo siguiente:

- Una directiva que se asigna directamente a un usuario tiene prioridad sobre cualquier otra directiva del mismo tipo asignada a un grupo. En otras palabras, si se asigna directamente a un usuario una directiva de un tipo determinado, ese usuario no heredará una directiva del mismo tipo de un grupo. Esto también significa que, si un usuario tiene una directiva de un tipo determinado que se le asignó directamente, tendrá que quitar esa directiva del usuario antes de que pueda heredar una directiva del mismo tipo de un grupo.
- Si un usuario no tiene una directiva asignada directamente y es miembro de dos o más grupos y cada grupo tiene asignada una directiva del mismo tipo, el usuario hereda la directiva de la asignación de grupo con la clasificación más alta.
- Si un usuario no es miembro de ningún grupo al que se le haya asignado una directiva, la directiva global (predeterminada para toda la organización) para ese tipo de directiva se aplica al usuario.

La directiva efectiva de un usuario se actualiza de acuerdo con estas reglas:

- cuando se agrega o quita un usuario de un grupo al que se le ha asignado una directiva.
- una directiva no está asignada a un grupo.
- se quita una directiva que se asigna directamente al usuario.

#### <a name="group-assignment-ranking"></a>Clasificación de tareas de grupo

> [!NOTE]
> Se puede asignar un tipo de directiva determinado a un máximo de 64 grupos en todas las instancias de directiva para ese tipo.

Al asignar una directiva a un grupo, se especifica una clasificación para la asignación del grupo. Esto se usa para determinar qué directiva debe heredar un usuario como su directiva efectiva si el usuario es miembro de dos o más grupos y se asigna una directiva del mismo tipo a cada grupo.

La clasificación de las asignaciones de grupo es relativa a otras asignaciones de grupo del mismo tipo. Por ejemplo, si va a asignar una directiva de llamada a dos grupos, establezca la clasificación de una tarea en 1 y la otra en 2, siendo 1 la más alta. La clasificación de asignaciones de grupo indica qué pertenencia a grupos es más importante o más relevante que otras pertenencias a grupos en lo que respecta a la herencia.

Supongamos, por ejemplo, que tiene dos grupos: Empleados de store y Administradores de tienda. A ambos grupos se les asigna una directiva de llamada Teams, una directiva de llamadas de empleados de store y una directiva de llamada de administradores de almacén, respectivamente. Para un administrador de almacén que se encuentra en ambos grupos, su rol como administrador es más relevante que su rol como empleado, por lo que la directiva de llamada que se asigna al grupo Administradores de almacén debe tener una clasificación más alta.

|Grupo |Teams nombre de directiva de llamadas  |Clasificación|
|---------|---------|---|
|Administradores de store   |Directiva de llamadas de administradores de almacén         |1|
|Empleados de store    |Directiva de llamadas de empleados de Store      |2|

Si no especifica una clasificación, se asigna la clasificación más baja a la asignación de directivas.

### <a name="in-the-teams-admin-center"></a>En el centro de administración de Teams

> [!NOTE]
> Actualmente, la asignación de directivas a grupos que usan el centro de administración de Microsoft Teams solo está disponible para la directiva de llamadas de Teams, Teams directiva de parque de llamadas, directiva de Teams, directiva de eventos en directo Teams, directiva de reunión de Teams y directiva de mensajería de Teams. Para otros tipos de directivas, use PowerShell.

1. En el panel de navegación izquierdo del centro de administración de Microsoft Teams, vaya a la página de tipo de directiva. Por ejemplo, vaya a **Directivas** >  de Reunión **.**
2. Seleccione la pestaña **Asignación de directiva de grupo** .
3. Seleccione **Agregar grupo** y, a continuación, en el panel **Asignar directiva a grupo** , haga lo siguiente:
    1. Busque y agregue el grupo al que desea asignar la directiva.
    2. Establezca la clasificación de la tarea de grupo.
    3. Seleccione la directiva que desea asignar.
    4. Seleccione **Aplicar**.
    
![Asigne una directiva a un grupo en el centro de administración de Teams.](media/assign-policy-group.png)

Para quitar una asignación de directiva de grupo, en la pestaña **Asignación de directiva** de grupo de la página directiva, seleccione la asignación de grupo y, a continuación, seleccione **Quitar**.

Para cambiar la clasificación de una asignación de grupo, primero tiene que quitar la asignación de directiva de grupo. Después, siga los pasos anteriores para asignar la directiva a un grupo.

### <a name="use-the-powershell-option"></a>Usar la opción PowerShell

> [!NOTE]
> Actualmente, la asignación de directivas a grupos con PowerShell no está disponible para todos los tipos de directiva de Teams. Consulte [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) para obtener la lista de tipos de directiva admitidos.

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Instalar y conectarse al módulo Microsoft Teams PowerShell

Para obtener instrucciones detalladas, vea [Instalar Teams PowerShell](teams-powershell-install.md).

#### <a name="assign-a-policy-to-a-group-of-users"></a>Asignar una directiva a un grupo de usuarios

Use el cmdlet [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) para asignar una directiva a un grupo. Puede especificar un grupo mediante el id. de objeto, la dirección SIP o la dirección de correo electrónico.

En este ejemplo, asignamos una directiva de reunión de Teams denominada Directiva de reunión de administradores de minoristas a un grupo con una clasificación de asignación de 1.

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a>Obtener asignaciones de directivas para un grupo

Use el cmdlet [Get-CsGroupPolicyAssignment](/powershell/module/teams/get-csgrouppolicyassignment) para asignar todas las directivas a un grupo. Tenga en cuenta que los grupos siempre se muestran por su id. de grupo incluso si se usó su dirección SIP o su dirección de correo electrónico para asignar la directiva.

En este ejemplo, recuperamos todas las directivas asignadas a un grupo específico.

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

En este ejemplo, se devuelven todos los grupos a los que se ha asignado una directiva de reunión de Teams.

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a>Quitar una directiva de un grupo

Use el cmdlet [Remove-CsGroupPolicyAssignment](/powershell/module/teams/remove-csgrouppolicyassignment) para quitar una directiva de un grupo. Al quitar una directiva de un grupo, se actualizan las prioridades de otras directivas del mismo tipo asignadas a ese grupo y que tienen una clasificación inferior. Por ejemplo, si quita una directiva que tiene una clasificación de 2, las directivas con una clasificación de 3 y 4 se actualizarán para reflejar su nueva clasificación. En las dos tablas siguientes se muestra este ejemplo.

Esta es una lista de las asignaciones y prioridades de directivas para una directiva de reunión de Teams.

|Nombre del grupo  |Nombre de la directiva  |Clasificación|
|---------|---------|---------|
|Ventas    |Directiva de ventas       | 1        |
|Región Oeste     |Directiva de región oeste         |2         |
|División    |Directiva de división         |3         |
|Subsidiaria   |Directiva de subsidiarias        |4         |

Si quitamos la directiva Región Oeste del grupo Región Oeste, las asignaciones y prioridades de la directiva se actualizarán de la siguiente manera.

|Nombre del grupo  |Nombre de la directiva  |Clasificación|
|---------|---------|---------|
|Ventas    |Directiva de ventas       | 1        |
|División    |Directiva de división         |2         |
|Subsidiaria   |Directiva de subsidiarias        |3        |

En este ejemplo, quitamos la directiva de reunión Teams de un grupo.

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

#### <a name="change-a-policy-assignment-for-a-group"></a>Cambiar una asignación de directiva para un grupo

> [!NOTE]
> El cmdlet [Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) estará disponible próximamente. Mientras tanto, para cambiar una asignación de directiva de grupo, puede quitar la asignación de directiva actual del grupo y, a continuación, agregar una nueva asignación de directiva.

Después de asignar una directiva a un grupo, puede usar el cmdlet [Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) para cambiar la asignación de directivas de ese grupo de la siguiente manera:

- Cambiar la clasificación
- Cambiar la directiva de un tipo de directiva determinado
- Cambiar la directiva de un determinado tipo de directiva y la clasificación

En este ejemplo, cambiamos la directiva de estacionamiento de llamadas Teams de un grupo a una directiva denominada SupportCallPark y la clasificación de tareas a 3.

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a>Cambiar la directiva eficaz para un usuario

Este es un ejemplo de cómo cambiar la directiva efectiva para un usuario al que se le asigna una directiva directamente.

En primer lugar, usamos el cmdlet [Get-CsUserPolicyAssignment](/powershell/module/teams/get-csuserpolicyassignment) junto con el `PolicySource` parámetro para obtener detalles de las directivas de difusión de reunión Teams asociadas con el usuario.

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

La salida muestra que al usuario se le asignó directamente una directiva de difusión de reunión Teams denominada Eventos de empleados, que tiene prioridad sobre la directiva denominada Eventos en directo de proveedor asignada a un grupo al que pertenece el usuario.

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

Ahora, quitamos la directiva Eventos de empleado del usuario. Esto significa que el usuario ya no tiene asignada una directiva de difusión de reunión de Teams directamente y heredará la directiva Eventos en directo del proveedor asignada al grupo al que pertenece el usuario.

Para ello, use el siguiente cmdlet en el módulo Skype Empresarial PowerShell.

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

Use el siguiente cmdlet en el módulo Teams PowerShell para hacerlo a escala a pesar de una asignación de directiva de lote, donde $users es una lista de usuarios que se especifica.

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a>Asignar una directiva a un lote de usuarios

### <a name="use-the-admin-center"></a>Usar el centro de administración

Para asignar una directiva a los usuarios en masa:

1. En el panel de navegación izquierdo del Microsoft Teams centro de administración, seleccione **Usuarios**.
2. Busque los usuarios a los que desea asignar la directiva o filtre la vista para mostrar los usuarios que desee.
3. En la columna **&#x2713;** (marca de verificación), seleccione los usuarios. Para seleccionar todos los usuarios, haga clic en &#x2713; (marca de verificación) situado en la parte superior de la tabla.
4. Selecciona **Editar configuración**, realiza los cambios que quieras y, a continuación, selecciona **Aplicar**.

Para ver el estado de la asignación de directiva, en el banner que aparece en la parte superior de la página **Usuarios** después de seleccionar **Aplicar** para enviar la asignación de directiva, seleccione **Registro de actividades**. O bien, en el panel de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **Panel** y, a continuación, en **Registro** de actividades, seleccione **Ver detalles**. El registro de actividades muestra las asignaciones de directivas a lotes de más de 20 usuarios a través del centro de administración de Microsoft Teams de los últimos 30 días. Para obtener más información, consulte [Ver las asignaciones de directivas en el registro de actividades](activity-log.md).

### <a name="use-powershell-method"></a>Usar el método de PowerShell

> [!NOTE]
> Actualmente, la asignación de directivas por lotes con PowerShell no está disponible para todos los tipos de directiva de Teams. Consulte [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) para obtener la lista de tipos de directiva admitidos.

Con la asignación de directivas por lotes, puede asignar una directiva a grandes conjuntos de usuarios a la vez sin tener que usar un script. Use el cmdlet [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) para enviar un lote de usuarios y la directiva que desea asignar. Las asignaciones se procesan como una operación de segundo plano y se genera un identificador de operación para cada lote. A continuación, puede usar el cmdlet [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) para realizar un seguimiento del progreso y el estado de las asignaciones de un lote.

Especifique los usuarios por su id. de objeto o dirección SIP (Protocolo de inicio de sesión). La dirección SIP de un usuario suele tener el mismo valor que el Nombre principal de usuario (UPN) o la dirección de correo electrónico, pero no es necesario. Si un usuario se especifica mediante su UPN o correo electrónico, pero tiene un valor diferente a su dirección SIP, se producirá un error en la asignación de directivas para el usuario. Si un lote incluye usuarios duplicados, los duplicados se quitarán del lote antes de procesarse y el estado solo se proporcionará para los usuarios únicos que quedan en el lote.

Un lote puede contener hasta 5000 usuarios. Para obtener los mejores resultados, no envíe más de unos pocos lotes a la vez. Permita que los lotes completen el procesamiento antes de enviar más lotes.

#### <a name="install-and-connect-to-the-teams-powershell-module"></a>Instalar y conectarse al módulo Teams PowerShell

Ejecute lo siguiente para instalar el [módulo Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams). Asegúrate de instalar la versión 1.0.5 o posterior.

```powershell
Install-Module -Name MicrosoftTeams
```

Ejecuta lo siguiente para conectarte a Teams e iniciar una sesión.

```powershell
Connect-MicrosoftTeams
```

Cuando se le solicite, inicie sesión con sus credenciales de administrador.

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a>Instalar y conectarse al módulo de PowerShell de Azure AD para Graph (opcional)

Es posible que también desee [descargar e instalar PowerShell de Azure AD para Graph módulo](/powershell/azure/active-directory/install-adv2) (si aún no lo ha hecho) y conectarse a Azure AD para poder recuperar una lista de usuarios de su organización.

Ejecute lo siguiente para conectarse a Azure AD.

```powershell
Connect-AzureAD
```

Cuando se le solicite, inicie sesión con las mismas credenciales de administrador que usó para conectarse a Teams.

#### <a name="assign-a-setup-policy-to-a-batch-of-users"></a>Asignar una directiva de configuración a un lote de usuarios

En este ejemplo, usamos el cmdlet [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) para asignar una directiva de configuración de aplicaciones denominada Directiva de configuración de aplicaciones de recursos humanos a un lote de usuarios enumerados en el archivo users_ids.text.

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $user_ids -OperationName "Example 1 batch"
```

En este ejemplo, nos conectamos a Azure AD para recuperar una colección de usuarios y, a continuación, asignamos una directiva de mensajería denominada Directiva de mensajería de nueva contratación a un lote de usuarios especificado mediante su dirección SIP.

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

#### <a name="get-the-status-of-a-batch-assignment"></a>Obtener el estado de una asignación por lotes

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
- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
- [Asignar directivas en Teams: introducción](policy-assignment-overview.md)
