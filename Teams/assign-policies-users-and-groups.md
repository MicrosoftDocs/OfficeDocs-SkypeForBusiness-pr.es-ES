---
title: Asignar directivas a usuarios y grupos
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
description: Obtenga información sobre las diferentes formas de asignar directivas a usuarios y grupos en Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 6b0db8c3da93e561bf374b32d08750d705ded8a2
ms.sourcegitcommit: 2bb8556650120b4f7cf509d8ff93d7e4d058829b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574352"
---
# <a name="assign-policies-to-users-and-groups"></a>Asignar directivas a usuarios y grupos

En este artículo se revisan las diferentes formas de asignar directivas a usuarios y grupos en Microsoft Teams. Antes de leer, asegúrese de que ha leído Asignar [directivas en Teams: introducción.](policy-assignment-overview.md)

## <a name="assign-a-policy-to-individual-users"></a>Asignar una directiva a usuarios individuales

Siga estos pasos para asignar una directiva a un usuario individual o a un pequeño número de usuarios a la vez.

### <a name="use-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

Para asignar una directiva a un usuario:

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Usuarios** y, a continuación, seleccione el usuario.
2. Seleccione el usuario haciendo clic a la izquierda del nombre de usuario y, a continuación, **seleccione Editar configuración.**
3. Seleccione la directiva que desea asignar y, a continuación, **seleccione Aplicar.**

![Asignar una directiva a un usuario en el Centro de administración de Teams](media/assign-policy-user.png)

También puede hacer lo siguiente:

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a la página de directiva.
2. Seleccione la directiva que desea asignar haciendo clic a la izquierda del nombre de la directiva.
3. Seleccione **Administrar usuarios**.
4. En el panel **Administrar usuarios**, busque el usuario por su nombre para mostrar o por su nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**. Repita este paso por cada usuario que quiera agregar.
5. Cuando haya terminado de agregar usuarios, seleccione **Aplicar**.

![Asignar una directiva a un usuario en el Centro de administración de Teams mediante el segundo método](media/assign-policy-user2.png)

### <a name="use-powershell"></a>Usar PowerShell

Cada tipo de directiva tiene su propio conjunto de cmdlets para administrarlo. Use el ```Grant-``` cmdlet de un tipo de directiva determinado para asignar la directiva. Por ejemplo, use el ```Grant-CsTeamsMeetingPolicy``` cmdlet para asignar una directiva de reunión de Teams a los usuarios. Estos cmdlets se incluyen en el módulo de PowerShell de Teams y se documentan en la referencia de [cmdlet de Skype Empresarial.](https://docs.microsoft.com/powershell/skype)

 Descargue e instale la versión pública de [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) de Teams (si aún no lo ha hecho) y ejecute lo siguiente para conectarse.

> [!NOTE]
> El conector en línea del cliente de Skype® Empresarial actualmente forma parte del módulo más reciente de Windows PowerShell de Teams.
>
> Si usa la última versión pública de PowerShell de [Teams,](https://www.powershellgallery.com/packages/MicrosoftTeams/)no es necesario instalar Skype Empresarial Online Connector.

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

En este ejemplo, asignamos una directiva de reunión de Teams denominada Directiva de reunión de estudiantes a un usuario denominado Reda.

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

Para obtener más información, lea [Administrar directivas a través de PowerShell.](teams-powershell-managing-teams.md#manage-policies-via-powershell)

## <a name="assign-a-policy-to-a-group"></a>Asignar una directiva a un grupo

La asignación de directivas a grupos le permite asignar una directiva a un grupo de usuarios, como un grupo de seguridad o una lista de distribución. La asignación de directiva se extiende a los miembros del grupo en función de las reglas de prioridad. A medida que se agregan o se eliminan miembros de un grupo, sus asignaciones de directivas heredadas se actualizan correspondientemente.

La asignación de directivas a grupos se recomienda para grupos de hasta 50 000 usuarios, pero también funcionará con grupos más grandes.

Al asignar la directiva, se asigna inmediatamente al grupo. Sin embargo, la propagación de la asignación de directivas a los miembros del grupo se realiza como una operación en segundo plano y puede tardar algún tiempo, dependiendo del tamaño del grupo. Lo mismo ocurre cuando una directiva no está desasignada de un grupo o cuando se agregan o quitan miembros de un grupo.

Las asignaciones de directivas de grupo solo se propagan a los usuarios que son miembros directos del grupo. Las tareas no se propagan a los miembros de grupos anidados.

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a>Qué necesita saber sobre la asignación de directivas a grupos

Antes de empezar, es importante comprender las reglas de prioridad y la clasificación de las asignaciones de grupo.

#### <a name="precedence-rules"></a>Reglas de prioridad

Para un tipo de directiva determinado, la directiva efectiva de un usuario se determina según lo siguiente:

- Una directiva que se asigna directamente a un usuario tiene prioridad sobre cualquier otra directiva del mismo tipo asignada a un grupo. En otras palabras, si a un usuario se le asigna directamente una directiva de un tipo determinado, ese usuario no heredará una directiva del mismo tipo de un grupo. Esto también significa que si un usuario tiene una directiva de un tipo determinado que se le asignó directamente, debe quitar esa directiva del usuario antes de que pueda heredar una directiva del mismo tipo de un grupo.
- Si un usuario no tiene una directiva asignada directamente a ellos y es miembro de dos o más grupos y cada grupo tiene asignada una directiva del mismo tipo, el usuario hereda la directiva de la asignación de grupo que tiene la clasificación más alta.
- Si un usuario no es miembro de ningún grupo al que se le haya asignado una directiva, la directiva global (predeterminada para toda la organización) para ese tipo de directiva se aplica al usuario.

La directiva efectiva de un usuario se actualiza según estas reglas:

- cuando se agrega o quita un usuario de un grupo al que se le ha asignado una directiva.
- una directiva no está desasignada de un grupo.
- se quita una directiva que está asignada directamente al usuario.

#### <a name="group-assignment-ranking"></a>Clasificación de tareas de grupo

Al asignar una directiva a un grupo, se especifica una clasificación para la asignación de grupo. Esto se usa para determinar qué directiva debe heredar un usuario como su directiva efectiva si el usuario es miembro de dos o más grupos y a cada grupo se le asigna una directiva del mismo tipo.

La clasificación de asignaciones de grupo es relativa a otras asignaciones de grupo del mismo tipo. Por ejemplo, si va a asignar una directiva de llamada a dos grupos, establezca la clasificación de una tarea en 1 y la otra en 2, siendo 1 la clasificación más alta. La clasificación de asignaciones de grupo indica qué pertenencia a un grupo es más importante o más relevante que otras pertenencias de grupo con respecto a la herencia.

Por ejemplo, tiene dos grupos: Empleados de la Tienda y Administradores de tienda. A ambos grupos se les asigna una directiva de llamadas de Teams, una directiva de llamadas de empleados de store y una directiva de llamadas de administradores de tienda, respectivamente. Para un administrador de tienda que está en ambos grupos, su rol como administrador es más relevante que su rol como empleado, por lo que la directiva de llamadas asignada al grupo Administradores de tienda debería tener una clasificación superior.

|Grupo |Nombre de directiva de llamadas de Teams  |Clasificación|
|---------|---------|---|
|Administradores de tienda   |Directiva de llamadas de administradores de tienda         |1|
|Almacenar empleados    |Directiva de llamadas de empleados de store      |2|

Si no especifica una clasificación, la asignación de directivas se asigna a la clasificación más baja.

### <a name="in-the-teams-admin-center"></a>En el Centro de administración de Teams

> [!NOTE]
> Actualmente, la asignación de directivas a grupos que usan el Centro de administración de Microsoft Teams solo está disponible para la directiva de llamadas de Teams, la directiva de parque de llamadas de Teams, la directiva de Teams, la directiva de eventos en directo de Teams, la directiva de reunión de Teams y la directiva de mensajería de Teams. Para otros tipos de directiva, use PowerShell.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a la página de tipo de directiva. Por ejemplo, vaya a **Directivas de reunión de**  >  **reuniones.**
2. Seleccione la **pestaña Asignación de directivas de** grupo.
3. Seleccione **Agregar grupo** y, a continuación, en el panel Asignar **directiva** al grupo, haga lo siguiente:
    1. Busque y agregue el grupo al que desea asignar la directiva.
    2. Establezca la clasificación de la tarea de grupo.
    3. Seleccione la directiva que desea asignar.
    4. Seleccione **Aplicar**.
    
![Asignar una directiva a un grupo en el Centro de administración de Teams](media/assign-policy-group.png)

Para quitar una asignación de directiva de grupo, en la pestaña **Asignación** de directivas de grupo de la página directiva, seleccione la asignación de grupo y, a continuación, **seleccione Quitar**.

Para cambiar la clasificación de una asignación de grupo, primero debe quitar la asignación de directiva de grupo. Después, siga los pasos anteriores para asignar la directiva a un grupo.

### <a name="use-the-powershell-option"></a>Usar la opción de PowerShell

> [!NOTE]
> Actualmente, la asignación de directivas a grupos que usan PowerShell no está disponible para todos los tipos de directivas de Teams. Vea [New-CsGroupPolicyAssignment para](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) obtener la lista de tipos de directiva admitidos.

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Instalar y conectarse al módulo De PowerShell de Microsoft Teams

Para obtener instrucciones paso a paso, vea [Instalar PowerShell de Teams.](teams-powershell-install.md)

#### <a name="assign-a-policy-to-a-group-of-users"></a>Asignar una directiva a un grupo de usuarios

Use el cmdlet [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) para asignar una directiva a un grupo. Puede especificar un grupo con el id. de objeto, la dirección SIP o la dirección de correo electrónico.

En este ejemplo, asignamos una directiva de reunión de Teams denominada Directiva de reunión de administradores minoristas a un grupo con una clasificación de tareas de 1.

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a>Obtener asignaciones de directivas para un grupo

Use el cmdlet [Get-CsGroupPolicyAssignment para](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment) obtener todas las directivas asignadas a un grupo. Tenga en cuenta que los grupos siempre aparecen en la lista por su id. de grupo, incluso si se usó su dirección SIP o su dirección de correo electrónico para asignar la directiva.

En este ejemplo, recuperamos todas las directivas asignadas a un grupo específico.

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

En este ejemplo, se devuelven todos los grupos asignados a una directiva de reunión de Teams.

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a>Quitar una directiva de un grupo

Use el cmdlet [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment) para quitar una directiva de un grupo. Al quitar una directiva de un grupo, se actualizan las prioridades de otras directivas del mismo tipo asignadas a ese grupo y que tienen una clasificación inferior. Por ejemplo, si quita una directiva que tiene una clasificación de 2, las directivas que tienen una clasificación de 3 y 4 se actualizan para reflejar su nueva clasificación. En las dos tablas siguientes se muestra este ejemplo.

Esta es una lista de las tareas de directiva y las prioridades de una directiva de reunión de Teams.

|Nombre del grupo  |Nombre de la directiva  |Clasificación|
|---------|---------|---------|
|Ventas    |Directiva de ventas       | 1        |
|Región Oeste     |Directiva región oeste         |2         |
|División    |Directiva de división         |3         |
|Subsidiaria   |Directiva subsidiaria        |4         |

Si quitamos la directiva región oeste del grupo Región oeste, las asignaciones de directivas y las prioridades se actualizan de la siguiente manera.

|Nombre del grupo  |Nombre de la directiva  |Clasificación|
|---------|---------|---------|
|Ventas    |Directiva de ventas       | 1        |
|División    |Directiva de división         |2         |
|Subsidiaria   |Directiva subsidiaria        |3        |

En este ejemplo, quitamos la directiva de reunión de Teams de un grupo.

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

#### <a name="change-a-policy-assignment-for-a-group"></a>Cambiar una asignación de directiva para un grupo

> [!NOTE]
> El cmdlet [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) estará disponible próximamente. Mientras tanto, para cambiar una asignación de directiva de grupo, puede quitar la asignación de directiva actual del grupo y, después, agregar una nueva asignación de directiva.

Después de asignar una directiva a un grupo, puede usar el cmdlet [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) para cambiar la asignación de directivas de ese grupo de la siguiente manera:

- Cambiar la clasificación
- Cambiar la directiva de un tipo de directiva determinado
- Cambiar la directiva de un tipo de directiva determinado y la clasificación

En este ejemplo, cambiamos la directiva de parque de llamadas de Teams de un grupo a una directiva denominada SupportCallPark y la clasificación de tareas a 3.

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a>Cambiar la directiva eficaz para un usuario

Este es un ejemplo de cómo cambiar la directiva eficaz para un usuario al que se le asigna directamente una directiva.

En primer lugar, usamos el cmdlet [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) junto con el parámetro para obtener detalles de las directivas de difusión de reuniones de ```PolicySource``` Teams asociadas con el usuario.

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

El resultado muestra que al usuario se le asignó directamente una directiva de difusión de reunión de Teams denominada Eventos de empleado, que tiene prioridad sobre la directiva denominada Eventos en directo de proveedor asignada a un grupo al que pertenece el usuario.

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

Ahora, quitamos la directiva Eventos de empleado del usuario. Esto significa que el usuario ya no tiene asignada una directiva de difusión de reunión de Teams directamente y heredará la directiva Eventos en directo del proveedor asignada al grupo al que pertenece el usuario.

Use el siguiente cmdlet en el módulo PowerShell de Skype Empresarial para ello.

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

Use el cmdlet siguiente en el módulo de PowerShell de Teams para hacerlo a escala a través de una asignación de directiva por lotes, donde $users es una lista de usuarios que especifique.

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a>Asignar una directiva a un lote de usuarios

### <a name="use-the-admin-center"></a>Usar el Centro de administración

Para asignar una directiva a los usuarios en masa:

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, seleccione **Usuarios.**
2. Busque los usuarios a los que desea asignar la directiva o filtre la vista para mostrar los usuarios que desee.
3. En la columna **&#x2713;** (marca de verificación), seleccione los usuarios. Para seleccionar todos los usuarios, haga clic en &#x2713; (marca de verificación) situado en la parte superior de la tabla.
4. Seleccione **Editar configuración,** realice los cambios que desee y, a continuación, **seleccione Aplicar**.

Para ver el estado de la asignación de directivas,  en el  banner que aparece en la parte superior de la página Usuarios después de seleccionar Aplicar para enviar la tarea de directiva, seleccione Registro **de actividades.** O bien, en la navegación izquierda del Centro de administración de Microsoft Teams, vaya a Panel **y,** a continuación, en Registro de **actividades,** seleccione **Ver detalles.** El registro de actividades muestra las asignaciones de directivas a lotes de más de 20 usuarios a través del Centro de administración de Microsoft Teams desde los últimos 30 días. Para obtener más información, vea [Ver las asignaciones de directivas en el registro de actividades.](activity-log.md)

### <a name="use-powershell-method"></a>Usar método de PowerShell

> [!NOTE]
> Actualmente, la asignación de directivas por lotes con PowerShell no está disponible para todos los tipos de directivas de Teams. Vea [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para obtener la lista de tipos de directiva admitidos.

Con la asignación de directivas por lotes, puede asignar una directiva a grandes conjuntos de usuarios a la vez sin tener que usar un script. Use el cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para enviar un lote de usuarios y la directiva que desea asignar. Las asignaciones se procesan como una operación de segundo plano y se genera un identificador de operación para cada lote. A continuación, puede usar el cmdlet [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) para realizar un seguimiento del progreso y el estado de las asignaciones en un lote.

Especifique los usuarios por su id. de objeto o dirección del Protocolo de inicio de sesión (SIP). La dirección SIP de un usuario suele tener el mismo valor que el nombre principal de usuario (UPN) o la dirección de correo electrónico, pero esto no es necesario. Si se especifica un usuario con su UPN o correo electrónico, pero tiene un valor diferente de su dirección SIP, la asignación de directivas no se realizará correctamente para el usuario. Si un lote incluye usuarios duplicados, los duplicados se quitarán del lote antes de procesar y el estado solo se proporciona para los usuarios únicos que permanecen en el lote.

Un lote puede contener hasta 5000 usuarios. Para obtener los mejores resultados, no envíe más de unos pocos lotes a la vez. Permitir que los lotes completen el procesamiento antes de enviar más lotes.

#### <a name="install-and-connect-to-the-teams-powershell-module"></a>Instalar y conectarse al módulo de PowerShell de Teams

Ejecute lo siguiente para instalar el módulo [PowerShell de Microsoft Teams.](https://www.powershellgallery.com/packages/MicrosoftTeams) Asegúrese de instalar la versión 1.0.5 o posterior.

```powershell
Install-Module -Name MicrosoftTeams
```

Ejecute lo siguiente para conectarse a Teams e iniciar una sesión.

```powershell
Connect-MicrosoftTeams
```

Cuando se le solicite, inicie sesión con sus credenciales de administrador.

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a>Instalar y conectarse al módulo Azure AD PowerShell para Graph (opcional)

Es posible que también quiera descargar e instalar el módulo [Azure AD PowerShell para Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (si aún no lo ha hecho) y conectarse a Azure AD para recuperar una lista de usuarios de su organización.

Ejecute lo siguiente para conectarse a Azure AD.

```powershell
Connect-AzureAD
```

Cuando se le solicite, inicie sesión con las mismas credenciales de administrador que usó para conectarse a Teams.

#### <a name="assign-a-setup-policy-to-a-batch-of-users"></a>Asignar una directiva de configuración a un lote de usuarios

En este ejemplo, usamos el cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para asignar una directiva de configuración de aplicaciones denominada Directiva de configuración de aplicaciones de HR a un lote de usuarios que aparecen en el archivo Users_ids.text.

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

En este ejemplo, nos conectamos a Azure AD para recuperar una colección de usuarios y, a continuación, asignamos una directiva de mensajería denominada Nueva directiva de mensajería de contratación a un lote de usuarios especificado mediante su dirección SIP.

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

#### <a name="get-the-status-of-a-batch-assignment"></a>Obtener el estado de una asignación por lotes

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
- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
- [Asignar directivas en Teams: introducción](policy-assignment-overview.md)
