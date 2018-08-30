---
title: Configurar el correo de voz del Sistema telefónico
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Phone System
description: 'Aprenda a configurar el correo de voz del sistema telefónico (Cloud PBX) para los usuarios de Skype for Business. '
ms.openlocfilehash: d311c6d0c0f6965d81f557c2080a9bb331de557b
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2018
ms.locfileid: "23252893"
---
# <a name="set-up-phone-system-voicemail"></a><span data-ttu-id="1cfe0-103">Configurar el correo de voz del Sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="1cfe0-103">Set up Phone System voicemail</span></span>

<span data-ttu-id="1cfe0-104">Este artículo está destinado a los [administradores de Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) que deseen configurar el correo de voz del Sistema telefónico para todos los miembros de sus organizaciones.</span><span class="sxs-lookup"><span data-stu-id="1cfe0-104">This article is for the [About Office 365 admin roles](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) who wants to set up Skype for Business Cloud PBX voicemail for everyone in their business.</span></span>

> [!NOTE]
> <span data-ttu-id="1cfe0-105">El correo de voz del Sistema telefónico permite depositar mensajes de voz solo en un buzón de Exchange y no admite sistemas de correo electrónico de terceros.</span><span class="sxs-lookup"><span data-stu-id="1cfe0-105">Cloud PBX voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> <span data-ttu-id="1cfe0-106">Como mecanismo de reserva, el correo de voz del Sistema telefónico puede reenviar mensajes mediante SMTP, lo que significa que los usuarios que tengan un buzón de un sistema de correo electrónico de terceros recibirán sus mensajes del correo de voz sin ninguna garantía del tiempo de actividad del servicio u otras funciones del correo de voz, como poder cambiar los saludos y otras configuraciones.</span><span class="sxs-lookup"><span data-stu-id="1cfe0-106">As a fallback mechanism, Cloud PBX Voicemail can resend messages using SMTP, which means users with a mailbox on a third-party email system will receive their voicemail messages with no guaranteed service uptime or other voicemail features, such as changing their greetings and other settings .</span></span>

## <a name="cloud-only-environments-set-up-phone-system-voicemail"></a><span data-ttu-id="1cfe0-107">Entornos de solo nube: configurar el correo de voz del Sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="1cfe0-107">Set up Phone System voicemail</span></span>

<span data-ttu-id="1cfe0-108">Para los usuarios de Skype for Business Online y de los planes de llamadas, el buzón de voz del Sistema telefónico se configura y aprovisiona automáticamente para los usuarios después de asignarles una licencia del **Sistema telefónico** y un número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="1cfe0-108">For Skype for Business Online and PSTN Calling users, Cloud PBX voicemail is automatically set up and provisioned for users after you assign a Skype for Business Cloud PBX license and a phone number to them.</span></span>

1. <span data-ttu-id="1cfe0-109">Si la característica del Sistema telefónico no está incluida en su plan, es posible que tenga que adquirir licencias de complementos de **Sistema telefónico**.</span><span class="sxs-lookup"><span data-stu-id="1cfe0-109">If the Phone System in Office 365 feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="1cfe0-110">También puede que tenga que comprar una licencia de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="1cfe0-110">You may also need to purchase an Exchange Online Plan 2 license.</span></span> <span data-ttu-id="1cfe0-111">Vea [Licencias de complementos de Skype for Business y Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="1cfe0-111">See [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md), and buy the licenses and plan.</span></span>

2. <span data-ttu-id="1cfe0-112">[Asignar o cancelar licencias para Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), las [Asignar licencias de Skype for Business](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) y las licencias de Exchange Online a los miembros de su organización.</span><span class="sxs-lookup"><span data-stu-id="1cfe0-112">[Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) and the[Assign Skype for Business licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) and Exchange Online Plan 2 licenses to the people in your business.</span></span> <span data-ttu-id="1cfe0-113">Después de hacerlo, podrán recibir mensajes del correo de voz.</span><span class="sxs-lookup"><span data-stu-id="1cfe0-113">After you do that, they will be able to receive voicemail messages!</span></span>

3. <span data-ttu-id="1cfe0-114">La compatibilidad de la transcripción del correo de voz se agregó en marzo de 2017 y está habilitada de manera predeterminada para todos los usuarios y organizaciones.</span><span class="sxs-lookup"><span data-stu-id="1cfe0-114">Support for Voicemail transcription has been added as of March 2017 and is enabled by default for all tenants and users.</span></span> <span data-ttu-id="1cfe0-115">Puede deshabilitar la transcripción para su organización utilizando Windows PowerShell y siguiendo los pasos que se indican a continuación.</span><span class="sxs-lookup"><span data-stu-id="1cfe0-115">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

## <a name="phone-system-with-on-premises-environments"></a><span data-ttu-id="1cfe0-116">Sistema telefónico con entornos locales</span><span class="sxs-lookup"><span data-stu-id="1cfe0-116">Phone System with on-premises environments</span></span>

<span data-ttu-id="1cfe0-117">La siguiente información se refiere a la configuración del correo de voz del Sistema telefónico para que funcione con los entornos locales del Plan de llamadas.</span><span class="sxs-lookup"><span data-stu-id="1cfe0-117">The following information is about configuring Phone System voicemail to work with on-premises Calling Plan environments.</span></span>

1. <span data-ttu-id="1cfe0-118">Si la característica del Sistema telefónico no está incluida en su plan, es posible que tenga que adquirir licencias de complementos de **Sistema telefónico**.</span><span class="sxs-lookup"><span data-stu-id="1cfe0-118">If the Phone System in Office 365 feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="1cfe0-119">También debe comprar una licencia de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="1cfe0-119">You also need to purchase an Exchange Online Plan 2 license.</span></span> <span data-ttu-id="1cfe0-120">Vea [Licencias de complementos de Skype for Business y Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="1cfe0-120">See [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md), and buy the licenses and plan.</span></span>

2. <span data-ttu-id="1cfe0-121">[Asignar o cancelar licencias para Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), las [Asignar licencias de Skype for Business](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) y las licencias de Exchange Online a los miembros de su organización.</span><span class="sxs-lookup"><span data-stu-id="1cfe0-121">[Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) and the[Assign Skype for Business licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) and Exchange Online Plan 2 licenses to the people in your business.</span></span>

3. <span data-ttu-id="1cfe0-122">Siga las instrucciones de la sección **Habilitar usuarios para servicios de voz del Sistema telefónico y correo de voz** de la[Guía de configuración de Skype for Business Cloud Connector Edition](https://technet.microsoft.com/en-us/library/mt605228.aspx).</span><span class="sxs-lookup"><span data-stu-id="1cfe0-122">Next, follow the instructions in the **Enable users for Cloud PBX voice and voice mail services** section of the[Configure Skype for Business Cloud Connector Edition guide](https://technet.microsoft.com/en-us/library/mt605228.aspx).</span></span>

4. <span data-ttu-id="1cfe0-123">La compatibilidad de la transcripción del correo de voz se agregó en marzo de 2017 y está habilitada de manera predeterminada para todos los usuarios y organizaciones.</span><span class="sxs-lookup"><span data-stu-id="1cfe0-123">Support for Voicemail transcription has been added as of March 2017 and is enabled by default for all tenants and users.</span></span> <span data-ttu-id="1cfe0-124">Puede deshabilitar la transcripción para su organización utilizando Windows PowerShell y siguiendo los pasos que se indican a continuación.</span><span class="sxs-lookup"><span data-stu-id="1cfe0-124">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

5. <span data-ttu-id="1cfe0-125">También puede ver el [soporte de correo de voz de Azure PBX para Exchange Server](https://support.microsoft.com/en-us/kb/3195158) para aprender a configurar la entrega de mensajes de correo de voz de Azure para usuarios del Sistema telefónico con buzones de correo locales.</span><span class="sxs-lookup"><span data-stu-id="1cfe0-125">You can also see [Azure PBX voicemail support for Exchange Server](https://support.microsoft.com/en-us/kb/3195158) to learn how to configure delivery of Azure voicemail messages for Phone System users who have a on-premises mailboxes.</span></span>

## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="1cfe0-126">Configuración de directivas de correo de voz en su organización</span><span class="sxs-lookup"><span data-stu-id="1cfe0-126">Setting voicemail policies in your organization</span></span>

<span data-ttu-id="1cfe0-127">La transcripción de correo de voz está habilitada de forma predeterminada y el enmascaramiento de contenido ofensivo de transcripción está deshabilitado de forma predeterminada para todos los usuarios y organizaciones; sin embargo, puede controlarlos mediante los cmdlets [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) y [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798311.aspx).</span><span class="sxs-lookup"><span data-stu-id="1cfe0-127">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798311.aspx) cmdlets.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1cfe0-128">No puede crear una nueva instancia de la directiva para la transcripción y el enmascaramiento de contenido ofensivo de transcripción mediante el cmdlet **New-CsOnlineVoiceMailPolicy**, y no puede quitar una instancia de directiva existente mediante el cmdlet **Remove-CsOnlineVoiceMailPolicy**.</span><span class="sxs-lookup"><span data-stu-id="1cfe0-128">You can't create a new policy instance for transcription using the **New-CsOnlineVoiceMailPolicy** cmdlet and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="1cfe0-129">Puede administrar la configuración de la transcripción para sus usuarios con las directivas del correo de voz.</span><span class="sxs-lookup"><span data-stu-id="1cfe0-129">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="1cfe0-130">Para ver todas las instancias de directivas disponibles de correo de voz, puede usar el cmdlet [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx).</span><span class="sxs-lookup"><span data-stu-id="1cfe0-130">To see the all available voicemail policy instances, you can use the[Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>

 <span data-ttu-id="1cfe0-131">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="1cfe0-131">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>

![Get-CsOnlineVoiceMailPolicy results window.](../../images/6cea8310-2d71-4b95-8d36-688472845727.png)

### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="1cfe0-133">Desactivar la transcripción para su organización</span><span class="sxs-lookup"><span data-stu-id="1cfe0-133">Turning off transcription for your organization</span></span>

<span data-ttu-id="1cfe0-134">Como la configuración predeterminada de la transcripción está activada para su organización, podrá deshabilitarla si lo desea mediante el cmdlet [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx).</span><span class="sxs-lookup"><span data-stu-id="1cfe0-134">Because the default setting for transcription is on for your organization, you may want to disable it by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx).</span></span> <span data-ttu-id="1cfe0-135">Para ello, ejecute:</span><span class="sxs-lookup"><span data-stu-id="1cfe0-135">To do this run:</span></span>

```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="1cfe0-136">Activar el enmascaramiento de contenido ofensivo de transcripción para su organización</span><span class="sxs-lookup"><span data-stu-id="1cfe0-136">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="1cfe0-137">El enmascaramiento de contenido ofensivo de transcripción está deshabilitado de forma predeterminada para su organización.</span><span class="sxs-lookup"><span data-stu-id="1cfe0-137">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="1cfe0-138">Si hay un requisito de negocio para habilitarlo, puede habilitar el enmascaramiento de contenido ofensivo de transcripción mediante [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx).</span><span class="sxs-lookup"><span data-stu-id="1cfe0-138">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx).</span></span> <span data-ttu-id="1cfe0-139">Para ello, ejecute:</span><span class="sxs-lookup"><span data-stu-id="1cfe0-139">To do this run:</span></span>

```
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="1cfe0-140">Desactivar la transcripción para un usuario</span><span class="sxs-lookup"><span data-stu-id="1cfe0-140">Turning off transcription for a user</span></span>

<span data-ttu-id="1cfe0-141">Las directivas de usuarios se evalúan antes que la configuración predeterminada de la organización.</span><span class="sxs-lookup"><span data-stu-id="1cfe0-141">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="1cfe0-142">Por ejemplo, si la transcripción del correo de voz está habilitada para todos los usuarios, puede asignar una directiva para deshabilitar la transcripción de un usuario específico mediante el cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx).</span><span class="sxs-lookup"><span data-stu-id="1cfe0-142">For example, if voicemail transcription is enabled for all of your users you can assign a policy to disable transcription for a specific user using [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="1cfe0-143">Para deshabilitar la transcripción para un único usuario, ejecute:</span><span class="sxs-lookup"><span data-stu-id="1cfe0-143">To disable transcription for a single user, run:</span></span>

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="1cfe0-144">Activar el enmascaramiento de contenido ofensivo de transcripción para un usuario</span><span class="sxs-lookup"><span data-stu-id="1cfe0-144">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="1cfe0-145">Para habilitar el enmascaramiento de contenido ofensivo de transcripción para un usuario específico, puede asignar una directiva para habilitar el enmascaramiento de contenido ofensivo de transcripción para un usuario específico mediante el cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798309.aspx).</span><span class="sxs-lookup"><span data-stu-id="1cfe0-145">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="1cfe0-146">Para habilitar el enmascaramiento de contenido ofensivo de transcripción para un solo usuario, ejecute:</span><span class="sxs-lookup"><span data-stu-id="1cfe0-146">To enable transcription profanity masking for a single user, run:</span></span>

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="1cfe0-p111">El servicio de correo de voz de Office 365 almacena en caché las directivas de correo de voz y actualiza la memoria caché cada 4 horas. Por lo tanto, los cambios de las directivas que realice pueden tardar hasta 4 horas en aplicarse.</span><span class="sxs-lookup"><span data-stu-id="1cfe0-p111">The voicemail service in Office 365 caches voicemail policies and updates the cache every 4 hours. So, policy changes that you make can take up to 4 hours to be applied.</span></span>

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="1cfe0-149">Ayudar a los usuarios a aprender acerca de las características del correo de voz de Skype for Business</span><span class="sxs-lookup"><span data-stu-id="1cfe0-149">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="1cfe0-150">Disponemos de información instructiva y artículos que pueden servir de ayuda a los usuarios para que alcancen el éxito con el correo de voz de Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="1cfe0-150">We have a lot of training information and articles to help your users be successful with Skype for Business voicemail.</span></span> <span data-ttu-id="1cfe0-151">Pídales que consulten los siguientes artículos:</span><span class="sxs-lookup"><span data-stu-id="1cfe0-151">Point them to the following articles:</span></span>

- <span data-ttu-id="1cfe0-152">[Comprobar el correo de voz y las opciones de Skype for Business](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): este artículo explica cómo escuchar el correo de voz en Skype for Business, cambiar su saludo, cambiar su configuración y escucharlo a diferentes velocidades.</span><span class="sxs-lookup"><span data-stu-id="1cfe0-152">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="1cfe0-153">Aprendizaje de Skype for Business 2016</span><span class="sxs-lookup"><span data-stu-id="1cfe0-153">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="1cfe0-154">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="1cfe0-154">Related topics</span></span>
[<span data-ttu-id="1cfe0-155">Configurar Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="1cfe0-155">Set up Skype for Business Online</span></span>](../../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

[<span data-ttu-id="1cfe0-156">Esto es lo que conseguirá con el Sistema telefónico de Office 365</span><span class="sxs-lookup"><span data-stu-id="1cfe0-156">Here's what you get with Phone System in Office 365</span></span>](../../what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system.md)


