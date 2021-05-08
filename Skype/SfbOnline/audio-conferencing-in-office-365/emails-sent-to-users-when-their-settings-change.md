---
title: Correos electrónicos enviados a los usuarios cuando su configuración cambia en Skype Empresarial Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Obtenga información sobre qué información se envía automáticamente a los usuarios por correo electrónico cuando la configuración de las conferencias de acceso telefónico local cambia en Skype Empresarial Online. '
ms.openlocfilehash: 75ed80ef7d686ecb649bc1d21f30a43fd115f1a3
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237346"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-skype-for-business-online"></a><span data-ttu-id="f02e0-103">Correos electrónicos enviados a los usuarios cuando su configuración cambia en Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="f02e0-103">Emails sent to users when their settings change in Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> <span data-ttu-id="f02e0-104">Si busca información de correo electrónico automática en Microsoft Teams, vea Correos electrónicos enviados a los usuarios cuando la configuración cambia [en Microsoft Teams](/MicrosoftTeams/emails-sent-to-users-when-their-settings-change-in-teams).</span><span class="sxs-lookup"><span data-stu-id="f02e0-104">If you're looking for automatic email information in Microsoft Teams, see [Emails sent to users when their settings change in Microsoft Teams](/MicrosoftTeams/emails-sent-to-users-when-their-settings-change-in-teams).</span></span>

<span data-ttu-id="f02e0-105">Los correos electrónicos se enviarán automáticamente a los usuarios habilitados para [conferencias](set-up-audio-conferencing.md) de audio con Microsoft como proveedor de audioconferencias.</span><span class="sxs-lookup"><span data-stu-id="f02e0-105">Emails will be automatically sent to users who are [enabled for Audio Conferencing](set-up-audio-conferencing.md) using Microsoft as the audio conferencing provider.</span></span>
  
<span data-ttu-id="f02e0-106">De forma predeterminada, hay cuatro tipos de correo electrónico que se enviarán a los usuarios habilitados para audioconferencias.</span><span class="sxs-lookup"><span data-stu-id="f02e0-106">By default, there are four types of email that will be sent to your users who are enabled for Audio Conferencing.</span></span> <span data-ttu-id="f02e0-107">Pero, si quiere limitar el número de correos electrónicos que se envían a los usuarios, puede desactivarlo.</span><span class="sxs-lookup"><span data-stu-id="f02e0-107">However, if you want to limit the number of emails sent to users, you can turn it off.</span></span> <span data-ttu-id="f02e0-108">Las conferencias de audio Microsoft 365 o Office 365 enviarán correo electrónico a los usuarios cuando:</span><span class="sxs-lookup"><span data-stu-id="f02e0-108">Audio Conferencing in Microsoft 365 or Office 365 will send email to your users' email when:</span></span>
  
- <span data-ttu-id="f02e0-109">**Se les asigna una licencia de audioconferencia o cuando cambia el proveedor de audioconferencias a Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="f02e0-109">**An Audio Conferencing license is assigned to them or when you are changing the audio conferencing provider to Microsoft.**</span></span>
    
     <span data-ttu-id="f02e0-110">Este correo electrónico incluye el id. de conferencia, el número de teléfono de conferencia predeterminado para las reuniones, el PIN de audioconferencia para el usuario, las instrucciones y el vínculo para usar la Herramienta de actualización de reuniones en línea de Skype Empresarial que se usa para actualizar las reuniones existentes para el usuario.</span><span class="sxs-lookup"><span data-stu-id="f02e0-110">This email includes the conference ID, the default conference phone number for the meetings, the audio conferencing PIN for the user, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="f02e0-111">Vea [Asignar Skype Empresarial licencias](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) o Asignar Microsoft como el proveedor de [audioconferencias.](assign-microsoft-as-the-audio-conferencing-provider.md)</span><span class="sxs-lookup"><span data-stu-id="f02e0-111">See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) or [Assign Microsoft as the audio conferencing provider](assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f02e0-112">Si en su organización se han habilitado los identificadores de conferencia dinámicos, todas las reuniones que se programen de un usuario tendrán identificadores de conferencia únicos.</span><span class="sxs-lookup"><span data-stu-id="f02e0-112">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="f02e0-113">Puede configurar los [ID dinámicos de audioconferencia en su organización.](./reset-a-conference-id-for-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="f02e0-113">You can set up [Audio Conferencing dynamic IDs in your organization](./reset-a-conference-id-for-a-user.md).</span></span> 
  
    <span data-ttu-id="f02e0-114">Este es un ejemplo de este correo electrónico:</span><span class="sxs-lookup"><span data-stu-id="f02e0-114">Here is an example of this email:</span></span>
    
     ![Skype Empresarial: comprobar licencia](../images/audio-conferencing-user-enabled.png)
  
    <span data-ttu-id="f02e0-116">Para más información sobre las licencias de Skype Empresarial, vea [Licencias complementarias de Skype Empresarial](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="f02e0-116">You can find out more about Skype for Business licensing by seeing [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
- <span data-ttu-id="f02e0-117">**Cambia el id. de conferencia o número de teléfono de conferencia predeterminado de un usuario.**</span><span class="sxs-lookup"><span data-stu-id="f02e0-117">**The conference ID or default conference phone number of a user changes.**</span></span>
    
    <span data-ttu-id="f02e0-118">Este correo electrónico contiene el id. de conferencia, el número de teléfono de conferencia predeterminado, las instrucciones y el vínculo para usar la Herramienta de actualización de reuniones en línea de Skype Empresarial que se usa para actualizar las reuniones existentes para el usuario.</span><span class="sxs-lookup"><span data-stu-id="f02e0-118">This email contains the conference ID, default conference phone number, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="f02e0-119">Pero este correo electrónico no incluye el PIN de audioconferencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="f02e0-119">But this email doesn't include the user's audio conferencing PIN.</span></span> <span data-ttu-id="f02e0-120">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="f02e0-120">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f02e0-121">Si en su organización se han habilitado los identificadores de conferencia dinámicos, todas las reuniones que se programen de un usuario tendrán identificadores de conferencia únicos.</span><span class="sxs-lookup"><span data-stu-id="f02e0-121">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="f02e0-122">Puede configurar los [ID dinámicos de audioconferencia en su organización.](./reset-a-conference-id-for-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="f02e0-122">You can set up [Audio Conferencing dynamic IDs in your organization](./reset-a-conference-id-for-a-user.md).</span></span> 
  
    <span data-ttu-id="f02e0-123">Este es un ejemplo de este correo electrónico:</span><span class="sxs-lookup"><span data-stu-id="f02e0-123">Here is an example of this email:</span></span>
    
     ![La información de conferencias de acceso telefónico local ha cambiado.](../images/audio-conferencing-info-change.png)
  
- <span data-ttu-id="f02e0-125">**Se restablece el PIN de audioconferencia de un usuario.**</span><span class="sxs-lookup"><span data-stu-id="f02e0-125">**The audio conferencing PIN of a user is reset.**</span></span>
    
    <span data-ttu-id="f02e0-126">Este correo electrónico contiene el PIN de audioconferencia del organizador, el id. de conferencia existente y el número de teléfono de conferencia predeterminado para el usuario.</span><span class="sxs-lookup"><span data-stu-id="f02e0-126">This email contains the organizer's audio conferencing PIN, the existing conference ID, and default conference phone number for the user.</span></span> <span data-ttu-id="f02e0-127">Vea [Restablecer el PIN de audioconferencia.](reset-the-audio-conferencing-pin.md)</span><span class="sxs-lookup"><span data-stu-id="f02e0-127">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f02e0-128">Si en su organización se han habilitado los identificadores de conferencia dinámicos, todas las reuniones que se programen de un usuario tendrán identificadores de conferencia únicos.</span><span class="sxs-lookup"><span data-stu-id="f02e0-128">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="f02e0-129">Puede configurar los [ID dinámicos de audioconferencia en su organización.](./reset-a-conference-id-for-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="f02e0-129">You can set up [Audio Conferencing dynamic IDs in your organization](./reset-a-conference-id-for-a-user.md).</span></span> 
  
    <span data-ttu-id="f02e0-130">Este es un ejemplo de este correo electrónico:</span><span class="sxs-lookup"><span data-stu-id="f02e0-130">Here is an example of this email:</span></span>
    
     ![El PIN para las conferencias de acceso telefónico local ha cambiado.](../images/audio-conferencing-pin-has-changed.png)
  
- <span data-ttu-id="f02e0-132">**Se quita la licencia de un usuario o cuando el proveedor de servicios de audioconferencia cambia de Microsoft a otro proveedor o ninguno.**</span><span class="sxs-lookup"><span data-stu-id="f02e0-132">**A user's license is removed or when audio conferencing provider changes from Microsoft to other provider or None.**</span></span>
    
    <span data-ttu-id="f02e0-133">Esto ocurre  cuando la licencia de audioconferencia se quita de un usuario o al cambiar el proveedor de audioconferencia de un usuario de Microsoft a un proveedor de audioconferencia de terceros o al establecer el proveedor en **Ninguno.**</span><span class="sxs-lookup"><span data-stu-id="f02e0-133">This happens when the **Audio Conferencing** license is removed from a user or when changing the audio conferencing provider of a user from Microsoft to a third-party audio conferencing provider or when setting the provider to **None**.</span></span> <span data-ttu-id="f02e0-134">Este correo electrónico contiene las instrucciones e información para que el usuario use la Herramienta de actualización de reuniones en línea de Skype Empresarial para quitar información específica de las audioconferencias, como el número de teléfono de conferencia predeterminado o el id. de conferencia.</span><span class="sxs-lookup"><span data-stu-id="f02e0-134">This email contains the instructions and information for the user to use the Skype for Business Online Meeting Update Tool to remove audio conferencing specific information, such as the default conference phone number or conference ID.</span></span>
    
    <span data-ttu-id="f02e0-135">Vea [Asignar o quitar licencias para Aplicaciones Microsoft 365 para negocios](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="f02e0-135">See [Assign or remove licenses for Microsoft 365 Apps for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
    
    <span data-ttu-id="f02e0-136">Este es un ejemplo de este correo electrónico:</span><span class="sxs-lookup"><span data-stu-id="f02e0-136">Here is an example of this email:</span></span>
    
     ![Las conferencias de acceso telefónico local están desactivadas.](../images/audio-conferencing-turned-off.png)
  
> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a><span data-ttu-id="f02e0-138">Realizar cambios en los mensajes de correo electrónico que se les envían</span><span class="sxs-lookup"><span data-stu-id="f02e0-138">Make changes to the email messages that are sent to them</span></span>

<span data-ttu-id="f02e0-139">Puede realizar cambios en el correo electrónico que se envía automáticamente a los usuarios, incluida la dirección de correo electrónico y el nombre para mostrar que se incluye en *la* información de contacto De.</span><span class="sxs-lookup"><span data-stu-id="f02e0-139">You can make changes to the email that is automatically sent to users including the email address and the display name that is included in the *From* contact information.</span></span> <span data-ttu-id="f02e0-140">De forma predeterminada, el remitente de los correos electrónicos será de Microsoft 365 o Office 365, pero puede cambiar la dirección de correo electrónico y el nombre para mostrar con Windows PowerShell y el cmdlet [Set-CsOnlineDialInConferencingTenantSettings.](/previous-versions//mt228132(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="f02e0-140">By default, the sender of the emails will be from Microsoft 365 or Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10)) cmdlet.</span></span> <span data-ttu-id="f02e0-141">To make changes to the email address that is sending the email to the users, you must:</span><span class="sxs-lookup"><span data-stu-id="f02e0-141">To make changes to the email address that is sending the email to the users, you must:</span></span>
  
- <span data-ttu-id="f02e0-142">Puede realizar cambios en el correo electrónico que se envía de forma automática a los usuarios, como la dirección de correo electrónico real y el nombre para mostrar de la información de contacto del remitente. De manera predeterminada, el remitente de los mensajes será de Office 365, pero puede cambiar la dirección de correo electrónico y el nombre para mostrar con Windows PowerShell y el cmdlet _Set-CsOnlineDialInConferencingTenantSettings_. Para realizar cambios en la dirección de correo electrónico que envía el correo electrónico a los usuarios:</span><span class="sxs-lookup"><span data-stu-id="f02e0-142">Enter the email address in the  _SendEmailFromAddress_ parameter.</span></span>
    
- <span data-ttu-id="f02e0-143">Escriba el nombre para mostrar del correo electrónico en el parámetro  _SendEmailFromDisplayName_.</span><span class="sxs-lookup"><span data-stu-id="f02e0-143">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>
    
- <span data-ttu-id="f02e0-144">Establezca el  _parámetro SendEmailOverride_ en  _True_.</span><span class="sxs-lookup"><span data-stu-id="f02e0-144">Set the  _SendEmailOverride_ parameter to  _True_.</span></span>
    
<span data-ttu-id="f02e0-145">Puede realizar cambios en el correo electrónico enviado a los usuarios, como la dirección de correo electrónico desde la que se envía el correo electrónico y el nombre para mostrar del correo electrónico, ejecutando:</span><span class="sxs-lookup"><span data-stu-id="f02e0-145">You can make changes to the email sent to users, such as the email address that the email is sent from and the display name for the email, by running:</span></span>
  
```PowerShell
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
>  <span data-ttu-id="f02e0-146">Si desea cambiar la información de la dirección de correo electrónico, debe asegurarse de que las directivas de correo electrónico entrante de su entorno permiten los correos electrónicos que proceden de la dirección personalizada especificada.</span><span class="sxs-lookup"><span data-stu-id="f02e0-146">If you want to change the email address information, you need to make sure that the inbound email policies of your environment allow emails that come from the custom specified from address.</span></span> <span data-ttu-id="f02e0-147">Si decide invalidar la *información* de contacto De, debe comprobar que los correos electrónicos se envían correctamente a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="f02e0-147">If you decide to override the *From* contact information, you should verify that the emails are correctly sent to users.</span></span> <span data-ttu-id="f02e0-148">Para ello, puede probar esto con un usuario de su organización.</span><span class="sxs-lookup"><span data-stu-id="f02e0-148">You can do this by testing this with one user in your organization.</span></span>
  
<span data-ttu-id="f02e0-149">You can use the [Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10)) cmdlet to manage other settings for your organization, including email.</span><span class="sxs-lookup"><span data-stu-id="f02e0-149">You can use the [Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10)) cmdlet to manage other settings for your organization, including email.</span></span>
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a><span data-ttu-id="f02e0-150">¿Qué pasa si no desea que se les envíen correos electrónicos?</span><span class="sxs-lookup"><span data-stu-id="f02e0-150">What if you don't want email to be sent to them?</span></span>

<span data-ttu-id="f02e0-151">Al deshabilitar el envío de correos electrónicos a los usuarios, el correo electrónico no se enviará incluso cuando se asigne una licencia a un usuario.</span><span class="sxs-lookup"><span data-stu-id="f02e0-151">When you disable sending emails to users, email won't be sent even when a user gets assigned a license.</span></span> <span data-ttu-id="f02e0-152">En este caso, el ID de conferencia, el número de teléfono de conferencia predeterminado y, lo que es más importante, su PIN de audioconferencia no se enviarán al usuario.</span><span class="sxs-lookup"><span data-stu-id="f02e0-152">In this case, the conference ID, default conferencing phone number, and, more importantly, their audio conferencing PIN won't be sent to the user.</span></span> <span data-ttu-id="f02e0-153">Cuando esto sucede, debe avisarle al usuario enviándole un correo electrónico independiente o llamándolo.</span><span class="sxs-lookup"><span data-stu-id="f02e0-153">When this happens, you must tell the user by sending them a separate email or by calling them.</span></span>
  
<span data-ttu-id="f02e0-154">De forma predeterminada, los correos electrónicos se enviarán a los usuarios, pero si quiere evitar que reciban correo electrónico para audioconferencias, puede usar el centro de administración de Skype Empresarial o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f02e0-154">By default, emails will be sent to your users, but if you want to prevent them from receiving email for audio conferencing, you can use the Skype for Business admin center or Windows PowerShell.</span></span> 
 
<span data-ttu-id="f02e0-155">![Un icono que muestra el Skype Empresarial ](../images/sfb-logo-30x30.png) **con el centro Skype Empresarial administración**  </span><span class="sxs-lookup"><span data-stu-id="f02e0-155">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png)  **Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="f02e0-156">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span><span class="sxs-lookup"><span data-stu-id="f02e0-156">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="f02e0-157">En la **página Configuración del puente de Microsoft,** seleccione o desactive Enviar mensajes de correo electrónico automáticamente a los usuarios si la configuración de las **audioconferencias cambia.**</span><span class="sxs-lookup"><span data-stu-id="f02e0-157">On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their audio conferencing settings change**.</span></span> 
    
3. <span data-ttu-id="f02e0-158">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f02e0-158">Click **Save**.</span></span> 

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
<span data-ttu-id="f02e0-159">Vea **Enviar un correo electrónico a un usuario con su información de conferencias de Audio**.</span><span class="sxs-lookup"><span data-stu-id="f02e0-159">**Using Windows PowerShell**</span></span>
  
1. <span data-ttu-id="f02e0-160">Ejecute las acciones siguientes para deshabilitar el envío de todos los correos electrónicos a sus usuarios:</span><span class="sxs-lookup"><span data-stu-id="f02e0-160">Run the following to disable sending all of your users email:</span></span>
    
   ```PowerShell
   Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $false
   ```

<span data-ttu-id="f02e0-161">You can use the [Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10)) cmdlet to manage other settings for your organization, including email.</span><span class="sxs-lookup"><span data-stu-id="f02e0-161">You can use the [Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10)) cmdlet to manage other settings for your organization, including email.</span></span>
  
## <a name="what-else-should-you-know-about-this-email"></a><span data-ttu-id="f02e0-162">¿Qué más debe saber sobre este correo electrónico?</span><span class="sxs-lookup"><span data-stu-id="f02e0-162">What else should you know about this email?</span></span>

- <span data-ttu-id="f02e0-163">Para más información sobre habilitar y deshabilitar el envío de correos electrónicos de forma automática a sus usuarios, vea [Habilitar o deshabilitar el envío de correos electrónicos cuando cambie la configuración de conferencias de Audio](enable-or-disable-sending-emails-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="f02e0-163">For more on enabling and disabling automatically sending email to your users, see [Enable or disable sending emails when Audio Conferencing settings change](enable-or-disable-sending-emails-when-their-settings-change.md).</span></span>
    
- <span data-ttu-id="f02e0-164">A veces, los usuarios pierden su información de audio y necesita poder enviarles toda su información de audio.</span><span class="sxs-lookup"><span data-stu-id="f02e0-164">Sometimes users lose their audio information and you need to be able to send them all of their audio information to them.</span></span> <span data-ttu-id="f02e0-165">Para ello, use el centro de administración  de Skype Empresarial y haga clic en Enviar información de conferencia por correo electrónico en las propiedades de audioconferencia de un usuario.</span><span class="sxs-lookup"><span data-stu-id="f02e0-165">You can do this by using the Skype for Business admin center and clicking **Send conference info via email** under the audio conferencing properties for a user.</span></span> <span data-ttu-id="f02e0-166">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="f02e0-166">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span> <span data-ttu-id="f02e0-167">Sin embargo, esta información no incluye el PIN de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="f02e0-167">However, this information doesn't include the audio conferencing PIN.</span></span>
    
    <span data-ttu-id="f02e0-168">Este es un ejemplo del correo electrónico que se les enviará:</span><span class="sxs-lookup"><span data-stu-id="f02e0-168">Here is an example of this email that will be sent to them:</span></span>
    
     ![Correo electrónico de conferencia de acceso telefónico](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="f02e0-170">¿Desea saber cómo administrar con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="f02e0-170">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="f02e0-171">De forma predeterminada, el remitente de los correos electrónicos será de Microsoft 365 o Office 365, pero puede cambiar la dirección de correo electrónico y el nombre para mostrar con Windows PowerShell y el cmdlet [Set-CsOnlineDialInConferencingTenantSettings.](/previous-versions//mt228132(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="f02e0-171">By default, the sender of the emails will be from Microsoft 365 or Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10)) cmdlet.</span></span>
    
- <span data-ttu-id="f02e0-172">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="f02e0-172">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="f02e0-173">Con Windows PowerShell, puede administrar Microsoft 365 o Office 365 un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas que hacer.</span><span class="sxs-lookup"><span data-stu-id="f02e0-173">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="f02e0-174">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="f02e0-174">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="f02e0-175">¿Por qué necesita usar Microsoft 365 o Office 365 PowerShell?</span><span class="sxs-lookup"><span data-stu-id="f02e0-175">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="f02e0-176">[Las mejores formas de administrar Microsoft 365 o Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="f02e0-176">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="f02e0-177">Windows PowerShell tiene muchas ventajas en la velocidad, la sencillez y la productividad sobre el uso del centro de administración de Microsoft 365, como cuando realiza cambios de configuración para muchos usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="f02e0-177">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="f02e0-178">Más información sobre estas ventajas en los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="f02e0-178">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="f02e0-179">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="f02e0-179">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="f02e0-180">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="f02e0-180">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="f02e0-181">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="f02e0-181">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > <span data-ttu-id="f02e0-p115">El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="f02e0-p115">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="f02e0-184">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="f02e0-184">Related topics</span></span>

[<span data-ttu-id="f02e0-185">Habilitar o deshabilitar el envío de correos electrónicos cuando cambie la configuración de conferencias de Audio</span><span class="sxs-lookup"><span data-stu-id="f02e0-185">Enable or disable sending emails when Audio Conferencing settings change</span></span>](enable-or-disable-sending-emails-when-their-settings-change.md)
  
[<span data-ttu-id="f02e0-186">Enviar un correo electrónico a un usuario con su información de conferencias de Audio</span><span class="sxs-lookup"><span data-stu-id="f02e0-186">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)
