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
description: Siga estos pasos para crear un número de teléfono predeterminado para que los autores de llamadas se unan a una reunión de Microsoft Teams.
ms.openlocfilehash: 7dd59950403543074d8428d35270ab963ca824e3
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372189"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a><span data-ttu-id="e3f7c-103">Establecer los números de teléfono incluidos en las invitaciones en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e3f7c-103">Set the phone numbers included on invites in Microsoft Teams</span></span>

<span data-ttu-id="e3f7c-104">Las audioconferencias en Microsoft 365 y Office 365 permiten a los usuarios de su organización crear reuniones de Microsoft Teams y, a continuación, permiten que los usuarios llamen a esas reuniones con un teléfono.</span><span class="sxs-lookup"><span data-stu-id="e3f7c-104">Audio Conferencing in Microsoft 365 and Office 365 enables users in your organization to create Microsoft Teams meetings, and then allow users to dial in to those meetings using a phone.</span></span>
  
<span data-ttu-id="e3f7c-105">Un puente de conferencias le proporciona un conjunto de números de teléfono de acceso telefónico local para su organización.</span><span class="sxs-lookup"><span data-stu-id="e3f7c-105">A conferencing bridge gives you a set of dial-in phone numbers for your organization.</span></span> <span data-ttu-id="e3f7c-106">Todos ellos se pueden usar para unirse a las reuniones que haya creado un organizador de reuniones, pero puede seleccionar los que se incluirán en las invitaciones a la reunión.</span><span class="sxs-lookup"><span data-stu-id="e3f7c-106">All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e3f7c-107">Puede haber un máximo de un número de pago y un número gratuito en la invitación a la reunión para el organizador de la reunión, pero también hay un vínculo en la parte inferior de cada invitación de reunión que abre la lista completa de los números de acceso telefónico local que se pueden usar para unirse a una reunión.</span><span class="sxs-lookup"><span data-stu-id="e3f7c-107">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a><span data-ttu-id="e3f7c-108">Asignación inicial de números de teléfono que se incluyen en las invitaciones de reunión para nuevos usuarios</span><span class="sxs-lookup"><span data-stu-id="e3f7c-108">Initial assignment of phone numbers that are included in the meeting invites for new users</span></span>

<span data-ttu-id="e3f7c-109">Los números de teléfono que se incluyen en las invitaciones de reunión de los usuarios habilitados para Audioconferencia se definen por el número de teléfono de pago de las conferencias y por la configuración predeterminada del usuario de número de teléfono gratuito para conferencias.</span><span class="sxs-lookup"><span data-stu-id="e3f7c-109">The phone numbers that get included in the meeting invites of users enabled for Audio Conferencing are defined by the default conferencing toll phone number and the default conferencing toll-free phone number user's settings.</span></span> <span data-ttu-id="e3f7c-110">Cada opción especifica qué número gratuito y de pago se incluirá en la invitación a la reunión de un usuario determinado.</span><span class="sxs-lookup"><span data-stu-id="e3f7c-110">Each setting specifies which toll and toll-free number will be included in the meeting invite of a given user.</span></span> <span data-ttu-id="e3f7c-111">Como se indicó anteriormente, cada invitación a una reunión contiene un número de pago, un número gratuito opcional y un vínculo que abre la lista completa de todos los números de acceso telefónico que se pueden usar para unirse a una reunión determinada.</span><span class="sxs-lookup"><span data-stu-id="e3f7c-111">As noted above, each meeting invite contains one toll number, one optional toll-free number and a link that opens the full list of all dial-in phone numbers that can be used to join a given meeting.</span></span>

<span data-ttu-id="e3f7c-112">Para un nuevo usuario, los números de pago de conferencia predeterminados se asignan según la ubicación de uso establecida en el centro de administración de Microsoft 365 del usuario cuando el usuario está habilitado para el servicio de Audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="e3f7c-112">For a new user, the default conferencing toll numbers is assigned based on the Usage Location that is set in the Microsoft 365 administration center of the user when the user is enabled for the Audio Conferencing service.</span></span> <span data-ttu-id="e3f7c-113">Si hay un número de pago en el puente de conferencia que coincida con el país del usuario, ese número se asignará automáticamente como el número de pago predeterminado del usuario.</span><span class="sxs-lookup"><span data-stu-id="e3f7c-113">If there is a toll number in the conference bridge that matches the country of the user, that number will be automatically assigned as the default toll number of the user.</span></span> <span data-ttu-id="e3f7c-114">Si no lo hay, el número que se define como el número de pago predeterminado del puente de conferencia se asignará como el número de pago predeterminado del usuario.</span><span class="sxs-lookup"><span data-stu-id="e3f7c-114">If there isn't one, the number that is defined as the default toll number of the conference bridge will be assigned as the default toll number of the user.</span></span>  

<span data-ttu-id="e3f7c-115">Una vez que el usuario está habilitado para el servicio de Audioconferencia, el administrador de inquilinos puede cambiar los números de teléfono gratuitos y de pago predeterminados del usuario de sus valores iniciales en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="e3f7c-115">Once the user is enabled for the Audio Conferencing service, the default toll and toll-free phone numbers of the user can be changed by the tenant administrator from their initial values at any moment.</span></span>

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a><span data-ttu-id="e3f7c-116">Establecer o cambiar el número de teléfono de audioconferencia predeterminado para un organizador o usuario de la reunión</span><span class="sxs-lookup"><span data-stu-id="e3f7c-116">Set or change the default audio conferencing phone number for a meeting organizer or user</span></span>

<span data-ttu-id="e3f7c-117">![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="e3f7c-117">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

<span data-ttu-id="e3f7c-118">Debe ser administrador del servicio de Teams para realizar estos cambios.</span><span class="sxs-lookup"><span data-stu-id="e3f7c-118">You must be a Teams service admin to make these changes.</span></span> <span data-ttu-id="e3f7c-119">Consulte [Usar los roles de administrador de Teams para administrar Teams y](https://docs.microsoft.com/microsoftteams/using-admin-roles) obtener información sobre cómo obtener permisos y roles de administrador.</span><span class="sxs-lookup"><span data-stu-id="e3f7c-119">See [Use Teams administrator roles to manage Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="e3f7c-120">Inicie sesión en el Centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e3f7c-120">Log in to the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="e3f7c-121">En el panel de navegación izquierdo, haga clic en **Usuarios.**</span><span class="sxs-lookup"><span data-stu-id="e3f7c-121">In the left navigation, click **Users**.</span></span>

    ![Muestra la selección de usuarios en el Centro de administración de Microsoft Teams](media/Admin-users.png)

3. <span data-ttu-id="e3f7c-123">Haga clic en el nombre de usuario de la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="e3f7c-123">Click the user name from the list of available users.</span></span>

4. <span data-ttu-id="e3f7c-124">Junto a **Audioconferencia,** haga clic en **Editar.**</span><span class="sxs-lookup"><span data-stu-id="e3f7c-124">Next to **Audio Conferencing**, click **Edit**.</span></span>

    ![Haga clic en Editar junto a Audioconferencia](media/teams-set-phone-numbers-on-invites-image3.png)

5. <span data-ttu-id="e3f7c-126">Use los **campos Número de pago** o Número **gratuito** para introducir los números del usuario.</span><span class="sxs-lookup"><span data-stu-id="e3f7c-126">Use the **Toll number** or **Toll-free number** fields to enter the numbers for the user.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e3f7c-127">Cuando cambia la configuración de audioconferencia de un usuario, las reuniones periódicas y futuras de Microsoft Teams deben actualizarse y enviarse a los asistentes.</span><span class="sxs-lookup"><span data-stu-id="e3f7c-127">When you change a user's audio conferencing settings, recurring and future Microsoft Teams meetings must be updated and sent to attendees.</span></span>

## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="e3f7c-128">¿Desea usar Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e3f7c-128">Want to use Windows PowerShell</span></span>

<span data-ttu-id="e3f7c-129">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="e3f7c-129">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="e3f7c-130">Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 con un único punto de administración que puede simplificar su trabajo diario cuando tenga que realizar varias tareas.</span><span class="sxs-lookup"><span data-stu-id="e3f7c-130">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="e3f7c-131">To get started with Windows PowerShell, see these topics:</span><span class="sxs-lookup"><span data-stu-id="e3f7c-131">To get started with Windows PowerShell, see these topics:</span></span>

- [<span data-ttu-id="e3f7c-132">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="e3f7c-132">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- [<span data-ttu-id="e3f7c-133">Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e3f7c-133">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

<span data-ttu-id="e3f7c-134">Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="e3f7c-134">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e3f7c-135">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="e3f7c-135">Related topics</span></span>

[<span data-ttu-id="e3f7c-136">Probar o comprar Audioconferencia en Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="e3f7c-136">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

[<span data-ttu-id="e3f7c-137">Cambiar los números de teléfono de su puente de Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="e3f7c-137">Change the phone numbers on your Audio Conferencing bridge</span></span>](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)
