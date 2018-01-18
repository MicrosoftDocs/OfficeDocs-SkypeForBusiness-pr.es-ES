---
title: "Habilitar la difusión de la reunión de Skype"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 5299cce0-850e-42dc-b6ae-2d0ee775c4a9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: SMB
description: "Antes de que las personas de su organización pueden utilizar Skype reunión difusión, debe habilitarlo. Para ello, necesita saber cómo usar Windows PowerShell. Si no conoce Windows PowerShell, considere la posibilidad de contratar a un socio de Microsoft para hacer este paso para usted."
ms.openlocfilehash: 975f0304f2053e23375c5eabc62ec224bedc02e7
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="enable-skype-meeting-broadcast"></a><span data-ttu-id="8d208-105">Habilitar la difusión de la reunión de Skype</span><span class="sxs-lookup"><span data-stu-id="8d208-105">Enable Skype Meeting Broadcast</span></span>

<span data-ttu-id="8d208-106">Antes de que las personas de su organización pueden utilizar Skype reunión difusión, debe habilitarlo.</span><span class="sxs-lookup"><span data-stu-id="8d208-106">Before the people in your organization can use Skype Meeting Broadcast, you need to enable it.</span></span> <span data-ttu-id="8d208-107">Para ello, necesita saber cómo usar Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8d208-107">To do this, you need to know how to use Windows PowerShell.</span></span> <span data-ttu-id="8d208-108">Si no conoce Windows PowerShell, considere la posibilidad de contratar a un [socio de Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para realizar este paso para usted.</span><span class="sxs-lookup"><span data-stu-id="8d208-108">If you don't know Windows PowerShell, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="8d208-109">Difusión de la reunión de Skype está desactivada de forma predeterminada porque la distribución del contenido multimedia de una reunión de difusión utiliza la red de entrega de contenido (CDN) de Microsoft Azure para lograr alta escala para soportar miles de personas viendo una difusión.</span><span class="sxs-lookup"><span data-stu-id="8d208-109">Skype Meeting Broadcast is turned off by default because distribution of the media content of a broadcast meeting uses Microsoft Azure's Content Delivery Network (CDN) to achieve very high scale to support thousands of people watching a broadcast.</span></span> <span data-ttu-id="8d208-110">Se cifra el contenido de medios fragmentada pasando por la CDN y la caché CDN tiene una vida limitada.</span><span class="sxs-lookup"><span data-stu-id="8d208-110">The chunked media content passing through the CDN is encrypted, and the CDN cache has a limited lifetime.</span></span> <span data-ttu-id="8d208-111">Además, el componente Azure CDN puede todavía cumple con todos los elementos de las cláusulas del modelo de la UE derivados de la directiva de protección de datos de la Unión Europea.</span><span class="sxs-lookup"><span data-stu-id="8d208-111">Also, the Azure CDN component may not yet meet all elements of the EU Model Clauses stemming from the EU Data Protection Directive.</span></span> <span data-ttu-id="8d208-112">Al habilitar esta característica, usted reconoce este aviso.</span><span class="sxs-lookup"><span data-stu-id="8d208-112">By enabling this feature, you acknowledge this notice.</span></span> 
  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a><span data-ttu-id="8d208-113">Habilitar Skype reunión difusión usando el Skype para el centro de administración de negocios</span><span class="sxs-lookup"><span data-stu-id="8d208-113">Enable Skype Meeting Broadcast using the Skype for Business admin center</span></span>

1. <span data-ttu-id="8d208-114">Inicie sesión con su cuenta de administrador global de Office 365 en [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span><span class="sxs-lookup"><span data-stu-id="8d208-114">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
2. <span data-ttu-id="8d208-115">En el centro de administración de Office 365, vaya a **centros de Admin** > **Skype para el negocio**.</span><span class="sxs-lookup"><span data-stu-id="8d208-115">In the Office 365 Admin center go to **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="8d208-116">En el **Skype para el centro de administración de negocios**, vaya a **las reuniones en línea** > **reuniones de difusión**y, a continuación, seleccione **Habilitar la difusión de reunión de Skype**.</span><span class="sxs-lookup"><span data-stu-id="8d208-116">In the **Skype for Business admin center**, go to **Online meetings** > **Broadcast meetings**, and then select **Enable Skype Meeting Broadcast**.</span></span>
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a><span data-ttu-id="8d208-117">Habilitar Skype reunión difusión usando PowerShell</span><span class="sxs-lookup"><span data-stu-id="8d208-117">Enable Skype Meeting Broadcast using PowerShell</span></span>

1. <span data-ttu-id="8d208-118">Compruebe que está ejecutando la versión 3.0 o posterior de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8d208-118">Verify that you are running version 3.0 or higher of Windows PowerShell.</span></span>
    
1. <span data-ttu-id="8d208-119">Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="8d208-119">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="8d208-120">Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="8d208-120">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="8d208-p104">Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell. Vea [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para descargar y actualizar Windows PowerShell a la versión 4.0. Reinicie el equipo cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="8d208-p104">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="8d208-p105">También necesitará instalar el módulo Windows PowerShell para Skype Empresarial Online que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype Empresarial Online. Este módulo, que solo se admite en equipos de 64 bits, puede descargarse desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=294688). Reinicie el equipo cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="8d208-p105">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
2. <span data-ttu-id="8d208-127">En el **Menú Inicio**, elija **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="8d208-127">From the **Start Menu**, choose **Windows PowerShell**.</span></span>
    
3. <span data-ttu-id="8d208-128">En la ventana **Windows PowerShell**, puede conectarse a su organización de Office 365 ejecutando:</span><span class="sxs-lookup"><span data-stu-id="8d208-128">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
  ```
  $Credential = get-credential
  $O365Session = New-CsOnlineSession -Credential $credential
  Import-PSSession $O365Session
  ```

4. <span data-ttu-id="8d208-129">Confirme su configuración de Skype reunión difusión actual ejecutando:</span><span class="sxs-lookup"><span data-stu-id="8d208-129">Confirm your current Skype Meeting Broadcast configuration by running:</span></span>
    
  ```
  Get-CsBroadcastMeetingConfiguration
  ```

    <span data-ttu-id="8d208-130">Compruebe que el parámetro _EnableBroadcastMeeting_ está establecido en `False`.</span><span class="sxs-lookup"><span data-stu-id="8d208-130">Verify that the parameter  _EnableBroadcastMeeting_ is set to `False`.</span></span>
    
     ![Cmdlet de Skype reunión difusión habilitar la organización.](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
5. <span data-ttu-id="8d208-132">Habilitar la difusión de reunión de Skype para su organización mediante la ejecución de:</span><span class="sxs-lookup"><span data-stu-id="8d208-132">Enable Skype Meeting Broadcast for your organization by running:</span></span>
    
  ```
  Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
  ```

    <span data-ttu-id="8d208-133">Puede confirmar que la configuración está habilitada mediante la ejecución de `Get-CsBroadcastMeetingConfiguration` otra vez.</span><span class="sxs-lookup"><span data-stu-id="8d208-133">You can confirm that the setting is enabled by running  `Get-CsBroadcastMeetingConfiguration` again.</span></span>
    
     ![Difusión de la reunión de Skype permiten Cmdlet de la organización.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > <span data-ttu-id="8d208-135">Después de realizar el cambio, puede tardar hasta una hora surtan efecto en el portal de difusión de la reunión de Skype.</span><span class="sxs-lookup"><span data-stu-id="8d208-135">After you make the change, it may take up to an hour to take effect in the Skype Meeting Broadcast portal.</span></span> 
  
6. <span data-ttu-id="8d208-136">Los usuarios ahora pueden contener difusión reuniones con otros usuarios de su negocio.</span><span class="sxs-lookup"><span data-stu-id="8d208-136">Your users can now hold broadcast meetings with other users in your business.</span></span> <span data-ttu-id="8d208-137">Para obtenerlas iniciado, remítales a [¿Qué es una reunión de Skype difusión?](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span><span class="sxs-lookup"><span data-stu-id="8d208-137">To get them started, point them to [What is a Skype Meeting Broadcast?](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span></span>
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a><span data-ttu-id="8d208-138">Configurar la red para difundir reuniones con asistentes externos</span><span class="sxs-lookup"><span data-stu-id="8d208-138">Configure your network to broadcast meetings with external attendees</span></span>

<span data-ttu-id="8d208-139">Si tiene un firewall, y que desea que conserve las difusiones con personas fuera de su empresa (que no sean un negocio federado), debe configurar la red con estas instrucciones: [Configurar la red para difundir reunión de Skype](set-up-your-network-for-skype-meeting-broadcast.md).</span><span class="sxs-lookup"><span data-stu-id="8d208-139">If you have a firewall, and you want to hold broadcasts with people outside of your business (who are not a federated business), you need to configure your network using these instructions: [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> 
  
<span data-ttu-id="8d208-140">Si no experimentados con la configuración del servidor de seguridad, considere la posibilidad de contratar a un [socio de Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para realizar este paso para usted.</span><span class="sxs-lookup"><span data-stu-id="8d208-140">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
<span data-ttu-id="8d208-141">Para omitir este paso y en su lugar agregar otra empresa para la federación, vea [Permitir a los usuarios ponerse en contacto con Skype externo para usuarios empresariales](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span><span class="sxs-lookup"><span data-stu-id="8d208-141">To skip this step and instead add another business to your federation, see [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="8d208-142">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="8d208-142">Related topics</span></span>

[<span data-ttu-id="8d208-143">Introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="8d208-143">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[<span data-ttu-id="8d208-144">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="8d208-144">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

