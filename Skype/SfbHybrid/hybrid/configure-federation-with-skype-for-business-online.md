---
title: Configurar Skype Empresarial híbrido
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
ms.openlocfilehash: bd8b3ee3e70cb3662a4eae68fdb5ae6149b55a84
ms.sourcegitcommit: 48f64fa38509cf7141b944cd3da60409ec51860b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "43750037"
---
# <a name="configure-skype-for-business-hybrid"></a><span data-ttu-id="93486-103">Configurar Skype Empresarial híbrido</span><span class="sxs-lookup"><span data-stu-id="93486-103">Configure Skype for Business hybrid</span></span>

<span data-ttu-id="93486-104">Para configurar Skype Empresarial híbrido, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="93486-104">To configure Skype for Business hybrid, you need to:</span></span>

- <span data-ttu-id="93486-105">[Configure el servicio perimetral local para federar con Office 365 u otra organización](#configure-your-on-premises-edge-service-to-federate-with-office-365-or-another-organization).</span><span class="sxs-lookup"><span data-stu-id="93486-105">[Configure your on-premises Edge service to federate with Office 365 or another organization](#configure-your-on-premises-edge-service-to-federate-with-office-365-or-another-organization).</span></span>
- <span data-ttu-id="93486-106">[Configure el entorno local para que confíe en office 365 y habilite el espacio de direcciones SIP compartido con office 365](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365).</span><span class="sxs-lookup"><span data-stu-id="93486-106">[Configure your on-premises environment to trust Office 365 and enable shared SIP address space with Office 365](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365).</span></span>
- <span data-ttu-id="93486-107">[Habilite el espacio de direcciones SIP compartido en el inquilino de Office 365](#enable-shared-sip-address-space-in-your-office-365-tenant).</span><span class="sxs-lookup"><span data-stu-id="93486-107">[Enable shared SIP address space in your Office 365 tenant](#enable-shared-sip-address-space-in-your-office-365-tenant).</span></span>

<span data-ttu-id="93486-108">Tenga en cuenta que si tiene Exchange local, es posible que desee configurar OAuth entre su entorno local de Exchange y los entornos de Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="93486-108">Note that if you have Exchange on-premises, you may want to configure OAuth between your Exchange on-premises and Skype for Business Online environments.</span></span> <span data-ttu-id="93486-109">Para obtener más información, vea [Manage Server-to-Server Authentication in Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) y [plan to Integrate Skype for Business and Exchange](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support).</span><span class="sxs-lookup"><span data-stu-id="93486-109">For more information, see  [Manage server-to-server authentication in Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) and [Plan to integrate Skype for Business and Exchange](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support).</span></span> 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-office-365-or-another-organization"></a><span data-ttu-id="93486-110">Configurar el servicio perimetral local para federar con Office 365 u otra organización</span><span class="sxs-lookup"><span data-stu-id="93486-110">Configure your on-premises Edge service to federate with Office 365 or another organization</span></span>

<span data-ttu-id="93486-111">La federación permite a los usuarios de su implementación local comunicarse con usuarios de Office 365 de su organización.</span><span class="sxs-lookup"><span data-stu-id="93486-111">Federation allows users in your on-premises deployment to communicate with Office 365 users in your organization.</span></span> <span data-ttu-id="93486-112">Para configurar la Federación, ejecute el siguiente cmdlet en el shell de administración de Skype empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="93486-112">To configure federation, run the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

<span data-ttu-id="93486-113">Si el valor "-EnablePartnerDiscovery" se establece en $True, Skype empresarial Server usará los registros DNS para intentar detectar dominios asociados que no aparezcan en la lista AllowedDomains.</span><span class="sxs-lookup"><span data-stu-id="93486-113">If '-EnablePartnerDiscovery' value is set to $True, Skype for Business Server will use DNS records to try and discover partner domains not listed in the AllowedDomains list.</span></span> <span data-ttu-id="93486-114">Si el valor se establece en $False, Skype empresarial Server solo se federe con los dominios que se encuentran en la lista AllowedDomains.</span><span class="sxs-lookup"><span data-stu-id="93486-114">If the value is set to $False , Skype for Business Server will only federate with domains found on the AllowedDomains list.</span></span> <span data-ttu-id="93486-115">Este parámetro es necesario si se usa el enrutamiento del servicio DNS.</span><span class="sxs-lookup"><span data-stu-id="93486-115">This parameter is required if you use DNS service routing.</span></span>

> [!NOTE]
> <span data-ttu-id="93486-116">Para obtener más información acerca de cómo habilitar la Federación entre los usuarios de su implementación local de Skype empresarial y los usuarios de una organización de Skype empresarial online, consulte [Configuring Federation Support for a Skype for Business online Customer in Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/manage/federation-and-external-access/federation-support/configuring-federation-support).</span><span class="sxs-lookup"><span data-stu-id="93486-116">For more details about enabling federation between users of your on-premises Skype for Business deployment and users of a Skype for Business Online organization, see [Configuring federation support for a Skype for Business Online customer in Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/manage/federation-and-external-access/federation-support/configuring-federation-support).</span></span>


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365"></a><span data-ttu-id="93486-117">Configurar el entorno local para habilitar el espacio de direcciones SIP compartido con Office 365</span><span class="sxs-lookup"><span data-stu-id="93486-117">Configure your on-premises environment to enable shared SIP address space with Office 365</span></span>

<span data-ttu-id="93486-118">Debe configurar su entorno local para que confíe en Office 365 y permita el espacio de dirección SIP compartida con Office 365.</span><span class="sxs-lookup"><span data-stu-id="93486-118">You must also configure your on-premises environment to trust Office 365 and enable shared SIP address space with Office 365.</span></span> <span data-ttu-id="93486-119">Esto significa que Office 365 puede hospedar potencialmente cuentas de usuario para el mismo conjunto de dominios SIP que el entorno local, y los mensajes se pueden enrutar entre usuarios hospedados de forma local y en línea.</span><span class="sxs-lookup"><span data-stu-id="93486-119">This means Office 365 can potentially host user accounts for the same set of SIP domains as your on-premises environment, and messages can be routed between users hosted on premises and online.</span></span>  <span data-ttu-id="93486-120">Para ello, configure un proveedor de hospedaje con ProxyFqdn = sipfed. online. Lync. com tal y como se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="93486-120">You do this by configuring a hosting provider with ProxyFqdn=sipfed.online.lync.com as described below.</span></span>

<span data-ttu-id="93486-121">En primer lugar, compruebe si ya tiene un proveedor de hospedaje con ProxyFqdn = sipfed. online. Lync. com.</span><span class="sxs-lookup"><span data-stu-id="93486-121">First, check if you already have a hosting provider with ProxyFqdn=sipfed.online.lync.com.</span></span> <span data-ttu-id="93486-122">Si la hay, quítela mediante el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="93486-122">If one exists, then remove it by using the following command:</span></span>

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

<span data-ttu-id="93486-123">A continuación, cree un nuevo proveedor de hospedaje, use el cmdlet New-CsHostingProvider de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="93486-123">Then create a new hosting provider, use the New-CsHostingProvider cmdlet as follows:</span></span> 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-office-365-tenant"></a><span data-ttu-id="93486-124">Habilitar el espacio de direcciones SIP compartido en el inquilino de Office 365</span><span class="sxs-lookup"><span data-stu-id="93486-124">Enable shared SIP address space in your Office 365 tenant</span></span>
  
<span data-ttu-id="93486-125">Además del cambio realizado en la implementación local, tendrá que realizar el cambio correspondiente en el inquilino de Office 365 para habilitar el espacio de direcciones SIP compartido con su implementación local.</span><span class="sxs-lookup"><span data-stu-id="93486-125">In addition to the change you made in your on-premises deployment, you'll need to make the corresponding change in your Office 365 tenant to enabled shared SIP address space with your on-premises deployment.</span></span>  

<span data-ttu-id="93486-126">Para habilitar el espacio de direcciones SIP compartido en su inquilino de Office 365, establezca una sesión de PowerShell remota con Skype empresarial online y, a continuación, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="93486-126">To enable shared SIP address space in your Office 365 tenant, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="93486-127">El atributo SharedSipAddressSpace debe permanecer "true" hasta que el movimiento a en línea sea final y ningún usuario permanece local.</span><span class="sxs-lookup"><span data-stu-id="93486-127">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="93486-128">Para establecer una sesión de PowerShell remota con Microsoft Teams o Skype empresarial online, primero debe instalar el módulo de conector de Skype empresarial online para Windows PowerShell, que puede obtener [aquí](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span><span class="sxs-lookup"><span data-stu-id="93486-128">To establish a remote PowerShell session with Teams or Skype for Business Online, you first need to install the Skype for Business Online connector module for Windows PowerShell, which you can get [here](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span></span>
  
<span data-ttu-id="93486-129">Después de instalar el módulo, puede establecer una sesión remota con los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="93486-129">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
  
```PowerShell
$cred = Get-Credential
Import-PSSession (New-CsOnlineSession -Credential $cred) -AllowClobber
```

<span data-ttu-id="93486-130">Para obtener más información sobre cómo establecer una sesión de PowerShell remota con Skype empresarial online y cómo usar el módulo conector de Skype empresarial online, consulte [configurar el equipo para Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="93486-130">For more information about how to establish a remote PowerShell session with Skype for Business Online, and how to use the Skype for Business Online Connector module, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  


## <a name="see-also"></a><span data-ttu-id="93486-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="93486-131">See also</span></span>

[<span data-ttu-id="93486-132">New-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="93486-132">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)
