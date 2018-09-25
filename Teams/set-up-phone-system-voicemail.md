---
title: Configurar el correo de voz de Sistema telefónico
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'Learn how to set up the phone system (Cloud PBX) voicemail for your Skype for Business users. '
ms.openlocfilehash: 6538713096804897d68d5b71d86bb84cf79be9ab
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "25015744"
---
# <a name="set-up-phone-system-voicemail"></a><span data-ttu-id="3103b-103">Configurar el correo de voz de Sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="3103b-103">Set up Phone System voicemail</span></span>

<span data-ttu-id="3103b-104">En este artículo es para la [administración de Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) que desea configurar la característica de correo de voz de sistema telefónico para todos los usuarios en la empresa.</span><span class="sxs-lookup"><span data-stu-id="3103b-104">This article is for the [Office 365 admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) who wants to set up the Phone System voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="3103b-105">Correo de voz de teléfono del sistema admite depositar los mensajes de correo de voz sólo en un buzón de Exchange y no es compatible con los sistemas de correo electrónico de otro fabricante.</span><span class="sxs-lookup"><span data-stu-id="3103b-105">Phone System voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> <span data-ttu-id="3103b-106">Como un mecanismo de reserva, correo de voz de sistema telefónico puede reenviar mensajes mediante SMTP, lo que significa que los usuarios con un buzón de correo en un sistema de correo electrónico de otro fabricante recibirán sus mensajes de correo de voz con ningún tiempo de actividad de servicio garantizado u otras características de correo de voz, como el cambio sus saludos y otras opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="3103b-106">As a fallback mechanism, Phone System voicemail can resend messages using SMTP, which means users with a mailbox on a third-party email system will receive their voicemail messages with no guaranteed service uptime or other voicemail features, such as changing their greetings and other settings.</span></span>

## <a name="cloud-only-environments-set-up-phone-system-voicemail"></a><span data-ttu-id="3103b-107">Entornos de nube: configurar el correo de voz del sistema de teléfono</span><span class="sxs-lookup"><span data-stu-id="3103b-107">Cloud-only environments: Set up Phone System voicemail</span></span>

<span data-ttu-id="3103b-108">Para Skype para los usuarios en línea de negocio y planes de llamada, correo de voz del sistema telefónico se configuran automáticamente y aprovisionar para los usuarios después de asignar una licencia de **Sistema telefónico** y un número de teléfono a ellos.</span><span class="sxs-lookup"><span data-stu-id="3103b-108">For Skype for Business Online and Calling Plans users, Phone System voicemail is automatically set up and provisioned for users after you assign a **Phone System** license and a phone number to them.</span></span>
  
1. <span data-ttu-id="3103b-109">Si la característica del sistema de teléfono no está incluida en el plan, debe comprar licencias de complemento de **Sistema telefónico** .</span><span class="sxs-lookup"><span data-stu-id="3103b-109">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="3103b-110">También es posible que necesite comprar una licencia de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3103b-110">You may also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="3103b-111">Vea [Skype para profesionales y los equipos de Microsoft complemento licencias](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).</span><span class="sxs-lookup"><span data-stu-id="3103b-111">See [Skype for Business and Microsoft Teams add-on licensing](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).</span></span>
    
2. <span data-ttu-id="3103b-112">[Asignar o quitar licencias de Office 365 para profesionales](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), la [Asignación de Skype para licencias de negocio y equipos de Microsoft](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)y las licencias de Exchange Online a las personas de su empresa.</span><span class="sxs-lookup"><span data-stu-id="3103b-112">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Skype for Business and Microsoft Teams licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses), and the Exchange Online licenses to the people in your business.</span></span> <span data-ttu-id="3103b-113">Después de hacerlo, podrán recibir mensajes del correo de voz.</span><span class="sxs-lookup"><span data-stu-id="3103b-113">After you do that, they will be able to receive voicemail messages!</span></span>
    
3. <span data-ttu-id="3103b-114">Compatibilidad con transcripción de correo de voz se ha agregado a partir de marzo de 2017 y está habilitada de forma predeterminada para todos los usuarios y las organizaciones.</span><span class="sxs-lookup"><span data-stu-id="3103b-114">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users.</span></span> <span data-ttu-id="3103b-115">Puede deshabilitar la transcripción para su organización utilizando Windows PowerShell y siguiendo los pasos que se indican a continuación.</span><span class="sxs-lookup"><span data-stu-id="3103b-115">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

## <a name="phone-system-with-on-premises-environments"></a><span data-ttu-id="3103b-116">Sistema telefónico con entornos locales</span><span class="sxs-lookup"><span data-stu-id="3103b-116">Phone System with on-premises environments</span></span>

<span data-ttu-id="3103b-117">La siguiente información se refiere a la configuración del correo de voz del Sistema telefónico para que funcione con los entornos locales del Plan de llamadas.</span><span class="sxs-lookup"><span data-stu-id="3103b-117">The following information is about configuring Phone System voicemail to work with on-premises Calling Plan environments.</span></span>
  
1. <span data-ttu-id="3103b-118">Si la característica del sistema de teléfono no está incluida en el plan, debe comprar licencias de complemento de **Sistema telefónico** .</span><span class="sxs-lookup"><span data-stu-id="3103b-118">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="3103b-119">También necesitará comprar una licencia de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3103b-119">You also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="3103b-120">Vea [Skype para profesionales y los equipos de Microsoft complemento licencias](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).</span><span class="sxs-lookup"><span data-stu-id="3103b-120">See [Skype for Business and Microsoft Teams add-on licensing](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).</span></span>
    
2. <span data-ttu-id="3103b-121">[Asignar o quitar licencias de Office 365 para profesionales](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), la [Asignación de Skype para licencias de negocio y equipos de Microsoft](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)y las licencias de Exchange Online a las personas de su empresa.</span><span class="sxs-lookup"><span data-stu-id="3103b-121">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Skype for Business and Microsoft Teams licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses), and the Exchange Online licenses to the people in your business.</span></span>
    
3. <span data-ttu-id="3103b-122">Siga las instrucciones que aparecen en la sección **Permitir que los usuarios de voz de sistema telefónico y servicios de correo de voz** de la [Configuración de Skype para guía de Business Edition de conector en la nube](https://technet.microsoft.com/library/mt605228.aspx).</span><span class="sxs-lookup"><span data-stu-id="3103b-122">Follow the instructions in the **Enable users for Phone System voice and voice mail services** section of the [Configure Skype for Business Cloud Connector Edition guide](https://technet.microsoft.com/library/mt605228.aspx).</span></span>

4. <span data-ttu-id="3103b-123">Compatibilidad con transcripción de correo de voz se ha agregado a partir de marzo de 2017 y está habilitada de forma predeterminada para todos los usuarios y las organizaciones.</span><span class="sxs-lookup"><span data-stu-id="3103b-123">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users.</span></span> <span data-ttu-id="3103b-124">Puede deshabilitar la transcripción para su organización utilizando Windows PowerShell y siguiendo los pasos que se indican a continuación.</span><span class="sxs-lookup"><span data-stu-id="3103b-124">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

5. <span data-ttu-id="3103b-125">También puede ver el [soporte de correo de voz de Azure PBX para Exchange Server](https://support.microsoft.com/kb/3195158) para aprender a configurar la entrega de mensajes de correo de voz de Azure para usuarios del Sistema telefónico con buzones de correo locales.</span><span class="sxs-lookup"><span data-stu-id="3103b-125">You can also see [Azure PBX voicemail support for Exchange Server](https://support.microsoft.com/kb/3195158) to learn how to configure delivery of Azure voicemail messages for Phone System users who have a on-premises mailboxes.</span></span>

## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="3103b-126">Configuración de directivas de correo de voz en su organización</span><span class="sxs-lookup"><span data-stu-id="3103b-126">Setting voicemail policies in your organization</span></span>

<span data-ttu-id="3103b-127">La transcripción de correo de voz está habilitada de forma predeterminada y el enmascaramiento de contenido ofensivo de transcripción está deshabilitado de forma predeterminada para todos los usuarios y organizaciones; sin embargo, puede controlarlos mediante los cmdlets [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) y [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx).</span><span class="sxs-lookup"><span data-stu-id="3103b-127">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlets.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3103b-128">No se puede crear una nueva instancia de directiva para transcripción y contenido ofensivo de transcripción de transparencias con el cmdlet **New-CsOnlineVoiceMailPolicy** y no se puede quitar una instancia de directiva existente con el cmdlet **Remove-CsOnlineVoiceMailPolicy** .</span><span class="sxs-lookup"><span data-stu-id="3103b-128">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="3103b-129">Puede administrar la configuración de la transcripción para sus usuarios con las directivas del correo de voz.</span><span class="sxs-lookup"><span data-stu-id="3103b-129">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="3103b-130">Para ver todas las instancias de la directiva de correo de voz disponibles, puede usar el cmdlet [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) .</span><span class="sxs-lookup"><span data-stu-id="3103b-130">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>

 <span data-ttu-id="3103b-131">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="3103b-131">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>
  
![Get-CsOnlineVoiceMailPolicy results window.](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="3103b-133">Desactivar la transcripción para su organización</span><span class="sxs-lookup"><span data-stu-id="3103b-133">Turning off transcription for your organization</span></span>

<span data-ttu-id="3103b-134">Debido a que el valor predeterminado de transcripción está activada para la organización, desea deshabilitar mediante el uso de [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span><span class="sxs-lookup"><span data-stu-id="3103b-134">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="3103b-135">Para ello, ejecute:</span><span class="sxs-lookup"><span data-stu-id="3103b-135">To do this, run:</span></span>

```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="3103b-136">Activar el enmascaramiento de contenido ofensivo de transcripción para su organización</span><span class="sxs-lookup"><span data-stu-id="3103b-136">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="3103b-137">El enmascaramiento de contenido ofensivo de transcripción está deshabilitado de forma predeterminada para su organización.</span><span class="sxs-lookup"><span data-stu-id="3103b-137">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="3103b-138">Si hay un requisito de negocio para habilitarlo, puede habilitar el enmascaramiento de contenido ofensivo de transcripción mediante [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span><span class="sxs-lookup"><span data-stu-id="3103b-138">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="3103b-139">Para ello, ejecute:</span><span class="sxs-lookup"><span data-stu-id="3103b-139">To do this, run:</span></span>

```
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="3103b-140">Desactivar la transcripción para un usuario</span><span class="sxs-lookup"><span data-stu-id="3103b-140">Turning off transcription for a user</span></span>

<span data-ttu-id="3103b-141">Las directivas de usuarios se evalúan antes que la configuración predeterminada de la organización.</span><span class="sxs-lookup"><span data-stu-id="3103b-141">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="3103b-142">Por ejemplo, si está habilitada la transcripción de correo de voz para todos los usuarios, puede asignar una directiva para deshabilitar transcripción para un usuario específico mediante el cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) .</span><span class="sxs-lookup"><span data-stu-id="3103b-142">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="3103b-143">Para deshabilitar la transcripción para un único usuario, ejecute:</span><span class="sxs-lookup"><span data-stu-id="3103b-143">To disable transcription for a single user, run:</span></span>

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="3103b-144">Activar el enmascaramiento de contenido ofensivo de transcripción para un usuario</span><span class="sxs-lookup"><span data-stu-id="3103b-144">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="3103b-145">Para habilitar el enmascaramiento de contenido ofensivo de transcripción para un usuario específico, puede asignar una directiva para habilitar el enmascaramiento de contenido ofensivo de transcripción para un usuario específico mediante el cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx).</span><span class="sxs-lookup"><span data-stu-id="3103b-145">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="3103b-146">Para habilitar el enmascaramiento de contenido ofensivo de transcripción para un solo usuario, ejecute:</span><span class="sxs-lookup"><span data-stu-id="3103b-146">To enable transcription profanity masking for a single user, run:</span></span>

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="3103b-p111">El servicio de correo de voz de Office 365 almacena en caché las directivas de correo de voz y actualiza la memoria caché cada 4 horas. Por lo tanto, los cambios de las directivas que realice pueden tardar hasta 4 horas en aplicarse.</span><span class="sxs-lookup"><span data-stu-id="3103b-p111">The voicemail service in Office 365 caches voicemail policies and updates the cache every 4 hours. So, policy changes that you make can take up to 4 hours to be applied.</span></span>

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="3103b-149">Ayudar a los usuarios a aprender acerca de las características del correo de voz de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="3103b-149">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="3103b-150">Disponemos de información de recursos de aprendizaje y artículos para ayudar a los usuarios a tener éxito con Skype para correo de voz empresarial.</span><span class="sxs-lookup"><span data-stu-id="3103b-150">We have training information and articles to help your users be successful with Skype for Business voicemail.</span></span> <span data-ttu-id="3103b-151">Pídales que consulten los siguientes artículos:</span><span class="sxs-lookup"><span data-stu-id="3103b-151">Point them to the following articles:</span></span>

- <span data-ttu-id="3103b-152">[Comprobación de Skype para opciones y correo de voz empresarial](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): en este artículo se explica cómo escuchar el correo de voz de Skype para la empresa, cambiar el saludo del correo de voz, cambiar la configuración del correo de voz y escuchar el correo de voz a diferentes velocidades.</span><span class="sxs-lookup"><span data-stu-id="3103b-152">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="3103b-153">Aprendizaje de Skype Empresarial 2016</span><span class="sxs-lookup"><span data-stu-id="3103b-153">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="3103b-154">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="3103b-154">Related topics</span></span>
[<span data-ttu-id="3103b-155">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="3103b-155">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="3103b-156">Esto es lo que conseguirá con Sistema telefónico en Office 365</span><span class="sxs-lookup"><span data-stu-id="3103b-156">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)


