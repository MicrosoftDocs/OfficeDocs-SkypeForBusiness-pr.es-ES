---
title: Administrar directivas de comentarios en Microsoft Teams
author: serdarsoysal
ms.author: serdars
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
description: Obtenga información sobre cómo usar directivas de comentarios para controlar si Teams usuarios de su organización pueden enviar comentarios sobre Teams a Microsoft.
ms.openlocfilehash: 4cb8914a793ddb6342b047caada087006da8f670
ms.sourcegitcommit: 3a8bec0445cee5cd776fb1991f093a0ec4351852
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2021
ms.locfileid: "60605776"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a>Administrar directivas de comentarios en Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Los usuarios de su organización pueden enviar comentarios sobre Microsoft Teams para hacernos saber cómo estamos haciendo directamente desde el escritorio Teams, clientes web y móviles. Estamos mejorando continuamente la experiencia Teams y usamos estos comentarios para mejorar Teams mejor.

> [!NOTE]
> Las directivas de comentarios no están disponibles en implementaciones GCC, GCC high o DOD.

**La **característica Enviar comentarios****

Los usuarios pueden enviarnos comentarios y sugerencias sobre Teams a nosotros yendo a Ayudar a enviar comentarios en  >   Teams escritorio y web.


![Opción Enviar comentarios en Teams](media/manage-feedback-policies-in-teams-give-feedback.png)

Obtener acceso a los comentarios en **dispositivos móviles Configuración**  >  **ayuda & enviar comentarios.**  >  

![Opción Enviar comentarios en Teams móvil](media/feedback3.jpg)

 Los datos  enviados  a través de Enviar comentarios y Enviar comentarios se consideran "Datos de soporte técnico" en virtud de su contrato de Microsoft 365 o Office 365, incluida la información que de otro modo se consideraría "Datos del cliente" o "Datos personales".



**Encuestas**

Los usuarios también pueden calificar su experiencia con Teams y enviarnos detalles sobre la clasificación que dan. Esta encuesta emergente se muestra a los usuarios de vez en cuando en Teams. Cuando un usuario selecciona **Proporcionar comentarios** en la notificación, se muestra la encuesta para que se complete.

![la notificación de encuesta y el formulario en Teams.](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a>Establecer si los usuarios pueden enviar comentarios sobre Teams a Microsoft

Como administrador, puede controlar si los usuarios de su organización pueden enviar comentarios sobre Teams a Microsoft y si reciben la encuesta. De forma predeterminada, a todos los usuarios de su organización se les asigna automáticamente la directiva global (predeterminada para toda la organización) y la característica de comentarios y la encuesta están habilitadas en la directiva. La excepción es Teams para Educación, donde las características están habilitadas para los profesores y deshabilitadas para los alumnos.

Puede editar la directiva global o crear y asignar una directiva personalizada. Después de editar la directiva global o asignar una directiva personalizada, los cambios pueden tardar unas horas en tener efecto.

Por ejemplo, quiere permitir que todos los usuarios de su organización envíen comentarios y reciban encuestas, excepto los nuevos empleados en el aprendizaje. En este escenario, creará una directiva personalizada para desactivar ambas características y asignarla a nuevos empleados. Todos los demás usuarios de su organización obtienen la directiva global con las características activadas.  

Puede administrar directivas de comentarios con PowerShell. Use el cmdlet [ **New-CsTeamsFeedbackPolicy**](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell) para crear una directiva personalizada. Use el cmdlet **Grant-CsTeamsFeedbackPolicy** para asignarlo a uno o varios usuarios o grupos de usuarios, como un grupo de seguridad o un grupo de distribución. Use **Set-CsTeamsFeedbackPolicy** para establecer marcas específicas.

Para desactivar y activar las características, establezca los siguientes parámetros:

 - **Enviar comentarios:** Establezca el **parámetro userInitiatedMode** en **habilitado** para permitir que los usuarios a los que se les asigne la directiva puedan enviar comentarios. Al establecer el parámetro en **deshabilitado** se desactiva la característica y los usuarios a los que se les asigna la directiva no tienen la opción de enviar comentarios.

 - **Encuestas:** establezca el **parámetro receiveSurveysMode** en **habilitado** para permitir que los usuarios a los que se les asigne la directiva reciban la encuesta. Para que los usuarios reciban la encuesta y les permitan optar por no participar, establezca el parámetro en **enabledUserOverride**. En Teams, los usuarios pueden ir **a Configuración** privacidad y elegir si quieren participar en  >   encuestas. Al establecer el parámetro en **deshabilitado,** se desactiva la característica y los usuarios a los que se les asigna la directiva no recibirán la encuesta.

 - **Correo** electrónico: use la **marca AllowEmailCollection** para agregar un campo de correo electrónico.
 - **Colección de registros:** use la **marca AllowLogCollection** para agregar la suscripción a la colección de registros para los usuarios. Actualmente, la colección de registros solo está habilitada en dispositivos móviles. Para obtener más información sobre qué datos se comparten a través de registros, [obtenga más información.](https://go.microsoft.com/fwlink/?linkid=2168178)

## <a name="create-a-custom-feedback-policy"></a>Crear una directiva de comentarios personalizada

En este ejemplo, creamos una directiva de comentarios denominada Nueva directiva de comentarios de contratación y desactivamos la capacidad de enviar comentarios a través de **Enviar** comentarios y la encuesta.

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a>Asignar una directiva de comentarios personalizados a los usuarios

[!INCLUDE [assign-policy](includes/assign-policy.md)]

En este ejemplo, asignamos una directiva personalizada denominada Nueva directiva de comentarios de contratación a un usuario denominado usuario1.

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a>Temas relacionados

- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
- [Asignar directivas a los usuarios en Teams](policy-assignment-overview.md)
