---
title: Restablecer un Id. de conferencia para un usuario en Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
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
description: Conozca cuáles son los pasos que hay que seguir para restablecer el Id. de conferencia de reunión de un usuario en Microsoft Teams, y obtenga los vínculos para las herramientas de migración y actualización de reuniones.
ms.openlocfilehash: 008a479677723dedbfe1923f57358808b16fd9ec
ms.sourcegitcommit: 09ff11f8e4f6a93cedc34a5d732a133163df79a0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "44042457"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a><span data-ttu-id="d01bd-103">Restablecer un Id. de conferencia para un usuario en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d01bd-103">Reset a conference ID for a user in Microsoft Teams</span></span>

<span data-ttu-id="d01bd-104">Al final de las invitaciones de reunión se incluye un Id. de conferencia dinámico junto con los números de teléfono de acceso telefónico local que pueden usar los autores de llamada para llamar a una reunión.</span><span class="sxs-lookup"><span data-stu-id="d01bd-104">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="d01bd-105">Cuando el usuario marque el número de teléfono, el operador automático de la reunión le pedirá al autor de la llamada que introduzca este Id. de conferencia para que pueda asistir a la reunión.</span><span class="sxs-lookup"><span data-stu-id="d01bd-105">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d01bd-106">Si el proveedor de servicios de conferencia es Microsoft, los Id. de conferencia de los usuarios se establecen en Dynamic Only (Solo dinámico) de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d01bd-106">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only by default.</span></span> <span data-ttu-id="d01bd-107">Lamentablemente, no existe ninguna forma de cambiarlo de nuevo a estático, no es compatible todavía.</span><span class="sxs-lookup"><span data-stu-id="d01bd-107">Unfortunately, there's no ability to change it to become static, as this is now unsupported.</span></span> <span data-ttu-id="d01bd-108">Los Id. de conferencia solo se establecen automáticamente para los usuarios de Microsoft Teams que tengan habilitada la Audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="d01bd-108">Conference IDs are only automatically set for Microsoft Teams users enabled for Audio Conferencing.</span></span> 


## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="d01bd-109">Restablecer el Id. de conferencia para un usuario</span><span class="sxs-lookup"><span data-stu-id="d01bd-109">Resetting the conference ID for a user</span></span>

<span data-ttu-id="d01bd-110">![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="d01bd-110">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="d01bd-111">En el navegación de la izquierda, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="d01bd-111">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="d01bd-112">Haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="d01bd-112">Click **Edit**.</span></span>

3. <span data-ttu-id="d01bd-113">En **Conferencia de audio** , haga clic en **restablecer ID de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="d01bd-113">Under **Audio Conferencing** click **Reset conference ID**.</span></span>

2. <span data-ttu-id="d01bd-114">En la ventana **restablecer ID de conferencia** , haga clic en **restablecer**.</span><span class="sxs-lookup"><span data-stu-id="d01bd-114">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="d01bd-115">Se creará automáticamente un ID de conferencia y un mensaje de correo electrónico con el nuevo identificador de conferencia.</span><span class="sxs-lookup"><span data-stu-id="d01bd-115">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="d01bd-116">De forma predeterminada, los correos electrónicos se envían a los usuarios, pero esto se puede desactivar.</span><span class="sxs-lookup"><span data-stu-id="d01bd-116">By default, emails are sent to users, but this can be turned off.</span></span>   

    
> [!NOTE]
> <span data-ttu-id="d01bd-117">Después de restablecer el identificador de conferencia, se enviará al usuario un mensaje de correo electrónico con la nueva identificación de conferencia.</span><span class="sxs-lookup"><span data-stu-id="d01bd-117">After you reset the conference ID, an email with the new conference ID will be sent to the user.</span></span> <span data-ttu-id="d01bd-118">Este mensaje de correo electrónico se enviará a la dirección de correo electrónico principal, en muchos casos, el buzón de Office 365.</span><span class="sxs-lookup"><span data-stu-id="d01bd-118">This email will be sent to the primary email address, in many cases, their Office 365 mailbox.</span></span> <span data-ttu-id="d01bd-119">El correo electrónico contiene el nuevo identificador de conferencia, los números de teléfono de acceso telefónico (s) predeterminados y las instrucciones para actualizar las reuniones existentes.</span><span class="sxs-lookup"><span data-stu-id="d01bd-119">The email contains the new conference ID, default dial-in phone number(s) and instructions for updating existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="d01bd-120">¿Qué más debo saber?</span><span class="sxs-lookup"><span data-stu-id="d01bd-120">What else should I know?</span></span>

- <span data-ttu-id="d01bd-121">Puede enviar toda la información de la Conferencia al usuario en un correo electrónico que incluya el identificador de la Conferencia y los números de teléfono de acceso telefónico local haciendo clic en **enviar información de conferencia por correo electrónico** para el usuario en la sección **audioconferencia** .</span><span class="sxs-lookup"><span data-stu-id="d01bd-121">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info in email** for the user in the **Audio Conferencing** section.</span></span> <span data-ttu-id="d01bd-122">No envía el PIN.</span><span class="sxs-lookup"><span data-stu-id="d01bd-122">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="d01bd-123">Un identificador de conferencia contendrá 8 dígitos y no se puede cambiar su longitud.</span><span class="sxs-lookup"><span data-stu-id="d01bd-123">A conference ID will contain 8 digits, and you can't change its length.</span></span>
    
- <span data-ttu-id="d01bd-124">Una vez que se ha restablecido el nuevo id. de conferencia, podrá verlo en **Id. de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="d01bd-124">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="d01bd-125">After a new conference ID is created, the old conference ID can't be used by callers.</span><span class="sxs-lookup"><span data-stu-id="d01bd-125">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="d01bd-126">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="d01bd-126">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="d01bd-127">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="d01bd-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="d01bd-p107">Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="d01bd-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="d01bd-131">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="d01bd-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="d01bd-132">Las mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d01bd-132">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="d01bd-133">Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="d01bd-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="d01bd-134">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="d01bd-134">Related topics</span></span>

[<span data-ttu-id="d01bd-135">Restablecer el PIN de Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="d01bd-135">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin-in-teams.md)
