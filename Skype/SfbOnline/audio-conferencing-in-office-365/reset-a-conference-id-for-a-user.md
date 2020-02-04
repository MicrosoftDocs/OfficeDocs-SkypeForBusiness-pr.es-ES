---
title: Restablecer un identificador de conferencia para un usuario en Skype empresarial online
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
description: 'Obtenga información sobre los pasos para restablecer el identificador de conferencia de un usuario en Skype empresarial online y obtenga vínculos a herramientas de actualización y de migración de reuniones. '
ms.openlocfilehash: c87db0972fb8144d7a8a807de81905f5be23191c
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41707155"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a><span data-ttu-id="16abe-103">Restablecer un identificador de conferencia para un usuario en Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="16abe-103">Reset a conference ID for a user in Skype for Business Online</span></span>

> [!NOTE]
> <span data-ttu-id="16abe-104">Para obtener información sobre cómo restablecer la identificación de conferencia en Microsoft Teams, consulte [restablecer un ID de conferencia para un usuario en Microsoft Teams](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams).</span><span class="sxs-lookup"><span data-stu-id="16abe-104">For information about resetting conference ID in Microsoft Teams, see [Reset a conference ID for a user in Microsoft Teams](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams).</span></span>

<span data-ttu-id="16abe-105">En la parte inferior de las invitaciones a reuniones se incluye un identificador de conferencia dinámico junto con los números de teléfono de acceso telefónico local que las personas que llaman pueden usar para llamar a una reunión.</span><span class="sxs-lookup"><span data-stu-id="16abe-105">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="16abe-106">Cuando el usuario marca el número de teléfono, el operador automático para la reunión le pedirá a la persona que lo llame para que pueda asistir a la reunión.</span><span class="sxs-lookup"><span data-stu-id="16abe-106">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="16abe-107">Si su proveedor de servicios de conferencia es Microsoft, los identificadores de conferencia de los usuarios se establecen en dinámicos únicamente.</span><span class="sxs-lookup"><span data-stu-id="16abe-107">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only.</span></span> <span data-ttu-id="16abe-108">Esto no se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="16abe-108">This cannot be changed.</span></span> <span data-ttu-id="16abe-109">Los identificadores de conferencia se establecen automáticamente para los usuarios de Skype empresarial habilitados para conferencias de audio.</span><span class="sxs-lookup"><span data-stu-id="16abe-109">Conference IDs are automatically set only for Skype for Business users enabled for Audio Conferencing.</span></span> 

## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="16abe-110">Restablecer el identificador de conferencia de un usuario</span><span class="sxs-lookup"><span data-stu-id="16abe-110">Resetting the conference ID for a user</span></span>
   
1. <span data-ttu-id="16abe-111">En el **centro de administración de Skype empresarial**, haga clic en**usuarios**de **Conferencia** > de audio, seleccione un usuario y, a continuación, en el panel de acciones, en ID de **Conferencia** , haga clic en **restablecer**.</span><span class="sxs-lookup"><span data-stu-id="16abe-111">In the **Skype for Business admin center**, click **Audio conferencing** > **Users**, select a user, and then in the Action pane under **Conference ID** click **Reset**.</span></span>
    
2. <span data-ttu-id="16abe-112">En la ventana **Restablecer Id. de conferencia?**, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="16abe-112">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="16abe-113">Se creará automáticamente un ID de conferencia y un mensaje de correo electrónico con el nuevo identificador de conferencia.</span><span class="sxs-lookup"><span data-stu-id="16abe-113">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="16abe-114">De forma predeterminada, los correos electrónicos se envían a los usuarios, pero esto se puede desactivar.</span><span class="sxs-lookup"><span data-stu-id="16abe-114">By default, emails are sent to users, but this can be turned off.</span></span>
    
> [!NOTE]
> <span data-ttu-id="16abe-p104">Después de restablecer el Id. de conferencia, se enviará al usuario un correo electrónico con el nuevo Id. de conferencia. Este mensaje de correo electrónico se enviará a la dirección de correo electrónico principal, en muchos casos, su buzón de correo de Office 365. El correo electrónico contiene el nuevo Id. de conferencia, los números de teléfono de acceso telefónico local predeterminados y las instrucciones para usar la herramienta de actualización de reuniones de Skype Empresarial para actualizar las reuniones existentes.</span><span class="sxs-lookup"><span data-stu-id="16abe-p104">After you reset the conference ID, an email with the new conference ID will be sent to the user. This email will be sent to the primary email address, in many cases, their Office 365 mailbox. The email contains the new conference ID, default dial-in phone number(s) and instructions to use the Skype for Business Meeting Update Tool to update existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="16abe-118">¿Qué más debo saber?</span><span class="sxs-lookup"><span data-stu-id="16abe-118">What else should I know?</span></span>

- <span data-ttu-id="16abe-119">Puede enviar toda la información de la Conferencia al usuario en un correo electrónico que incluya el identificador de la Conferencia y los números de teléfono de acceso telefónico local haciendo clic en **enviar información de conferencia por correo electrónico** para el usuario en el panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="16abe-119">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info via email** for the user in the Action pane.</span></span> <span data-ttu-id="16abe-120">No envía el PIN.</span><span class="sxs-lookup"><span data-stu-id="16abe-120">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="16abe-121">Un identificador de conferencia contendrá 7 dígitos y no podrá cambiar su longitud en el centro de administración de Skype empresarial o mediante Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="16abe-121">A conference ID will contain 7 digits, and you can't change its length in the Skype for Business admin center or by using Windows PowerShell.</span></span>
    
- <span data-ttu-id="16abe-122">Una vez que se ha restablecido el nuevo id. de conferencia, podrá verlo en **Id. de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="16abe-122">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="16abe-123">El identificador de conferencia de un usuario para las conferencias de audio puede verse en la parte inferior del panel de acciones, en **audioconferencias** , cuando selecciona el usuario en la página **usuarios** .</span><span class="sxs-lookup"><span data-stu-id="16abe-123">The conference ID for a user for audio conferencing can be viewed at the bottom of the Action pane under **Audio conferencing** when you select the user on the **Users** page.</span></span>
    
- <span data-ttu-id="16abe-124">After a new conference ID is created, the old conference ID can't be used by callers.</span><span class="sxs-lookup"><span data-stu-id="16abe-124">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="16abe-125">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="16abe-125">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="16abe-126">Los usuarios pueden usar la herramienta de reunión de Skype empresarial para actualizar las reuniones existentes.</span><span class="sxs-lookup"><span data-stu-id="16abe-126">The users can use Skype for Business Meeting Tool to update their existing meetings.</span></span> <span data-ttu-id="16abe-127">Para obtener información sobre cómo descargar, instalar y ejecutar la herramienta de actualización de reuniones de Skype empresarial, consulte:</span><span class="sxs-lookup"><span data-stu-id="16abe-127">To see how to download, install, and run the Skype for Business Meeting Update Tool, see:</span></span>
    
  - [<span data-ttu-id="16abe-128">Herramienta de actualización de reuniones para Skype y Lync</span><span class="sxs-lookup"><span data-stu-id="16abe-128">Meeting Update Tool for Skype for Business and Lync</span></span>](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [<span data-ttu-id="16abe-129">Skype Empresarial Online, herramienta de migración de reuniones (64 bits)</span><span class="sxs-lookup"><span data-stu-id="16abe-129">Skype for Business Online, Meeting Migration Tool (64-bit)</span></span>](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [<span data-ttu-id="16abe-130">Skype Empresarial Online, herramienta de migración de reuniones (32 bits)</span><span class="sxs-lookup"><span data-stu-id="16abe-130">Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="16abe-131">¿Desea saber cómo administrar con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="16abe-131">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="16abe-p107">En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="16abe-p107">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="16abe-135">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="16abe-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="16abe-136">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="16abe-136">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="16abe-137">Windows PowerShell tiene muchas ventajas en cuanto a velocidad, simplicidad y productividad en lugar de usar únicamente el centro de administración de Microsoft 365, como cuando se hacen los cambios de configuración para muchos usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="16abe-137">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="16abe-138">Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="16abe-138">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="16abe-139">Mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="16abe-139">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="16abe-140">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="16abe-140">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="16abe-141">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="16abe-141">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="16abe-142">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="16abe-142">Related topics</span></span>

[<span data-ttu-id="16abe-143">Restablecer el PIN de Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="16abe-143">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin.md)
