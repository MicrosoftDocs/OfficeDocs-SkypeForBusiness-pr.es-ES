---
title: Asignar directivas a los usuarios de Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: tomkau, saragava, ritikag, jastark
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
description: Aprenda las distintas maneras de asignar directivas a los usuarios en Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 3a788ff2712c065d0273d4dfb6233f03e2272337
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196299"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a>Asignar directivas a los usuarios de Microsoft Teams

Como administrador, debe usar directivas para controlar las características de Teams que están disponibles para los usuarios de su organización. Por ejemplo, hay directivas de llamadas, directivas de reuniones y directivas de mensajería, por nombrar tan solo algunas.

Las organizaciones tienen diferentes tipos de usuarios con necesidades únicas. Las directivas personalizadas que cree y asigne le permitirán adaptar la configuración de directiva a diferentes conjuntos de usuarios en función de esas necesidades.

Para administrar fácilmente las directivas de su organización, Teams ofrece varias maneras de asignar directivas a los usuarios. Asigne una directiva directamente a los usuarios, ya sea de forma individual o a escala a través de una asignación por lotes, o a un grupo al que los usuarios sean miembros. También puedes usar paquetes de directivas para asignar una colección predefinida de directivas a los usuarios de tu organización que tengan roles similares. La opción que elija dependerá del número de directivas que administra y del número de usuarios a los que asigne las directivas. Las directivas globales (predeterminadas para toda la organización) se aplican al mayor número de usuarios de su organización. Solo tiene que asignar directivas a los usuarios que requieran directivas especializadas.

En este artículo se describen las diferentes maneras en que puede asignar directivas a los usuarios y los escenarios recomendados para cuándo usar cada uno.

## <a name="which-policy-takes-precedence"></a>¿Qué directiva tiene prioridad?

Un usuario tiene una directiva eficaz para cada tipo de directiva. Es posible, o incluso probable, que se haya asignado directamente una directiva a un usuario y que también sea miembro de uno o más grupos a los que se haya asignado una directiva del mismo tipo. En estos tipos de escenarios, ¿qué directiva tiene prioridad? La directiva eficaz de un usuario se determina según las reglas de prioridad, como se muestra a continuación.

Si a un usuario se le asigna directamente una directiva (ya sea de forma individual o a través de una asignación por lotes), esa directiva tiene prioridad. En el siguiente ejemplo visual, la directiva eficaz del usuario es la directiva de reunión de Square Square, que se asigna directamente al usuario.

![Diagrama que muestra cómo una directiva asignada directamente tiene prioridad](media/assign-policies-example-directly-assigned.png)

Si a un usuario no se le asigna directamente una directiva de un tipo determinado, la directiva asignada a un grupo del que el usuario es miembro tiene prioridad. Si un usuario es miembro de varios grupos, [](#group-assignment-ranking) la directiva que tenga la clasificación de asignación de grupo más alta para el tipo de directiva determinado tendrá prioridad.

En este ejemplo visual, la directiva eficaz del usuario es la directiva Exec Teams y HD, que tiene la clasificación más alta en asignaciones con respecto a otros grupos a los que el usuario es miembro y a los que también se les asigna una directiva del mismo tipo de directiva.  

![Diagrama que muestra cómo una directiva heredada de un grupo tiene prioridad](media/assign-policies-example-group.png)

Si un usuario no tiene asignada directamente una directiva o no es miembro de ningún grupo al que se le haya asignado una directiva, el usuario obtiene la directiva global (predeterminada para toda la organización) para ese tipo de directiva. Este es un ejemplo visual.

![Diagrama que muestra cómo tiene prioridad una directiva global](media/assign-policies-example-global.png)

Para obtener más información, vea [Reglas de prioridad.](#precedence-rules)

## <a name="ways-to-assign-policies"></a>Formas de asignar directivas

Aquí tiene información general sobre las formas en que puede asignar directivas a los usuarios y los escenarios recomendados para cada uno de ellos. Seleccione los vínculos para obtener más información.

Antes de asignar directivas a usuarios o grupos individuales, empiece por establecer las directivas globales (predeterminadas para toda la [organización)](#set-the-global-policies) para que se apliquen al mayor número de usuarios de su organización.  Una vez establecidas las directivas globales, solo tendrá que asignar directivas a los usuarios que requieran directivas especializadas.

|Haga lo siguiente  |Si...  | Usando...
|---------|---------|----|
|[Asignar una directiva a usuarios individuales](#assign-a-policy-to-individual-users)    | Es nuevo en Teams y acaba de empezar o solo necesita asignar una o un par de directivas a un número reducido de usuarios. |El Centro de administración de Microsoft Teams o los cmdlets de PowerShell en el módulo PowerShell de Skype Empresarial Online
|[Asignar una directiva a un grupo](#assign-a-policy-to-a-group) |Asigne directivas basadas en la pertenencia a grupos de un usuario. Por ejemplo, asigne una directiva a todos los usuarios de un grupo de seguridad o una lista de distribución.| El Centro de administración de Microsoft Teams o los cmdlets de PowerShell en el módulo PowerShell de Teams|
|[Asignar una directiva a un lote de usuarios](#assign-a-policy-to-a-batch-of-users)   | Asigne directivas a grandes conjuntos de usuarios. Por ejemplo, asigne una directiva a cientos o miles de usuarios de su organización a la vez. |El Centro de administración de Microsoft Teams o los cmdlets de PowerShell en el módulo PowerShell de Teams|
| [Asignar un paquete de directiva a los usuarios](#assign-a-policy-package-to-users)  |Asigne varias directivas a conjuntos específicos de usuarios de su organización que tienen el mismo rol o uno similar. Por ejemplo, asigne el paquete de directivas de Educación (para profesores) a los profesores de su centro educativo para darles acceso total a chats, llamadas y reuniones. Asigne el paquete de directivas de Educación (estudiante de secundaria) a los alumnos secundarios para limitar algunas funciones, como las llamadas privadas.  |El Centro de administración de Microsoft Teams o los cmdlets de PowerShell en el módulo PowerShell de Teams|
| [Asignar un paquete de directiva a un grupo](#assign-a-policy-package-to-a-group) (en versión preliminar privada)   |Asigne varias directivas a un grupo de usuarios de la organización que tienen el mismo rol o uno similar. Por ejemplo, asigne un paquete de directiva a todos los usuarios de un grupo de seguridad o una lista de distribución. |El Centro de administración de Microsoft Teams (próximamente) o los cmdlets de PowerShell en el módulo PowerShell de Teams|
| [Asignar un paquete de directiva a un lote de usuarios](#assign-a-policy-package-to-a-batch-of-users)|Asigne varias directivas a un lote de usuarios de su organización que tienen el mismo rol o uno similar. Por ejemplo, asigne el paquete de directivas de Educación (para profesores) a todos los profesores de su centro educativo mediante la asignación por lotes para darles acceso total a chats, llamadas y reuniones. Asigne el paquete de directivas de Educación (estudiante de secundaria) a un lote de estudiantes secundarios para limitar ciertas capacidades, como las llamadas privadas.|Cmdlets de PowerShell en el módulo de PowerShell de Teams|

## <a name="set-the-global-policies"></a>Establecer las directivas globales

Siga estos pasos para establecer las directivas globales (predeterminadas para toda la organización) para cada tipo de directiva.

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a la página de directiva del tipo de directiva que quiera actualizar. Por ejemplo, **directivas**  >  **de** Teams, **directivas de reuniones,** directivas de mensajería o  >  directivas **de** llamadas de   >  **voz.**
2. Seleccione la **directiva global (predeterminada para toda la organización)** para ver la configuración actual.
3. Actualice la directiva según sea necesario y, después, seleccione **Aplicar.**

### <a name="using-powershell"></a>Con PowerShell

Para establecer las directivas globales con PowerShell, use el identificador global.  Empiece revisando la directiva Global actual para determinar qué configuración desea cambiar.

```powershell
Get-CsTeamsMessagingPolicy -Identity Global
 
Identity                      : Global
Description                   :
AllowUrlPreviews              : True
AllowOwnerDeleteMessage       : False
AllowUserEditMessage          : True
AllowUserDeleteMessage        : True
AllowUserChat                 : True
AllowRemoveUser               : True
AllowGiphy                    : True
GiphyRatingType               : Moderate
AllowMemes                    : True
AllowImmersiveReader          : True
AllowStickers                 : True
AllowUserTranslation          : False
ReadReceiptsEnabledType       : UserPreference
AllowPriorityMessages         : True
ChannelsInChatListEnabledType : DisabledUserOverride
AudioMessageEnabledType       : ChatsAndChannels
Expand (20 lines) Collapse 
```

Después, actualice la directiva global según sea necesario.  Solo necesita especificar los valores de la configuración que desea cambiar.

```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="assign-a-policy-to-individual-users"></a>Asignar una directiva a usuarios individuales

Siga estos pasos para asignar una directiva a un usuario individual o a un número reducido de usuarios a la vez.

### <a name="use-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

Para asignar una directiva a un usuario:

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a Usuarios y, a continuación, seleccione el usuario.
2. Seleccione el usuario haciendo clic a la izquierda del nombre de usuario y, a continuación, seleccione **Editar configuración.**
3. Seleccione la directiva que desea asignar y, a continuación, seleccione **Aplicar.**

También puede hacer lo siguiente:

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a la página de directiva.
2. Seleccione la directiva que desea asignar haciendo clic a la izquierda del nombre de la directiva.
3. Seleccione **Administrar usuarios**.
4. En el panel **Administrar usuarios**, busque el usuario por su nombre para mostrar o por su nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**. Repita este paso por cada usuario que quiera agregar.
5. Cuando haya terminado de agregar usuarios, seleccione **Aplicar.**

### <a name="use-powershell"></a>Usar PowerShell

Cada tipo de directiva tiene su propio conjunto de cmdlets para administrarlo. Use el ```Grant-``` cmdlet de un tipo de directiva determinado para asignar la directiva. Por ejemplo, use el ```Grant-CsTeamsMeetingPolicy``` cmdlet para asignar una directiva de reuniones de Teams a los usuarios. Estos cmdlets se incluyen en el módulo de PowerShell de Skype Empresarial Online y se documentan en la referencia de [cmdlet de Skype Empresarial.](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

 Descargue e instale el módulo [De PowerShell](https://www.microsoft.com/download/details.aspx?id=39366) de Skype Empresarial Online (si aún no lo ha hecho) y, después, ejecute lo siguiente para conectarse a Skype Empresarial Online e iniciar una sesión.

> [!NOTE]
> Skype Empresarial Online Connector forma actualmente parte del módulo de PowerShell de Teams más reciente.
>
> Si usa la versión pública más reciente de PowerShell de [Teams,](https://www.powershellgallery.com/packages/MicrosoftTeams/)no es necesario instalar Skype Empresarial Online Connector.

```powershell
Import-Module -Name MicrosoftTeams
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

En este ejemplo, asignamos una directiva de reunión de Teams denominada Directiva de reunión de estudiante a un usuario llamado Reda.

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

Para obtener más información, lea [Administrar directivas a través de PowerShell.](teams-powershell-managing-teams.md#manage-policies-via-powershell)

## <a name="assign-a-policy-to-a-group"></a>Asignar una directiva a un grupo

La asignación de directivas a grupos le permite asignar una directiva a un grupo de usuarios, como un grupo de seguridad o una lista de distribución. La asignación de directiva se extiende a los miembros del grupo en función de las reglas de prioridad. A medida que se agregan o se eliminan miembros de un grupo, sus asignaciones de directivas heredadas se actualizan correspondientemente.

La asignación de directivas a grupos se recomienda para grupos de hasta 50 000 usuarios, pero también funcionará con grupos más grandes.

Al asignar la directiva, se asigna inmediatamente al grupo. Sin embargo, la propagación de la asignación de directiva a los miembros del grupo se realiza como una operación en segundo plano y puede tardar algún tiempo, dependiendo del tamaño del grupo. Ocurre lo mismo cuando se quita una directiva de un grupo o cuando se agregan miembros a un grupo o se quitan de él.

Las asignaciones de directivas de grupo solo se propagan a los usuarios que son miembros directos del grupo. Las asignaciones no se propagan a miembros de grupos anidados.

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a>Lo que debe saber sobre la asignación de directivas a grupos

Antes de empezar, es importante comprender las reglas de prioridad y la clasificación de las asignaciones de grupo.

#### <a name="precedence-rules"></a>Reglas de prioridad

Para un tipo de directiva determinado, la directiva eficaz de un usuario se determina según lo siguiente:

- Una directiva que se asigna directamente a un usuario tiene prioridad sobre cualquier otra directiva del mismo tipo que se asigne a un grupo. Es decir, si se asigna directamente a un usuario una directiva de un tipo determinado, dicho usuario no heredará de un grupo una directiva del mismo tipo. Esto también significa que, si un usuario tiene una directiva de un tipo determinado que se le asignó directamente, tendrá que quitar esa directiva del usuario antes de que pueda heredar una directiva del mismo tipo de un grupo.
- Si un usuario no tiene una directiva asignada directamente y es miembro de dos o más grupos y cada grupo tiene asignada una directiva del mismo tipo, el usuario hereda la directiva de la asignación de grupo que tenga la clasificación más alta.
- Si un usuario no es miembro de ningún grupo al que se le haya asignado una directiva, la directiva global (predeterminada para toda la organización) para ese tipo de directiva se aplica al usuario.

La directiva eficaz de un usuario se actualiza de acuerdo con estas reglas:

- cuando se agrega o quita un usuario de un grupo al que se ha asignado una directiva.
- una directiva no se ha desasignado a un grupo.
- Se quitará una directiva que esté asignada directamente al usuario.

#### <a name="group-assignment-ranking"></a>Clasificación de tareas de grupo

Al asignar una directiva a un grupo, se especifica una clasificación para la asignación del grupo. Esto se usa para determinar qué directiva debe heredar un usuario como su directiva eficaz si el usuario es miembro de dos o más grupos y a cada grupo se le asigna una directiva del mismo tipo.

La clasificación de las asignaciones de grupo es relativa a otras asignaciones de grupo del mismo tipo. Por ejemplo, si va a asignar una directiva de llamada a dos grupos, establezca la clasificación de una asignación en 1 y la otra en 2, siendo 1 la clasificación más alta. La clasificación de asignaciones de grupo indica qué pertenencia de grupo es más importante o más relevante que otras pertenencias a grupos en lo que respecta a la herencia.

Por ejemplo, tiene dos grupos: Empleados de store y Administradores de store. A ambos grupos se les asigna una directiva de llamadas de Teams, una directiva de llamadas de empleados de Store y una directiva de llamadas de administradores de store, respectivamente. Para un administrador de store que se encuentra en ambos grupos, su rol como administrador es más relevante que su rol como empleado, por lo que la directiva de llamadas que se asigna al grupo Administradores de store debe tener un nivel más alto.

|Grupo |Nombre de directiva de llamada de Teams  |Clasificación|
|---------|---------|---|
|Administradores de store   |Directiva de llamadas de administradores de store         |1|
|Empleados de Store    |Directiva de llamadas de empleados de Store      |2|

Si no especifica una clasificación, se asigna la asignación de directiva a la clasificación más baja.

### <a name="in-the-teams-admin-center"></a>En el Centro de administración de Teams

> [!NOTE]
> Actualmente, la asignación de directivas a grupos mediante el Centro de administración de Microsoft Teams solo está disponible para la directiva de llamadas de Teams, la directiva de parque de llamadas de Teams, la directiva de teams, la directiva de eventos en directo de Teams, la directiva de reuniones de Teams y la directiva de mensajería de Teams. Para otros tipos de directiva, use PowerShell.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a la página de tipo de directiva. Por ejemplo, vaya a **Directivas de**  >  **reuniones.**
2. Seleccione la pestaña **Asignación de directiva de** grupo.
3. Seleccione **Agregar grupo y,** a continuación, en el panel Asignar **directiva** a grupo, haga lo siguiente:
    1. Busque y agregue el grupo al que desea asignar la directiva.
    2. Establezca la clasificación de la asignación de grupo.
    3. Seleccione la directiva que desea asignar.
    4. Seleccione **Aplicar.**

Para quitar una asignación de directiva de grupo, en la **pestaña Asignación** de directiva de grupo de la página de directiva, seleccione la asignación de grupo y, a continuación, **seleccione Quitar.**

Para cambiar la clasificación de una asignación de grupo, primero tiene que quitar la asignación de directiva de grupo. A continuación, siga los pasos anteriores para asignar la directiva a un grupo.

### <a name="use-the-powershell-option"></a>Usar la opción de PowerShell

> [!NOTE]
> Actualmente, la asignación de directivas a grupos con PowerShell no está disponible para todos los tipos de directiva de Teams. Vea [New-CsGroupPolicyAssignment para](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) obtener una lista de los tipos de directiva admitidos.

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Instalar y conectarse al módulo De PowerShell de Microsoft Teams

Para obtener instrucciones paso a paso, vea [Instalar Teams powerShell.](teams-powershell-install.md)

#### <a name="assign-a-policy-to-a-group-of-users"></a>Asignar una directiva a un grupo de usuarios

Use el [cmdlet New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) para asignar una directiva a un grupo. Puede especificar un grupo mediante el id. de objeto, la dirección SIP o la dirección de correo electrónico.

En este ejemplo, asignamos una directiva de reunión de Teams denominada Directiva de reunión de directores comerciales a un grupo con una clasificación de asignación de 1.

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a>Obtener asignaciones de directivas para un grupo

Use el [cmdlet Get-CsGroupPolicyAssignment para](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment) obtener todas las directivas asignadas a un grupo. Tenga en cuenta que los grupos siempre aparecen en la lista por su id. de grupo incluso si se usó su dirección sip o dirección de correo electrónico para asignar la directiva.

En este ejemplo, recuperamos todas las directivas asignadas a un grupo específico.

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

En este ejemplo, se devuelven todos los grupos que tienen asignada una directiva de reunión de Teams.

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a>Quitar una directiva de un grupo

Use el [cmdlet Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment) para quitar una directiva de un grupo. Al quitar una directiva de un grupo, se actualizan las prioridades de otras directivas del mismo tipo asignadas a ese grupo, que tienen una clasificación inferior. Por ejemplo, si quita una directiva que tiene una clasificación de 2, las directivas que tienen una clasificación de 3 y 4 se actualizan para reflejar la nueva clasificación. En las dos tablas siguientes se muestra este ejemplo.

Esta es una lista de las asignaciones de directiva y prioridades para una directiva de reunión de Teams.

|Nombre del grupo  |Nombre de la directiva  |Clasificación|
|---------|---------|---------|
|Ventas    |Directiva de ventas       | 1        |
|Región Oeste     |Directiva de región Oeste         |2         |
|División    |Directiva de división         |3         |
|Subsidiaria   |Directiva subsidiaria        |4         |

Si quitamos la directiva de la Región Oeste del grupo Región Oeste, las asignaciones y prioridades de la directiva se actualizan de la siguiente manera.

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
> El [cmdlet Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) estará disponible próximamente. Mientras tanto, para cambiar una asignación de directiva de grupo, puede quitar la asignación de directiva actual del grupo y luego agregar una nueva asignación de directiva.

Después de asignar una directiva a un grupo, puede usar el cmdlet [Set-CsGroupPolicyAssignment para](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cambiar la asignación de directivas de ese grupo de la siguiente manera:

- Cambiar la clasificación
- Cambiar la directiva de un tipo de directiva determinado
- Cambiar la directiva de un tipo de directiva determinado y la clasificación

En este ejemplo, cambiamos la directiva de parque de llamadas de Teams de un grupo a una directiva denominada SupportCallPark y la clasificación de asignaciones a 3.

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a>Cambiar la directiva eficaz para un usuario

Este es un ejemplo de cómo cambiar la directiva eficaz para un usuario al que se le asigna directamente una directiva.

En primer lugar, usamos el cmdlet [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) junto con el parámetro para obtener detalles de las directivas de difusión de reunión de Teams asociadas ```PolicySource``` con el usuario.

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

El resultado muestra que al usuario se le asignó directamente una directiva de difusión de reunión de Teams denominada Eventos de empleado, que tiene prioridad sobre la directiva denominada Eventos en directo de proveedor que se asigna a un grupo al que pertenece el usuario.

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

Ahora, quitamos la directiva De eventos de empleado del usuario. Esto significa que el usuario ya no tiene una directiva de difusión de reunión de Teams asignada directamente y heredará la directiva de eventos en directo de proveedor que se asigna al grupo al que pertenece el usuario.

Use el siguiente cmdlet en el módulo de PowerShell de Skype Empresarial para hacerlo.

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

Use el cmdlet siguiente en el módulo de PowerShell de Teams para realizar esta tarea a escala a través de una asignación de directiva por lotes, donde $users es una lista de usuarios que especifique.

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a>Asignar una directiva a un lote de usuarios

### <a name="use-the-admin-center"></a>Usar el Centro de administración

Para asignar una directiva a los usuarios en masa:

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, seleccione **Usuarios.**
2. Busque los usuarios a los que desea asignar la directiva o filtre la vista para mostrar los usuarios que desea.
3. En la columna **&#x2713;** (marca de verificación), seleccione los usuarios. Para seleccionar todos los usuarios, haga clic en &#x2713; (marca de verificación) situado en la parte superior de la tabla.
4. Seleccione **Editar configuración,** realice los cambios que desee y, a continuación, **seleccione Aplicar.**

Para ver el estado de la asignación de directiva,  en el  banner que aparece en la parte superior de la página Usuarios después de seleccionar Aplicar para enviar la asignación de directiva, seleccione Registro **de actividades.** O bien, en el panel de navegación izquierdo del centro de administración de Microsoft Teams, vaya al panel **y,** a continuación, en registro de **actividades,** **seleccione Ver detalles.** El registro de actividades muestra las asignaciones de directivas a lotes de más de 20 usuarios a través del Centro de administración de Microsoft Teams de los últimos 30 días. Para obtener más información, [vea Ver las asignaciones de directivas en el registro de actividades.](activity-log.md)

### <a name="use-powershell-method"></a>Usar el método de PowerShell

> [!NOTE]
> Actualmente, la asignación de directivas por lotes con PowerShell no está disponible para todos los tipos de directiva de Teams. Vea [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para obtener la lista de los tipos de directiva admitidos.

Con la asignación de directivas por lotes, puede asignar una directiva a grandes conjuntos de usuarios a la vez sin tener que usar un script. Use el [cmdlet New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para enviar un lote de usuarios y la directiva que desea asignar. Las asignaciones se procesan como una operación de segundo plano y se genera un identificador de operación para cada lote. A continuación, puede usar el cmdlet [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) para realizar un seguimiento del progreso y el estado de las asignaciones en un lote.

Especifique los usuarios por su id. de objeto o la dirección SIP (Protocolo de inicio de sesión). La dirección SIP de un usuario suele tener el mismo valor que el nombre principal de usuario (UPN) o la dirección de correo electrónico, pero esto no es necesario. Si se especifica un usuario mediante un UPN o un correo electrónico, pero tiene un valor diferente a la dirección SIP, se producirá un error en la asignación de la directiva para el usuario. Si un lote incluye usuarios duplicados, los duplicados se quitarán del lote antes de procesar y el estado solo se proporciona para los usuarios únicos que permanecen en el lote.

Un lote puede contener hasta 5000 usuarios. Para obtener los mejores resultados, no envíe más de un par de lotes a la vez. Permitir que los lotes completen el procesamiento antes de enviar más lotes.

#### <a name="install-and-connect-to-the-teams-powershell-module"></a>Instalar y conectarse al módulo de PowerShell de Teams

Ejecute lo siguiente para instalar el módulo [De PowerShell de Microsoft Teams.](https://www.powershellgallery.com/packages/MicrosoftTeams) Asegúrese de instalar la versión 1.0.5 o posterior.

```powershell
Install-Module -Name MicrosoftTeams
```

Ejecute lo siguiente para conectarse a Teams e iniciar una sesión.

```powershell
Connect-MicrosoftTeams
```

Cuando se le solicite, inicie sesión con sus credenciales de administrador.

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a>Instalar y conectarse al módulo PowerShell de Azure AD para Graph (opcional)

Es posible que también desee descargar e instalar el módulo [PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) de Azure AD para Graph (si aún no lo ha hecho) y conectarse a Azure AD para recuperar una lista de usuarios de su organización.

Ejecute lo siguiente para conectarse a Azure AD.

```powershell
Connect-AzureAD
```

Cuando se le solicite, inicie sesión con las mismas credenciales de administrador que usó para conectarse a Teams.

#### <a name="assign-a-setup-policy-to-a-batch-of-users"></a>Asignar una directiva de configuración a un lote de usuarios

En este ejemplo, usamos el cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para asignar una directiva de configuración de la aplicación denominada Directiva de configuración de aplicaciones de RR. HUMANOS a un lote de usuarios enumerados en el archivo Users_ids.text.

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

En este ejemplo, conectamos a Azure AD para recuperar una colección de usuarios y, a continuación, asignamos una directiva de mensajería denominada Nueva directiva de mensajería de contratación a un lote de usuarios especificado con su dirección SIP.

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

Si en el resultado se muestra que se produjo un error, ejecute lo siguiente para obtener más información sobre los errores que se encuentran en la ```UserState``` propiedad.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

Para obtener más información, [vea Get-CsBatchPolicyAssignmentOperation.](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)

## <a name="assign-a-policy-package-to-users"></a>Asignar un paquete de directiva a los usuarios

Un paquete de directiva en Teams es una colección de directivas predefinidas y configuraciones de directiva que puede asignar a los usuarios que tienen el mismo rol o uno similar en su organización. Cada paquete de directiva está diseñado en torno a un rol de usuario e incluye directivas predefinidas y configuraciones de directiva que admiten actividades típicas para ese rol. Algunos ejemplos de paquetes de directiva son el paquete de educación (profesor) y el paquete de productos sanitarios (trabajador clínico). Para obtener más información, consulte [Administrar paquetes de directivas en Teams.](manage-policy-packages.md)

### <a name="assign-a-policy-package-to-one-user"></a>Asignar un paquete de directiva a un usuario

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a Usuarios y, a continuación, seleccione el usuario.
2. En la página del usuario, seleccione **Directivas y,** a continuación, junto **a Paquete de directiva,** seleccione **Editar.**
3. En el **panel Asignar paquete de** directivas, selecciona el paquete que quieres asignar y, a continuación, selecciona **Guardar.**

### <a name="assign-a-policy-package-to-multiple-users"></a>Asignar un paquete de directiva a varios usuarios

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a Paquetes de directiva y, a continuación, seleccione el paquete de directiva que desea asignar haciendo clic a la izquierda del nombre del paquete.
2. Seleccione **Administrar usuarios**.
3. En el panel **Administrar usuarios**, busque el usuario por su nombre para mostrar o por su nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**. Repita este paso por cada usuario que quiera agregar.
4. Cuando haya terminado de agregar usuarios, seleccione **Guardar.**

## <a name="assign-a-policy-package-to-a-group"></a>Asignar un paquete de directivas a un grupo

**Esta característica está en versión preliminar privada**

La opción de asignar un paquete de directiva a grupos le permite asignar múltiples directivas a un grupo de usuarios, como un grupo de seguridad o una lista de distribución. La asignación de directiva se extiende a los miembros del grupo en función de las reglas de prioridad. A medida que se agregan o se eliminan miembros de un grupo, sus asignaciones de directivas heredadas se actualizan correspondientemente.

Se recomienda la asignación de paquetes de directiva a grupos para grupos de hasta 50 000 usuarios, pero también funcionará con grupos más grandes.

Al asignar el paquete de directivas, se asigna inmediatamente al grupo. Sin embargo, la propagación de la asignación de directiva a los miembros del grupo se realiza como una operación en segundo plano y puede tardar algún tiempo, dependiendo del tamaño del grupo. Ocurre lo mismo cuando se quita una directiva de un grupo o cuando se agregan miembros a un grupo o se quitan de él.

> [!IMPORTANT]
> Antes de empezar, es importante [](#precedence-rules) comprender las reglas de prioridad y la clasificación [de asignaciones de grupo.](#group-assignment-ranking) Asegúrese de leer y comprender los conceptos de [lo que debe saber acerca](#what-you-need-to-know-about-policy-assignment-to-groups) de la asignación de directivas a grupos anteriormente en este artículo.

### <a name="assign-a-policy-package-to-a-group-of-users-in-the-admin-center"></a>Asignar un paquete de directivas a un grupo de usuarios en el centro de administración

1. Inicie sesión en el Centro de administración de Teams.
2. En el panel de navegación izquierdo, vaya a la página del paquete de directivas.
3. Seleccione la pestaña Asignación de directiva de grupo.
4. Seleccione **Agregar grupo** y, a continuación, en el panel Asignar un paquete de directiva al grupo, haga lo siguiente:

    a. Busca y agrega el grupo al que quieres asignar el paquete de directivas.

    b. Selecciona un paquete de directiva.

    c. Establezca la clasificación para cada tipo de directiva.

    d. Seleccione **Aplicar.**

    ![muestra la asignación de directiva de grupo](media/group-pkg-assignment.png)

5. Para administrar la clasificación de un tipo de directiva específico, vaya a la página de directiva específica.
6. Para reasignar un paquete de directivas a un grupo, primero quite la asignación de directiva de grupo. A continuación, siga los pasos anteriores para asignar el paquete de directiva a un grupo.

### <a name="work-with-powershell"></a>Trabajar con PowerShell

#### <a name="get-the-teams-powershell-module"></a>Obtener el módulo PowerShell de Teams

Para obtener instrucciones paso a paso, vea [Instalar Teams powerShell.](teams-powershell-install.md)

#### <a name="assign-a-policy-package-to-a-group-of-users"></a>Asignar un paquete de directiva a un grupo de usuarios

Use el [cmdlet Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) para asignar un paquete de directiva a un grupo. Puede especificar un grupo mediante el id. de objeto, la dirección SIP o la dirección de correo electrónico. Al asignar el paquete de directivas, especifique una clasificación [de asignación](#group-assignment-ranking) de grupo para cada tipo de directiva en el paquete de directivas.

En este ejemplo, asignamos el paquete de directivas de Education_Teacher a un grupo con una clasificación de asignación de 1 para TeamsAppSetupPolicy y TeamsMeetingBroadcastPolicy y un ranking de 2 para TeamsMeetingPolicy.

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a>Asignar un paquete de directiva a un lote de usuarios

Con la asignación de paquetes de directivas por lotes, puede asignar un paquete de directiva a grandes conjuntos de usuarios a la vez sin tener que usar un script. Use el [cmdlet New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para enviar un lote de usuarios y el paquete de directiva que desea asignar. Las asignaciones se procesan como una operación de segundo plano y se genera un identificador de operación para cada lote. A continuación, puede usar el cmdlet [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) para realizar un seguimiento del progreso y el estado de las asignaciones en un lote.

Especifique los usuarios por su id. de objeto o la dirección SIP (Protocolo de inicio de sesión). La dirección SIP de un usuario suele tener el mismo valor que el nombre principal de usuario (UPN) o la dirección de correo electrónico, pero esto no es necesario. Si se especifica un usuario mediante un UPN o un correo electrónico, pero tiene un valor diferente a la dirección SIP, se producirá un error en la asignación de la directiva para el usuario. Si un lote incluye usuarios duplicados, los duplicados se quitarán del lote antes de procesar y el estado solo se proporciona para los usuarios únicos que permanecen en el lote.

Un lote contiene hasta 5.000 usuarios. Para obtener los mejores resultados, no envíe más de un par de lotes a la vez. Permitir que los lotes completen el procesamiento antes de enviar más lotes.

### <a name="use-the-teams-powershell-module"></a>Usar el módulo PowerShell de Teams

Ejecute lo siguiente para instalar el módulo [De PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) de Microsoft Teams (si aún no lo ha hecho). Asegúrese de instalar la versión 1.0.5 o posterior.

```powershell
Install-Module -Name MicrosoftTeams
```

Ejecute lo siguiente para conectarse a Teams e iniciar una sesión.

```powershell
Connect-MicrosoftTeams
```

Cuando se le solicite, inicie sesión con sus credenciales de administrador.

### <a name="assign-policy-packages-to-a-batch-of-users"></a>Asignar paquetes de directiva a un lote de usuarios

En este ejemplo, usamos el cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para asignar el paquete de directiva Education_PrimaryStudent a un lote de usuarios.

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="see-the-status-of-a-batch-assignment"></a>Ver el estado de una asignación por lotes

Ejecute lo siguiente para obtener el estado de una asignación por lotes, donde OperationId es el id. de operación devuelto por el ```New-CsBatchPolicyAssignmentOperation``` cmdlet para un lote determinado.

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

Si en el resultado se muestra que se produjo un error, ejecute lo siguiente para obtener más información sobre los errores que se encuentran en la ```UserState``` propiedad.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

Para obtener más información, [vea Get-CsBatchPolicyAssignmentOperation.](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)

## <a name="related-topics"></a>Temas relacionados

[Descripción de PowerShell para Teams](teams-powershell-overview.md)
