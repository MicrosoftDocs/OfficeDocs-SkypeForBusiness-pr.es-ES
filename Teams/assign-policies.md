---
title: Asignar directivas a los usuarios de Microsoft Teams
author: lanachin
ms.author: v-lanac
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
description: Obtenga información sobre las diferentes formas de asignar directivas a los usuarios en Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 9d6253645e674d680f86d0b6f89a62968e6c21ba
ms.sourcegitcommit: dc3e8ae454c42981f037f4de2e48005428b6078e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/31/2020
ms.locfileid: "46533947"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a>Asignar directivas a los usuarios de Microsoft Teams

Como administrador, use directivas para controlar las características de teams que están disponibles para los usuarios de su organización. Por ejemplo, hay directivas de llamadas, directivas de reunión y directivas de mensajería, por citar algunas.

Las organizaciones tienen diferentes tipos de usuarios con necesidades exclusivas y directivas personalizadas que usted crea y asigna le permiten adaptar la configuración de directivas a distintos conjuntos de usuarios según esas necesidades.

Para facilitar la administración de directivas de su organización, Teams ofrece varias formas de asignar directivas a los usuarios. Puede asignar una directiva directamente a los usuarios, ya sea de forma individual o a escala a través de una asignación por lotes, o a un grupo del que son miembros los usuarios. También puede usar paquetes de directivas para asignar una colección preconfigurada de directivas a los usuarios de su organización que tengan roles similares. La opción que elija dependerá del número de directivas que esté administrando y del número de usuarios a los que va a asignar. Al configurar las directivas globales (predeterminada para toda la organización) de modo que se apliquen al mayor número de usuarios de su organización, solo tiene que asignar directivas a aquellos usuarios que requieran directivas especializadas.

En este artículo se describen las diferentes maneras en las que puede asignar directivas a los usuarios y las situaciones recomendadas para Cuándo usarlas.

## <a name="which-policy-takes-precedence"></a>¿Qué directiva tiene prioridad?

Un usuario tiene una directiva vigente para cada tipo de directiva. Es posible o incluso probable que un usuario tenga asignada directamente una directiva y también es miembro de uno o más grupos a los que se ha asignado una directiva del mismo tipo. En estos tipos de escenarios, ¿qué directiva tiene prioridad?  La Directiva efectiva del usuario se determina según las reglas de prioridad, de la siguiente manera.

Si un usuario tiene asignada directamente una directiva (ya sea de forma individual o mediante una asignación por lotes), tiene prioridad. En el ejemplo siguiente, la Directiva efectiva del usuario es la Lincoln cuadrada de la reunión, que se asigna directamente al usuario.

![Diagrama que muestra cómo tiene prioridad una directiva asignada directamente](media/assign-policies-example-directly-assigned.png)

Si un usuario no tiene asignada directamente una directiva de un tipo determinado, tendrá prioridad la directiva asignada a un grupo al que pertenece el usuario. Si un usuario es miembro de varios grupos, tiene prioridad la Directiva que tiene la mayor [clasificación de asignación de grupo](#group-assignment-ranking) para el tipo de directiva determinado.

En este ejemplo, la Directiva efectiva del usuario es el equipo de ejecución y la Directiva de alta definición, que tiene la mayor clasificación de asignación relativa a otros grupos de los que el usuario es miembro y al que también se les ha asignado una directiva del mismo tipo de directiva.  

![Diagrama que muestra cómo tiene prioridad una directiva heredada del grupo](media/assign-policies-example-group.png)

Si un usuario no tiene asignada directamente una directiva o no es miembro de ningún grupo al que se le haya asignado una directiva, el usuario recibirá la directiva global (opción predeterminada para toda la organización) para ese tipo de directiva. Este es un ejemplo.

![Diagrama que muestra cómo tiene prioridad una directiva global](media/assign-policies-example-global.png)

Para obtener más información, vea [reglas de prioridad](#precedence-rules).

## <a name="ways-to-assign-policies"></a>Formas de asignar directivas

A continuación se ofrece una descripción general de las formas en que puede asignar directivas a los usuarios y los escenarios recomendados para cada uno. Haga clic en los vínculos para obtener más información.

Antes de asignar directivas a usuarios individuales o grupos, primero [establezca las directivas globales (valor predeterminado de organización)](#set-the-global-policies) para que se apliquen al mayor número de usuarios de su organización.  Una vez configuradas las directivas globales, solo tendrá que asignar directivas a aquellos usuarios que requieran directivas especializadas.

|Haga lo siguiente  |Si...  | Usar...
|---------|---------|----|
|[Asignar una directiva a usuarios individuales](#assign-a-policy-to-individual-users)    | Ya está familiarizado con Teams y solo necesita asignar una o dos directivas a un pequeño número de usuarios. |El centro de administración de Microsoft Teams o los cmdlets de PowerShell en el módulo de PowerShell de Skype empresarial online
| [Asignar un paquete de directivas](#assign-a-policy-package)   | Debe asignar varias directivas a conjuntos específicos de usuarios de su organización que tengan roles iguales o similares. Por ejemplo, asigne el paquete de directivas Educación (profesor) a los profesores de su escuela para proporcionarles acceso completo a chats, llamadas y reuniones, y al paquete de directivas Educación (estudiante secundario escolar) a los estudiantes secundarios para limitar ciertas funciones como las llamadas privadas.  |El centro de administración de Microsoft Teams o los cmdlets de PowerShell en el módulo de PowerShell de Teams|
|[Asignar una directiva a un lote de usuarios](#assign-a-policy-to-a-batch-of-users)   | Debe asignar directivas a grandes conjuntos de usuarios. Por ejemplo, desea asignar una directiva a cientos o miles de usuarios de su organización al mismo tiempo.  |El centro de administración de Microsoft Teams o los cmdlets de PowerShell en el módulo de PowerShell de Teams|
|[Asignar una directiva a un grupo](#assign-a-policy-to-a-group) |Debe asignar directivas en función de la pertenencia a grupos de un usuario. Por ejemplo, desea asignar una directiva a todos los usuarios de un grupo de seguridad o de una lista de distribución.| El centro de administración de Microsoft Teams o los cmdlets de PowerShell en el módulo de PowerShell de Teams|
| [Asignar un paquete de directivas a un lote de usuarios](#assign-a-policy-package-to-a-batch-of-users)|Debe asignar varias directivas a un lote de usuarios de su organización que tengan roles iguales o similares. Por ejemplo, asigne el paquete de directivas Educación (profesor) a todos los profesores de su escuela mediante la asignación por lotes para proporcionarles acceso total a chats, llamadas y reuniones, y asigne el paquete de directivas Educación (estudiante secundario) a un lote de estudiantes secundarios para limitar ciertas capacidades como las llamadas privadas.|Cmdlets de PowerShell en el módulo de PowerShell de Teams|
| Asignar un paquete de directivas a un grupo (próximamente)   | ||

## <a name="set-the-global-policies"></a>Establecer las directivas globales

Siga estos pasos para establecer las directivas globales (valor predeterminado de la organización) para cada tipo de directiva.

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el centro de administración de Microsoft Teams

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a la página de directivas del tipo de directiva que desea actualizar. Por ejemplo, **Teams**  >  **Policies**, directivas de reuniones de **reuniones**  >  **Meetings policies**, **directivas de mensajería**o directivas de llamadas de **voz**  >  **Calling policies**.
2. Seleccione la directiva **global (opción predeterminada para toda la organización)** para ver la configuración actual.
3. Actualice la Directiva según sea necesario y, a continuación, seleccione **aplicar**.

### <a name="using-powershell"></a>Con PowerShell

Para establecer las directivas globales mediante PowerShell, use el identificador global.  Para empezar, revisamos la directiva global actual para determinar qué configuración desea cambiar.

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

A continuación, actualice la directiva global según sea necesario.  Solo tiene que especificar los valores de la configuración que quiere cambiar. 
 
```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="assign-a-policy-to-individual-users"></a>Asignar una directiva a usuarios individuales

Siga estos pasos para asignar una directiva a un usuario individual o a un número reducido de usuarios a la vez.

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el centro de administración de Microsoft Teams

Para asignar una directiva a un usuario:

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Usuarios** y, después, haga clic en el usuario.
2. Para seleccionar el usuario, haga clic a la izquierda del nombre de usuario y, después, en **Editar configuración**.
3. Seleccione la Directiva que desea asignar y, a continuación, haga clic en **aplicar**.

También puede hacer lo siguiente:

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a la página de la Directiva.
2. Seleccione la Directiva que desea asignar haciendo clic a la izquierda del nombre de la Directiva.
3. Seleccione **Administrar usuarios**.
4. En el panel **Administrar usuarios**, busque el usuario por su nombre para mostrar o por su nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**. Repita este paso por cada usuario que quiera agregar.
5. Cuando haya terminado de agregar usuarios, seleccione **aplicar**.

### <a name="using-powershell"></a>Con PowerShell

Cada tipo de directiva tiene su propio conjunto de cmdlets para administrarlo. Use el ```Grant-``` cmdlet para un tipo de directiva determinado para asignar la Directiva. Por ejemplo, use el ```Grant-CsTeamsMeetingPolicy``` cmdlet para asignar una política de reunión de Teams a los usuarios. Estos cmdlets están incluidos en el módulo de PowerShell de Skype empresarial online y están documentados en la [Referencia del cmdlet de Skype empresarial](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).

 Descargue e instale el [módulo de PowerShell de Skype empresarial online](https://www.microsoft.com/en-us/download/details.aspx?id=39366) (si todavía no lo ha hecho) y, a continuación, ejecute lo siguiente para conectarse a Skype empresarial online e iniciar una sesión.

```powershell
Import-Module SkypeOnlineConnector
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

En este ejemplo, asignamos una directiva de reunión de Teams denominada Directiva de reunión de estudiantes a un usuario denominado Reda.

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

Para obtener más información, lea [Administración de directivas a través de PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).

## <a name="assign-a-policy-package"></a>Asignar un paquete de directivas

Un paquete de directivas de Teams es una colección de directivas y opciones de directiva predefinidas que puede asignar a los usuarios que tienen roles iguales o similares en su organización. Cada paquete de directivas está diseñado según un rol de usuario e incluye directivas predefinidas y opciones de directiva que admiten actividades típicas de ese rol. Algunos ejemplos de paquetes de directivas son el paquete educativo (profesor) y el paquete de salud (trabajador clínico).

Cuando se asigna un paquete de directivas a los usuarios, se crean las directivas del paquete y, después, se puede personalizar la configuración de cada Directiva del paquete para satisfacer las necesidades de los usuarios.

Para obtener más información sobre los paquetes de directivas, incluidas las instrucciones paso a paso sobre cómo asignarlos y administrarlos, consulte [administrar paquetes de directivas en Teams](manage-policy-packages.md).

## <a name="assign-a-policy-to-a-batch-of-users"></a>Asignar una directiva a un lote de usuarios

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el centro de administración de Microsoft Teams

Para asignar una directiva a usuarios en bloque:

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, seleccione **usuarios**.
2. Busque los usuarios a los que desea asignar la Directiva o filtre la vista para mostrar los usuarios que desea.
3. En la columna **&#x2713;** (marca de verificación), seleccione los usuarios. Para seleccionar todos los usuarios, haga clic en &#x2713; (marca de verificación) situado en la parte superior de la tabla.
4. Haga clic en **Editar configuración**, haga los cambios que desee y, a continuación, haga clic en **Aplicar**.

Para ver el estado de la asignación de Directiva, en la pancarta que aparece en la parte superior de la página **usuarios** después de hacer clic en **aplicar** para enviar la asignación de Directiva, haga clic en **registro de actividades**. O bien, en el panel de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **Panel**y, a continuación, en **registro de actividades**, haga clic en **Ver detalles**. En el registro de actividades se muestran asignaciones de directivas de los lotes de más de 20 usuarios a través del centro de administración de Microsoft Teams desde los últimos 30 días. Para obtener más información, vea [ver las asignaciones de directivas en el registro de actividades](activity-log.md).

### <a name="using-powershell"></a>Con PowerShell

> [!NOTE]
> Actualmente, la asignación de directivas por lotes con PowerShell no está disponible para todos los tipos de directivas de Teams. Vea [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para obtener la lista de tipos de directiva admitidos.
 
Con la asignación de directivas por lotes, puede asignar una directiva a grandes conjuntos de usuarios a la vez sin tener que usar un script. Use el ```New-CsBatchPolicyAssignmentOperation``` cmdlet para enviar un lote de usuarios y la Directiva que desea asignar. Las asignaciones se procesan como una operación en segundo plano y se genera un identificador de operación para cada lote. Después, puede usar el ```Get-CsBatchPolicyAssignmentOperation``` cmdlet para realizar un seguimiento del progreso y el estado de las asignaciones de un lote.

Puede especificar los usuarios por su identificador de objeto o dirección de protocolo de inicio de sesión (SIP). Tenga en cuenta que la dirección SIP de un usuario a menudo tiene el mismo valor que el nombre principal de usuario (UPN) o la dirección de correo electrónico, pero esto no es necesario. Si un usuario se especifica mediante su UPN o correo electrónico pero tiene un valor distinto del de su dirección SIP, se producirá un error en la asignación de directivas del usuario. Si un lote incluye usuarios duplicados, los duplicados se eliminarán del lote antes de su procesamiento y su estado solo se proporcionará para los usuarios únicos que quedan en el lote. 

Un lote puede contener hasta 5.000 usuarios. Para obtener los mejores resultados, no envíes más de unos pocos lotes a la vez. Permita que los lotes terminen de procesarse antes de enviar más lotes.

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Instalar y conectarse al módulo de PowerShell de Microsoft Teams

Ejecute lo siguiente para instalar el [Módulo Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams). Asegúrese de instalar la versión 1.0.5 o posterior.

```powershell
Install-Module -Name MicrosoftTeams
```

Ejecute lo siguiente para conectarse a teams e iniciar una sesión.

```powershell
Connect-MicrosoftTeams
```

Cuando se le solicite, inicie sesión con sus credenciales de administrador.

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a>Instalar y conectarse al módulo de Azure AD PowerShell for Graph (opcional)

Es posible que también desee [Descargar e instalar el módulo Azure ad PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (si todavía no lo ha hecho) y conectarse a Azure ad para poder recuperar una lista de usuarios de su organización.

Ejecute lo siguiente para conectarse a Azure AD.

```powershell
Connect-AzureAD
```

Cuando se le solicite, inicie sesión con las mismas credenciales de administrador que usó para conectarse a teams.

#### <a name="assign-a-policy-to-a-batch-of-users"></a>Asignar una directiva a un lote de usuarios

En este ejemplo, usamos el ```New-CsBatchPolicyAssignmentOperation``` cmdlet para asignar una directiva de configuración de aplicación denominada Directiva de configuración de la aplicación de RRHH a un lote de usuarios que aparece en el archivo Users_ids. Text.

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

En este ejemplo, se conectará a Azure AD para recuperar una colección de usuarios y, a continuación, asignar una directiva de mensajería llamada nueva Directiva de mensajería de contratación a un lote de usuarios especificado mediante su dirección SIP.

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

Para obtener más información, vea [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).

#### <a name="get-the-status-of-a-batch-assignment"></a>Obtener el estado de una asignación por lotes

Ejecute lo siguiente para obtener el estado de una asignación por lotes, donde OperationId es el identificador de la operación devuelto por el ```New-CsBatchPolicyAssignmentOperation``` cmdlet para un lote determinado.

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

Si el resultado muestra que se ha producido un error, ejecute lo siguiente para obtener más información sobre los errores, que están en la ```UserState``` propiedad.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

Para obtener más información, vea [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).

## <a name="assign-a-policy-to-a-group"></a>Asignar una directiva a un grupo

La asignación de directivas a grupos le permite asignar una directiva a un grupo de usuarios, como un grupo de seguridad o una lista de distribución. La asignación de Directiva se propaga a los miembros del grupo según las reglas de prioridad. A medida que se agregan o quitan miembros de un grupo, sus asignaciones de directivas heredadas se actualizan según corresponda.

La asignación de directivas a grupos se recomienda para grupos de hasta 50.000 usuarios, pero también funciona con grupos más grandes.

Al asignar la Directiva, se asigna inmediatamente al grupo. Sin embargo, ten en cuenta que la propagación de la asignación de directiva a miembros del grupo se realiza como una operación en segundo plano y puede llevar algún tiempo, según el tamaño del grupo. Lo mismo sucede cuando se elimina la asignación de una directiva de un grupo, o cuando se agregan miembros a un grupo o se quitan de él.

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a>Lo que debe saber sobre la asignación de directivas a grupos

Antes de empezar, es importante comprender las reglas de prioridad y la clasificación de asignación de grupo.

#### <a name="precedence-rules"></a>Reglas de prioridad

Para un tipo de directiva determinado, la Directiva efectiva del usuario se determina de acuerdo con lo siguiente:

- Una directiva que se asigna directamente a un usuario tiene prioridad sobre cualquier otra directiva del mismo tipo que esté asignada a un grupo. En otras palabras, si un usuario tiene asignada directamente una directiva de un tipo determinado, ese usuario no heredará una directiva del mismo tipo de un grupo. Esto también significa que si un usuario tiene una directiva de un determinado tipo que se le asignó directamente, tendrá que quitar esa Directiva del usuario antes de que pueda heredar una directiva del mismo tipo de un grupo.
- Si un usuario no tiene una directiva asignada directamente y es miembro de dos o más grupos y cada grupo tiene una directiva del mismo tipo que tiene asignada, el usuario hereda la Directiva de la asignación de grupo que tiene la clasificación más alta.
- Si un usuario no es miembro de ningún grupo al que se le ha asignado una directiva, la directiva global (opción predeterminada para toda la organización) para ese tipo de Directiva se aplica al usuario.

La Directiva efectiva de un usuario se actualiza de acuerdo con estas reglas cuando se agrega o se quita un usuario de un grupo al que se asigna una directiva, se elimina la asignación de una directiva de un grupo o se quita una directiva que se asigna directamente al usuario.

#### <a name="group-assignment-ranking"></a>Clasificación de asignación de grupo
 
Cuando se asigna una directiva a un grupo, se especifica una clasificación para la asignación de grupo. Se usa para determinar qué directiva debe heredar un usuario como su Directiva efectiva si el usuario es miembro de dos o más grupos y se le asigna una directiva del mismo tipo.

La clasificación de la asignación de grupo es relativa a otras asignaciones de grupo del mismo tipo. Por ejemplo, si va a asignar una directiva de llamadas a dos grupos, establezca la jerarquía de una asignación en 1 y la otra en 2, siendo 1 el ranking más alto. La clasificación de la asignación de grupo indica qué pertenencia de grupo es más importante o más relevante que otras pertenencias a grupos en relación con la herencia.
 
Por ejemplo, supongamos que tiene dos grupos, guarda empleados y administradores de la tienda. Ambos grupos tienen asignada una directiva de llamadas de equipo, almacenan empleados que llaman a la Directiva de llamadas y a los jefes de tienda, respectivamente. En el caso de un administrador de tienda que esté en ambos grupos, su rol como director es más relevante que su rol como empleado, por lo que la política de llamadas que se asigna al grupo de administradores de la tienda debería tener una clasificación más alta.

|Mesa |Nombre de directiva de llamadas de equipo  |Clasificación|
|---------|---------|---|
|Administradores de tienda   |Directiva de llamadas a administradores de tienda         |1|
|Almacenar empleados    |Almacenar la política de llamadas      |2|

Si no especifica una clasificación, la asignación de directiva recibe la clasificación más baja. 

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el centro de administración de Microsoft Teams

> [!NOTE]
> Por el momento, la asignación de directivas a grupos que usan el centro de administración de Microsoft Teams solo está disponible para la Directiva de llamadas de Teams, la Directiva de Parque de llamadas de Teams, la Directiva de Teams, la Directiva de eventos en vivo de Teams, la Directiva de reuniones Para otros tipos de directivas, use PowerShell.

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a la página tipo de directiva. Por ejemplo, vaya a **Meetings**  >  **las directivas de reunión**de reuniones.
2. Seleccione la pestaña **asignación de directiva de grupo** .
3. Seleccione **Agregar grupo**y, a continuación, en el panel **asignar Directiva a grupo** , haga lo siguiente:
    1. Busque y agregue el grupo al que desea asignar la Directiva.
    2. Establezca la clasificación de la asignación de grupo.
    3. Seleccione la Directiva que desea asignar. 
    4. Seleccione **aplicar**.

Para quitar una asignación de directiva de grupo, en la pestaña **asignación de directiva de grupo** de la página de Directiva, seleccione la asignación de grupo y, a continuación, seleccione **quitar**.

Para cambiar la jerarquía de una asignación de grupo, primero debe quitar la asignación de directiva de grupo. Después, siga los pasos anteriores para asignar la Directiva a un grupo.

### <a name="using-powershell"></a>Con PowerShell

> [!NOTE]
> Por el momento, la asignación de directivas a grupos con PowerShell no está disponible para todos los tipos de directivas de Teams. Vea [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) para obtener la lista de tipos de directiva admitidos.

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Instalar y conectarse al módulo de PowerShell de Microsoft Teams

Para obtener instrucciones paso a paso, consulte [instalar Teams PowerShell](teams-powershell-install.md).

#### <a name="assign-a-policy-to-a-group"></a>Asignar una directiva a un grupo

Use el ```New-CsGroupPolicyAssignment``` cmdlet para asignar una directiva a un grupo. Puede especificar un grupo mediante el identificador de objeto, la dirección SIP o la dirección de correo electrónico.

En este ejemplo, usamos el ```New-CsGroupPolicyAssignment``` cmdlet para asignar una directiva de reunión de Teams denominada Directiva de reunión de directores minoristas a un grupo con una clasificación de asignación de 1.

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

Para obtener más información, vea [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).

#### <a name="get-policy-assignments-for-a-group"></a>Obtener asignaciones de directivas para un grupo

Use el ```Get-CsGroupPolicyAssignment``` cmdlet para obtener todas las directivas asignadas a un grupo. Ten en cuenta que los grupos siempre aparecen en la lista por su identificador de grupo aunque su dirección SIP o dirección de correo electrónico se hayan usado para asignar la Directiva.

En este ejemplo, recuperamos todas las directivas asignadas a un grupo específico.

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

En este ejemplo, se devuelven todos los grupos que tienen asignada una directiva de reunión de Teams.

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

Para obtener más información, vea [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).

#### <a name="remove-a-policy-from-a-group"></a>Quitar una directiva de un grupo

Use el ```Remove-CsGroupPolicyAssignment``` cmdlet para quitar una directiva de un grupo. Al quitar una directiva de un grupo, se actualizan las prioridades de otras directivas del mismo tipo asignadas a ese grupo y con una clasificación menor. Por ejemplo, si quita una directiva que tiene una clasificación de 2, las directivas que tengan una jerarquía de 3 y 4 se actualizarán para reflejar su nueva clasificación. En las dos tablas siguientes se muestra este ejemplo.

A continuación se ofrece una lista de las asignaciones de directivas y las prioridades de una directiva de reunión de Teams.

|Nombre del grupo  |Nombre de la directiva  |Clasificación|
|---------|---------|---------|
|Ventas    |Política de ventas       | 1        |
|Región occidental     |Política de la región occidental         |2         |
|Departamentos    |Política de división         |3         |
|Secundaria   |Directiva subsidiaria        |4         |

Si quitamos la política de región occidental del grupo región oeste, las asignaciones y prioridades de directivas se actualizan de la siguiente manera.

|Nombre del grupo  |Nombre de la directiva  |Clasificación|
|---------|---------|---------|
|Ventas    |Política de ventas       | 1        |
|Departamentos    |Política de división         |2         |
|Secundaria   |Directiva subsidiaria        |3        |

En este ejemplo, quitamos la política de reuniones de Teams de un grupo.

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

Para obtener más información, consulte [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).

#### <a name="change-a-policy-assignment-for-a-group"></a>Cambiar una asignación de directiva para un grupo

> [!NOTE]
> El ```Set-CsGroupPolicyAssignment``` cmdlet estará disponible pronto. Mientras tanto, para cambiar una asignación de directiva de grupo, puede quitar la asignación de directiva actual del grupo y, a continuación, agregar una nueva asignación de directiva.

Después de asignar una directiva a un grupo, puede usar el ```Set-CsGroupPolicyAssignment``` cmdlet para cambiar la asignación de directivas del grupo de la siguiente manera:

- Cambiar la clasificación
- Cambiar la Directiva de un tipo de directiva determinado
- Cambiar la Directiva de un determinado tipo de directiva y la clasificación

En este ejemplo, cambiamos la Directiva de los equipos de un grupo a una directiva llamada SupportCallPark y la clasificación de asignación a 3.

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

Para obtener más información, consulte [set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).



#### <a name="change-the-effective-policy-for-a-user"></a>Cambiar la Directiva efectiva de un usuario

Este es un ejemplo de cómo cambiar la Directiva efectiva para un usuario que tiene asignada directamente una directiva.

En primer lugar, usamos el ```Get-CsUserPolicyAssignment``` cmdlet junto con el ```PolicySource``` parámetro para obtener detalles de los equipos de reunión de las directivas de difusión asociados con el usuario. Para obtener más información, vea [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

En la salida se muestra que al usuario se le asignó directamente una directiva de difusión de reunión de Teams denominada eventos de empleados, que tiene prioridad sobre la Directiva denominada eventos de proveedor que se asignan a un grupo al que pertenece el usuario.

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

Ahora, quitamos la Directiva de eventos de empleados del usuario. Esto significa que el usuario ya no tiene una directiva de difusión de reunión de equipos que se les asignó directamente y heredará la Directiva de eventos en vivo de proveedores que se asigna al grupo al que pertenece el usuario. 

Use el siguiente cmdlet en el módulo de PowerShell de Skype empresarial para hacerlo.

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

Puede usar el siguiente cmdlet en el módulo de PowerShell de Teams para hacerlo a escala mediante una asignación de Directiva por lotes, donde $users es una lista de los usuarios que especifique.

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a>Asignar un paquete de directivas a un lote de usuarios

Con la asignación de paquetes de directivas por lotes, puede asignar un paquete de directivas a grandes conjuntos de usuarios a la vez sin tener que usar un script. Use el ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet para enviar un lote de usuarios y el paquete de directivas que desea asignar. Las asignaciones se procesan como una operación en segundo plano y se genera un identificador de operación para cada lote. Después, puede usar el ```Get-CsBatchPolicyAssignmentOperation``` cmdlet para realizar un seguimiento del progreso y el estado de las asignaciones de un lote.

Puede especificar los usuarios por su identificador de objeto o dirección de protocolo de inicio de sesión (SIP). Tenga en cuenta que la dirección SIP de un usuario a menudo tiene el mismo valor que el nombre principal de usuario (UPN) o la dirección de correo electrónico, pero esto no es necesario. Si un usuario se especifica mediante su UPN o correo electrónico pero tiene un valor distinto del de su dirección SIP, se producirá un error en la asignación de directivas del usuario. Si un lote incluye usuarios duplicados, los duplicados se eliminarán del lote antes de su procesamiento y su estado solo se proporcionará para los usuarios únicos que quedan en el lote. 

Un lote puede contener hasta 5.000 usuarios. Para obtener los mejores resultados, no envíes más de unos pocos lotes a la vez. Permita que los lotes terminen de procesarse antes de enviar más lotes.

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Instalar y conectarse al módulo de PowerShell de Microsoft Teams

Ejecute lo siguiente para instalar el [Módulo Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (si todavía no lo ha hecho). Asegúrese de instalar la versión 1.0.5 o posterior.

```powershell
Install-Module -Name MicrosoftTeams
```

Ejecute lo siguiente para conectarse a teams e iniciar una sesión.

```powershell
Connect-MicrosoftTeams
```

Cuando se le solicite, inicie sesión con sus credenciales de administrador.

### <a name="assign-a-policy-package-to-a-batch-of-users"></a>Asignar un paquete de directivas a un lote de usuarios

En este ejemplo, usamos el ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet para asignar el paquete de directivas Education_PrimaryStudent a un lote de usuarios.

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

Para obtener más información, vea [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).

### <a name="get-the-status-of-a-batch-assignment"></a>Obtener el estado de una asignación por lotes

Ejecute lo siguiente para obtener el estado de una asignación por lotes, donde OperationId es el identificador de la operación devuelto por el ```New-CsBatchPolicyAssignmentOperation``` cmdlet para un lote determinado.

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

Si el resultado muestra que se ha producido un error, ejecute lo siguiente para obtener más información sobre los errores, que están en la ```UserState``` propiedad.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

Para obtener más información, vea [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation). 

## <a name="related-topics"></a>Temas relacionados

[Descripción de PowerShell para Teams](teams-powershell-overview.md)
