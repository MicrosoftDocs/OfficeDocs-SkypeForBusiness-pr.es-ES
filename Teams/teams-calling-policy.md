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
description: Aprenda a crear, modificar y agregar usuarios a directivas de llamadas personalizadas en Microsoft Teams, así como a varias configuraciones de directiva de llamada.
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

En Microsoft Teams, las directivas de llamadas controlan qué características de llamadas y desvía llamadas están disponibles para los usuarios. Las directivas de llamadas determinan si un usuario puede realizar llamadas privadas, usar el reenvío de llamadas o llamar simultáneamente a otros usuarios o números de teléfono externos, enrutar llamadas al correo de voz, enviar llamadas a grupos de llamadas, usar la delegación para llamadas entrantes y salientes, y así sucesivamente.

Puede usar la directiva global (predeterminada para toda la organización) que se crea automáticamente o crear y asignar directivas personalizadas.

## <a name="create-a-custom-calling-policy"></a>Crear una directiva de llamadas personalizada

Siga estos pasos para crear una directiva de llamadas personalizada.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a las directivas  >  **de llamadas de voz.**
2. Seleccione **Agregar**.
3. Active o desactive las características que quiera usar en su directiva de llamadas.
4. Para controlar si los usuarios pueden enrutar llamadas entrantes al correo de voz, seleccione **Habilitado** o **Controlado por usuario.** Para evitar el enrutamiento al correo de voz, seleccione **Deshabilitado.**
5. Seleccione **Guardar**.

## <a name="edit-a-calling-policy"></a>Editar una directiva de llamada

Siga estos pasos para editar una directiva de llamadas existente.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, seleccione Directivas  >  **de llamadas de voz.**
2. Haga clic junto a la directiva que desea modificar y, a continuación, **seleccione Editar.**
3. Realice los cambios que desee y, a continuación, haga clic en **Guardar.**

## <a name="assign-a-custom-calling-policy-to-users"></a>Asignar una directiva de llamadas personalizada a los usuarios

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a>Configuración de la directiva de llamadas

Esta es la configuración que puede configurar para las directivas de llamadas.

### <a name="make-private-calls"></a>Realizar llamadas privadas

Esta configuración controla todas las capacidades de llamadas en Teams. Desactive esta opción para desactivar todas las funciones de llamadas en Teams.

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a>Call forwarding and simultaneousing to people in your organization

Esta configuración controla si las llamadas entrantes se pueden reenviar a otros usuarios o pueden llamar a otra persona al mismo tiempo. 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>Reenvío de llamadas y llamadas simultáneas a números de teléfono externos

Esta configuración controla si las llamadas entrantes pueden desviarse a un número externo o llamar a un número externo al mismo tiempo.

### <a name="voicemail-is-available-for-routing-inbound-calls"></a>El correo de voz está disponible para enrutar llamadas entrantes

Esta configuración permite que las llamadas entrantes se envíen al correo de voz. Las opciones válidas son:

- **Habilitado** El correo de voz siempre está disponible para las llamadas entrantes.
- **Deshabilitado**  El correo de voz no está disponible para las llamadas entrantes.
- **Controlado por el usuario** Los usuarios pueden determinar si quieren que el correo de voz esté disponible.

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>Las llamadas entrantes se pueden enrutar a grupos de llamadas 

> [!Include [feature preview](includes/preview-feature.md)]

Esta configuración controla si las llamadas entrantes se pueden reenviar a un grupo de llamadas.

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a>Permitir la delegación para llamadas entrantes y salientes

> [!Include [feature preview](includes/preview-feature.md)]

Esta configuración permite enrutar las llamadas entrantes a los delegados, lo que permite a los delegados realizar llamadas salientes en nombre de los usuarios para los que tienen permisos delegados. Para obtener más información, [vea Compartir una línea telefónica con un delegado.](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>Evitar la omisión de pago y enviar llamadas a través de RTC 

Establecer esta opción **en "On"** enviará llamadas a través de LA RTC y conllevará cargos en lugar de enviarlas a través de la red y omitir los números de pago.

### <a name="busy-on-busy-is-available-while-in-a-call"></a>Ocupado está disponible durante una llamada

Ocupado en Ocupado (Opciones de disponibilidad) es una nueva configuración que le permite configurar cómo se gestionan las llamadas entrantes cuando un usuario ya está en una llamada o en una conferencia o tiene una llamada en espera. Las llamadas nuevas o entrantes se pueden rechazar con una señal de ocupado. Puede habilitar las opciones de disponibilidad en el nivel de inquilino o en el nivel de usuario. Independientemente de cómo se configuren las opciones de ocupado, no se impide que los usuarios de una llamada o conferencia o aquellos con una llamada en espera inicien nuevas llamadas o conferencias. Esta configuración está deshabilitada de forma predeterminada.

### <a name="allow-web-pstn-calling"></a>Permitir llamadas RTC web

Esta configuración permite a los usuarios llamar a números RTC con el cliente web de Teams.

### <a name="allow-music-on-hold"></a>Permitir música en espera

Esta configuración le permite activar o desactivar la música en espera cuando un autor de llamada RTC está en espera. Está activada de forma predeterminada. Esta configuración no se aplica a las características de estacionar llamadas y delegados por jefe, y actualmente solo está disponible a través de PowerShell.

## <a name="related-topics"></a>Temas relacionados

[Set-CSTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)

[Asignar directivas a los usuarios en Teams](assign-policies.md)
