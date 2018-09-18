---
title: Enviar un correo electrónico a un usuario con su información de audioconferencia en Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords: None
ms.custom:
- Audio Conferencing
description: Envíe a sus usuarios un correo electrónico con la información de sus audioconferencias en Microsoft Teams.
ms.openlocfilehash: 85e219481884bb08a2574809b6170c232abccf83
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "23892095"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-microsoft-teams"></a><span data-ttu-id="c5127-103">Enviar un correo electrónico a un usuario con su información de audioconferencia en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c5127-103">Send an email to a user with their Audio Conferencing information</span></span>

<span data-ttu-id="c5127-104">A veces, puede que los usuarios de Microsoft Teams necesiten que les envíe su información sobre la audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="c5127-104">Sometimes users may need you to send them their dial-in conferencing information.</span></span> <span data-ttu-id="c5127-105">Para ello, haga clic en **Enviar información de conferencia por correo electrónico** en las propiedades de un usuario.</span><span class="sxs-lookup"><span data-stu-id="c5127-105">You can do this by using the Skype for Business admin center and clicking **Send conference info via email** under the dial-in properties for a user.</span></span> <span data-ttu-id="c5127-106">Cuando se envíe este correo electrónico, este contendrá toda la información de la audioconferencia, incluido lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c5127-106">When you send this email, it will contain all of the dial-in information including:</span></span>
  
- <span data-ttu-id="c5127-107">El número de teléfono de la conferencia o el número de teléfono de acceso telefónico local del usuario</span><span class="sxs-lookup"><span data-stu-id="c5127-107">The conference phone or dial-in phone number for the user.</span></span>
    
- <span data-ttu-id="c5127-108">El Id. de conferencia del usuario</span><span class="sxs-lookup"><span data-stu-id="c5127-108">The user's conference ID.</span></span>
    
   
<span data-ttu-id="c5127-109">A continuación se muestra un ejemplo del correo electrónico que se envía:</span><span class="sxs-lookup"><span data-stu-id="c5127-109">Here is an example of the email that is sent to users that are enabled for dial-in conferencing:</span></span>
  
![Correo electrónico de conferencia de acceso telefónico local](media/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="c5127-111">Enviar un correo electrónico con la información de audioconferencia a un usuario</span><span class="sxs-lookup"><span data-stu-id="c5127-111">Send an email with Audio Conferencing information to a user</span></span>

1. <span data-ttu-id="c5127-112">En el panel de navegación izquierdo, haga clic en **Usuarios** y seleccione el usuario en la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="c5127-112">In the left navigation of the **Office 365 admin center, go to UsersActive users**, and then select the user or users from the list of available users.</span></span>

2. <span data-ttu-id="c5127-113">En la parte superior de la página, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c5127-113">At the top of the Conference Bridges page, click Bridge Settings.</span></span>

3. <span data-ttu-id="c5127-114">En **Audioconferencia**, haga clic en **Enviar información de conferencia por correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="c5127-114">Under **Audio Conferencing**, click **Send conference info in email**.</span></span>


## <a name="what-else-should-you-know-about-this-email"></a><span data-ttu-id="c5127-115">¿Qué más tiene que saber sobre este correo electrónico?</span><span class="sxs-lookup"><span data-stu-id="c5127-115">What else should you know about this email?</span></span>

- <span data-ttu-id="c5127-116">Existen diversos correos electrónicos que se envían a los usuarios de su organización una vez que se han habilitado para la audioconferencia:</span><span class="sxs-lookup"><span data-stu-id="c5127-116">There are several emails that are sent to users in your organization after they are enabled for dial-in conferencing:</span></span>
    
  - <span data-ttu-id="c5127-117">Cuando se les asigna una licencia de **Audioconferencia**.</span><span class="sxs-lookup"><span data-stu-id="c5127-117">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="c5127-118">Al restablecer de forma manual el PIN de audioconferencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="c5127-118">When you manually reset the user's dial-in conferencing PIN.</span></span>
    
  - <span data-ttu-id="c5127-119">Al restablecer de forma manual el Id. de conferencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="c5127-119">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="c5127-120">Cuando se elimina una licencia de **Audioconferencia** para el usuario.</span><span class="sxs-lookup"><span data-stu-id="c5127-120">When an **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="c5127-121">Cuando el proveedor de servicios de audioconferencia de un usuario se cambia de Microsoft a otro usuario o a **Ninguno**.</span><span class="sxs-lookup"><span data-stu-id="c5127-121">When the dial-in conferencing provider for a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="c5127-122">Cuando el proveedor de servicios de audioconferencia de un usuario se cambia a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c5127-122">When the dial-in conferencing provider for a user is changed to Microsoft.</span></span>
    
- <span data-ttu-id="c5127-123">De manera predeterminada, el remitente de los mensajes de correo electrónico será de Office 365, pero puede cambiar la dirección de correo electrónico y el nombre para mostrar con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c5127-123">By default, the sender of the emails will be from Office 365 but you can change the email address and display name using Windows PowerShell and theSet-CsOnlineDialInConferencingTenantSettings cmdlet.</span></span> <span data-ttu-id="c5127-124">Vea la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="c5127-124">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="c5127-125">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="c5127-125">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="c5127-p103">Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="c5127-p103">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="c5127-129">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="c5127-129">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="c5127-130">Las mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c5127-130">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="c5127-131">Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="c5127-131">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="c5127-132">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="c5127-132">Related topics</span></span>

[<span data-ttu-id="c5127-133">Probar o comprar Audioconferencia en Office 365</span><span class="sxs-lookup"><span data-stu-id="c5127-133">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
