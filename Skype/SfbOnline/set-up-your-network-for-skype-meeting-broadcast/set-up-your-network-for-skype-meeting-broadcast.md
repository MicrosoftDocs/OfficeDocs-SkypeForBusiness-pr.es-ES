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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- SMB
description: Learn about the Skype Meeting Broadcast feature of Skype for Business Online that enables you to schedule, produce, and broadcast meetings or events to large online audiences up to 10,000 attendees.
ms.openlocfilehash: 443810772eeb8bf11721825b06b6a87ccb2c97c8
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/18/2019
ms.locfileid: "35792924"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a><span data-ttu-id="73e34-103">Configurar la red para Difusión de reunión de Skype</span><span class="sxs-lookup"><span data-stu-id="73e34-103">Set up your network for Skype Meeting Broadcast</span></span>

<span data-ttu-id="73e34-104">Después de [Habilitar](enable-skype-meeting-broadcast.md) la difusión de reunión de Skype de difusión de reunión de Skype, debe configurar su red.</span><span class="sxs-lookup"><span data-stu-id="73e34-104">After you [Enable Skype Meeting Broadcast](enable-skype-meeting-broadcast.md) Skype Meeting Broadcast, you need to configure your network.</span></span> <span data-ttu-id="73e34-105">Lleve a cabo este paso si desea mantener seminarios y otras difusiones para personas fuera de su empresa.</span><span class="sxs-lookup"><span data-stu-id="73e34-105">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span>

<span data-ttu-id="73e34-106">Si no tiene experiencia con la configuración del firewall, analice contratar un [socio de Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para que lleve a cabo este paso por usted.</span><span class="sxs-lookup"><span data-stu-id="73e34-106">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>

<span data-ttu-id="73e34-107">Para omitir este paso y, en su lugar, agregar otra empresa a su Federación para poder invitarlos a las difusiones, siga los pasos que se indican en [permitir que los usuarios se pongan en contacto con usuarios externos de Skype empresarial](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span><span class="sxs-lookup"><span data-stu-id="73e34-107">To skip this step and instead add another business to your federation so you can invite them to broadcasts, follow the steps in [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span>

## <a name="step-1-set-up-allowed-domains"></a><span data-ttu-id="73e34-108">Paso 1: configurar los dominios permitidos</span><span class="sxs-lookup"><span data-stu-id="73e34-108">Step 1: Set up allowed domains</span></span>

<span data-ttu-id="73e34-109">Use **uno** de los métodos siguientes para configurar los dominios permitidos:</span><span class="sxs-lookup"><span data-stu-id="73e34-109">Use **one** of the following methods to set up allowed domains:</span></span>

## #

 <span data-ttu-id="73e34-110">**Método 1: usar el centro de administración**</span><span class="sxs-lookup"><span data-stu-id="73e34-110">**Method 1: Use the admin center**</span></span>

1. <span data-ttu-id="73e34-111">Vaya al centro de administración y, a continuación, en el explorador de navegación izquierdo, haga clic en\*\*Complementos de servicios &amp; \*\*de **configuración** > y, a continuación, elija **Skype empresarial**.</span><span class="sxs-lookup"><span data-stu-id="73e34-111">Go to the admin center and then in the left nav, click **Settings** > **Services &amp; add-ins**, and then choose **Skype for Business**.</span></span>

2. <span data-ttu-id="73e34-112">En la página **uso compartido externo** , en **excepciones de dominio**, seleccione **todos los dominios están bloqueados excepto**e introduzca los siguientes dominios separados por comas (,):</span><span class="sxs-lookup"><span data-stu-id="73e34-112">On the **External sharing** page under **Domain exceptions**, select **All domains are blocked except**, and enter the following domains, separated with a comma (,):</span></span>

   - <span data-ttu-id="73e34-113">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="73e34-113">noammeetings.lync.com</span></span>

   - <span data-ttu-id="73e34-114">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="73e34-114">emeameetings.lync.com</span></span>

   - <span data-ttu-id="73e34-115">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="73e34-115">apacmeetings.lync.com</span></span>

   - <span data-ttu-id="73e34-116">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="73e34-116">resources.lync.com</span></span>

3. <span data-ttu-id="73e34-117">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="73e34-117">Click **Save**.</span></span>

## #

 <span data-ttu-id="73e34-118">**Método 2: usar Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="73e34-118">**Method 2: Use Windows PowerShell**</span></span>

- <span data-ttu-id="73e34-119">En el **menú Inicio**, haga clic con el botón derecho en **Windows PowerShell** y haga clic en **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="73e34-119">From the **Start Menu**, right-click **Windows PowerShell** and click **Run as administrator**.</span></span> <span data-ttu-id="73e34-120">In the **Windows PowerShell** window, type each line and press Enter.</span><span class="sxs-lookup"><span data-stu-id="73e34-120">In the **Windows PowerShell** window, type each line and press Enter.</span></span>

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

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a><span data-ttu-id="73e34-121">Paso 2: agregar dominios de difusión de reunión de Skype, direcciones URL y direcciones IP</span><span class="sxs-lookup"><span data-stu-id="73e34-121">Step 2: Add Skype Meeting Broadcast domains, URLs, and IP addresses</span></span>

<span data-ttu-id="73e34-122">El segundo paso del proceso de configuración es agregar primero los dominios necesarios y, a continuación, agregar direcciones IP y direcciones URL necesarias para que la difusión de reunión de Skype funcione.</span><span class="sxs-lookup"><span data-stu-id="73e34-122">The second step in the setup process is for you to first add domains that are needed and then add IP addresses and URLs that are required for Skype Meeting Broadcast to work.</span></span>

- <span data-ttu-id="73e34-123">**Agregar las direcciones IP y las direcciones URL de los extremos de Skype empresarial online necesarias consultando Cuáles son obligatorias** [aquí](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).</span><span class="sxs-lookup"><span data-stu-id="73e34-123">**Add the required Skype for Business Online endpoint URLs and IP addresses by seeing which ones are required** [here](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).</span></span>

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a><span data-ttu-id="73e34-124">Configurar Difusión de reunión de Skype en organizaciones e implementaciones híbridas</span><span class="sxs-lookup"><span data-stu-id="73e34-124">Set up Skype Meeting Broadcast in Hybrid deployments and organizations</span></span>

<span data-ttu-id="73e34-125">Si dispone de una organización de Skype empresarial online y una implementación local de Lync Server 2010, Microsoft Lync Server 2013 y Skype empresarial Server 2015, y tiene usuarios en línea y locales, hay otros pasos de configuración que necesitará realizar en complemento de los anteriores para permitir que su organización local se comunique con Skype empresarial online y permitir que todos los usuarios se unan a una difusión de reunión de Skype.</span><span class="sxs-lookup"><span data-stu-id="73e34-125">If you have a Skype for Business Online organization and an on-premises deployment of Lync Server 2010, Microsoft Lync Server 2013, and Skype for Business Server 2015 and have users both online and on-premises, there are other setup steps that you will need to do in addition to the ones above to enable your on-premises organization to communicate with Skype for Business Online and allow all your users to join a Skype Meeting Broadcast.</span></span> <span data-ttu-id="73e34-126">Para ver cuáles son esos requisitos, consulte [Configurar la implementación local para la Difusión de reunión de Skype](https://go.microsoft.com/fwlink/?LinkId=617070).</span><span class="sxs-lookup"><span data-stu-id="73e34-126">To see what those requirements are, see [Configure your on-premises deployment for Skype Meeting Broadcast](https://go.microsoft.com/fwlink/?LinkId=617070).</span></span>

## <a name="related-topics"></a><span data-ttu-id="73e34-127">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="73e34-127">Related topics</span></span>

[<span data-ttu-id="73e34-128">Habilitar la Difusión de reunión de Skype</span><span class="sxs-lookup"><span data-stu-id="73e34-128">Enable Skype Meeting Broadcast</span></span>](enable-skype-meeting-broadcast.md)

[<span data-ttu-id="73e34-129">Direcciones URL e intervalos de direcciones IP de Office 365</span><span class="sxs-lookup"><span data-stu-id="73e34-129">Office 365 URLs and IP address ranges</span></span>](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[<span data-ttu-id="73e34-130">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="73e34-130">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)



