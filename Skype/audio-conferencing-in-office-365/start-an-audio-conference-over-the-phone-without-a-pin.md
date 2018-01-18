---
title: "Iniciar una conferencia de Audio por teléfono sin un PIN"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn how to enable or disable anonymous callers from joining a meeting from the Skype for Business admin center or using a PowerShell script. '
ms.openlocfilehash: c77921af87cab23b475c31205da4661755c56961
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin"></a><span data-ttu-id="07147-103">Iniciar una conferencia de Audio por teléfono sin un PIN</span><span class="sxs-lookup"><span data-stu-id="07147-103">Start an Audio Conference over the phone without a PIN</span></span>

<span data-ttu-id="07147-104">Puede ser frustrante para los usuarios que llamen a una reunión que se celebrará en la sala de la reunión escuchar música porque el Skype para el organizador de la reunión de negocios o Teams de Microsoft no ha comenzado la reunión.</span><span class="sxs-lookup"><span data-stu-id="07147-104">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Skype for Business or Microsoft Teams meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="07147-105">Si llama a un organizador de la reunión la reunión, de forma predeterminada, se requiere un PIN para iniciar una reunión.</span><span class="sxs-lookup"><span data-stu-id="07147-105">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="07147-106">Puede configurar, por lo que cualquiera puede llamar a una reunión y no se le pida un PIN iniciar la reunión.</span><span class="sxs-lookup"><span data-stu-id="07147-106">You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="07147-107">Puede utilizar el Skype para el centro de administración de negocios para habilitar o deshabilitar a esta configuración para un único usuario.</span><span class="sxs-lookup"><span data-stu-id="07147-107">You can use the Skype for Business admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="07147-108">Un PIN no es necesario para el organizador de la reunión si alguien ha iniciado la conferencia desde un Skype para la aplicación de negocios o Teams de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="07147-108">A PIN isn't required for the meeting organizer if someone has started the meeting from a Skype for Business or Microsoft Teams app.</span></span> <span data-ttu-id="07147-109">Un PIN sólo es necesario cuando el organizador de una reunión se une a la reunión a través de un teléfono.</span><span class="sxs-lookup"><span data-stu-id="07147-109">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="07147-110">El NIP de reuniones se envía al usuario audio cuando se asignan a la licencia de **Conferencias de Audio** y están habilitados para conferencias de Audio.</span><span class="sxs-lookup"><span data-stu-id="07147-110">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="07147-111">Ver [mensajes de correo electrónico que se envían automáticamente a los usuarios al cambia su configuración de conferencia de Audio](emails-sent-to-users-when-their-settings-change.md)y [Enviar un correo electrónico a un usuario con su información de conferencia de Audio](send-an-email-to-a-user-with-their-dial-in-information.md) .</span><span class="sxs-lookup"><span data-stu-id="07147-111">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="07147-112">Habilitar o deshabilitar la posibilidad de que los autores de llamada anónimos se unan a la reunión</span><span class="sxs-lookup"><span data-stu-id="07147-112">Enable or disable anonymous callers from joining a meeting</span></span>

1. <span data-ttu-id="07147-113">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="07147-113">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="07147-114">Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="07147-114">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="07147-115">En el **Skype para el centro de administración de negocios**, en la exploración de la izquierda, vaya a las **conferencias de Audio** > **usuarios**.</span><span class="sxs-lookup"><span data-stu-id="07147-115">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**.</span></span> 
    
4. <span data-ttu-id="07147-116">En la lista, seleccione el usuario y en el panel Acción, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="07147-116">In the list, select the user and in the Action pane click **Edit**.</span></span> 
    
5. <span data-ttu-id="07147-117">En la página de propiedades del usuario, en **Opciones de la reunión**, active o desactive Permitir no autenticado a **quienes llaman para ser los primeros en una reunión. Si no, a continuación, esperan en la sala de espera hasta que un usuario autenticado se une**.</span><span class="sxs-lookup"><span data-stu-id="07147-117">On the user's properties page, under **Meeting options**, select or clear **Allow unauthenticated callers to be the first people in a meeting. If not, then they will wait in the lobby until an authenticated user joins**.</span></span>
    
6. <span data-ttu-id="07147-118">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="07147-118">Click **Save**.</span></span> 
    
 <span data-ttu-id="07147-119">**Para habilitar o deshabilitar a los llamadores anónimos a todas las reuniones, del usuario con Windows Powershell**</span><span class="sxs-lookup"><span data-stu-id="07147-119">**To enable or disable anonymous callers to all of your user's meetings using Windows Powershell**</span></span>
  
- <span data-ttu-id="07147-120">Ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="07147-120">Run the following:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="07147-121">¿Qué más debe saber?</span><span class="sxs-lookup"><span data-stu-id="07147-121">What else should you know?</span></span>

- <span data-ttu-id="07147-122">Si desea restablecer el PIN, consulte [Restablecer el PIN de conferencia de Audio para un usuario](reset-the-audio-conferencing-pin-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="07147-122">If you want to reset the PIN, see [Reset the Audio Conferencing PIN for a user](reset-the-audio-conferencing-pin-for-a-user.md).</span></span>
    
- <span data-ttu-id="07147-123">Si está habilitado el acceso anónimo o que no requiere un PIN iniciar una reunión:</span><span class="sxs-lookup"><span data-stu-id="07147-123">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="07147-124">Si no ha iniciado la reunión (hay nadie en la reunión todavía): un llamador se preguntará si es el organizador; Si contesta Sí, pedirá su PIN y después de él escribe el NIP, se iniciará la sesión y el usuario unirá a la reunión.</span><span class="sxs-lookup"><span data-stu-id="07147-124">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="07147-125">Si la reunión ya inició (alguien ya está en la reunión): no se solicita un llamador si es el organizador y nunca se pedirá el PIN; ya se ha iniciado la sesión y unirá a la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="07147-125">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="07147-126">Si se deshabilita el acceso anónimo o que no requiere un PIN iniciar una reunión:</span><span class="sxs-lookup"><span data-stu-id="07147-126">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="07147-127">Si no ha iniciado la reunión (hay nadie en la reunión aún): no se solicita un llamador si es el organizador y nunca se pedirá el PIN.</span><span class="sxs-lookup"><span data-stu-id="07147-127">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="07147-128">Debido a la configuración del organizador se establece en off, se iniciará la reunión y los llamadores anónimos se unirá a la reunión.</span><span class="sxs-lookup"><span data-stu-id="07147-128">Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="07147-129">Si la reunión ya inició (alguien ya está en la reunión): no se solicita un llamador si es el organizador y nunca se pedirá el PIN; ya se ha iniciado la sesión y unirá a la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="07147-129">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="07147-130">¿Desea saber cómo administrar con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="07147-130">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="07147-131">Para ahorrar tiempo o automatizar este proceso para más de un usuario, puede usar el cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).</span><span class="sxs-lookup"><span data-stu-id="07147-131">To save time or automate this for more than one user, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet.</span></span>
    
-  <span data-ttu-id="07147-p104">Cuando se trata de Windows PowerShell, Skype Empresarial Online se centra en la administración de usuarios y en determinar qué pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tiene varias tareas que realizar. Para empezar a usar Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="07147-p104">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - <span data-ttu-id="07147-135">Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="07147-135">[Why you need to use Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)</span></span>
    
  - [<span data-ttu-id="07147-136">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="07147-136">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="07147-137">Windows PowerShell tiene muchas ventajas en velocidad, simplicidad y productividad sobre utilizando sólo el centro de administración de Office 365, como cuando realice cambios en la configuración de muchos usuarios al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="07147-137">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="07147-138">Obtenga información acerca de estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="07147-138">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="07147-139">Introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="07147-139">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="07147-140">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="07147-140">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="07147-141">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="07147-141">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="07147-p106">El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="07147-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="07147-144">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="07147-144">Related topics</span></span>

[<span data-ttu-id="07147-145">Configurar Audioconferencia para Skype Empresarial y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="07147-145">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
