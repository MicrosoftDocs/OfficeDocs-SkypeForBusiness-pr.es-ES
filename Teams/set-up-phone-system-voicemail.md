---
title: Configurar el Correo de voz en la nube
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
description: 'Obtenga información sobre cómo configurar Correo de voz en la nube para los usuarios. '
ms.openlocfilehash: c6fbd02e30c5be0280b05088a1cec281c2534039
ms.sourcegitcommit: 31c5b9cd3d4f500e1f9d7823052dae8f8c298b1e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2021
ms.locfileid: "52901917"
---
# <a name="set-up-cloud-voicemail"></a><span data-ttu-id="b5942-103">Configurar el Correo de voz en la nube</span><span class="sxs-lookup"><span data-stu-id="b5942-103">Set up Cloud Voicemail</span></span>

<span data-ttu-id="b5942-104">Este artículo es para el administrador Microsoft 365 o Office 365 como se describe en Acerca de los [roles](/microsoft-365/admin/add-users/about-admin-roles) de administrador que desea configurar la característica Correo de voz en la nube para todos los usuarios de la empresa.</span><span class="sxs-lookup"><span data-stu-id="b5942-104">This article is for the Microsoft 365 or Office 365 admin as described in [About admin roles](/microsoft-365/admin/add-users/about-admin-roles) who wants to set up the Cloud Voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="b5942-105">Correo de voz en la nube permite depositar mensajes de correo de voz solo en un buzón de correo Exchange y no es compatible con ningún sistema de correo electrónico de terceros.</span><span class="sxs-lookup"><span data-stu-id="b5942-105">Cloud Voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> 

> [!NOTE]
> <span data-ttu-id="b5942-106">Cuando un delegado responde a una llamada en nombre de un delegado, las notificaciones no están disponibles en Correo de voz en la nube.</span><span class="sxs-lookup"><span data-stu-id="b5942-106">When a delegate answers a call on behalf of a delegator, notifications are not available in Cloud Voicemail.</span></span> <span data-ttu-id="b5942-107">Los usuarios pueden recibir notificaciones de llamadas perdidas.</span><span class="sxs-lookup"><span data-stu-id="b5942-107">Users can receive notifications for missed calls.</span></span>

## <a name="cloud-only-environments-set-up-cloud-voicemail-for-online-phone-system-users"></a><span data-ttu-id="b5942-108">Entornos solo en la nube: Configurar Correo de voz en la nube para usuarios Sistema telefónico en línea</span><span class="sxs-lookup"><span data-stu-id="b5942-108">Cloud-only environments: Set up Cloud Voicemail for Online Phone System users</span></span>

<span data-ttu-id="b5942-109">Para los usuarios Sistema telefónico online, Correo de voz en la nube se configura y aprovisiona automáticamente para los usuarios después de asignar una **Sistema telefónico** a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="b5942-109">For Online Phone System users, Cloud Voicemail is automatically set up and provisioned for users after you assign a **Phone System** license to the users.</span></span> 

> [!NOTE]
> <span data-ttu-id="b5942-110">Para usuarios Skype Empresarial Sistema telefónico en línea con números de teléfono proporcionados localmente, es posible que tenga que habilitar el correo de voz hospedado con [Set-CsUser -HostedVoicemail $True](/powershell/module/skype/set-csuser?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="b5942-110">For Online Skype for Business Phone System users with on-premises provided phone numbers, you may need to enable hosted voice mail with [Set-CsUser -HostedVoicemail $True](/powershell/module/skype/set-csuser?view=skype-ps).</span></span> 

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a><span data-ttu-id="b5942-111">Configurar Correo de voz en la nube usuarios Exchange Server buzón de correo</span><span class="sxs-lookup"><span data-stu-id="b5942-111">Set up Cloud Voicemail for Exchange Server Mailbox Users</span></span>

<span data-ttu-id="b5942-112">La siguiente información es sobre cómo configurar Correo de voz en la nube para trabajar con usuarios que están en línea para Sistema telefónico pero tienen su buzón en Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="b5942-112">The following information is about configuring Cloud Voicemail to work with users who are online for Phone System but have their mailbox on Exchange Server.</span></span> 
  
1. <span data-ttu-id="b5942-113">Los mensajes de correo de voz se entregan a los buzones Exchange los usuarios a través de SMTP enrutados a través de Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="b5942-113">Voicemail messages are delivered to users' Exchange mailbox via SMTP routed through Exchange Online Protection.</span></span> <span data-ttu-id="b5942-114">Para habilitar la entrega correcta de estos mensajes, asegúrese de que los conectores Exchange están configurados correctamente entre los servidores Exchange y Exchange Online Protection; [Usar conectores para configurar el correo Flow](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span><span class="sxs-lookup"><span data-stu-id="b5942-114">To enable successful delivery of these messages, please be sure that Exchange Connectors are configured correctly between your Exchange servers and Exchange Online Protection; [Use Connectors to Configure Mail Flow](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span> 

2. <span data-ttu-id="b5942-115">Para habilitar características de correo de voz como personalizar saludos y correo de voz visual en clientes Skype Empresarial, se requiere conectividad de Microsoft 365 o Office 365 al buzón de servidor de Exchange a través de Exchange Servicios web.</span><span class="sxs-lookup"><span data-stu-id="b5942-115">To enable Voicemail features such as customizing greetings and visual voicemail in Skype for Business clients, connectivity from Microsoft 365 or Office 365 to the Exchange server mailbox via Exchange Web Services is required.</span></span> <span data-ttu-id="b5942-116">Para habilitar esta conectividad, debe configurar el nuevo protocolo de autenticación de Oauth de Exchange descrito en Configurar autenticación [de OAuth](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)entre organizaciones de Exchange y Exchange Online, o ejecutar el Asistente híbrido de Exchange desde Exchange 2013 CU5 o posterior.</span><span class="sxs-lookup"><span data-stu-id="b5942-116">To enable this connectivity, you must configure the new Exchange Oauth authentication protocol described in [Configure OAuth authentication between Exchange and Exchange Online organizations](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help), or run the Exchange Hybrid Wizard from Exchange 2013 CU5 or greater.</span></span> <span data-ttu-id="b5942-117">Además, debe configurar la integración y Oauth entre Skype Empresarial Online y un servidor Exchange descrito en Configurar integración y [OAuth](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)entre Skype Empresarial Online y Exchange Server .</span><span class="sxs-lookup"><span data-stu-id="b5942-117">Additionally, you must configure integration and Oauth between Skype for Business Online and Exchange server described in [Configure Integration and OAuth between Skype for Business Online and Exchange Server](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).</span></span> 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a><span data-ttu-id="b5942-118">Configurar Correo de voz en la nube usuarios Skype Empresarial Server usuarios</span><span class="sxs-lookup"><span data-stu-id="b5942-118">Set up Cloud Voicemail for Skype for Business Server Users</span></span>

<span data-ttu-id="b5942-119">Para configurar Skype Empresarial de servidor para Correo de voz en la nube, consulte Planear Correo de voz en la nube para usuarios [locales.](/skypeforbusiness/hybrid/plan-cloud-voicemail)</span><span class="sxs-lookup"><span data-stu-id="b5942-119">To configure Skype for Business server users for Cloud Voicemail, please see [Plan Cloud Voicemail service for on-premises users](/skypeforbusiness/hybrid/plan-cloud-voicemail).</span></span>

## <a name="enabling-protected-voicemail-in-your-organization"></a><span data-ttu-id="b5942-120">Habilitar el correo de voz protegido en su organización</span><span class="sxs-lookup"><span data-stu-id="b5942-120">Enabling protected voicemail in your organization</span></span>

<span data-ttu-id="b5942-121">Cuando alguien deja un mensaje de correo de voz para un usuario de su organización, el correo de voz se entrega al buzón del usuario como datos adjuntos de un mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="b5942-121">When someone leaves a voicemail message for a user in your organization, the voicemail is delivered to the user's mailbox as an email message attachment.</span></span> <span data-ttu-id="b5942-122">Si usa reglas de flujo de correo para aplicar el cifrado de mensajes, puede evitar que esos mensajes de correo de voz se reenván a otros destinatarios.</span><span class="sxs-lookup"><span data-stu-id="b5942-122">Using mail flow rules to apply message encryption, you can prevent those voicemail messages from being forwarded to other recipients.</span></span> <span data-ttu-id="b5942-123">Al habilitar el correo de voz protegido, los usuarios pueden escuchar mensajes de correo de voz protegidos llamando a su buzón de voz o abriendo el mensaje en Outlook, Outlook en la web o en Outlook para Android o iOS.</span><span class="sxs-lookup"><span data-stu-id="b5942-123">When you enable protected voicemail, users can listen to protected voicemail messages by calling into their voicemail mailbox or by opening the message in Outlook, Outlook on the web, or in Outlook for Android or iOS.</span></span> <span data-ttu-id="b5942-124">Los mensajes de correo de voz protegidos no se pueden abrir en Skype Empresarial o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b5942-124">Protected voicemail messages can't be opened in Skype for Business or Microsoft Teams.</span></span>

<span data-ttu-id="b5942-125">Para obtener más información sobre el cifrado de mensajes, vea [Cifrado de correo electrónico.](/microsoft-365/compliance/email-encryption?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="b5942-125">For more information about message encryption, see [Email encryption](/microsoft-365/compliance/email-encryption?view=o365-worldwide).</span></span>

<span data-ttu-id="b5942-126">Para configurar el correo de voz protegido, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b5942-126">To set up protected voicemail, do the following:</span></span>

1. <span data-ttu-id="b5942-127">Vaya a https://admin.microsoft.com e inicie sesión con una cuenta con permisos de administrador global.</span><span class="sxs-lookup"><span data-stu-id="b5942-127">Go to https://admin.microsoft.com and sign in using an account with global administrator permissions.</span></span>
2. <span data-ttu-id="b5942-128">Seleccione **Mostrar todo y,** a continuación, vaya a Centros **de**  >  **administración Exchange**.</span><span class="sxs-lookup"><span data-stu-id="b5942-128">Select **Show all** and then go to **Admin centers** > **Exchange**.</span></span>
3. <span data-ttu-id="b5942-129">En el Centro Exchange administración, seleccione **Reglas de flujo de**  >  **correo.**</span><span class="sxs-lookup"><span data-stu-id="b5942-129">In the Exchange Admin Center, select **Mail flow** > **Rules**.</span></span>
4. <span data-ttu-id="b5942-130">Seleccione **+** **Agregar** y, a continuación, seleccione **Aplicar Cifrado de mensajes de Office 365 protección de derechos y derechos a los mensajes.**</span><span class="sxs-lookup"><span data-stu-id="b5942-130">Select **+** **Add**, and then select **Apply Office 365 Message Encryption and rights protection to messages**.</span></span>
5. <span data-ttu-id="b5942-131">Proporcione un nombre para la nueva regla de flujo de correo y, a continuación, en Aplicar **esta** regla si , seleccione Las propiedades del mensaje Incluya el tipo  >  **de mensaje Correo** de  >  **voz.**</span><span class="sxs-lookup"><span data-stu-id="b5942-131">Provide a name for the new mail flow rule and then under **Apply this rule if**, select **The message properties** > **Include the message type** > **Voice mail**.</span></span> <span data-ttu-id="b5942-132">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b5942-132">Select **OK**.</span></span>
6. <span data-ttu-id="b5942-133">En **Hacer lo siguiente,** seleccione **Aplicar Cifrado de mensajes de Office 365 protección** de derechos y derechos al mensaje con y, a continuación, seleccione **Seleccionar uno**.</span><span class="sxs-lookup"><span data-stu-id="b5942-133">Under **Do the following**, select **Apply Office 365 Message Encryption and rights protection to the message with** and then select **Select one**.</span></span> <span data-ttu-id="b5942-134">En **Plantilla RMS,** seleccione **No reenviar**.</span><span class="sxs-lookup"><span data-stu-id="b5942-134">Under **RMS template**, select **Do not forward**.</span></span> <span data-ttu-id="b5942-135">Seleccione **Aceptar** y, a **continuación, Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b5942-135">Select **OK** and then **Save**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="b5942-136">Si la **lista de plantillas rms** está vacía, debe configurar el cifrado de mensajes.</span><span class="sxs-lookup"><span data-stu-id="b5942-136">If the **RMS template** list is empty, you need to set up Message Encryption.</span></span> <span data-ttu-id="b5942-137">Para obtener más información sobre cómo configurar el cifrado de mensajes, vea los siguientes artículos:</span><span class="sxs-lookup"><span data-stu-id="b5942-137">For more information about setting up Message Encryption, see the following articles:</span></span>
    > - [<span data-ttu-id="b5942-138">Configurar nuevas funcionalidades de cifrado de mensajes</span><span class="sxs-lookup"><span data-stu-id="b5942-138">Set up new Message Encryption capabilities</span></span>](/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)
    > - [<span data-ttu-id="b5942-139">Configurar y administrar plantillas para Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="b5942-139">Configuring and managing templates for Azure Information Protection</span></span>](/information-protection/deploy-use/configure-policy-templates)
    > - [<span data-ttu-id="b5942-140">Opción No reenviar para correos electrónicos</span><span class="sxs-lookup"><span data-stu-id="b5942-140">Do Not Forward option for emails</span></span>](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)

## <a name="help-your-users-learn-teams-voicemail-features"></a><span data-ttu-id="b5942-141">Ayudar a los usuarios a aprender Teams de correo de voz</span><span class="sxs-lookup"><span data-stu-id="b5942-141">Help your users learn Teams voicemail features</span></span>

<span data-ttu-id="b5942-142">Tenemos la siguiente información para los usuarios sobre cómo administrar la configuración del correo de voz, así como otras características de llamadas en Teams:</span><span class="sxs-lookup"><span data-stu-id="b5942-142">We have the following information for your users on managing their voicemail settings as well as other calling features in Teams:</span></span>

- <span data-ttu-id="b5942-143">[Administre la configuración de la llamada en Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).</span><span class="sxs-lookup"><span data-stu-id="b5942-143">[Manage your call settings in Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).</span></span> <span data-ttu-id="b5942-144">En este artículo se explica cómo administrar todas las características de llamadas de Teams usuario final.</span><span class="sxs-lookup"><span data-stu-id="b5942-144">This article explains how to manage all end-user Teams calling features.</span></span> 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="b5942-145">Ayudar a los usuarios a aprender acerca de las características del correo de voz de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="b5942-145">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="b5942-146">Tenemos información de aprendizaje y artículos para ayudar a los usuarios a tener éxito con Skype Empresarial correo de voz.</span><span class="sxs-lookup"><span data-stu-id="b5942-146">We have training information and articles to help your users be successful with Skype for Business voicemail.</span></span> <span data-ttu-id="b5942-147">Pídales que consulten los siguientes artículos:</span><span class="sxs-lookup"><span data-stu-id="b5942-147">Point them to the following articles:</span></span>

- <span data-ttu-id="b5942-148">[Comprobar Skype Empresarial](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)correo de voz y opciones: en este artículo se explica cómo escuchar el correo de voz en Skype Empresarial, cambiar el saludo de correo de voz, cambiar la configuración del correo de voz y escuchar el correo de voz a diferentes velocidades.</span><span class="sxs-lookup"><span data-stu-id="b5942-148">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="b5942-149">Aprendizaje de Skype Empresarial 2016</span><span class="sxs-lookup"><span data-stu-id="b5942-149">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="b5942-150">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="b5942-150">Related topics</span></span>
[<span data-ttu-id="b5942-151">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="b5942-151">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="b5942-152">Esto es lo obtiene con el Sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="b5942-152">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="b5942-153">Planificar la migración de Skype Empresarial Server y Exchange Server</span><span class="sxs-lookup"><span data-stu-id="b5942-153">Plan for Skype for Business Server and Exchange Server migration</span></span>](/SkypeForBusiness/hybrid/plan-um-migration)
