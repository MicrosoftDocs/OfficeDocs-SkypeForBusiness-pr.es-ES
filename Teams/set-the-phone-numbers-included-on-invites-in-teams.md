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
description: Siga estos pasos para crear un número de teléfono predeterminado para que los autores de llamadas se unan a Microsoft Teams reunión.
ms.openlocfilehash: 476075ccf5e261695564b78ec084605af9e6898c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117178"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a><span data-ttu-id="9517e-103">Establecer los números de teléfono incluidos en las invitaciones en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9517e-103">Set the phone numbers included on invites in Microsoft Teams</span></span>

<span data-ttu-id="9517e-104">Las audioconferencias en Microsoft 365 y Office 365 permiten a los usuarios de su organización crear reuniones Microsoft Teams y, a continuación, permitir que los usuarios llamen a esas reuniones con un teléfono.</span><span class="sxs-lookup"><span data-stu-id="9517e-104">Audio Conferencing in Microsoft 365 and Office 365 enables users in your organization to create Microsoft Teams meetings, and then allow users to dial in to those meetings using a phone.</span></span>
  
<span data-ttu-id="9517e-105">Un puente de conferencias le proporciona un conjunto de números de teléfono de acceso telefónico local para su organización.</span><span class="sxs-lookup"><span data-stu-id="9517e-105">A conferencing bridge gives you a set of dial-in phone numbers for your organization.</span></span> <span data-ttu-id="9517e-106">Todas ellas se pueden usar para unirse a las reuniones que ha creado un organizador de la reunión, pero puede seleccionar las que se incluirán en sus invitaciones de reunión.</span><span class="sxs-lookup"><span data-stu-id="9517e-106">All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9517e-107">Puede haber un máximo de un número de teléfono gratuito y un número de teléfono gratuito en la invitación de reunión para un organizador de la reunión, pero también hay un vínculo situado en la parte inferior de cada invitación a la reunión que abre la lista completa de todos los números de teléfono de acceso telefónico local que se pueden usar para unirse a una reunión.</span><span class="sxs-lookup"><span data-stu-id="9517e-107">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a><span data-ttu-id="9517e-108">Asignación inicial de números de teléfono que se incluyen en las invitaciones de reunión para nuevos usuarios</span><span class="sxs-lookup"><span data-stu-id="9517e-108">Initial assignment of phone numbers that are included in the meeting invites for new users</span></span>

<span data-ttu-id="9517e-109">Los números de teléfono que se incluyen en las invitaciones de reunión de los usuarios habilitados para las audioconferencias se definen por el número de teléfono de pago de conferencia predeterminado y la configuración predeterminada del usuario de número de teléfono gratuito de conferencias.</span><span class="sxs-lookup"><span data-stu-id="9517e-109">The phone numbers that get included in the meeting invites of users enabled for Audio Conferencing are defined by the default conferencing toll phone number and the default conferencing toll-free phone number user's settings.</span></span> <span data-ttu-id="9517e-110">Cada configuración especifica qué número de pago y gratuito se incluirán en la invitación a la reunión de un usuario determinado.</span><span class="sxs-lookup"><span data-stu-id="9517e-110">Each setting specifies which toll and toll-free number will be included in the meeting invite of a given user.</span></span> <span data-ttu-id="9517e-111">Como se ha indicado anteriormente, cada invitación a la reunión contiene un número de pago, un número gratuito opcional y un vínculo que abre la lista completa de todos los números de teléfono de acceso telefónico telefónico que se pueden usar para unirse a una reunión determinada.</span><span class="sxs-lookup"><span data-stu-id="9517e-111">As noted above, each meeting invite contains one toll number, one optional toll-free number and a link that opens the full list of all dial-in phone numbers that can be used to join a given meeting.</span></span>

<span data-ttu-id="9517e-112">Para un nuevo usuario, los números de pago de conferencia predeterminados se asignan en función de la ubicación de uso que se establece en el centro de administración de Microsoft 365 del usuario cuando el usuario está habilitado para el servicio de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="9517e-112">For a new user, the default conferencing toll numbers is assigned based on the Usage Location that is set in the Microsoft 365 administration center of the user when the user is enabled for the Audio Conferencing service.</span></span> <span data-ttu-id="9517e-113">Si hay un número de pago en el puente de conferencia que coincida con el país del usuario, ese número se asignará automáticamente como el número de pago predeterminado del usuario.</span><span class="sxs-lookup"><span data-stu-id="9517e-113">If there is a toll number in the conference bridge that matches the country of the user, that number will be automatically assigned as the default toll number of the user.</span></span> <span data-ttu-id="9517e-114">Si no hay ninguna, el número que se define como el número de peaje predeterminado del puente de conferencia se asignará como el número de pago predeterminado del usuario.</span><span class="sxs-lookup"><span data-stu-id="9517e-114">If there isn't one, the number that is defined as the default toll number of the conference bridge will be assigned as the default toll number of the user.</span></span>  

<span data-ttu-id="9517e-115">Una vez que el usuario está habilitado para el servicio de audioconferencia, el administrador de inquilinos puede cambiar los números de teléfono gratuitos y de pago predeterminados del usuario a partir de sus valores iniciales en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="9517e-115">Once the user is enabled for the Audio Conferencing service, the default toll and toll-free phone numbers of the user can be changed by the tenant administrator from their initial values at any moment.</span></span>

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a><span data-ttu-id="9517e-116">Establecer o cambiar el número de teléfono de audioconferencia predeterminado para un organizador o usuario de la reunión</span><span class="sxs-lookup"><span data-stu-id="9517e-116">Set or change the default audio conferencing phone number for a meeting organizer or user</span></span>

<span data-ttu-id="9517e-117">![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="9517e-117">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

<span data-ttu-id="9517e-118">Debe ser administrador de servicio de Teams para poder realizar estos cambios.</span><span class="sxs-lookup"><span data-stu-id="9517e-118">You must be a Teams service admin to make these changes.</span></span> <span data-ttu-id="9517e-119">Consulte [Usar los roles de administrador de Teams para administrar Teams](./using-admin-roles.md) para obtener información sobre cómo obtener roles de administrador y permisos.</span><span class="sxs-lookup"><span data-stu-id="9517e-119">See [Use Teams administrator roles to manage Teams](./using-admin-roles.md) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="9517e-120">Inicie sesión en el Microsoft Teams de administración.</span><span class="sxs-lookup"><span data-stu-id="9517e-120">Log in to the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="9517e-121">En el panel de navegación izquierdo, haga clic en **Usuarios.**</span><span class="sxs-lookup"><span data-stu-id="9517e-121">In the left navigation, click **Users**.</span></span>

    ![Muestra la selección de usuarios en el Microsoft Teams de administración](media/Admin-users.png)

3. <span data-ttu-id="9517e-123">Haga clic en el nombre de usuario de la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="9517e-123">Click the user name from the list of available users.</span></span>

4. <span data-ttu-id="9517e-124">Junto a **Audioconferencia,** haga clic en **Editar.**</span><span class="sxs-lookup"><span data-stu-id="9517e-124">Next to **Audio Conferencing**, click **Edit**.</span></span>

    ![Haga clic en Editar junto a Audioconferencia](media/teams-set-phone-numbers-on-invites-image3.png)

5. <span data-ttu-id="9517e-126">Use los **campos Número de pago** o **Número** gratuito para escribir los números del usuario.</span><span class="sxs-lookup"><span data-stu-id="9517e-126">Use the **Toll number** or **Toll-free number** fields to enter the numbers for the user.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9517e-127">Al cambiar la configuración de audioconferencia de un usuario, las reuniones periódicas y futuras Microsoft Teams deben actualizarse y enviarse a los asistentes.</span><span class="sxs-lookup"><span data-stu-id="9517e-127">When you change a user's audio conferencing settings, recurring and future Microsoft Teams meetings must be updated and sent to attendees.</span></span>

## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="9517e-128">¿Desea usar Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9517e-128">Want to use Windows PowerShell</span></span>

<span data-ttu-id="9517e-129">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="9517e-129">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="9517e-130">Con Windows PowerShell, puede administrar Microsoft 365 o Office 365 mediante un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas que hacer.</span><span class="sxs-lookup"><span data-stu-id="9517e-130">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="9517e-131">To get started with Windows PowerShell, see these topics:</span><span class="sxs-lookup"><span data-stu-id="9517e-131">To get started with Windows PowerShell, see these topics:</span></span>

- [<span data-ttu-id="9517e-132">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="9517e-132">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- <span data-ttu-id="9517e-133">[Las mejores formas de administrar Microsoft 365 o Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="9517e-133">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>

<span data-ttu-id="9517e-134">Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="9517e-134">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="9517e-135">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="9517e-135">Related topics</span></span>

[<span data-ttu-id="9517e-136">Pruebe o compre Audioconferencia en Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="9517e-136">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

[<span data-ttu-id="9517e-137">Cambiar los números de teléfono de su puente de Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="9517e-137">Change the phone numbers on your Audio Conferencing bridge</span></span>](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)