---
title: Establecer los números de teléfono incluidos en las invitaciones en Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
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
description: 'Vea los pasos que hay que seguir para crear un número de teléfono predeterminado con el que los autores de llamada puedan unirse a una reunión de Microsoft Teams. '
ms.openlocfilehash: eddab0762b679dba08dd9981d6ae61a1403ebf47
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882963"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a><span data-ttu-id="47179-103">Establecer los números de teléfono incluidos en las invitaciones en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="47179-103">Set the phone numbers included on invites</span></span>

<span data-ttu-id="47179-104">Con Audioconferencia de Office 365, los usuarios de su organización pueden crear reuniones de Microsoft Teams y permitir que los usuarios accedan por teléfono a la reunión con un teléfono.</span><span class="sxs-lookup"><span data-stu-id="47179-104">Audio Conferencing in Office 365 enables users in your organization to create Microsoft Teams meetings, and then allow users to dial in to those meetings using a phone.</span></span> <span data-ttu-id="47179-105">En Office 365, tiene la opción de usar un puente de audioconferencia de Microsoft o usar un puente de audioconferencia de terceros que esté hospedado por un proveedor de servicios de audioconferencia (ACP) aprobado.</span><span class="sxs-lookup"><span data-stu-id="47179-105">In Office 365, you have the option of using a Microsoft dial-in conferencing bridge or to use a third-party audio conferencing bridge that is hosted by an approved audio conferencing provider (ACP).</span></span>
  
<span data-ttu-id="47179-106">Un puente de conferencia ofrece un conjunto de números de teléfono de acceso telefónico local para su organización.</span><span class="sxs-lookup"><span data-stu-id="47179-106">A conferencing bridge gives you a set of dial-in phone numbers for your organization.</span></span> <span data-ttu-id="47179-107">Todos ellos se pueden usar para unirse a las reuniones que cree un organizador de reuniones, pero puede seleccionar cuáles se incluirán en las invitaciones.</span><span class="sxs-lookup"><span data-stu-id="47179-107">All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="47179-108">En la invitación para un organizador de reuniones, puede haber un máximo de un número de teléfono de pago y uno gratuito, aunque también habrá un vínculo situado en la parte inferior de cada invitación con el que se abre una lista de números de teléfono de acceso telefónico local que se pueden usar para unirse a una reunión.</span><span class="sxs-lookup"><span data-stu-id="47179-108">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a><span data-ttu-id="47179-109">Establecer o cambiar el número de teléfono de audioconferencia predeterminado para un usuario o un organizar de reunión</span><span class="sxs-lookup"><span data-stu-id="47179-109">Set or change the default audio conferencing phone number for a meeting organizer or user</span></span>

1. <span data-ttu-id="47179-110">En el panel de navegación izquierdo, haga clic en **Usuarios** y seleccione el usuario en la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="47179-110">In the left navigation of the **Office 365 admin center, go to UsersActive users**, and then select the user or users from the list of available users.</span></span>

    ![Muestra la selección de Usuarios en el Centro de administración de Skype Empresarial y Microsoft Teams](media/teamsselectusers.png)

2. <span data-ttu-id="47179-112">En la parte superior de la página, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="47179-112">At the top of the Conference Bridges page, click Bridge Settings.</span></span>

    ![Haga clic en Editar en el Centro de administración de Skype Empresarial y Microsoft Teams](media/teamsedituser.png)

3. <span data-ttu-id="47179-114">Junto a **Audioconferencia**, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="47179-114">Next to **Audio Conferencing**, click **Edit**.</span></span> 
    
    ![Haga clic en Editar junto a Audioconferencia](media/teamseditaudioconf.png)

4. <span data-ttu-id="47179-116">Use los campos **Número de pago** o **Número gratuito** para introducir los números para el usuario.</span><span class="sxs-lookup"><span data-stu-id="47179-116">Use the **Toll number** or **Toll-free number** fields to enter the numbers for the user.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="47179-117">Cuando se cambia la configuración de audioconferencias de un usuario, también se tienen que actualizar las reuniones periódicas y futuras de Microsoft Teams y enviarlas a los asistentes.</span><span class="sxs-lookup"><span data-stu-id="47179-117">When you change a user's audio conferencing settings, recurring and future Microsoft Teams meetings must be updated and sent to attendees.</span></span> 

## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="47179-118">¿Quiere usar Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="47179-118">Want to use Windows PowerShell?</span></span>

<span data-ttu-id="47179-p103">Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="47179-p103">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="47179-122">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="47179-122">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="47179-123">Las mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="47179-123">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="47179-124">Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="47179-124">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span> 
  
    
## <a name="related-topics"></a><span data-ttu-id="47179-125">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="47179-125">Related topics</span></span>

[<span data-ttu-id="47179-126">Probar o comprar Audioconferencia en Office 365</span><span class="sxs-lookup"><span data-stu-id="47179-126">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
