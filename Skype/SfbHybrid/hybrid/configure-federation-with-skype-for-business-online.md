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
description: 'Summary: Learn how to configure interoperability between your on-premises deployment and Teams.'
ms.openlocfilehash: 2c6fda43b939a616071009be2b8d28e636036101
ms.sourcegitcommit: 17ad87556fb8e0de3c498e53f98f951ae3fa526b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2021
ms.locfileid: "52305974"
---
# <a name="configure-skype-for-business-hybrid"></a><span data-ttu-id="e6ced-103">Configurar Skype Empresarial híbrido</span><span class="sxs-lookup"><span data-stu-id="e6ced-103">Configure Skype for Business hybrid</span></span>

<span data-ttu-id="e6ced-104">Para configurar Skype Empresarial híbrido, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e6ced-104">To configure Skype for Business hybrid, you need to:</span></span>

- <span data-ttu-id="e6ced-105">[Configure el servicio perimetral local para federar con Teams](#configure-your-on-premises-edge-service-to-federate-with-teams).</span><span class="sxs-lookup"><span data-stu-id="e6ced-105">[Configure your on-premises Edge service to federate with Teams](#configure-your-on-premises-edge-service-to-federate-with-teams).</span></span>
- <span data-ttu-id="e6ced-106">[Configure el entorno local para que confíe en Teams y habilite el espacio de direcciones SIP compartido.](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-teams)</span><span class="sxs-lookup"><span data-stu-id="e6ced-106">[Configure your on-premises environment to trust Teams and enable shared SIP address space](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-teams).</span></span>
- <span data-ttu-id="e6ced-107">[Habilite el espacio de direcciones SIP compartido en su Teams organización](#enable-shared-sip-address-space-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="e6ced-107">[Enable shared SIP address space in your Teams organization](#enable-shared-sip-address-space-in-your-organization).</span></span>

<span data-ttu-id="e6ced-108">Si ha Exchange local, es posible que desee configurar OAuth entre los entornos Exchange local y Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="e6ced-108">If you have Exchange on-premises, you may want to configure OAuth between your Exchange on-premises and Skype for Business Online environments.</span></span> <span data-ttu-id="e6ced-109">Para obtener más información, vea [Manage server-to-server authentication in Skype Empresarial Server](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md) and Plan to integrate Skype Empresarial and [Exchange](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span><span class="sxs-lookup"><span data-stu-id="e6ced-109">For more information, see  [Manage server-to-server authentication in Skype for Business Server](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md) and [Plan to integrate Skype for Business and Exchange](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span></span> 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-teams"></a><span data-ttu-id="e6ced-110">Configurar el servicio perimetral local para federar con Teams</span><span class="sxs-lookup"><span data-stu-id="e6ced-110">Configure your on-premises Edge service to federate with Teams</span></span>

<span data-ttu-id="e6ced-111">La federación permite a los usuarios de la implementación local comunicarse con Teams y Skype Empresarial usuarios en línea de la organización.</span><span class="sxs-lookup"><span data-stu-id="e6ced-111">Federation allows users in your on-premises deployment to communicate with Teams and Skype for Business Online  users in your organization.</span></span> <span data-ttu-id="e6ced-112">Para configurar la federación, ejecute el siguiente cmdlet en el Shell Skype Empresarial Server administración:</span><span class="sxs-lookup"><span data-stu-id="e6ced-112">To configure federation, run the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

<span data-ttu-id="e6ced-113">Si el valor '-EnablePartnerDiscovery' se establece en $True, Skype Empresarial Server usará registros DNS para intentar detectar dominios de asociado que no aparecen en la lista AllowedDomains.</span><span class="sxs-lookup"><span data-stu-id="e6ced-113">If '-EnablePartnerDiscovery' value is set to $True, Skype for Business Server will use DNS records to try and discover partner domains not listed in the AllowedDomains list.</span></span> <span data-ttu-id="e6ced-114">Si el valor se establece en $False , Skype Empresarial Server solo se federará con los dominios que se encuentran en la lista AllowedDomains.</span><span class="sxs-lookup"><span data-stu-id="e6ced-114">If the value is set to $False , Skype for Business Server will only federate with domains found on the AllowedDomains list.</span></span> <span data-ttu-id="e6ced-115">Este parámetro es necesario si se usa el enrutamiento del servicio DNS.</span><span class="sxs-lookup"><span data-stu-id="e6ced-115">This parameter is required if you use DNS service routing.</span></span>

> [!NOTE]
> <span data-ttu-id="e6ced-116">Para obtener más información sobre cómo habilitar la federación entre los usuarios de la implementación de Skype Empresarial local y los usuarios de una organización de Microsoft 365, vea [Configuring federation support for a Microsoft 365 customer in Skype Empresarial Server](../../SfbServer/manage/federation-and-external-access/federation-support/configuring-federation-support.md).</span><span class="sxs-lookup"><span data-stu-id="e6ced-116">For more details about enabling federation between users of your on-premises Skype for Business deployment and users of a Microsoft 365 organization, see [Configuring federation support for a Microsoft 365 customer in Skype for Business Server](../../SfbServer/manage/federation-and-external-access/federation-support/configuring-federation-support.md).</span></span>


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-teams"></a><span data-ttu-id="e6ced-117">Configurar el entorno local para habilitar el espacio de direcciones SIP compartido con Teams</span><span class="sxs-lookup"><span data-stu-id="e6ced-117">Configure your on-premises environment to enable shared SIP address space with Teams</span></span>

<span data-ttu-id="e6ced-118">También debe configurar el entorno local para que confíe en Teams y habilite el espacio de direcciones SIP compartido.</span><span class="sxs-lookup"><span data-stu-id="e6ced-118">You must also configure your on-premises environment to trust Teams and enable shared SIP address space.</span></span> <span data-ttu-id="e6ced-119">Esta configuración significa Teams puede hospedar posiblemente cuentas de usuario para el mismo conjunto de dominios SIP que el entorno local, y los mensajes se pueden enrutar entre usuarios hospedados localmente y en línea.</span><span class="sxs-lookup"><span data-stu-id="e6ced-119">This configuration means Teams can potentially host user accounts for the same set of SIP domains as your on-premises environment, and messages can be routed between users hosted on premises and online.</span></span> <span data-ttu-id="e6ced-120">Debe configurar un proveedor de hospedaje con ProxyFqdn=sipfed.online.lync.com como se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="e6ced-120">You configuring a hosting provider with ProxyFqdn=sipfed.online.lync.com as described below.</span></span>

<span data-ttu-id="e6ced-121">En primer lugar, compruebe si ya tiene un proveedor de hospedaje con ProxyFqdn=sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="e6ced-121">First, check if you already have a hosting provider with ProxyFqdn=sipfed.online.lync.com.</span></span> <span data-ttu-id="e6ced-122">Si existe una, quítela mediante el siguiente comando en el Shell Skype Empresarial Server administración:</span><span class="sxs-lookup"><span data-stu-id="e6ced-122">If one exists, then remove it by using the following command in the Skype for Business Server Management Shell:</span></span>

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

<span data-ttu-id="e6ced-123">A continuación, cree un nuevo proveedor de hospedaje mediante el cmdlet New-CsHostingProvider siguiente:</span><span class="sxs-lookup"><span data-stu-id="e6ced-123">Then create a new hosting provider by using the New-CsHostingProvider cmdlet as follows:</span></span> 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-organization"></a><span data-ttu-id="e6ced-124">Habilitar el espacio de direcciones SIP compartido en la organización</span><span class="sxs-lookup"><span data-stu-id="e6ced-124">Enable shared SIP address space in your organization</span></span>
  
<span data-ttu-id="e6ced-125">Además del cambio realizado en la implementación local, deberá realizar el cambio correspondiente en la organización de Teams para habilitar el espacio de direcciones SIP compartido con la implementación local.</span><span class="sxs-lookup"><span data-stu-id="e6ced-125">In addition to the change you made in your on-premises deployment, you'll need to make the corresponding change in your Teams organization to enabled shared SIP address space with your on-premises deployment.</span></span>  

<span data-ttu-id="e6ced-126">Para habilitar el espacio de direcciones SIP compartido en la organización, establezca una sesión remota de PowerShell con Teams y, a continuación, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e6ced-126">To enable shared SIP address space in your organization, establish a remote PowerShell session with Teams, and then run the following cmdlet:</span></span>
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="e6ced-127">El atributo SharedSipAddressSpace debe permanecer "True" hasta que el traslado a línea sea definitivo y ningún usuario permanezca local.</span><span class="sxs-lookup"><span data-stu-id="e6ced-127">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="e6ced-128">Para establecer una sesión remota de PowerShell con Teams (o Skype Empresarial Online), primero debe instalar el módulo Teams [PowerShell](/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="e6ced-128">To establish a remote PowerShell session with Teams (or Skype for Business Online), you first need to install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span> <span data-ttu-id="e6ced-129">El Teams PowerShell reemplaza al módulo Skype busines Online Connector, que se ha retirado.</span><span class="sxs-lookup"><span data-stu-id="e6ced-129">The Teams PowerShell module replaces the Skype for Busines Online Connector module, which has been retired.</span></span>
  
<span data-ttu-id="e6ced-130">Después de instalar el módulo, puede establecer una sesión remota con los cmdlets siguientes:</span><span class="sxs-lookup"><span data-stu-id="e6ced-130">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

<span data-ttu-id="e6ced-131">Para obtener más información acerca de cómo establecer una sesión remota de PowerShell con Teams y cómo usar el módulo de PowerShell de Teams, vea Configurar el equipo para [Windows PowerShell](../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="e6ced-131">For more information about how to establish a remote PowerShell session with Teams, and how to use the Teams PowerShell module, see [Set up your computer for Windows PowerShell](../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  


## <a name="see-also"></a><span data-ttu-id="e6ced-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6ced-132">See also</span></span>

[<span data-ttu-id="e6ced-133">New-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="e6ced-133">New-CsHostingProvider</span></span>](/powershell/module/skype/new-cshostingprovider?view=skype-ps)
