---
title: 'Directivas de llamadas en Microsoft Teams: características de desvío de llamadas y llamadas'
author: CarolynRowe
ms.author: crowe
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
ms.openlocfilehash: a02df903574c7e7db796294ad90c9e05ab732eb0
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2022
ms.locfileid: "69245778"
---
# <a name="calling-policies-calling-and-call-forwarding-features-in-teams"></a>Directivas de llamadas: Características de llamadas y desvío de llamadas en Teams

En Microsoft Teams, las directivas de llamada controlan qué características de desvío de llamadas y llamadas están disponibles para los usuarios. Las directivas de llamada determinan si un usuario puede realizar llamadas privadas, usar desvío de llamadas o llamadas simultáneas a otros usuarios o números de teléfono externos, enrutar llamadas al correo de voz, enviar llamadas a grupos de llamadas, usar la delegación para llamadas entrantes y salientes, etc.

Puede usar la directiva global (predeterminada para toda la organización) que se crea automáticamente o crear y asignar directivas personalizadas.

## <a name="create-a-custom-calling-policy"></a>Crear una directiva de llamada personalizada

Siga estos pasos para crear una directiva de llamada personalizada.

1. En el panel de navegación izquierdo del Microsoft centro de administración de Teams, vaya a **Directivas de llamadas** de **voz** > .
2. Seleccione **Agregar**.
3. Active o desactive las características que quiera usar en la directiva de llamadas.
    - Por ejemplo, para controlar si los usuarios pueden redirigir las llamadas entrantes al correo de voz, seleccione **Habilitado** o **Controlado por el usuario**. Para evitar el enrutamiento al correo de voz, seleccione **No habilitado**.
4. Seleccione **Guardar**.

## <a name="edit-a-calling-policy"></a>Editar una directiva de llamada

Siga estos pasos para editar una directiva de llamada existente.

1. En el panel de navegación izquierdo del Microsoft centro de administración de Teams, seleccione **Directivas de llamadas** de **voz** > .
2. Haga clic junto a la directiva que desea modificar y, a continuación, seleccione **Editar**.
3. Realice los cambios que desee y, a continuación, haga clic en **Guardar**.

## <a name="assign-a-custom-calling-policy-to-users"></a>Asignar una directiva de llamada personalizada a los usuarios

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a>Configuración de la directiva de llamadas

Estas son las opciones que puede configurar para las directivas de llamada.

### <a name="make-private-calls"></a>Realizar llamadas privadas

Esta configuración controla todas las funcionalidades de llamadas en Teams. Desactive esta opción para desactivar todas las funciones de llamadas en Teams.

### <a name="cloud-recording-for-calling"></a>Grabación en la nube para llamadas

Esta configuración controla si los usuarios pueden grabar llamadas. Esta opción está desactivada de forma predeterminada.

### <a name="transcription"></a>Transcripción

Esta configuración controla si la transcripción de llamadas está disponible para los usuarios. Esta opción está desactivada de forma predeterminada.

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a>Desvío de llamadas y llamadas simultáneas a personas de su organización

Esta configuración controla si las llamadas entrantes se pueden desviar a otros usuarios o pueden llamar a otra persona de la organización al mismo tiempo. Esta opción está activada de forma predeterminada.

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>Desvío de llamadas y llamadas simultáneas a números de teléfono externos

Esta configuración controla si las llamadas entrantes se pueden desviar a un número externo o pueden llamar a un número externo al mismo tiempo. Esta opción está activada de forma predeterminada.

### <a name="voicemail-is-available-for-routing-inbound-calls"></a>El correo de voz está disponible para enrutar llamadas entrantes

Esta configuración permite que las llamadas entrantes se envíen al correo de voz. La configuración predeterminada es **Controlado por el usuario**. Las opciones válidas son:

- **Habilitado** El correo de voz siempre está disponible para las llamadas entrantes.
- **No habilitado**  El correo de voz no está disponible para las llamadas entrantes.
- **Controlado por el usuario** Los usuarios pueden determinar si quieren que el correo de voz esté disponible.

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>Las llamadas entrantes se pueden enrutar a grupos de llamadas

Esta configuración controla si las llamadas entrantes se pueden desviar a un grupo de llamadas. Esta opción está activada de forma predeterminada.

### <a name="delegation-for-inbound-and-outbound-calls"></a>Delegación para llamadas entrantes y salientes

Esta configuración permite redirigir las llamadas entrantes a los delegados, lo que permite a los delegados realizar llamadas salientes en nombre de los usuarios para los que tienen permisos delegados. Esta configuración está activada de forma predeterminada. Para obtener más información, vea [Compartir una línea telefónica con un delegado](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>Evitar la omisión de pago y enviar llamadas a través de la RTC

Si establece esta opción **en Activado** , se enviarán llamadas a través de la RTC y se generarán cargos en lugar de enviarlas a través de la red y omitir los peajes. Esta configuración está desactivada de forma predeterminada.

### <a name="music-on-hold-for-pstn-calls"></a>Música en espera para llamadas RTC

Esta configuración le permite activar o desactivar la música en espera cuando se pone en espera una llamada RTC. Está activada de forma predeterminada. Esta configuración no se aplica a las características de estacionamiento de llamadas y delegados de jefes. Más información sobre cómo [configurar música personalizada](music-on-hold.md).

### <a name="busy-on-busy-when-in-a-call"></a>Ocupado al estar ocupado durante una llamada

Ocupado ocupado cuando está en una llamada (también denominada "opciones de ocupado") le permite configurar cómo se administran las llamadas entrantes cuando un usuario ya está en una llamada o conferencia o tiene una llamada en espera. Las llamadas nuevas o entrantes se pueden rechazar con una señal de ocupado o se pueden enrutar en consecuencia a la configuración no respondida del usuario. Independientemente de cómo estén configuradas sus opciones de ocupado, no se impide que los usuarios de una llamada o conferencia o aquellos con una llamada en espera inicien nuevas llamadas o conferencias. Esta configuración está establecida en **No habilitado** de forma predeterminada.

- **No habilitado** No hay ninguna opción de ocupado habilitada y las llamadas nuevas o entrantes pueden seguir recibiendo al usuario mientras el usuario ya está en una llamada.
- **Habilitado** Las llamadas nuevas o entrantes se rechazarán con una señal de ocupado.
- **Contestar** Se usará la configuración no respondida del usuario, como el enrutamiento al correo de voz o el reenvío a otro usuario.

### <a name="web-pstn-calling"></a>Llamadas RTC en la web

Esta configuración permite a los usuarios llamar a números RTC con el cliente web de Teams. Esta opción está activada de forma predeterminada.

### <a name="real-time-captions-in-teams-calls"></a>Subtítulos en tiempo real en llamadas de Teams

Esta configuración controla si los subtítulos en tiempo real en las llamadas de Teams están disponibles para los usuarios. Esta opción está activada de forma predeterminada.

### <a name="automatically-answer-incoming-meeting-invites"></a>Responder automáticamente a las invitaciones entrantes a reuniones

Esta configuración controla si las invitaciones entrantes a reuniones se responden automáticamente. Está desactivado por defecto. Tenga en cuenta que esta configuración solo se aplica a las invitaciones de reunión entrantes. No se aplica a otros tipos de llamadas.

### <a name="spam-filtering"></a>Filtrado de correo no deseado

Esta configuración le permite controlar el tipo de filtrado de correo no deseado disponible en las llamadas entrantes. Se pueden realizar comprobaciones de Voz interactiva (IVR) básica y captcha. Esta opción está activada de forma predeterminada.

### <a name="sip-devices-can-be-used-for-calls"></a>Los dispositivos SIP se pueden usar para llamadas

Esta configuración permite a los usuarios usar un dispositivo SIP para realizar y recibir llamadas. Esta opción está desactivada de forma predeterminada.

### <a name="open-apps-in-browser-for-incoming-pstn-calls"></a>Abrir aplicaciones en el explorador para llamadas RTC entrantes

Esta configuración controla si las aplicaciones se abren automáticamente en el explorador para las llamadas RTC entrantes a los usuarios. Esto se puede usar para pasar el número de teléfono de un autor de llamada entrante a una aplicación para buscar el registro de cliente asociado mientras se realiza la llamada. Esta configuración está desactivada de forma predeterminada.

Si está activado, deberá especificarse un vínculo a la aplicación en la **dirección URL para abrir aplicaciones en el explorador para las llamadas RTC entrantes** . Puedes usar el marcador de posición {phone} para pasar el número de teléfono (en formato E.164) a la dirección URL proporcionada. O bien, puede proporcionar una dirección URL genérica sin ningún marcador de posición. Esto simplemente iniciará la dirección URL de la lista.

![Captura de pantalla de la configuración de directiva Abrir aplicaciones en el explorador para llamadas RTC entrantes.](media/teams-open-apps-in-browser-pstn.png)

## <a name="related-articles"></a>Artículos relacionados

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

[Asignar directivas a los usuarios en Teams](policy-assignment-overview.md)

[Opciones de conectividad con RTC](pstn-connectivity.md)

[Configurar las opciones de llamada para los usuarios](user-call-settings.md)
