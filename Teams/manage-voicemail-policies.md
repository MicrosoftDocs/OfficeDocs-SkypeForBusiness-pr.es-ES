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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Administrar directivas de correo de voz para los usuarios.
ms.openlocfilehash: aa6b08cba7118a5e43f7f2bd3baea7fb3bc7f158
ms.sourcegitcommit: 2419348e964cfe97b72d533f267c5d7055d5366f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/12/2021
ms.locfileid: "52910062"
---
# <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="67bc0-103">Configuración de directivas de correo de voz en su organización</span><span class="sxs-lookup"><span data-stu-id="67bc0-103">Setting voicemail policies in your organization</span></span>

> [!WARNING]
> <span data-ttu-id="67bc0-104">Para Skype Empresarial clientes, deshabilitar el correo de voz mediante una directiva de Microsoft Teams de llamadas también puede deshabilitar el servicio de correo de voz para Skype Empresarial usuarios.</span><span class="sxs-lookup"><span data-stu-id="67bc0-104">For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.</span></span>

## <a name="voicemail-organization-defaults-for-all-users"></a><span data-ttu-id="67bc0-105">Organización de correo de voz predeterminada para todos los usuarios</span><span class="sxs-lookup"><span data-stu-id="67bc0-105">Voicemail organization defaults for all users</span></span>
- <span data-ttu-id="67bc0-106">La transcripción del correo de voz está habilitada.</span><span class="sxs-lookup"><span data-stu-id="67bc0-106">Voicemail transcription is enabled.</span></span>
- <span data-ttu-id="67bc0-107">El enmascaramiento de la transcripción del correo de voz está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="67bc0-107">Voicemail transcription profanity masking is disabled.</span></span>
- <span data-ttu-id="67bc0-108">La duración máxima de la grabación se establece en cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="67bc0-108">The maximum recording duration is set to five minutes.</span></span>

<span data-ttu-id="67bc0-109">Puede controlar estos valores predeterminados mediante los [cmdlets Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) y [Grant-CsOnlineVoicemailPolicy.](/powershell/module/skype/Get-CsOnlineVoicemailPolicy)</span><span class="sxs-lookup"><span data-stu-id="67bc0-109">You can control these defaults by using the [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) and [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) cmdlets.</span></span>

<span data-ttu-id="67bc0-110">Los mensajes de correo de voz recibidos por los usuarios de su organización se transcribirán en la región donde se hospeda Microsoft 365 o Office 365 organización.</span><span class="sxs-lookup"><span data-stu-id="67bc0-110">Voicemail messages received by users in your organization are transcribed in the region where your Microsoft 365 or Office 365 organization is hosted.</span></span> <span data-ttu-id="67bc0-111">Es posible que la región donde se hospeda el inquilino no sea la misma región donde se encuentra el usuario que recibe el mensaje de correo de voz.</span><span class="sxs-lookup"><span data-stu-id="67bc0-111">The region where your tenant is hosted might not be the same region where the user receiving the voicemail message is located.</span></span> <span data-ttu-id="67bc0-112">Para ver la región donde se hospeda [](https://go.microsoft.com/fwlink/p/?linkid=2067339) el inquilino, vaya a la página Perfil de la organización y, a continuación, haga clic en **Ver detalles** junto a Ubicación **de datos.**</span><span class="sxs-lookup"><span data-stu-id="67bc0-112">To view the region where your tenant is hosted, go to the [Organization profile](https://go.microsoft.com/fwlink/p/?linkid=2067339) page and then click **View details** next to **Data location**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="67bc0-113">No puede crear una nueva instancia de directiva para la transcripción y la transcripción con el cmdlet **New-CsOnlineVoiceMailPolicy** y no puede quitar una instancia de directiva existente con el cmdlet **Remove-CsOnlineVoiceMailPolicy.**</span><span class="sxs-lookup"><span data-stu-id="67bc0-113">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="67bc0-114">Puede administrar la configuración de la transcripción para sus usuarios con las directivas del correo de voz.</span><span class="sxs-lookup"><span data-stu-id="67bc0-114">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="67bc0-115">Para ver todas las instancias de directiva de correo de voz disponibles, puede usar el cmdlet [Get-CsOnlineVoicemailPolicy.](/powershell/module/skype/Get-CsOnlineVoicemailPolicy)</span><span class="sxs-lookup"><span data-stu-id="67bc0-115">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) cmdlet.</span></span>

```PowerShell
PS C:\> Get-CsOnlineVoicemailPolicy


Identity                            : Global
EnableTranscription                 : True
ShareData                           : Defer
EnableTranscriptionProfanityMasking : False
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True

Identity                            : Tag:Default
EnableTranscription                 : True
ShareData                           : Defer
EnableTranscriptionProfanityMasking : False
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True

Identity                            : Tag:TranscriptionProfanityMaskingEnabled
EnableTranscription                 : True
ShareData                           : Defer
EnableTranscriptionProfanityMasking : True
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True

Identity                            : Tag:TranscriptionDisabled
EnableTranscription                 : False
ShareData                           : Defer
EnableTranscriptionProfanityMasking : False
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True
```
  
## <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="67bc0-116">Desactivar la transcripción para su organización</span><span class="sxs-lookup"><span data-stu-id="67bc0-116">Turning off transcription for your organization</span></span>

<span data-ttu-id="67bc0-117">Dado que la configuración predeterminada para la transcripción está en su organización, es posible que desee deshabilitarla mediante [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span><span class="sxs-lookup"><span data-stu-id="67bc0-117">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span></span> <span data-ttu-id="67bc0-118">Para ello, ejecute:</span><span class="sxs-lookup"><span data-stu-id="67bc0-118">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

## <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="67bc0-119">Activar el enmascaramiento de contenido ofensivo de transcripción para su organización</span><span class="sxs-lookup"><span data-stu-id="67bc0-119">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="67bc0-120">El enmascaramiento de contenido ofensivo de transcripción está deshabilitado de forma predeterminada para su organización.</span><span class="sxs-lookup"><span data-stu-id="67bc0-120">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="67bc0-121">Si hay un requisito de negocio para habilitarlo, puede habilitar el enmascaramiento de contenido ofensivo de transcripción mediante [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span><span class="sxs-lookup"><span data-stu-id="67bc0-121">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span></span> <span data-ttu-id="67bc0-122">Para ello, ejecute:</span><span class="sxs-lookup"><span data-stu-id="67bc0-122">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

## <a name="changing-the-recording-duration-for-your-organization"></a><span data-ttu-id="67bc0-123">Cambiar la duración de la grabación de su organización</span><span class="sxs-lookup"><span data-stu-id="67bc0-123">Changing the recording duration for your organization</span></span>

<span data-ttu-id="67bc0-124">La duración máxima de la grabación se establece en cinco minutos de forma predeterminada para su organización.</span><span class="sxs-lookup"><span data-stu-id="67bc0-124">The maximum recording length is set to five minutes by default for your organization.</span></span> <span data-ttu-id="67bc0-125">Si hay un requisito empresarial para aumentar o reducir la longitud máxima de grabación, esto se puede hacer con [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span><span class="sxs-lookup"><span data-stu-id="67bc0-125">If there is a business requirement to increase or decrease the maximum recording length, this can be done by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span></span> <span data-ttu-id="67bc0-126">Por ejemplo, para establecer el tiempo máximo de grabación en 60 segundos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="67bc0-126">For example, to set the maximum recording time to 60 seconds,  run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -MaximumRecordingLength ([TimeSpan]::FromSeconds(60))
```

## <a name="dual-language-system-prompts-for-your-organization"></a><span data-ttu-id="67bc0-127">Solicitudes de sistema de doble idioma para su organización</span><span class="sxs-lookup"><span data-stu-id="67bc0-127">Dual language system prompts for your organization</span></span>

<span data-ttu-id="67bc0-128">De forma predeterminada, las solicitudes del sistema de correo de voz se presentan a las personas que llaman en el idioma seleccionado por el usuario al configurar su correo de voz.</span><span class="sxs-lookup"><span data-stu-id="67bc0-128">By default, the voicemail system prompts are presented to callers in the language selected by the user when setting up their voicemail.</span></span> <span data-ttu-id="67bc0-129">Si hay un requisito empresarial para que se presenten las solicitudes del sistema de correo de voz en dos idiomas, puede hacerlo con [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span><span class="sxs-lookup"><span data-stu-id="67bc0-129">If there is a business requirement to have the voicemail system prompts presented in two languages, this can be done by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span></span> <span data-ttu-id="67bc0-130">Se debe establecer un idioma principal y secundario y puede que no sea el mismo.</span><span class="sxs-lookup"><span data-stu-id="67bc0-130">A primary and secondary language must be set and may not be the same.</span></span> <span data-ttu-id="67bc0-131">Para ello, ejecute:</span><span class="sxs-lookup"><span data-stu-id="67bc0-131">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -PrimarySystemPromptLanguage en-US -SecondarySystemPromptLanguage es-ES
```

## <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="67bc0-132">Desactivar la transcripción para un usuario</span><span class="sxs-lookup"><span data-stu-id="67bc0-132">Turning off transcription for a user</span></span>

<span data-ttu-id="67bc0-133">Las directivas de usuarios se evalúan antes que la configuración predeterminada de la organización.</span><span class="sxs-lookup"><span data-stu-id="67bc0-133">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="67bc0-134">Por ejemplo, si la transcripción del correo de voz está habilitada para todos los usuarios, puede asignar una directiva para deshabilitar la transcripción de un usuario específico mediante el cmdlet [Grant-CsOnlineVoicemailPolicy.](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy)</span><span class="sxs-lookup"><span data-stu-id="67bc0-134">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) cmdlet.</span></span>

<span data-ttu-id="67bc0-135">Para deshabilitar la transcripción para un único usuario, ejecute:</span><span class="sxs-lookup"><span data-stu-id="67bc0-135">To disable transcription for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

## <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="67bc0-136">Activar el enmascaramiento de contenido ofensivo de transcripción para un usuario</span><span class="sxs-lookup"><span data-stu-id="67bc0-136">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="67bc0-137">Para habilitar el enmascaramiento de contenido ofensivo de transcripción para un usuario específico, puede asignar una directiva para habilitar el enmascaramiento de contenido ofensivo de transcripción para un usuario específico mediante el cmdlet [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy).</span><span class="sxs-lookup"><span data-stu-id="67bc0-137">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) cmdlet.</span></span>

<span data-ttu-id="67bc0-138">Para habilitar el enmascaramiento de contenido ofensivo de transcripción para un solo usuario, ejecute:</span><span class="sxs-lookup"><span data-stu-id="67bc0-138">To enable transcription profanity masking for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

## <a name="changing-the-recording-duration-for-a-user"></a><span data-ttu-id="67bc0-139">Cambiar la duración de la grabación para un usuario</span><span class="sxs-lookup"><span data-stu-id="67bc0-139">Changing the recording duration for a user</span></span>

<span data-ttu-id="67bc0-140">Primero debe crear una directiva de correo de voz personalizada con el cmdlet [New-CsOnlineVoicemailPolicy.](/powershell/module/skype/New-CsOnlineVoicemailPolicy)</span><span class="sxs-lookup"><span data-stu-id="67bc0-140">You must first create a custom voicemail policy using the [New-CsOnlineVoicemailPolicy](/powershell/module/skype/New-CsOnlineVoicemailPolicy) cmdlet.</span></span> <span data-ttu-id="67bc0-141">El comando que se muestra a continuación crea una directiva de correo de voz en línea por usuario OneMinuteVoicemailPolicy con MaximumRecordingLength establecido en 60 segundos y otros campos establecidos en valor global de nivel de inquilino.</span><span class="sxs-lookup"><span data-stu-id="67bc0-141">The command shown below creates a per-user online voicemail policy OneMinuteVoicemailPolicy with MaximumRecordingLength set to 60 seconds and other fields set to tenant level global value.</span></span>

```PowerShell
New-CsOnlineVoicemailPolicy -Identity "OneMinuteVoicemailPolicy" -MaximumRecordingLength ([TimeSpan]::FromSeconds(60))
```

<span data-ttu-id="67bc0-142">Para asignar esta directiva personalizada a un usuario, ejecute:</span><span class="sxs-lookup"><span data-stu-id="67bc0-142">To assign this custom policy to a user, run:</span></span> 

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName OneMinuteVoicemailPolicy -Identity sip:amosmar@contoso.com
```

## <a name="dual-language-system-prompts-for-a-user"></a><span data-ttu-id="67bc0-143">Solicitudes de sistema de doble idioma para un usuario</span><span class="sxs-lookup"><span data-stu-id="67bc0-143">Dual language system prompts for a user</span></span>

<span data-ttu-id="67bc0-144">Primero debe crear una directiva de correo de voz personalizada con el cmdlet [New-CsOnlineVoicemailPolicy.](/powershell/module/skype/New-CsOnlineVoicemailPolicy)</span><span class="sxs-lookup"><span data-stu-id="67bc0-144">You must first create a custom voicemail policy using the [New-CsOnlineVoicemailPolicy](/powershell/module/skype/New-CsOnlineVoicemailPolicy) cmdlet.</span></span> <span data-ttu-id="67bc0-145">El comando que se muestra a continuación crea una directiva de correo de voz en línea por usuario enUS-esSP-VoicemailPolicy con primarysystempromptLanguage establecido en en-US (Inglés - Estados Unidos) y secondarySystemPromptLanguage establecido en es-SP (español - España).</span><span class="sxs-lookup"><span data-stu-id="67bc0-145">The command shown below creates a per-user online voicemail policy enUS-esSP-VoicemailPolicy with the PrimarySystemPromptLanguage set to en-US (English - United States) and the SecondarySystemPromptLanguage set to es-SP (Spanish - Spain).</span></span>

```PowerShell
New-CsOnlineVoicemailPolicy -Identity "enUS-esES-VoicemailPolicy" -PrimarySystemPromptLanguage en-US -SecondarySystemPromptLanguage es-ES
```

<span data-ttu-id="67bc0-146">Para asignar esta directiva personalizada a un usuario, ejecute:</span><span class="sxs-lookup"><span data-stu-id="67bc0-146">To assign this custom policy to a user, run:</span></span> 

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName "enUS-esES-VoicemailPolicy" -Identity sip:amosmar@contoso.com
```

> [!NOTE]
> <span data-ttu-id="67bc0-147">El cmdlet Get-CsOnlineVoicemailPolicy no devuelve actualmente los valores de PrimarySystemPromptLanguage y SecondarySystemPromptLanguage.</span><span class="sxs-lookup"><span data-stu-id="67bc0-147">The Get-CsOnlineVoicemailPolicy cmdlet is not currently returning the values for PrimarySystemPromptLanguage and SecondarySystemPromptLanguage.</span></span> <span data-ttu-id="67bc0-148">Para ver estos valores, modifique el comando de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="67bc0-148">To see these values modify the command as follows:</span></span>
>
> >```PowerShell
> > (Get-CsOnlineVoicemailPolicy -Identity PolicyName).PrimarySystemPromptLanguage or
> > (Get-CsOnlineVoicemailPolicy -Identity PolicyName).SecondarySystemPromptLanguage 
>
> <span data-ttu-id="67bc0-149">Reemplace **PolicyName** por el nombre de la directiva.</span><span class="sxs-lookup"><span data-stu-id="67bc0-149">Replace **PolicyName** with the name of the policy.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="67bc0-150">El servicio de correo de voz Microsoft 365 y Office 365 las directivas de correo de voz y actualiza la memoria caché cada 6 horas.</span><span class="sxs-lookup"><span data-stu-id="67bc0-150">The voicemail service in Microsoft 365 and Office 365 caches voicemail policies and updates the cache every 6 hours.</span></span> <span data-ttu-id="67bc0-151">Por lo tanto, los cambios de directiva que realice pueden tardar hasta 6 horas en aplicarse.</span><span class="sxs-lookup"><span data-stu-id="67bc0-151">So, policy changes that you make can take up to 6 hours to be applied.</span></span>
