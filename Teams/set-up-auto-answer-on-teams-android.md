---
title: Configurar la respuesta automática para dispositivos Teams Android
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: kponnus
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom: ''
description: Obtenga información sobre cómo configurar la característica de respuesta automática para Salas de Microsoft Teams en dispositivos de teléfonos de vídeo Android y Teams con PowerShell.
ms.openlocfilehash: fac458a2b7b100a2074dbaac0e209fbdd3527eef
ms.sourcegitcommit: 9532eb79310cd653010565607fa394f2b8dd182d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/23/2022
ms.locfileid: "65646599"
---
# <a name="set-up-auto-answer-for-microsoft-teams-rooms-on-android-and-teams-video-phone-devices"></a>Configurar la respuesta automática para Salas de Microsoft Teams en dispositivos de videollamada Android y Teams

Este artículo le ayudará a configurar la función de respuesta automática en Salas de Microsoft Teams en Android y Teams dispositivos de videollamada. La respuesta automática permite a los usuarios de su organización con privilegios administrativos cambiar la configuración del dispositivo para aceptar automáticamente invitaciones a reuniones entrantes y aceptar automáticamente llamadas con vídeo.

## <a name="enable-auto-answer-with-powershell"></a>Habilitar la respuesta automática con PowerShell

Usa los siguientes atributos para habilitar la respuesta automática en Salas de Microsoft Teams en dispositivos de teléfonos de vídeo Android y Teams:

- **Set-CsTeamsCallingPolicy -AutoAnswerEnabledType**
- **Set-CsTeamsIPPhonePolicy -SignInMode**

### <a name="1-turn-on-auto-answer-for-incoming-meeting-invites"></a>1. Activar la respuesta automática para las invitaciones entrantes a reuniones

Use **Set-CsTeamsCallingPolicy -AutoAnswerEnabledType** para activar la respuesta automática para las invitaciones de reunión entrantes. La respuesta automática está **desactivada** de forma predeterminada. Esta directiva solo se aplica a las invitaciones entrantes a reuniones y no admite otros tipos de llamadas. Lea [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy) para obtener más información sobre el cmdlet.

```powershell
Set-CsTeamsCallingPolicy -AutoAnswerEnabledType Enabled
```

### <a name="2-set-the-device-sign-in-mode"></a>2. Establecer el modo de inicio de sesión del dispositivo

Use **Set-CsTeamsIPPhonePolicy -SignInMode** para establecer el modo de inicio de sesión para que el dispositivo determine el comportamiento al iniciar sesión en Teams. Lea [Set-CsTeamsIPPhonePolicy](/powershell/module/skype/set-csteamsipphonepolicy) para obtener más información sobre el cmdlet.

Hay tres opciones para el modo de inicio de sesión:

- **UserSignIn:** Permite que un usuario individual Teams experiencia en el teléfono.
- **CommonAreaPhoneSignIn:** Habilita una experiencia de teléfono de área común en el teléfono.
- **MeetingSignIn:** Habilita una experiencia de sala de reuniones en el teléfono.

Por ejemplo, la siguiente directiva establece el modo de inicio de sesión en una experiencia de sala de reuniones.

```powershell
Set-CsTeamsIPPhonePolicy -Identity Device -SignInMode MeetingSignIn
```

### <a name="configure-device-settings"></a>Configurar la configuración del dispositivo

Después de habilitar la respuesta automática, los usuarios con permisos administrativos pueden activar la función en la configuración del dispositivo. Para habilitar la característica en el nivel de dispositivo, debe activar **Aceptar automáticamente invitaciones a reuniones entrantes**. También puede activar **Aceptar automáticamente con vídeo**. Ambas opciones de configuración están desactivadas de forma predeterminada.

## <a name="related-topics"></a>Temas relacionados

[Soporte técnico de Microsoft: llamadas y dispositivos](https://support.microsoft.com/office/calls-and-devices-4d96653e-6176-4978-98ab-2c19df137e43#ID0EBBD=Devices)

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

[Set-CsTeamsIPPhonePolicy](/powershell/module/skype/set-csteamsipphonepolicy)
