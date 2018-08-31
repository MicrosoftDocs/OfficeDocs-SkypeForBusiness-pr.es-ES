---
title: Activar o desactivar la entrada y salida de anuncios para reuniones en Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Obtenga información sobre cómo activar o desactivar la entrada y salida de anuncios en una reunión de Skype for Business Online usando el centro de administración de Skype for Business. '
ms.openlocfilehash: 874624c3d7cfb184f4206f61cf2a91a67eb2e2cd
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2018
ms.locfileid: "23779039"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-skype-for-business-online"></a><span data-ttu-id="be1d8-103">Activar o desactivar la entrada y salida de anuncios para reuniones en Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="be1d8-103">Turn on or off entry and exit announcements for meetings in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="be1d8-104">Para obtener información acerca de anuncios de entrada y salida en Microsoft Teams, vea [Activar o desactivar los anuncios de entrada y salida para las reuniones en Microsoft Teams](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams).</span><span class="sxs-lookup"><span data-stu-id="be1d8-104">For information about entry and exit announcements in Microsoft Teams, see [Turn on or off entry and exit announcements for meetings in Microsoft Teams](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams).</span></span>

<span data-ttu-id="be1d8-105">Cuando establece una audioconferencia en Office 365, obtendrá un puente de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="be1d8-105">When you are setting up Audio Conferencing in Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="be1d8-106">Un puente de conferencia puede contener uno o más números de teléfono que los usuarios utilizarán para llamar a una reunión de Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="be1d8-106">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Skype for Business meeting.</span></span> 
  
<span data-ttu-id="be1d8-107">El puente de conferencia responde a una llamada de un usuario que llama a una reunión mediante un teléfono.</span><span class="sxs-lookup"><span data-stu-id="be1d8-107">The dial-in conferencing or audio conferencing bridge answers a call for a user that is dialing into a meeting using a phone.</span></span> <span data-ttu-id="be1d8-108">El puente de conferencia responde el autor de la llamada con mensajes de voz de un operador automático de conferencia y, a continuación, dependiendo de la configuración, puede reproducir notificaciones, pedir a los autores de llamadas que graben su nombre y que configuren la seguridad de PIN.</span><span class="sxs-lookup"><span data-stu-id="be1d8-108">The conferencing bridge answers a call and prompts the caller with voice prompts using a meeting auto attendant and then depending on your settings can play notifications, ask callers to record their name and controls the PIN settings.</span></span> <span data-ttu-id="be1d8-109">Se da un PIN a un organizador de Skype for Business, y este les permite iniciar una reunión si no pueden iniciar la reunión utilizando la aplicación de Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="be1d8-109">A PIN is given to a Skype for Business meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Skype for Business app.</span></span> <span data-ttu-id="be1d8-110">Sin embargo, lo puede establecer para que no sea necesario un PIN para iniciar una reunión.</span><span class="sxs-lookup"><span data-stu-id="be1d8-110">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="be1d8-111">Configurar las opciones para unirse a una reunión</span><span class="sxs-lookup"><span data-stu-id="be1d8-111">Setting meeting join options</span></span>
    
1. <span data-ttu-id="be1d8-112">En el **centro de administración de Skype for Business**, en la navegación izquierda, vaya a **Audioconferencia** > **Configuración de puente de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="be1d8-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="be1d8-113">En **Experiencia de unirse a una reunión**, active o desactive **Habilitar las notificaciones de entrada o salida**.</span><span class="sxs-lookup"><span data-stu-id="be1d8-113">Under ** Meeting join experience** > check or uncheck Enable meeting entry and exit notifications to be turned on This is selected by default.</span></span> <span data-ttu-id="be1d8-114">Esta opción está seleccionada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="be1d8-114">This is selected by default.</span></span> <span data-ttu-id="be1d8-115">Si se desactiva, los usuarios que ya se han unido a la reunión no recibirá una notificación cuando alguien entre o salga de la reunión.</span><span class="sxs-lookup"><span data-stu-id="be1d8-115">However if you uncheck it, users that have already joined the meeting won't be notified that someone enters or leaves the meeting</span></span>
    
3. <span data-ttu-id="be1d8-116">En **Tipo de anuncio de entrada o salida**, seleccione **Nombres o números de teléfono** o **Tonos**.</span><span class="sxs-lookup"><span data-stu-id="be1d8-116">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
4. <span data-ttu-id="be1d8-117">Active o desactive **Pedir a los autores de llamadas que graben su nombre antes de unirse a la reunión**.</span><span class="sxs-lookup"><span data-stu-id="be1d8-117">Ask callers to record their name before joining the meeting</span></span>
    
5. <span data-ttu-id="be1d8-118">Después de realizar los cambios, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="be1d8-118">After you make your changes, click **Save**.</span></span>
    

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="be1d8-119">¿Desea saber cómo administrar con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="be1d8-119">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="be1d8-120">Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/en-us/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="be1d8-120">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/en-us/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet.</span></span>
    
-  <span data-ttu-id="be1d8-p104">Cuando se trata de Windows PowerShell, Skype Empresarial Online se centra en la administración de usuarios y en determinar qué pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tiene varias tareas que realizar. Para empezar a usar Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="be1d8-p104">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="be1d8-124">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="be1d8-124">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="be1d8-125">Las mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="be1d8-125">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="be1d8-126">Windows PowerShell tiene muchas ventajas en velocidad, simplificidad y productividad respecto a utilizar únicamente el centro de administración de Office 365, como, por ejemplo, al realizar cambios de configuración para muchos usuarios en una única ubicación.</span><span class="sxs-lookup"><span data-stu-id="be1d8-126">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="be1d8-127">Más información sobre estas ventajas en los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="be1d8-127">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="be1d8-128">Introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="be1d8-128">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="be1d8-129">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="be1d8-129">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="be1d8-130">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="be1d8-130">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="be1d8-p106">El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="be1d8-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="be1d8-133">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="be1d8-133">Related topics</span></span>

[<span data-ttu-id="be1d8-134">Preguntas comunes sobre audioconferencias</span><span class="sxs-lookup"><span data-stu-id="be1d8-134">Audio Conferencing common questions</span></span>](/MicrosoftTeams/audio-conferencing-common-questions)
