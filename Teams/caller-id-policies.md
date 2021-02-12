---
title: Administrar directivas de identificador de llamada en Microsoft Teams
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
description: Aprenda a usar y administrar directivas de identificador de llamada en Microsoft Teams para cambiar o bloquear el identificador de llamada de los usuarios de Teams de su organización.
ms.openlocfilehash: c3eabc5a9e906fd514ce92864e08cad5015f6670
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255533"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a>Administrar directivas de identificador de llamada en Microsoft Teams

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

Como administrador, puede usar las directivas de identificador de llamada de Microsoft Teams para cambiar o bloquear el identificador de llamada (también conocido como identificador de línea de llamada). De forma predeterminada, se puede ver el número de teléfono de los usuarios de Teams cuando hacen una llamada a un teléfono RTC y el número de teléfono de las personas que llaman a RTC se puede ver cuando llaman a un usuario de Teams. Puede usar directivas de identificador de llamada para mostrar un número de teléfono alternativo para los usuarios de Teams de su organización o bloquear la visualización de un número entrante.

Por ejemplo, cuando los usuarios hacen una llamada, puede cambiar el identificador de llamada para que muestre el número de teléfono principal de su organización en lugar de los números de teléfono de los usuarios.

Para administrar las directivas de identificación de llamadas, vaya a las **directivas de** identificador de llamada de voz en el Centro de administración de Microsoft  >   Teams. Puede usar la directiva global (predeterminada para toda la organización) o crear y asignar directivas personalizadas. Los usuarios de su organización obtendrán automáticamente la directiva global, a menos que cree y asigne una directiva personalizada.

## <a name="create-a-custom-caller-id-policy"></a>Crear una directiva de identificador de llamada personalizada

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a las directivas **de** identificador de llamada  >  **de voz.**
2. Haga clic en **Agregar**. <br>
![Captura de pantalla de la página nueva directiva de identificador de llamada en el centro de administración](media/caller-id-policies-add-policy.png)
3. Escriba un nombre y una descripción para la directiva.
4. Desde aquí, elija la configuración que desee:

    - **Bloquear la identificación de llamadas entrantes:** active esta opción para impedir que se muestre el identificador de llamada de las llamadas entrantes.
    - **Invalidar la directiva de identificación de** llamadas: active esta configuración para permitir que los usuarios invaliden o no la configuración de la directiva en cuanto a mostrar o no su número a los autores de llamadas. Esto significa que los usuarios pueden elegir si desea mostrar su identificador de llamada. Para obtener más información, vea [el control por parte del usuario final del identificador de llamada saliente.](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id)
    - **Reemplace el identificador de llamada por:** establezca el identificador de llamada para que se muestre a los usuarios seleccionando una de las opciones siguientes:

        - **Número de usuario:** muestra el número del usuario. 
        - **Número de servicio:** le permite establecer un número de teléfono de servicio para que se muestre como identificador de llamada.
        - **Anónimo:** muestra el identificador de llamada como anónimo.

    - **Reemplazar el identificador de llamada con este número de servicio:** elija un número de servicio para reemplazar el identificador de llamada de los usuarios. Esta opción está disponible si ha seleccionado Número de **servicio en** Reemplazar el identificador de **llamada con.**

5. Haga clic en **Guardar**.

## <a name="edit-a-caller-id-policy"></a>Editar una directiva de identificación de llamadas

Puede editar la directiva global o las directivas personalizadas que cree. 

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a las directivas **de** identificador de llamada  >  **de voz.**
2. Haga clic a la izquierda del nombre de la directiva para seleccionarla y, luego, en **Editar**.
3. Cambie la configuración que desee y, a continuación, haga clic en **Guardar.**

## <a name="assign-a-custom-caller-id-policy-to-users"></a>Asignar una directiva de identificador de llamada personalizada a los usuarios

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>Temas relacionados

[New-CsCallingLineIdentity](https://docs.microsoft.com/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

[Asignar directivas a los usuarios en Teams](assign-policies.md)
