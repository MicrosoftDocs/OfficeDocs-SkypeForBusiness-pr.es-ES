---
title: Configurar la red para Difusión de reunión de Skype
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: dfa736b9-4920-4f48-b8c0-b5487ec6086f
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- SMB
description: Learn about the Skype Meeting Broadcast feature of Skype for Business Online that enables you to schedule, produce, and broadcast meetings or events to large online audiences up to 10,000 attendees.
ms.openlocfilehash: e1f10ad5036e2866cc480491e98bd2dd7396895a
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23862219"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a><span data-ttu-id="7ab01-103">Configurar la red para Difusión de reunión de Skype</span><span class="sxs-lookup"><span data-stu-id="7ab01-103">Set up your network for Skype Meeting Broadcast</span></span>

<span data-ttu-id="7ab01-104">Después de [Habilitar la difusión de reunión de Skype](enable-skype-meeting-broadcast.md) Difundir presentación de reunión de Skype, debe configurar la red.</span><span class="sxs-lookup"><span data-stu-id="7ab01-104">After you [Enable Skype Meeting Broadcast](enable-skype-meeting-broadcast.md) Skype Meeting Broadcast, you need to configure your network.</span></span> <span data-ttu-id="7ab01-105">Realice este paso si desea que se espera seminarios Web y otras difusiones para las personas de fuera de su negocio.</span><span class="sxs-lookup"><span data-stu-id="7ab01-105">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span>

<span data-ttu-id="7ab01-106">Si no tiene experiencia con la configuración del firewall, analice contratar un [socio de Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para que lleve a cabo este paso por usted.</span><span class="sxs-lookup"><span data-stu-id="7ab01-106">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>

<span data-ttu-id="7ab01-107">Para omitir este paso y en su lugar agregar otra empresa para la federación, por lo que puede invitarlos a las difusiones, siga los pasos de [Permitir a los usuarios ponerse en contacto con Skype externo para los usuarios empresariales](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span><span class="sxs-lookup"><span data-stu-id="7ab01-107">To skip this step and instead add another business to your federation so you can invite them to broadcasts, follow the steps in [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span>

## <a name="step-1-set-up-allowed-domains"></a><span data-ttu-id="7ab01-108">Paso 1: Configurar los dominios permitidos</span><span class="sxs-lookup"><span data-stu-id="7ab01-108">Step 1: Set up allowed domains</span></span>

<span data-ttu-id="7ab01-109">Utilice **uno** de los métodos siguientes para configurar los dominios permitidos:</span><span class="sxs-lookup"><span data-stu-id="7ab01-109">Use **one** of the following methods to set up allowed domains:</span></span>

###

 <span data-ttu-id="7ab01-110">**Método 1: Usar el centro de administración de Office 365**</span><span class="sxs-lookup"><span data-stu-id="7ab01-110">**Method 1: Use the Office 365 admin center**</span></span>

1. <span data-ttu-id="7ab01-111">Vaya al **Centro de administración de Office 365** y, a continuación, en el panel de navegación izquierdo, haga clic en **configuración de** > **servicios &amp; complementos**y, a continuación, elija **Skype para la empresa**.</span><span class="sxs-lookup"><span data-stu-id="7ab01-111">Go to the **Office 365 admin center** and then in the left nav, click **Settings** > **Services &amp; add-ins**, and then choose **Skype for Business**.</span></span>

2. <span data-ttu-id="7ab01-112">En la página de **uso compartido externo** , en **excepciones de dominio**, seleccione **todos los dominios están bloqueados, excepto**y especifique los siguientes dominios separados con una coma (,):</span><span class="sxs-lookup"><span data-stu-id="7ab01-112">On the **External sharing** page under **Domain exceptions**, select **All domains are blocked except**, and enter the following domains, separated with a comma (,):</span></span>

  - <span data-ttu-id="7ab01-113">noammeetings.Lync.com</span><span class="sxs-lookup"><span data-stu-id="7ab01-113">noammeetings.lync.com</span></span>

  - <span data-ttu-id="7ab01-114">emeameetings.Lync.com</span><span class="sxs-lookup"><span data-stu-id="7ab01-114">emeameetings.lync.com</span></span>

  - <span data-ttu-id="7ab01-115">apacmeetings.Lync.com</span><span class="sxs-lookup"><span data-stu-id="7ab01-115">apacmeetings.lync.com</span></span>

  - <span data-ttu-id="7ab01-116">Resources.Lync.com</span><span class="sxs-lookup"><span data-stu-id="7ab01-116">resources.lync.com</span></span>

3. <span data-ttu-id="7ab01-117">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="7ab01-117">Click **Save**.</span></span>

###

 <span data-ttu-id="7ab01-118">**Método 2: Uso de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="7ab01-118">**Method 2: Use Windows PowerShell**</span></span>

- <span data-ttu-id="7ab01-119">En el **Menú Inicio**, haga clic en **Windows PowerShell** y haga clic en **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="7ab01-119">From the **Start Menu**, right-click **Windows PowerShell** and click **Run as administrator**.</span></span> <span data-ttu-id="7ab01-120">In the **Windows PowerShell** window, type each line and press Enter.</span><span class="sxs-lookup"><span data-stu-id="7ab01-120">In the **Windows PowerShell** window, type each line and press Enter.</span></span>

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

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a><span data-ttu-id="7ab01-121">Paso 2: Agregar reunión Difundir presentación de Skype dominios, las direcciones URL, IP y direcciones</span><span class="sxs-lookup"><span data-stu-id="7ab01-121">Step 2: Add Skype Meeting Broadcast domains, URLs, and IP addresses</span></span>

<span data-ttu-id="7ab01-122">El segundo paso en el proceso de instalación es para que usted agregar dominios que son necesarios y, a continuación, agregue las direcciones IP y las direcciones URL que son necesarias para la difusión de reunión de Skype trabajar.</span><span class="sxs-lookup"><span data-stu-id="7ab01-122">The second step in the setup process is for you to first add domains that are needed and then add IP addresses and URLs that are required for Skype Meeting Broadcast to work.</span></span>

- <span data-ttu-id="7ab01-123">**Agregar el Skype necesaria para direcciones URL de extremo en línea de negocio y las direcciones IP viendo cuáles son necesarias** [aquí](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).</span><span class="sxs-lookup"><span data-stu-id="7ab01-123">**Add the required Skype for Business Online endpoint URLs and IP addresses by seeing which ones are required** [here](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).</span></span>

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a><span data-ttu-id="7ab01-124">Configurar Difusión de reunión de Skype en organizaciones e implementaciones híbridas</span><span class="sxs-lookup"><span data-stu-id="7ab01-124">Set up Skype Meeting Broadcast in Hybrid deployments and organizations</span></span>

<span data-ttu-id="7ab01-125">Si tiene un Skype para la organización en línea de negocio y una implementación local de Lync Server 2010, Microsoft Lync Server 2013 y Skype para Business Server 2015 y tienen los usuarios tanto en línea y local, hay otros pasos de configuración que debe llevar a cabo en Además de las anteriores para habilitar la organización local para comunicarse con Skype para profesionales en línea y permitir que todos los usuarios puedan crear y unirse a una reunión de Skype Difundir presentación.</span><span class="sxs-lookup"><span data-stu-id="7ab01-125">If you have a Skype for Business Online organization and an on-premises deployment of Lync Server 2010, Microsoft Lync Server 2013, and Skype for Business Server 2015 and have users both online and on-premises, there are other setup steps that you will need to do in addition to the ones above to enable your on-premises organization to communicate with Skype for Business Online and allow all of your users to be able to create and join a Skype Meeting Broadcast.</span></span> <span data-ttu-id="7ab01-126">Para ver cuáles son esos requisitos, consulte [Configurar la implementación local para la Difusión de reunión de Skype](https://go.microsoft.com/fwlink/?LinkId=617070).</span><span class="sxs-lookup"><span data-stu-id="7ab01-126">To see what those requirements are, see [Configure your on-premises deployment for Skype Meeting Broadcast](https://go.microsoft.com/fwlink/?LinkId=617070).</span></span>

## <a name="related-topics"></a><span data-ttu-id="7ab01-127">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="7ab01-127">Related topics</span></span>

[<span data-ttu-id="7ab01-128">Habilitar Difusión de reunión de Skype</span><span class="sxs-lookup"><span data-stu-id="7ab01-128">Enable Skype Meeting Broadcast</span></span>](enable-skype-meeting-broadcast.md)

[<span data-ttu-id="7ab01-129">URL de Office 365 e intervalos de direcciones IP</span><span class="sxs-lookup"><span data-stu-id="7ab01-129">Office 365 URLs and IP address ranges</span></span>](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[<span data-ttu-id="7ab01-130">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="7ab01-130">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)



