---
title: Establecer el teléfono los números incluidos en invitaciones en Microsoft Teams
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
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Obtener los pasos para crear un número de teléfono predeterminado para los autores de llamadas para unirse a una reunión de Microsoft Teams. '
ms.openlocfilehash: 20dfd4255cd41e9f5aebf419f77307b30fe40042
ms.sourcegitcommit: 75e0c9e186dc167bad01f5b17ec9de8a682ee007
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2018
ms.locfileid: "26005524"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a><span data-ttu-id="e4b00-103">Establecer los números de teléfono incluidos en las invitaciones en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e4b00-103">Set the phone numbers included on invites in Microsoft Teams</span></span>

<span data-ttu-id="e4b00-104">Conferencias de audio en Office 365 permiten a los usuarios de la organización crear reuniones de Microsoft Teams y, a continuación, permitir a los usuarios para conectarse a las reuniones utilizando un teléfono.</span><span class="sxs-lookup"><span data-stu-id="e4b00-104">Audio Conferencing in Office 365 enables users in your organization to create Microsoft Teams meetings, and then allow users to dial in to those meetings using a phone.</span></span>
  
<span data-ttu-id="e4b00-105">Un puente de conferencia le proporciona un conjunto de números de teléfono de acceso telefónico para su organización.</span><span class="sxs-lookup"><span data-stu-id="e4b00-105">A conferencing bridge gives you a set of dial-in phone numbers for your organization.</span></span> <span data-ttu-id="e4b00-106">Todos ellos se pueden usar para unirse a las reuniones que ha creado un organizador de la reunión, pero puede seleccionar cuáles se incluirá en sus invitaciones de reunión.</span><span class="sxs-lookup"><span data-stu-id="e4b00-106">All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e4b00-107">Puede haber un máximo de un teléfono de pago y un número de teléfono gratuito en la invitación a la reunión para un organizador de la reunión, pero también hay un vínculo que se encuentra en la parte inferior de cada invitación a la reunión que se abre la lista completa de todos los números de teléfono de acceso telefónico que se pueden usar para unirse a una reunión.</span><span class="sxs-lookup"><span data-stu-id="e4b00-107">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a><span data-ttu-id="e4b00-108">Asignación inicial de números de teléfono que se incluyen en la reunión invitaciones para nuevos usuarios</span><span class="sxs-lookup"><span data-stu-id="e4b00-108">Initial assignment of phone numbers that are included in the meeting invites for new users</span></span>

<span data-ttu-id="e4b00-109">Se invita los números de teléfono que se incluyan en la reunión de los usuarios habilitados para conferencias de Audio se definen mediante el número de teléfono de pago de conferencia de forma predeterminada y la configuración de la conferencia teléfono gratuito número del usuario predeterminado.</span><span class="sxs-lookup"><span data-stu-id="e4b00-109">The phone numbers that get included in the meeting invites of users enabled for Audio Conferencing are defined by the default conferencing toll phone number and the default conferencing toll-free phone number user's settings.</span></span> <span data-ttu-id="e4b00-110">Cada opción de configuración especifica qué números de pago y el número de teléfono gratuito se incluirá en la invitación a la reunión de un usuario determinado.</span><span class="sxs-lookup"><span data-stu-id="e4b00-110">Each setting specifies which toll and toll-free number will be included in the meeting invite of a given user.</span></span> <span data-ttu-id="e4b00-111">Como se mencionó anteriormente, cada invitación a la reunión contiene el número de teléfono de uno pago, un número de teléfono gratuito opcional y un vínculo que se abre la lista completa de todos los números de teléfono de acceso telefónico que se pueden usar para unirse a una reunión determinada.</span><span class="sxs-lookup"><span data-stu-id="e4b00-111">As noted above, each meeting invite contains one toll number, one optional toll-free number and a link that opens the full list of all dial-in phone numbers that can be used to join a given meeting.</span></span>

<span data-ttu-id="e4b00-112">Para un nuevo usuario, se asignan los números de teléfono de pago de conferencia predeterminados según el país en el que se establece en el perfil de Office 365 del usuario cuando el usuario está habilitado para el servicio de conferencia de Audio.</span><span class="sxs-lookup"><span data-stu-id="e4b00-112">For a new user, the default conferencing toll numbers is assigned based on the country that is set in the Office 365 profile of the user when the user is enabled for the Audio Conferencing service.</span></span> <span data-ttu-id="e4b00-113">Si no hay un número de teléfono de pago en el puente de conferencia que coincide con el país del usuario, ese número se asignará automáticamente como el número de teléfono de pago predeterminado del usuario.</span><span class="sxs-lookup"><span data-stu-id="e4b00-113">If there is a toll number in the conference bridge that matches the country of the user, that number will be automatically assigned as the default toll number of the user.</span></span> <span data-ttu-id="e4b00-114">Si no hay, se asignará el número al que se ha definido como el número de teléfono de pago predeterminado del puente de conferencia como el número de teléfono de pago predeterminado del usuario.</span><span class="sxs-lookup"><span data-stu-id="e4b00-114">If there isn't one, the number that is defined as the default toll number of the conference bridge will be assigned as the default toll number of the user.</span></span>  

<span data-ttu-id="e4b00-115">Una vez que el usuario está habilitado para el servicio de conferencia de Audio, el pago de forma predeterminada y los números de teléfono gratuito del usuario pueden cambiarse por el Administrador de inquilinos de sus valores iniciales en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="e4b00-115">Once the user is enabled for the Audio Conferencing service, the default toll and toll-free phone numbers of the user can be changed by the tenant administrator from their initial values at any moment.</span></span>

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a><span data-ttu-id="e4b00-116">Establecer o cambiar el número de teléfono de conferencia de audio predeterminada para un usuario o el organizador de la reunión</span><span class="sxs-lookup"><span data-stu-id="e4b00-116">Set or change the default audio conferencing phone number for a meeting organizer or user</span></span>

![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) <span data-ttu-id="e4b00-118">Uso del equipos de Microsoft y Skype para centro de administración de negocio</span><span class="sxs-lookup"><span data-stu-id="e4b00-118">Using the Microsoft Teams and Skype for Business Admin Center</span></span>

1. <span data-ttu-id="e4b00-119">En el panel de navegación izquierdo, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="e4b00-119">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

    ![Selección de los usuarios en el Microsoft Teams y Skype para el centro de administración de negocio de muestra](media/teamsselectusers.png)

2. <span data-ttu-id="e4b00-121">En la parte superior de la página, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e4b00-121">At the top of the page, click **Edit**.</span></span>

    ![Haga clic en Editar en los equipos de Microsoft y Skype para el centro de administración de negocio](media/teamsedituser.png)

3. <span data-ttu-id="e4b00-123">Junto a **Conferencias de Audio**, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e4b00-123">Next to **Audio Conferencing**, click **Edit**.</span></span> 
    
    ![Haga clic en Editar junto a la conferencia de Audio](media/teamseditaudioconf.png)

4. <span data-ttu-id="e4b00-125">Use los campos de **número de teléfono de pago** o **número de teléfono gratuito** para escribir los números para el usuario.</span><span class="sxs-lookup"><span data-stu-id="e4b00-125">Use the **Toll number** or **Toll-free number** fields to enter the numbers for the user.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="e4b00-126">Cuando se cambia la configuración de conferencia de audio de un usuario, las reuniones de Microsoft Teams periódicas y futuras deben actualiza y se envía a los asistentes.</span><span class="sxs-lookup"><span data-stu-id="e4b00-126">When you change a user's audio conferencing settings, recurring and future Microsoft Teams meetings must be updated and sent to attendees.</span></span> 

## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="e4b00-127">¿Desea usar Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="e4b00-127">Want to use Windows PowerShell?</span></span>

<span data-ttu-id="e4b00-p104">Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="e4b00-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="e4b00-131">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="e4b00-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="e4b00-132">Las mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e4b00-132">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="e4b00-133">Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="e4b00-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span> 
  
    
## <a name="related-topics"></a><span data-ttu-id="e4b00-134">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="e4b00-134">Related topics</span></span>

[<span data-ttu-id="e4b00-135">Probar o comprar Audioconferencia en Office 365</span><span class="sxs-lookup"><span data-stu-id="e4b00-135">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
