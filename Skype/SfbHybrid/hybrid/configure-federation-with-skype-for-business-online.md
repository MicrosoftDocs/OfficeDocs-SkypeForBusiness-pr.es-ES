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
ms.openlocfilehash: 0df507fcc47157a9290018a199e1362cb203048b
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221454"
---
# <a name="configure-skype-for-business-hybrid"></a><span data-ttu-id="88f82-103">Configurar Skype Empresarial híbrido</span><span class="sxs-lookup"><span data-stu-id="88f82-103">Configure Skype for Business hybrid</span></span>

<span data-ttu-id="88f82-104">Para configurar Skype Empresarial híbrido, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="88f82-104">To configure Skype for Business hybrid, you need to:</span></span>

- <span data-ttu-id="88f82-105">[Configure el servicio perimetral local para federar con Microsoft 365 u Office 365.](#configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365)</span><span class="sxs-lookup"><span data-stu-id="88f82-105">[Configure your on-premises Edge service to federate with Microsoft 365 or Office 365](#configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365).</span></span>
- <span data-ttu-id="88f82-106">Configure su entorno local para que confíe en [Microsoft 365 u Office 365 y](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365)habilite el espacio de direcciones SIP compartido.</span><span class="sxs-lookup"><span data-stu-id="88f82-106">[Configure your on-premises environment to trust Microsoft 365 or Office 365 and enable shared SIP address space](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365).</span></span>
- <span data-ttu-id="88f82-107">[Habilite el espacio de direcciones SIP compartido en su organización de Microsoft 365 u Office 365.](#enable-shared-sip-address-space-in-your-organization)</span><span class="sxs-lookup"><span data-stu-id="88f82-107">[Enable shared SIP address space in your Microsoft 365 or Office 365 organization](#enable-shared-sip-address-space-in-your-organization).</span></span>

<span data-ttu-id="88f82-108">Tenga en cuenta que si tiene Exchange local, es posible que desee configurar OAuth entre los entornos de Exchange local y Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="88f82-108">Note that if you have Exchange on-premises, you may want to configure OAuth between your Exchange on-premises and Skype for Business Online environments.</span></span> <span data-ttu-id="88f82-109">Para obtener más información, vea Administrar la autenticación de servidor a servidor en Skype Empresarial [Server](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) y planear la integración de Skype Empresarial [y Exchange.](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support)</span><span class="sxs-lookup"><span data-stu-id="88f82-109">For more information, see  [Manage server-to-server authentication in Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) and [Plan to integrate Skype for Business and Exchange](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support).</span></span> 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365"></a><span data-ttu-id="88f82-110">Configurar el servicio perimetral local para federar con Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="88f82-110">Configure your on-premises Edge service to federate with Microsoft 365 or Office 365</span></span>

<span data-ttu-id="88f82-111">La federación permite a los usuarios de la implementación local comunicarse con los usuarios de Microsoft 365 u Office 365 de su organización.</span><span class="sxs-lookup"><span data-stu-id="88f82-111">Federation allows users in your on-premises deployment to communicate with Microsoft 365 or Office 365 users in your organization.</span></span> <span data-ttu-id="88f82-112">Para configurar la federación, ejecute el siguiente cmdlet en el Shell de administración de Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="88f82-112">To configure federation, run the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

<span data-ttu-id="88f82-113">Si el valor "-EnablePartnerDiscovery" se establece en $True, Skype Empresarial Server usará registros DNS para intentar detectar dominios de socios que no aparecen en la lista AllowedDomains.</span><span class="sxs-lookup"><span data-stu-id="88f82-113">If '-EnablePartnerDiscovery' value is set to $True, Skype for Business Server will use DNS records to try and discover partner domains not listed in the AllowedDomains list.</span></span> <span data-ttu-id="88f82-114">Si el valor se establece en $False, Skype Empresarial Server solo se federará con los dominios que se encuentran en la lista AllowedDomains.</span><span class="sxs-lookup"><span data-stu-id="88f82-114">If the value is set to $False , Skype for Business Server will only federate with domains found on the AllowedDomains list.</span></span> <span data-ttu-id="88f82-115">Este parámetro es necesario si se usa el enrutamiento del servicio DNS.</span><span class="sxs-lookup"><span data-stu-id="88f82-115">This parameter is required if you use DNS service routing.</span></span>

> [!NOTE]
> <span data-ttu-id="88f82-116">Para obtener más información sobre cómo habilitar la federación entre los usuarios de la implementación local de Skype Empresarial y los usuarios de una organización de Skype Empresarial Online, consulte Configurar la compatibilidad de federación para un cliente de Skype Empresarial Online en [Skype Empresarial Server.](https://docs.microsoft.com/skypeforbusiness/manage/federation-and-external-access/federation-support/configuring-federation-support)</span><span class="sxs-lookup"><span data-stu-id="88f82-116">For more details about enabling federation between users of your on-premises Skype for Business deployment and users of a Skype for Business Online organization, see [Configuring federation support for a Skype for Business Online customer in Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/manage/federation-and-external-access/federation-support/configuring-federation-support).</span></span>


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365"></a><span data-ttu-id="88f82-117">Configurar el entorno local para habilitar el espacio de direcciones SIP compartido con Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="88f82-117">Configure your on-premises environment to enable shared SIP address space with Microsoft 365 or Office 365</span></span>

<span data-ttu-id="88f82-118">También debe configurar el entorno local para que confíe en Microsoft 365 u Office 365 y habilite el espacio de direcciones SIP compartido.</span><span class="sxs-lookup"><span data-stu-id="88f82-118">You must also configure your on-premises environment to trust Microsoft 365 or Office 365 and enable shared SIP address space.</span></span> <span data-ttu-id="88f82-119">Esto significa que Microsoft 365 u Office 365 pueden hospedar potencialmente cuentas de usuario para el mismo conjunto de dominios SIP que el entorno local, y los mensajes se pueden enrutar entre usuarios hospedados localmente y en línea.</span><span class="sxs-lookup"><span data-stu-id="88f82-119">This means Microsoft 365 or Office 365 can potentially host user accounts for the same set of SIP domains as your on-premises environment, and messages can be routed between users hosted on premises and online.</span></span>  <span data-ttu-id="88f82-120">Para ello, configure un proveedor de hospedaje con ProxyFqdn=sipfed.online.lync.com, como se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="88f82-120">You do this by configuring a hosting provider with ProxyFqdn=sipfed.online.lync.com as described below.</span></span>

<span data-ttu-id="88f82-121">En primer lugar, compruebe si ya tiene un proveedor de hospedaje con ProxyFqdn=sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="88f82-121">First, check if you already have a hosting provider with ProxyFqdn=sipfed.online.lync.com.</span></span> <span data-ttu-id="88f82-122">Si existe alguna, quítela mediante el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="88f82-122">If one exists, then remove it by using the following command:</span></span>

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

<span data-ttu-id="88f82-123">A continuación, cree un nuevo proveedor de hospedaje, use New-CsHostingProvider cmdlet como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="88f82-123">Then create a new hosting provider, use the New-CsHostingProvider cmdlet as follows:</span></span> 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-organization"></a><span data-ttu-id="88f82-124">Habilitar el espacio de direcciones SIP compartido en la organización</span><span class="sxs-lookup"><span data-stu-id="88f82-124">Enable shared SIP address space in your organization</span></span>
  
<span data-ttu-id="88f82-125">Además del cambio realizado en la implementación local, deberá realizar el cambio correspondiente en su organización de Microsoft 365 u Office 365 para habilitar el espacio de direcciones SIP compartido con la implementación local.</span><span class="sxs-lookup"><span data-stu-id="88f82-125">In addition to the change you made in your on-premises deployment, you'll need to make the corresponding change in your Microsoft 365 or Office 365 organization to enabled shared SIP address space with your on-premises deployment.</span></span>  

<span data-ttu-id="88f82-126">Para habilitar el espacio de direcciones SIP compartido en su organización, establezca una sesión remota de PowerShell con Skype Empresarial Online y, a continuación, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="88f82-126">To enable shared SIP address space in your organization, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="88f82-127">El atributo SharedSipAddressSpace debe permanecer "True" hasta que la conexión sea final y ningún usuario permanezca local.</span><span class="sxs-lookup"><span data-stu-id="88f82-127">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="88f82-128">Para establecer una sesión remota de PowerShell con Teams o Skype Empresarial Online, primero debe instalar el módulo de conector de Skype Empresarial Online para Windows PowerShell, que puede obtener [aquí.](https://go.microsoft.com/fwlink/p/?LinkId=391911)</span><span class="sxs-lookup"><span data-stu-id="88f82-128">To establish a remote PowerShell session with Teams or Skype for Business Online, you first need to install the Skype for Business Online connector module for Windows PowerShell, which you can get [here](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span></span>
  
<span data-ttu-id="88f82-129">Después de instalar el módulo, puede establecer una sesión remota con los cmdlets siguientes:</span><span class="sxs-lookup"><span data-stu-id="88f82-129">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
  
```PowerShell
$cred = Get-Credential
Import-PSSession (New-CsOnlineSession -Credential $cred) -AllowClobber
```

<span data-ttu-id="88f82-130">Para obtener más información acerca de cómo establecer una sesión remota de PowerShell con Skype Empresarial Online y cómo usar el módulo conector de Skype Empresarial Online, consulte Configurar el equipo para [Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="88f82-130">For more information about how to establish a remote PowerShell session with Skype for Business Online, and how to use the Skype for Business Online Connector module, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  


## <a name="see-also"></a><span data-ttu-id="88f82-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="88f82-131">See also</span></span>

[<span data-ttu-id="88f82-132">New-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="88f82-132">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)
