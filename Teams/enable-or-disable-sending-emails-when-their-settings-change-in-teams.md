---
title: Opciones de correo electrónico cuando cambia la configuración de conferencias de audio
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
description: 'Obtenga información sobre cómo habilitar o deshabilitar Skype para que no envíe correos electrónicos a los usuarios cuando la configuración, como los cambios de anclar o el número de conferencia predeterminado, cambie en Microsoft Teams. '
ms.openlocfilehash: e1bb6df0a443f01ed3c9bc70d03eedc05f217ce4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092708"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a><span data-ttu-id="edbc6-103">Habilitar o deshabilitar el envío de correos electrónicos cuando cambie la configuración de Audioconferencia en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="edbc6-103">Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams</span></span>

<span data-ttu-id="edbc6-104">Los usuarios se notifican automáticamente por correo electrónico cuando están habilitados para las audioconferencias.</span><span class="sxs-lookup"><span data-stu-id="edbc6-104">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="edbc6-105">Sin embargo, puede haber ocasiones en las que quiera reducir el número de correos electrónicos que se envían a los usuarios de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="edbc6-105">There may be times, however, when you want to reduce the number of emails that are sent to Microsoft Teams users.</span></span> <span data-ttu-id="edbc6-106">En estos casos, puede deshabilitar el envío de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="edbc6-106">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="edbc6-107">Si deshabilita el envío de correos electrónicos, los correos electrónicos de audioconferencia no se enviarán a los usuarios, incluidos los correos electrónicos para cuando los usuarios estén habilitados o deshabilitados para las audioconferencias, cuando se restablezca su PIN y cuando cambie el id. de conferencia y el número de teléfono de conferencia predeterminado.</span><span class="sxs-lookup"><span data-stu-id="edbc6-107">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="edbc6-108">Este es un ejemplo del correo electrónico que se envía a los usuarios cuando están habilitados para las audioconferencias:</span><span class="sxs-lookup"><span data-stu-id="edbc6-108">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![Ejemplo de un mensaje de correo electrónico de audioconferencia](media/teams-emails-sent-to-users-when-settings-change-image1.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="edbc6-110">¿Cuándo se envían correos electrónicos a los usuarios?</span><span class="sxs-lookup"><span data-stu-id="edbc6-110">When are emails being sent to your users?</span></span>

- <span data-ttu-id="edbc6-111">Hay varios correos electrónicos que se envían a los usuarios de su organización después de que estén habilitados para las audioconferencias:</span><span class="sxs-lookup"><span data-stu-id="edbc6-111">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="edbc6-112">Cuando se les asigna una licencia **de** audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="edbc6-112">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="edbc6-113">Cuando restablezca manualmente el PIN de audioconferencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="edbc6-113">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="edbc6-114">Al restablecer de forma manual el id. de conferencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="edbc6-114">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="edbc6-115">Cuando se **quita la licencia de conferencias** de audio.</span><span class="sxs-lookup"><span data-stu-id="edbc6-115">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="edbc6-116">Cuando el proveedor de audioconferencias de un usuario se cambia de Microsoft a otro proveedor o **Ninguno.**</span><span class="sxs-lookup"><span data-stu-id="edbc6-116">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="edbc6-117">Cuando el proveedor de audioconferencias de un usuario se cambia a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="edbc6-117">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="edbc6-118">Habilitar o deshabilitar el correo electrónico para que no se envíe a los usuarios</span><span class="sxs-lookup"><span data-stu-id="edbc6-118">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="edbc6-119">Puede usar Microsoft Teams o Windows PowerShell para habilitar o deshabilitar el correo electrónico enviado a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="edbc6-119">You can use Microsoft Teams or Windows PowerShell to enable or disable email sent to users.</span></span>

<span data-ttu-id="edbc6-120">![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Centro de administración de Microsoft Teams en uso**</span><span class="sxs-lookup"><span data-stu-id="edbc6-120">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="edbc6-121">En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="edbc6-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="edbc6-122">En la parte superior de la **página Puentes de** conferencia, haga clic en **Configuración de puente.**</span><span class="sxs-lookup"><span data-stu-id="edbc6-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="edbc6-123">En el **panel Configuración de puente,** habilite o deshabilite Enviar mensajes de correo electrónico automáticamente a los usuarios si cambia la configuración **de acceso telefónico.**</span><span class="sxs-lookup"><span data-stu-id="edbc6-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="edbc6-124">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="edbc6-124">Click **Save**.</span></span>

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="edbc6-125">Vea **Enviar un correo electrónico a un usuario con su información de conferencias de Audio**.</span><span class="sxs-lookup"><span data-stu-id="edbc6-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="edbc6-126">Vea la [referencia de PowerShell de Microsoft Teams](/powershell/module/teams/?view=teams-ps) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="edbc6-126">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>

    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="edbc6-127">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="edbc6-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="edbc6-128">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="edbc6-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="edbc6-129">Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 con un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas que hacer.</span><span class="sxs-lookup"><span data-stu-id="edbc6-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="edbc6-130">To get started with Windows PowerShell, see these topics:</span><span class="sxs-lookup"><span data-stu-id="edbc6-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="edbc6-131">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="edbc6-131">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="edbc6-132">[Las mejores formas de administrar Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="edbc6-132">[Best ways to manage Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="edbc6-133">Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="edbc6-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="edbc6-134">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="edbc6-134">Related topics</span></span>

[<span data-ttu-id="edbc6-135">Correos electrónicos enviados a los usuarios cuando cambian sus opciones de audioconferencia</span><span class="sxs-lookup"><span data-stu-id="edbc6-135">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change-in-teams.md)

[<span data-ttu-id="edbc6-136">Enviar un correo electrónico a un usuario con su información de conferencias de Audio</span><span class="sxs-lookup"><span data-stu-id="edbc6-136">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)