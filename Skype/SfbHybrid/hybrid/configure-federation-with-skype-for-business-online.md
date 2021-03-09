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
description: 'Resumen: obtenga información sobre cómo configurar la interoperabilidad entre la implementación local y Skype Empresarial Online.'
ms.openlocfilehash: a97072c9c4b65b4cc13d29a733b8ddc840529363
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569222"
---
# <a name="configure-skype-for-business-hybrid"></a><span data-ttu-id="a73d1-103">Configurar Skype Empresarial híbrido</span><span class="sxs-lookup"><span data-stu-id="a73d1-103">Configure Skype for Business hybrid</span></span>

<span data-ttu-id="a73d1-104">Para configurar Skype Empresarial híbrido, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a73d1-104">To configure Skype for Business hybrid, you need to:</span></span>

- <span data-ttu-id="a73d1-105">[Configure el servicio perimetral local para federar con Microsoft 365 u Office 365](#configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365).</span><span class="sxs-lookup"><span data-stu-id="a73d1-105">[Configure your on-premises Edge service to federate with Microsoft 365 or Office 365](#configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365).</span></span>
- <span data-ttu-id="a73d1-106">Configure el entorno local para que confíe [en Microsoft 365 u Office 365](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365)y habilite el espacio de direcciones SIP compartido.</span><span class="sxs-lookup"><span data-stu-id="a73d1-106">[Configure your on-premises environment to trust Microsoft 365 or Office 365 and enable shared SIP address space](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365).</span></span>
- <span data-ttu-id="a73d1-107">[Habilitar el espacio de direcciones SIP compartido en su organización de Microsoft 365 u Office 365](#enable-shared-sip-address-space-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="a73d1-107">[Enable shared SIP address space in your Microsoft 365 or Office 365 organization](#enable-shared-sip-address-space-in-your-organization).</span></span>

<span data-ttu-id="a73d1-108">Tenga en cuenta que si tiene Exchange local, es posible que desee configurar OAuth entre los entornos locales de Exchange y Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="a73d1-108">Note that if you have Exchange on-premises, you may want to configure OAuth between your Exchange on-premises and Skype for Business Online environments.</span></span> <span data-ttu-id="a73d1-109">Para obtener más información, vea  [Manage server-to-server authentication in Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) y Plan to integrate Skype for Business and [Exchange](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support).</span><span class="sxs-lookup"><span data-stu-id="a73d1-109">For more information, see  [Manage server-to-server authentication in Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) and [Plan to integrate Skype for Business and Exchange](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support).</span></span> 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365"></a><span data-ttu-id="a73d1-110">Configurar el servicio perimetral local para federar con Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="a73d1-110">Configure your on-premises Edge service to federate with Microsoft 365 or Office 365</span></span>

<span data-ttu-id="a73d1-111">La federación permite a los usuarios de la implementación local comunicarse con usuarios de Microsoft 365 u Office 365 de la organización.</span><span class="sxs-lookup"><span data-stu-id="a73d1-111">Federation allows users in your on-premises deployment to communicate with Microsoft 365 or Office 365 users in your organization.</span></span> <span data-ttu-id="a73d1-112">Para configurar la federación, ejecute el siguiente cmdlet en el Shell de administración de Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="a73d1-112">To configure federation, run the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

<span data-ttu-id="a73d1-113">Si el valor '-EnablePartnerDiscovery' se establece en $True, Skype Empresarial Server usará registros DNS para intentar detectar dominios de asociado que no aparecen en la lista AllowedDomains.</span><span class="sxs-lookup"><span data-stu-id="a73d1-113">If '-EnablePartnerDiscovery' value is set to $True, Skype for Business Server will use DNS records to try and discover partner domains not listed in the AllowedDomains list.</span></span> <span data-ttu-id="a73d1-114">Si el valor se establece en $False, Skype Empresarial Server solo se federará con los dominios que se encuentran en la lista AllowedDomains.</span><span class="sxs-lookup"><span data-stu-id="a73d1-114">If the value is set to $False , Skype for Business Server will only federate with domains found on the AllowedDomains list.</span></span> <span data-ttu-id="a73d1-115">Este parámetro es necesario si se usa el enrutamiento del servicio DNS.</span><span class="sxs-lookup"><span data-stu-id="a73d1-115">This parameter is required if you use DNS service routing.</span></span>

> [!NOTE]
> <span data-ttu-id="a73d1-116">Para obtener más información sobre cómo habilitar la federación entre los usuarios de la implementación local de Skype Empresarial y los usuarios de una organización de Skype Empresarial Online, vea [Configuring federation support for a Skype for Business Online customer in Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/manage/federation-and-external-access/federation-support/configuring-federation-support).</span><span class="sxs-lookup"><span data-stu-id="a73d1-116">For more details about enabling federation between users of your on-premises Skype for Business deployment and users of a Skype for Business Online organization, see [Configuring federation support for a Skype for Business Online customer in Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/manage/federation-and-external-access/federation-support/configuring-federation-support).</span></span>


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365"></a><span data-ttu-id="a73d1-117">Configurar el entorno local para habilitar el espacio de direcciones SIP compartido con Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="a73d1-117">Configure your on-premises environment to enable shared SIP address space with Microsoft 365 or Office 365</span></span>

<span data-ttu-id="a73d1-118">También debe configurar el entorno local para que confíe en Microsoft 365 u Office 365 y habilite el espacio de direcciones SIP compartido.</span><span class="sxs-lookup"><span data-stu-id="a73d1-118">You must also configure your on-premises environment to trust Microsoft 365 or Office 365 and enable shared SIP address space.</span></span> <span data-ttu-id="a73d1-119">Esto significa que Microsoft 365 u Office 365 pueden hospedar posiblemente cuentas de usuario para el mismo conjunto de dominios SIP que el entorno local, y los mensajes se pueden enrutar entre usuarios hospedados localmente y en línea.</span><span class="sxs-lookup"><span data-stu-id="a73d1-119">This means Microsoft 365 or Office 365 can potentially host user accounts for the same set of SIP domains as your on-premises environment, and messages can be routed between users hosted on premises and online.</span></span>  <span data-ttu-id="a73d1-120">Para ello, configure un proveedor de hospedaje con ProxyFqdn=sipfed.online.lync.com como se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="a73d1-120">You do this by configuring a hosting provider with ProxyFqdn=sipfed.online.lync.com as described below.</span></span>

<span data-ttu-id="a73d1-121">En primer lugar, compruebe si ya tiene un proveedor de hospedaje con ProxyFqdn=sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="a73d1-121">First, check if you already have a hosting provider with ProxyFqdn=sipfed.online.lync.com.</span></span> <span data-ttu-id="a73d1-122">Si existe, quítela mediante el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="a73d1-122">If one exists, then remove it by using the following command:</span></span>

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

<span data-ttu-id="a73d1-123">A continuación, cree un nuevo proveedor de hospedaje, use el cmdlet New-CsHostingProvider de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="a73d1-123">Then create a new hosting provider, use the New-CsHostingProvider cmdlet as follows:</span></span> 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-organization"></a><span data-ttu-id="a73d1-124">Habilitar el espacio de direcciones SIP compartido en la organización</span><span class="sxs-lookup"><span data-stu-id="a73d1-124">Enable shared SIP address space in your organization</span></span>
  
<span data-ttu-id="a73d1-125">Además del cambio que realizó en la implementación local, deberá realizar el cambio correspondiente en su organización de Microsoft 365 u Office 365 para habilitar el espacio de direcciones SIP compartido con la implementación local.</span><span class="sxs-lookup"><span data-stu-id="a73d1-125">In addition to the change you made in your on-premises deployment, you'll need to make the corresponding change in your Microsoft 365 or Office 365 organization to enabled shared SIP address space with your on-premises deployment.</span></span>  

<span data-ttu-id="a73d1-126">Para habilitar el espacio de direcciones SIP compartido en su organización, establezca una sesión remota de PowerShell con Skype Empresarial Online y, a continuación, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="a73d1-126">To enable shared SIP address space in your organization, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="a73d1-127">El atributo SharedSipAddressSpace debe permanecer "True" hasta que el traslado a línea sea definitivo y ningún usuario permanezca local.</span><span class="sxs-lookup"><span data-stu-id="a73d1-127">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="a73d1-128">Para establecer una sesión remota de PowerShell con Teams o Skype Empresarial Online, primero debe instalar el módulo [de PowerShell de Teams](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="a73d1-128">To establish a remote PowerShell session with Teams or Skype for Business Online, you first need to install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
  
<span data-ttu-id="a73d1-129">Después de instalar el módulo, puede establecer una sesión remota con los cmdlets siguientes:</span><span class="sxs-lookup"><span data-stu-id="a73d1-129">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

<span data-ttu-id="a73d1-130">Para obtener más información acerca de cómo establecer una sesión remota de PowerShell con Skype Empresarial Online y cómo usar el módulo Skype Empresarial Online Connector, vea Configurar el equipo para [Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="a73d1-130">For more information about how to establish a remote PowerShell session with Skype for Business Online, and how to use the Skype for Business Online Connector module, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  


## <a name="see-also"></a><span data-ttu-id="a73d1-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a73d1-131">See also</span></span>

[<span data-ttu-id="a73d1-132">New-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="a73d1-132">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)
