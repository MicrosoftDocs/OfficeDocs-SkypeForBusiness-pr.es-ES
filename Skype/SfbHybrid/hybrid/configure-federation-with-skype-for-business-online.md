---
title: Configurar la implementación híbrida de Skype empresarial
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 'Resumen: Obtenga información sobre cómo configurar la interoperabilidad entre su implementación local y Skype empresarial online.'
ms.openlocfilehash: 1b36a25674c3d6690b7490d0cd0793f05131cc12
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726790"
---
# <a name="configure-skype-for-business-hybrid"></a><span data-ttu-id="225af-103">Configurar la implementación híbrida de Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="225af-103">Configure Skype for Business hybrid</span></span>

<span data-ttu-id="225af-104">Para configurar el entorno híbrido de Skype empresarial, debe:</span><span class="sxs-lookup"><span data-stu-id="225af-104">To configure Skype for Business hybrid, you need to:</span></span>

- <span data-ttu-id="225af-105">[Configure el servicio de entorno local para federar con Office 365](#configure-your-on-premises-edge-service-to-federate-with-office-365).</span><span class="sxs-lookup"><span data-stu-id="225af-105">[Configure your on-premises environment service to federate with Office 365](#configure-your-on-premises-edge-service-to-federate-with-office-365).</span></span>
- <span data-ttu-id="225af-106">[Configure el entorno local para que confíe en office 365 y habilite el espacio de direcciones SIP compartido con office 365](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365).</span><span class="sxs-lookup"><span data-stu-id="225af-106">[Configure your on-premises environment to trust Office 365 and enable shared SIP address space with Office 365](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365).</span></span>
- <span data-ttu-id="225af-107">[Habilite el espacio de direcciones SIP compartido en el inquilino de Office 365](#enable-shared-sip-address-space-in-your-office-365-tenant).</span><span class="sxs-lookup"><span data-stu-id="225af-107">[Enable shared SIP address space in your Office 365 tenant](#enable-shared-sip-address-space-in-your-office-365-tenant).</span></span>

<span data-ttu-id="225af-108">Tenga en cuenta que si tiene Exchange local, es posible que desee configurar OAuth entre su entorno local de Exchange y los entornos de Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="225af-108">Note that if you have Exchange on-premises, you may want to configure OAuth between your Exchange on-premises and Skype for Business Online environments.</span></span> <span data-ttu-id="225af-109">Para obtener más información, vea [Manage Server-to-Server Authentication in Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) y [plan to Integrate Skype for Business and Exchange](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support).</span><span class="sxs-lookup"><span data-stu-id="225af-109">For more information, see  [Manage server-to-server authentication in Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) and [Plan to integrate Skype for Business and Exchange](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support).</span></span> 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-office-365"></a><span data-ttu-id="225af-110">Configurar el servicio perimetral local para federar con Office 365</span><span class="sxs-lookup"><span data-stu-id="225af-110">Configure your on-premises Edge service to federate with Office 365</span></span>

<span data-ttu-id="225af-111">La Federación permite que los usuarios de la implementación local se comuniquen con los usuarios de Office 365 de su organización.</span><span class="sxs-lookup"><span data-stu-id="225af-111">Federation allows users in your on-premises deployment to communicate with Office 365 users in your organization.</span></span> <span data-ttu-id="225af-112">Para configurar la Federación, ejecute el siguiente cmdlet en el shell de administración de Skype empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="225af-112">To configure federation, run the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -EnablePartnerDiscovery 1 -UseDnsSrvRouting
```

<span data-ttu-id="225af-113">Si el valor "-EnablePartnerDiscovery" se establece en 1, Skype empresarial Server usará los registros DNS para intentar detectar dominios asociados que no aparezcan en la lista AllowedDomains.</span><span class="sxs-lookup"><span data-stu-id="225af-113">If '-EnablePartnerDiscovery' value set to 1, Skype for Business Server will use DNS records to try and discover partner domains not listed in the AllowedDomains list.</span></span> <span data-ttu-id="225af-114">Si el valor se establece en 0, Skype empresarial Server solo se federe con los dominios que se encuentran en la lista AllowedDomains.</span><span class="sxs-lookup"><span data-stu-id="225af-114">If the value set to 0, Skype for Business Server will only federate with domains found on the AllowedDomains list.</span></span> <span data-ttu-id="225af-115">Este parámetro es necesario si se usa el enrutamiento del servicio DNS.</span><span class="sxs-lookup"><span data-stu-id="225af-115">This parameter is required if you use DNS service routing.</span></span>



## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365"></a><span data-ttu-id="225af-116">Configurar el entorno local para habilitar el espacio de direcciones SIP compartido con Office 365</span><span class="sxs-lookup"><span data-stu-id="225af-116">Configure your on-premises environment to enable shared SIP address space with Office 365</span></span>

<span data-ttu-id="225af-117">También debe configurar el entorno local para confiar en Office 365 y habilitar el espacio de direcciones SIP compartido con Office 365.</span><span class="sxs-lookup"><span data-stu-id="225af-117">You must also configure your on-premises environment to trust Office 365 and enable shared SIP address space with Office 365.</span></span> <span data-ttu-id="225af-118">Esto significa que Office 365 puede hospedar potencialmente cuentas de usuario para el mismo conjunto de dominios SIP que el entorno local, y los mensajes se pueden enrutar entre usuarios hospedados de forma local y en línea.</span><span class="sxs-lookup"><span data-stu-id="225af-118">This means Office 365 can potentially host user accounts for the same set of SIP domains as your on-premises environment, and messages can be routed between users hosted on premises and online.</span></span>  <span data-ttu-id="225af-119">Para ello, configure un proveedor de hospedaje con ProxyFqdn = sipfed. online. Lync. com tal y como se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="225af-119">You do this by configuring a hosting provider with ProxyFqdn=sipfed.online.lync.com as described below.</span></span>

<span data-ttu-id="225af-120">En primer lugar, compruebe si ya tiene un proveedor de hospedaje con ProxyFqdn = sipfed. online. Lync. com.</span><span class="sxs-lookup"><span data-stu-id="225af-120">First, check if you already have a hosting provider with ProxyFqdn=sipfed.online.lync.com.</span></span> <span data-ttu-id="225af-121">Si la hay, quítela mediante el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="225af-121">If one exists, then remove it by using the following command:</span></span>

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

<span data-ttu-id="225af-122">A continuación, cree un nuevo proveedor de hospedaje, use el cmdlet New-CsHostingProvider de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="225af-122">Then create a new hosting provider, use the New-CsHostingProvider cmdlet as follows:</span></span> 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-office-365-tenant"></a><span data-ttu-id="225af-123">Habilitar el espacio de direcciones SIP compartido en el inquilino de Office 365</span><span class="sxs-lookup"><span data-stu-id="225af-123">Enable shared SIP address space in your Office 365 tenant</span></span>
  
<span data-ttu-id="225af-124">Además del cambio realizado en la implementación local, tendrá que realizar el cambio correspondiente en el inquilino de Office 365 para habilitar el espacio de direcciones SIP compartido con su implementación local.</span><span class="sxs-lookup"><span data-stu-id="225af-124">In addition to the change you made in your on-premises deployment, you'll need to make the corresponding change in your Office 365 tenant to enabled shared SIP address space with your on-premises deployment.</span></span>  

<span data-ttu-id="225af-125">Para habilitar el espacio de direcciones SIP compartido en su inquilino de Office 365, establezca una sesión de PowerShell remota con Skype empresarial online y, a continuación, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="225af-125">To enable shared SIP address space in your Office 365 tenant, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="225af-126">El atributo SharedSipAddressSpace debe permanecer "true" hasta que el movimiento a en línea sea final y ningún usuario permanece local.</span><span class="sxs-lookup"><span data-stu-id="225af-126">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="225af-127">Para establecer una sesión de PowerShell remota con Microsoft Teams o Skype empresarial online, primero debe instalar el módulo de conector de Skype empresarial online para Windows PowerShell, que puede obtener [aquí](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span><span class="sxs-lookup"><span data-stu-id="225af-127">To establish a remote PowerShell session with Teams or Skype for Business Online, you first need to install the Skype for Business Online connector module for Windows PowerShell, which you can get [here](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span></span>
  
<span data-ttu-id="225af-128">Después de instalar el módulo, puede establecer una sesión remota con los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="225af-128">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
  
```PowerShell
$cred = Get-Credential
Import-PSSession (New-CsOnlineSession -Credential $cred) -AllowClobber
```

<span data-ttu-id="225af-129">Para obtener más información sobre cómo establecer una sesión de PowerShell remota con Skype empresarial online y cómo usar el módulo conector de Skype empresarial online, consulte [configurar el equipo para Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="225af-129">For more information about how to establish a remote PowerShell session with Skype for Business Online, and how to use the Skype for Business Online Connector module, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  


## <a name="see-also"></a><span data-ttu-id="225af-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="225af-130">See also</span></span>

[<span data-ttu-id="225af-131">New-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="225af-131">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)

