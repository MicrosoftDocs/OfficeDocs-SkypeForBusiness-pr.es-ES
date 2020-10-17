---
title: 'Lync Server 2013: configurar la Federación con Lync Online'
description: 'Lync Server 2013: configurar la Federación con Lync Online.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure federation with Lync Online
ms:assetid: a10bd1d5-c003-46db-9f57-7d55d3fa08da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205126(v=OCS.15)
ms:contentKeyID: 48184946
ms.date: 08/15/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3372a76b5ff7ad9dde5a00fd562b74877bd679a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553316"
---
# <a name="configure-federation-of-lync-server-2013-with-lync-online"></a><span data-ttu-id="7873c-103">Configurar la Federación de Lync Server 2013 con Lync Online</span><span class="sxs-lookup"><span data-stu-id="7873c-103">Configure federation of Lync Server 2013 with Lync Online</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7873c-104">_**Última modificación del tema:** 2016-08-15_</span><span class="sxs-lookup"><span data-stu-id="7873c-104">_**Topic Last Modified:** 2016-08-15_</span></span>

<span data-ttu-id="7873c-105">Siga los pasos de esta sección para configurar la interoperabilidad entre su implementación local y Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="7873c-105">Follow the steps in this section to configure interoperability between your on-premises deployment and Skype for Business Online.</span></span>

<span id="a"></span>

<div>

## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a><span data-ttu-id="7873c-106">Configurar el servicio perimetral local para la Federación con Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="7873c-106">Configure Your On-Premises Edge Service for Federation with Skype for Business Online</span></span>

<span data-ttu-id="7873c-107">La Federación permite que los usuarios de su implementación local se comuniquen con los usuarios de Microsoft 365 o Office 365 en su organización.</span><span class="sxs-lookup"><span data-stu-id="7873c-107">Federation allows users in your on-premises deployment to communicate with Microsoft 365 or Office 365 users in your organization.</span></span> <span data-ttu-id="7873c-108">Para configurar la Federación, ejecute los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="7873c-108">To configure federation, run the following cmdlets:</span></span>

   ```powershell
    Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $True
   ```

   ```powershell
    New-CSHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
   ```

</div>

<span id="b"></span>

<div>

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a><span data-ttu-id="7873c-109">Configurar el inquilino de Skype empresarial online para un espacio de direcciones SIP compartido</span><span class="sxs-lookup"><span data-stu-id="7873c-109">Configure Your Skype for Business Online Tenant for a Shared SIP Address Space</span></span>

<span data-ttu-id="7873c-110">Una dirección de protocolo de inicio de sesión (SIP) es un identificador único para cada usuario de una red, similar a un número de teléfono o a una dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="7873c-110">A Session Initiation Protocol (SIP) address is a unique identifier for each user on a network, similar to a phone number or an email address.</span></span> <span data-ttu-id="7873c-111">Antes de intentar mover a los usuarios de Lync de forma local a Skype empresarial online, necesitará configurar la organización de Microsoft 365 u Office 365 para compartir el espacio de direcciones del Protocolo de inicio de sesión (SIP) compartido con su implementación local.</span><span class="sxs-lookup"><span data-stu-id="7873c-111">Before you try to move Lync users from on-premises to Skype for Business Online, you’ll need to configure your Microsoft 365 or Office 365 organization to share the Shared Session Initiation Protocol (SIP) address space with your on-premises deployment.</span></span> <span data-ttu-id="7873c-112">Si no está configurado, es posible que vea el siguiente mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="7873c-112">If this is not configured, you may see the following error message:</span></span>

<span data-ttu-id="7873c-113">Move-CsUser: error de HostedMigration: error = (510), descripción = (el inquilino del usuario no está habilitado para el espacio de direcciones SIP compartido).</span><span class="sxs-lookup"><span data-stu-id="7873c-113">Move-CsUser : HostedMigration fault: Error=(510), Description=(This user’s tenant is not enabled for shared sip address space.)</span></span>

<span data-ttu-id="7873c-114">Para configurar un espacio de direcciones SIP compartido, establezca una sesión de PowerShell remota con Skype empresarial online y, a continuación, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="7873c-114">To configure a shared SIP address space, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
```powershell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```
<span data-ttu-id="7873c-115">Para establecer una sesión de PowerShell remota con Skype empresarial online, primero debe instalar el módulo de Skype empresarial online para Windows PowerShell, que puede obtener aquí: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?linkid=391911) .</span><span class="sxs-lookup"><span data-stu-id="7873c-115">To establish a remote PowerShell session with Skype for Business Online, you first need to install the Skype for Business Online module for Windows PowerShell, which you can get here: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?linkid=391911).</span></span>

<span data-ttu-id="7873c-116">Después de instalar el módulo, puede establecer una sesión remota con los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="7873c-116">After you install the module, you can establish a remote session with the following cmdlets:</span></span>

   ```powershell
    Import-Module LyncOnlineConnector
   ```

   ```powershell
    $cred = Get-Credential
   ``` 

   ```powershell
    $CSSession = New-CsOnlineSession -Credential $cred
   ```

   ```powershell
    Import-PSSession $CSSession -AllowClobber
   ```

<span data-ttu-id="7873c-117">Para obtener más información acerca de cómo establecer una sesión de PowerShell remota con Skype empresarial online, consulte [conectarse a Skype empresarial online mediante Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="7873c-117">For more information about how to establish a remote PowerShell session with Skype for Business Online, see [Connecting to Skype for Business Online by using Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

<span data-ttu-id="7873c-118">Para obtener más información sobre el uso del módulo de PowerShell de Skype empresarial online, vea [using Windows PowerShell to Manage Skype for Business online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="7873c-118">For more information about using the Skype for Business Online PowerShell module, see [Using Windows PowerShell to manage Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7873c-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7873c-119">See Also</span></span>


[<span data-ttu-id="7873c-120">New-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="7873c-120">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
