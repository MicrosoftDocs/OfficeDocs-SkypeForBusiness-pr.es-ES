---
title: Establecer los números de teléfono incluidos en las invitaciones
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Siga estos pasos para crear un número de teléfono predeterminado para que los autores de llamadas se unan a una reunión de Microsoft Teams.
ms.openlocfilehash: 27ff7040b27d2265bcdc5ab30f48cb919746471b
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2022
ms.locfileid: "67642071"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a>Establecer los números de teléfono incluidos en las invitaciones en Microsoft Teams

Las audioconferencias en Microsoft 365 y Office 365 permiten a los usuarios de su organización crear reuniones de Microsoft Teams y, a continuación, permiten que los usuarios llamen a esas reuniones con un número de teléfono.

Un puente de conferencias le proporciona un conjunto de números de teléfono de acceso telefónico local para su organización. Todos ellos se pueden usar para unirse a las reuniones que ha creado un organizador de la reunión, pero puede seleccionar cuáles se incluirán en las invitaciones de la reunión.

Además de los números de teléfono incluidos en la invitación a la reunión para un organizador de la reunión, también hay un vínculo situado en la parte inferior de cada invitación a la reunión que abre la lista completa de todos los números de teléfono de acceso telefónico local que se pueden usar para unirse a una reunión.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-users"></a>Asignación inicial de números de teléfono que se incluyen en las invitaciones de reunión para los usuarios

Los números de teléfono incluidos en las invitaciones a reuniones de usuarios habilitados para Audioconferencia se definen en *teamsaudioconferencingPolicy* que se asigna a los usuarios. Cuando un *TeamsAudioConferencingPolicy* se asigna a un usuario, todos los números de teléfono gratuitos y de pago agregados en la directiva se incluyen en las invitaciones de reunión para los usuarios que tienen esa directiva. Si a un usuario se le asigna *TeamsAudioConferencingPolicy* y no se agregan números de teléfono gratuitos o de pago a la directiva, en ese caso los números de teléfono que aparecen en las invitaciones de reunión de estos usuarios se definen por el número de teléfono de pago de conferencia predeterminado y el número de teléfono gratuito de conferencia predeterminado en la configuración de cada usuario individual.

> [!NOTE]
> Los números de teléfono gratuitos o de pago agregados a *TeamsAudioConferencingPolicy* de un usuario tienen prioridad sobre los números de teléfono establecidos individualmente mediante el número de teléfono de pago de conferencia predeterminado y el número de teléfono gratuito de conferencia predeterminado en la configuración de un usuario.

Como se mencionó anteriormente, además de los números de teléfono, cada invitación a la reunión contiene un vínculo que abre la lista completa de todos los números de teléfono de acceso telefónico local que se pueden usar para unirse a una reunión determinada.

> [!IMPORTANT]
> Los números de teléfono asignados pueden tardar hasta 24 horas en aparecer en la invitación a la reunión. Si no ves números actualizados, espera al menos 24 horas antes de ponerte en contacto con el servicio de soporte técnico.

### <a name="new-users"></a>Nuevos usuarios

Los números de teléfono gratuitos y de pago incluidos en las invitaciones a reuniones para nuevos usuarios también se definen en *TeamsAudioconferencingPolicy* , que se asigna a esos usuarios. De forma predeterminada, a todos los usuarios nuevos se les asigna Global *TeamsAudioconferencingPolicy*. La directiva global no tiene ningún número de teléfono agregado (a menos que el administrador de inquilinos lo cambie). En este caso, los números de teléfono que se incluyen en las invitaciones de reunión de los usuarios habilitados para audioconferencia se definen por el número de teléfono de pago de conferencia predeterminado y el número de teléfono gratuito de conferencia predeterminado que se encuentra en la configuración de cada usuario.

Para un nuevo usuario, los números de pago de conferencia predeterminados se asignan en función de la ubicación de uso establecida en el centro de administración de Microsoft 365 del usuario cuando el usuario está habilitado para el servicio de Audioconferencia. Si hay un número de pago en el puente de conferencia que coincida con el país del usuario, ese número se asignará automáticamente como el número de pago predeterminado del usuario. Si no hay uno, el número definido como número de pago predeterminado del puente de conferencia se asignará como el número de pago predeterminado del usuario.  

Una vez que el usuario está habilitado para el servicio de Audioconferencia, el administrador de inquilinos puede cambiar los números de teléfono gratuitos y de pago predeterminados del usuario de sus valores iniciales según sea necesario.

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-users-in-powershell-using-the-teamsaudioconferencingpolicy-cmdlet"></a>Establecer o cambiar el número de teléfono de audioconferencia predeterminado para los usuarios de Powershell mediante el cmdlet *TeamsAudioConferencingPolicy*

Consulte [Configuración de la directiva de Audioconferencia para números de pago y gratuitos](audio-conferencing-toll-free-numbers-policy.md)

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user-individually"></a>Establecer o cambiar el número de teléfono de audioconferencia predeterminado para un organizador o usuario de la reunión de forma individual

Debe ser administrador de servicio de Teams para poder realizar estos cambios. Consulte [Usar los roles de administrador de Teams para administrar Teams](./using-admin-roles.md) para obtener información sobre cómo obtener roles de administrador y permisos.

1. Inicie sesión en el Centro de administración de Microsoft Teams.

2. En el panel de navegación izquierdo, haga clic en **Usuarios**.

    ![Muestra la selección de usuarios en el Centro de administración de Microsoft Teams.](media/Admin-users.png)

3. Haga clic en el nombre de usuario de la lista de usuarios disponibles.

4. Junto a **Audioconferencia**, haga clic en **Editar**.

    ![Haga clic en Editar junto a Audioconferencia.](media/teams-set-phone-numbers-on-invites-image3.png)

5. Use los campos **Número de pago** o **Número gratuito** para escribir los números del usuario.

> [!IMPORTANT]
> Al cambiar la configuración de audioconferencia de un usuario, las reuniones periódicas y futuras de Microsoft Teams deben actualizarse y enviarse a los asistentes.

> [!NOTE]
> Los números de teléfono introducidos en esta configuración solo se usan si *TeamsAudioConferencingPolicy* asignado al usuario no tiene ningún número de teléfono agregado.

## <a name="want-to-use-windows-powershell"></a>¿Desea usar Windows PowerShell

Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Microsoft 365 o Office 365 con un único punto de administración que puede simplificar su trabajo diario cuando tenga que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:

- [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Las mejores formas de administrar Microsoft 365 o Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Para establecer o cambiar el número de teléfono de audioconferencia predeterminado de un organizador o usuario de la reunión con [PowerShell de Microsoft Teams](/powershell/module/teams/?view=teams-ps), establezca los **`ServiceNumber`** **`TollFreeServiceNumber`** o parámetros del cmdlet [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/set-CsOnlineDialInConferencingUser?view=skype-ps) en uno de los números disponibles.

## <a name="related-topics"></a>Temas relacionados

[Probar o comprar Audioconferencia en Microsoft 365 para Microsoft Teams](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)

[Cambiar los números de teléfono de su puente de Audioconferencia](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)
