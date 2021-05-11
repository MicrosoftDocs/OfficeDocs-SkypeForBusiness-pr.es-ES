---
title: Administrar directivas del id. de llamada en Microsoft Teams
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: roykuntz; jens
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.voice.callinglineid.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo usar y administrar directivas de identificador de llamadas en Microsoft Teams para cambiar o bloquear el identificador de llamada de Teams usuarios de su organización.
ms.openlocfilehash: cd928af5213a1e6fa927662adaba0fefecb687d5
ms.sourcegitcommit: 83f14c4c79559ef28357ff076938e52b369fc0c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2021
ms.locfileid: "52308379"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a>Administrar directivas del id. de llamada en Microsoft Teams

> [!NOTE]
> Para establecer el identificador de llamada en un número de teléfono de cuenta de recurso y establecer el nombre de la parte que llama, use los cmdlets de PowerShell New-CsCallingLineIdentity o Set-CsCallingLineIdentity en el módulo de PowerShell de Teams 2.3.1 o posterior. (Estas opciones no están disponibles actualmente en el centro Microsoft Teams administración). 

De forma predeterminada, cuando un Teams realiza una llamada a un teléfono RTC, el número de teléfono del Teams usuario está visible. Del mismo modo, cuando un autor de la llamada RTC realiza una llamada a un Teams, el número de teléfono del autor de la llamada RTC está visible.

Como administrador, puede usar directivas de identificación de llamadas para cambiar o bloquear el identificador de llamada (también conocido como identificador de línea de llamada). Puede usar directivas de identificación de llamadas para mostrar un número de teléfono alternativo para los usuarios de Teams de su organización, bloquear el número de teléfono saliente, bloquear la visualización de un número entrante o establecer el nombre de la parte que llama (CNAM). Por ejemplo, cuando un usuario realiza una llamada, puede cambiar el identificador de llamada para mostrar el número de teléfono principal y el nombre de la empresa de su organización en lugar del número de teléfono del usuario.

Para administrar las directivas de identificación de llamadas, vaya **a** Directivas de identificador de llamadas de voz en el centro de Microsoft Teams de  >   llamadas. Puede usar la directiva global (predeterminada para toda la organización) o crear y asignar directivas personalizadas. Los usuarios de su organización obtendrán automáticamente la directiva global, a menos que cree y asigne una directiva personalizada.

## <a name="create-a-custom-caller-id-policy"></a>Crear una directiva de identificación de llamadas personalizada

1. En el panel de navegación izquierdo del Microsoft Teams de administración, vaya **a** Directivas de identificación de llamadas  >  **de voz.**
2. Haga clic en **Agregar**. <br>
![Captura de pantalla de la nueva página de directiva de identificación de llamadas en el Centro de administración](media/caller-id-policies-add-policy.png)
3. Escriba un nombre y una descripción para la directiva.
4. Desde aquí, elija la configuración que desee:

    - **Bloquear el identificador de llamada entrante:** active esta configuración para bloquear la visualización del identificador de llamada de las llamadas entrantes.
    - **Invalidar la directiva de identificador de** llamada: active esta configuración para permitir que los usuarios invaliden la configuración de la directiva en relación con la visualización de su número en callees o no. Esto significa que los usuarios pueden elegir si desea mostrar su identificador de llamada. Para obtener más información, vea [Control de usuario final del identificador de llamada saliente.](./how-can-caller-id-be-used-in-your-organization.md#end-user-control-of-outbound-caller-id)
    - **Reemplace el identificador de llamada por:** Establezca el id. de autor de la llamada para que se muestre para los usuarios seleccionando una de las siguientes opciones:

        - **Número de usuario:** muestra el número del usuario. 
        - **Número de servicio:** le permite establecer un número de teléfono de servicio para que se muestre como el identificador de llamada.
        - **Anónimo:** muestra el identificador de llamada como Anónimo.

    - **Reemplace el identificador de llamada por este número de servicio:** elija un número de servicio para reemplazar el id. de autor de la llamada de los usuarios. Esta opción está disponible si ha seleccionado Número **de servicio en** Reemplazar el identificador de llamada **con**.

5. Haga clic en **Guardar**.

## <a name="edit-a-caller-id-policy"></a>Editar una directiva de identificador de llamada

Puede editar la directiva global o las directivas personalizadas que cree. 

1. En el panel de navegación izquierdo del Microsoft Teams de administración, vaya **a** Directivas de identificación de llamadas  >  **de voz.**
2. Haga clic a la izquierda del nombre de la directiva para seleccionarla y, luego, en **Editar**.
3. Cambie la configuración que desee y, a continuación, haga clic en **Guardar.**

## <a name="assign-a-custom-caller-id-policy-to-users"></a>Asignar una directiva de identificador de llamada personalizada a los usuarios

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>Temas relacionados

[New-CsCallingLineIdentity](/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

[Set-CsCallingLineIdentity](/powershell/module/skype/set-cscallinglineidentity?view=skype-ps)

[Asignar directivas a los usuarios en Teams](assign-policies.md)