---
title: Directivas de llamadas en Microsoft Teams
author: LolaJacobsen
ms.author: tonysmit
manager: serdars
ms.date: 05/06/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
search.appverid: MET150
description: Obtenga información acerca de la configuración de la directiva de llamada en Microsoft Teams.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c35c2455c3164f04dd9fdbbb210e20809a719bc6
ms.sourcegitcommit: c997490cf7239d07e2fd52a4b03bec464b3d192b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/09/2019
ms.locfileid: "33835330"
---
<a name="calling-policies-in-microsoft-teams"></a>Directivas de llamadas en Microsoft Teams
===================================

En Microsoft Teams, llamar al control de las directivas que la llamada a y las características de desvío de llamadas están disponibles para los usuarios. Las directivas de la llamada a determinan si un usuario puede realizar llamadas privadas, use el desvío de llamadas o llamadas a otros usuarios o números de teléfono externos simultáneas, enrutar las llamadas al correo de voz, enviar las llamadas a grupos de llamadas, delegación para las llamadas entrantes y salientes, y así sucesivamente. Una directiva global predeterminada se crea automáticamente, pero los administradores también pueden crear y asignar directivas de llamada personalizadas.

## <a name="create-a-custom-calling-policy"></a>Crear una directiva llamada personalizada

Siga estos pasos para crear una directiva llamada personalizada.

1. En el centro de administración de Microsoft Teams, seleccione **voz** > **Directiva de llamada**.
2. Seleccione **nueva directiva**.
3. Activar las características que desea usar en la directiva de llamada. Todas las selecciones están **desactivadas** de forma predeterminada.
4. Para controlar si los usuarios pueden enrutar las llamadas entrantes al correo de voz, seleccione **siempre habilitado** o **bajo control de usuario**. Para evitar que el enrutamiento al correo de voz, seleccione **siempre deshabilitado**.
5. Seleccione **Guardar**.

## <a name="modify-an-existing-calling-policy"></a>Modificar una directiva de llamada existente

Siga estos pasos para modificar una directiva de llamada existente.

1. En el centro de administración de Microsoft Teams, seleccione **voz** > **Directiva de llamada**.
2. Haga clic en junto a la directiva que desea modificar y, a continuación, seleccione **Editar**.
3. Activar las características que desea usar en la directiva de llamada. Todas las selecciones están **desactivadas** de forma predeterminada.
4. Para controlar si los usuarios pueden enrutar las llamadas entrantes al correo de voz, seleccione **siempre habilitado** o **bajo control de usuario**. Para evitar que el enrutamiento al correo de voz, seleccione **siempre deshabilitado**.
5. Seleccione **Guardar**.

## <a name="assign-a-calling-policy-to-a-user"></a>Asignar una directiva de llamada a un usuario

Siga estos pasos para asignar una directiva personalizada que llama a un usuario.

1. En el centro de administración de Microsoft Teams, seleccione **voz** > **Directiva de llamada**.
2. Haga clic en junto al nombre de directiva para seleccionarlo y, a continuación, seleccione **Administrar usuarios**.
3. En el panel **Administrar usuarios** , buscar el nombre del usuario. (Debe escribir al menos tres caracteres).
4. Seleccione el nombre del usuario y, a continuación, seleccione **Agregar**.
5. Seleccione **Guardar**.

## <a name="calling-policy-settings"></a>Configuración de la directiva de llamada

Use la siguiente configuración para crear una directiva llamada personalizada.

### <a name="user-can-make-private-calls"></a>Usuario puede realizar llamadas privadas

Esta configuración controla todas las capacidades de llamada en los equipos. Desactivar para desactivar la opción toda la funcionalidad de llamada en los equipos.

### <a name="call-forwarding-and-simultaneous-ringing-to-other-users"></a>Desvío de llamadas y las llamadas simultáneas a otros usuarios

Esta configuración controla si las llamadas recibidas pueden transferirse a otros usuarios o pueden llamar a otra persona al mismo tiempo. 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>Desvío de llamadas y las llamadas simultáneas a números de teléfono externos

Esta configuración controla si las llamadas recibidas pueden transferirse a un número externo o pueden llamar a un número externo al mismo tiempo.

### <a name="voicemail-is-available-for-routing-inbound-calls-to-users"></a>Correo de voz está disponible para enrutar las llamadas entrantes a los usuarios

Esta configuración permite que las llamadas entrantes que se envíen al correo de voz. Las opciones válidas son:

   - **Siempre habilitado** Correo de voz siempre está disponible para las llamadas entrantes. 
   - **Siempre deshabilitado**  Correo de voz no está disponible para las llamadas entrantes. 
   - **Controla el usuario**. Los usuarios pueden determinar si desean enviar correo de voz para que esté disponible.

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>Se pueden redirigir las llamadas entrantes para llamar a grupos 

> [!Include [feature preview](includes/preview-feature.md)]

Esta configuración controla si se pueden reenviar las llamadas entrantes a un grupo de llamada.

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a>Permitir la delegación de las llamadas entrantes y salientes

> [!Include [feature preview](includes/preview-feature.md)]

Esta configuración permite que las llamadas entrantes se enrutan a los delegados, permitir que los delegados realizar llamadas salientes en nombre de los usuarios para quienes se delega permisos. Para obtener más información, vea [compartir una línea telefónica con un delegado](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).


### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>Evitar el desvío de pago y enviar las llamadas a través de la RTC 

Si se establece en **** va a enviar las llamadas a través de la RTC e incurrir en los cargos en lugar de enviarlos a través de la red y omitir el cuotas.

### <a name="busy-on-busy-is-available-while-in-a-call"></a>No disponible en no disponible está disponible mientras se encuentre en una llamada

No disponible en no disponible (las opciones de disponibilidad)) es un nuevo valor en los equipos que se administran las directivas de llamada que le permite configurar las llamadas entrantes cuando un usuario ya está en una llamada o conferencia o tiene una llamada se pondrá en espera. Se pueden rechazar las llamadas entrantes o nuevo con una señal de ocupado. Puede habilitar las opciones de disponibilidad en el nivel de inquilino o en el nivel de usuario. Independientemente de cómo se configuran las opciones de disponibilidad, los usuarios de una llamada o conferencia o aquellos con una llamada en espera no se les impide iniciar nuevas llamadas o conferencias. Esta opción está deshabilitada de forma predeterminada.

## <a name="see-also"></a>Vea también

[Set-CSTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)