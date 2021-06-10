---
title: Administrar directivas de comentarios en Microsoft Teams
author: cichur
ms.author: v-cichur
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
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo usar directivas de comentarios para controlar si Teams usuarios de su organización pueden enviar comentarios sobre Teams a Microsoft.
ms.openlocfilehash: 66f14467e66456f244664a8273e0ff962297c05f
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656726"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a>Administrar directivas de comentarios en Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Los usuarios de su organización pueden enviar comentarios sobre Teams a Microsoft para que sepamos cómo estamos, directamente desde los clientes Teams de escritorio y web. Estamos mejorando continuamente la experiencia Teams y usamos estos comentarios para mejorar Teams mejor.

> [!NOTE]
> Las directivas de comentarios no están disponibles en implementaciones GCC, GCC high o DOD.

**La característica Enviar comentarios**

Los usuarios pueden enviar comentarios y sugerencias sobre Teams a nosotros yendo a **Ayuda**  >  **para enviar comentarios** en Teams. Los datos  enviados a través de Enviar comentarios se consideran "Datos de soporte técnico" en virtud de su contrato de Microsoft 365 o Office 365, incluida la información que de otro modo se consideraría "Datos del cliente" o "Datos personales".

![Captura de pantalla de la opción Enviar comentarios en Teams](media/manage-feedback-policies-in-teams-give-feedback.png)

**Encuestas**

Los usuarios también pueden calificar su experiencia con Teams y enviarnos detalles sobre la clasificación que dan. Esta encuesta emergente se muestra a los usuarios de vez en cuando en Teams. Cuando un usuario selecciona **Proporcionar comentarios** en la notificación, se muestra la encuesta para que se complete.

![la notificación de encuesta y el formulario en Teams](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a>Establecer si los usuarios pueden enviar comentarios sobre Teams a Microsoft

Como administrador, puede controlar si los usuarios de su organización pueden  enviar comentarios sobre Teams a Microsoft a través de Enviar comentarios y si reciben la encuesta. De forma predeterminada, a todos los usuarios de su organización se les  asigna automáticamente la directiva global (predeterminada para toda la organización) y la característica y la encuesta Dele comentarios están habilitadas en la directiva. La excepción es Teams educación, donde las características están habilitadas para los profesores y deshabilitadas para los alumnos.

Puede editar la directiva global o crear y asignar una directiva personalizada. Después de editar la directiva global o asignar una directiva personalizada, los cambios pueden tardar unas horas en tener efecto.

Por ejemplo, quiere permitir que todos los usuarios de  su organización envíen comentarios a través de Enviar comentarios y recibir encuestas, excepto los nuevos empleados en formación. En este escenario, creará una directiva personalizada para desactivar ambas características y asignarla a nuevos empleados. Todos los demás usuarios de su organización obtienen la directiva global con las características activadas.  

Puede administrar directivas de comentarios con PowerShell. Use el cmdlet **New-CsTeamsFeedbackPolicy,** que se puede encontrar *[aquí,](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)* para crear una directiva personalizada. Use el cmdlet **Grant-CsTeamsFeedbackPolicy** para asignarlo a uno o varios usuarios o grupos de usuarios, como un grupo de seguridad o un grupo de distribución. Use **Set-CsTeamsFeedbackPolicy** para establecer marcas específicas.

Para desactivar y activar las características, establezca los siguientes parámetros:

 - **Enviar comentarios:** Establezca el **parámetro userInitiatedMode** en **habilitado** para permitir que los usuarios a los que se les asigne la directiva puedan enviar comentarios. Al establecer el parámetro en **deshabilitado** se desactiva la característica y los usuarios a los que se les asigna la directiva no tienen la opción de enviar comentarios.
 - **Encuestas:** establezca el **parámetro receiveSurveysMode** en **habilitado** para permitir que los usuarios a los que se les asigne la directiva reciban la encuesta. Para que los usuarios reciban la encuesta y les permitan optar por no participar, establezca el parámetro en **enabledUserOverride**. En Teams, los usuarios pueden ir **a Configuración** privacidad y elegir si quieren participar en  >   encuestas. Al establecer el parámetro en **deshabilitado,** se desactiva la característica y los usuarios a los que se les asigna la directiva no recibirán la encuesta.
 - **Correo** electrónico: use la **marca AllowEmailCollection** para agregar un campo de correo electrónico.

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
- [Asignar directivas a los usuarios en Teams](assign-policies.md)
