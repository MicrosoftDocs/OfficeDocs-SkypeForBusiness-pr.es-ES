---
title: Configurar la respuesta automática para Teams dispositivos Android
author: KarliStites
ms.author: kastites
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
ms.custom: null
description: Obtenga información sobre cómo configurar la característica de respuesta automática para Salas de Microsoft Teams dispositivos android y Teams dispositivos de videollamadas con PowerShell.
---

# <a name="set-up-auto-answer-for-microsoft-teams-rooms-on-android-and-teams-video-phone-devices"></a>Configurar la respuesta automática para Salas de Microsoft Teams dispositivos android y Teams de vídeo

Este artículo le ayudará a configurar la característica de respuesta automática en Salas de Microsoft Teams android y Teams dispositivos de videollamadas. La respuesta automática permite a los usuarios de su organización con privilegios administrativos cambiar la configuración de su dispositivo para aceptar automáticamente las invitaciones a reuniones entrantes y aceptar automáticamente las llamadas con vídeo.

## <a name="enable-auto-answer-with-powershell"></a>Habilitar la respuesta automática con PowerShell

Use los siguientes atributos para habilitar la respuesta automática en Salas de Microsoft Teams dispositivos android y Teams de vídeo:

- **Set-CsTeamsCallingPolicy -AutoAnswerEnabledType**
- **Set-CsTeamsIPPhonePolicy -SignInMode**

### <a name="1-turn-on-auto-answer-for-incoming-meeting-invites"></a>1. Activar la respuesta automática para las invitaciones a reuniones entrantes

Use **Set-CsTeamsCallingPolicy -AutoAnswerEnabledType para** activar la respuesta automática para las invitaciones a reuniones entrantes. La respuesta automática **está desactivada de** forma predeterminada. Esta directiva solo se aplica a las invitaciones a reuniones entrantes y no admite otros tipos de llamadas. Lea [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy) para obtener más información sobre el cmdlet.

```powershell
Set-CsTeamsCallingPolicy -AutoAnswerEnabledType Enabled
```

### <a name="2-set-the-device-sign-in-mode"></a>2. Establecer el modo de inicio de sesión del dispositivo

Use **Set-CsTeamsIPPhonePolicy -SignInMode** para establecer el modo de inicio de sesión del dispositivo para determinar el comportamiento al iniciar sesión en Teams. Lea [Set-CsTeamsIPPhonePolicy](/powershell/module/skype/set-csteamsipphonepolicy) para obtener más información sobre el cmdlet.

Hay tres opciones para el modo de inicio de sesión:

- **UserSignIn:** Permite a un usuario Teams experiencia en el teléfono.
- **CommonAreaPhoneSignIn:** Habilita una experiencia de teléfono de área común en el teléfono.
- **MeetingSignIn:** Habilita una experiencia de sala de reuniones en el teléfono.

Por ejemplo, la siguiente directiva establece el modo de inicio de sesión en una experiencia de sala de reuniones.

```powershell
Set-CsTeamsIPPhonePolicy -Identity Device -SignInMode MeetingSignIn
```

### <a name="configure-device-settings"></a>Configurar la configuración del dispositivo

Después de habilitar la respuesta automática, los usuarios con permisos administrativos pueden activar la característica en la configuración del dispositivo. Para habilitar la característica en el nivel de dispositivo, debe activar Aceptar automáticamente invitaciones **a reuniones entrantes**. También puede activar Aceptar **automáticamente con vídeo**. Ambas opciones de configuración están desactivadas de forma predeterminada.

## <a name="related-topics"></a>Temas relacionados

[Soporte técnico de Microsoft: llamadas y dispositivos](https://support.microsoft.com/office/calls-and-devices-4d96653e-6176-4978-98ab-2c19df137e43#ID0EBBD=Devices)

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

[Set-CsTeamsIPPhonePolicy](/powershell/module/skype/set-csteamsipphonepolicy)
