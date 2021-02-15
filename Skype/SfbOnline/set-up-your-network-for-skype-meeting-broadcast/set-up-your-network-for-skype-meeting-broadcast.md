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
f1.keywords:
- NOCSH
ms.custom:
- SMB
description: Learn about the Skype Meeting Broadcast feature of Skype for Business Online that enables you to schedule, produce, and broadcast meetings or events to large online audiences up to 10,000 attendees.
ms.openlocfilehash: b774c368674f421c11f36339ef7188ea8de82e64
ms.sourcegitcommit: ab566ddab9d26440bac1716a975f30e075d0c7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "49865164"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a><span data-ttu-id="e3b70-103">Configurar la red para Difusión de reunión de Skype</span><span class="sxs-lookup"><span data-stu-id="e3b70-103">Set up your network for Skype Meeting Broadcast</span></span>

<span data-ttu-id="e3b70-104">Después de [habilitar Difusión de reunión de](enable-skype-meeting-broadcast.md) Skype, debe configurar su red.</span><span class="sxs-lookup"><span data-stu-id="e3b70-104">After you [Enable Skype Meeting Broadcast](enable-skype-meeting-broadcast.md) Skype Meeting Broadcast, you need to configure your network.</span></span> <span data-ttu-id="e3b70-105">Realice este paso si quiere realizar seminarios web y otras difusiones para personas que no forme parte de su empresa.</span><span class="sxs-lookup"><span data-stu-id="e3b70-105">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e3b70-106">Skype Empresarial Online se retirará el 31 de julio de 2021, momento en el que finalizará el acceso al servicio.</span><span class="sxs-lookup"><span data-stu-id="e3b70-106">Skype for Business Online is retiring on July 31, 2021, at which time access to the service will end.</span></span> <span data-ttu-id="e3b70-107">Animamos a los clientes a comenzar la actualización a Microsoft Teams, el cliente principal de comunicaciones y trabajo en equipo en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e3b70-107">We encourage customers to begin the upgrade to Microsoft Teams, the core client for communications and teamwork in Microsoft 365.</span></span>

<span data-ttu-id="e3b70-108">Si no tiene experiencia con la configuración del firewall, analice contratar un [socio de Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para que lleve a cabo este paso por usted.</span><span class="sxs-lookup"><span data-stu-id="e3b70-108">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>

<span data-ttu-id="e3b70-109">Para omitir este paso y, en su lugar, agregar otra empresa a su federación para poder invitarlos a difusiones, siga los pasos de Permitir que los usuarios se contacten con usuarios externos de [Skype Empresarial.](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)</span><span class="sxs-lookup"><span data-stu-id="e3b70-109">To skip this step and instead add another business to your federation so you can invite them to broadcasts, follow the steps in [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span>

## <a name="step-1-set-up-allowed-domains"></a><span data-ttu-id="e3b70-110">Paso 1: Configurar dominios permitidos</span><span class="sxs-lookup"><span data-stu-id="e3b70-110">Step 1: Set up allowed domains</span></span>

<span data-ttu-id="e3b70-111">Use **uno** de los siguientes métodos para configurar dominios permitidos:</span><span class="sxs-lookup"><span data-stu-id="e3b70-111">Use **one** of the following methods to set up allowed domains:</span></span>

## #

 <span data-ttu-id="e3b70-112">**Método 1: Usar el centro de administración**</span><span class="sxs-lookup"><span data-stu-id="e3b70-112">**Method 1: Use the admin center**</span></span>

1. <span data-ttu-id="e3b70-113">Vaya al centro de administración y, a continuación, en la barra de navegación izquierda, haga clic en Complementos de Servicios de configuración y, a continuación, elija  >  **&amp;** **Skype Empresarial.**</span><span class="sxs-lookup"><span data-stu-id="e3b70-113">Go to the admin center and then in the left nav, click **Settings** > **Services &amp; add-ins**, and then choose **Skype for Business**.</span></span>

2. <span data-ttu-id="e3b70-114">En la **página Uso compartido** externo, en Excepciones de dominio, seleccione Todos los dominios están **bloqueados** excepto **y** escriba los siguientes dominios separados con una coma (,):</span><span class="sxs-lookup"><span data-stu-id="e3b70-114">On the **External sharing** page under **Domain exceptions**, select **All domains are blocked except**, and enter the following domains, separated with a comma (,):</span></span>

   - <span data-ttu-id="e3b70-115">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="e3b70-115">noammeetings.lync.com</span></span>

   - <span data-ttu-id="e3b70-116">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="e3b70-116">emeameetings.lync.com</span></span>

   - <span data-ttu-id="e3b70-117">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="e3b70-117">apacmeetings.lync.com</span></span>

   - <span data-ttu-id="e3b70-118">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="e3b70-118">resources.lync.com</span></span>

3. <span data-ttu-id="e3b70-119">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e3b70-119">Click **Save**.</span></span>

## #

 <span data-ttu-id="e3b70-120">**Método 2: Usar Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="e3b70-120">**Method 2: Use Windows PowerShell**</span></span>

- <span data-ttu-id="e3b70-121">En el **menú Inicio, haga** clic con el **botón derecho Windows PowerShell** haga clic en Ejecutar **como administrador.**</span><span class="sxs-lookup"><span data-stu-id="e3b70-121">From the **Start Menu**, right-click **Windows PowerShell** and click **Run as administrator**.</span></span> <span data-ttu-id="e3b70-122">In the **Windows PowerShell** window, type each line and press Enter.</span><span class="sxs-lookup"><span data-stu-id="e3b70-122">In the **Windows PowerShell** window, type each line and press Enter.</span></span>

  ```PowerShell
  $r = New-CsEdgeDomainPattern -Domain "noammeetings.lync.com"
  ```

  ```PowerShell
  $s = New-CsEdgeDomainPattern -Domain "emeameetings.lync.com"
  ```

  ```PowerShell
  $t = New-CsEdgeDomainPattern -Domain "apacmeetings.lync.com"
  ```

  ```PowerShell
  $n = New-CsEdgeDomainPattern -Domain "resources.lync.com"
  ```

  ```PowerShell
  $newAllowList = New-CsEdgeAllowList -AllowedDomain $r,$s,$t,$n
  ```

  ```PowerShell
  Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList
  ```

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a><span data-ttu-id="e3b70-123">Paso 2: Agregar dominios, direcciones URL y direcciones IP de Difusión de reunión de Skype</span><span class="sxs-lookup"><span data-stu-id="e3b70-123">Step 2: Add Skype Meeting Broadcast domains, URLs, and IP addresses</span></span>

<span data-ttu-id="e3b70-124">El segundo paso del proceso de configuración consiste en agregar primero los dominios necesarios y después agregar las direcciones IP y las URL necesarias para que funcione la Difusión de reunión de Skype.</span><span class="sxs-lookup"><span data-stu-id="e3b70-124">The second step in the setup process is for you to first add domains that are needed and then add IP addresses and URLs that are required for Skype Meeting Broadcast to work.</span></span>

- <span data-ttu-id="e3b70-125">**Agregue las direcciones IP** [](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo)y URL de puntos de conexión de Skype Empresarial Online necesarias.</span><span class="sxs-lookup"><span data-stu-id="e3b70-125">**Add the required Skype for Business Online endpoint URLs and IP addresses by seeing which ones are required** [here](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).</span></span>

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a><span data-ttu-id="e3b70-126">Configurar Difusión de reunión de Skype en organizaciones e implementaciones híbridas</span><span class="sxs-lookup"><span data-stu-id="e3b70-126">Set up Skype Meeting Broadcast in Hybrid deployments and organizations</span></span>

<span data-ttu-id="e3b70-127">Si tiene una organización de Skype Empresarial Online y una implementación local de Lync Server 2010, Microsoft Lync Server 2013 y Skype Empresarial Server 2015, y tiene usuarios tanto en línea como local, hay otros pasos de configuración que deberá realizar además de los anteriores para permitir que su organización local se comunique con Skype Empresarial Online y permita que todos los usuarios se unan a una Difusión de reunión de Skype.</span><span class="sxs-lookup"><span data-stu-id="e3b70-127">If you have a Skype for Business Online organization and an on-premises deployment of Lync Server 2010, Microsoft Lync Server 2013, and Skype for Business Server 2015 and have users both online and on-premises, there are other setup steps that you will need to do in addition to the ones above to enable your on-premises organization to communicate with Skype for Business Online and allow all your users to join a Skype Meeting Broadcast.</span></span> <span data-ttu-id="e3b70-128">Para ver cuáles son esos requisitos, consulte [Configurar la implementación local para la Difusión de reunión de Skype](https://go.microsoft.com/fwlink/?LinkId=617070).</span><span class="sxs-lookup"><span data-stu-id="e3b70-128">To see what those requirements are, see [Configure your on-premises deployment for Skype Meeting Broadcast](https://go.microsoft.com/fwlink/?LinkId=617070).</span></span>

## <a name="related-topics"></a><span data-ttu-id="e3b70-129">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="e3b70-129">Related topics</span></span>

[<span data-ttu-id="e3b70-130">Habilitar la Difusión de reunión de Skype</span><span class="sxs-lookup"><span data-stu-id="e3b70-130">Enable Skype Meeting Broadcast</span></span>](enable-skype-meeting-broadcast.md)

[<span data-ttu-id="e3b70-131">Direcciones URL e intervalos de direcciones IP de Office 365</span><span class="sxs-lookup"><span data-stu-id="e3b70-131">Office 365 URLs and IP address ranges</span></span>](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[<span data-ttu-id="e3b70-132">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="e3b70-132">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)



