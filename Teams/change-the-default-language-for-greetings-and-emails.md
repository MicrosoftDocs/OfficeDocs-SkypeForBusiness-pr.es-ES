---
title: Cambiar el idioma predeterminado en los saludos y los correos electrónicos
author: crowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: 820c3892-1b7e-47d3-ae8d-6e27e7cbcf38
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: Obtenga información sobre cómo configurar Microsoft Teams y Skype Empresarial usar otro idioma para el saludo de correo de voz predeterminado de su organización.
ms.openlocfilehash: 30e122c0d41c93326cdfa39de4c0ceb3a6d55cd2
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "66241129"
---
# <a name="change-the-default-language-for-greetings-and-emails"></a>Cambiar el idioma predeterminado en los saludos y los correos electrónicos

Correo de voz en la nube usa varias configuraciones de idioma para reproducir saludos, generar traducciones de transcripción y generar mensajes de correo de voz. La configuración de idioma se puede especificar de forma predeterminada en el nivel de inquilino, por directiva o de forma individual en un usuario determinado.

## <a name="greetings"></a>Saludos
Los saludos se reproducen al autor de la llamada que sale del correo de voz y puede ser de los siguientes tipos:

- Saludos del sistema
- Saludos personalizados grabados por el usuario al que se llama
- Saludo de texto a voz personalizado especificado en el usuario al que se llama

El idioma usado para reproducir el saludo del sistema es, en orden de prioridad, el idioma de mensaje principal y secundario especificado en la directiva de correo de voz en línea asignada al usuario, el idioma preferido especificado para el usuario o el idioma del inquilino predeterminado.

El saludo personalizado y de fuera de la oficina lo graba el usuario en el idioma elegido por el usuario.

Si el usuario o el administrador de inquilinos especifican saludos personalizados de texto a voz, el idioma usado para generar la voz es el símbolo del sistema especificado junto con los saludos de texto a voz.

Los saludos personalizados de texto a voz solo se usan si no se graban saludos personalizados para el usuario.

## <a name="transcription"></a>Transcripción
Si la directiva de correo de voz en línea habilita al usuario al que se llama, Correo de voz en la nube intentará transcribir el correo de voz que dejó el autor de la llamada. Utilizará la detección de voz para comprender el idioma usado en el contenido de audio y, si es posible, transcribir el contenido con el idioma detectado.

## <a name="transcription-translation"></a>Traducción de transcripción
Si la directiva de correo de voz en línea habilita al usuario al que se llama, Correo de voz en la nube traducirá el correo de voz transcribido. Se traducirá desde el idioma detectado durante la detección de voz a, en orden de prioridad, el idioma preferido especificado para el usuario o el idioma predeterminado del espacio empresarial.

## <a name="voicemail-message-template"></a>Plantilla de mensaje de correo de voz
Correo de voz en la nube generará el mensaje de correo de voz con una plantilla de idioma basada, en orden de prioridad, en el idioma preferido especificado para el usuario o en el idioma predeterminado del inquilino.

## <a name="setting-the-preferred-language-for-a-user"></a>Establecer el idioma preferido para un usuario
Puede establecer el idioma preferido para un usuario mediante PowerShell en Azure Active Directory o en la Active Directory local. Para obtener más información, consulte [Cómo establecer la configuración de idioma y región para Microsoft 365 o Office 365](/office365/troubleshoot/access-management/set-language-and-region).

Los usuarios pueden cambiar su propio idioma preferido a través de su configuración después de iniciar sesión. Para obtener más información, vea [Cambiar el idioma y la zona horaria de la interfaz de pantalla en Microsoft 365 para empresas](https://support.office.com/article/change-your-display-language-and-time-zone-in-microsoft-365-for-business-6f238bff-5252-441e-b32b-655d5d85d15b?ui=en-US&rs=en-US&ad=US).

## <a name="change-the-system-language-for-everyone-in-your-organization"></a>Cambiar el idioma del sistema para todos los usuarios de la organización

1. Inicia sesión con tu cuenta [de administrador global](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) en [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).

2. En la Centro de administración de Microsoft 365, elija **Configuración De** >  la **organización** > **Perfil de la organización**.

3. Elija **Información de la organización**.

4. Seleccione un idioma en la lista **Idioma preferido** para todos los usuarios de la organización.

5. Elija **Guardar**.

**Los idiomas disponibles dependen de la ubicación de su organización**. Por ejemplo, si su organización está en Estados Unidos, puede definir su idioma predeterminado como inglés o español. Si su organización está ubicada en Canadá, puede elegir entre inglés y francés.

## <a name="supported-languages-in-cloud-voicemail"></a>Idiomas admitidos en Correo de voz en la nube
Para obtener una lista de los idiomas admitidos en Correo de voz en la nube para Microsoft Teams y Skype Empresarial, consulte [Correo de voz en la nube idiomas admitidos](languages-for-voicemail-greetings-and-messages.md).
  

## <a name="custom-greeting-recorded-by-a-user"></a>Saludo personalizado grabado por un usuario
Los usuarios pueden grabar su propio saludo personalizado y de fuera de la oficina. Consulte [Configuración del cliente de escritorio de Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f) y [Comprobar Skype Empresarial correo de voz y opciones](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).

## <a name="custom-text-to-speech-greeting-specified-for-a-user"></a>Saludo de texto a voz personalizado especificado para un usuario
El administrador de inquilinos puede especificar el saludo de texto a voz personalizado e idioma de mensaje para un usuario mediante la pestaña Correo de voz de la página de detalles del usuario en el Centro de administración de Teams o mediante el cmdlet [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings) .

## <a name="custom-text-to-speech-greeting-specified-by-a-user"></a>Saludo de texto a voz personalizado especificado por un usuario
Los usuarios pueden especificar sus propios saludos personalizados de texto a voz y el idioma que se usa para el saludo. Para Microsoft Teams: los usuarios pueden cambiar el saludo del correo de voz desde la [configuración del cliente de escritorio de Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f). Por Skype Empresarial [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) y elige un nuevo idioma en **Idioma de aviso**. 


## <a name="related-articles"></a>Artículos relacionados

[Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings)

[Get-CsOnlineVoicemailUserSettings](/powershell/module/skype/get-csonlinevoicemailusersettings)

[Set-CsOnlineVoicemailPolicy](/powershell/module/skype/set-csonlinevoicemailpolicy)

[Get-CsOnlineVoicemailPolicy](/powershell/module/skype/get-csonlinevoicemailpolicy)
