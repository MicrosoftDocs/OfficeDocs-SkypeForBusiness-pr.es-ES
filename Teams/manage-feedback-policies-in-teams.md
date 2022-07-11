---
title: Administrar directivas de comentarios en Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: heprecel
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
ms.localizationpriority: medium
search.appverid: MET150
description: Obtenga información sobre cómo usar las directivas de comentarios para controlar si los usuarios de Teams de su organización pueden enviar comentarios sobre Teams a Microsoft.
ms.openlocfilehash: 7fcfa1738f7dbbc0f7c70afec86e9e2f181d6d21
ms.sourcegitcommit: 8d7a926758971bee491d24f23b1ad14f5e5c6f7f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2022
ms.locfileid: "66713348"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a>Administrar directivas de comentarios en Microsoft Teams

Los usuarios de su organización pueden enviar comentarios sobre Microsoft Teams para hacernos saber cómo lo estamos haciendo directamente desde el escritorio, los clientes web y los dispositivos móviles de Teams. Mejoramos continuamente la experiencia de Teams y usamos estos comentarios para mejorar Teams.

> [!NOTE]
> Las directivas de comentarios no están disponibles en implementaciones GCC, GCC High ni DOD.

**La característica **Enviar comentarios****

Los usuarios pueden enviarnos comentarios y sugerencias sobre Teams yendo **a Ayuda** >  para **enviar comentarios** en la versión de escritorio y web de Teams.


![Opción Enviar comentarios en Teams](media/manage-feedback-policies-in-teams-give-feedback.png)

Obtenga acceso a comentarios sobre dispositivos móviles con **la Ayuda** **de Configuración** >  &**enviar comentarios** > .

![Opción Enviar comentarios en Teams para móviles](media/feedback3.jpg)

 Los datos enviados a través de **Enviar comentarios** y **Enviar comentarios** se consideran "Datos de soporte técnico" en virtud de su contrato de Microsoft 365 o Office 365, incluida la información que, de lo contrario, se consideraría "Datos del cliente" o "Datos personales".



**Encuestas**

Los usuarios también pueden valorar su experiencia con Teams y enviarnos detalles sobre la clasificación que proporcionan. Esta encuesta emergente se muestra a los usuarios de vez en cuando en Teams. Cuando un usuario selecciona **Proporcionar comentarios** en la notificación, se muestra la encuesta para que la complete.

![la notificación y el formulario de la encuesta en Teams.](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a>Establecer si los usuarios pueden enviar comentarios sobre Teams a Microsoft

Como administrador, puede controlar si los usuarios de su organización pueden enviar comentarios sobre Teams a Microsoft y si reciben la encuesta. De forma predeterminada, a todos los usuarios de su organización se les asigna automáticamente la directiva global (predeterminada para toda la organización), y la característica de comentarios y la encuesta están habilitadas en la directiva. La excepción es Teams para Educación, donde las características están habilitadas para los profesores y deshabilitadas para los alumnos.

Puede editar la directiva global o crear y asignar una directiva personalizada. Después de editar la directiva global o asignar una directiva personalizada, los cambios pueden tardar unas horas en surtir efecto.

Supongamos, por ejemplo, que desea permitir que todos los usuarios de su organización envíen comentarios y reciban encuestas, excepto los nuevos empleados de formación. En este escenario, creará una directiva personalizada para desactivar ambas características y asignarla a los nuevos empleados. El resto de usuarios de su organización obtienen la directiva global con las características activadas.  

Puede administrar las directivas de comentarios con PowerShell. Use el [cmdlet **New-CsTeamsFeedbackPolicy**](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell) para crear una directiva personalizada. Use el cmdlet **Grant-CsTeamsFeedbackPolicy** para asignarlo a uno o más usuarios o grupos de usuarios, como un grupo de distribución o un grupo de seguridad. Use **Set-CsTeamsFeedbackPolicy** para establecer marcas específicas.

Para desactivar y activar las características, establezca los siguientes parámetros:

 - **Enviar comentarios**: establezca el parámetro **userInitiatedMode** **en habilitado** para permitir que los usuarios asignados a la directiva proporcionen comentarios. Si se establece el parámetro **en Deshabilitado** , se desactivará la característica y los usuarios a los que se les asigne la directiva no tendrán la opción de enviar comentarios.

 - **Encuestas**: establezca el parámetro **receiveSurveysMode** **en habilitado** para permitir que los usuarios asignados a la directiva reciban la encuesta. Para que los usuarios reciban la encuesta y les permita optar por no participar, establezca el parámetro **en enabledUserOverride**. En Teams, los usuarios pueden ir a **Configuración** > **privacidad** y elegir si quieren participar en encuestas. Si se establece el parámetro **en deshabilitado** , se desactivará la característica y los usuarios que tengan asignada la directiva no recibirán la encuesta.

 - **Correo electrónico**: use la marca **AllowEmailCollection** para agregar un campo de correo electrónico.
 - **Colección de registros**: Utilice la marca **AllowLogCollection** para agregar opt-in de la colección de registros para los usuarios. Actualmente, la recopilación de registros solo está habilitada en dispositivos móviles. Para obtener más información sobre qué datos se comparten a través de los registros, [obtenga más información](https://go.microsoft.com/fwlink/?linkid=2168178).

## <a name="create-a-custom-feedback-policy"></a>Crear una directiva de comentarios personalizada

En este ejemplo, creamos una directiva de comentarios denominada Directiva de comentarios de nuevos empleados y desactivamos la posibilidad de enviar comentarios mediante **Enviar comentarios** y la encuesta.

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a>Asignar una directiva de comentarios personalizada a los usuarios

[!INCLUDE [assign-policy](includes/assign-policy.md)]

En este ejemplo, asignamos una directiva personalizada denominada Directiva de comentarios de nuevos empleados a un usuario denominado usuario1.

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a>Temas relacionados

- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
- [Asignar directivas a los usuarios en Teams](policy-assignment-overview.md)
