---
title: Restablecer un identificador de conferencia para un usuario en Microsoft Teams
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
description: 'Obtenga información sobre los pasos para restablecer un usuario reunión de identificador de conferencia en Microsoft Teams y get contiene vínculos a las herramientas de actualización y migración de la reunión. '
ms.openlocfilehash: 4e338e5ad00792a48e0a6c9e0791c0c5e4b759ac
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887855"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a><span data-ttu-id="51971-103">Restablecer un identificador de conferencia para un usuario en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="51971-103">Reset a conference ID for a user in Microsoft Teams</span></span>

<span data-ttu-id="51971-104">Un identificador de conferencia dinámico se incluye en la parte inferior de las invitaciones junto con los números de teléfono de acceso telefónico que pueden usarse por los autores de llamadas a llama a una reunión de la reunión.</span><span class="sxs-lookup"><span data-stu-id="51971-104">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="51971-105">Cuando el usuario marca el número de teléfono, el operador automático de la reunión le preguntará el autor de la llamada para escribir este identificador de conferencia, por lo que pueden asistir a la reunión.</span><span class="sxs-lookup"><span data-stu-id="51971-105">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="51971-106">Si su proveedor de conferencia es Microsoft, los identificadores de conferencia de los usuarios se establecen en dinámico sólo de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="51971-106">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only by default.</span></span> <span data-ttu-id="51971-107">Lamentablemente, no hay ninguna capacidad para cambiarlo de manera que se convierten en estáticos, ya que esta es ahora no compatible.</span><span class="sxs-lookup"><span data-stu-id="51971-107">Unfortunately, there's no ability to change it to become static, as this is now unsupported.</span></span> <span data-ttu-id="51971-108">ID de conferencia se establece automáticamente solo para los usuarios de Microsoft Teams habilitados para conferencias de Audio.</span><span class="sxs-lookup"><span data-stu-id="51971-108">Conference IDs are only automatically set for Microsoft Teams users enabled for Audio Conferencing.</span></span> 


## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="51971-109">Restablecer el identificador de conferencia para un usuario</span><span class="sxs-lookup"><span data-stu-id="51971-109">Resetting the conference ID for a user</span></span>

1. <span data-ttu-id="51971-110">En el panel de navegación izquierdo, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="51971-110">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="51971-111">En la parte superior de la página, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="51971-111">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="51971-112">En las **Conferencias de Audio** , haga clic en **Restablecer el identificador de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="51971-112">Under **Audio Conferencing** click **Reset conference ID**.</span></span>

2. <span data-ttu-id="51971-113">En la ventana **Restablecer Id. de conferencia** , haga clic en **Restablecer**.</span><span class="sxs-lookup"><span data-stu-id="51971-113">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="51971-114">Una conferencia que se creará automáticamente el identificador y un correo electrónico enviado al usuario con el nuevo identificador de conferencia.</span><span class="sxs-lookup"><span data-stu-id="51971-114">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="51971-115">De forma predeterminada, se envían mensajes de correo electrónico a los usuarios, pero esto se puede desactivar.</span><span class="sxs-lookup"><span data-stu-id="51971-115">By default, emails are sent to users, but this can be turned off.</span></span>   

    
> [!NOTE]
> <span data-ttu-id="51971-116">Después de restablecer el identificador de conferencia, se enviará un correo electrónico con el nuevo identificador de conferencia al usuario.</span><span class="sxs-lookup"><span data-stu-id="51971-116">After you reset the conference ID, an email with the new conference ID will be sent to the user.</span></span> <span data-ttu-id="51971-117">Este correo electrónico se enviarán a la dirección de correo electrónico principal, en muchos casos, su buzón de Office 365.</span><span class="sxs-lookup"><span data-stu-id="51971-117">This email will be sent to the primary email address, in many cases, their Office 365 mailbox.</span></span> <span data-ttu-id="51971-118">El correo electrónico contiene el nuevo identificador de conferencia, números de teléfono de acceso telefónico predeterminada e instrucciones para la actualización de reuniones existentes.</span><span class="sxs-lookup"><span data-stu-id="51971-118">The email contains the new conference ID, default dial-in phone number(s) and instructions for updating existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="51971-119">¿Qué más debo saber?</span><span class="sxs-lookup"><span data-stu-id="51971-119">What else should I know?</span></span>

- <span data-ttu-id="51971-120">Puede enviar toda la información de conferencia para el usuario en un correo electrónico que incluye el identificador de conferencia y los números de teléfono de acceso telefónico, haga clic en **Enviar información de conferencia en el correo electrónico** para el usuario en la sección de **Conferencias de Audio** .</span><span class="sxs-lookup"><span data-stu-id="51971-120">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info in email** for the user in the **Audio Conferencing** section.</span></span> <span data-ttu-id="51971-121">No envía el PIN.</span><span class="sxs-lookup"><span data-stu-id="51971-121">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="51971-122">Un identificador de conferencia va a contener 7 dígitos, y no se puede cambiar su longitud.</span><span class="sxs-lookup"><span data-stu-id="51971-122">A conference ID will contain 7 digits, and you can't change its length.</span></span>
    
- <span data-ttu-id="51971-123">Una vez que se ha restablecido el nuevo id. de conferencia, podrá verlo en **Id. de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="51971-123">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="51971-124">After a new conference ID is created, the old conference ID can't be used by callers.</span><span class="sxs-lookup"><span data-stu-id="51971-124">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="51971-125">Debe notificar a los usuarios para que reprogramen sus invitaciones de reunión existentes para asegurarse de que se agrega a las invitaciones el nuevo Id. de conferencia.</span><span class="sxs-lookup"><span data-stu-id="51971-125">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="51971-126">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="51971-126">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="51971-p107">Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="51971-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="51971-130">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="51971-130">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="51971-131">Las mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="51971-131">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="51971-132">Para obtener más información acerca de Windows PowerShell, vea la [referencia de PowerShell de los equipos de Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="51971-132">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="51971-133">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="51971-133">Related topics</span></span>

[<span data-ttu-id="51971-134">Restablecer el PIN de conferencia de Audio</span><span class="sxs-lookup"><span data-stu-id="51971-134">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin-in-teams.md)
