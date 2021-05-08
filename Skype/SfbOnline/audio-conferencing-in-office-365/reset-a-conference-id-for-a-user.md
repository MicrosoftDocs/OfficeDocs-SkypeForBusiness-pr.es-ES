---
title: Restablecer un id. de conferencia para un usuario en Skype Empresarial Online
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Obtenga información sobre los pasos para restablecer el id. de conferencia de reunión de un usuario en Skype Empresarial Online y obtenga vínculos a herramientas de actualización y migración de reuniones. '
ms.openlocfilehash: 24037de3849ae54920777636e7eb745671ae2f57
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237776"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a><span data-ttu-id="e3570-103">Restablecer un id. de conferencia para un usuario en Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="e3570-103">Reset a conference ID for a user in Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]
> <span data-ttu-id="e3570-104">Para obtener información sobre cómo restablecer el id. de conferencia en Microsoft Teams, vea Restablecer un [id.](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams)de conferencia para un usuario en Microsoft Teams .</span><span class="sxs-lookup"><span data-stu-id="e3570-104">For information about resetting conference ID in Microsoft Teams, see [Reset a conference ID for a user in Microsoft Teams](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams).</span></span>

<span data-ttu-id="e3570-105">Se incluye un id. de conferencia dinámico en la parte inferior de las invitaciones de reunión junto con los números de teléfono de acceso telefónico que pueden usar las personas que llaman para llamar a una reunión.</span><span class="sxs-lookup"><span data-stu-id="e3570-105">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="e3570-106">Cuando el usuario marca el número de teléfono, el operador automático de la reunión le pedirá al autor de la llamada que escriba este id. de conferencia para que pueda asistir a la reunión.</span><span class="sxs-lookup"><span data-stu-id="e3570-106">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e3570-107">Si su proveedor de conferencias es Microsoft, los IDs de conferencia de los usuarios se establecen en Solo dinámico.</span><span class="sxs-lookup"><span data-stu-id="e3570-107">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only.</span></span> <span data-ttu-id="e3570-108">Esto no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="e3570-108">This cannot be changed.</span></span> <span data-ttu-id="e3570-109">Los IDs de conferencia se establecen automáticamente solo para los Skype Empresarial habilitados para audioconferencias.</span><span class="sxs-lookup"><span data-stu-id="e3570-109">Conference IDs are automatically set only for Skype for Business users enabled for Audio Conferencing.</span></span> 

## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="e3570-110">Restablecer el id. de conferencia de un usuario</span><span class="sxs-lookup"><span data-stu-id="e3570-110">Resetting the conference ID for a user</span></span>
   
1. <span data-ttu-id="e3570-111">En el Skype Empresarial de administración, **haga** clic en **Usuarios** de audioconferencia, seleccione un usuario y, a continuación, en el panel Acción en  >   **Id.** de conferencia, haga clic en **Restablecer**.</span><span class="sxs-lookup"><span data-stu-id="e3570-111">In the **Skype for Business admin center**, click **Audio conferencing** > **Users**, select a user, and then in the Action pane under **Conference ID** click **Reset**.</span></span>
    
2. <span data-ttu-id="e3570-112">En la ventana **Restablecer Id. de conferencia?**, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="e3570-112">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="e3570-113">Se creará automáticamente un id. de conferencia y se enviará un correo electrónico al usuario con el nuevo id. de conferencia.</span><span class="sxs-lookup"><span data-stu-id="e3570-113">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="e3570-114">De forma predeterminada, los correos electrónicos se envían a los usuarios, pero esto se puede desactivar.</span><span class="sxs-lookup"><span data-stu-id="e3570-114">By default, emails are sent to users, but this can be turned off.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e3570-115">Después de restablecer el id. de conferencia, se enviará al usuario un correo electrónico con el nuevo id. de conferencia.</span><span class="sxs-lookup"><span data-stu-id="e3570-115">After you reset the conference ID, an email with the new conference ID will be sent to the user.</span></span> <span data-ttu-id="e3570-116">Este correo electrónico se enviará a la dirección de correo electrónico principal, en muchos casos, su Microsoft 365 o Office 365 buzón.</span><span class="sxs-lookup"><span data-stu-id="e3570-116">This email will be sent to the primary email address, in many cases, their Microsoft 365 or Office 365 mailbox.</span></span> <span data-ttu-id="e3570-117">El correo electrónico contiene el nuevo id. de conferencia, los números de teléfono de acceso telefónico de acceso telefónico predeterminados e instrucciones para usar la herramienta de actualización de reuniones Skype Empresarial actualizar las reuniones existentes.</span><span class="sxs-lookup"><span data-stu-id="e3570-117">The email contains the new conference ID, default dial-in phone number(s) and instructions to use the Skype for Business Meeting Update Tool to update existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="e3570-118">¿Qué más debo saber?</span><span class="sxs-lookup"><span data-stu-id="e3570-118">What else should I know?</span></span>

- <span data-ttu-id="e3570-119">Puede enviar toda la información de conferencia al usuario en un correo electrónico que incluya  el id. de conferencia y los números de teléfono de acceso telefónico local haciendo clic en Enviar información de conferencia por correo electrónico para el usuario en el panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="e3570-119">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info via email** for the user in the Action pane.</span></span> <span data-ttu-id="e3570-120">No envía el PIN.</span><span class="sxs-lookup"><span data-stu-id="e3570-120">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="e3570-121">Un id. de conferencia contendrá 7 dígitos y no puede cambiar su longitud en el centro de administración de Skype Empresarial o mediante Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e3570-121">A conference ID will contain 7 digits, and you can't change its length in the Skype for Business admin center or by using Windows PowerShell.</span></span>
    
- <span data-ttu-id="e3570-122">Una vez que se ha restablecido el nuevo id. de conferencia, podrá verlo en **Id. de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="e3570-122">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="e3570-123">El id. de conferencia de un usuario para conferencias de audioconferencia se puede ver en la parte inferior del panel de acciones en **Audioconferencia** al seleccionar el usuario en la **página** Usuarios.</span><span class="sxs-lookup"><span data-stu-id="e3570-123">The conference ID for a user for audio conferencing can be viewed at the bottom of the Action pane under **Audio conferencing** when you select the user on the **Users** page.</span></span>
    
- <span data-ttu-id="e3570-124">After a new conference ID is created, the old conference ID can't be used by callers.</span><span class="sxs-lookup"><span data-stu-id="e3570-124">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="e3570-125">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="e3570-125">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="e3570-126">Los usuarios pueden usar Skype Empresarial de reunión para actualizar sus reuniones existentes.</span><span class="sxs-lookup"><span data-stu-id="e3570-126">The users can use Skype for Business Meeting Tool to update their existing meetings.</span></span> <span data-ttu-id="e3570-127">Para ver cómo descargar, instalar y ejecutar la Skype Empresarial actualización de reuniones, vea:</span><span class="sxs-lookup"><span data-stu-id="e3570-127">To see how to download, install, and run the Skype for Business Meeting Update Tool, see:</span></span>
    
  - [<span data-ttu-id="e3570-128">Herramienta de actualización de reuniones para Skype y Lync</span><span class="sxs-lookup"><span data-stu-id="e3570-128">Meeting Update Tool for Skype for Business and Lync</span></span>](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [<span data-ttu-id="e3570-129">Skype Empresarial Online, herramienta de migración de reuniones (64 bits)</span><span class="sxs-lookup"><span data-stu-id="e3570-129">Skype for Business Online, Meeting Migration Tool (64-bit)</span></span>](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [<span data-ttu-id="e3570-130">Skype Empresarial Online, herramienta de migración de reuniones (32 bits)</span><span class="sxs-lookup"><span data-stu-id="e3570-130">Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>](https://www.microsoft.com/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="e3570-131">¿Desea saber cómo administrar con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="e3570-131">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="e3570-132">En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios.</span><span class="sxs-lookup"><span data-stu-id="e3570-132">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="e3570-133">Con Windows PowerShell, puede administrar Microsoft 365 o Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario, cuando tiene varias tareas que hacer.</span><span class="sxs-lookup"><span data-stu-id="e3570-133">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="e3570-134">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="e3570-134">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="e3570-135">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="e3570-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="e3570-136">¿Por qué necesita usar Microsoft 365 o Office 365 PowerShell?</span><span class="sxs-lookup"><span data-stu-id="e3570-136">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
 
- <span data-ttu-id="e3570-137">Windows PowerShell tiene muchas ventajas en velocidad, simplicidad y productividad en comparación con el uso del centro de administración de Microsoft 365, por ejemplo, cuando realiza cambios de configuración para muchos usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="e3570-137">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="e3570-138">Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="e3570-138">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="e3570-139">[Las mejores formas de administrar Microsoft 365 o Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="e3570-139">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="e3570-140">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="e3570-140">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="e3570-141">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="e3570-141">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="e3570-142">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="e3570-142">Related topics</span></span>

[<span data-ttu-id="e3570-143">Restablecer el PIN de Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="e3570-143">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin.md)
