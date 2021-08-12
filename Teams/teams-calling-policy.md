---
title: 'Directivas de llamadas en Microsoft Teams: características de llamadas y reenvío de llamadas'
author: SerdarSoysal
ms.author: tonysmit
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: Obtenga información sobre cómo crear, modificar y agregar usuarios a directivas de llamadas personalizadas en Microsoft Teams, así como varias configuraciones de directiva de llamadas.
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
ms.openlocfilehash: e38a566e025c711a9b17a050137e67af7507e63d5c5e829ba4448ee4a1577790
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54309249"
---
#  <a name="calling-and-call-forwarding-in-teams"></a>Llamadas y reenvío de llamadas en Teams

En Microsoft Teams, las directivas de llamada controlan las características de llamada y desvío de llamadas que están disponibles para los usuarios. Las directivas de llamadas determinan si un usuario puede realizar llamadas privadas, usar el reenvío de llamadas o llamadas simultáneas a otros usuarios o números de teléfono externos, enrutar llamadas al correo de voz, enviar llamadas a grupos de llamadas, usar la delegación para llamadas entrantes y salientes, y así sucesivamente.

Puede usar la directiva global (predeterminada para toda la organización) que se crea automáticamente o crear y asignar directivas personalizadas.

## <a name="create-a-custom-calling-policy"></a>Crear una nueva directiva de llamada personalizada

Siga estos pasos para crear una directiva de llamada personalizada.

1. En la navegación izquierda del Centro Microsoft Teams administración, vaya a **Directivas**  >  **de llamadas de voz.**
2. Seleccione **Agregar**.
3. Active o desactive las características que quiera usar en la directiva de llamada.
4. Para controlar si los usuarios pueden enrutar llamadas entrantes al correo de voz, seleccione **Habilitado** o **Controlado por el usuario**. Para evitar el enrutamiento al correo de voz, seleccione **Deshabilitado**.
5. Seleccione **Guardar**.

## <a name="edit-a-calling-policy"></a>Editar una directiva de llamada

Siga estos pasos para editar una directiva de llamada existente.

1. En la navegación izquierda del centro de administración Microsoft Teams, seleccione **Directivas**  >  **de llamadas de voz.**
2. Haga clic junto a la directiva que desea modificar y, a continuación, **seleccione Editar**.
3. Realice los cambios que desee y, a continuación, haga clic **en Guardar**.

## <a name="assign-a-custom-calling-policy-to-users"></a>Asignar una nueva directiva de llamada a los usuarios

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a>Configuración de la directiva de llamada

Esta es la configuración que puede configurar para las directivas de llamada.

### <a name="make-private-calls"></a>Realizar llamadas privadas

Esta configuración controla todas las funcionalidades de llamadas de Teams. Desactive esto para desactivar todas las funciones de llamadas en Teams.

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a>Desvío de llamadas y llamadas simultáneas a las personas de la organización

Esta configuración controla si las llamadas entrantes se pueden reenviar a otros usuarios o pueden llamar a otra persona al mismo tiempo. 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>Desvío de llamadas y llamadas simultáneas a números de teléfono externos

Esta configuración controla si las llamadas entrantes se pueden reenviar a un número externo o pueden llamar a un número externo al mismo tiempo.

### <a name="voicemail-is-available-for-routing-inbound-calls"></a>El correo de voz está disponible para la redirección de llamadas entrantes

Esta configuración permite que las llamadas entrantes se envíen al correo de voz. Las opciones válidas son:

- **Habilitado** El correo de voz siempre está disponible para las llamadas entrantes.
- **Deshabilitado**  El correo de voz no está disponible para las llamadas entrantes.
- **Controlado por el usuario** Los usuarios pueden determinar si quieren que el correo de voz esté disponible.

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>Las llamadas entrantes se pueden redirigir a grupos de llamadas

Esta configuración controla si las llamadas entrantes se pueden reenviar a un grupo de llamadas.

### <a name="delegation-for-inbound-and-outbound-calls"></a>Delegación para llamadas entrantes y salientes

Esta configuración permite enrutar las llamadas entrantes a los delegados, lo que permite a los delegados realizar llamadas salientes en nombre de los usuarios para los que tienen permisos delegados. Para obtener más información, vea [Compartir una línea de teléfono con un delegado](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>Impedir la derivación de números de pago y enviar las llamadas a través de RTC 

Si se establece en **On,** se enviarán llamadas a través de la RTC e incurrirán en cargos en lugar de enviarlos a través de la red y omitir los peajes.

### <a name="busy-on-busy-is-available-when-in-a-call"></a>La disponibilidad en disponibilidad está disponible cuando se llama

Ocupado en ocupado (opciones de disponibilidad) le permite configurar cómo se controlan las llamadas entrantes cuando un usuario ya está en una llamada o conferencia o tiene una llamada en espera. Las llamadas nuevas o entrantes se pueden rechazar con una señal de disponibilidad o se pueden enrutar según la configuración sin respuesta del usuario. Puede habilitar las opciones de disponibilidad en el nivel de inquilino o en el nivel de usuario. Independientemente de cómo se configuren sus opciones de disponibilidad, los usuarios de una llamada o conferencia o aquellos con una llamada en espera no se impiden iniciar nuevas llamadas o conferencias. Esta opción está deshabilitada de forma predeterminada.

### <a name="web-pstn-calling"></a>Llamadas RTC web

Esta configuración permite a los usuarios llamar a números RTC mediante Teams cliente web.

### <a name="incoming-meeting-invites-are-automatically-answered"></a>Las invitaciones a reuniones entrantes se responden automáticamente

Esta configuración controla si las invitaciones a reuniones entrantes se responden automáticamente. Está desactivada de forma predeterminada. Tenga en cuenta que esta configuración solo se aplica a las invitaciones a reuniones entrantes. No se aplica a otros tipos de llamadas.

### <a name="allow-music-on-hold"></a>Permitir música en espera

Esta configuración le permite activar o desactivar la música en espera cuando un autor de la llamada RTC está en espera. Está activado de manera predeterminada. Esta configuración no se aplica a las características de estacionamiento de llamadas y delegado de jefe, y actualmente solo está disponible a través de PowerShell.

## <a name="related-articles"></a>Artículos relacionados

[Set-CSTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

[Asignar directivas a los usuarios en Teams](assign-policies.md)
