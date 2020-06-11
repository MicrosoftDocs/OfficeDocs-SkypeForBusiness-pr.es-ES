---
title: Establecer los números de teléfono incluidos en las invitaciones
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
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
description: Siga estos pasos para crear un número de teléfono predeterminado para que las personas que llamen se unan a una reunión de Microsoft Teams.
ms.openlocfilehash: 81624090b1e82bf695f8e558cd55324a45d927e5
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691116"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a><span data-ttu-id="ac76a-103">Establecer los números de teléfono incluidos en las invitaciones en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ac76a-103">Set the phone numbers included on invites in Microsoft Teams</span></span>

<span data-ttu-id="ac76a-104">La Conferencia de audio en Microsoft 365 y Office 365 permite a los usuarios de su organización crear reuniones de Microsoft Teams y, a continuación, permitir a los usuarios que llamen a esas reuniones con un teléfono.</span><span class="sxs-lookup"><span data-stu-id="ac76a-104">Audio Conferencing in Microsoft 365 and Office 365 enables users in your organization to create Microsoft Teams meetings, and then allow users to dial in to those meetings using a phone.</span></span>
  
<span data-ttu-id="ac76a-105">Un puente de conferencia le ofrece un conjunto de números de teléfono de acceso telefónico local para su organización.</span><span class="sxs-lookup"><span data-stu-id="ac76a-105">A conferencing bridge gives you a set of dial-in phone numbers for your organization.</span></span> <span data-ttu-id="ac76a-106">Todas ellas se pueden usar para unirse a las reuniones que ha creado el organizador de la reunión, pero puede seleccionar cuáles se incluirán en sus invitaciones a reuniones.</span><span class="sxs-lookup"><span data-stu-id="ac76a-106">All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ac76a-107">Puede haber un máximo de un número de teléfono de pago y un número de teléfono gratuito en la invitación a la reunión para un organizador de la reunión, pero también hay un vínculo en la parte inferior de cada invitación a la reunión que abre la lista completa de todos los números de teléfono de acceso telefónico local que se pueden usar para unirse a una reunión.</span><span class="sxs-lookup"><span data-stu-id="ac76a-107">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a><span data-ttu-id="ac76a-108">Asignación inicial de números de teléfono que se incluyen en las invitaciones a reuniones para nuevos usuarios</span><span class="sxs-lookup"><span data-stu-id="ac76a-108">Initial assignment of phone numbers that are included in the meeting invites for new users</span></span>

<span data-ttu-id="ac76a-109">Los números de teléfono que se incluyen en las invitaciones de reunión de los usuarios habilitados para las conferencias de audio se definen mediante el número de teléfono de conferencia predeterminado y la configuración de usuario gratuito de las conferencias de conferencia predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ac76a-109">The phone numbers that get included in the meeting invites of users enabled for Audio Conferencing are defined by the default conferencing toll phone number and the default conferencing toll-free phone number user's settings.</span></span> <span data-ttu-id="ac76a-110">Cada opción especifica qué número de pago y gratuito se incluirá en la invitación a la reunión de un usuario dado.</span><span class="sxs-lookup"><span data-stu-id="ac76a-110">Each setting specifies which toll and toll-free number will be included in the meeting invite of a given user.</span></span> <span data-ttu-id="ac76a-111">Como se mencionó anteriormente, cada invitación a una reunión contiene un número de teléfono, un número opcional gratuito y un vínculo que abre la lista completa de todos los números de teléfono de acceso telefónico local que se pueden usar para unirse a una reunión determinada.</span><span class="sxs-lookup"><span data-stu-id="ac76a-111">As noted above, each meeting invite contains one toll number, one optional toll-free number and a link that opens the full list of all dial-in phone numbers that can be used to join a given meeting.</span></span>

<span data-ttu-id="ac76a-112">Para un nuevo usuario, los números de teléfono de conferencia predeterminados se asignan en función de la ubicación de uso establecida en el centro de administración de Microsoft 365 del usuario cuando el usuario está habilitado para el servicio audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="ac76a-112">For a new user, the default conferencing toll numbers is assigned based on the Usage Location that is set in the Microsoft 365 administration center of the user when the user is enabled for the Audio Conferencing service.</span></span> <span data-ttu-id="ac76a-113">Si hay un número de pago en el puente de conferencia que coincide con el país del usuario, ese número se asignará automáticamente como el número de pago predeterminado del usuario.</span><span class="sxs-lookup"><span data-stu-id="ac76a-113">If there is a toll number in the conference bridge that matches the country of the user, that number will be automatically assigned as the default toll number of the user.</span></span> <span data-ttu-id="ac76a-114">Si no hay ninguno, el número que se define como número de teléfono predeterminado del puente de conferencia se asignará como número de teléfono de pago predeterminado del usuario.</span><span class="sxs-lookup"><span data-stu-id="ac76a-114">If there isn't one, the number that is defined as the default toll number of the conference bridge will be assigned as the default toll number of the user.</span></span>  

<span data-ttu-id="ac76a-115">Una vez que el usuario está habilitado para el servicio de audioconferencia, los números de teléfono de pago y gratuitos, que el administrador del inquilino puede cambiar de forma predeterminada en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="ac76a-115">Once the user is enabled for the Audio Conferencing service, the default toll and toll-free phone numbers of the user can be changed by the tenant administrator from their initial values at any moment.</span></span>

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a><span data-ttu-id="ac76a-116">Establecer o cambiar el número de teléfono de conferencia de audio predeterminado para un organizador de la reunión o un usuario</span><span class="sxs-lookup"><span data-stu-id="ac76a-116">Set or change the default audio conferencing phone number for a meeting organizer or user</span></span>

<span data-ttu-id="ac76a-117">![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="ac76a-117">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

<span data-ttu-id="ac76a-118">Debe ser administrador para realizar estos cambios.</span><span class="sxs-lookup"><span data-stu-id="ac76a-118">You must be an admin to make these changes.</span></span>

1. <span data-ttu-id="ac76a-119">Inicie sesión en el centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="ac76a-119">Log in to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="ac76a-120">En el navegación de la izquierda, haga clic en **usuarios**.</span><span class="sxs-lookup"><span data-stu-id="ac76a-120">In the left navigation, click **Users**.</span></span>

    ![Se muestra la selección de usuarios en el centro de administración de Microsoft Teams](media/Admin-users.png)

3. <span data-ttu-id="ac76a-122">Haga clic en el nombre de usuario de la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="ac76a-122">Click the user name from the list of available users.</span></span>

4. <span data-ttu-id="ac76a-123">Junto a **audioconferencia**, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="ac76a-123">Next to **Audio Conferencing**, click **Edit**.</span></span> 
    
    ![Haga clic en Editar junto a audioconferencia](media/teams-set-phone-numbers-on-invites-image3.png)

5. <span data-ttu-id="ac76a-125">Use los campos **número de pago** o **número gratuito** para introducir los números del usuario.</span><span class="sxs-lookup"><span data-stu-id="ac76a-125">Use the **Toll number** or **Toll-free number** fields to enter the numbers for the user.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="ac76a-126">Al cambiar la configuración de la Conferencia de audio de un usuario, las reuniones periódicas y futuras de Microsoft Teams deben actualizarse y enviarse a los asistentes.</span><span class="sxs-lookup"><span data-stu-id="ac76a-126">When you change a user's audio conferencing settings, recurring and future Microsoft Teams meetings must be updated and sent to attendees.</span></span> 

## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="ac76a-127">¿Desea usar Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="ac76a-127">Want to use Windows PowerShell?</span></span>

<span data-ttu-id="ac76a-128">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="ac76a-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="ac76a-129">Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 con un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas para hacer.</span><span class="sxs-lookup"><span data-stu-id="ac76a-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="ac76a-130">To get started with Windows PowerShell, see these topics:</span><span class="sxs-lookup"><span data-stu-id="ac76a-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="ac76a-131">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="ac76a-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="ac76a-132">Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ac76a-132">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="ac76a-133">Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="ac76a-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span> 
  
    
## <a name="related-topics"></a><span data-ttu-id="ac76a-134">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="ac76a-134">Related topics</span></span>

[<span data-ttu-id="ac76a-135">Probar o comprar audioconferencia en Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="ac76a-135">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

[<span data-ttu-id="ac76a-136">Cambiar los números de teléfono de su puente de Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="ac76a-136">Change the phone numbers on your Audio Conferencing bridge</span></span>](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)
