---
title: 'Directivas de llamadas en Microsoft Teams: características de desvío de llamadas y llamadas'
author: SerdarSoysal
ms.author: tonysmit
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: Obtenga información sobre cómo crear, modificar y agregar usuarios a directivas de llamada personalizadas en Microsoft Teams, así como a varias configuraciones de directivas de llamada.
ms.localizationpriority: medium
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
ms.openlocfilehash: 6a52b30e1ced457377d7dd1c820192cb856827ba
ms.sourcegitcommit: 3b86e55787c34da76428d6915964ac4f3c6239fc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2022
ms.locfileid: "65601680"
---
# <a name="calling-and-call-forwarding-in-teams"></a>Llamadas y desvío de llamadas en Teams

En Microsoft Teams, las directivas de llamada controlan qué características de desvío de llamadas y llamadas están disponibles para los usuarios. Las directivas de llamada determinan si un usuario puede realizar llamadas privadas, usar desvío de llamadas o llamadas simultáneas a otros usuarios o números de teléfono externos, enrutar llamadas al correo de voz, enviar llamadas a grupos de llamadas, usar la delegación para llamadas entrantes y salientes, etc.

Puede usar la directiva global (predeterminada para toda la organización) que se crea automáticamente o crear y asignar directivas personalizadas.

## <a name="create-a-custom-calling-policy"></a>Crear una directiva de llamada personalizada

Siga estos pasos para crear una directiva de llamada personalizada.

1. En el panel de navegación izquierdo del Microsoft Teams centro de administración, vaya a **Directivas** **de VoiceCalling** > .
2. Seleccione **Agregar**.
3. Active o desactive las características que quiera usar en la directiva de llamadas.
4. Para controlar si los usuarios pueden redirigir las llamadas entrantes al correo de voz, seleccione **Habilitado** o **Controlado por el usuario**. Para evitar el enrutamiento al correo de voz, seleccione **Deshabilitado**.
5. Seleccione **Guardar**.

## <a name="edit-a-calling-policy"></a>Editar una directiva de llamada

Siga estos pasos para editar una directiva de llamada existente.

1. En el panel de navegación izquierdo del Microsoft Teams centro de administración, seleccione **Directivas de Llamada de** **voz** > .
2. Haga clic junto a la directiva que desea modificar y, a continuación, seleccione **Editar**.
3. Realice los cambios que desee y, a continuación, haga clic en **Guardar**.

## <a name="assign-a-custom-calling-policy-to-users"></a>Asignar una directiva de llamada personalizada a los usuarios

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a>Configuración de la directiva de llamadas

Estas son las opciones que puede configurar para las directivas de llamada.

### <a name="make-private-calls"></a>Realizar llamadas privadas

Esta configuración controla todas las funcionalidades de llamada de Teams. Desactívalo para desactivar todas las funciones de llamadas en Teams.

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a>Desvío de llamadas y llamadas simultáneas a personas de su organización

Esta configuración controla si las llamadas entrantes se pueden desviar a otros usuarios o llamar a otra persona al mismo tiempo.

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>Desvío de llamadas y llamadas simultáneas a números de teléfono externos

Esta configuración controla si las llamadas entrantes se pueden desviar a un número externo o pueden llamar a un número externo al mismo tiempo.

### <a name="voicemail-is-available-for-routing-inbound-calls"></a>El correo de voz está disponible para enrutar llamadas entrantes

Esta configuración permite que las llamadas entrantes se envíen al correo de voz. Las opciones válidas son:

- **Habilitado** El correo de voz siempre está disponible para las llamadas entrantes.
- **Deshabilitado**  El correo de voz no está disponible para las llamadas entrantes.
- **Controlado por el usuario** Los usuarios pueden determinar si quieren que el correo de voz esté disponible.

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>Las llamadas entrantes se pueden enrutar a grupos de llamadas

Esta configuración controla si las llamadas entrantes se pueden desviar a un grupo de llamadas.

### <a name="delegation-for-inbound-and-outbound-calls"></a>Delegación para llamadas entrantes y salientes

Esta configuración permite redirigir las llamadas entrantes a los delegados, lo que permite a los delegados realizar llamadas salientes en nombre de los usuarios para los que tienen permisos delegados. Para obtener más información, vea [Compartir una línea telefónica con un delegado](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>Evitar la omisión de pago y enviar llamadas a través de la RTC

Si establece esta opción **en Activado** , se enviarán llamadas a través de la RTC y se generarán cargos en lugar de enviarlas a través de la red y omitir los peajes.

### <a name="busy-on-busy-is-available-when-in-a-call"></a>Ocupado ocupado está disponible cuando está en una llamada

Ocupado en ocupado (opciones de ocupado) le permite configurar cómo se gestionan las llamadas entrantes cuando un usuario ya está en una llamada o conferencia o tiene una llamada en espera. Las llamadas nuevas o entrantes se pueden rechazar con una señal de ocupado o se pueden enrutar en consecuencia a la configuración no respondida del usuario. Puede habilitar las opciones de ocupado en el nivel de inquilino o en el nivel de usuario. Independientemente de cómo estén configuradas sus opciones de ocupado, no se impide que los usuarios de una llamada o conferencia o aquellos con una llamada en espera inicien nuevas llamadas o conferencias. Esta configuración está deshabilitada de forma predeterminada.

### <a name="web-pstn-calling"></a>Llamadas RTC en la web

Esta configuración permite a los usuarios llamar a números RTC con el cliente web de Teams.

### <a name="automatically-answer-incoming-meeting-invites"></a>Responder automáticamente a las invitaciones entrantes a reuniones

Esta configuración controla si las invitaciones entrantes a reuniones se responden automáticamente. Está desactivado por defecto. Tenga en cuenta que esta configuración solo se aplica a las invitaciones de reunión entrantes. No se aplica a otros tipos de llamadas.

### <a name="allow-music-on-hold"></a>Permitir música en espera

Esta configuración le permite activar o desactivar la música en espera cuando se pone en espera una llamada RTC. Está activada de forma predeterminada. Esta configuración no se aplica a las características de estacionamiento de llamadas y delegados de jefes.

### <a name="allow-sip-devices-calling"></a>Permitir llamadas de dispositivos SIP

Esta configuración permite a los usuarios usar un dispositivo SIP para realizar y recibir llamadas.

### <a name="spam-filtering"></a>Filtrado de correo no deseado

Esta configuración le permite controlar el tipo de filtrado de correo no deseado disponible en las llamadas entrantes.

### <a name="call-recording-live-captions-and-transcription"></a>Grabación de llamadas, subtítulos en directo y transcripción

Esta configuración le permite controlar si la grabación de llamadas, los subtítulos en directo y la transcripción están disponibles para los usuarios.

## <a name="related-articles"></a>Artículos relacionados

[New-CsTeamsCallingPolicy](/powershell/module/skype/new-csteamscallingpolicy)

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

[Get-CsTeamsCallingPolicy](/powershell/module/skype/get-csteamscallingpolicy)

[Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy)

[Remove-CsTeamsCallingPolicy](/powershell/module/skype/remove-csteamscallingpolicy)

[Asignar directivas a los usuarios en Teams](policy-assignment-overview.md)
