---
title: Administrar directivas de correo de voz
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Administrar directivas de correo de voz para los usuarios.
ms.openlocfilehash: 3f4c64194fc9e2b24c59dc7bc06ed972e801a6a8
ms.sourcegitcommit: cd9a1f7afaaf053741c81022e7052bf6f8008fcc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2022
ms.locfileid: "65370833"
---
# <a name="setting-voicemail-policies-in-your-organization"></a>Configuración de directivas de correo de voz en su organización

> [!WARNING]
> Para Skype Empresarial clientes, deshabilitar el correo de voz a través de una directiva de llamadas de Microsoft Teams también podría deshabilitar el servicio de correo de voz para los usuarios de Skype Empresarial.

Puede usar directivas de correo de voz para controlar las diferentes características relacionadas con Correo de voz en la nube.

## <a name="voicemail-organization-defaults-for-all-users"></a>La organización del correo de voz está predeterminada para todos los usuarios
- La transcripción del correo de voz está habilitada.
- La traducción de la transcripción del correo de voz está habilitada.
- El enmascaramiento de la transcripción del correo de voz está deshabilitado.
- La duración de grabación máxima se establece en cinco minutos.
- La edición de reglas de respuesta de llamadas está habilitada.
- Los idiomas de solicitud del sistema principal y secundario se establecen en null y se usa la configuración de idioma del correo de voz del usuario.

Puede usar la directiva global (predeterminada para toda la organización) que se crea automáticamente o crear y asignar directivas personalizadas.

## <a name="create-a-custom-voicemail-policy"></a>Crear una directiva de correo de voz personalizada

Siga estos pasos para crear una directiva de correo de voz personalizada.

1. En el panel de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **Directivas** de **VoiceVoicemail** > .
2. Seleccione **Agregar**.
3. Active o desactive las características que quiera usar en la directiva de correo de voz.
4. Seleccione **Guardar**.

## <a name="edit-a-voicemail-policy"></a>Editar una directiva de correo de voz

Siga estos pasos para editar una directiva de correo de voz existente.

1. En el panel de navegación izquierdo del Microsoft Teams centro de administración, seleccione **Directivas de** **VoiceVoicemail** > .
2. Haga clic junto a la directiva que desea modificar y, a continuación, seleccione **Editar**.
3. Realice los cambios que desee y, a continuación, haga clic en **Guardar**.

> [!IMPORTANT]
> No puede editar ni quitar las instancias de directiva preconfiguradas denominadas TranscriptionDisabled y TranscriptionProfanityMaskingEnabled.


## <a name="assign-a-custom-voicemail-policy-to-users"></a>Asignar una directiva de correo de voz personalizada a los usuarios

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="voicemail-policy-settings"></a>Configuración de la directiva del correo de voz
  
### <a name="enable-transcription"></a>Habilitar la transcripción

Esta configuración controla si el servicio de Correo de voz en la nube generará una transcipción de texto del correo de voz grabado e incluirá en el mensaje de correo de voz. La transcripción se realizará en función del idioma detectado en el correo de voz grabado.

### <a name="transcription-translation"></a>Traducción de transcripción

Esta configuración controla si el servicio de Correo de voz en la nube traducirá la transcripción del correo de voz grabado. La traducción se intentará en el idioma preferido del receptor del correo de voz.

### <a name="transcription-profanity-masking"></a>Enmascaramiento de lenguaje profanado de transcripción

Esta configuración controla si el servicio de Correo de voz en la nube enmascarará la lenguaje profanado que se encuentra en la transcripción del correo de voz.

### <a name="maximum-recording-duration"></a>Duración de grabación máxima

La longitud máxima de la grabación controla el tiempo máximo que se puede grabar un correo de voz. El valor predeterminado es de 5 minutos.

### <a name="call-answering-rules"></a>Reglas de respuesta de llamadas

Esta configuración controla si el usuario puede configurar las reglas de respuesta de llamadas del correo de voz en Microsoft Teams.

### <a name="dual-language-system-prompts"></a>Avisos del sistema de doble idioma

De forma predeterminada, las indicaciones del sistema del correo de voz se presentan a los autores de llamadas en el idioma seleccionado por el usuario al configurar su correo de voz. Si hay un requisito empresarial para que las solicitudes del sistema del correo de voz se presenten en dos idiomas, se puede establecer un idioma principal y otro secundario y puede que no sean los mismos.

### <a name="share-data-for-service-improvements"></a>Compartir datos para mejoras del servicio

Especifica si el correo de voz y los datos de transcripción se comparten con el servicio para la formación y la mejora de la precisión. Si se establece en false, los datos del correo de voz no se compartirán, independientemente de la elección del usuario.


> [!IMPORTANT]
> El servicio de correo de voz de Microsoft 365 y Office 365 almacena en caché las directivas de correo de voz y actualiza la memoria caché cada 6 horas. Por lo tanto, los cambios de directiva que realice pueden tardar hasta 6 horas en aplicarse.

## <a name="related-articles"></a>Artículos relacionados

[New-CsOnlineVoicemailPolicy](/powershell/module/skype/new-csonlinevoicemailpolicy)

[Set-CsOnlineVoicemailPolicy](/powershell/module/skype/set-csonlinevoicemailpolicy)

[Get-CsOnlineVoicemailPolicy](/powershell/module/skype/get-csonlinevoicemailpolicy)

[Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/grant-csonlinevoicemailpolicy)

[Remove-CsOnlineVoicemailPolicy](/powershell/module/skype/remove-csonlinevoicemailpolicy)
