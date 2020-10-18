---
title: Directivas de llamadas en Microsoft Teams
author: SerdarSoysal
ms.author: tonysmit
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: Obtenga información sobre cómo crear, modificar y agregar usuarios a directivas de llamadas personalizadas en Microsoft Teams, así como diversas configuraciones de la Directiva de llamadas.
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callingpolicies.overview
- seo-marvel-apr2020
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 03ec48de66bc5b179b3a1d8cfe006b1789d09a33
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48581066"
---
<a name="calling-policies-in-microsoft-teams"></a>Directivas de llamadas en Microsoft Teams
===================================

En Microsoft Teams, las directivas de llamadas controlan qué características de llamadas y desvío de llamadas están disponibles para los usuarios. Las políticas de llamadas determinan si un usuario puede hacer llamadas privadas, usar el desvío de llamadas o llamar de forma simultánea a otros usuarios o números de teléfono externos, enrutar llamadas al buzón de voz, enviar llamadas a grupos de llamadas, usar la delegación para llamadas entrantes y salientes, etc.

Puede usar la directiva global (predeterminada para toda la organización) que se crea automáticamente o crear y asignar directivas personalizadas.

## <a name="create-a-custom-calling-policy"></a>Crear una directiva de llamadas personalizada

Siga estos pasos para crear una directiva de llamadas personalizada.

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a directivas de llamadas de **voz**  >  **Calling policies**.
2. Seleccione **Agregar**.
3. Activa o desactiva las características que deseas usar en tu Directiva de llamadas.
4. Para controlar si los usuarios pueden enrutar llamadas entrantes al buzón de voz, seleccione **habilitado** o controlado por el **usuario**. Para evitar el enrutamiento al buzón de voz, seleccione **deshabilitado**.
5. Seleccione **Guardar**.

## <a name="edit-a-calling-policy"></a>Modificar una directiva de llamada

Siga estos pasos para editar una directiva de llamadas existente.

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, seleccione directivas de llamadas de **voz**  >  **Calling policies**.
2. Haga clic en junto a la Directiva que desea modificar y, a continuación, seleccione **Editar**.
3. Realice los cambios que desee y, a continuación, haga clic en **Guardar**.

## <a name="assign-a-custom-calling-policy-to-users"></a>Asignar una directiva de llamadas personalizada a los usuarios

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a>Configuración de la Directiva de llamadas

Esta es la configuración que puede configurar para las directivas de llamada.

### <a name="make-private-calls"></a>Realizar llamadas privadas

Esta opción controla todas las capacidades de llamadas de Teams. Desactive esta opción para desactivar toda la funcionalidad de llamadas en Teams.

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a>Desvío de llamadas y llamadas simultáneas a las personas de su organización

Esta configuración controla si las llamadas entrantes pueden desviarse a otros usuarios o pueden llamar a otra persona al mismo tiempo. 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>Desvío de llamadas y llamadas simultáneas a números de teléfono externos

Esta configuración controla si las llamadas entrantes pueden desviarse a un número externo o pueden sonar un número externo al mismo tiempo.

### <a name="voicemail-is-available-for-routing-inbound-calls"></a>El buzón de voz está disponible para enrutar llamadas entrantes

Esta configuración permite que las llamadas entrantes se envíen al buzón de voz. Las opciones válidas son:

- **Habilitado** El buzón de voz siempre está disponible para las llamadas entrantes.
- **Desactivado**  El buzón de voz no está disponible para llamadas entrantes.
- **Controlado** por el usuario Los usuarios pueden determinar si desean que el buzón de voz esté disponible.

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>Las llamadas entrantes se pueden enrutar a grupos de llamadas 

> [!Include [feature preview](includes/preview-feature.md)]

Esta configuración controla si las llamadas entrantes se pueden desviar a un grupo de llamadas.

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a>Permitir la delegación de llamadas entrantes y salientes

> [!Include [feature preview](includes/preview-feature.md)]

Esta configuración permite que las llamadas entrantes se enruten a delegados, lo que permite a los delegados hacer llamadas salientes en nombre de los usuarios para los que han delegado permisos. Para obtener más información, consulte [compartir una línea telefónica con un delegado](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>Evitar la omisión de peajes y enviar llamadas a través de la RTC 

Si se establece **en activado** , se enviarán llamadas a través de la RTC y se provocarán cargos, en lugar de enviarlos por la red y omitir los peajes.

### <a name="busy-on-busy-is-available-while-in-a-call"></a>El uso ocupado está disponible mientras estás en una llamada

Ocupado en ocupado (opciones de ocupado) es una nueva opción que le permite configurar cómo se administran las llamadas entrantes cuando un usuario ya está en una llamada o una conferencia o hace una llamada en espera. Las llamadas nuevas o entrantes pueden rechazarse con una señal de ocupado. Puede habilitar las opciones de ocupado en el nivel de espacio empresarial o en el nivel de usuario. Independientemente de la configuración de las opciones de ocupado, los usuarios de una llamada o conferencia, o aquellos con una llamada en espera, no pueden iniciar nuevas llamadas o conferencias. Esta opción está deshabilitada de forma predeterminada.

### <a name="allow-web-pstn-calling"></a>Permitir llamadas RTC en Web

Esta configuración permite a los usuarios llamar a números de RTC mediante el cliente web de Teams.

### <a name="allow-music-on-hold"></a>Permitir música en espera

Esta configuración le permite activar o desactivar la música en espera cuando una persona que llama RTC se coloca en espera. Está activada de forma predeterminada. Esta configuración no se aplica a las características del delegado llamar y el jefe, y actualmente solo está disponible a través de PowerShell.

## <a name="related-topics"></a>Temas relacionados

[Set-CSTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)

[Asignar directivas a los usuarios de Teams](assign-policies.md)
