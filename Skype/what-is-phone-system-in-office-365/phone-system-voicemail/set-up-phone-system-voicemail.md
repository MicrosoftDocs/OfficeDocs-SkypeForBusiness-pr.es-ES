---
title: Configurar correo de voz del sistema de teléfono
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
- Strat_SB_PSTN
description: 'Learn how to set up the phone system (Cloud PBX) voicemail for your Skype for Business users. '
ms.openlocfilehash: bc96530de35f98a71863ad0c46ef026d5e670412
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2018
---
# <a name="set-up-phone-system-voicemail"></a><span data-ttu-id="53eb9-103">Configurar correo de voz del sistema de teléfono</span><span class="sxs-lookup"><span data-stu-id="53eb9-103">Set up Phone System voicemail</span></span>

<span data-ttu-id="53eb9-104">Este artículo es para la [administración de Office 365](http://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) que quiere configurar la característica de correo de voz de sistema telefónico para todos los usuarios del negocio.</span><span class="sxs-lookup"><span data-stu-id="53eb9-104">This article is for the [Office 365 admin](http://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) who wants to set up the Phone System voicemail feature for everyone in the business.</span></span>
  
> [!NOTE]
> <span data-ttu-id="53eb9-105">Correo de voz de sistema de teléfono es compatible con mensajes de correo de voz para depositar sólo en un buzón de Exchange y no es compatible con los sistemas de correo de terceros.</span><span class="sxs-lookup"><span data-stu-id="53eb9-105">Phone System voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> <span data-ttu-id="53eb9-106">Como un mecanismo de reserva, correo de voz del sistema de teléfono puede reenviar mensajes mediante SMTP, lo que significa que los usuarios con un buzón en un sistema de correo de terceros recibirán sus mensajes de correo de voz con ningún tiempo de actividad de servicio garantizado u otras características de correo de voz, como el cambio sus saludos y otras configuraciones.</span><span class="sxs-lookup"><span data-stu-id="53eb9-106">As a fallback mechanism, Phone System voicemail can resend messages using SMTP, which means users with a mailbox on a third-party email system will receive their voicemail messages with no guaranteed service uptime or other voicemail features, such as changing their greetings and other settings.</span></span> 
  
## <a name="cloud-only-environments-set-up-phone-system-voicemail"></a><span data-ttu-id="53eb9-107">Entornos sólo de nube: configurar correo de voz del sistema de teléfono</span><span class="sxs-lookup"><span data-stu-id="53eb9-107">Cloud-only environments: Set up Phone System voicemail</span></span>

<span data-ttu-id="53eb9-108">Para Skype para usuarios de negocios en línea y planes de llamada, correo de voz del sistema telefónico se configuran automáticamente y aprovisionado para los usuarios después de asignar una licencia de **Sistema de teléfono** y un número de teléfono a ellos.</span><span class="sxs-lookup"><span data-stu-id="53eb9-108">For Skype for Business Online and Calling Plans users, Phone System voicemail is automatically set up and provisioned for users after you assign a **Phone System** license and a phone number to them.</span></span>
  
1. <span data-ttu-id="53eb9-109">Si la función de sistema de teléfono no está incluida en el plan, debe adquirir licencias adicionales de **Sistema telefónico** .</span><span class="sxs-lookup"><span data-stu-id="53eb9-109">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="53eb9-110">También necesitará adquirir una licencia de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="53eb9-110">You may also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="53eb9-111">Consulte [Skype para negocios y equipos de Microsoft licencias adicionales](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="53eb9-111">See [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="53eb9-112">[Asignar o quitar licencias para Office 365 para el negocio](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), la [Asigne Skype para licencias de negocio y equipos de Microsoft](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)y las licencias de Exchange Online a las personas de su empresa.</span><span class="sxs-lookup"><span data-stu-id="53eb9-112">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span> <span data-ttu-id="53eb9-113">Después de hacerlo, podrán recibir mensajes del correo de voz.</span><span class="sxs-lookup"><span data-stu-id="53eb9-113">After you do that, they will be able to receive voicemail messages!</span></span>
    
3. <span data-ttu-id="53eb9-114">Compatibilidad con transcripción de correo de voz se ha agregado a partir de marzo de 2017 y está habilitada de forma predeterminada para todas las organizaciones y los usuarios.</span><span class="sxs-lookup"><span data-stu-id="53eb9-114">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users.</span></span> <span data-ttu-id="53eb9-115">Puede deshabilitar la transcripción para su organización mediante Windows PowerShell y los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="53eb9-115">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>
    
## <a name="phone-system-with-on-premises-environments"></a><span data-ttu-id="53eb9-116">Sistema de teléfono con los entornos locales</span><span class="sxs-lookup"><span data-stu-id="53eb9-116">Phone System with on-premises environments</span></span>

<span data-ttu-id="53eb9-117">Es la siguiente información acerca de cómo configurar el correo de voz del sistema telefónico para trabajar con entornos de Plan de llamadas locales.</span><span class="sxs-lookup"><span data-stu-id="53eb9-117">The following information is about configuring Phone System voicemail to work with on-premises Calling Plan environments.</span></span>
  
1. <span data-ttu-id="53eb9-118">Si la función de sistema de teléfono no está incluida en el plan, debe adquirir licencias adicionales de **Sistema telefónico** .</span><span class="sxs-lookup"><span data-stu-id="53eb9-118">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="53eb9-119">También necesitará adquirir una licencia de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="53eb9-119">You also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="53eb9-120">Consulte [Skype para negocios y equipos de Microsoft licencias adicionales](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="53eb9-120">See [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="53eb9-121">[Asignar o quitar licencias para Office 365 para el negocio](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), la [Asigne Skype para licencias de negocio y equipos de Microsoft](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)y las licencias de Exchange Online a las personas de su empresa.</span><span class="sxs-lookup"><span data-stu-id="53eb9-121">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span>
    
3. <span data-ttu-id="53eb9-122">Siga las instrucciones en la sección **Habilitar usuarios para la voz del sistema de teléfono y los servicios de correo de voz** de la [Configurar Skype para conector de nube Business Edition Guía](https://technet.microsoft.com/en-us/library/mt605228.aspx).</span><span class="sxs-lookup"><span data-stu-id="53eb9-122">Follow the instructions in the **Enable users for Phone System voice and voice mail services** section of the [Configure Skype for Business Cloud Connector Edition guide](https://technet.microsoft.com/en-us/library/mt605228.aspx).</span></span>
    
4. <span data-ttu-id="53eb9-123">Compatibilidad con transcripción de correo de voz se ha agregado a partir de marzo de 2017 y está habilitada de forma predeterminada para todas las organizaciones y los usuarios.</span><span class="sxs-lookup"><span data-stu-id="53eb9-123">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users.</span></span> <span data-ttu-id="53eb9-124">Puede deshabilitar la transcripción para su organización mediante Windows PowerShell y los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="53eb9-124">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span> 
    
5. <span data-ttu-id="53eb9-125">También puede ver el [correo de voz de PBX de Azure soporte para Exchange Server](https://support.microsoft.com/en-us/kb/3195158) para aprender a configurar la entrega de mensajes de correo de voz de Azure para los usuarios del sistema telefónico que tienen un buzones locales.</span><span class="sxs-lookup"><span data-stu-id="53eb9-125">You can also see [Azure PBX voicemail support for Exchange Server](https://support.microsoft.com/en-us/kb/3195158) to learn how to configure delivery of Azure voicemail messages for Phone System users who have a on-premises mailboxes.</span></span>
    
## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="53eb9-126">Configuración de directivas de correo de voz en su organización</span><span class="sxs-lookup"><span data-stu-id="53eb9-126">Setting voicemail policies in your organization</span></span>

<span data-ttu-id="53eb9-127">Transcripción de correo de voz está habilitada de forma predeterminada para todas las organizaciones y usuarios; Sin embargo, se puede controlar mediante los cmdlets [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) y [CsOnlineVoicemailPolicy de la concesión](https://technet.microsoft.com/library/mt798311.aspx) .</span><span class="sxs-lookup"><span data-stu-id="53eb9-127">Voicemail transcription is enabled by default for all organizations and users; however, you can control it by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlets.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="53eb9-128">No se puede crear una nueva instancia de directiva transcripción mediante el cmdlet **New-CsOnlineVoiceMailPolicy** , y no se puede quitar una instancia de directiva existente con el cmdlet **Remove-CsOnlineVoiceMailPolicy** .</span><span class="sxs-lookup"><span data-stu-id="53eb9-128">You can't create a new policy instance for transcription using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>
  
<span data-ttu-id="53eb9-129">Puede administrar la configuración de la transcripción para sus usuarios con las directivas del correo de voz.</span><span class="sxs-lookup"><span data-stu-id="53eb9-129">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="53eb9-130">Para ver todas las instancias de la directiva de correo de voz disponibles, puede utilizar el cmdlet [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) .</span><span class="sxs-lookup"><span data-stu-id="53eb9-130">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>
  
 <span data-ttu-id="53eb9-131">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="53eb9-131">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>
  
![Get-CsOnlineVoiceMailPolicy results window.](../../images/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="53eb9-133">Desactivar la transcripción para su organización</span><span class="sxs-lookup"><span data-stu-id="53eb9-133">Turning off transcription for your organization</span></span>

<span data-ttu-id="53eb9-134">Debido a la configuración predeterminada de transcripción está activada para la organización, desea deshabilitar utilizando el [Conjunto CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx).</span><span class="sxs-lookup"><span data-stu-id="53eb9-134">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx).</span></span> <span data-ttu-id="53eb9-135">Para ello, ejecute:</span><span class="sxs-lookup"><span data-stu-id="53eb9-135">To do this, run:</span></span>
  
```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="53eb9-136">Desactivar la transcripción para un usuario</span><span class="sxs-lookup"><span data-stu-id="53eb9-136">Turning off transcription for a user</span></span>

<span data-ttu-id="53eb9-137">Las directivas de usuarios se evalúan antes que la configuración predeterminada de la organización.</span><span class="sxs-lookup"><span data-stu-id="53eb9-137">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="53eb9-138">Por ejemplo, si está habilitada la transcripción de correo de voz para todos los usuarios, puede asignar una directiva para deshabilitar la transcripción para un usuario específico mediante el cmdlet de [Concesión CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) .</span><span class="sxs-lookup"><span data-stu-id="53eb9-138">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>
  
<span data-ttu-id="53eb9-139">Para deshabilitar la transcripción para un único usuario, ejecute:</span><span class="sxs-lookup"><span data-stu-id="53eb9-139">To disable transcription for a single user, run:</span></span>
  
```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="53eb9-p110">El servicio de correo de voz de Office 365 almacena en caché las directivas de correo de voz y actualiza la memoria caché cada 4 horas. Por lo tanto, los cambios de las directivas que realice pueden tardar hasta 4 horas en aplicarse.</span><span class="sxs-lookup"><span data-stu-id="53eb9-p110">The voicemail service in Office 365 caches voicemail policies and updates the cache every 4 hours. So, policy changes that you make can take up to 4 hours to be applied.</span></span> 
  
## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="53eb9-142">Ayudar a los usuarios a aprender acerca de las características del correo de voz de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="53eb9-142">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="53eb9-143">Tenemos información de capacitación y artículos para ayudar a los usuarios a tener éxito con Skype para correo de voz de negocio.</span><span class="sxs-lookup"><span data-stu-id="53eb9-143">We have training information and articles to help your users be successful with Skype for Business voicemail.</span></span> <span data-ttu-id="53eb9-144">Pídales que consulten los siguientes artículos:</span><span class="sxs-lookup"><span data-stu-id="53eb9-144">Point them to the following articles:</span></span>
  
- <span data-ttu-id="53eb9-145">[Comprobar Skype para opciones y correo de voz de negocio](http://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): en este artículo se explica cómo escuchar su correo de voz de Skype para el negocio, cambiar su saludo del correo de voz, cambiar la configuración de correo de voz y escuchar su correo de voz a diferentes velocidades.</span><span class="sxs-lookup"><span data-stu-id="53eb9-145">[Check Skype for Business voicemail and options](http://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>
    
- [<span data-ttu-id="53eb9-146">Aprendizaje de Skype Empresarial 2016</span><span class="sxs-lookup"><span data-stu-id="53eb9-146">Skype for Business 2016 training</span></span>](http://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)
    
## <a name="related-topics"></a><span data-ttu-id="53eb9-147">See also</span><span class="sxs-lookup"><span data-stu-id="53eb9-147">Related topics</span></span>
[<span data-ttu-id="53eb9-148">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="53eb9-148">Set up Skype for Business Online</span></span>](../../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

[<span data-ttu-id="53eb9-149">Esto es lo que conseguirá con Sistema telefónico en Office 365</span><span class="sxs-lookup"><span data-stu-id="53eb9-149">Here's what you get with Phone System in Office 365</span></span>](../../what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system.md)
