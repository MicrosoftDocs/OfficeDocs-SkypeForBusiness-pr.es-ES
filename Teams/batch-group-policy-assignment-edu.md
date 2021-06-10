---
title: Asignar directivas a grandes conjuntos de usuarios de la escuela
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: karsmith, angch, cebulnes
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo asignar directivas a grandes conjuntos de usuarios de su institución educativa en función de la pertenencia a grupos o directamente a través de una asignación por lotes para fines educativos remotos (teleescuelas, teleescuelas).
f1keywords: ''
ms.openlocfilehash: f2d36db6a96f6a9a42590ada6600ef38738b30a9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092908"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a>Asignar directivas a grandes conjuntos de usuarios de la escuela

[!INCLUDE [policy-wizard-edu](includes/policy-wizard-edu.md)]

> [!NOTE]
> Para obtener más información sobre cómo asignar directivas en Microsoft Teams, vea Asignar directivas a [los usuarios en Teams](assign-policies.md).

## <a name="overview"></a>Información general

¿Necesita dar a sus alumnos y profesores acceso a diferentes características en Microsoft Teams? Puede identificar rápidamente los usuarios de su organización por tipo de licencia y, a continuación, asignarles la directiva adecuada. En este tutorial se muestra cómo asignar una directiva de reunión a grandes conjuntos de usuarios de su centro educativo. Puede asignar directivas con el centro Microsoft Teams administración y PowerShell y le mostraremos ambas formas.

Puede asignar una directiva de reunión a un grupo de seguridad del que los usuarios son miembros o directamente a los usuarios a escala a través de una asignación de directiva por lotes. Aprenderá a:

- **Use [la asignación de directivas](#assign-a-policy-to-a-group) a grupos para asignar una directiva de reunión a un grupo de seguridad (recomendado).** Este método le permite asignar una directiva basada en la pertenencia a grupos. Puede asignar una directiva a un grupo de seguridad o una lista de distribución. A medida que se agregan o quitan miembros del grupo, sus asignaciones de directivas heredadas se actualizan en consecuencia. Le recomendamos que use este método porque reduce el tiempo de administración de directivas para los nuevos usuarios o cuando cambian los roles de los usuarios. Este método funciona mejor para grupos de hasta 50 000 usuarios, pero también funcionará con grupos más grandes.

- **Use [la asignación de directivas por](assign-policies.md#assign-a-policy-to-a-batch-of-users) lotes para asignar una directiva de reunión directamente a los usuarios en masa.** Puede asignar una directiva para un máximo de 5.000 usuarios a la vez. Si tiene más de 5.000 usuarios, puede enviar varios lotes. Con este método, cuando tenga nuevos usuarios, tendrá que volver a ejecutar la asignación por lotes para asignar la directiva a esos nuevos usuarios.

Recuerde que en Teams, los usuarios obtienen automáticamente la directiva global (predeterminada para toda la organización) para un tipo de directiva Teams a menos que cree y asigne una directiva personalizada. Dado que la población de estudiantes suele ser el mayor conjunto de usuarios y a menudo reciben la configuración más restrictiva, le recomendamos que haga lo siguiente:

- Cree una directiva personalizada que permita funcionalidades básicas, como chat privado y programación de reuniones, y asigne la directiva a su personal y profesores.
- Asigne la directiva personalizada a su personal y profesores.
- Edite y aplique la directiva Global (predeterminada para toda la organización) para restringir las capacidades de los alumnos.

Tenga en cuenta que la directiva global se aplicará a todos los usuarios de su centro educativo hasta que cree una directiva personalizada y la asigne a su personal y profesores.

En este tutorial, los alumnos recibirán la directiva de reunión global y asignaremos una directiva de reunión personalizada denominada EducatorMeetingPolicy a docentes y docentes. Suponemos que ha editado la directiva global para adaptar la configuración de la reunión [a](policy-packages-edu.md) los alumnos y ha creado una directiva personalizada que define la experiencia de la reunión para el personal y los profesores.

![Captura de pantalla de la página Directivas de reunión en el Teams de administración](media/batch-group-policy-assignment-edu-meeting-policies.png)

## <a name="assign-a-policy-to-a-group"></a>Asignar una directiva a un grupo

Siga estos pasos para crear un grupo de seguridad para el personal y los profesores y, a continuación, asigne una directiva de reunión personalizada denominada EducatorMeetingPolicy a ese grupo de seguridad.

### <a name="before-you-get-started"></a>Antes de empezar

> [!IMPORTANT]
> Al asignar una directiva a un grupo, la asignación de directiva se propaga a los miembros del grupo según las reglas de prioridad. Por ejemplo, si a un usuario se le asigna directamente una directiva (ya sea individualmente o a través de una asignación por lotes), esa directiva tiene prioridad sobre una directiva heredada de un grupo. Esto también significa que si un usuario tiene una directiva de reunión que se le asignó directamente, tendrá que quitar esa directiva de reunión del usuario antes de que pueda heredar una directiva de reunión de un grupo de seguridad.

Antes de empezar, es importante comprender las reglas de [prioridad](assign-policies.md#precedence-rules) y la clasificación [de las asignaciones de grupo.](assign-policies.md#group-assignment-ranking) Asegúrese de leer y comprender los conceptos de Lo que necesita saber sobre la asignación de directivas **[a grupos.](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)**

Deberá completar todos estos pasos para que el personal y los profesores hereden una directiva de reunión de un grupo de seguridad.

1. [Crear grupos de seguridad](#create-security-groups).
2. [Asignar una directiva a un grupo de seguridad.](#assign-a-policy-to-a-security-group)
3. [Quitar una directiva que se asignó directamente a los usuarios.](#remove-a-policy-that-was-directly-assigned-to-users)

### <a name="create-security-groups"></a>Crear grupos de seguridad

En primer lugar, cree un grupo de seguridad para el personal y los profesores.

Con [School Data Sync](/SchoolDataSync/) (SDS), puede crear fácilmente grupos de seguridad [educadores y alumnos](/SchoolDataSync/edu-security-groups) de su escuela. Le recomendamos que use SDS para crear los grupos de seguridad que necesita para administrar las directivas de su centro educativo.

Si no puede implementar SDS en su entorno, use este script de [PowerShell](scripts/powershell-script-security-groups-edu.md) para crear dos grupos de seguridad, uno para todos los docentes y docentes que tengan asignada una licencia de profesorado y otro para todos los alumnos que tengan asignada una licencia de Estudiante. Tendrá que ejecutar este script de forma rutinaria para mantener los grupos actualizados y actualizados.

### <a name="assign-a-policy-to-a-security-group"></a>Asignar una directiva a un grupo de seguridad

#### <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

> [!NOTE]
> Actualmente, la asignación de directivas a grupos que usan el Centro de administración de Microsoft Teams Teams solo está disponible para una directiva de llamadas Teams, una directiva de parque de llamadas, una directiva de Teams Teams, una directiva de eventos en directo Teams, una directiva de reunión y una directiva de mensajería Teams. Para otros tipos de directiva, use PowerShell.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Reuniones** > **Directivas de reunión**.
2. Seleccione la **pestaña Asignación de directivas de** grupo.
3. Seleccione **Agregar grupo** y, a continuación, en el panel Asignar **directiva** al grupo, haga lo siguiente:

    ![Captura de pantalla del panel Editar configuración, que muestra la directiva de reunión](media/batch-group-policy-assignment-edu-group.png)
    1. En el **cuadro Seleccionar un grupo,** busque y agregue el grupo de seguridad que contiene el personal y los profesores.
    2. En el **cuadro Seleccionar jerarquía,** escriba **1**.
    3. En el **cuadro Seleccionar una directiva,** seleccione **EducatorMeetingPolicy**.
    4. Seleccione **Aplicar**.

Para quitar una asignación de directiva de grupo, en la pestaña **Asignación** de directivas de grupo de la página directiva, seleccione la asignación de grupo y, a continuación, **seleccione Quitar**.

Para cambiar la clasificación de una asignación de grupo, primero debe quitar la asignación de directiva de grupo. Después, siga los pasos anteriores para asignar la directiva a un grupo.

#### <a name="using-powershell"></a>Con PowerShell

> [!NOTE]
> Actualmente, la asignación de directivas a grupos que usan PowerShell no está disponible para todos los Teams de directiva. Vea [New-CsGroupPolicyAssignment para](/powershell/module/teams/new-csgrouppolicyassignment) obtener la lista de tipos de directiva admitidos.

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Instalar y conectarse al módulo Microsoft Teams PowerShell

Ejecute lo siguiente para instalar el [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (si aún no está instalado). Asegúrese de instalar la versión 1.0.5 o posterior.

```powershell
Install-Module -Name MicrosoftTeams
```

Ejecute lo siguiente para conectarse a Teams e iniciar una sesión.

```powershell
Connect-MicrosoftTeams
```

Cuando se le solicite, inicie sesión con sus credenciales de administrador.

##### <a name="assign-a-policy-to-a-group"></a>Asignar una directiva a un grupo

Ejecute lo siguiente para asignar la directiva de reunión denominada EducatorMeetingPolicy al grupo de seguridad que contiene el personal y los profesores y establezca la clasificación de tareas en 1. Puede especificar un grupo de seguridad mediante el id. del objeto, la dirección del Protocolo de inicio de sesión (SIP) o la dirección de correo electrónico. En este ejemplo, usamos una dirección de correo electrónico (staff-faculty@contoso.com).

```powershell
New-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com -PolicyType TeamsMeetingPolicy -PolicyName "EducatorMeetingPolicy" -Rank 1
```

### <a name="remove-a-policy-that-was-directly-assigned-to-users"></a>Quitar una directiva que se asignó directamente a los usuarios

Recuerde que si a un usuario se le asignó directamente una directiva (ya sea individualmente o a través de una asignación por lotes), esa directiva tiene prioridad. Esto significa que si un usuario tiene una directiva de reunión que se le asignó directamente, tendrá que quitar esa directiva de reunión del usuario antes de que pueda heredar una directiva de reunión de un grupo de seguridad.

Para obtener más información, vea [Qué necesita saber sobre la asignación de directivas a grupos.](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)

Siga estos pasos para quitar la directiva de reunión que se asignó directamente a su personal y profesores.

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Instalar y conectarse al módulo Microsoft Teams PowerShell

Ejecute lo siguiente para instalar el [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (si aún no está instalado). Asegúrese de instalar la versión 1.0.5 o posterior.

```powershell
Install-Module -Name MicrosoftTeams
```

Ejecute lo siguiente para conectarse a Teams e iniciar una sesión.

```powershell
Connect-MicrosoftTeams
```

Cuando se le solicite, inicie sesión con las mismas credenciales de administrador que usó para conectarse a Azure AD.

#### <a name="unassign-a-policy-that-was-directly-assigned-to-users"></a>Desasignación de una directiva que se asignó directamente a los usuarios

Ejecute lo siguiente para quitar una directiva de reunión de los usuarios a los que se les asignó directamente esa directiva. Puede especificar usuarios por dirección de correo electrónico o id. de objeto.

En este ejemplo, la directiva de reunión se quita de los usuarios especificados por su dirección de correo electrónico.

```powershell
$users_ids = @("reda@contoso.com", "nikica@contoso.com", "jamie@contoso.com")
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

En este ejemplo, la directiva de reunión se quita de la lista de usuarios de un archivo de texto denominado user_ids.txt.

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

##### <a name="get-policy-assignments-for-a-group"></a>Obtener asignaciones de directivas para un grupo

Ejecute lo siguiente para ver todas las directivas asignadas a un grupo de seguridad específico. Tenga en cuenta que los grupos siempre aparecen en la lista por su id. de grupo, incluso si se usó su dirección SIP o su dirección de correo electrónico para asignar la directiva.

```powershell
Get-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com

```

##### <a name="get-the-policies-assigned-to-a-user"></a>Obtener las directivas asignadas a un usuario

Ejecute lo siguiente para ver todas las directivas asignadas a un usuario específico. En el ejemplo siguiente se muestra cómo obtener las directivas asignadas a reda@contoso.com.

```powershell
Get-CsUserPolicyAssignment -Identity reda@contoso.com
```

## <a name="assign-a-policy-to-a-batch-of-users"></a>Asignar una directiva a un lote de usuarios

Siga estos pasos para asignar una directiva de reunión personalizada denominada EducatorMeetingPolicy directamente a su personal y profesores en masa.

### <a name="using-powershell"></a>Con PowerShell

#### <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a>Conectar el módulo PowerShell de Azure AD para Graph y el módulo Teams PowerShell

Antes de realizar los pasos de este artículo, deberá instalar y conectarse al módulo Azure AD PowerShell para Graph (para identificar usuarios por sus licencias asignadas) y al módulo de PowerShell de Microsoft Teams (para asignar las directivas a esos usuarios).

##### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a>Instalar y conectarse a Azure AD PowerShell para Graph módulo

Abra un símbolo Windows PowerShell símbolo del sistema (ejecute Windows PowerShell como administrador) y, a continuación, ejecute lo siguiente para instalar el Azure Active Directory PowerShell para Graph módulo.

```powershell
Install-Module -Name AzureAD
```

Ejecute lo siguiente para conectarse a Azure AD.

```powershell
Connect-AzureAD
```

Cuando se le solicite, inicie sesión con sus credenciales de administrador.

Para obtener más información, [vea Conectar con el Azure Active Directory PowerShell para Graph módulo](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Instalar y conectarse al módulo Microsoft Teams PowerShell

Ejecute lo siguiente para instalar el [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (si aún no está instalado). Asegúrese de instalar la versión 1.0.5 o posterior.

```powershell
Install-Module -Name MicrosoftTeams
```

Ejecute lo siguiente para conectarse a Teams e iniciar una sesión.

```powershell
Connect-MicrosoftTeams
```

Cuando se le solicite, inicie sesión con las mismas credenciales de administrador que usó para conectarse a Azure AD.

#### <a name="identify-your-users"></a>Identificar a los usuarios

En primer lugar, ejecute lo siguiente para identificar el personal y los profesores por tipo de licencia. Esto le indica qué SKU están en uso en su organización. A continuación, puede identificar docentes y docentes que tengan asignada una SKU de profesores.

```powershell
Get-AzureAdSubscribedSku | Select-Object -Property SkuPartNumber,SkuId
```

Lo que devuelve:

```
SkuPartNumber      SkuId
-------------      -----
M365EDU_A5_FACULTY e97c048c-37a4-45fb-ab50-922fbf07a370
M365EDU_A5_STUDENT 46c119d4-0379-4a9d-85e4-97c66d3f909e
```

En este ejemplo, el resultado muestra que skuId de licencia de profesores es "e97c048c-37a4-45fb-ab50-922fbf07a370".

> [!NOTE]
> Para ver una lista de SKU de educación e IDs de SKU, vea [Referencia de SKU de educación.](sku-reference-edu.md)

A continuación, ejecutamos lo siguiente para identificar los usuarios que tienen esta licencia y recopilarlos todos juntos.

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object {($_.assignedLicenses).SkuId -contains "e97c048c-37a4-45fb-ab50-922fbf07a370"}
```

#### <a name="assign-a-policy-in-bulk"></a>Asignar una directiva en masa

Ahora, asignamos las directivas adecuadas a los usuarios en masa. El número máximo de usuarios a los que puede asignar o actualizar directivas es de 5 000 a la vez. Por ejemplo, si tiene más de 5.000 docentes y profesores, tendrá que enviar varios lotes.

Ejecute lo siguiente para asignar una directiva de reunión personalizada denominada EducatorMeetingPolicy a su personal y profesores.

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> Para asignar un tipo de directiva diferente en masa, como TeamsMessagingPolicy, tendrá que cambiar a la directiva que va a asignar y al nombre ```PolicyType``` ```PolicyName``` de la directiva.

#### <a name="get-the-status-of-a-bulk-assignment"></a>Obtener el estado de una tarea en masa

Cada asignación en masa devuelve un id. de operación, que puede usar para realizar un seguimiento del progreso de las asignaciones de directivas o identificar los errores que puedan producirse. Por ejemplo, ejecute lo siguiente:

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

Para ver el estado de asignación de cada usuario en la operación por lotes, ejecute lo siguiente. Los detalles de cada usuario están en la ```UserState``` propiedad.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

#### <a name="assign-a-policy-in-bulk-if-you-have-more-than-5000-users"></a>Asignar una directiva en masa si tiene más de 5.000 usuarios

En primer lugar, ejecute lo siguiente para ver cuántos docentes y docentes tiene:

```powershell
$faculty.count
```

En lugar de proporcionar toda la lista de id. de usuario, ejecute lo siguiente para especificar los primeros 5.000 y, a continuación, los 5.000 siguientes, y así sucesivamente.

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty[0..19999].ObjectId
```

Puede cambiar el rango de id. de usuario hasta que llegue a la lista completa de usuarios. Por ejemplo, escriba para el primer lote, úsese para el segundo lote, escriba para el tercer ```$faculty[0..4999``` ```$faculty[5000..9999``` ```$faculty[10000..14999``` lote, y así sucesivamente.

#### <a name="get-the-policies-assigned-to-a-user"></a>Obtener las directivas asignadas a un usuario

Ejecute lo siguiente para ver todas las directivas asignadas a un usuario específico. En el ejemplo siguiente se muestra cómo obtener las directivas asignadas a hannah@contoso.com.

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a>Preguntas más frecuentes

**No estoy familiarizado con PowerShell para Teams. ¿Dónde puedo obtener más información?**

Para obtener información general sobre cómo usar PowerShell para administrar Teams, vea Teams [información general de PowerShell.](teams-powershell-overview.md) Para obtener más información sobre los cmdlets usados en este artículo, vea:

- [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment)
- [Get-CsGroupPolicyAssignment](/powershell/module/teams/get-csgrouppolicyassignment)
- [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [Get-CsUserPolicyAssignment](/powershell/module/teams/get-csuserpolicyassignment)

## <a name="related-topics"></a>Temas relacionados

- [Asignar directivas a los usuarios](assign-policies.md)
- [Directivas de Teams y paquetes de directivas para educación](policy-packages-edu.md)
- [Administración de directivas de reunión en Teams](meeting-policies-in-teams.md)