---
title: Administrar directivas de comentarios en Microsoft Teams
author: cichur
ms.author: v-cichur
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
description: Obtenga información sobre cómo usar las directivas de comentarios para controlar si los usuarios de Teams de su organización pueden enviar comentarios sobre Teams a Microsoft.
ms.openlocfilehash: e2415204650ce47f875e432f062fd4a5e0438cd6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804700"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a>Administrar directivas de comentarios en Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Los usuarios de su organización pueden enviar comentarios sobre Teams a Microsoft para hacernos saber cómo lo hacemos, directamente desde los clientes web y de escritorio de Teams. Mejoramos continuamente la experiencia de Teams y usamos estos comentarios para mejorar Teams.

> [!NOTE]
> Las directivas de comentarios no están disponibles en las implementaciones GCC, GCC High o DOD.

**Característica Enviar comentarios**

Los usuarios pueden enviarnos comentarios y sugerencias sobre Teams si van **a ayudarnos**  >  **a enviar comentarios** en Teams. Los datos  enviados a través de Enviar comentarios se consideran "Datos de soporte técnico" en virtud de su contrato de Microsoft 365 u Office 365, incluida la información que, de otro modo, se consideraría "Datos del cliente" o "Datos personales".

![Captura de pantalla de la opción Enviar comentarios en Teams](media/manage-feedback-policies-in-teams-give-feedback.png)

**Encuestas**

Los usuarios también pueden puntuar su experiencia con Teams y enviarnos detalles sobre la clasificación que dan. Esta encuesta emergente se muestra a los usuarios de vez en cuando en Teams. Cuando un usuario hace clic **en Proporcionar** comentarios en la notificación, se muestra la encuesta para que la complete.

![Captura de pantalla de la notificación y el formulario de encuesta en Teams](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a>Establecer si los usuarios pueden enviar comentarios sobre Teams a Microsoft

Como administrador, puede controlar si los usuarios de su organización  pueden enviar comentarios sobre Teams a Microsoft mediante comentarios y si reciben la encuesta. De forma predeterminada, a todos los usuarios de su organización se  les asigna automáticamente la directiva global (predeterminada para toda la organización) y la característica Enviar comentarios y la encuesta están habilitadas en la directiva. La excepción es Teams para el sector educativo, donde las características están habilitadas para los profesores y deshabilitadas para los alumnos.

Puede editar la directiva global o crear y asignar una directiva personalizada. Después de editar la directiva global o asignar una directiva personalizada, los cambios pueden tardar unas horas en tener efecto.

Por ejemplo, quiere permitir que todos los usuarios de  su organización envíen comentarios a través de enviar comentarios y recibir encuestas excepto para los nuevos empleados en formación. En este escenario, creará una directiva personalizada para desactivar ambas características y asignarla a los nuevos empleados. Todos los demás usuarios de su organización obtienen la directiva global con las características activadas.  

Puede administrar las directivas de comentarios con PowerShell. Use el cmdlet **New-CsTeamsFeedbackPolicy** *[](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)(que* se encuentra aquí) para crear una directiva personalizada y el cmdlet **Grant-CsTeamsFeedbackPolicy** para asignarlo a uno o varios usuarios o grupos de usuarios, como un grupo de seguridad o un grupo de distribución.

Para desactivar y activar las características, establezca los parámetros siguientes:

 - **Enviar comentarios:** establezca el **parámetro userInitiatedMode** en **"enabled"** para permitir que los usuarios asignados a la directiva puedan enviar comentarios. Al establecer el parámetro en **deshabilitado** se desactiva la característica y los usuarios asignados a la directiva no tienen la opción de proporcionar comentarios.
 - **Encuestas:** establezca el **parámetro receiveSurveysMode** en **habilitado** para permitir que los usuarios a los que se les asigne la directiva reciban la encuesta. Para que los usuarios reciban la encuesta y permitan que no puedan participar, establezca el parámetro **"enabledUserOverride" en "enabledUserOverride".** En Teams, los usuarios pueden ir a Configuración de privacidad y elegir si  >   desean participar en encuestas. Al establecer el parámetro en **deshabilitado** se desactiva la característica y los usuarios asignados a la directiva no recibirán la encuesta.

## <a name="create-a-custom-feedback-policy"></a>Crear una directiva de comentarios personalizada

En este ejemplo, creamos una directiva de comentarios denominada Directiva de comentarios de nuevos empleados y desactivamos la capacidad de enviar comentarios mediante Enviar comentarios **y** la encuesta.

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a>Asignar una directiva de comentarios personalizada a los usuarios

[!INCLUDE [assign-policy](includes/assign-policy.md)]

En este ejemplo, asignamos una directiva personalizada denominada Directiva de comentarios de nuevos empleados a un usuario llamado usuario1.

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a>Temas relacionados

- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
- [Asignar directivas a los usuarios en Teams](assign-policies.md)