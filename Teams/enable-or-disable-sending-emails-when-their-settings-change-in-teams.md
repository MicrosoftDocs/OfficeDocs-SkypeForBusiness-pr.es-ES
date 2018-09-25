---
title: Habilitar o deshabilitar el envío de correos electrónicos cuando cambie la configuración de Audioconferencia en Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
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
description: 'Aprenda a habilitar o deshabilitar a Skype para enviar correos electrónicos a los usuarios cuando cambien opciones de configuración, como el PIN, o cambie el número de conferencia predeterminado en Microsoft Teams. '
ms.openlocfilehash: 2c082410f7acf000473e001f46587025edd6e9c7
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "25015544"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a><span data-ttu-id="bc87c-103">Habilitar o deshabilitar el envío de correos electrónicos cuando cambie la configuración de Audioconferencia en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bc87c-103">Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams</span></span>

<span data-ttu-id="bc87c-104">Cuando están habilitados para conferencias de Audio, se notificación automáticamente a los usuarios por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="bc87c-104">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="bc87c-105">Puede haber ocasiones, sin embargo, cuando desea reducir el número de mensajes de correo electrónico que se envían a los usuarios de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bc87c-105">There may be times, however, when you want to reduce the number of emails that are sent to Microsoft Teams users.</span></span> <span data-ttu-id="bc87c-106">En estos casos, puede deshabilitar el envío de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="bc87c-106">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="bc87c-107">Si deshabilita el envío de correos electrónicos, no se enviará ningún correo de Audioconferencia a los usuarios, incluidos los correos electrónicos para cuando se habilite o deshabilite a los usuarios para participar en audioconferencias, cuando se restablezca su código PIN o cuando cambie el Id. de conferencia y el número de teléfono de conferencia predeterminado.</span><span class="sxs-lookup"><span data-stu-id="bc87c-107">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="bc87c-108">A continuación se muestra un ejemplo del correo electrónico que se envía a los usuarios cuando se les habilita para Audioconferencia:</span><span class="sxs-lookup"><span data-stu-id="bc87c-108">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![Correo electrónico de Audioconferencia](media/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="bc87c-110">¿Cuándo se envían correos electrónicos a los usuarios?</span><span class="sxs-lookup"><span data-stu-id="bc87c-110">When are emails being sent to your users?</span></span>

- <span data-ttu-id="bc87c-111">Existen diversos correos electrónicos que se envían a los usuarios de su organización una vez que se han habilitado para la audioconferencia:</span><span class="sxs-lookup"><span data-stu-id="bc87c-111">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="bc87c-112">Cuando se les asigna una licencia de **Audioconferencia**.</span><span class="sxs-lookup"><span data-stu-id="bc87c-112">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="bc87c-113">Al restablecer de forma manual el PIN de audioconferencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="bc87c-113">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="bc87c-114">Al restablecer de forma manual el Id. de conferencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="bc87c-114">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="bc87c-115">Cuando se elimina la licencia de **Audioconferencia** para el usuario.</span><span class="sxs-lookup"><span data-stu-id="bc87c-115">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="bc87c-116">Cuando el proveedor de servicios de audioconferencia de un usuario se cambia de Microsoft a otro proveedor o a **Ninguno**.</span><span class="sxs-lookup"><span data-stu-id="bc87c-116">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="bc87c-117">Cuando el proveedor de servicios de audioconferencia de un usuario se cambia a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bc87c-117">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="bc87c-118">Habilitar o deshabilitar que el correo electrónico se envíe a los usuarios</span><span class="sxs-lookup"><span data-stu-id="bc87c-118">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="bc87c-119">Para habilitar o deshabilitar el envío de correos electrónicos a los usuarios se utiliza Microsoft Teams o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bc87c-119">You can use Microsoft Teams or Windows PowerShell to enable or disable email sent to users.</span></span>

<span data-ttu-id="bc87c-120">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Mediante el Centro de administración de Skype for Business y Microsoft Teams:**</span><span class="sxs-lookup"><span data-stu-id="bc87c-120">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>
1. <span data-ttu-id="bc87c-121">En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="bc87c-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="bc87c-122">En la parte superior de la página **Puentes de conferencia**, haga clic en **Configuración de puente**.</span><span class="sxs-lookup"><span data-stu-id="bc87c-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="bc87c-123">En el panel **Configuración de puente**, habilite o deshabilite **Enviar automáticamente correos electrónicos a los usuarios si se produce algún cambio en la configuración del acceso telefónico local**.</span><span class="sxs-lookup"><span data-stu-id="bc87c-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="bc87c-124">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="bc87c-124">Click **Save**.</span></span>

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="bc87c-125">**Uso de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="bc87c-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="bc87c-126">Vea la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="bc87c-126">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="bc87c-127">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="bc87c-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="bc87c-p102">Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="bc87c-p102">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="bc87c-131">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="bc87c-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="bc87c-132">Las mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bc87c-132">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="bc87c-133">Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="bc87c-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="bc87c-134">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="bc87c-134">Related topics</span></span>

[<span data-ttu-id="bc87c-135">Correos electrónicos que se envían a los usuarios cuando cambia la configuración de Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="bc87c-135">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change-in-teams.md)

[<span data-ttu-id="bc87c-136">Enviar un correo electrónico a un usuario con su información de conferencias de Audio</span><span class="sxs-lookup"><span data-stu-id="bc87c-136">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)


