---
title: Habilitar la Difusión de reunión de Skype
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 5299cce0-850e-42dc-b6ae-2d0ee775c4a9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- SMB
description: Antes de que los miembros de su organización puedan usar Difusión de reunión de Skype, usted deberá habilitarla. Para llevar a cabo este paso, tiene que saber cómo usar Windows PowerShell. Si no tiene experiencia con Windows PowerShell, analice contratar un socio de Microsoft para que lleve a cabo este paso por usted.
ms.openlocfilehash: f2c95e16a091c79425ea508f557a78f91ce1262f
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="enable-skype-meeting-broadcast"></a><span data-ttu-id="4d047-105">Habilitar la Difusión de reunión de Skype</span><span class="sxs-lookup"><span data-stu-id="4d047-105">Enable Skype Meeting Broadcast</span></span>

<span data-ttu-id="4d047-p102">[] Antes de que los miembros de su organización puedan usar Difusión de reunión de Skype, usted deberá habilitarla. Para llevar a cabo este paso, tiene que saber cómo usar Windows PowerShell. Si no tiene experiencia con Windows PowerShell, analice contratar un [socio de Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para que lleve a cabo este paso por usted.</span><span class="sxs-lookup"><span data-stu-id="4d047-p102">Before the people in your organization can use Skype Meeting Broadcast, you need to enable it. To do this, you need to know how to use Windows PowerShell. If you don't know Windows PowerShell, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="4d047-p103">Difusión de reunión de Skype está desactivada de manera predeterminada porque la distribución del contenido multimedia de una reunión de difusión usa Red de entrega de contenido (CDN) de Microsoft Azure para conseguir una escala realmente elevada y ser compatible con las miles de personas que están viendo la difusión. El contenido multimedia agrupado que pasa a través de la CDN está cifrado, y el caché de CDN tiene un tiempo de vida limitado. Además, es posible que el componente de CDN de Azure todavía no satisfaga todos los elementos de las cláusulas modelo de la UE que deriva de la Directiva de protección de datos de la UE. Al habilitar esta característica, da por hecho que conoce esta advertencia.</span><span class="sxs-lookup"><span data-stu-id="4d047-p103">Skype Meeting Broadcast is turned off by default because distribution of the media content of a broadcast meeting uses Microsoft Azure's Content Delivery Network (CDN) to achieve very high scale to support thousands of people watching a broadcast. The chunked media content passing through the CDN is encrypted, and the CDN cache has a limited lifetime. Also, the Azure CDN component may not yet meet all elements of the EU Model Clauses stemming from the EU Data Protection Directive. By enabling this feature, you acknowledge this notice.</span></span> 
  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a><span data-ttu-id="4d047-113">Habilitar Difusión de reunión de Skype mediante el Centro de administración de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="4d047-113">Enable Skype Meeting Broadcast using the Skype for Business admin center</span></span>

1. <span data-ttu-id="4d047-114">Inicie sesión con su cuenta de administrador global de Office 365 en [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span><span class="sxs-lookup"><span data-stu-id="4d047-114">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
2. <span data-ttu-id="4d047-115">En el Centro de administración de Office 365, vaya a **Centros de administración** > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="4d047-115">In the Office 365 Admin center go to **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="4d047-116">En el **Skype para el centro de administración de negocios**, vaya a **las reuniones en línea** > **reuniones de difusión**y, a continuación, seleccione **Habilitar la difusión de reunión de Skype**.</span><span class="sxs-lookup"><span data-stu-id="4d047-116">In the **Skype for Business admin center**, go to **Online meetings** > **Broadcast meetings**, and then select **Enable Skype Meeting Broadcast**.</span></span>
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a><span data-ttu-id="4d047-117">Habilitar la Difusión de reunión de Skype mediante PowerShell</span><span class="sxs-lookup"><span data-stu-id="4d047-117">Enable Skype Meeting Broadcast using PowerShell</span></span>

1. <span data-ttu-id="4d047-118">Compruebe que está ejecutando la versión 3.0 o superior de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4d047-118">Verify that you are running version 3.0 or higher of Windows PowerShell.</span></span>
    
1. <span data-ttu-id="4d047-119">Para comprobar que ejecuta la versión 3.0 o superior: **menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="4d047-119">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="4d047-120">Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="4d047-120">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="4d047-p104">Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell. Vea [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para descargar y actualizar Windows PowerShell a la versión 4.0. Reinicie el equipo cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="4d047-p104">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="4d047-p105">También necesitará instalar el módulo Windows PowerShell para Skype Empresarial Online que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype Empresarial Online. Este módulo, que solo se admite en equipos de 64 bits, puede descargarse desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=294688). Reinicie el equipo cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="4d047-p105">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
2. <span data-ttu-id="4d047-127">En el **Menú Inicio**, elija **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="4d047-127">From the **Start Menu**, choose **Windows PowerShell**.</span></span>
    
3. <span data-ttu-id="4d047-128">En la ventana de **Windows PowerShell** y conéctese a su organización de Office 365 ejecutando el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="4d047-128">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
  ```
  $Credential = get-credential
  $O365Session = New-CsOnlineSession -Credential $credential
  Import-PSSession $O365Session
  ```

4. <span data-ttu-id="4d047-129">Confirme la configuración actual de Difusión de reunión de Skype ejecutando el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="4d047-129">Confirm your current Skype Meeting Broadcast configuration by running:</span></span>
    
  ```
  Get-CsBroadcastMeetingConfiguration
  ```

    <span data-ttu-id="4d047-130">Compruebe que el parámetro  _EnableBroadcastMeeting_ está establecido como `False`.</span><span class="sxs-lookup"><span data-stu-id="4d047-130">Verify that the parameter  _EnableBroadcastMeeting_ is set to `False`.</span></span>
    
     ![Habilitar cmdlet de organización en una Difusión de reunión de Skype.](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
5. <span data-ttu-id="4d047-132">Habilite la Difusión de reunión de Skype para su organización ejecutando el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="4d047-132">Enable Skype Meeting Broadcast for your organization by running:</span></span>
    
  ```
  Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
  ```

    <span data-ttu-id="4d047-133">Puede confirmar que la opción está habilitada volviendo a ejecutar  `Get-CsBroadcastMeetingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="4d047-133">You can confirm that the setting is enabled by running  `Get-CsBroadcastMeetingConfiguration` again.</span></span>
    
     ![Habilitar cmdlet de organización en una Difusión de reunión de Skype.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > <span data-ttu-id="4d047-135">Después de realizar el cambio, es posible que tarde hasta una hora en surtir efecto en el portal de Difusión de reunión de Skype.</span><span class="sxs-lookup"><span data-stu-id="4d047-135">After you make the change, it may take up to an hour to take effect in the Skype Meeting Broadcast portal.</span></span> 
  
6. <span data-ttu-id="4d047-p106">Los usuarios ahora pueden realizar reuniones de difusión con otros usuarios de su empresa. Para que puedan empezar, pídales que lean [¿Qué es una Difusión de reunión de Skype?](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span><span class="sxs-lookup"><span data-stu-id="4d047-p106">Your users can now hold broadcast meetings with other users in your business. To get them started, point them to [What is a Skype Meeting Broadcast?](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span></span>
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a><span data-ttu-id="4d047-138">Configurar su red para difundir reuniones con asistentes externos</span><span class="sxs-lookup"><span data-stu-id="4d047-138">Configure your network to broadcast meetings with external attendees</span></span>

<span data-ttu-id="4d047-139">Si tiene un firewall y quiere realizar difusiones con personas que no pertenecen a su empresa (que no son una empresa federada), tendrá que configurar su red con estas instrucciones: [Configurar la red para Difusión de reunión de Skype](set-up-your-network-for-skype-meeting-broadcast.md).</span><span class="sxs-lookup"><span data-stu-id="4d047-139">If you have a firewall, and you want to hold broadcasts with people outside of your business (who are not a federated business), you need to configure your network using these instructions: [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> 
  
<span data-ttu-id="4d047-140">Si no tiene experiencia con la configuración del firewall, analice contratar un [socio de Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para que lleve a cabo este paso por usted.</span><span class="sxs-lookup"><span data-stu-id="4d047-140">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
<span data-ttu-id="4d047-141">Para omitir este paso y, en su lugar, agregar otra empresa a su federación, siga los pasos en [Permitir que los usuarios se pongan en contacto con usuarios externos de Skype Empresarial](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span><span class="sxs-lookup"><span data-stu-id="4d047-141">To skip this step and instead add another business to your federation, see [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="4d047-142">See also</span><span class="sxs-lookup"><span data-stu-id="4d047-142">Related topics</span></span>

[<span data-ttu-id="4d047-143">Introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="4d047-143">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[<span data-ttu-id="4d047-144">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="4d047-144">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
 