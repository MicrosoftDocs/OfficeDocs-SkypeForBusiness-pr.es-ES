---
title: Planear el Correo de voz en la nube
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: wasseemh, phans
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 'Obtenga información sobre cómo configurar el buzón de voz en la nube para sus usuarios. '
ms.openlocfilehash: 62729794ff1e23ce29b3e3aad86fa09b63a428e5
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691056"
---
# <a name="set-up-cloud-voicemail"></a><span data-ttu-id="1ead6-103">Planear el Correo de voz en la nube</span><span class="sxs-lookup"><span data-stu-id="1ead6-103">Set up Cloud Voicemail</span></span>

<span data-ttu-id="1ead6-104">Este artículo es para el administrador de Microsoft 365 u Office 365 según se describe en acerca de los [roles de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) que quieren configurar la característica de buzón de voz de la nube para todos los usuarios de la empresa.</span><span class="sxs-lookup"><span data-stu-id="1ead6-104">This article is for the Microsoft 365 or Office 365 admin as described in [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) who wants to set up the Cloud Voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="1ead6-105">El buzón de voz de nube admite el depósito de mensajes de voz solo en un buzón de Exchange y no es compatible con ningún sistema de correo de terceros.</span><span class="sxs-lookup"><span data-stu-id="1ead6-105">Cloud Voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> 

> [!NOTE]
> <span data-ttu-id="1ead6-106">Cuando un delegado responde a una llamada en nombre de un delegador, las notificaciones no están disponibles en el buzón de voz de la nube.</span><span class="sxs-lookup"><span data-stu-id="1ead6-106">When a delegate answers a call on behalf of a delegator, notifications are not available in Cloud Voicemail.</span></span> <span data-ttu-id="1ead6-107">Los usuarios pueden recibir notificaciones de llamadas perdidas.</span><span class="sxs-lookup"><span data-stu-id="1ead6-107">Users can receive notifications for missed calls.</span></span>

## <a name="cloud-only-environments-set-up-cloud-voicemail-for-online-phone-system-users"></a><span data-ttu-id="1ead6-108">Entornos solo de nube: configurar el buzón de voz en la nube para usuarios de sistemas telefónicos en línea</span><span class="sxs-lookup"><span data-stu-id="1ead6-108">Cloud-only environments: Set up Cloud Voicemail for Online Phone System users</span></span>

<span data-ttu-id="1ead6-109">Para los usuarios de sistemas telefónicos en línea, el buzón de voz se configura y se aprovisiona automáticamente para los usuarios después de asignar una licencia de **sistema telefónico** a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="1ead6-109">For Online Phone System users, Cloud Voicemail is automatically set up and provisioned for users after you assign a **Phone System** license to the users.</span></span> 

> [!NOTE]
> <span data-ttu-id="1ead6-110">Para los usuarios del sistema telefónico de Skype empresarial en línea con números de teléfono proporcionados localmente, es posible que necesite habilitar el correo de voz hospedado con [set-CsUser-HostedVoicemail $true](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="1ead6-110">For Online Skype for Business Phone System users with on-premises provided phone numbers, you may need to enable hosted voice mail with [Set-CsUser -HostedVoicemail $True](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps).</span></span> 

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a><span data-ttu-id="1ead6-111">Configurar el buzón de voz en la nube para usuarios de buzones de Exchange Server</span><span class="sxs-lookup"><span data-stu-id="1ead6-111">Set up Cloud Voicemail for Exchange Server Mailbox Users</span></span>

<span data-ttu-id="1ead6-112">La siguiente información está relacionada con la configuración del buzón de voz de la nube para trabajar con usuarios que están conectados para el sistema telefónico pero que tienen su buzón en Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="1ead6-112">The following information is about configuring Cloud Voicemail to work with users who are online for Phone System but have their mailbox on Exchange Server.</span></span> 
  
1. <span data-ttu-id="1ead6-113">Los mensajes de voz se entregan al buzón de Exchange de los usuarios mediante SMTP enrutado a través de Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="1ead6-113">Voicemail messages are delivered to users' Exchange mailbox via SMTP routed through Exchange Online Protection.</span></span> <span data-ttu-id="1ead6-114">Para habilitar la entrega correcta de estos mensajes, asegúrese de que los conectores de Exchange están configurados correctamente entre los servidores de Exchange y Exchange Online Protection; [Use conectores para configurar el flujo de correo](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span><span class="sxs-lookup"><span data-stu-id="1ead6-114">To enable successful delivery of these messages, please be sure that Exchange Connectors are configured correctly between your Exchange servers and Exchange Online Protection; [Use Connectors to Configure Mail Flow](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span> 

2. <span data-ttu-id="1ead6-115">Para habilitar características de buzón de voz, como la personalización de saludos y el buzón de voz en clientes de Skype empresarial, se requiere conectividad de Microsoft 365 u Office 365 al buzón de Exchange Server a través de los servicios Web de Exchange.</span><span class="sxs-lookup"><span data-stu-id="1ead6-115">To enable Voicemail features such as customizing greetings and visual voicemail in Skype for Business clients, connectivity from Microsoft 365 or Office 365 to the Exchange server mailbox via Exchange Web Services is required.</span></span> <span data-ttu-id="1ead6-116">Para habilitar esta conectividad, debe configurar el nuevo protocolo de autenticación de OAuth de Exchange que se describe en [configurar la autenticación OAuth entre Exchange y las organizaciones de Exchange Online](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx), o ejecutar el Asistente para la implementación híbrida de Exchange 2013 CU5 o superior.</span><span class="sxs-lookup"><span data-stu-id="1ead6-116">To enable this connectivity, you must configure the new Exchange Oauth authentication protocol described in [Configure OAuth authentication between Exchange and Exchange Online organizations](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx), or run the Exchange Hybrid Wizard from Exchange 2013 CU5 or greater.</span></span> <span data-ttu-id="1ead6-117">Además, debe configurar la integración y OAuth entre Skype empresarial online y Exchange Server que se describen en [configurar la integración y OAuth entre Skype empresarial online y Exchange Server](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).</span><span class="sxs-lookup"><span data-stu-id="1ead6-117">Additionally, you must configure integration and Oauth between Skype for Business Online and Exchange server described in [Configure Integration and OAuth between Skype for Business Online and Exchange Server](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).</span></span> 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a><span data-ttu-id="1ead6-118">Configurar el buzón de voz en la nube para usuarios de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="1ead6-118">Set up Cloud Voicemail for Skype for Business Server Users</span></span>

<span data-ttu-id="1ead6-119">Para configurar los usuarios de Skype empresarial Server para el buzón de voz en la nube, consulte [planear el servicio de buzón de voz en la nube para usuarios locales](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-cloud-voicemail).</span><span class="sxs-lookup"><span data-stu-id="1ead6-119">To configure Skype for Business server users for Cloud Voicemail, please see [Plan Cloud Voicemail service for on-premises users](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-cloud-voicemail).</span></span>

## <a name="enabling-protected-voicemail-in-your-organization"></a><span data-ttu-id="1ead6-120">Habilitar el buzón de voz protegido en su organización</span><span class="sxs-lookup"><span data-stu-id="1ead6-120">Enabling protected voicemail in your organization</span></span>

<span data-ttu-id="1ead6-121">Cuando alguien deja un mensaje de voz para un usuario de su organización, el buzón de voz se envía al buzón del usuario como datos adjuntos de un mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="1ead6-121">When someone leaves a voicemail message for a user in your organization, the voicemail is delivered to the user's mailbox as an email message attachment.</span></span> <span data-ttu-id="1ead6-122">Con las reglas de flujo de correo para aplicar el cifrado de mensajes, puede evitar que estos mensajes de voz se desvíen a otros destinatarios.</span><span class="sxs-lookup"><span data-stu-id="1ead6-122">Using mail flow rules to apply message encryption, you can prevent those voicemail messages from being forwarded to other recipients.</span></span> <span data-ttu-id="1ead6-123">Al habilitar el buzón de voz protegido, los usuarios pueden escuchar mensajes de voz protegidos llamando a su buzón de voz o abriendo el mensaje en Outlook, en Outlook en la web o en Outlook para Android o iOS.</span><span class="sxs-lookup"><span data-stu-id="1ead6-123">When you enable protected voicemail, users can listen to protected voicemail messages by calling into their voicemail mailbox or by opening the message in Outlook, Outlook on the web, or in Outlook for Android or iOS.</span></span> <span data-ttu-id="1ead6-124">Los mensajes de buzón de voz protegidos no se pueden abrir en Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="1ead6-124">Protected voicemail messages can't be opened in Skype for Business.</span></span>

<span data-ttu-id="1ead6-125">Para obtener más información sobre el cifrado de mensajes, consulte [cifrado de correo electrónico](https://docs.microsoft.com/microsoft-365/compliance/email-encryption?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="1ead6-125">For more information about message encryption, see [Email encryption](https://docs.microsoft.com/microsoft-365/compliance/email-encryption?view=o365-worldwide).</span></span>

<span data-ttu-id="1ead6-126">Para configurar el buzón de voz protegido, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1ead6-126">To set up protected voicemail, do the following:</span></span>

1. <span data-ttu-id="1ead6-127">Vaya a https://admin.microsoft.com e inicie sesión con una cuenta que tenga permisos de administrador global.</span><span class="sxs-lookup"><span data-stu-id="1ead6-127">Go to https://admin.microsoft.com and sign in using an account with global administrator permissions.</span></span>
2. <span data-ttu-id="1ead6-128">Seleccione **Mostrar todo** y, a continuación, vaya a **centro de administración**de  >  **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="1ead6-128">Select **Show all** and then go to **Admin centers** > **Exchange**.</span></span>
3. <span data-ttu-id="1ead6-129">En el centro de administración de Exchange, seleccione reglas de **flujo de correo**  >  **Rules**.</span><span class="sxs-lookup"><span data-stu-id="1ead6-129">In the Exchange Admin Center, select **Mail flow** > **Rules**.</span></span>
4. <span data-ttu-id="1ead6-130">Seleccione **+** **Agregar**y, a continuación, seleccione **aplicar el cifrado de mensajes de Office 365 y la protección de derechos a los mensajes**.</span><span class="sxs-lookup"><span data-stu-id="1ead6-130">Select **+** **Add**, and then select **Apply Office 365 Message Encryption and rights protection to messages**.</span></span>
5. <span data-ttu-id="1ead6-131">Escriba un nombre para la nueva regla de flujo de correo y, a continuación, en **aplicar esta regla si**, seleccione **el mensaje las propiedades**  >  **incluyen el**  >  **correo de voz**.</span><span class="sxs-lookup"><span data-stu-id="1ead6-131">Provide a name for the new mail flow rule and then under **Apply this rule if**, select **The message properties** > **Include the message type** > **Voice mail**.</span></span> <span data-ttu-id="1ead6-132">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1ead6-132">Select **OK**.</span></span>
6. <span data-ttu-id="1ead6-133">En **hacer lo siguiente**, seleccione **aplicar el cifrado de mensajes de Office 365 y la protección de derechos al mensaje con** y, después, seleccione **seleccionar uno**.</span><span class="sxs-lookup"><span data-stu-id="1ead6-133">Under **Do the following**, select **Apply Office 365 Message Encryption and rights protection to the message with** and then select **Select one**.</span></span> <span data-ttu-id="1ead6-134">En **plantilla RMS**, seleccione no **reenviar**.</span><span class="sxs-lookup"><span data-stu-id="1ead6-134">Under **RMS template**, select **Do not forward**.</span></span> <span data-ttu-id="1ead6-135">Seleccione **Aceptar** y, a continuación, **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="1ead6-135">Select **OK** and then **Save**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="1ead6-136">Si la lista de **plantillas de RMS** está vacía, debe configurar el cifrado de mensajes.</span><span class="sxs-lookup"><span data-stu-id="1ead6-136">If the **RMS template** list is empty, you need to set up Message Encryption.</span></span> <span data-ttu-id="1ead6-137">Para obtener más información sobre cómo configurar el cifrado de mensajes, vea los artículos siguientes:</span><span class="sxs-lookup"><span data-stu-id="1ead6-137">For more information about setting up Message Encryption, see the following articles:</span></span>
    > - [<span data-ttu-id="1ead6-138">Configurar nuevas capacidades de cifrado de mensajes</span><span class="sxs-lookup"><span data-stu-id="1ead6-138">Set up new Message Encryption capabilities</span></span>](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)
    > - [<span data-ttu-id="1ead6-139">Configuración y administración de plantillas para Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="1ead6-139">Configuring and managing templates for Azure Information Protection</span></span>](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)
    > - [<span data-ttu-id="1ead6-140">Opción no reenviar para correos electrónicos</span><span class="sxs-lookup"><span data-stu-id="1ead6-140">Do Not Forward option for emails</span></span>](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)

## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="1ead6-141">Configuración de directivas de correo de voz en su organización</span><span class="sxs-lookup"><span data-stu-id="1ead6-141">Setting voicemail policies in your organization</span></span>

> [!WARNING]
> <span data-ttu-id="1ead6-142">Para los clientes de Skype empresarial, deshabilitar el buzón de voz a través de una directiva de llamadas de Microsoft Teams también puede deshabilitar el servicio de buzón de voz para los usuarios de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="1ead6-142">For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.</span></span>

<span data-ttu-id="1ead6-143">La transcripción de correo de voz está habilitada de forma predeterminada y el enmascaramiento de contenido ofensivo de transcripción está deshabilitado de forma predeterminada para todos los usuarios y organizaciones; sin embargo, puede controlarlos mediante los cmdlets [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) y [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx).</span><span class="sxs-lookup"><span data-stu-id="1ead6-143">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlets.</span></span>

<span data-ttu-id="1ead6-144">Los mensajes de voz recibidos por los usuarios de su organización se transforman en la región donde está hospedada su organización de Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="1ead6-144">Voicemail messages received by users in your organization are transcribed in the region where your Microsoft 365 or Office 365 organization is hosted.</span></span> <span data-ttu-id="1ead6-145">Es posible que la región en la que se hospeda el inquilino no sea la misma región en la que se encuentra el usuario que recibe el mensaje de voz.</span><span class="sxs-lookup"><span data-stu-id="1ead6-145">The region where your tenant is hosted might not be the same region where the user receiving the voicemail message is located.</span></span> <span data-ttu-id="1ead6-146">Para ver la región donde se hospeda el inquilino, vaya a la página del perfil de la [organización](https://go.microsoft.com/fwlink/p/?linkid=2067339) y haga clic en **Ver detalles** junto a **Ubicación de datos**.</span><span class="sxs-lookup"><span data-stu-id="1ead6-146">To view the region where your tenant is hosted, go to the [Organization profile](https://go.microsoft.com/fwlink/p/?linkid=2067339) page and then click **View details** next to **Data location**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1ead6-147">No puede crear una nueva instancia de directiva para transcripción y máscaras de blasfemias por transcripción con el cmdlet **New-CsOnlineVoiceMailPolicy** y no puede quitar una instancia de directiva existente mediante el cmdlet **Remove-CsOnlineVoiceMailPolicy** .</span><span class="sxs-lookup"><span data-stu-id="1ead6-147">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="1ead6-148">Puede administrar la configuración de la transcripción para sus usuarios con las directivas del correo de voz.</span><span class="sxs-lookup"><span data-stu-id="1ead6-148">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="1ead6-149">Para ver todas las instancias disponibles de la Directiva del buzón de voz, puede usar el cmdlet [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) .</span><span class="sxs-lookup"><span data-stu-id="1ead6-149">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>

 <span data-ttu-id="1ead6-150">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="1ead6-150">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>
  
![Get-CsOnlineVoiceMailPolicy results window.](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="1ead6-152">Desactivar la transcripción para su organización</span><span class="sxs-lookup"><span data-stu-id="1ead6-152">Turning off transcription for your organization</span></span>

<span data-ttu-id="1ead6-153">Dado que la configuración predeterminada de transcripción está activada para su organización, es posible que desee deshabilitarla mediante [set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span><span class="sxs-lookup"><span data-stu-id="1ead6-153">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="1ead6-154">Para ello, ejecute:</span><span class="sxs-lookup"><span data-stu-id="1ead6-154">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="1ead6-155">Activar el enmascaramiento de contenido ofensivo de transcripción para su organización</span><span class="sxs-lookup"><span data-stu-id="1ead6-155">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="1ead6-156">El enmascaramiento de contenido ofensivo de transcripción está deshabilitado de forma predeterminada para su organización.</span><span class="sxs-lookup"><span data-stu-id="1ead6-156">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="1ead6-157">Si hay un requisito de negocio para habilitarlo, puede habilitar el enmascaramiento de contenido ofensivo de transcripción mediante [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span><span class="sxs-lookup"><span data-stu-id="1ead6-157">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="1ead6-158">Para ello, ejecute:</span><span class="sxs-lookup"><span data-stu-id="1ead6-158">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="1ead6-159">Desactivar la transcripción para un usuario</span><span class="sxs-lookup"><span data-stu-id="1ead6-159">Turning off transcription for a user</span></span>

<span data-ttu-id="1ead6-160">Las directivas de usuarios se evalúan antes que la configuración predeterminada de la organización.</span><span class="sxs-lookup"><span data-stu-id="1ead6-160">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="1ead6-161">Por ejemplo, si la transcripción del buzón de voz está habilitada para todos los usuarios, puede asignar una directiva para deshabilitar la transcripción para un usuario específico mediante el cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) .</span><span class="sxs-lookup"><span data-stu-id="1ead6-161">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="1ead6-162">Para deshabilitar la transcripción para un único usuario, ejecute:</span><span class="sxs-lookup"><span data-stu-id="1ead6-162">To disable transcription for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="1ead6-163">Activar el enmascaramiento de contenido ofensivo de transcripción para un usuario</span><span class="sxs-lookup"><span data-stu-id="1ead6-163">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="1ead6-164">Para habilitar el enmascaramiento de contenido ofensivo de transcripción para un usuario específico, puede asignar una directiva para habilitar el enmascaramiento de contenido ofensivo de transcripción para un usuario específico mediante el cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx).</span><span class="sxs-lookup"><span data-stu-id="1ead6-164">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="1ead6-165">Para habilitar el enmascaramiento de contenido ofensivo de transcripción para un solo usuario, ejecute:</span><span class="sxs-lookup"><span data-stu-id="1ead6-165">To enable transcription profanity masking for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="1ead6-166">El servicio de buzón de voz de Microsoft 365 y Office 365 almacena en caché las directivas de buzón de voz y actualiza la caché cada 4 horas.</span><span class="sxs-lookup"><span data-stu-id="1ead6-166">The voicemail service in Microsoft 365 and Office 365 caches voicemail policies and updates the cache every 4 hours.</span></span> <span data-ttu-id="1ead6-167">Por lo tanto, los cambios de las directivas que realice pueden tardar hasta 4 horas en aplicarse.</span><span class="sxs-lookup"><span data-stu-id="1ead6-167">So, policy changes that you make can take up to 4 hours to be applied.</span></span>

## <a name="help-your-users-learn-teams-voicemail-features"></a><span data-ttu-id="1ead6-168">Ayudar a los usuarios a aprender las características del buzón de voz</span><span class="sxs-lookup"><span data-stu-id="1ead6-168">Help your users learn Teams voicemail features</span></span>

<span data-ttu-id="1ead6-169">Tenemos la siguiente información para los usuarios sobre la administración de la configuración del buzón de voz, así como otras características de llamadas en Teams:</span><span class="sxs-lookup"><span data-stu-id="1ead6-169">We have the following information for your users on managing their voicemail settings as well as other calling features in Teams:</span></span>

- <span data-ttu-id="1ead6-170">[Administre la configuración de llamadas en Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).</span><span class="sxs-lookup"><span data-stu-id="1ead6-170">[Manage your call settings in Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).</span></span> <span data-ttu-id="1ead6-171">En este artículo se explica cómo administrar todas las características de las llamadas de los equipos de los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="1ead6-171">This article explains how to manage all end-user Teams calling features.</span></span> 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="1ead6-172">Ayudar a los usuarios a aprender acerca de las características del correo de voz de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="1ead6-172">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="1ead6-173">Tenemos información de aprendizaje y artículos que ayudan a los usuarios a tener éxito con el buzón de voz de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="1ead6-173">We have training information and articles to help your users be successful with Skype for Business voicemail.</span></span> <span data-ttu-id="1ead6-174">Pídales que consulten los siguientes artículos:</span><span class="sxs-lookup"><span data-stu-id="1ead6-174">Point them to the following articles:</span></span>

- <span data-ttu-id="1ead6-175">[Consulta el buzón de voz y las opciones de Skype empresarial](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): en este artículo se explica cómo escuchar el buzón de voz en Skype empresarial, cambiar el saludo del correo de voz, cambiar la configuración del buzón de voz y escuchar el buzón de voz a velocidades diferentes.</span><span class="sxs-lookup"><span data-stu-id="1ead6-175">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="1ead6-176">Aprendizaje de Skype Empresarial 2016</span><span class="sxs-lookup"><span data-stu-id="1ead6-176">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="1ead6-177">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="1ead6-177">Related topics</span></span>
[<span data-ttu-id="1ead6-178">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="1ead6-178">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="1ead6-179">Esto es lo obtiene con el Sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="1ead6-179">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="1ead6-180">Planificar la migración de Skype Empresarial Server y Exchange Server</span><span class="sxs-lookup"><span data-stu-id="1ead6-180">Plan for Skype for Business Server and Exchange Server migration</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-um-migration)
