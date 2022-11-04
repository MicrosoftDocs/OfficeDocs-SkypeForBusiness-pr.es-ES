---
title: Administrar directivas de correo de voz
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
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
ms.openlocfilehash: 02df2f235512ce0aca658031fae000edc99b5ea9
ms.sourcegitcommit: 18e66d54a9e349d4516253addc85cc12892c69a3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2022
ms.locfileid: "68851821"
---
# <a name="manage-cloud-voicemail-policies-for-your-users"></a>Administrar directivas de Correo de voz en la nube para los usuarios

> [!WARNING]
> Para Skype Empresarial clientes, deshabilitar el correo de voz a través de una directiva de llamadas de Microsoft Teams también podría deshabilitar el servicio de correo de voz para los usuarios de Skype Empresarial.

Las directivas de correo de voz le permiten configurar y asignar directivas de correo de voz nuevas o existentes a grupos de usuarios para características como reglas de respuesta a llamadas, transcripción del correo de voz, enmascaramiento de lenguaje profanado de transcripción, traducción de transcripción e idioma de mensaje del sistema.

Antes de especificar directivas, lea [Configurar Correo de voz en la nube](set-up-phone-system-voicemail.md). Para obtener información sobre la administración de la configuración para usuarios individuales, vea [Administrar la configuración del correo de voz](manage-voicemail-settings.md).

Para administrar las directivas del correo de voz, puede usar el Centro de administración de Teams o el cmdlet de New-CsOnlineVoicemailPolicy PowerShell. 

Las directivas predeterminadas para los usuarios son las siguientes:

- La transcripción del correo de voz está habilitada.
- La traducción de la transcripción del correo de voz está habilitada.
- El enmascaramiento de la transcripción del correo de voz está deshabilitado.
- La duración de grabación máxima se establece en cinco minutos.
- La edición de reglas de respuesta de llamadas está habilitada.
- Los idiomas de solicitud del sistema principal y secundario se establecen en null y se usa la configuración de idioma del correo de voz del usuario.
- No se ha configurado ningún pre o postamble.

Puede usar la directiva global (predeterminada para toda la organización) que se crea automáticamente o crear y asignar directivas personalizadas.

> [!IMPORTANT]
> El servicio de correo de voz de Microsoft 365 almacena en caché las directivas de correo de voz y actualiza la memoria caché cada 6 horas. Por lo tanto, los cambios de directiva que realice pueden tardar hasta 6 horas en aplicarse.

## <a name="use-teams-admin-center"></a>Usar el Centro de administración de Teams

### <a name="create-a-custom-voicemail-policy"></a>Crear una directiva de correo de voz personalizada

Siga estos pasos para crear una directiva de correo de voz personalizada.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Directivas de correo de voz** > .

2. Seleccione **Agregar**.

3. Active o desactive las características que quiera usar en la directiva de correo de voz.

4. Seleccione **Guardar**.

### <a name="edit-a-voicemail-policy"></a>Editar una directiva de correo de voz

Siga estos pasos para editar una directiva de correo de voz existente.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, seleccione **Directivas de correo de voz** > .

2. Haga clic junto a la directiva que desea modificar y, a continuación, seleccione **Editar**.

3. Realice los cambios que desee y, a continuación, haga clic en **Guardar**.

> [!IMPORTANT]
> No puede editar ni quitar las instancias de directiva preconfiguradas denominadas TranscriptionDisabled y TranscriptionProfanityMaskingEnabled.


### <a name="assign-a-custom-voicemail-policy-to-users"></a>Asignar una directiva de correo de voz personalizada a los usuarios

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="use-powershell"></a>Usar PowerShell

También puede usar PowerShell para configurar y asignar directivas de correo de voz nuevas o existentes. Para administrar directivas con PowerShell, use los siguientes cmdlets:

- [New-CsOnlineVoicemailPolicy](/powershell/module/skype/new-csonlinevoicemailpolicy)

- [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/set-csonlinevoicemailpolicy)

- [Get-CsOnlineVoicemailPolicy](/powershell/module/skype/get-csonlinevoicemailpolicy)

- [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/grant-csonlinevoicemailpolicy)

- [Remove-CsOnlineVoicemailPolicy](/powershell/module/skype/remove-csonlinevoicemailpolicy)

## <a name="voicemail-policy-settings"></a>Configuración de la directiva del correo de voz
  
- **Habilitar la transcripción**: esta configuración controla si el servicio de Correo de voz en la nube generará una transcipción de texto del correo de voz grabado e incluirálo en el mensaje de correo de voz. La transcripción se realizará en función del idioma detectado en el correo de voz grabado.

- **Traducción de la transcripción**: esta configuración controla si el servicio de Correo de voz en la nube traducirá la transcripción del correo de voz grabado. La traducción se intentará en el idioma preferido del receptor del correo de voz.

- **Enmascaramiento de lenguaje profanado de la transcripción**: esta configuración controla si el servicio de Correo de voz en la nube enmascarará la lenguaje profanado que se encuentra en la transcripción del correo de voz.

- **Duración máxima de la grabación** : la duración máxima de la grabación controla el tiempo máximo en que se puede grabar un correo de voz. El valor predeterminado es de 5 minutos.

- **Reglas de respuesta de llamadas** : esta configuración controla si el usuario puede configurar reglas de respuesta de llamadas del correo de voz en Microsoft Teams.

- **Avisos del sistema de doble idioma** : de forma predeterminada, las indicaciones del sistema del correo de voz se presentan a los autores de llamadas en el idioma seleccionado por el usuario al configurar su correo de voz. Si hay un requisito empresarial para que las solicitudes del sistema del correo de voz se presenten en dos idiomas, se puede establecer un idioma principal y otro secundario y puede que no sean los mismos.

- **BytesAudioFile** : actualmente solo está disponible a través de PowerShell. El archivo de audio que se reproducirá al autor de la llamada antes de que se reproduzca el saludo del correo de voz del usuario.

- **PostambleAudioFile** - Actualmente solo está disponible a través de PowerShell. El archivo de audio que se reproducirá al autor de la llamada después de que se reproduzca el saludo del correo de voz del usuario y antes de que el autor de la llamada deje un mensaje de correo de voz.

- **PreámbuloPostambleMandatory** : actualmente solo está disponible a través de PowerShell. Se está reproduciendo el Pre o Postamble obligatorio antes de que el autor de la llamada pueda dejar un mensaje.

### <a name="share-data-for-service-improvements"></a>Compartir datos para mejoras del servicio

Especifica si el correo de voz y los datos de transcripción se comparten con el servicio para la formación y la mejora de la precisión. Si se establece en false, los datos del correo de voz no se compartirán, independientemente de la elección del usuario.


## <a name="related-articles"></a>Artículos relacionados


