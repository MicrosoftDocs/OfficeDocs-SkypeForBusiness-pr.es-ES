---
title: Restablecer un Id. de conferencia para un usuario en Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Conozca cuáles son los pasos que hay que seguir para restablecer el Id. de conferencia de reunión de un usuario en Microsoft Teams, y obtenga los vínculos para las herramientas de migración y actualización de reuniones. '
ms.openlocfilehash: 4e338e5ad00792a48e0a6c9e0791c0c5e4b759ac
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887855"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a><span data-ttu-id="d18a7-103">Restablecer un Id. de conferencia para un usuario en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d18a7-103">Reset a conference ID for a user</span></span>

<span data-ttu-id="d18a7-104">Al final de las invitaciones de reunión se incluye un Id. de conferencia dinámico junto con los números de teléfono de acceso telefónico local que pueden usar los autores de llamada para llamar a una reunión.</span><span class="sxs-lookup"><span data-stu-id="d18a7-104">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="d18a7-105">Cuando el usuario marque el número de teléfono, el operador automático de la reunión le pedirá al autor de la llamada que introduzca este Id. de conferencia para que pueda asistir a la reunión.</span><span class="sxs-lookup"><span data-stu-id="d18a7-105">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d18a7-106">Si el proveedor de servicios de conferencia es Microsoft, los Id. de conferencia de los usuarios se establecen en Dynamic Only (Solo dinámico) de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d18a7-106">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only by default.</span></span> <span data-ttu-id="d18a7-107">Lamentablemente, no existe ninguna forma de cambiarlo de nuevo a estático, no es compatible todavía.</span><span class="sxs-lookup"><span data-stu-id="d18a7-107">Unfortunately, there's no ability to change it to become static, as this is now unsupported.</span></span> <span data-ttu-id="d18a7-108">Los Id. de conferencia solo se establecen automáticamente para los usuarios de Microsoft Teams que tengan habilitada la Audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="d18a7-108">Conference IDs are only automatically set for Microsoft Teams users enabled for Audio Conferencing.</span></span> 


## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="d18a7-109">Restablecer el Id. de conferencia para un usuario</span><span class="sxs-lookup"><span data-stu-id="d18a7-109">Resetting the meeting conference ID for a user</span></span>

1. <span data-ttu-id="d18a7-110">En el panel de navegación izquierdo, haga clic en **Usuarios** y seleccione el usuario en la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="d18a7-110">In the left navigation of the **Office 365 admin center, go to UsersActive users**, and then select the user or users from the list of available users.</span></span>

2. <span data-ttu-id="d18a7-111">En la parte superior de la página, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="d18a7-111">At the top of the Conference Bridges page, click Bridge Settings.</span></span>

3. <span data-ttu-id="d18a7-112">En **Audioconferencia**, haga clic en **Restablecer Id. de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="d18a7-112">Under **Audio Conferencing** click **Reset conference ID**.</span></span>

2. <span data-ttu-id="d18a7-113">En la ventana **Restablecer Id. de conferencia**, haga clic en **Restablecer**.</span><span class="sxs-lookup"><span data-stu-id="d18a7-113">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="d18a7-114">El Id. de conferencia se creará automáticamente y se enviará un correo electrónico al usuario con el Id. de conferencia nuevo.</span><span class="sxs-lookup"><span data-stu-id="d18a7-114">In the Reset conference ID? window, click Yes. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.</span></span> <span data-ttu-id="d18a7-115">Los correos electrónicos se envían a los usuarios de forma predeterminada, aunque esto también se puede desactivar.</span><span class="sxs-lookup"><span data-stu-id="d18a7-115">By default, emails are sent to users, but this can be turned off.</span></span>   

    
> [!NOTE]
> <span data-ttu-id="d18a7-116">Después de restablecer el Id. de conferencia, se enviará un correo electrónico al usuario con el nuevo Id. de conferencia.</span><span class="sxs-lookup"><span data-stu-id="d18a7-116">After you reset the conference ID, an email with the new conference ID will be sent to the user.</span></span> <span data-ttu-id="d18a7-117">Este correo se enviará a la dirección de correo principal que, en muchos casos, será el buzón de Office 365.</span><span class="sxs-lookup"><span data-stu-id="d18a7-117">This email will be sent to the primary email address, in many cases, their Office 365 mailbox.</span></span> <span data-ttu-id="d18a7-118">El correo electrónico contiene el nuevo Id. de conferencia, los números de teléfono de acceso telefónico local predeterminados y las instrucciones para actualizar las reuniones existentes.</span><span class="sxs-lookup"><span data-stu-id="d18a7-118">The email contains the new conference ID, default dial-in phone number(s) and instructions for updating existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="d18a7-119">¿Qué más debo saber?</span><span class="sxs-lookup"><span data-stu-id="d18a7-119">What else should I know?</span></span>

- <span data-ttu-id="d18a7-120">Puede enviar toda la información de la conferencia al usuario en un correo electrónico que incluya el Id. de conferencia y los números de teléfono de acceso telefónico local haciendo clic en **Enviar información de conferencia a través del correo electrónico** para el usuario en la sección **Audioconferencia**.</span><span class="sxs-lookup"><span data-stu-id="d18a7-120">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking the **Send conference info via email**. It doesn't send the PIN.</span></span> <span data-ttu-id="d18a7-121">De esta forma no se envía el PIN.</span><span class="sxs-lookup"><span data-stu-id="d18a7-121">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="d18a7-122">El Id. de conferencia contendrá siete dígitos y su longitud no se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="d18a7-122">A conference ID will contain 7 digits and you can't change it's length in either the Skype for Business admin center or using Windows PowerShell.</span></span>
    
- <span data-ttu-id="d18a7-123">Una vez que se haya restablecido, podrá ver el Id. de conferencia nuevo en la lista de **Id. de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="d18a7-123">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="d18a7-124">Una vez que se haya creado el Id. de conferencia nuevo, los autores de llamada no podrán usar el anterior.</span><span class="sxs-lookup"><span data-stu-id="d18a7-124">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="d18a7-125">Tendrá que notificar a los usuarios que deben volver a programar las invitaciones de reunión que ya tienen y comprobar que se haya añadido el nuevo Id. de conferencia a las invitaciones.</span><span class="sxs-lookup"><span data-stu-id="d18a7-125">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="d18a7-126">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="d18a7-126">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="d18a7-p107">Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="d18a7-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="d18a7-130">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="d18a7-130">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="d18a7-131">Las mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d18a7-131">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="d18a7-132">Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="d18a7-132">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="d18a7-133">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="d18a7-133">Related topics</span></span>

<span data-ttu-id="d18a7-134">[Restablecer el PIN de Audioconferencia](reset-the-audio-conferencing-pin-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="d18a7-134">[](reset-the-audio-conferencing-pin-in-teams.md)Reset the Audio Conferencing PIN for a user</span></span>
