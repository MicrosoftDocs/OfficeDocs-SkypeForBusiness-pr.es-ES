---
title: Configuración de Skype para entornos híbridos de negocio
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: 'Resumen: Obtenga información sobre cómo configurar la interoperabilidad entre su implementación local y Skype para profesionales en línea.'
ms.openlocfilehash: b71ea92b5f7ce275dc5d1b5d2b7ece5be3c77ffc
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/13/2018
ms.locfileid: "27244007"
---
# <a name="configure-skype-for-business-hybrid"></a><span data-ttu-id="02777-103">Configuración de Skype para entornos híbridos de negocio</span><span class="sxs-lookup"><span data-stu-id="02777-103">Configure Skype for Business hybrid</span></span>

<span data-ttu-id="02777-104">Para configurar Skype para entornos híbridos de negocio, debe:</span><span class="sxs-lookup"><span data-stu-id="02777-104">To configure Skype for Business hybrid, you need to:</span></span>

- [<span data-ttu-id="02777-105">Configurar el entorno local para federar con Office 365.</span><span class="sxs-lookup"><span data-stu-id="02777-105">Configure your on-premises environment to federate with Office 365.</span></span>](#configure-your-on-premises-edge-service-to-federate-with-Office-365)
- [<span data-ttu-id="02777-106">Configurar su entorno local para que confíe en Office 365 y habilitar el espacio de direcciones SIP compartido con Office 365.</span><span class="sxs-lookup"><span data-stu-id="02777-106">Configure your on-premises environment to trust Office 365 and enable shared SIP address space with Office 365.</span></span>](#configure-your-on-premises-environment-to-share-your-SIP-address-space-with-Office-365)
- [<span data-ttu-id="02777-107">Habilitar el espacio de direcciones SIP compartido en el inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="02777-107">Enable shared SIP address space in your Office 365 tenant.</span></span>](#configure-server-to-server-authentication-if-required)

<span data-ttu-id="02777-108">Tenga en cuenta que si dispone de Exchange local, es posible que desea configurar OAuth entre la organización local de Exchange y Skype para entornos en línea de negocio.</span><span class="sxs-lookup"><span data-stu-id="02777-108">Note that if you have Exchange on-premises, you may want to configure OAuth between your Exchange on-premises and Skype for Business Online environments.</span></span> <span data-ttu-id="02777-109">Para obtener más información, vea [Administrar la autenticación de servidor a servidor en Skype para Business Server](https://docs.microsoft.com/en-us/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) y [Planear la integración de Skype para empresas y Exchange](https://docs.microsoft.com/en-us/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support).</span><span class="sxs-lookup"><span data-stu-id="02777-109">For more information, see  [Manage server-to-server authentication in Skype for Business Server](https://docs.microsoft.com/en-us/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) and [Plan to integrate Skype for Business and Exchange](https://docs.microsoft.com/en-us/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support).</span></span> 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-office-365"></a><span data-ttu-id="02777-110">Configure su servicio de perimetral local para federar con Office 365</span><span class="sxs-lookup"><span data-stu-id="02777-110">Configure your on-premises Edge service to federate with Office 365</span></span>

<span data-ttu-id="02777-111">Federación permite a los usuarios en su implementación local para comunicarse con usuarios de Office 365 en su organización.</span><span class="sxs-lookup"><span data-stu-id="02777-111">Federation allows users in your on-premises deployment to communicate with Office 365 users in your organization.</span></span> <span data-ttu-id="02777-112">Para configurar la federación, ejecute el siguiente cmdlet en el Skype para Shell de administración de servidor empresarial:</span><span class="sxs-lookup"><span data-stu-id="02777-112">To configure federation, run the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -EnablePartnerDiscovery 1 -UseDnsSrvRouting
```



## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365"></a><span data-ttu-id="02777-113">Configurar el entorno local para habilitar el espacio de direcciones SIP compartido con Office 365</span><span class="sxs-lookup"><span data-stu-id="02777-113">Configure your on-premises environment to enable shared SIP address space with Office 365</span></span>

<span data-ttu-id="02777-114">También debe configurar el entorno local para que confíe en Office 365 y habilitar el espacio de direcciones SIP compartido con Office 365.</span><span class="sxs-lookup"><span data-stu-id="02777-114">You must also configure your on-premises environment to trust Office 365 and enable shared SIP address space with Office 365.</span></span> <span data-ttu-id="02777-115">Esto significa que Office 365 puede hospedar potencialmente cuentas de usuario para el mismo conjunto de dominios SIP que su entorno local, y pueden ser mensajes enrutados entre los usuarios alojados en local y en línea.</span><span class="sxs-lookup"><span data-stu-id="02777-115">This means Office 365 can potentially host user accounts for the same set of SIP domains as your on-premises environment, and messages can be routed between users hosted on premises and online.</span></span>  <span data-ttu-id="02777-116">Para ello, mediante la configuración de un proveedor de hospedaje con ProxyFqdn=sipfed.online.lync.com tal y como se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="02777-116">You do this by configuring a hosting provider with ProxyFqdn=sipfed.online.lync.com as described below.</span></span>

<span data-ttu-id="02777-117">En primer lugar, compruebe si ya tiene un proveedor de hospedaje con ProxyFqdn=sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="02777-117">First, check if you already have a hosting provider with ProxyFqdn=sipfed.online.lync.com.</span></span> <span data-ttu-id="02777-118">Si lo hay, a continuación, quitarlo mediante el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="02777-118">If one exists, then remove it by using the following command:</span></span>

```
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

<span data-ttu-id="02777-119">A continuación, cree un nuevo proveedor de hospedaje, use el cmdlet New-CsHostingProvider como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="02777-119">Then create a new hosting provider, use the New-CsHostingProvider cmdlet as follows:</span></span> 

```
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-office-365-tenant"></a><span data-ttu-id="02777-120">Habilitar el espacio de direcciones SIP compartido en el inquilino de Office 365</span><span class="sxs-lookup"><span data-stu-id="02777-120">Enable shared SIP address space in your Office 365 tenant</span></span>
  
<span data-ttu-id="02777-121">Además del cambio realizado en la implementación local, debe realizar el cambio correspondiente en el inquilino de Office 365 para el espacio de direcciones SIP compartido habilitado con la implementación local.</span><span class="sxs-lookup"><span data-stu-id="02777-121">In addition to the change you made in your on-premises deployment, you'll need to make the corresponding change in your Office 365 tenant to enabled shared SIP address space with your on-premises deployment.</span></span>  

<span data-ttu-id="02777-122">Para habilitar el espacio de direcciones SIP compartido en el inquilino de Office 365, establecer una sesión remota de PowerShell con Skype para profesionales en línea y, a continuación, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="02777-122">To enable shared SIP address space in your Office 365 tenant, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
  
```
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="02777-123">El atributo SharedSipAddressSpace debe permanecer como "True" hasta que la transferencia a en línea sea final y no quede ningún usuario en local.</span><span class="sxs-lookup"><span data-stu-id="02777-123">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="02777-124">Para establecer una sesión remota de PowerShell con los equipos o Skype para profesionales en línea, primero debe instalar el Skype para módulo del conector empresarial en línea para Windows PowerShell, que se puede obtener [aquí](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span><span class="sxs-lookup"><span data-stu-id="02777-124">To establish a remote PowerShell session with Teams or Skype for Business Online, you first need to install the Skype for Business Online connector module for Windows PowerShell, which you can get [here](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span></span>
  
<span data-ttu-id="02777-125">Después de instalar el módulo, puede establecer una sesión remota con los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="02777-125">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
  
```
$cred = Get-Credential
Import-PSSession (New-CsOnlineSession -Credential $cred) -AllowClobber
```

<span data-ttu-id="02777-126">Para obtener más información acerca de cómo establecer una sesión remota de PowerShell con Skype para profesionales en línea y cómo usar el Skype para el módulo del conector en línea de negocio, vea [Configurar el equipo de Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="02777-126">For more information about how to establish a remote PowerShell session with Skype for Business Online, and how to use the Skype for Business Online Connector module, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  


## <a name="see-also"></a><span data-ttu-id="02777-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="02777-127">See also</span></span>

[<span data-ttu-id="02777-128">New-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="02777-128">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)

