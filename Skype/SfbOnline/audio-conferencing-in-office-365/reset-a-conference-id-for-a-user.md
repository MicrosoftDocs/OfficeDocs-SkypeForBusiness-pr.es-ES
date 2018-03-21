---
title: Restablecer un id. de conferencia para un usuario
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn the steps to reset a user''s meeting conference ID, and get links to meeting update and migration tools. '
ms.openlocfilehash: 2a5ab1adf9335b2bc5c219975aff11c9e54292fa
ms.sourcegitcommit: 997c03395fd1966607cef0df8ee884303401cd64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2018
---
# <a name="reset-a-conference-id-for-a-user"></a><span data-ttu-id="bd3d1-103">Restablecer un id. de conferencia para un usuario</span><span class="sxs-lookup"><span data-stu-id="bd3d1-103">Reset a conference ID for a user</span></span>

<span data-ttu-id="bd3d1-104">Cuando las organizaciones todavía no ha habilitado para identificadores de conferencia dinámico, un ID de conferencia estática se crea automáticamente cuando se habilita un Skype para usuarios de negocios o Teams de Microsoft para conferencias de Audio mediante Microsoft como proveedor.</span><span class="sxs-lookup"><span data-stu-id="bd3d1-104">When your organizations hasn't been enabled for dynamic conference IDs, a static conference ID is automatically created when a Skype for Business or Microsoft Teams user is enabled for Audio Conferencing using Microsoft as the provider.</span></span> <span data-ttu-id="bd3d1-105">Este ID de conferencia se incluye en la parte inferior de las invitaciones junto con los números de teléfono de acceso telefónico que pueden utilizarse por los llamadores que llaman a una reunión a reuniones.</span><span class="sxs-lookup"><span data-stu-id="bd3d1-105">This conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="bd3d1-106">Cuando el usuario marca el número de teléfono, el operador automático de la reunión le preguntará el llamador para introducir este ID de conferencia para poder asistir a la reunión.</span><span class="sxs-lookup"><span data-stu-id="bd3d1-106">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bd3d1-107">Si su proveedor de conferencias es Microsoft, identificadores de conferencia de los usuarios se establecen en sólo dinámica predeterminada.</span><span class="sxs-lookup"><span data-stu-id="bd3d1-107">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only by default.</span></span> <span data-ttu-id="bd3d1-108">Por desgracia, no podrá cambiarla en el Skype para el centro de administración de negocio o el uso de Windows Powershell.</span><span class="sxs-lookup"><span data-stu-id="bd3d1-108">Unfortunately, you won't be able to change it in the Skype for Business Admin Center or using Windows Powershell.</span></span> <span data-ttu-id="bd3d1-109">Tendrá que ponerse en contacto con el soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bd3d1-109">You will have to contact Microsoft support.</span></span> 
  
<span data-ttu-id="bd3d1-110">Identificadores estáticos se utilizan cuando las personas de la organización no desean recordar un número aleatorio; Puede seleccionar un determinado número o utilizar uno que sea fácil de recordar.</span><span class="sxs-lookup"><span data-stu-id="bd3d1-110">Static IDs are used when people in your organization don't want to remember a random number; they can select a certain number or use one that's easy to remember.</span></span> <span data-ttu-id="bd3d1-111">Cuando se utilizan identificadores de conferencia dinámico, cada reunión programaciones de un usuario obtener asignará un identificador único conferencia.</span><span class="sxs-lookup"><span data-stu-id="bd3d1-111">When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="bd3d1-112">Si desea asignar el dinámico en lugar de conferencia estática IDs, [vaya aquí](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="bd3d1-112">If you want to assign dynamic rather than static conference IDs, [go here](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span>
  
<span data-ttu-id="bd3d1-113">Identificadores de conferencia sólo se establecen automáticamente sólo para Skype para usuarios de negocios y Teams de Microsoft habilitado para conferencias de Audio mediante Microsoft como su proveedor de conferencia de audio.</span><span class="sxs-lookup"><span data-stu-id="bd3d1-113">Conference IDs are only automatically set only for Skype for Business and Microsoft Teams users enabled for Audio Conferencing using Microsoft as their audio conferencing provider.</span></span> <span data-ttu-id="bd3d1-114">Si necesita restablecer un Id. de conferencia para un usuario que está usando un proveedor de conferencia de audio de terceros (ACP), deberá especificar manualmente un Id. de conferencia en la página de propiedades para el usuario.</span><span class="sxs-lookup"><span data-stu-id="bd3d1-114">If you need to reset a conference ID for a user who is using a third-party audio conferencing provider (ACP), you will need to manually enter a conference ID on the properties page for the user.</span></span>
  
## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="bd3d1-115">Restablecer el Id. de conferencia para un usuario</span><span class="sxs-lookup"><span data-stu-id="bd3d1-115">Resetting the conference ID for a user</span></span>

1. <span data-ttu-id="bd3d1-116">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="bd3d1-116">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="bd3d1-117">Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="bd3d1-117">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="bd3d1-118">En el **Skype para el centro de administración de negocios**, haga clic en **conferencias de Audio** > **usuarios**, seleccione un usuario y, a continuación, en el panel de acción en el **Id. de conferencia** , haga clic en **Restablecer**.</span><span class="sxs-lookup"><span data-stu-id="bd3d1-118">In the **Skype for Business admin center**, click **Audio conferencing** > **Users**, select a user, and then in the Action pane under **Conference ID** click **Reset**.</span></span>
    
4. <span data-ttu-id="bd3d1-119">En el **Restablecer Id. de conferencia?** ventana, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="bd3d1-119">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="bd3d1-120">Una conferencia que se creará automáticamente el ID y el correo electrónico enviado al usuario con el nuevo ID de conferencia.</span><span class="sxs-lookup"><span data-stu-id="bd3d1-120">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="bd3d1-121">De forma predeterminada, se envían mensajes de correo electrónico a los usuarios, pero esto se puede desactivar.</span><span class="sxs-lookup"><span data-stu-id="bd3d1-121">By default, emails are sent to users, but this can be turned off.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bd3d1-p106">Después de restablecer el Id. de conferencia, se enviará al usuario un correo electrónico con el nuevo Id. de conferencia. Este mensaje de correo electrónico se enviará a la dirección de correo electrónico principal, en muchos casos, su buzón de correo de Office 365. El correo electrónico contiene el nuevo Id. de conferencia, los números de teléfono de acceso telefónico local predeterminados y las instrucciones para usar la herramienta de actualización de reuniones de Skype Empresarial para actualizar las reuniones existentes.</span><span class="sxs-lookup"><span data-stu-id="bd3d1-p106">After you reset the conference ID, an email with the new conference ID will be sent to the user. This email will be sent to the primary email address, in many cases, their Office 365 mailbox. The email contains the new conference ID, default dial-in phone number(s) and instructions to use the Skype for Business Meeting Update Tool to update existing meetings.</span></span> 
  
## <a name="what-else-should-i-know"></a><span data-ttu-id="bd3d1-125">¿Qué más debo saber?</span><span class="sxs-lookup"><span data-stu-id="bd3d1-125">What else should I know?</span></span>

- <span data-ttu-id="bd3d1-126">Toda la información de la conferencia puede enviar al usuario en un correo electrónico que incluye el Id. de conferencia y números de teléfono de acceso telefónico, haga clic en **Enviar información de conferencia a través de correo electrónico** para el usuario en el panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="bd3d1-126">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info via email** for the user in the Action pane.</span></span> <span data-ttu-id="bd3d1-127">No envía el PIN.</span><span class="sxs-lookup"><span data-stu-id="bd3d1-127">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="bd3d1-128">Un ID de conferencia contiene 7 dígitos y no puede cambiar su longitud en el Skype para el centro de administración de negocios o mediante Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bd3d1-128">A conference ID will contain 7 digits, and you can't change its length in the Skype for Business admin center or by using Windows PowerShell.</span></span>
    
- <span data-ttu-id="bd3d1-129">Una vez que se ha restablecido el nuevo id. de conferencia, podrá verlo en **Id. de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="bd3d1-129">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="bd3d1-130">El identificador de la conferencia de un usuario para conferencias de audio puede verse en la parte inferior del panel de acciones en **conferencias de Audio** cuando se selecciona el usuario en la página **usuarios** .</span><span class="sxs-lookup"><span data-stu-id="bd3d1-130">The conference ID for a user for audio conferencing can be viewed at the bottom of the Action pane under **Audio conferencing** when you select the user on the **Users** page.</span></span>
    
- <span data-ttu-id="bd3d1-131">After a new conference ID is created, the old conference ID can't be used by callers.</span><span class="sxs-lookup"><span data-stu-id="bd3d1-131">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="bd3d1-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="bd3d1-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="bd3d1-133">Los usuarios pueden utilizar Skype para la herramienta de reuniones de negocios para actualizar sus reuniones existentes.</span><span class="sxs-lookup"><span data-stu-id="bd3d1-133">The users can use Skype for Business Meeting Tool to update their existing meetings.</span></span> <span data-ttu-id="bd3d1-134">Para ver cómo descargar, instalar y ejecutar el Skype para la herramienta de actualización de reunión empresarial, consulte:</span><span class="sxs-lookup"><span data-stu-id="bd3d1-134">To see how to download, install, and run the Skype for Business Meeting Update Tool, see:</span></span>
    
  - [<span data-ttu-id="bd3d1-135">Herramienta de actualización de reuniones para Skype y Lync</span><span class="sxs-lookup"><span data-stu-id="bd3d1-135">Meeting Update Tool for Skype for Business and Lync</span></span>](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [<span data-ttu-id="bd3d1-136">Skype Empresarial Online, herramienta de migración de reuniones (64 bits)</span><span class="sxs-lookup"><span data-stu-id="bd3d1-136">Skype for Business Online, Meeting Migration Tool (64-bit)</span></span>](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [<span data-ttu-id="bd3d1-137">Skype Empresarial Online, herramienta de migración de reuniones (32 bits)</span><span class="sxs-lookup"><span data-stu-id="bd3d1-137">Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="bd3d1-138">¿Desea saber cómo administrar con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="bd3d1-138">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="bd3d1-p109">En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="bd3d1-p109">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="bd3d1-142">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="bd3d1-142">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="bd3d1-143">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="bd3d1-143">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="bd3d1-p110">Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="bd3d1-p110">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="bd3d1-146">Mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bd3d1-146">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="bd3d1-147">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="bd3d1-147">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="bd3d1-148">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="bd3d1-148">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="bd3d1-149">See also</span><span class="sxs-lookup"><span data-stu-id="bd3d1-149">Related topics</span></span>

[<span data-ttu-id="bd3d1-150">Restablecer el PIN de Audioconferencia para un usuario</span><span class="sxs-lookup"><span data-stu-id="bd3d1-150">Reset the Audio Conferencing PIN for a user</span></span>](reset-the-audio-conferencing-pin-for-a-user.md)
