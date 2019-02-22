---
title: Correos electrónicos que se envían a los usuarios cuando cambia la configuración en Microsoft Teams
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
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Vea qué información se envía por correo electrónico automáticamente a los usuarios cuando cambia su configuración de las conferencias de acceso telefónico local en Microsoft Teams. '
ms.openlocfilehash: 1431cd4391219e052ec2ad3702a9e4c227912a06
ms.sourcegitcommit: d3c459dc1304db5f5ba78b5e093b5a4fd797c8ec
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2019
ms.locfileid: "30178696"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a><span data-ttu-id="5d3db-103">Correos electrónicos que se envían a los usuarios cuando cambia la configuración en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5d3db-103">Emails sent to users when their settings change in Microsoft Teams</span></span>

<span data-ttu-id="5d3db-104">Los correos electrónicos se enviarán automáticamente a los usuarios que estén [habilitados para Audioconferencia](/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing) con Microsoft como proveedor de servicios de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="5d3db-104">Emails will be automatically sent to users who are [enabled for Audio Conferencing](/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing) using Microsoft as the audio conferencing provider.</span></span>

<span data-ttu-id="5d3db-105">De manera predeterminada, hay cuatro tipos de correos electrónicos que se enviarán a los usuarios habilitados para Audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="5d3db-105">By default, there are four types of email that will be sent to your users who are enabled for Audio Conferencing.</span></span> <span data-ttu-id="5d3db-106">Sin embargo, si quiere limitar el número de correos electrónicos que se envían a los usuarios, puede desactivar esta función.</span><span class="sxs-lookup"><span data-stu-id="5d3db-106">However, if you want to limit the number of emails sent to users, you can turn it off.</span></span> <span data-ttu-id="5d3db-107">Audioconferencia en Office 365 enviará un correo electrónico a los usuarios en las siguientes circunstancias:</span><span class="sxs-lookup"><span data-stu-id="5d3db-107">Audio Conferencing in Office 365 will send email to your users' email when:</span></span>

- <span data-ttu-id="5d3db-108">**Se les asigna una licencia de Audioconferencia o cuando está cambiando el proveedor de servicios de audioconferencia a Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="5d3db-108">**An Audio Conferencing license is assigned to them or when you are changing the audio conferencing provider to Microsoft.**</span></span>

     <span data-ttu-id="5d3db-109">Este correo electrónico incluye el Id. de conferencia, el número de teléfono de conferencia predeterminado para las reuniones, el PIN del usuario para audioconferencias, así como las instrucciones y el vínculo para usar la herramienta de actualización de reuniones de Skype Empresarial Online que se utiliza para actualizar reuniones existentes del usuario.</span><span class="sxs-lookup"><span data-stu-id="5d3db-109">This email includes the conference ID, the default conference phone number for the meetings, the audio conferencing PIN for the user, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="5d3db-110">Vea [las licencias de asignar los equipos de Microsoft](assign-teams-licenses.md) o [Microsoft asignar como el proveedor de conferencia de audio](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span><span class="sxs-lookup"><span data-stu-id="5d3db-110">See [Assign Microsoft Teams licenses](assign-teams-licenses.md) or [Assign Microsoft as the audio conferencing provider](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>

    > [!NOTE]
    > <span data-ttu-id="5d3db-111">Si en su organización se han habilitado los identificadores de conferencia dinámicos, todas las reuniones que se programen de un usuario tendrán identificadores de conferencia únicos.</span><span class="sxs-lookup"><span data-stu-id="5d3db-111">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="5d3db-112">Puede configurar [identificadores dinámicos de Audioconferencia en su organización](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="5d3db-112">You can set up [Audio Conferencing dynamic IDs in your organization](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user).</span></span> 

    <span data-ttu-id="5d3db-113">A continuación tiene un ejemplo de este correo electrónico:</span><span class="sxs-lookup"><span data-stu-id="5d3db-113">Here is an example of this email:</span></span>

     ![Skype Empresarial: comprobar licencia](media/teams-emails-sent-to-users-when-settings-change-image1.png)

    <span data-ttu-id="5d3db-115">Para obtener más información acerca de las licencias, vea [licencias de complemento de equipos de Microsoft](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="5d3db-115">To find out more about licensing, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

- <span data-ttu-id="5d3db-116">**El Id. de conferencia o el número de teléfono de conferencia predeterminado de un usuario cambia.**</span><span class="sxs-lookup"><span data-stu-id="5d3db-116">**The conference ID or default conference phone number of a user changes.**</span></span>

    <span data-ttu-id="5d3db-117">Este correo electrónico contiene el Id. de conferencia, el número de teléfono de conferencia predeterminado, y las instrucciones y el vínculo para usar la herramienta de actualización de reuniones de Skype Empresarial Online que se usa para actualizar reuniones existentes para el usuario.</span><span class="sxs-lookup"><span data-stu-id="5d3db-117">This email contains the conference ID, default conference phone number, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="5d3db-118">Sin embargo, en este correo electrónico no se incluye el PIN de audioconferencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="5d3db-118">But this email doesn't include the user's audio conferencing PIN.</span></span> <span data-ttu-id="5d3db-119">Vea [Restablecer un Id. de conferencia para un usuario](reset-a-conference-id-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="5d3db-119">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span></span>

    <span data-ttu-id="5d3db-120">A continuación tiene un ejemplo de este correo electrónico:</span><span class="sxs-lookup"><span data-stu-id="5d3db-120">Here is an example of this email:</span></span>

     ![La información de conferencias de acceso telefónico local ha cambiado.](media/teams-emails-sent-to-users-when-settings-change-image2.png)

- <span data-ttu-id="5d3db-122">**El PIN de audioconferencia de un usuario se ha restablecido.**</span><span class="sxs-lookup"><span data-stu-id="5d3db-122">**The audio conferencing PIN of a user is reset.**</span></span>

    <span data-ttu-id="5d3db-123">Este correo electrónico contiene el PIN de audioconferencia del organizador, el Id. de conferencia existente y el número de teléfono de la conferencia predeterminado para el usuario.</span><span class="sxs-lookup"><span data-stu-id="5d3db-123">This email contains the organizer's audio conferencing PIN, the existing conference ID, and default conference phone number for the user.</span></span> <span data-ttu-id="5d3db-124">Vea [Restablecer el PIN de Audioconferencia](reset-the-audio-conferencing-pin-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="5d3db-124">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
    
     <span data-ttu-id="5d3db-125">A continuación tiene un ejemplo de este correo electrónico:</span><span class="sxs-lookup"><span data-stu-id="5d3db-125">Here is an example of this email:</span></span>
    
     ![La información de las conferencias de acceso telefónico local ha cambiado.](media/teams-emails-sent-to-users-when-settings-change-image3.png)
  
- <span data-ttu-id="5d3db-127">**Cuando se quita la licencia de un usuario o cuando el proveedor de servicios de audioconferencia cambia de Microsoft a otro proveedor o a Ninguno.**</span><span class="sxs-lookup"><span data-stu-id="5d3db-127">**A user's license is removed or when audio conferencing provider changes from Microsoft to other provider or None.**</span></span>

    <span data-ttu-id="5d3db-128">Esto se produce cuando la licencia de **Audioconferencia** se quita de un usuario o cuando el proveedor de servicios de audioconferencia de un usuario cambia de Microsoft a un proveedor de servicios de audioconferencia de terceros, o bien cuando se establece el proveedor en **Ninguno**.</span><span class="sxs-lookup"><span data-stu-id="5d3db-128">This happens when the **Audio Conferencing** license is removed from a user or when changing the audio conferencing provider of a user from Microsoft to a third-party audio conferencing provider or when setting the provider to **None**.</span></span> <span data-ttu-id="5d3db-129">Este correo electrónico contiene las instrucciones e información para que el usuario pueda usar la herramienta de actualización de reuniones de Skype Empresarial Online para quitar información específica de las audioconferencias, como el número de teléfono o el Id. de conferencia predeterminados.</span><span class="sxs-lookup"><span data-stu-id="5d3db-129">This email contains the instructions and information for the user to use the Skype for Business Online Meeting Update Tool to remove audio conferencing specific information, such as the default conference phone number or conference ID.</span></span>

    <span data-ttu-id="5d3db-130">Consulte [Asignar o cancelar licencias para Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="5d3db-130">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

    <span data-ttu-id="5d3db-131">A continuación tiene un ejemplo de este correo electrónico:</span><span class="sxs-lookup"><span data-stu-id="5d3db-131">Here is an example of this email:</span></span>

     ![Las conferencias de acceso telefónico local están desactivadas.](media/teams-emails-sent-to-users-when-settings-change-image4.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a><span data-ttu-id="5d3db-133">Realizar cambios en los mensajes de correo electrónico que se les envían</span><span class="sxs-lookup"><span data-stu-id="5d3db-133">Make changes to the email messages that are sent to them</span></span>

<span data-ttu-id="5d3db-134">Puede realizar cambios en el correo electrónico que se envía de forma automática a los usuarios, incluidos la dirección de correo electrónico y el nombre para mostrar que se incluye en la información de contacto del *remitente*.</span><span class="sxs-lookup"><span data-stu-id="5d3db-134">You can make changes to the email that is automatically sent to users including the email address and the display name that is included in the *From* contact information.</span></span> <span data-ttu-id="5d3db-135">De manera predeterminada, el remitente de los mensajes será de Office 365, pero puede cambiar la dirección de correo electrónico y el nombre para mostrar con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5d3db-135">By default, the sender of the emails will be from Office 365, but you can change the email address and display name using Windows PowerShell.</span></span> <span data-ttu-id="5d3db-136">Vea la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="5d3db-136">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a><span data-ttu-id="5d3db-137">¿Qué sucede si no desea que se les envíen correos electrónicos?</span><span class="sxs-lookup"><span data-stu-id="5d3db-137">What if you don't want email to be sent to them?</span></span>

<span data-ttu-id="5d3db-138">Cuando se deshabilita el envío de correos electrónicos a los usuarios, estos no se enviarán en ningún momento, ni tan siquiera cuando se asigne una licencia a un usuario.</span><span class="sxs-lookup"><span data-stu-id="5d3db-138">When you disable sending emails to users, email won't be sent even when a user gets assigned a license.</span></span> <span data-ttu-id="5d3db-139">En este caso, no se enviaría al usuario el Id. de conferencia, el número de teléfono de conferencia predeterminado ni, lo más importante, el PIN de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="5d3db-139">In this case, the conference ID, default conferencing phone number, and, more importantly, their audio conferencing PIN won't be sent to the user.</span></span> <span data-ttu-id="5d3db-140">Cuando esto suceda, debe informar al usuario mediante un correo electrónico por separado o llamándole.</span><span class="sxs-lookup"><span data-stu-id="5d3db-140">When this happens, you must tell the user by sending them a separate email or by calling them.</span></span>

<span data-ttu-id="5d3db-141">De manera predeterminada, los correos electrónicos se envían a los usuarios, pero, si quiere evitar que reciban correos electrónicos para el uso de audioconferencias, puede usar Microsoft Teams o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5d3db-141">By default, emails will be sent to your users, but if you want to prevent them from receiving email for audio conferencing, you can use Microsoft Teams or Windows PowerShell.</span></span> 

<span data-ttu-id="5d3db-142">![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) **desde el centro de administración de equipos de Microsoft**</span><span class="sxs-lookup"><span data-stu-id="5d3db-142">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="5d3db-143">En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="5d3db-143">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="5d3db-144">En la parte superior de la página **Puentes de conferencia**, haga clic en **Configuración de puente**.</span><span class="sxs-lookup"><span data-stu-id="5d3db-144">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="5d3db-145">En el panel **Configuración de puente**, habilite o deshabilite **Enviar automáticamente correos electrónicos a los usuarios si se produce algún cambio en la configuración del acceso telefónico local**.</span><span class="sxs-lookup"><span data-stu-id="5d3db-145">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="5d3db-146">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="5d3db-146">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="5d3db-147">**Uso de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="5d3db-147">**Using Windows PowerShell**</span></span>

<span data-ttu-id="5d3db-148">Vea la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="5d3db-148">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="5d3db-149">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="5d3db-149">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="5d3db-150">De manera predeterminada, el remitente de los mensajes será de Office 365, pero puede cambiar la dirección de correo electrónico y el nombre para mostrar con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5d3db-150">By default, the sender of the emails will be from Office 365, but you can change the email address and display name using Windows PowerShell.</span></span> 

<span data-ttu-id="5d3db-p109">Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="5d3db-p109">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="5d3db-154">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="5d3db-154">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [<span data-ttu-id="5d3db-155">Las mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5d3db-155">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

<span data-ttu-id="5d3db-156">Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="5d3db-156">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="related-topics"></a><span data-ttu-id="5d3db-157">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="5d3db-157">Related topics</span></span>

[<span data-ttu-id="5d3db-158">Habilitar o deshabilitar el envío de correos electrónicos cuando cambie la configuración de Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="5d3db-158">Enable or disable sending emails when Audio Conferencing settings change</span></span>](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)

[<span data-ttu-id="5d3db-159">Enviar un correo electrónico a un usuario con su información de conferencias de Audio</span><span class="sxs-lookup"><span data-stu-id="5d3db-159">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
