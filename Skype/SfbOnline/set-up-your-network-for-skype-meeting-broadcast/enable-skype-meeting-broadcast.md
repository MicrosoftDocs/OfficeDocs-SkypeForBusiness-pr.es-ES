---
title: Habilitar la Difusión de reunión de Skype
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: 5299cce0-850e-42dc-b6ae-2d0ee775c4a9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- SMB
description: Antes de que los usuarios de su organización puedan Skype difusión de reunión, debe habilitarla. Para ello, debe saber cómo usar Windows PowerShell. Si no tiene experiencia con Windows PowerShell, analice contratar un socio de Microsoft para que lleve a cabo este paso por usted.
ms.openlocfilehash: 6cdd7f12483025697b139203907f87f9cd3dc764
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237016"
---
# <a name="enable-skype-meeting-broadcast"></a><span data-ttu-id="15efc-105">Habilitar la Difusión de reunión de Skype</span><span class="sxs-lookup"><span data-stu-id="15efc-105">Enable Skype Meeting Broadcast</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!IMPORTANT]
> <span data-ttu-id="15efc-106">Skype Empresarial Online se retirará el 31 de julio de 2021, momento en el que finalizará el acceso al servicio.</span><span class="sxs-lookup"><span data-stu-id="15efc-106">Skype for Business Online is retiring on July 31, 2021, at which time access to the service will end.</span></span> <span data-ttu-id="15efc-107">Animamos a los clientes a comenzar la actualización a Microsoft Teams, el cliente principal para las comunicaciones y el trabajo en equipo en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="15efc-107">We encourage customers to begin the upgrade to Microsoft Teams, the core client for communications and teamwork in Microsoft 365.</span></span>

<span data-ttu-id="15efc-108">Antes de que los usuarios de su organización puedan Skype difusión de reunión, debe habilitarla.</span><span class="sxs-lookup"><span data-stu-id="15efc-108">Before the people in your organization can use Skype Meeting Broadcast, you need to enable it.</span></span> <span data-ttu-id="15efc-109">Para ello, debe saber cómo usar Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="15efc-109">To do this, you need to know how to use Windows PowerShell.</span></span> <span data-ttu-id="15efc-110">Si no tiene experiencia con Windows PowerShell, analice contratar un [socio de Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para que lleve a cabo este paso por usted.</span><span class="sxs-lookup"><span data-stu-id="15efc-110">If you don't know Windows PowerShell, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>



> [!NOTE]
> <span data-ttu-id="15efc-111">El Microsoft Teams de administración ha sustituido al Skype Empresarial de administración (portal heredado).</span><span class="sxs-lookup"><span data-stu-id="15efc-111">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="15efc-112">Todas las opciones de Skype Empresarial están ahora en el centro Teams administración.</span><span class="sxs-lookup"><span data-stu-id="15efc-112">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="15efc-113">Debe tener asignado el rol de administrador de [Azure AD](/azure/active-directory/roles/permissions-reference) de administrador global o Skype Empresarial administrador para administrar Skype Empresarial características en el centro Teams administración.</span><span class="sxs-lookup"><span data-stu-id="15efc-113">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="15efc-114">Para conocer más, consulte [Administrar la configuración de Skype empresarial en el Centro de administración de Microsoft Teams](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json)</span><span class="sxs-lookup"><span data-stu-id="15efc-114">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span></span>

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a><span data-ttu-id="15efc-115">Habilitar Difusión de reunión de Skype mediante el Centro de administración de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="15efc-115">Enable Skype Meeting Broadcast using the Skype for Business admin center</span></span>

<span data-ttu-id="15efc-116">![Icono que muestra el logotipo de Skype Empresarial](../images/sfb-logo-30x30.png) **Usar el Centro de administración de Skype Empresarial**</span><span class="sxs-lookup"><span data-stu-id="15efc-116">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="15efc-117">Inicie sesión con su cuenta de administrador global o Skype Empresarial cuenta de administrador en [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) .</span><span class="sxs-lookup"><span data-stu-id="15efc-117">Sign in with your global admin account or Skype for Business admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
2. <span data-ttu-id="15efc-118">En el centro de administración, vaya a Centros **de**  >  **administración Teams**.</span><span class="sxs-lookup"><span data-stu-id="15efc-118">In the admin center, go to **Admin centers** > **Teams**.</span></span>
    
3. <span data-ttu-id="15efc-119">En el **Teams de** administración, vaya a **Portal** heredado En línea Reuniones en línea Difundir reuniones y, a  >    >  continuación, seleccione Habilitar **Skype difusión de reunión**.</span><span class="sxs-lookup"><span data-stu-id="15efc-119">In the **Teams admin center**, go to **Legacy portal** > **Online meetings** > **Broadcast meetings**, and then select **Enable Skype Meeting Broadcast**.</span></span>
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a><span data-ttu-id="15efc-120">Habilitar la Difusión de reunión de Skype mediante PowerShell</span><span class="sxs-lookup"><span data-stu-id="15efc-120">Enable Skype Meeting Broadcast using PowerShell</span></span>

1. <span data-ttu-id="15efc-121">Instale el [Teams PowerShell](/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="15efc-121">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="15efc-122">Abra un Windows PowerShell de comandos y ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="15efc-122">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
3. <span data-ttu-id="15efc-123">Confirme la configuración actual de Difusión de reunión de Skype ejecutando el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="15efc-123">Confirm your current Skype Meeting Broadcast configuration by running:</span></span>
    
   ```PowerShell
   Get-CsBroadcastMeetingConfiguration
   ```

    <span data-ttu-id="15efc-124">Compruebe que el parámetro  _EnableBroadcastMeeting_ está establecido como `False`.</span><span class="sxs-lookup"><span data-stu-id="15efc-124">Verify that the parameter  _EnableBroadcastMeeting_ is set to `False`.</span></span>
    
     ![Habilitar cmdlet de organización en una Difusión de reunión de Skype.](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. <span data-ttu-id="15efc-126">Habilite la Difusión de reunión de Skype para su organización ejecutando el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="15efc-126">Enable Skype Meeting Broadcast for your organization by running:</span></span>
    
   ```PowerShell
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    <span data-ttu-id="15efc-127">Puede confirmar que la configuración está habilitada ejecutándose de  `Get-CsBroadcastMeetingConfiguration` nuevo.</span><span class="sxs-lookup"><span data-stu-id="15efc-127">You can confirm that the setting is enabled by running  `Get-CsBroadcastMeetingConfiguration` again.</span></span>
    
     ![Habilitar cmdlet de organización en una Difusión de reunión de Skype.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > <span data-ttu-id="15efc-129">Después de realizar el cambio, es posible que tarde hasta una hora en surtir efecto en el portal de Difusión de reunión de Skype.</span><span class="sxs-lookup"><span data-stu-id="15efc-129">After you make the change, it may take up to an hour to take effect in the Skype Meeting Broadcast portal.</span></span> 
  
10. <span data-ttu-id="15efc-p105">Los usuarios ahora pueden realizar reuniones de difusión con otros usuarios de su empresa. Para que puedan empezar, pídales que lean [¿Qué es una Difusión de reunión de Skype?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span><span class="sxs-lookup"><span data-stu-id="15efc-p105">Your users can now hold broadcast meetings with other users in your business. To get them started, point them to [What is a Skype Meeting Broadcast?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span></span>
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a><span data-ttu-id="15efc-132">Configurar su red para difundir reuniones con asistentes externos</span><span class="sxs-lookup"><span data-stu-id="15efc-132">Configure your network to broadcast meetings with external attendees</span></span>

<span data-ttu-id="15efc-133">Si tiene un firewall y quiere realizar difusiones con personas que no pertenecen a su empresa (que no son una empresa federada), tendrá que configurar su red con estas instrucciones: [Configurar la red para Difusión de reunión de Skype](set-up-your-network-for-skype-meeting-broadcast.md).</span><span class="sxs-lookup"><span data-stu-id="15efc-133">If you have a firewall, and you want to hold broadcasts with people outside of your business (who are not a federated business), you need to configure your network using these instructions: [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> 
  
<span data-ttu-id="15efc-134">Si no tiene experiencia con la configuración del firewall, analice contratar un [socio de Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para que lleve a cabo este paso por usted.</span><span class="sxs-lookup"><span data-stu-id="15efc-134">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
<span data-ttu-id="15efc-135">Para omitir este paso y, en su lugar, agregar otra empresa a su federación, siga los pasos en [Permitir que los usuarios se pongan en contacto con usuarios externos de Skype Empresarial](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span><span class="sxs-lookup"><span data-stu-id="15efc-135">To skip this step and instead add another business to your federation, see [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="15efc-136">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="15efc-136">Related topics</span></span>

[<span data-ttu-id="15efc-137">Introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="15efc-137">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
[<span data-ttu-id="15efc-138">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="15efc-138">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
