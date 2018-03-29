---
title: Configurar la federación con Skype Empresarial Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/12/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: a10bd1d5-c003-46db-9f57-7d55d3fa08da
description: 'Resumen: Conozca cómo configurar interoperabilidad entre su implementación local y Skype para los negocios en línea.'
ms.openlocfilehash: 1a08fdb9ad9522e50bc412adcc9214fff3bbb924
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-federation-with-skype-for-business-online"></a><span data-ttu-id="cf6d2-103">Configurar la federación con Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="cf6d2-103">Configure federation with Skype for Business Online</span></span>
 
<span data-ttu-id="cf6d2-104">**Resumen:** Aprenda a configurar interoperabilidad entre su implementación local y Skype para los negocios en línea.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-104">**Summary:** Learn how to configure interoperability between your on-premises deployment and Skype for Business Online.</span></span>
  
<span data-ttu-id="cf6d2-105">Siga los pasos de esta sección para configurar la interoperabilidad entre su implementación local y Skype para los negocios en línea.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-105">Follow the steps in this section to configure interoperability between your on-premises deployment and Skype for Business Online.</span></span>
  
## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a><span data-ttu-id="cf6d2-106">Configurar el servicio de extremo local para la federación con Skype para los negocios en línea</span><span class="sxs-lookup"><span data-stu-id="cf6d2-106">Configure your on-premises Edge service for federation with Skype for Business Online</span></span>

<span data-ttu-id="cf6d2-107">La federación permite a los usuarios en la implementación local para comunicarse con usuarios de Office 365 en su organización.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-107">Federation allows users in your on-premises deployment to communicate with Office 365 users in your organization.</span></span> <span data-ttu-id="cf6d2-108">Para configurar la federación, ejecute los siguientes cmdlets en el Skype para el Shell de administración de servidor de negocios:</span><span class="sxs-lookup"><span data-stu-id="cf6d2-108">To configure federation, run the following cmdlets in the Skype for Business Server Management Shell:</span></span>
  
```
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -EnablePartnerDiscovery 1 -UseDnsSrvRouting
```

```
New-CSHostingProvider -Identity SkypeforBusinessOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
```

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a><span data-ttu-id="cf6d2-109">Configurar el Skype para los negocios en línea arrendatario para un espacio de direcciones compartido de SIP</span><span class="sxs-lookup"><span data-stu-id="cf6d2-109">Configure your Skype for Business Online tenant for a shared SIP address space</span></span>

<span data-ttu-id="cf6d2-110">Una dirección de protocolo de inicio de sesión (SIP) es un identificador único para cada usuario de una red, parecido a un número de teléfono o a una dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-110">A Session Initiation Protocol (SIP) address is a unique identifier for each user on a network, similar to a phone number or an email address.</span></span> <span data-ttu-id="cf6d2-111">Antes de intentar mover usuarios desde local a Skype para los negocios en línea, necesitará configurar el inquilino Office 365 para compartir el espacio de direcciones de protocolo de inicio de sesión (SIP) compartida con su implementación local.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-111">Before you try to move users from on-premises to Skype for Business Online, you'll need to configure your Office 365 tenant to share the Shared Session Initiation Protocol (SIP) address space with your on-premises deployment.</span></span> <span data-ttu-id="cf6d2-112">Si no lo configura, es probable que se le presente el siguiente mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="cf6d2-112">If this is not configured, you may see the following error message:</span></span>
  
<span data-ttu-id="cf6d2-113">Move-CsUser: Error de HostedMigration: Error=(510), descripción = (inquilino de este usuario no está habilitado para el espacio de direcciones compartido sip).</span><span class="sxs-lookup"><span data-stu-id="cf6d2-113">Move-CsUser : HostedMigration fault: Error=(510), Description=(This user's tenant is not enabled for shared sip address space.)</span></span>
  
<span data-ttu-id="cf6d2-114">Para configurar un espacio de direcciones compartido de SIP, establecer una sesión remota de PowerShell con Skype para los negocios en línea y, a continuación, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="cf6d2-114">To configure a shared SIP address space, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
  
```
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="cf6d2-115">El atributo SharedSipAddressSpace debe permanecer como "True" hasta que la transferencia a en línea sea final y no quede ningún usuario en local.</span><span class="sxs-lookup"><span data-stu-id="cf6d2-115">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="cf6d2-116">Para establecer una sesión remota de PowerShell con Skype para los negocios en línea, primero debe instalar el Skype para el módulo del conector de negocios en línea para Windows PowerShell, que se puede obtener aquí: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span><span class="sxs-lookup"><span data-stu-id="cf6d2-116">To establish a remote PowerShell session with Skype for Business Online, you first need to install the Skype for Business Online connector module for Windows PowerShell, which you can get here: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span></span>
  
<span data-ttu-id="cf6d2-117">Después de instalar el módulo, puede establecer una sesión remota con los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="cf6d2-117">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
  
```
Import-Module SkypeOnlineConnector
```

```
$cred = Get-Credential
```

```
$CSSession = New-CsOnlineSession -Credential $cred
```

```
Import-PSSession $CSSession -AllowClobber
```

<span data-ttu-id="cf6d2-118">Para obtener más información acerca de cómo establecer una sesión remota de PowerShell con Skype para los negocios en línea, vea [conectarse a Lync Online por utilizando Windows PowerShell](http://technet.microsoft.com/library/6167dad9-9628-4fdb-bed1-bdb3f7108e64.aspx).</span><span class="sxs-lookup"><span data-stu-id="cf6d2-118">For more information about how to establish a remote PowerShell session with Skype for Business Online, see [Connecting to Lync Online By Using Windows PowerShell](http://technet.microsoft.com/library/6167dad9-9628-4fdb-bed1-bdb3f7108e64.aspx).</span></span>
  
<span data-ttu-id="cf6d2-119">Para obtener más información acerca de cómo utilizar el Skype para el módulo de PowerShell de conector negocios en línea, consulte [Uso de Windows PowerShell para administrar Lync Online](http://technet.microsoft.com/library/9ef2d853-10fb-4e02-a552-dcf6818d7153.aspx).</span><span class="sxs-lookup"><span data-stu-id="cf6d2-119">For more information about using the Skype for Business Online connector PowerShell module, see [Using Windows PowerShell to Manage Lync Online](http://technet.microsoft.com/library/9ef2d853-10fb-4e02-a552-dcf6818d7153.aspx).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cf6d2-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf6d2-120">See also</span></span>

#### 

[<span data-ttu-id="cf6d2-121">Nueva CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="cf6d2-121">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)

