---
title: "Configurar la red para difundir reunión de Skype"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: dfa736b9-4920-4f48-b8c0-b5487ec6086f
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: SMB
description: "Obtenga información acerca de la característica de difusión de la reunión de Skype de Skype para los negocios en línea que le permite programar, producen y difusión de reuniones o eventos a grandes audiencias en línea hasta 10.000 asistentes."
ms.openlocfilehash: 3e4afb09d6a65654af418e14cc124e3c78dc0e0c
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a><span data-ttu-id="4dfa2-103">Configurar la red para difundir reunión de Skype</span><span class="sxs-lookup"><span data-stu-id="4dfa2-103">Set up your network for Skype Meeting Broadcast</span></span>

<span data-ttu-id="4dfa2-104">Después de [Habilitar la difusión de reunión Skype](enable-skype-meeting-broadcast.md) difusión de reunión Skype, debe configurar la red.</span><span class="sxs-lookup"><span data-stu-id="4dfa2-104">After you [Enable Skype Meeting Broadcast](enable-skype-meeting-broadcast.md) Skype Meeting Broadcast, you need to configure your network.</span></span> <span data-ttu-id="4dfa2-105">Realice este paso si desea celebrar seminarios y otras difusiones para personas fuera de su negocio.</span><span class="sxs-lookup"><span data-stu-id="4dfa2-105">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span>
  
<span data-ttu-id="4dfa2-106">Si no experimentados con la configuración del servidor de seguridad, considere la posibilidad de contratar a un [socio de Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para realizar este paso para usted.</span><span class="sxs-lookup"><span data-stu-id="4dfa2-106">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
<span data-ttu-id="4dfa2-107">Para omitir este paso y en su lugar agregar otra empresa para la federación para invitarlos a las difusiones, siga los pasos de [Permitir a los usuarios ponerse en contacto con Skype externo para usuarios empresariales](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span><span class="sxs-lookup"><span data-stu-id="4dfa2-107">To skip this step and instead add another business to your federation so you can invite them to broadcasts, follow the steps in [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span>
  
## <a name="step-1-set-up-allowed-domains"></a><span data-ttu-id="4dfa2-108">Paso 1: Configurar dominios permitidos</span><span class="sxs-lookup"><span data-stu-id="4dfa2-108">Step 1: Set up allowed domains</span></span>

<span data-ttu-id="4dfa2-109">Utilice **uno** de los métodos siguientes para configurar dominios permitidos:</span><span class="sxs-lookup"><span data-stu-id="4dfa2-109">Use **one** of the following methods to set up allowed domains:</span></span>
  
### 

 <span data-ttu-id="4dfa2-110">**Método 1: Utilizar el centro de administración de Office 365**</span><span class="sxs-lookup"><span data-stu-id="4dfa2-110">**Method 1: Use the Office 365 admin center**</span></span>
  
1. <span data-ttu-id="4dfa2-111">Ir al **Centro de administración de Office 365** y, a continuación, haga clic en **configuración**en la barra de navegación izquierda, > **servicios &amp; complementos**y, a continuación, elija **Skype para el negocio**.</span><span class="sxs-lookup"><span data-stu-id="4dfa2-111">Go to the **Office 365 admin center** and then in the left nav, click **Settings** > **Services &amp; add-ins**, and then choose **Skype for Business**.</span></span>
    
2. <span data-ttu-id="4dfa2-112">En la página **Compartir externo** en **excepciones de dominio**, seleccione **todos los dominios están bloqueados excepto**y escriba los siguientes dominios separados con una coma (,):</span><span class="sxs-lookup"><span data-stu-id="4dfa2-112">On the **External sharing** page under **Domain exceptions**, select **All domains are blocked except**, and enter the following domains, separated with a comma (,):</span></span>
    
  - <span data-ttu-id="4dfa2-113">noammeetings.Lync.com</span><span class="sxs-lookup"><span data-stu-id="4dfa2-113">noammeetings.lync.com</span></span>
    
  - <span data-ttu-id="4dfa2-114">emeameetings.Lync.com</span><span class="sxs-lookup"><span data-stu-id="4dfa2-114">emeameetings.lync.com</span></span>
    
  - <span data-ttu-id="4dfa2-115">apacmeetings.Lync.com</span><span class="sxs-lookup"><span data-stu-id="4dfa2-115">apacmeetings.lync.com</span></span>
    
  - <span data-ttu-id="4dfa2-116">Resources.Lync.com</span><span class="sxs-lookup"><span data-stu-id="4dfa2-116">resources.lync.com</span></span>
    
3. <span data-ttu-id="4dfa2-117">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="4dfa2-117">Click **Save**.</span></span>
    
### 

 <span data-ttu-id="4dfa2-118">**Método 2: Usar Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="4dfa2-118">**Method 2: Use Windows PowerShell**</span></span>
  
- <span data-ttu-id="4dfa2-119">En el **Menú Inicio**, haga clic en **Windows PowerShell** y haga clic en **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="4dfa2-119">From the **Start Menu**, right-click **Windows PowerShell** and click **Run as administrator**.</span></span> <span data-ttu-id="4dfa2-120">En la ventana **De Windows PowerShell** , escriba cada línea y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="4dfa2-120">In the **Windows PowerShell** window, type each line and press Enter.</span></span>
    
  ```
  $r = New-CsEdgeDomainPattern -Domain "noammeetings.lync.com"
  ```

  ```
  $s = New-CsEdgeDomainPattern -Domain "emeameetings.lync.com"
  ```

  ```
  $t = New-CsEdgeDomainPattern -Domain "apacmeetings.lync.com"
  ```

  ```
  $n = New-CsEdgeDomainPattern -Domain "resources.lync.com"
  ```

  ```
  $newAllowList = New-CsEdgeAllowList -AllowedDomain $r,$s,$t,$n
  ```

  ```
  Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList
  ```

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a><span data-ttu-id="4dfa2-121">Paso 2: Agregar Skype reunión difusión dominios, direcciones URL e IP direcciones</span><span class="sxs-lookup"><span data-stu-id="4dfa2-121">Step 2: Add Skype Meeting Broadcast domains, URLs, and IP addresses</span></span>

<span data-ttu-id="4dfa2-122">El segundo paso en el proceso de instalación es agregar primero los dominios que son necesarios y, a continuación, agregar las direcciones IP y las direcciones URL que son necesarias para la difusión de reunión Skype trabajar.</span><span class="sxs-lookup"><span data-stu-id="4dfa2-122">The second step in the setup process is for you to first add domains that are needed and then add IP addresses and URLs that are required for Skype Meeting Broadcast to work.</span></span>
  
- <span data-ttu-id="4dfa2-123">**Agregar el Skype necesario para los negocios en línea de direcciones URL de extremo y se requieren direcciones IP viendo cuáles** [aquí](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).</span><span class="sxs-lookup"><span data-stu-id="4dfa2-123">**Add the required Skype for Business Online endpoint URLs and IP addresses by seeing which ones are required**[here](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).</span></span>
    
## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a><span data-ttu-id="4dfa2-124">Configurar difusión de reunión de Skype en las organizaciones y las implementaciones de híbrido</span><span class="sxs-lookup"><span data-stu-id="4dfa2-124">Set up Skype Meeting Broadcast in Hybrid deployments and organizations</span></span>

<span data-ttu-id="4dfa2-125">Si tiene un Skype para una implementación local de Lync Server 2010, Microsoft Lync Server 2013 y Skype y organización empresarial en línea para Business Server 2015 y tiene tanto los usuarios en línea y local, existen otros pasos de configuración que se debe hacer en Además de las anteriores permiten a su organización local para comunicarse con Skype para los negocios en línea y permitir que todos los usuarios puedan crear y unirse a una reunión de Skype difusión.</span><span class="sxs-lookup"><span data-stu-id="4dfa2-125">If you have a Skype for Business Online organization and an on-premises deployment of Lync Server 2010, Microsoft Lync Server 2013, and Skype for Business Server 2015 and have users both online and on-premises, there are other setup steps that you will need to do in addition to the ones above to enable your on-premises organization to communicate with Skype for Business Online and allow all of your users to be able to create and join a Skype Meeting Broadcast.</span></span> <span data-ttu-id="4dfa2-126">Para ver cuáles son los requisitos, consulte [configurar su implementación local para difundir reunión de Skype](https://go.microsoft.com/fwlink/?LinkId=617070).</span><span class="sxs-lookup"><span data-stu-id="4dfa2-126">To see what those requirements are, see [Configure your on-premises deployment for Skype Meeting Broadcast](https://go.microsoft.com/fwlink/?LinkId=617070).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="4dfa2-127">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="4dfa2-127">Related topics</span></span>

[<span data-ttu-id="4dfa2-128">Habilitar la difusión de la reunión de Skype</span><span class="sxs-lookup"><span data-stu-id="4dfa2-128">Enable Skype Meeting Broadcast</span></span>](enable-skype-meeting-broadcast.md)
  
[<span data-ttu-id="4dfa2-129">URL de Office 365 e intervalos de direcciones IP</span><span class="sxs-lookup"><span data-stu-id="4dfa2-129">Office 365 URLs and IP address ranges</span></span>](http://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[<span data-ttu-id="4dfa2-130">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="4dfa2-130">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  

