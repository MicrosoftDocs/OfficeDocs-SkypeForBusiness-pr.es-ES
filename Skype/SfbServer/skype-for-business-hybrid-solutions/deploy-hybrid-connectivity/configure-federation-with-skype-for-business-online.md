---
title: Configurar la federación con Skype Empresarial Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/12/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: a10bd1d5-c003-46db-9f57-7d55d3fa08da
description: 'Resumen: Obtenga información sobre cómo configurar la interoperabilidad entre su implementación local y Skype para profesionales en línea.'
ms.openlocfilehash: 24a3d95c1da90abd083835a9838e246d25c8a954
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "19504449"
---
# <a name="configure-federation-with-skype-for-business-online"></a><span data-ttu-id="b187d-103">Configurar la federación con Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="b187d-103">Configure federation with Skype for Business Online</span></span>
 
<span data-ttu-id="b187d-104">**Resumen:** Obtenga información sobre cómo configurar la interoperabilidad entre su implementación local y Skype para profesionales en línea.</span><span class="sxs-lookup"><span data-stu-id="b187d-104">**Summary:** Learn how to configure interoperability between your on-premises deployment and Skype for Business Online.</span></span>
  
<span data-ttu-id="b187d-105">Siga los pasos descritos en esta sección para configurar la interoperabilidad entre su implementación local y Skype para profesionales en línea.</span><span class="sxs-lookup"><span data-stu-id="b187d-105">Follow the steps in this section to configure interoperability between your on-premises deployment and Skype for Business Online.</span></span>
  
## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a><span data-ttu-id="b187d-106">Configurar el servicio de borde de local para la federación con Skype para profesionales en línea</span><span class="sxs-lookup"><span data-stu-id="b187d-106">Configure your on-premises Edge service for federation with Skype for Business Online</span></span>

<span data-ttu-id="b187d-107">Federación permite a los usuarios en su implementación local para comunicarse con usuarios de Office 365 en su organización.</span><span class="sxs-lookup"><span data-stu-id="b187d-107">Federation allows users in your on-premises deployment to communicate with Office 365 users in your organization.</span></span> <span data-ttu-id="b187d-108">Para configurar la federación, ejecute los siguientes cmdlets en el Skype para Shell de administración de servidor empresarial:</span><span class="sxs-lookup"><span data-stu-id="b187d-108">To configure federation, run the following cmdlets in the Skype for Business Server Management Shell:</span></span>
  
```
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -EnablePartnerDiscovery 1 -UseDnsSrvRouting
```

```
New-CSHostingProvider -Identity SkypeforBusinessOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
```

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a><span data-ttu-id="b187d-109">Configurar su Skype para inquilino empresarial en línea para un espacio de direcciones SIP compartido</span><span class="sxs-lookup"><span data-stu-id="b187d-109">Configure your Skype for Business Online tenant for a shared SIP address space</span></span>

<span data-ttu-id="b187d-110">Una dirección de protocolo de inicio de sesión (SIP) es un identificador único para cada usuario de una red, parecido a un número de teléfono o a una dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="b187d-110">A Session Initiation Protocol (SIP) address is a unique identifier for each user on a network, similar to a phone number or an email address.</span></span> <span data-ttu-id="b187d-111">Antes de intentar mover usuarios de local a Skype para profesionales en línea, debe configurar el inquilino de Office 365 para compartir el espacio de direcciones de protocolo de inicio de sesión (SIP) compartidos con la implementación local.</span><span class="sxs-lookup"><span data-stu-id="b187d-111">Before you try to move users from on-premises to Skype for Business Online, you'll need to configure your Office 365 tenant to share the Shared Session Initiation Protocol (SIP) address space with your on-premises deployment.</span></span> <span data-ttu-id="b187d-112">Si no lo configura, es probable que se le presente el siguiente mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="b187d-112">If this is not configured, you may see the following error message:</span></span>
  
<span data-ttu-id="b187d-113">Move-CsUser: Tolerancia HostedMigration: Error=(510), descripción = (inquilino de este usuario no está habilitado para el espacio de direcciones sip compartido).</span><span class="sxs-lookup"><span data-stu-id="b187d-113">Move-CsUser : HostedMigration fault: Error=(510), Description=(This user's tenant is not enabled for shared sip address space.)</span></span>
  
<span data-ttu-id="b187d-114">Para configurar un espacio de direcciones SIP compartido, establecer una sesión remota de PowerShell con Skype para profesionales en línea y, a continuación, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b187d-114">To configure a shared SIP address space, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
  
```
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="b187d-115">El atributo SharedSipAddressSpace debe permanecer como "True" hasta que la transferencia a en línea sea final y no quede ningún usuario en local.</span><span class="sxs-lookup"><span data-stu-id="b187d-115">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="b187d-116">Para establecer una sesión remota de PowerShell con Skype para profesionales en línea, primero debe instalar el Skype para módulo del conector empresarial en línea para Windows PowerShell, que se puede obtener aquí: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span><span class="sxs-lookup"><span data-stu-id="b187d-116">To establish a remote PowerShell session with Skype for Business Online, you first need to install the Skype for Business Online connector module for Windows PowerShell, which you can get here: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span></span>
  
<span data-ttu-id="b187d-117">Después de instalar el módulo, puede establecer una sesión remota con los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="b187d-117">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
  
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

<span data-ttu-id="b187d-118">Para obtener más información acerca de cómo establecer una sesión remota de PowerShell con Skype para profesionales en línea, consulte [Connecting to Lync Online por Using Windows PowerShell](http://technet.microsoft.com/library/6167dad9-9628-4fdb-bed1-bdb3f7108e64.aspx).</span><span class="sxs-lookup"><span data-stu-id="b187d-118">For more information about how to establish a remote PowerShell session with Skype for Business Online, see [Connecting to Lync Online By Using Windows PowerShell](http://technet.microsoft.com/library/6167dad9-9628-4fdb-bed1-bdb3f7108e64.aspx).</span></span>
  
<span data-ttu-id="b187d-119">Para obtener más información acerca del uso de la Skype para el módulo de PowerShell de conector en línea de negocio, vea [Using Windows PowerShell para administrar Lync Online](http://technet.microsoft.com/library/9ef2d853-10fb-4e02-a552-dcf6818d7153.aspx).</span><span class="sxs-lookup"><span data-stu-id="b187d-119">For more information about using the Skype for Business Online connector PowerShell module, see [Using Windows PowerShell to Manage Lync Online](http://technet.microsoft.com/library/9ef2d853-10fb-4e02-a552-dcf6818d7153.aspx).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b187d-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="b187d-120">See also</span></span>

[<span data-ttu-id="b187d-121">New-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="b187d-121">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)