---
title: Planear el Correo de voz en la nube
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: wasseemh, phans
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'Obtenga información sobre cómo configurar el correo de voz en la nube para los usuarios. '
ms.openlocfilehash: a4d992ac4f42dca1bffe7a4c3d7ae01400b8e635
ms.sourcegitcommit: b2acf18ba6487154ebb4ee46938e96dc56cb2c9a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/09/2019
ms.locfileid: "33865009"
---
# <a name="set-up-cloud-voicemail"></a><span data-ttu-id="b7d50-103">Planear el Correo de voz en la nube</span><span class="sxs-lookup"><span data-stu-id="b7d50-103">Set up Cloud Voicemail</span></span>

<span data-ttu-id="b7d50-104">En este artículo es para la [administración de Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) que desea configurar la característica de correo de voz en la nube para todos los usuarios en la empresa.</span><span class="sxs-lookup"><span data-stu-id="b7d50-104">This article is for the [Office 365 admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) who wants to set up the Cloud Voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="b7d50-105">Correo de voz en la nube admite depositar los mensajes de correo de voz sólo en un buzón de Exchange y no es compatible con los sistemas de correo electrónico de otro fabricante.</span><span class="sxs-lookup"><span data-stu-id="b7d50-105">Cloud Voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> 

## <a name="cloud-only-environments-set-up-cloud-voicemail"></a><span data-ttu-id="b7d50-106">Entornos de nube: configurar el correo de voz en la nube</span><span class="sxs-lookup"><span data-stu-id="b7d50-106">Cloud-only environments: Set up Cloud Voicemail</span></span>

<span data-ttu-id="b7d50-107">Para Skype para los usuarios en línea de negocio y planes de llamada, correo de voz en la nube se configuran automáticamente y aprovisionar para los usuarios después de asignar una licencia de **Sistema telefónico** y un número de teléfono a ellos.</span><span class="sxs-lookup"><span data-stu-id="b7d50-107">For Skype for Business Online and Calling Plans users, Cloud Voicemail is automatically set up and provisioned for users after you assign a **Phone System** license and a phone number to them.</span></span>
  
1. <span data-ttu-id="b7d50-108">Si la característica del sistema de teléfono no está incluida en el plan, debe comprar licencias de complemento de **Sistema telefónico** .</span><span class="sxs-lookup"><span data-stu-id="b7d50-108">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="b7d50-109">También es posible que necesite comprar una licencia de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b7d50-109">You may also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="b7d50-110">Vea [las licencias de complemento de equipos de Microsoft](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="b7d50-110">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="b7d50-111">[Asignar o quitar licencias de Office 365 para profesionales](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), las [licencias de asignar los equipos de Microsoft](assign-teams-licenses.md)y las licencias de Exchange Online a las personas de su empresa.</span><span class="sxs-lookup"><span data-stu-id="b7d50-111">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams licenses](assign-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span> <span data-ttu-id="b7d50-112">Después de hacerlo, podrán recibir mensajes del correo de voz.</span><span class="sxs-lookup"><span data-stu-id="b7d50-112">After you do that, they will be able to receive voicemail messages!</span></span>
    
3. <span data-ttu-id="b7d50-113">Compatibilidad con transcripción de correo de voz se ha agregado a partir de marzo de 2017 y está habilitada de forma predeterminada para todos los usuarios y las organizaciones.</span><span class="sxs-lookup"><span data-stu-id="b7d50-113">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users.</span></span> <span data-ttu-id="b7d50-114">Puede deshabilitar la transcripción para su organización utilizando Windows PowerShell y siguiendo los pasos que se indican a continuación.</span><span class="sxs-lookup"><span data-stu-id="b7d50-114">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

## <a name="phone-system-with-on-premises-environments"></a><span data-ttu-id="b7d50-115">Sistema telefónico con entornos locales</span><span class="sxs-lookup"><span data-stu-id="b7d50-115">Phone System with on-premises environments</span></span>

<span data-ttu-id="b7d50-116">Es la siguiente información acerca de cómo configurar el correo de voz en la nube para trabajar con entornos de planeación de llamada local.</span><span class="sxs-lookup"><span data-stu-id="b7d50-116">The following information is about configuring Cloud Voicemail to work with on-premises Calling Plan environments.</span></span>
  
1. <span data-ttu-id="b7d50-117">Si la característica del sistema de teléfono no está incluida en el plan, debe comprar licencias de complemento de **Sistema telefónico** .</span><span class="sxs-lookup"><span data-stu-id="b7d50-117">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="b7d50-118">También necesitará comprar una licencia de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b7d50-118">You also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="b7d50-119">Vea [las licencias de complemento de equipos de Microsoft](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="b7d50-119">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="b7d50-120">[Asignar o quitar licencias de Office 365 para profesionales](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), las [licencias de asignar los equipos de Microsoft](assign-teams-licenses.md)y las licencias de Exchange Online a las personas de su empresa.</span><span class="sxs-lookup"><span data-stu-id="b7d50-120">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams licenses](assign-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span>
    
3. <span data-ttu-id="b7d50-121">Siga las instrucciones que coincidan con RTC local al llamar a la solución de implementada para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="b7d50-121">Follow instructions matching on-premises PSTN calling solution deployed for your users.</span></span> <span data-ttu-id="b7d50-122">Edition de conector en la nube, siga las instrucciones que aparecen en la sección **Permitir que los usuarios de servicios de voz y correo de voz del sistema de teléfono** de la [Configuración de Skype para guía de Business Edition de conector en la nube](https://technet.microsoft.com/library/mt605228.aspx).</span><span class="sxs-lookup"><span data-stu-id="b7d50-122">For Cloud Connector Edition, follow instructions in the **Enable users for Phone System voice and voicemail services** section of the [Configure Skype for Business Cloud Connector Edition guide](https://technet.microsoft.com/library/mt605228.aspx).</span></span> <span data-ttu-id="b7d50-123">Para llamar a con Skype para Business Server de RTC, siga [Habilitar a los usuarios para Enterprise Voice en local](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises).</span><span class="sxs-lookup"><span data-stu-id="b7d50-123">For PSTN calling with Skype for Business Server, follow [Enable the users for Enterprise Voice on premises](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises).</span></span> <span data-ttu-id="b7d50-124">Para el enrutamiento directo de los equipos, siga la sección **Configurar el número de teléfono y habilitar enterprise voice y correo de voz** de [Configurar el enrutamiento directo](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail).</span><span class="sxs-lookup"><span data-stu-id="b7d50-124">For Teams Direct Routing, follow  the **Configure the phone number and enable enterprise voice and voicemail** section of [Configure Direct Routing](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail).</span></span>

4. <span data-ttu-id="b7d50-125">Compatibilidad con transcripción de correo de voz se ha agregado a partir de marzo de 2017 y está habilitada de forma predeterminada para todos los usuarios y las organizaciones.</span><span class="sxs-lookup"><span data-stu-id="b7d50-125">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users.</span></span> <span data-ttu-id="b7d50-126">Puede deshabilitar la transcripción para su organización utilizando Windows PowerShell y siguiendo los pasos que se indican a continuación.</span><span class="sxs-lookup"><span data-stu-id="b7d50-126">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

5. <span data-ttu-id="b7d50-127">Los mensajes de correo de voz se envían al buzón de Exchange de los usuarios a través de SMTP que se enrutan a través de Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="b7d50-127">Voicemail messages are delivered to users' Exchange mailbox via SMTP routed through Exchange Online Protection.</span></span> <span data-ttu-id="b7d50-128">Para habilitar la entrega de estos mensajes se realizó correctamente, asegúrese de que los conectores de Exchange se han configurado correctamente entre los servidores de Exchange y Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="b7d50-128">To enable successful delivery of these messages, please be sure that Exchange Connectors are configured correctly between your Exchange servers and Exchange Online Protection.</span></span> <span data-ttu-id="b7d50-129">[Usar conectores para configurar el flujo de correo](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span><span class="sxs-lookup"><span data-stu-id="b7d50-129">[Use Connectors to Configure Mail Flow](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span>

6. <span data-ttu-id="b7d50-130">Para habilitar las características de correo de voz como personalizar el saludo y correo de voz visual en Skype para clientes empresariales, se requiere conectividad de Office 365 para el buzón de correo de Exchange server a través de servicios Web de Exchange.</span><span class="sxs-lookup"><span data-stu-id="b7d50-130">To enable Voicemail features such as customizing greetings, and visual voicemail in Skype for Business clients, connectivity from Office 365 to the Exchange server mailbox via Exchange Web Services is required.</span></span> <span data-ttu-id="b7d50-131">Para habilitar esta conectividad debe configurar el nuevo Oauth de Exchange se describe el protocolo de autenticación de [OAuth de configurar la autenticación entre organizaciones de Exchange y Exchange Online](https://technet.microsoft.com/en-us/library/dn594521(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="b7d50-131">To enable this connectivity you must configure the new Exchange Oauth authentication protocol describe in [Configure OAuth authentication between Exchange and Exchange Online organizations](https://technet.microsoft.com/en-us/library/dn594521(v=exchg.150).aspx)</span></span> 

> [!NOTE]
> <span data-ttu-id="b7d50-132">El Asistente de Exchange híbrida ejecución desde Exchange 2013 CU5 o mayor controlará los requisitos en los pasos 5 y 6 automáticamente.</span><span class="sxs-lookup"><span data-stu-id="b7d50-132">The Exchange Hybrid Wizard run from Exchange 2013 CU5 or greater will handle the requirements in steps 5 and 6 automatically.</span></span> 

## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="b7d50-133">Configuración de directivas de correo de voz en su organización</span><span class="sxs-lookup"><span data-stu-id="b7d50-133">Setting voicemail policies in your organization</span></span>

> [!WARNING]
> <span data-ttu-id="b7d50-134">Deshabilitar el correo de voz a través de un Teams Microsoft directiva de llamada de Skype para los clientes empresariales, es posible que deshabilitar también el servicio de correo de voz para su Skype para usuarios profesionales.</span><span class="sxs-lookup"><span data-stu-id="b7d50-134">For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.</span></span>

<span data-ttu-id="b7d50-135">La transcripción de correo de voz está habilitada de forma predeterminada y el enmascaramiento de contenido ofensivo de transcripción está deshabilitado de forma predeterminada para todos los usuarios y organizaciones; sin embargo, puede controlarlos mediante los cmdlets [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) y [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx).</span><span class="sxs-lookup"><span data-stu-id="b7d50-135">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlets.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b7d50-136">No se puede crear una nueva instancia de directiva para transcripción y contenido ofensivo de transcripción de transparencias con el cmdlet **New-CsOnlineVoiceMailPolicy** y no se puede quitar una instancia de directiva existente con el cmdlet **Remove-CsOnlineVoiceMailPolicy** .</span><span class="sxs-lookup"><span data-stu-id="b7d50-136">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="b7d50-137">Puede administrar la configuración de la transcripción para sus usuarios con las directivas del correo de voz.</span><span class="sxs-lookup"><span data-stu-id="b7d50-137">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="b7d50-138">Para ver todas las instancias de la directiva de correo de voz disponibles, puede usar el cmdlet [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) .</span><span class="sxs-lookup"><span data-stu-id="b7d50-138">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>

 <span data-ttu-id="b7d50-139">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="b7d50-139">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>
  
![Get-CsOnlineVoiceMailPolicy results window.](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="b7d50-141">Desactivar la transcripción para su organización</span><span class="sxs-lookup"><span data-stu-id="b7d50-141">Turning off transcription for your organization</span></span>

<span data-ttu-id="b7d50-142">Debido a que el valor predeterminado de transcripción está activada para la organización, desea deshabilitar mediante el uso de [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span><span class="sxs-lookup"><span data-stu-id="b7d50-142">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="b7d50-143">Para ello, ejecute:</span><span class="sxs-lookup"><span data-stu-id="b7d50-143">To do this, run:</span></span>

```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="b7d50-144">Activar el enmascaramiento de contenido ofensivo de transcripción para su organización</span><span class="sxs-lookup"><span data-stu-id="b7d50-144">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="b7d50-145">El enmascaramiento de contenido ofensivo de transcripción está deshabilitado de forma predeterminada para su organización.</span><span class="sxs-lookup"><span data-stu-id="b7d50-145">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="b7d50-146">Si hay un requisito de negocio para habilitarlo, puede habilitar el enmascaramiento de contenido ofensivo de transcripción mediante [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span><span class="sxs-lookup"><span data-stu-id="b7d50-146">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="b7d50-147">Para ello, ejecute:</span><span class="sxs-lookup"><span data-stu-id="b7d50-147">To do this, run:</span></span>

```
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="b7d50-148">Desactivar la transcripción para un usuario</span><span class="sxs-lookup"><span data-stu-id="b7d50-148">Turning off transcription for a user</span></span>

<span data-ttu-id="b7d50-149">Las directivas de usuarios se evalúan antes que la configuración predeterminada de la organización.</span><span class="sxs-lookup"><span data-stu-id="b7d50-149">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="b7d50-150">Por ejemplo, si está habilitada la transcripción de correo de voz para todos los usuarios, puede asignar una directiva para deshabilitar transcripción para un usuario específico mediante el cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) .</span><span class="sxs-lookup"><span data-stu-id="b7d50-150">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="b7d50-151">Para deshabilitar la transcripción para un único usuario, ejecute:</span><span class="sxs-lookup"><span data-stu-id="b7d50-151">To disable transcription for a single user, run:</span></span>

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="b7d50-152">Activar el enmascaramiento de contenido ofensivo de transcripción para un usuario</span><span class="sxs-lookup"><span data-stu-id="b7d50-152">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="b7d50-153">Para habilitar el enmascaramiento de contenido ofensivo de transcripción para un usuario específico, puede asignar una directiva para habilitar el enmascaramiento de contenido ofensivo de transcripción para un usuario específico mediante el cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx).</span><span class="sxs-lookup"><span data-stu-id="b7d50-153">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="b7d50-154">Para habilitar el enmascaramiento de contenido ofensivo de transcripción para un solo usuario, ejecute:</span><span class="sxs-lookup"><span data-stu-id="b7d50-154">To enable transcription profanity masking for a single user, run:</span></span>

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="b7d50-p113">El servicio de correo de voz de Office 365 almacena en caché las directivas de correo de voz y actualiza la memoria caché cada 4 horas. Por lo tanto, los cambios de las directivas que realice pueden tardar hasta 4 horas en aplicarse.</span><span class="sxs-lookup"><span data-stu-id="b7d50-p113">The voicemail service in Office 365 caches voicemail policies and updates the cache every 4 hours. So, policy changes that you make can take up to 4 hours to be applied.</span></span>

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="b7d50-157">Ayudar a los usuarios a aprender acerca de las características del correo de voz de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="b7d50-157">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="b7d50-158">Disponemos de información de recursos de aprendizaje y artículos para ayudar a los usuarios a tener éxito con Skype para correo de voz empresarial.</span><span class="sxs-lookup"><span data-stu-id="b7d50-158">We have training information and articles to help your users be successful with Skype for Business voicemail.</span></span> <span data-ttu-id="b7d50-159">Pídales que consulten los siguientes artículos:</span><span class="sxs-lookup"><span data-stu-id="b7d50-159">Point them to the following articles:</span></span>

- <span data-ttu-id="b7d50-160">[Comprobación de Skype para opciones y correo de voz empresarial](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): en este artículo se explica cómo escuchar el correo de voz de Skype para la empresa, cambiar el saludo del correo de voz, cambiar la configuración del correo de voz y escuchar el correo de voz a diferentes velocidades.</span><span class="sxs-lookup"><span data-stu-id="b7d50-160">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="b7d50-161">Aprendizaje de Skype Empresarial 2016</span><span class="sxs-lookup"><span data-stu-id="b7d50-161">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="b7d50-162">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="b7d50-162">Related topics</span></span>
[<span data-ttu-id="b7d50-163">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="b7d50-163">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="b7d50-164">Esto es lo obtiene con el Sistema telefónico de Office 365</span><span class="sxs-lookup"><span data-stu-id="b7d50-164">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="b7d50-165">Planificar la migración de Skype Empresarial Server y Exchange Server</span><span class="sxs-lookup"><span data-stu-id="b7d50-165">Plan for Skype for Business Server and Exchange Server migration</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/plan-um-migration)


