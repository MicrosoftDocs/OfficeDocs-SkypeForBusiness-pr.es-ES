---
title: Administrar directivas de comentarios en Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: msedliak
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Aprenda a usar las directivas de comentarios para controlar si los usuarios de equipos de su organización pueden enviar comentarios sobre los equipos a Microsoft.
ms.openlocfilehash: b016a1d566f15cdabea55913b7fe107d86dee358
ms.sourcegitcommit: b381d8f0b9fc45133d52175fa85901b66e744abd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "44326687"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a>Administrar directivas de comentarios en Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Los usuarios de su organización pueden enviar comentarios acerca de Teams a Microsoft para saber cómo estamos haciendo, directamente desde el escritorio de Teams y los clientes Web. Mejoramos continuamente la experiencia de los equipos y usamos estos comentarios para mejorar los equipos.

**La característica proporcionar comentarios**

Los usuarios pueden enviar comentarios y sugerencias sobre los equipos para que nos **ayuden**a  >  **proporcionar comentarios** en Teams. Los datos enviados a través de enviar **comentarios** se consideran "datos de soporte técnico" en el acuerdo de Office 365, incluida información que de otro modo se consideraría "datos de los clientes" o "datos personales".

![Captura de pantalla de la opción ofrecer comentarios en Teams](media/manage-feedback-policies-in-teams-give-feedback.png)

**Inspeccion**

Los usuarios también pueden calificar su experiencia con Teams y enviarnos detalles sobre la clasificación que ofrecen. Esta encuesta emergente se muestra a los usuarios de vez en cuando en Teams. Cuando un usuario hace clic en **proporcionar comentarios** en la notificación, la encuesta se muestra para que se complete.

![Captura de pantalla de la notificación de encuesta y el formulario en Teams](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a>Establecer si los usuarios pueden enviar comentarios sobre equipos a Microsoft

Como administrador, puede controlar si los usuarios de su organización pueden enviar comentarios sobre equipos a Microsoft mediante **comentarios** y si reciben la encuesta. De forma predeterminada, a todos los usuarios de la organización se les asigna automáticamente la directiva global (opción predeterminada para toda la organización) y la característica **proporcionar comentarios** y la encuesta están habilitadas en la Directiva. La excepción es equipos para el ámbito educativo, donde las características están habilitadas para los profesores y deshabilitadas para los alumnos.

Puede editar la directiva global o crear y asignar una directiva personalizada. Si un usuario tiene asignada una directiva personalizada, esa Directiva se aplica al usuario. Si un usuario no tiene asignada una directiva personalizada, la política global se aplica al usuario. Después de modificar la directiva global o asignar una directiva, los cambios pueden demorar algunas horas en surtir efecto.

Supongamos, por ejemplo, que desea permitir que todos los usuarios de su organización envíen **comentarios y** reciban encuestas, excepto para los nuevos empleados en curso. En este escenario, puede crear una directiva personalizada para desactivar ambas características y asignarla a nuevos empleados. El resto de los usuarios de su organización obtienen la directiva global con las características activadas.  

Use el cmdlet **New-CsTeamsFeedbackPolicy** , *que se puede [encontrar aquí](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*, para crear una directiva personalizada y el cmdlet **Grant-CsTeamsFeedbackPolicy** para asignarla a uno o más usuarios o grupos de usuarios, como un grupo de seguridad o un grupo de distribución.

Para desactivar y activar las características, establezca los siguientes parámetros:

 - **Enviar comentarios**: establezca el parámetro **userInitiatedMode** en **habilitado** para permitir a los usuarios a quienes les asignan Comentarios. Establecer el parámetro en **deshabilitado** desactiva la característica y los usuarios a los que se les asigna la Directiva no tienen la opción de enviar comentarios.
 - **Encuestas**: establezca el parámetro **receiveSurveysMode** en **habilitado** para permitir que los usuarios a los que se les asigne la Directiva reciban la encuesta. Para que los usuarios reciban la encuesta y les permita su cancelación, establezca el parámetro en **enabledUserOverride**. En Teams, los usuarios pueden ir a la **configuración**  >  **privacidad** y elegir si desean participar en encuestas. Establecer el parámetro en **deshabilitado** desactiva la característica y los usuarios que tienen asignada la Directiva no recibirán la encuesta.

## <a name="create-a-custom-feedback-policy"></a>Crear una directiva personalizada de comentarios

En este ejemplo, creamos una política de comentarios denominada nueva Directiva de comentarios para empleados y desactivamos la posibilidad de enviar comentarios mediante **comentarios** y la encuesta.

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy"></a>Asignar una directiva personalizada de comentarios

### <a name="assign-a-custom-feedback-policy-to-a-user"></a>Asignar una directiva personalizada de comentarios a un usuario

En este ejemplo, asignamos una directiva personalizada denominada nueva Directiva de comentarios para el contrato a un usuario denominado usuario1.

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```
### <a name="assign-a-custom-feedback-policy-to-users-in-a-group"></a>Asignar una directiva de comentarios personalizada a los usuarios de un grupo

Es posible que desee asignar una directiva personalizada de comentarios a varios usuarios que ya haya identificado. Por ejemplo, es posible que desee asignar una directiva a todos los usuarios de un grupo de seguridad.

En este ejemplo, asignamos una directiva personalizada de comentarios denominada nueva política de comentarios de la contratación a todos los usuarios del grupo contoso New contratados.  

Obtén la GroupObjectId del grupo en particular.
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso New Hires"
```
Obtener los miembros del grupo especificado.
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
Asignar todos los usuarios del grupo a una política de comentarios determinada. En este ejemplo, se trata de una nueva política de comentarios de los empleados.
```PowerShell
$members | ForEach-Object {Grant-CsTeamsFeedbackPolicy -PolicyName "New Hire Feedback Policy" -Identity $_.UserPrincipalName}
``` 
Según el número de miembros del grupo, este comando puede demorar varios minutos en ejecutarse.

## <a name="related-topics"></a>Temas relacionados

- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
