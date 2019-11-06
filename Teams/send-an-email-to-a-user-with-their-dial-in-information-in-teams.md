---
title: Enviar un correo electrónico a un usuario con su información de audioconferencia en Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords: None
ms.custom:
- Audio Conferencing
description: Envíe a sus usuarios un correo electrónico con la información de sus audioconferencias en Microsoft Teams.
ms.openlocfilehash: 9e4508f3907de35ee2752077ac22b5cd8a5e5735
ms.sourcegitcommit: 15fe483079847d24869e325eead35f252da8c7dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2019
ms.locfileid: "37571320"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-microsoft-teams"></a><span data-ttu-id="f783f-103">Enviar un correo electrónico a un usuario con su información de audioconferencia en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f783f-103">Send an email to a user with their Audio Conferencing information in Microsoft Teams</span></span>

<span data-ttu-id="f783f-104">A veces, puede que los usuarios de Microsoft Teams necesiten que les envíe su información sobre la audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="f783f-104">Sometimes Microsoft Teams users may need you to send them their Audio Conferencing information.</span></span> <span data-ttu-id="f783f-105">Para ello, haga clic en **Enviar información de conferencia por correo electrónico** en las propiedades de un usuario.</span><span class="sxs-lookup"><span data-stu-id="f783f-105">You can do this by clicking **Send conference info via email** under the properties for a user.</span></span> <span data-ttu-id="f783f-106">Cuando se envíe este correo electrónico, este contendrá toda la información de la audioconferencia, incluido lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f783f-106">When you send this email, it will contain all of the audio conferencing information, including:</span></span>
  
- <span data-ttu-id="f783f-107">El número de teléfono de la conferencia o el número de teléfono de acceso telefónico local del usuario</span><span class="sxs-lookup"><span data-stu-id="f783f-107">The conference phone or dial-in phone number for the user.</span></span>
    
- <span data-ttu-id="f783f-108">El Id. de conferencia del usuario</span><span class="sxs-lookup"><span data-stu-id="f783f-108">The user's conference ID.</span></span>
    
   
<span data-ttu-id="f783f-109">A continuación se muestra un ejemplo del correo electrónico que se envía:</span><span class="sxs-lookup"><span data-stu-id="f783f-109">Here is an example of the email that is sent:</span></span>
  
![Ejemplo de un mensaje de correo de conferencia de acceso telefónico local](media/teams-send-email-to-user-with-audio-conferencing-image1.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="f783f-111">Enviar un correo electrónico con la información de audioconferencia a un usuario</span><span class="sxs-lookup"><span data-stu-id="f783f-111">Send an email with audio conferencing information to a user</span></span>

### <a name="an-icon-showing-the-microsoft-teams-logomediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) <span data-ttu-id="f783f-113">Usar el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f783f-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="f783f-114">En el navegación de la izquierda, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="f783f-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="f783f-115">En la parte superior de la página, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="f783f-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="f783f-116">En **Conferencia de audio**, haga clic en **enviar información de conferencia por correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="f783f-116">Under **Audio Conferencing**, click **Send conference info in email**.</span></span>


## <a name="what-else-should-you-know-about-this-email"></a><span data-ttu-id="f783f-117">¿Qué más debe saber sobre este correo electrónico?</span><span class="sxs-lookup"><span data-stu-id="f783f-117">What else should you know about this email?</span></span>

- <span data-ttu-id="f783f-118">Se envían varios correos electrónicos a los usuarios de su organización después de que estén habilitados para las conferencias de audio:</span><span class="sxs-lookup"><span data-stu-id="f783f-118">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="f783f-119">Cuando se les asigna una licencia de **conferencias de audio** .</span><span class="sxs-lookup"><span data-stu-id="f783f-119">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="f783f-120">Cuando restablece manualmente el PIN de conferencia de audio del usuario.</span><span class="sxs-lookup"><span data-stu-id="f783f-120">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="f783f-121">Al restablecer de forma manual el id. de conferencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="f783f-121">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="f783f-122">Cuando se quita una licencia de **conferencias de audio** de ellos.</span><span class="sxs-lookup"><span data-stu-id="f783f-122">When an **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="f783f-123">Cuando el proveedor de servicios de audioconferencia de un usuario cambia de Microsoft a otro proveedor o a **ninguno**.</span><span class="sxs-lookup"><span data-stu-id="f783f-123">When the audio conferencing provider for a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="f783f-124">Cuando se cambia el proveedor de servicios de audioconferencia de un usuario a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f783f-124">When the audio conferencing provider for a user is changed to Microsoft.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="f783f-125">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="f783f-125">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="f783f-p102">Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="f783f-p102">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="f783f-129">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="f783f-129">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="f783f-130">Las mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f783f-130">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="f783f-131">Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="f783f-131">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="f783f-132">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="f783f-132">Related topics</span></span>

[<span data-ttu-id="f783f-133">Probar o comprar Audioconferencia en Office 365</span><span class="sxs-lookup"><span data-stu-id="f783f-133">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
