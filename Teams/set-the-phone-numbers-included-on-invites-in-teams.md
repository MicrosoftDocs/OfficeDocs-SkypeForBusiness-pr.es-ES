---
title: Establecer el teléfono los números incluidos en invitaciones en los equipos de Microsoft
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
description: 'Obtener los pasos para crear un número de teléfono predeterminado para los autores de llamadas para unirse a una reunión de los equipos de Microsoft. '
ms.openlocfilehash: eddab0762b679dba08dd9981d6ae61a1403ebf47
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882963"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a><span data-ttu-id="5d8e3-103">Establecer el teléfono los números incluidos en invitaciones en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5d8e3-103">Set the phone numbers included on invites in Microsoft Teams</span></span>

<span data-ttu-id="5d8e3-104">Conferencias de audio en Office 365 permiten a los usuarios de la organización crear reuniones de Microsoft Teams y, a continuación, permitir a los usuarios para conectarse a las reuniones utilizando un teléfono.</span><span class="sxs-lookup"><span data-stu-id="5d8e3-104">Audio Conferencing in Office 365 enables users in your organization to create Microsoft Teams meetings, and then allow users to dial in to those meetings using a phone.</span></span> <span data-ttu-id="5d8e3-105">En Office 365, tendrá la opción de utilizar un puente de conferencia de audio de Microsoft o un puente de conferencia de audio de terceros que está hospedado en un proveedor de conferencias de audio aprobadas (ACP).</span><span class="sxs-lookup"><span data-stu-id="5d8e3-105">In Office 365, you have the option of using a Microsoft audio conferencing bridge or a third-party audio conferencing bridge that is hosted by an approved audio conferencing provider (ACP).</span></span>
  
<span data-ttu-id="5d8e3-106">Un puente de conferencia le proporciona un conjunto de números de teléfono de acceso telefónico para su organización.</span><span class="sxs-lookup"><span data-stu-id="5d8e3-106">A conferencing bridge gives you a set of dial-in phone numbers for your organization.</span></span> <span data-ttu-id="5d8e3-107">Todos ellos se pueden usar para unirse a las reuniones que ha creado un organizador de la reunión, pero puede seleccionar cuáles se incluirá en sus invitaciones de reunión.</span><span class="sxs-lookup"><span data-stu-id="5d8e3-107">All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5d8e3-108">Puede haber un máximo de un teléfono de pago y un número de teléfono gratuito en la invitación a la reunión para un organizador de la reunión, pero también hay un vínculo que se encuentra en la parte inferior de cada invitación a la reunión que se abre la lista completa de todos los números de teléfono de acceso telefónico que se pueden usar para unirse a una reunión.</span><span class="sxs-lookup"><span data-stu-id="5d8e3-108">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a><span data-ttu-id="5d8e3-109">Establecer o cambiar el número de teléfono de conferencia de audio predeterminada para un usuario o el organizador de la reunión</span><span class="sxs-lookup"><span data-stu-id="5d8e3-109">Set or change the default audio conferencing phone number for a meeting organizer or user</span></span>

1. <span data-ttu-id="5d8e3-110">En el panel de navegación izquierdo, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="5d8e3-110">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

    ![Selección de los usuarios en el Microsoft Teams y Skype para el centro de administración de negocio de muestra](media/teamsselectusers.png)

2. <span data-ttu-id="5d8e3-112">En la parte superior de la página, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="5d8e3-112">At the top of the page, click **Edit**.</span></span>

    ![Haga clic en Editar en los equipos de Microsoft y Skype para el centro de administración de negocio](media/teamsedituser.png)

3. <span data-ttu-id="5d8e3-114">Junto a **Conferencias de Audio**, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="5d8e3-114">Next to **Audio Conferencing**, click **Edit**.</span></span> 
    
    ![Haga clic en Editar junto a la conferencia de Audio](media/teamseditaudioconf.png)

4. <span data-ttu-id="5d8e3-116">Use los campos de **número de teléfono de pago** o **número de teléfono gratuito** para escribir los números para el usuario.</span><span class="sxs-lookup"><span data-stu-id="5d8e3-116">Use the **Toll number** or **Toll-free number** fields to enter the numbers for the user.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="5d8e3-117">Cuando se cambia la configuración de conferencia de audio de un usuario, las reuniones de Microsoft Teams periódicas y futuras deben actualiza y se envía a los asistentes.</span><span class="sxs-lookup"><span data-stu-id="5d8e3-117">When you change a user's audio conferencing settings, recurring and future Microsoft Teams meetings must be updated and sent to attendees.</span></span> 

## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="5d8e3-118">¿Desea usar Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="5d8e3-118">Want to use Windows PowerShell?</span></span>

<span data-ttu-id="5d8e3-p103">Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="5d8e3-p103">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="5d8e3-122">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="5d8e3-122">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="5d8e3-123">Las mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5d8e3-123">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="5d8e3-124">Para obtener más información acerca de Windows PowerShell, vea la [referencia de PowerShell de los equipos de Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="5d8e3-124">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span> 
  
    
## <a name="related-topics"></a><span data-ttu-id="5d8e3-125">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="5d8e3-125">Related topics</span></span>

[<span data-ttu-id="5d8e3-126">Probar o comprar Audioconferencia en Office 365</span><span class="sxs-lookup"><span data-stu-id="5d8e3-126">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
