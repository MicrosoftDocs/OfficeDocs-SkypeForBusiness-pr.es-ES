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
ms.openlocfilehash: 52b547fee5bf027bcef21914e3ba3aa79b0e4e08
ms.sourcegitcommit: 7a9c63ee790108eaa61950ce28ae8027311039d9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662130"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a><span data-ttu-id="34f91-103">Restablecer un Id. de conferencia para un usuario en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="34f91-103">Reset a conference ID for a user in Microsoft Teams</span></span>

<span data-ttu-id="34f91-104">Al final de las invitaciones de reunión se incluye un Id. de conferencia dinámico junto con los números de teléfono de acceso telefónico local que pueden usar los autores de llamada para llamar a una reunión.</span><span class="sxs-lookup"><span data-stu-id="34f91-104">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="34f91-105">Cuando el usuario marque el número de teléfono, el operador automático de la reunión le pedirá al autor de la llamada que introduzca este Id. de conferencia para que pueda asistir a la reunión.</span><span class="sxs-lookup"><span data-stu-id="34f91-105">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="34f91-106">Los identificadores de conferencia se generan automáticamente, estarán entre 7-9 dígitos y se establecen al habilitar audioconferencias para un usuario.</span><span class="sxs-lookup"><span data-stu-id="34f91-106">Conference IDs are generated automatically, will be between 7-9 digits, and are set when you enable Audio Conferencing for a user.</span></span> <span data-ttu-id="34f91-107">**No se admiten identificadores de conferencia estáticos.**</span><span class="sxs-lookup"><span data-stu-id="34f91-107">**Static conference IDs aren't supported.**</span></span> 

## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="34f91-108">Restablecer el identificador de conferencia de un usuario</span><span class="sxs-lookup"><span data-stu-id="34f91-108">Resetting the conference ID for a user</span></span>

<span data-ttu-id="34f91-109">![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="34f91-109">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="34f91-110">En el panel de navegación izquierdo, haga clic en **Usuarios** y seleccione el usuario en la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="34f91-110">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="34f91-111">Haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="34f91-111">Click **Edit**.</span></span>

3. <span data-ttu-id="34f91-112">En **Audioconferencia**, haga clic en **Restablecer Id. de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="34f91-112">Under **Audio Conferencing** click **Reset conference ID**.</span></span>

2. <span data-ttu-id="34f91-113">En la ventana **Restablecer Id. de conferencia**, haga clic en **Restablecer**.</span><span class="sxs-lookup"><span data-stu-id="34f91-113">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="34f91-114">El Id. de conferencia se creará automáticamente y se enviará un correo electrónico al usuario con el Id. de conferencia nuevo.</span><span class="sxs-lookup"><span data-stu-id="34f91-114">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="34f91-115">Los correos electrónicos se envían a los usuarios de forma predeterminada, aunque esto también se puede desactivar.</span><span class="sxs-lookup"><span data-stu-id="34f91-115">By default, emails are sent to users, but this can be turned off.</span></span>   

    
> [!NOTE]
> <span data-ttu-id="34f91-116">Después de restablecer el Id. de conferencia, se enviará un correo electrónico al usuario con el nuevo Id. de conferencia.</span><span class="sxs-lookup"><span data-stu-id="34f91-116">After you reset the conference ID, an email with the new conference ID will be sent to the user.</span></span> <span data-ttu-id="34f91-117">Este mensaje de correo electrónico se enviará a la dirección de correo electrónico principal, en muchos casos, en el buzón de Microsoft 365 o de Office 365.</span><span class="sxs-lookup"><span data-stu-id="34f91-117">This email will be sent to the primary email address, in many cases, their Microsoft 365 or Office 365 mailbox.</span></span> <span data-ttu-id="34f91-118">El correo electrónico contiene el nuevo Id. de conferencia, los números de teléfono de acceso telefónico local predeterminados y las instrucciones para actualizar las reuniones existentes.</span><span class="sxs-lookup"><span data-stu-id="34f91-118">The email contains the new conference ID, default dial-in phone number(s) and instructions for updating existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="34f91-119">¿Qué más debo saber?</span><span class="sxs-lookup"><span data-stu-id="34f91-119">What else should I know?</span></span>

- <span data-ttu-id="34f91-120">Puede enviar toda la información de la conferencia al usuario en un correo electrónico que incluya el Id. de conferencia y los números de teléfono de acceso telefónico local haciendo clic en **Enviar información de conferencia a través del correo electrónico** para el usuario en la sección **Audioconferencia**.</span><span class="sxs-lookup"><span data-stu-id="34f91-120">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info in email** for the user in the **Audio Conferencing** section.</span></span> <span data-ttu-id="34f91-121">De esta forma no se envía el PIN.</span><span class="sxs-lookup"><span data-stu-id="34f91-121">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="34f91-122">El servicio de Teams crea un identificador de conferencia de 7-9 dígitos.</span><span class="sxs-lookup"><span data-stu-id="34f91-122">A 7- 9 digit conference ID is created by the Teams service.</span></span> <span data-ttu-id="34f91-123">No se puede cambiar su longitud.</span><span class="sxs-lookup"><span data-stu-id="34f91-123">You can't change its length.</span></span>
    
- <span data-ttu-id="34f91-124">Una vez que se ha restablecido el nuevo id. de conferencia, podrá verlo en **Id. de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="34f91-124">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="34f91-125">After a new conference ID is created, the old conference ID can't be used by callers.</span><span class="sxs-lookup"><span data-stu-id="34f91-125">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="34f91-126">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="34f91-126">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="34f91-127">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="34f91-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="34f91-128">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="34f91-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="34f91-129">Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 con un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas para hacer.</span><span class="sxs-lookup"><span data-stu-id="34f91-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="34f91-130">To get started with Windows PowerShell, see these topics:</span><span class="sxs-lookup"><span data-stu-id="34f91-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="34f91-131">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="34f91-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="34f91-132">Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="34f91-132">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="34f91-133">Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="34f91-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="34f91-134">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="34f91-134">Related topics</span></span>

[<span data-ttu-id="34f91-135">Restablecer el PIN de Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="34f91-135">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin-in-teams.md)
