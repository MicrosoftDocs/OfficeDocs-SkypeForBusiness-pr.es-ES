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
ms.openlocfilehash: fb04ecd53c93ae7bd64fca760b752d2d69324c3d
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295358"
---
# <a name="configure-skype-for-business-hybrid"></a><span data-ttu-id="17566-103">Configuración de Skype para entornos híbridos de negocio</span><span class="sxs-lookup"><span data-stu-id="17566-103">Configure Skype for Business hybrid</span></span>

<span data-ttu-id="17566-104">Para configurar Skype para entornos híbridos de negocio, debe:</span><span class="sxs-lookup"><span data-stu-id="17566-104">To configure Skype for Business hybrid, you need to:</span></span>

- [<span data-ttu-id="17566-105">Configurar la federación</span><span class="sxs-lookup"><span data-stu-id="17566-105">Configure federation</span></span>](#configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online)
- [<span data-ttu-id="17566-106">Configurar un espacio de direcciones de protocolo de inicio de sesión (SIP) compartida</span><span class="sxs-lookup"><span data-stu-id="17566-106">Configure a shared Session Initiation Protocol (SIP) address space</span></span>](#configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space)
- [<span data-ttu-id="17566-107">Configurar la autenticación de servidor a servidor si es necesario</span><span class="sxs-lookup"><span data-stu-id="17566-107">Configure server-to-server authentication if required</span></span>](#configure-server-to-server-authentication-if-required)
  
## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a><span data-ttu-id="17566-108">Configurar el servicio de borde de local para la federación con Skype para profesionales en línea</span><span class="sxs-lookup"><span data-stu-id="17566-108">Configure your on-premises Edge service for federation with Skype for Business Online</span></span>

<span data-ttu-id="17566-109">Federación permite a los usuarios en su implementación local para comunicarse con usuarios de Office 365 en su organización.</span><span class="sxs-lookup"><span data-stu-id="17566-109">Federation allows users in your on-premises deployment to communicate with Office 365 users in your organization.</span></span> <span data-ttu-id="17566-110">Para configurar la federación, ejecute los siguientes cmdlets en el Skype para Shell de administración de servidor empresarial:</span><span class="sxs-lookup"><span data-stu-id="17566-110">To configure federation, run the following cmdlets in the Skype for Business Server Management Shell:</span></span>
  
```
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -EnablePartnerDiscovery 1 -UseDnsSrvRouting
```

```
New-CSHostingProvider -Identity SkypeforBusinessOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
```

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a><span data-ttu-id="17566-111">Configurar su Skype para inquilino empresarial en línea para un espacio de direcciones SIP compartido</span><span class="sxs-lookup"><span data-stu-id="17566-111">Configure your Skype for Business Online tenant for a shared SIP address space</span></span>

<span data-ttu-id="17566-112">Una dirección de protocolo de inicio de sesión (SIP) es un identificador único para cada usuario de una red, parecido a un número de teléfono o a una dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="17566-112">A Session Initiation Protocol (SIP) address is a unique identifier for each user on a network, similar to a phone number or an email address.</span></span> <span data-ttu-id="17566-113">Antes de intentar mover usuarios de local a Skype para profesionales en línea, debe configurar el inquilino de Office 365 para compartir el espacio de direcciones de protocolo de inicio de sesión (SIP) compartidos con la implementación local.</span><span class="sxs-lookup"><span data-stu-id="17566-113">Before you try to move users from on-premises to Skype for Business Online, you'll need to configure your Office 365 tenant to share the Shared Session Initiation Protocol (SIP) address space with your on-premises deployment.</span></span> <span data-ttu-id="17566-114">Si no lo configura, es probable que se le presente el siguiente mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="17566-114">If this is not configured, you may see the following error message:</span></span>
  
<span data-ttu-id="17566-115">Move-CsUser: Tolerancia HostedMigration: Error=(510), descripción = (inquilino de este usuario no está habilitado para el espacio de direcciones sip compartido).</span><span class="sxs-lookup"><span data-stu-id="17566-115">Move-CsUser : HostedMigration fault: Error=(510), Description=(This user's tenant is not enabled for shared sip address space.)</span></span>
  
<span data-ttu-id="17566-116">Para configurar un espacio de direcciones SIP compartido, establecer una sesión remota de PowerShell con Skype para profesionales en línea y, a continuación, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="17566-116">To configure a shared SIP address space, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
  
```
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="17566-117">El atributo SharedSipAddressSpace debe permanecer como "True" hasta que la transferencia a en línea sea final y no quede ningún usuario en local.</span><span class="sxs-lookup"><span data-stu-id="17566-117">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="17566-118">Para establecer una sesión remota de PowerShell con Skype para profesionales en línea, primero debe instalar el Skype para módulo del conector empresarial en línea para Windows PowerShell, que se puede obtener [aquí](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span><span class="sxs-lookup"><span data-stu-id="17566-118">To establish a remote PowerShell session with Skype for Business Online, you first need to install the Skype for Business Online connector module for Windows PowerShell, which you can get [here](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span></span>
  
<span data-ttu-id="17566-119">Después de instalar el módulo, puede establecer una sesión remota con los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="17566-119">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
  
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

<span data-ttu-id="17566-120">Para obtener más información acerca de cómo establecer una sesión remota de PowerShell con Skype para profesionales en línea y cómo usar el Skype para el módulo del conector en línea de negocio, vea [Configurar el equipo de Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="17566-120">For more information about how to establish a remote PowerShell session with Skype for Business Online, and how to use the Skype for Business Online Connector module, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  
## <a name="configure-server-to-server-authentication-if-required"></a><span data-ttu-id="17566-121">Configurar la autenticación de servidor a servidor si es necesario</span><span class="sxs-lookup"><span data-stu-id="17566-121">Configure server-to-server authentication if required</span></span>

<span data-ttu-id="17566-122">En función del tipo de entorno híbrido que está configurando, deberá configurar la autenticación de servidor a servidor.</span><span class="sxs-lookup"><span data-stu-id="17566-122">Depending on the type of hybrid environment you are configuring, you may need to configure server-to-server authentication.</span></span>  <span data-ttu-id="17566-123">Para obtener más información, vea [Administrar la autenticación de servidor a servidor en Skype para Business Server](https://docs.microsoft.com/en-us/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications).</span><span class="sxs-lookup"><span data-stu-id="17566-123">For more information, see  [Manage server-to-server authentication in Skype for Business Server](https://docs.microsoft.com/en-us/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications).</span></span>


## <a name="see-also"></a><span data-ttu-id="17566-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="17566-124">See also</span></span>

[<span data-ttu-id="17566-125">New-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="17566-125">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)

