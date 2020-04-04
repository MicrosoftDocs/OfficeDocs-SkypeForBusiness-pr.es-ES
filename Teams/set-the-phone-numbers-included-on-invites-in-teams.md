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
description: 'Siga los pasos para crear un número de teléfono predeterminado para que las personas que llaman participen en una reunión de Microsoft Teams. '
ms.openlocfilehash: 6c45a28ab48add26eef8929e37e5cf60113185ea
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2020
ms.locfileid: "43140903"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a><span data-ttu-id="5f8ca-103">Establecer los números de teléfono incluidos en las invitaciones en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5f8ca-103">Set the phone numbers included on invites in Microsoft Teams</span></span>

<span data-ttu-id="5f8ca-104">Las conferencias de audio en Office 365 permiten a los usuarios de su organización crear reuniones de Microsoft Teams y, a continuación, permitir a los usuarios que llamen a esas reuniones con un teléfono.</span><span class="sxs-lookup"><span data-stu-id="5f8ca-104">Audio Conferencing in Office 365 enables users in your organization to create Microsoft Teams meetings, and then allow users to dial in to those meetings using a phone.</span></span>
  
<span data-ttu-id="5f8ca-105">Un puente de conferencia le ofrece un conjunto de números de teléfono de acceso telefónico local para su organización.</span><span class="sxs-lookup"><span data-stu-id="5f8ca-105">A conferencing bridge gives you a set of dial-in phone numbers for your organization.</span></span> <span data-ttu-id="5f8ca-106">Todas ellas se pueden usar para unirse a las reuniones que ha creado el organizador de la reunión, pero puede seleccionar cuáles se incluirán en sus invitaciones a reuniones.</span><span class="sxs-lookup"><span data-stu-id="5f8ca-106">All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5f8ca-107">Puede haber un máximo de un número de teléfono de pago y un número de teléfono gratuito en la invitación a la reunión para un organizador de la reunión, pero también hay un vínculo en la parte inferior de cada invitación a la reunión que abre la lista completa de todos los números de teléfono de acceso telefónico local que se pueden usar para unirse a una reunión.</span><span class="sxs-lookup"><span data-stu-id="5f8ca-107">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a><span data-ttu-id="5f8ca-108">Asignación inicial de números de teléfono que se incluyen en las invitaciones a reuniones para nuevos usuarios</span><span class="sxs-lookup"><span data-stu-id="5f8ca-108">Initial assignment of phone numbers that are included in the meeting invites for new users</span></span>

<span data-ttu-id="5f8ca-109">Los números de teléfono que se incluyen en las invitaciones de reunión de los usuarios habilitados para las conferencias de audio se definen mediante el número de teléfono de conferencia predeterminado y la configuración de usuario gratuito de las conferencias de conferencia predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5f8ca-109">The phone numbers that get included in the meeting invites of users enabled for Audio Conferencing are defined by the default conferencing toll phone number and the default conferencing toll-free phone number user's settings.</span></span> <span data-ttu-id="5f8ca-110">Cada opción especifica qué número de pago y gratuito se incluirá en la invitación a la reunión de un usuario dado.</span><span class="sxs-lookup"><span data-stu-id="5f8ca-110">Each setting specifies which toll and toll-free number will be included in the meeting invite of a given user.</span></span> <span data-ttu-id="5f8ca-111">Como se mencionó anteriormente, cada invitación a una reunión contiene un número de teléfono, un número opcional gratuito y un vínculo que abre la lista completa de todos los números de teléfono de acceso telefónico local que se pueden usar para unirse a una reunión determinada.</span><span class="sxs-lookup"><span data-stu-id="5f8ca-111">As noted above, each meeting invite contains one toll number, one optional toll-free number and a link that opens the full list of all dial-in phone numbers that can be used to join a given meeting.</span></span>

<span data-ttu-id="5f8ca-112">Para un nuevo usuario, los números de teléfono de conferencia predeterminados se asignan en función de la ubicación de uso establecida en el centro de administración de Office 365 del usuario cuando el usuario está habilitado para el servicio audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="5f8ca-112">For a new user, the default conferencing toll numbers is assigned based on the Usage Location that is set in the Office 365 administration center of the user when the user is enabled for the Audio Conferencing service.</span></span> <span data-ttu-id="5f8ca-113">Si hay un número de pago en el puente de conferencia que coincide con el país del usuario, ese número se asignará automáticamente como el número de pago predeterminado del usuario.</span><span class="sxs-lookup"><span data-stu-id="5f8ca-113">If there is a toll number in the conference bridge that matches the country of the user, that number will be automatically assigned as the default toll number of the user.</span></span> <span data-ttu-id="5f8ca-114">Si no hay ninguno, el número que se define como número de teléfono predeterminado del puente de conferencia se asignará como número de teléfono de pago predeterminado del usuario.</span><span class="sxs-lookup"><span data-stu-id="5f8ca-114">If there isn't one, the number that is defined as the default toll number of the conference bridge will be assigned as the default toll number of the user.</span></span>  

<span data-ttu-id="5f8ca-115">Una vez que el usuario está habilitado para el servicio de audioconferencia, los números de teléfono de pago y gratuitos, que el administrador del inquilino puede cambiar de forma predeterminada en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="5f8ca-115">Once the user is enabled for the Audio Conferencing service, the default toll and toll-free phone numbers of the user can be changed by the tenant administrator from their initial values at any moment.</span></span>

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a><span data-ttu-id="5f8ca-116">Establecer o cambiar el número de teléfono de conferencia de audio predeterminado para un organizador de la reunión o un usuario</span><span class="sxs-lookup"><span data-stu-id="5f8ca-116">Set or change the default audio conferencing phone number for a meeting organizer or user</span></span>

<span data-ttu-id="5f8ca-117">![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="5f8ca-117">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="5f8ca-118">En el navegación de la izquierda, haga clic en **usuarios**.</span><span class="sxs-lookup"><span data-stu-id="5f8ca-118">In the left navigation, click **Users**.</span></span>

    ![Se muestra la selección de usuarios en el centro de administración de Microsoft Teams](media/teams-set-phone-numbers-on-invites-image1.png)

2. <span data-ttu-id="5f8ca-120">Haga clic en el nombre de usuario de la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="5f8ca-120">Click the user name from the list of available users.</span></span>

3. <span data-ttu-id="5f8ca-121">Junto a **audioconferencia**, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="5f8ca-121">Next to **Audio Conferencing**, click **Edit**.</span></span> 
    
    ![Haga clic en Editar junto a audioconferencia](media/teams-set-phone-numbers-on-invites-image3.png)

4. <span data-ttu-id="5f8ca-123">Use los campos **número de pago** o **número gratuito** para introducir los números del usuario.</span><span class="sxs-lookup"><span data-stu-id="5f8ca-123">Use the **Toll number** or **Toll-free number** fields to enter the numbers for the user.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="5f8ca-124">Al cambiar la configuración de la Conferencia de audio de un usuario, las reuniones periódicas y futuras de Microsoft Teams deben actualizarse y enviarse a los asistentes.</span><span class="sxs-lookup"><span data-stu-id="5f8ca-124">When you change a user's audio conferencing settings, recurring and future Microsoft Teams meetings must be updated and sent to attendees.</span></span> 

## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="5f8ca-125">¿Desea usar Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="5f8ca-125">Want to use Windows PowerShell?</span></span>

<span data-ttu-id="5f8ca-p104">Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="5f8ca-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="5f8ca-129">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="5f8ca-129">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="5f8ca-130">Las mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5f8ca-130">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="5f8ca-131">Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="5f8ca-131">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span> 
  
    
## <a name="related-topics"></a><span data-ttu-id="5f8ca-132">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="5f8ca-132">Related topics</span></span>

[<span data-ttu-id="5f8ca-133">Probar o comprar Audioconferencia en Office 365</span><span class="sxs-lookup"><span data-stu-id="5f8ca-133">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

[<span data-ttu-id="5f8ca-134">Cambiar los números de teléfono de su puente de Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="5f8ca-134">Change the phone numbers on your Audio Conferencing bridge</span></span>](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)
