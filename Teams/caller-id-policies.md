---
title: Administrar directivas del id. de llamada en Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: jastark
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
description: Obtenga información sobre cómo usar y administrar directivas de identificación de llamadas en Microsoft Teams para cambiar o bloquear el identificador de llamada de los usuarios de Teams de su organización.
ms.openlocfilehash: cd15245523cdc3f5fb3625a2b4cfdae4deebb7d3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102786"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a>Administrar directivas del id. de llamada en Microsoft Teams

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

Como administrador, puede usar directivas de identificación de llamadas en Microsoft Teams para cambiar o bloquear el identificador de llamada (también conocido como identificador de línea de llamada). De forma predeterminada, el número de teléfono de los usuarios de Teams se puede ver cuando hacen una llamada a un teléfono RTC y el número de teléfono de las llamadas RTC se puede ver cuando llaman a un usuario de Teams. Puede usar directivas de identificación de llamadas para mostrar un número de teléfono alternativo para los usuarios de Teams de su organización o bloquear la visualización de un número entrante.

Por ejemplo, cuando los usuarios hacen una llamada, puede cambiar el identificador de llamada para mostrar el número de teléfono principal de su organización en lugar de los números de teléfono de los usuarios.

Para administrar las directivas de identificador de llamadas, vaya **a** Directivas de identificación de llamadas  >  **de** voz en el Centro de administración de Microsoft Teams. Puede usar la directiva global (predeterminada para toda la organización) o crear y asignar directivas personalizadas. Los usuarios de su organización obtendrán automáticamente la directiva global, a menos que cree y asigne una directiva personalizada.

## <a name="create-a-custom-caller-id-policy"></a>Crear una directiva de identificación de llamadas personalizada

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya **a** Directivas de identificación de llamadas  >  **de voz.**
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

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya **a** Directivas de identificación de llamadas  >  **de voz.**
2. Haga clic a la izquierda del nombre de la directiva para seleccionarla y, luego, en **Editar**.
3. Cambie la configuración que desee y, a continuación, haga clic en **Guardar.**

## <a name="assign-a-custom-caller-id-policy-to-users"></a>Asignar una directiva de identificador de llamada personalizada a los usuarios

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>Temas relacionados

[New-CsCallingLineIdentity](/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

[Asignar directivas a los usuarios en Teams](assign-policies.md)