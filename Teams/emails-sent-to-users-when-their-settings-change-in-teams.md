---
title: Correos electrónicos que se envían a los usuarios cuando cambia la configuración
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'Vea qué información se envía por correo electrónico automáticamente a los usuarios cuando cambia su configuración de las conferencias de acceso telefónico local en Microsoft Teams. '
ms.openlocfilehash: 15c35570d509ae69a41e4c6d9522a5a62d32dd59
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691486"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a><span data-ttu-id="c110d-103">Correos electrónicos que se envían a los usuarios cuando cambia la configuración en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c110d-103">Emails sent to users when their settings change in Microsoft Teams</span></span>

<span data-ttu-id="c110d-104">Los correos electrónicos se enviarán automáticamente a los usuarios que estén [habilitados para Audioconferencia](set-up-audio-conferencing-in-teams.md) con Microsoft como proveedor de servicios de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="c110d-104">Emails will be automatically sent to users who are [enabled for Audio Conferencing](set-up-audio-conferencing-in-teams.md) using Microsoft as the audio conferencing provider.</span></span>

<span data-ttu-id="c110d-105">De manera predeterminada, hay cuatro tipos de correos electrónicos que se enviarán a los usuarios habilitados para Audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="c110d-105">By default, there are four types of email that will be sent to your users who are enabled for Audio Conferencing.</span></span> <span data-ttu-id="c110d-106">Sin embargo, si quiere limitar el número de correos electrónicos que se envían a los usuarios, puede desactivar esta función.</span><span class="sxs-lookup"><span data-stu-id="c110d-106">However, if you want to limit the number of emails sent to users, you can turn it off.</span></span> <span data-ttu-id="c110d-107">Las conferencias de audio en Microsoft 365 u Office 365 enviarán correos electrónicos al correo electrónico de los usuarios cuando:</span><span class="sxs-lookup"><span data-stu-id="c110d-107">Audio Conferencing in Microsoft 365 or Office 365 will send email to your users' email when:</span></span>

- <span data-ttu-id="c110d-108">**Se les asigna una licencia de Audioconferencia o cuando está cambiando el proveedor de servicios de audioconferencia a Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="c110d-108">**An Audio Conferencing license is assigned to them or when you are changing the audio conferencing provider to Microsoft.**</span></span>

     <span data-ttu-id="c110d-109">Este correo electrónico incluye el Id. de conferencia, el número de teléfono de conferencia predeterminado para las reuniones, el PIN del usuario para audioconferencias, así como las instrucciones y el vínculo para usar la herramienta de actualización de reuniones de Skype Empresarial Online que se utiliza para actualizar reuniones existentes del usuario.</span><span class="sxs-lookup"><span data-stu-id="c110d-109">This email includes the conference ID, the default conference phone number for the meetings, the audio conferencing PIN for the user, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="c110d-110">Consulte [asignar licencias de complemento de Microsoft Teams](teams-add-on-licensing/assign-teams-add-on-licenses.md) o [asignar Microsoft como proveedor](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)de servicios de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="c110d-110">See [Assign Microsoft Teams add-on licenses](teams-add-on-licensing/assign-teams-add-on-licenses.md) or [Assign Microsoft as the audio conferencing provider](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>

    > [!NOTE]
    > <span data-ttu-id="c110d-111">Si en su organización se han habilitado los identificadores de conferencia dinámicos, todas las reuniones que se programen de un usuario tendrán identificadores de conferencia únicos.</span><span class="sxs-lookup"><span data-stu-id="c110d-111">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="c110d-112">Puede configurar [identificadores dinámicos de Audioconferencia en su organización](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="c110d-112">You can set up [Audio Conferencing dynamic IDs in your organization](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user).</span></span> 

    <span data-ttu-id="c110d-113">A continuación tiene un ejemplo de este correo electrónico:</span><span class="sxs-lookup"><span data-stu-id="c110d-113">Here is an example of this email:</span></span>

     ![Skype Empresarial: comprobar licencia](media/teams-emails-sent-to-users-when-settings-change-image1.png)

    <span data-ttu-id="c110d-115">Para más información sobre las licencias, vea [licencias complementarias de Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="c110d-115">To find out more about licensing, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

- <span data-ttu-id="c110d-116">**El Id. de conferencia o el número de teléfono de conferencia predeterminado de un usuario cambia.**</span><span class="sxs-lookup"><span data-stu-id="c110d-116">**The conference ID or default conference phone number of a user changes.**</span></span>

    <span data-ttu-id="c110d-117">Este correo electrónico contiene el Id. de conferencia, el número de teléfono de conferencia predeterminado, y las instrucciones y el vínculo para usar la herramienta de actualización de reuniones de Skype Empresarial Online que se usa para actualizar reuniones existentes para el usuario.</span><span class="sxs-lookup"><span data-stu-id="c110d-117">This email contains the conference ID, default conference phone number, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="c110d-118">Sin embargo, en este correo electrónico no se incluye el PIN de audioconferencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="c110d-118">But this email doesn't include the user's audio conferencing PIN.</span></span> <span data-ttu-id="c110d-119">Vea [Restablecer un Id. de conferencia para un usuario](reset-a-conference-id-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="c110d-119">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span></span>

    <span data-ttu-id="c110d-120">A continuación tiene un ejemplo de este correo electrónico:</span><span class="sxs-lookup"><span data-stu-id="c110d-120">Here is an example of this email:</span></span>

     ![La información de conferencias de acceso telefónico local ha cambiado.](media/teams-emails-sent-to-users-when-settings-change-image2.png)

- <span data-ttu-id="c110d-122">**El PIN de audioconferencia de un usuario se ha restablecido.**</span><span class="sxs-lookup"><span data-stu-id="c110d-122">**The audio conferencing PIN of a user is reset.**</span></span>

    <span data-ttu-id="c110d-123">Este correo electrónico contiene el PIN de audioconferencia del organizador, el Id. de conferencia existente y el número de teléfono de la conferencia predeterminado para el usuario.</span><span class="sxs-lookup"><span data-stu-id="c110d-123">This email contains the organizer's audio conferencing PIN, the existing conference ID, and default conference phone number for the user.</span></span> <span data-ttu-id="c110d-124">Vea [Restablecer el PIN de Audioconferencia](reset-the-audio-conferencing-pin-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="c110d-124">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
    
     <span data-ttu-id="c110d-125">A continuación tiene un ejemplo de este correo electrónico:</span><span class="sxs-lookup"><span data-stu-id="c110d-125">Here is an example of this email:</span></span>
    
     ![La información de las conferencias de acceso telefónico local ha cambiado.](media/teams-emails-sent-to-users-when-settings-change-image3.png)
  
- <span data-ttu-id="c110d-127">**Cuando se quita la licencia de un usuario o cuando el proveedor de servicios de audioconferencia cambia de Microsoft a otro proveedor o a Ninguno.**</span><span class="sxs-lookup"><span data-stu-id="c110d-127">**A user's license is removed or when audio conferencing provider changes from Microsoft to other provider or None.**</span></span>

    <span data-ttu-id="c110d-128">Esto sucede cuando se quita la licencia de **audioconferencia** de un usuario o cuando se configura el proveedor de servicios de audioconferencia como **ninguno**.</span><span class="sxs-lookup"><span data-stu-id="c110d-128">This happens when the **Audio Conferencing** license is removed from a user or when setting the audio conferencing provider to **None**.</span></span>

    <span data-ttu-id="c110d-129">Consulte [asignar o quitar licencias de Microsoft 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="c110d-129">See [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

    <span data-ttu-id="c110d-130">Este es un ejemplo de este correo electrónico:</span><span class="sxs-lookup"><span data-stu-id="c110d-130">Here is an example of this email:</span></span>

     ![Las conferencias de acceso telefónico local están desactivadas.](media/teams-emails-sent-to-users-when-settings-change-image4.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a><span data-ttu-id="c110d-132">Realizar cambios en los mensajes de correo electrónico que se les envían</span><span class="sxs-lookup"><span data-stu-id="c110d-132">Make changes to the email messages that are sent to them</span></span>

<span data-ttu-id="c110d-133">Puede realizar cambios en el correo electrónico que se envía automáticamente a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="c110d-133">You can make changes to the email that is automatically sent to users.</span></span> <span data-ttu-id="c110d-134">De forma predeterminada, el remitente de los mensajes de correo electrónico será de Microsoft 365 u Office 365, pero puede cambiar el nombre para mostrar con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c110d-134">By default, the sender of the emails will be from Microsoft 365 or Office 365, but you can change the display name using Windows PowerShell.</span></span> <span data-ttu-id="c110d-135">Para obtener más información, vea la [referencia de Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) .</span><span class="sxs-lookup"><span data-stu-id="c110d-135">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a><span data-ttu-id="c110d-136">¿Qué pasa si no desea que se les envíen correos electrónicos?</span><span class="sxs-lookup"><span data-stu-id="c110d-136">What if you don't want email to be sent to them?</span></span>

<span data-ttu-id="c110d-137">Cuando deshabilite el envío de correos electrónicos a los usuarios, el correo electrónico no se enviará aunque se asigne una licencia a un usuario.</span><span class="sxs-lookup"><span data-stu-id="c110d-137">When you disable sending emails to users, email won't be sent even when a user gets assigned a license.</span></span> <span data-ttu-id="c110d-138">En este caso, el identificador de la Conferencia, el número de teléfono de conferencia predeterminado y, lo que es más importante, su PIN de audioconferencia no se enviará al usuario.</span><span class="sxs-lookup"><span data-stu-id="c110d-138">In this case, the conference ID, default conferencing phone number, and, more importantly, their audio conferencing PIN won't be sent to the user.</span></span> <span data-ttu-id="c110d-139">Cuando esto sucede, debe decir al usuario enviándoles un mensaje de correo electrónico o llamándolos.</span><span class="sxs-lookup"><span data-stu-id="c110d-139">When this happens, you must tell the user by sending them a separate email or by calling them.</span></span>

<span data-ttu-id="c110d-140">De forma predeterminada, los correos electrónicos se enviarán a los usuarios, pero si quiere evitar que reciban correo electrónico para las conferencias de audio, puede usar Microsoft Teams o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c110d-140">By default, emails will be sent to your users, but if you want to prevent them from receiving email for audio conferencing, you can use Microsoft Teams or Windows PowerShell.</span></span> 

<span data-ttu-id="c110d-141">![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="c110d-141">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="c110d-142">En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="c110d-142">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="c110d-143">En la parte superior de la página **puentes de conferencia** , haga clic en **configuración del puente**.</span><span class="sxs-lookup"><span data-stu-id="c110d-143">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="c110d-144">En el panel **configuración de puente** , habilite o deshabilite **el envío automático de correos electrónicos a los usuarios si cambia la configuración de acceso telefónico local**.</span><span class="sxs-lookup"><span data-stu-id="c110d-144">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="c110d-145">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="c110d-145">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="c110d-146">Vea **Enviar un correo electrónico a un usuario con su información de conferencias de Audio**.</span><span class="sxs-lookup"><span data-stu-id="c110d-146">**Using Windows PowerShell**</span></span>

<span data-ttu-id="c110d-147">Para obtener más información, vea la [referencia de Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) .</span><span class="sxs-lookup"><span data-stu-id="c110d-147">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="c110d-148">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="c110d-148">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="c110d-149">De forma predeterminada, el remitente de los mensajes de correo electrónico será de Microsoft 365 u Office 365, pero puede cambiar la dirección de correo electrónico y el nombre para mostrar con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c110d-149">By default, the sender of the emails will be from Microsoft 365 or Office 365, but you can change the email address and display name using Windows PowerShell.</span></span> 

<span data-ttu-id="c110d-150">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="c110d-150">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="c110d-151">Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 con un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas para hacer.</span><span class="sxs-lookup"><span data-stu-id="c110d-151">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="c110d-152">To get started with Windows PowerShell, see these topics:</span><span class="sxs-lookup"><span data-stu-id="c110d-152">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="c110d-153">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="c110d-153">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [<span data-ttu-id="c110d-154">Las mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c110d-154">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

<span data-ttu-id="c110d-155">Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="c110d-155">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="related-topics"></a><span data-ttu-id="c110d-156">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="c110d-156">Related topics</span></span>

[<span data-ttu-id="c110d-157">Habilitar o deshabilitar el envío de correos electrónicos cuando cambie la configuración de conferencias de Audio</span><span class="sxs-lookup"><span data-stu-id="c110d-157">Enable or disable sending emails when Audio Conferencing settings change</span></span>](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)

[<span data-ttu-id="c110d-158">Enviar un correo electrónico a un usuario con su información de conferencias de Audio</span><span class="sxs-lookup"><span data-stu-id="c110d-158">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
