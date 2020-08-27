---
title: Administrar directivas de identificación de llamadas en Microsoft Teams
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
description: Aprenda a usar y administrar directivas de identificación de llamadas en Microsoft Teams para cambiar o bloquear la identificación de llamadas de los usuarios de su organización.
ms.openlocfilehash: c3eabc5a9e906fd514ce92864e08cad5015f6670
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255533"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a>Administrar directivas de identificación de llamadas en Microsoft Teams

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

Como administrador, puede usar directivas de identificación de llamadas en Microsoft Teams para cambiar o bloquear la identificación de llamadas (también conocida como identificador de línea de llamada). De forma predeterminada, se puede ver el número de teléfono de los usuarios de Teams cuando hacen una llamada a un teléfono PSTN y el número de teléfono de los autores de llamadas RTC se puede ver al llamar a un usuario de Teams. Puede usar las directivas de identificación de llamadas para mostrar un número de teléfono alternativo para los usuarios de equipos de su organización o impedir que se muestre un número entrante.

Por ejemplo, cuando los usuarios hacen una llamada, puede cambiar la identificación de llamadas para mostrar el número de teléfono principal de su organización en lugar de los números de teléfono de los usuarios.

Para administrar las directivas de identificación de llamadas, **Voice**vaya a  >  **directivas de identificación de llamadas** de voz en el centro de administración de Microsoft Teams. Puede usar la directiva global (predeterminada para toda la organización) o crear y asignar directivas personalizadas. Los usuarios de su organización obtendrán automáticamente la directiva global, a menos que cree y asigne una directiva personalizada.

## <a name="create-a-custom-caller-id-policy"></a>Crear una directiva de identificación de llamadas personalizada

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **Voice**  >  **directivas de identificación de llamadas**de voz.
2. Haga clic en **Agregar**. <br>
![Captura de pantalla de la nueva página de la Directiva de identificación de llamadas en el centro de administración](media/caller-id-policies-add-policy.png)
3. Escriba un nombre y una descripción para la directiva.
4. Desde aquí, elija la configuración que desee:

    - **Bloquear la identificación de llamadas entrantes**: activa esta configuración para bloquear la identificación de llamadas entrantes de llamadas entrantes.
    - **Invalidar la Directiva de identificación de llamadas**: activa esta configuración para permitir a los usuarios invalidar la configuración de la Directiva relativa a la presentación de su número a destinatarios o no. Esto significa que los usuarios pueden elegir si deseas Mostrar la identificación de llamadas. Para obtener más información, consulte [control del usuario final de la identificación de llamadas salientes](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id).
    - **Cambie la identificación de llamadas por**: establezca la identificación de llamadas que se va a mostrar para los usuarios seleccionando una de las siguientes opciones:

        - **Número de usuario**: muestra el número de usuario. 
        - **Número de servicio**: te permite establecer un número de teléfono de servicio para que se muestre como la identificación de llamadas.
        - **Anonymous**: muestra la identificación de llamadas como anónima.

    - **Reemplazar la identificación de llamadas por este número de servicio**: elige un número de servicio para reemplazar la identificación de llamadas de los usuarios. Esta opción está disponible si seleccionaste **número de servicio** en **reemplazar la identificación de llamadas por**.

5. Haga clic en **Guardar **.

## <a name="edit-a-caller-id-policy"></a>Editar una directiva de identificación de llamadas

Puede editar la directiva global o cualquier directiva personalizada que cree. 

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **Voice**  >  **directivas de identificación de llamadas**de voz.
2. Seleccione la Directiva haciendo clic a la izquierda del nombre de la Directiva y, a continuación, haga clic en **Editar**.
3. Cambie la configuración que desee y, a continuación, haga clic en **Guardar**.

## <a name="assign-a-custom-caller-id-policy-to-users"></a>Asignar una directiva de identificación de llamadas personalizada a los usuarios

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>Temas relacionados

[Nuevo: CsCallingLineIdentity](https://docs.microsoft.com/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

[Asignar directivas a los usuarios de Teams](assign-policies.md)
