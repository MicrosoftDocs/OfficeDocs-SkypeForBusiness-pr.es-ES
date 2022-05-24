---
title: Asignar directivas en Teams
author: mkbond007
ms.author: mabond
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
ms.localizationpriority: medium
search.appverid: MET150
description: Obtenga información sobre las diferentes formas de asignar directivas y paquetes de directivas a usuarios y grupos de Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: c618653199a41bc358f4b2a14bdf1c0e8923d9b7
ms.sourcegitcommit: 9532eb79310cd653010565607fa394f2b8dd182d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/23/2022
ms.locfileid: "65646419"
---
# <a name="assign-policies-in-teams--getting-started"></a>Asignar directivas en Teams: introducción

Como administrador, puede usar directivas para controlar las características de Teams que están disponibles para los usuarios de su organización. Por ejemplo, hay directivas de llamadas, directivas de reunión y directivas de mensajería, por nombrar solo algunas.

Las organizaciones tienen diferentes tipos de usuarios con necesidades únicas. Las directivas personalizadas que cree y asigne le permiten personalizar la configuración de directivas a diferentes conjuntos de usuarios en función de esas necesidades.

Para administrar fácilmente las directivas de su organización, Teams ofrece varias formas de asignar directivas a los usuarios. Asigne una directiva directamente a los usuarios, ya sea de forma individual o a escala a través de una asignación por lotes, o a un grupo del que los usuarios sean miembros. También puede usar paquetes de directivas para asignar una colección predefinida de directivas a los usuarios de su organización que tengan roles similares. La opción que elija dependerá del número de directivas que esté administrando y del número de usuarios a los que asigne las directivas. Las directivas globales (predeterminadas para toda la organización) se aplican al mayor número de usuarios de su organización. Solo tiene que asignar directivas a los usuarios que requieren directivas especializadas.

En este artículo se describen las diferentes maneras en que puede asignar directivas a los usuarios y los escenarios recomendados para cuándo usar qué.

Para obtener más información sobre cómo **asignar directivas a usuarios y grupos**, vea [Asignar directivas a usuarios y grupos](assign-policies-users-and-groups.md). Para obtener más información sobre cómo **asignar paquetes de directivas**, consulta [Asignar paquetes de directiva](assign-policy-packages.md).

## <a name="which-policy-takes-precedence"></a>¿Qué directiva tiene prioridad?

Un usuario tiene una directiva eficaz para cada tipo de directiva. Es posible, o incluso probable, que un usuario tenga asignada directamente una directiva y también sea miembro de uno o más grupos a los que se haya asignado una directiva del mismo tipo. En estos tipos de escenarios, ¿qué directiva tiene prioridad? La directiva eficaz de un usuario se determina según las reglas de prioridad, como se indica a continuación.

Si a un usuario se le asigna directamente una directiva (ya sea de forma individual o a través de una asignación por lotes), esa directiva tiene prioridad. En el siguiente ejemplo visual, la directiva eficaz del usuario es la directiva de reunión de Lincoln Square, que se asigna directamente al usuario.

![Diagrama que muestra cómo una directiva asignada directamente tiene prioridad.](media/assign-policies-example-directly-assigned.png)

Si un usuario no tiene asignada directamente una directiva de un tipo determinado, la directiva asignada a un grupo al que el usuario es miembro tiene prioridad. Si un usuario es miembro de varios grupos, la directiva que tenga la más alta ([clasificación de asignaciones de grupo](assign-policies-users-and-groups.md#group-assignment-ranking)) para el tipo de directiva dado tiene prioridad.

En este ejemplo visual, la directiva eficaz del usuario es la directiva Exec Teams y HD, que tiene la clasificación de asignación más alta con respecto a otros grupos a los que pertenece el usuario y a los que también se asigna una directiva del mismo tipo de directiva.  

![Diagrama que muestra cómo tiene prioridad una directiva heredada de un grupo.](media/assign-policies-example-group.png)

Si un usuario no tiene asignada directamente una directiva o no es miembro de ningún grupo al que se le haya asignado una directiva, el usuario obtiene la directiva global (predeterminada para toda la organización) para ese tipo de directiva. Este es un ejemplo visual.

![Diagrama que muestra cómo tiene prioridad una directiva global.](media/assign-policies-example-global.png)

Para obtener más información, consulte ([Reglas de prioridad](assign-policies-users-and-groups.md#precedence-rules)).

## <a name="ways-to-assign-policies"></a>Formas de asignar directivas

Esta es una descripción general de las formas en que puede asignar directivas a los usuarios y los escenarios recomendados para cada uno de ellos. Seleccione los vínculos para obtener más información.

Antes de asignar directivas a usuarios o grupos individuales, comience [por establecer las directivas globales (predeterminadas para toda](#set-the-global-policies) la organización) para que se apliquen al mayor número de usuarios de su organización.  Una vez establecidas las directivas globales, solo tendrá que asignar directivas a los usuarios que requieran directivas especializadas.

|Haz esto  |Si...  | Usando...
|---------|---------|----|
|[Asignar una directiva a usuarios individuales](assign-policies-users-and-groups.md#assign-a-policy-to-individual-users)   | No está familiarizado con Teams y acaba de empezar o solo necesita asignar una o un par de directivas a un pequeño número de usuarios. |Centro de administración de Microsoft Teams o cmdlets de PowerShell en el módulo Teams PowerShell
|[Asignar una directiva a un grupo](assign-policies-users-and-groups.md#assign-a-policy-to-a-group) |Asigne directivas basadas en la pertenencia a grupos de un usuario. Por ejemplo, asigne una directiva a todos los usuarios de un grupo de seguridad o una lista de distribución.| Centro de administración de Microsoft Teams o cmdlets de PowerShell en el módulo Teams PowerShell|
|[Asignar una directiva a un lote de usuarios](assign-policies-users-and-groups.md#assign-a-policy-to-a-batch-of-users)   | Asigne directivas a grandes conjuntos de usuarios. Por ejemplo, asigne una directiva a cientos o miles de usuarios de su organización a la vez. |Centro de administración de Microsoft Teams o cmdlets de PowerShell en el módulo Teams PowerShell|
|[Asignar un paquete de directiva a los usuarios](assign-policy-packages.md#assign-a-policy-package-to-users)  |Asigne varias directivas a conjuntos específicos de usuarios de su organización que tienen los mismos roles o similares. Por ejemplo, asigne el paquete de directivas Educación (profesor) a los profesores de su centro educativo para proporcionarles acceso total a chats, llamadas y reuniones. Asigne el paquete de directivas Educación (alumno de secundaria) a los alumnos secundarios para limitar determinadas capacidades, como las llamadas privadas.  |Centro de administración de Microsoft Teams o cmdlets de PowerShell en el módulo Teams PowerShell|
|[Asignar un paquete de directivas a un grupo](assign-policy-packages.md#assign-a-policy-package-to-a-group)  |Asigne varias directivas a un grupo de usuarios de su organización que tienen los mismos roles o similares. Por ejemplo, asigne un paquete de directivas a todos los usuarios de un grupo de seguridad o una lista de distribución. |Centro de administración de Microsoft Teams (próximamente) o cmdlets de PowerShell en el módulo Teams PowerShell|
|[Asignar un paquete de directivas a un lote de usuarios](assign-policy-packages.md#assign-a-policy-package-to-a-batch-of-users)|Asigne varias directivas a un lote de usuarios de su organización que tienen los mismos roles o similares. Por ejemplo, asigne el paquete de directivas Educación (profesor) a todos los profesores de su escuela mediante asignación por lotes para proporcionarles acceso total a chats, llamadas y reuniones. Asigne el paquete de directivas Educación (alumno de secundaria) a un lote de alumnos secundarios para limitar determinadas capacidades, como las llamadas privadas.|Cmdlets de PowerShell en el módulo Teams PowerShell|

## <a name="set-the-global-policies"></a>Establecer las directivas globales

Siga estos pasos para establecer las directivas globales (predeterminadas para toda la organización) para cada tipo de directiva.

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

1. En el panel de navegación izquierdo del centro de administración de Microsoft Teams, vaya a la página de directiva del tipo de directiva que desea actualizar. Por ejemplo, **directivas Teams** >  **Teams**, **directivas MeetingsMeetings**, **directivas de mensajes** o **directivas** >  **de Llamada** **de voz** > .
2. Seleccione la **directiva Global (predeterminada para toda** la organización) para ver la configuración actual.
3. Actualice la directiva según sea necesario y, después, seleccione **Aplicar**.

![Actualizar la directiva global en Teams centro de administración.](media/assign-globalpolicy.png)

### <a name="using-powershell"></a>Con PowerShell

Para establecer las directivas globales con PowerShell, use el identificador global.  Empiece revisando la directiva global actual para determinar qué configuración desea cambiar.

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

A continuación, actualice la directiva global según sea necesario.  Solo necesita especificar valores para la configuración que desea cambiar.

```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="view-your-policy-assignments-in-the-activity-log"></a>Ver las asignaciones de directivas en el registro de actividades

Al asignar directivas a usuarios en el Microsoft Teams centro de administración, puede ver el estado de esas asignaciones de directivas en el [registro de actividades](https://admin.teams.microsoft.com/activitylog). El registro de actividades muestra información de carga de registros de red, operaciones de directivas de grupo desde Teams centro de administración y PowerShell, y operaciones de directivas de lotes (para más de 20 usuarios) desde el centro de administración de Teams durante los últimos 30 días.

![Captura de pantalla de la página del registro de actividades.](media/Activity_Log.png)

Para ver las operaciones de directivas en el registro de actividades:

1. En el panel de navegación izquierdo del Microsoft Teams centro de administración, vaya a **Panel** y, a continuación, en **Registro** de actividades, seleccione **Ver detalles**.
2. Verá la siguiente información sobre cada operación de directiva:
    - **Actividad**: el nombre de la operación de directiva. Por ejemplo: **Asignación de directiva de grupo**
    - **Nombre del** grupo: el nombre del grupo en el que se completó la operación de directiva.
    - **Tipo de directiva**: el tipo de directiva.
    - **Nombre de la directiva**: el nombre de la operación de directiva. Para las asignaciones de directivas por lotes, puede seleccionar el vínculo para ver más detalles. Esto incluye el número de usuarios a los que se asignó la directiva y el número de asignaciones completadas, en curso y no iniciadas. También verá la lista de usuarios del lote y el estado y el resultado de cada usuario.
    - **Enviado por**: El nombre del usuario que envió la operación de directiva.
    - **Enviado el**: Fecha y hora en que se envió la operación de directiva.
    - **Completado el**: Fecha y hora en que se completó la operación de directiva.
    - **Afectado**: número de usuarios en el lote o grupo.
    - **Estado general**: estado de la operación de directiva. Una directiva puede tener uno de los siguientes estados:
        - **No iniciado**: el administrador ha enviado la operación de directiva.
        - **En curso**: la operación de directiva ha comenzado a procesarse.
        - **Implementación para los usuarios**: el sistema ha comenzado a aplicar la actualización de directiva a los usuarios.
        - **Completado**: la actualización de la directiva se ha aplicado a todos los usuarios.
        - **Completado con errores "x"**: la operación de directiva está completa, pero hay errores.

> [!NOTE]
> También puede acceder al registro de actividades desde la página **Usuarios** . Después de seleccionar **Aplicar** para enviar una asignación de directiva masiva, verá un banner en la parte superior de la página. Seleccione el vínculo **Registro de** actividades en la pancarta.

## <a name="related-topics"></a>Temas relacionados

- [Asignar directivas a usuarios y grupos](assign-policies-users-and-groups.md)
- [Asignar paquetes de directivas a usuarios y grupos](assign-policy-packages.md)
- [Administrar Teams con directivas](manage-teams-with-policies.md)
- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
