---
title: Asignar directivas a grandes conjuntos de usuarios de la escuela
author: lanachin
ms.author: v-lanac
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
description: Aprenda a asignar directivas a grandes conjuntos de usuarios de su institución educativa basándose en la pertenencia a grupos o directamente a través de un proceso por lotes para la escuela remota (teleschool, tele-School).
f1keywords: ''
ms.openlocfilehash: 0b4fd804b51fef9537d30230aed400bb0cb7e0aa
ms.sourcegitcommit: dc3e8ae454c42981f037f4de2e48005428b6078e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/31/2020
ms.locfileid: "46534135"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a>Asignar directivas a grandes conjuntos de usuarios de la escuela

> [!NOTE]
> Para obtener la historia más grande sobre la asignación de directivas en Microsoft Teams, consulte [asignar directivas a los usuarios de Teams](assign-policies.md).

## <a name="overview"></a>Información general

¿Necesita dar acceso a las diferentes características de Microsoft Teams a sus alumnos y educadores? Puede identificar rápidamente los usuarios de su organización por tipo de licencia y, a continuación, asignarles la Directiva adecuada. En este tutorial se muestra cómo asignar una directiva de reunión a grandes conjuntos de usuarios de la escuela. Puede asignar directivas con el centro de administración de Microsoft Teams y PowerShell y le mostraremos ambas maneras.

Puede asignar una directiva de reunión a un grupo de seguridad al que los usuarios son miembros o directamente a los usuarios a escala mediante una asignación de Directiva por lotes. Aprenderá a:

- **Use [asignación de directiva a grupos](#assign-a-policy-to-a-group) para asignar una directiva de reunión a un grupo de seguridad (recomendado)**. Este método le permite asignar una directiva basada en la pertenencia a grupos. Puede asignar una directiva a un grupo de seguridad o a una lista de distribución. A medida que se agregan o quitan miembros del grupo, sus asignaciones de directivas heredadas se actualizan según corresponda. Le recomendamos que use este método porque reduce el tiempo de administración de directivas para nuevos usuarios o cuando cambian las funciones de los usuarios. Este método funciona mejor para grupos de hasta 50.000 usuarios, pero también funciona con grupos más grandes.

- **Use [asignación de Directiva por lotes](assign-policies.md#assign-a-policy-to-a-batch-of-users) para asignar una directiva de reunión directamente a los usuarios de forma masiva**. Puede asignar una directiva para un máximo de 5.000 usuarios a la vez. Si tiene más de 5.000 usuarios, puede enviar varios lotes. Con este método, cuando tenga usuarios nuevos, tendrá que volver a ejecutar la asignación por lotes para asignar la Directiva a esos nuevos usuarios.

Recuerde que en Teams, los usuarios obtienen automáticamente la directiva global (opción predeterminada para toda la organización) para un tipo de directiva de Teams, a menos que cree y asigne una directiva personalizada. Como la población de alumnos suele ser el mayor conjunto de usuarios y a menudo reciben la configuración más restrictiva, le recomendamos que haga lo siguiente:

- Crear una directiva personalizada que permita capacidades básicas, como la programación privada de chats y reuniones, y la asignación de la Directiva a su personal y educadores.
- Asigne la directiva personalizada a su personal y educadores.
- Edite y aplique la directiva global (valor predeterminado de la organización) para restringir las capacidades de los alumnos.

Tenga en cuenta que la directiva global se aplicará a todos los usuarios de su escuela hasta que cree una directiva personalizada y la asigne a su personal y educadores.

En este tutorial, los alumnos obtendrán la Directiva de reunión global y asignaremos una directiva de reunión personalizada denominada EducatorMeetingPolicy al personal y los educadores. Damos por hecho que ha modificado la directiva global para personalizar la configuración de la reunión de los alumnos y [creado una directiva personalizada](policy-packages-edu.md) que define la experiencia de la reunión para el personal y los educadores.

![Captura de pantalla de la página directivas de la reunión en el centro de administración de Teams](media/batch-group-policy-assignment-edu-meeting-policies.png)

## <a name="assign-a-policy-to-a-group"></a>Asignar una directiva a un grupo

Siga estos pasos para crear un grupo de seguridad para su personal y educadores y, a continuación, asigne una directiva de reunión personalizada denominada EducatorMeetingPolicy a ese grupo de seguridad.

### <a name="before-you-get-started"></a>Antes de empezar

> [!IMPORTANT]
> Cuando se asigna una directiva a un grupo, la asignación de Directiva se propaga a los miembros del grupo según las reglas de prioridad. Por ejemplo, si un usuario tiene asignada directamente una directiva (ya sea de forma individual o mediante una asignación por lotes), esta directiva tiene prioridad sobre una directiva heredada de un grupo. Esto también significa que si un usuario tiene una directiva de reunión que se le asignó directamente, tendrá que quitar esa Directiva de la reunión del usuario antes de que puedan heredar una directiva de reunión de un grupo de seguridad.

Antes de empezar, es importante comprender [las reglas de prioridad](assign-policies.md#precedence-rules) y la [clasificación de asignación de grupo](assign-policies.md#group-assignment-ranking). Asegúrese **de leer y comprender los conceptos de lo que debe [saber sobre la asignación de directivas a grupos](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)**.

Tendrá que completar todos estos pasos para que su personal y educadores hereden una directiva de reunión de un grupo de seguridad.

1. [Crear grupos de seguridad](#create-security-groups).
2. [Asignar una directiva a un grupo de seguridad](#assign-a-policy-to-a-security-group).
3. [Quitar una directiva que se asignó directamente a los usuarios](#remove-a-policy-that-was-directly-assigned-to-users).

### <a name="create-security-groups"></a>Crear grupos de seguridad

En primer lugar, cree un grupo de seguridad para su personal y educadores.

Con [School Data Sync](https://docs.microsoft.com/SchoolDataSync/) (SDS), puede [crear fácilmente educadores y alumnos de grupos de seguridad](https://docs.microsoft.com/SchoolDataSync/edu-security-groups) en su escuela. Le recomendamos que use SDS para crear los grupos de seguridad que necesita para administrar las directivas de su escuela.

Si no puede implementar SDS dentro de su entorno, use [este script de PowerShell](scripts/powershell-script-security-groups-edu.md) para crear dos grupos de seguridad, uno para todos los docentes y educadores que tengan una licencia de profesorado asignada y otra para todos los alumnos que tengan asignada una licencia de estudiante. Tendrá que ejecutar esta secuencia de comandos de forma rutinaria para mantener actualizados los grupos y actualizarlos.

### <a name="assign-a-policy-to-a-security-group"></a>Asignar una directiva a un grupo de seguridad

#### <a name="using-the-microsoft-teams-admin-center"></a>Usar el centro de administración de Microsoft Teams

> [!NOTE]
> Por el momento, la asignación de directivas a grupos que usan el centro de administración de Microsoft Teams solo está disponible para la Directiva de llamadas de Teams, la Directiva de Parque de llamadas de Teams, la Directiva de Teams, la Directiva de eventos en vivo de Teams, la Directiva de reuniones Para otros tipos de directivas, use PowerShell.

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a directivas de reunión de **reuniones**  >  **Meeting policies**.
2. Seleccione la pestaña **asignación de directiva de grupo** .
3. Seleccione **Agregar grupo**y, a continuación, en el panel **asignar Directiva a grupo** , haga lo siguiente:

    ![Captura de pantalla del panel Editar configuración, que muestra la Directiva de reunión](media/batch-group-policy-assignment-edu-group.png)
    1. En el cuadro **seleccionar un grupo** , busque y agregue el grupo de seguridad que contiene su personal y educadores.
    2. En el cuadro **Seleccionar rango** , escriba **1**.
    3. En el cuadro **seleccionar una directiva** , seleccione **EducatorMeetingPolicy**.
    4. Seleccione **aplicar**.

Para quitar una asignación de directiva de grupo, en la pestaña **asignación de directiva de grupo** de la página de Directiva, seleccione la asignación de grupo y, a continuación, seleccione **quitar**.

Para cambiar la jerarquía de una asignación de grupo, primero debe quitar la asignación de directiva de grupo. Después, siga los pasos anteriores para asignar la Directiva a un grupo.

#### <a name="using-powershell"></a>Con PowerShell

> [!NOTE]
> Por el momento, la asignación de directivas a grupos con PowerShell no está disponible para todos los tipos de directivas de Teams. Vea [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) para obtener la lista de tipos de directiva admitidos.

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Instalar y conectarse al módulo de PowerShell de Microsoft Teams

Ejecute lo siguiente para instalar el [módulo de PowerShell de Teams](https://www.powershellgallery.com/packages/MicrosoftTeams) (si aún no está instalado). Asegúrese de instalar la versión 1.0.5 o posterior.

```powershell
Install-Module -Name MicrosoftTeams
```

Ejecute lo siguiente para conectarse a teams e iniciar una sesión.

```powershell
Connect-MicrosoftTeams
```

Cuando se le solicite, inicie sesión con sus credenciales de administrador.

##### <a name="assign-a-policy-to-a-group"></a>Asignar una directiva a un grupo

Ejecute lo siguiente para asignar la Directiva de reunión denominada EducatorMeetingPolicy al grupo de seguridad que contiene su personal y educadores y establezca la clasificación de asignaciones en 1. Puede especificar un grupo de seguridad mediante el identificador de objeto, la dirección del Protocolo de inicio de sesión (SIP) o la dirección de correo electrónico. En este ejemplo, usamos una dirección de correo electrónico (staff-faculty@contoso.com).

```powershell
New-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com -PolicyType TeamsMeetingPolicy -PolicyName "EducatorMeetingPolicy" -Rank 1
```

### <a name="remove-a-policy-that-was-directly-assigned-to-users"></a>Quitar una directiva que se asignó directamente a los usuarios

Recuerde que si un usuario tiene asignada una directiva directamente (ya sea de forma individual o a través de una asignación por lotes), tiene prioridad. Esto significa que si un usuario tiene una directiva de reunión que se le asignó directamente, tendrá que quitar esa Directiva de la reunión del usuario antes de que puedan heredar una directiva de reunión de un grupo de seguridad.

Para obtener más información, vea [lo que debe saber sobre la asignación de directivas a grupos](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups).

Siga estos pasos para quitar la Directiva de reunión que se asignó directamente a su personal y educadores.

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Instalar y conectarse al módulo de PowerShell de Microsoft Teams

Ejecute lo siguiente para instalar el [módulo de PowerShell de Teams](https://www.powershellgallery.com/packages/MicrosoftTeams) (si aún no está instalado). Asegúrese de instalar la versión 1.0.5 o posterior.

```powershell
Install-Module -Name MicrosoftTeams
```

Ejecute lo siguiente para conectarse a teams e iniciar una sesión.

```powershell
Connect-MicrosoftTeams
```
Cuando se le solicite, inicie sesión con las mismas credenciales de administrador que usó para conectarse a Azure AD.

#### <a name="unassign-a-policy-that-was-directly-assigned-to-users"></a>Cancelar la asignación de una directiva que se asignó directamente a los usuarios

Ejecute lo siguiente para quitar una directiva de reunión de los usuarios que han asignado directamente esa Directiva. Puede especificar usuarios por dirección de correo electrónico o identificador de objeto.

En este ejemplo, la política de la reunión se quita de los usuarios especificados por su dirección de correo electrónico.

```powershell
$users_ids = @("reda@contoso.com", "nikica@contoso.com", "jamie@contoso.com")
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

En este ejemplo, la Directiva de la reunión se quita de la lista de usuarios en un archivo de texto denominado user_ids.txt. 

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

##### <a name="get-policy-assignments-for-a-group"></a>Obtener asignaciones de directivas para un grupo

Ejecute lo siguiente para ver todas las directivas asignadas a un grupo de seguridad específico. Ten en cuenta que los grupos siempre aparecen en la lista por su identificador de grupo aunque su dirección SIP o dirección de correo electrónico se hayan usado para asignar la Directiva.

```powershell
Get-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com

```

##### <a name="get-the-policies-assigned-to-a-user"></a>Obtener las directivas asignadas a un usuario

Ejecute lo siguiente para ver todas las directivas que se han asignado a un usuario específico. En el ejemplo siguiente se muestra cómo obtener las directivas que se asignan a reda@contoso.com.

```powershell
Get-CsUserPolicyAssignment -Identity reda@contoso.com
```

## <a name="assign-a-policy-to-a-batch-of-users"></a>Asignar una directiva a un lote de usuarios

Siga estos pasos para asignar una directiva de reunión personalizada denominada EducatorMeetingPolicy directamente a su personal y educadores en bloque.

### <a name="using-powershell"></a>Con PowerShell

#### <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a>Conectarse al módulo de Azure AD PowerShell para Graph y al módulo de PowerShell de Teams

Antes de realizar los pasos de este artículo, tendrá que instalar y conectarse con el módulo Azure AD PowerShell for Graph (para identificar a los usuarios por sus licencias asignadas) y el módulo Microsoft Teams PowerShell (para asignar las directivas a esos usuarios).

##### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a>Instalar y conectarse al módulo de Azure AD PowerShell para Graph

Abra un símbolo del sistema de Windows PowerShell con privilegios elevados (ejecute Windows PowerShell como administrador) y, a continuación, ejecute lo siguiente para instalar el módulo Azure Active Directory PowerShell para Graph.

```powershell
Install-Module -Name AzureAD
```

Ejecute lo siguiente para conectarse a Azure AD.

```powershell
Connect-AzureAD
```

Cuando se le solicite, inicie sesión con sus credenciales de administrador.

Para obtener más información, vea [conectarse con el módulo Azure Active Directory PowerShell para Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Instalar y conectarse al módulo de PowerShell de Microsoft Teams

Ejecute lo siguiente para instalar el [módulo de PowerShell de Teams](https://www.powershellgallery.com/packages/MicrosoftTeams) (si aún no está instalado). Asegúrese de instalar la versión 1.0.5 o posterior.

```powershell
Install-Module -Name MicrosoftTeams
```

Ejecute lo siguiente para conectarse a teams e iniciar una sesión.

```powershell
Connect-MicrosoftTeams
```
Cuando se le solicite, inicie sesión con las mismas credenciales de administrador que usó para conectarse a Azure AD.

#### <a name="identify-your-users"></a>Identificar a los usuarios

En primer lugar, ejecute lo siguiente para identificar a su personal y educadores por tipo de licencia. Esto le indica qué SKU están en uso en su organización. A continuación, puede identificar el personal y los formadores que tienen una SKU de profesores asignados.

```powershell
Get-AzureAdSubscribedSku | Select-Object -Property SkuPartNumber,SkuId
```

Que devuelve:

```
SkuPartNumber      SkuId
-------------      -----
M365EDU_A5_FACULTY e97c048c-37a4-45fb-ab50-922fbf07a370
M365EDU_A5_STUDENT 46c119d4-0379-4a9d-85e4-97c66d3f909e
```

En este ejemplo, la salida muestra que el SkuId de la licencia del profesorado es "e97c048c-37a4-45FB-AB50-922fbf07a370".

> [!NOTE]
> Para ver una lista de SKU de educación e identificadores de SKU, consulte [educación SKU SKU](sku-reference-edu.md).

A continuación, ejecutamos lo siguiente para identificar los usuarios que tienen esta licencia y recopilar todas ellas.

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object {($_.assignedLicenses).SkuId -contains "e97c048c-37a4-45fb-ab50-922fbf07a370"}
```

#### <a name="assign-a-policy-in-bulk"></a>Asignar una directiva en masa

Ahora, asignamos las directivas apropiadas a usuarios de forma masiva. La cantidad máxima de usuarios para los que puede asignar o actualizar directivas es 5.000 a la vez. Por ejemplo, si tiene más de 5.000 de personal y educadores, tendrá que enviar varios lotes.

Ejecute lo siguiente para asignar una directiva de reunión personalizada denominada EducatorMeetingPolicy a su personal y educadores.

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> Para asignar un tipo de directiva diferente en masa, como TeamsMessagingPolicy, tendrá que cambiar ```PolicyType``` a la Directiva que está asignando y ```PolicyName``` al nombre de la Directiva.

#### <a name="get-the-status-of-a-bulk-assignment"></a>Obtener el estado de una asignación masiva

Cada asignación en masa devuelve un identificador de operación, que puede usar para realizar un seguimiento del progreso de las asignaciones de directivas o para identificar los errores que puedan producirse. Por ejemplo, ejecute lo siguiente:

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

Para ver el estado de asignación de cada usuario en la operación por lotes, ejecute lo siguiente. Los detalles de cada usuario están en la ```UserState``` propiedad.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

#### <a name="assign-a-policy-in-bulk-if-you-have-more-than-5000-users"></a>Asignar una directiva de forma masiva si tiene más de 5.000 usuarios

En primer lugar, ejecute lo siguiente para ver cuánto personal y educadores tiene:

```powershell
$faculty.count
```

En lugar de proporcionar la lista completa de identificadores de usuario, ejecute lo siguiente para especificar el primer 5.000, después, el siguiente 5.000, etc.

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty[0..19999].ObjectId
```

Puede cambiar el intervalo de identificadores de usuario hasta que llegue a la lista completa de usuarios. Por ejemplo, escriba ```$faculty[0..4999``` para el primer lote, use ```$faculty[5000..9999``` para el segundo lote, especifique ```$faculty[10000..14999``` el tercer lote, y así sucesivamente.

#### <a name="get-the-policies-assigned-to-a-user"></a>Obtener las directivas asignadas a un usuario

Ejecute lo siguiente para ver todas las directivas que se han asignado a un usuario específico. En el ejemplo siguiente se muestra cómo obtener las directivas que se asignan a hannah@contoso.com.

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a>Preguntas más frecuentes

**No estoy familiarizado con PowerShell para Teams. ¿Dónde puedo obtener más información?**

Para obtener información general sobre cómo usar PowerShell para administrar equipos, consulte [información general de Teams PowerShell](teams-powershell-overview.md). Para obtener más información sobre los cmdlets que se usan en este artículo, vea:

- [Nuevo: CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment)
- [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment)
- [Nuevo: CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)

## <a name="related-topics"></a>Temas relacionados

- [Asignar directivas a los usuarios](assign-policies.md)
- [Directivas y paquetes de directivas de Teams para el ámbito educativo](policy-packages-edu.md)
- [Administrar directivas de reunión en Teams](meeting-policies-in-teams.md)
