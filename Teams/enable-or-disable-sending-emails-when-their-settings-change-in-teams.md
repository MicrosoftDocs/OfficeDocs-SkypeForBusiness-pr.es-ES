---
title: Habilitar o deshabilitar el envío de los correos electrónicos al cambia configuración de conferencia de Audio en Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Obtenga información sobre cómo habilitar o deshabilitar Skype de envío de mensajes de correo electrónico a los usuarios cuando cambie la configuración como pin o los cambios de número de conferencia de forma predeterminada en Microsoft Teams. '
ms.openlocfilehash: 5d18d039c379bb56a861ba6f6a36d23f301150b4
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23861894"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a><span data-ttu-id="33f36-103">Habilitar o deshabilitar el envío de los correos electrónicos al cambia configuración de conferencia de Audio en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="33f36-103">Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams</span></span>

<span data-ttu-id="33f36-104">Cuando están habilitados para conferencias de Audio, se notificación automáticamente a los usuarios por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="33f36-104">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="33f36-105">Puede haber ocasiones, sin embargo, cuando desea reducir el número de mensajes de correo electrónico que se envían a los usuarios de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="33f36-105">There may be times, however, when you want to reduce the number of emails that are sent to Microsoft Teams users.</span></span> <span data-ttu-id="33f36-106">En estos casos, puede deshabilitar el envío de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="33f36-106">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="33f36-107">Si se deshabilitación el envío de los correos electrónicos, mensajes de correo electrónico de conferencia de Audio no se enviará a los usuarios, incluidos los correos electrónicos para cuando los usuarios se habilitan o deshabilitan para conferencias de audio, cuando se restablezca su NIP y cuando el identificador de conferencia y la conferencia predeterminado cambios del número de teléfono .</span><span class="sxs-lookup"><span data-stu-id="33f36-107">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="33f36-108">Este es un ejemplo del correo electrónico que se envía a los usuarios cuando están habilitados para conferencias de Audio:</span><span class="sxs-lookup"><span data-stu-id="33f36-108">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![Correo electrónico de conferencia audio](media/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="33f36-110">¿Cuándo se envían correos electrónicos a los usuarios?</span><span class="sxs-lookup"><span data-stu-id="33f36-110">When are emails being sent to your users?</span></span>

- <span data-ttu-id="33f36-111">Hay varios correos electrónicos que se envían a los usuarios de su organización después de que están habilitados para conferencias de audio:</span><span class="sxs-lookup"><span data-stu-id="33f36-111">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="33f36-112">Cuando se asigna una licencia de **Conferencias de Audio** a ellos.</span><span class="sxs-lookup"><span data-stu-id="33f36-112">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="33f36-113">Al restablecer manualmente PIN de conferencia de audio del usuario.</span><span class="sxs-lookup"><span data-stu-id="33f36-113">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="33f36-114">Al restablecer de forma manual el id. de conferencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="33f36-114">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="33f36-115">Cuando la licencia de **Conferencias de Audio** se quita de ellos.</span><span class="sxs-lookup"><span data-stu-id="33f36-115">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="33f36-116">Cuando se cambia el proveedor de conferencia de audio de un usuario de Microsoft a otro proveedor o **Ninguno**.</span><span class="sxs-lookup"><span data-stu-id="33f36-116">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="33f36-117">Cuando se cambia el proveedor de conferencia de audio de un usuario a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="33f36-117">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="33f36-118">Habilitar o deshabilitar el correo electrónico no se envía a los usuarios</span><span class="sxs-lookup"><span data-stu-id="33f36-118">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="33f36-119">Puede usar Microsoft Teams o Windows PowerShell para habilitar o deshabilitar el correo electrónico enviado a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="33f36-119">You can use Microsoft Teams or Windows PowerShell to enable or disable email sent to users.</span></span>

<span data-ttu-id="33f36-120">![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="33f36-120">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>
1. <span data-ttu-id="33f36-121">En el panel de navegación izquierdo, vaya a **las reuniones** > **Puentes de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="33f36-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="33f36-122">En la parte superior de la página de **Puentes de conferencia** , haga clic en **configuración de puente**.</span><span class="sxs-lookup"><span data-stu-id="33f36-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="33f36-123">En el panel **configuración de puente** , habilitar o deshabilitar **Enviar automáticamente mensajes de correo electrónico a los usuarios si cambia su configuración de acceso telefónico**.</span><span class="sxs-lookup"><span data-stu-id="33f36-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="33f36-124">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="33f36-124">Click **Save**.</span></span>

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="33f36-125">**Vea **Enviar un correo electrónico a un usuario con su información de conferencias de Audio**.**</span><span class="sxs-lookup"><span data-stu-id="33f36-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="33f36-126">Vea la [referencia de PowerShell de los equipos de Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="33f36-126">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="33f36-127">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="33f36-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="33f36-p102">Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="33f36-p102">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="33f36-131">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="33f36-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="33f36-132">Las mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="33f36-132">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="33f36-133">Para obtener más información acerca de Windows PowerShell, vea la [referencia de PowerShell de los equipos de Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="33f36-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="33f36-134">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="33f36-134">Related topics</span></span>

[<span data-ttu-id="33f36-135">Correos electrónicos enviados a los usuarios cuando cambie su configuración de conferencias de Audio</span><span class="sxs-lookup"><span data-stu-id="33f36-135">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change-in-teams.md)

[<span data-ttu-id="33f36-136">Enviar un correo electrónico a un usuario con su información de conferencias de Audio</span><span class="sxs-lookup"><span data-stu-id="33f36-136">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)


