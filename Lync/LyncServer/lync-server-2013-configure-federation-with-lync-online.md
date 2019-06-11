---
title: 'Lync Server 2013: configurar la Federación con Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure federation with Lync Online
ms:assetid: a10bd1d5-c003-46db-9f57-7d55d3fa08da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205126(v=OCS.15)
ms:contentKeyID: 48184946
ms.date: 08/15/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d690b21614ec416d82834761772cee05ee16f26e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842369"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-of-lync-server-2013-with-lync-online"></a><span data-ttu-id="86f04-102">Configurar la Federación de Lync Server 2013 con Lync Online</span><span class="sxs-lookup"><span data-stu-id="86f04-102">Configure federation of Lync Server 2013 with Lync Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86f04-103">_**Última modificación del tema:** 2016-08-15_</span><span class="sxs-lookup"><span data-stu-id="86f04-103">_**Topic Last Modified:** 2016-08-15_</span></span>

<span data-ttu-id="86f04-104">Siga los pasos de esta sección para configurar la interoperabilidad entre su implementación local y Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="86f04-104">Follow the steps in this section to configure interoperability between your on-premises deployment and Skype for Business Online.</span></span>

<span id="a"></span>

<div>

## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a><span data-ttu-id="86f04-105">Configurar el servicio perimetral local para la Federación con Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="86f04-105">Configure Your On-Premises Edge Service for Federation with Skype for Business Online</span></span>

<span data-ttu-id="86f04-106">La Federación permite que los usuarios de su implementación local se comuniquen con los usuarios de Office 365 de su organización.</span><span class="sxs-lookup"><span data-stu-id="86f04-106">Federation allows users in your on-premises deployment to communicate with Office 365 users in your organization.</span></span> <span data-ttu-id="86f04-107">Para configurar la Federación, ejecute los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="86f04-107">To configure federation, run the following cmdlets:</span></span>

   ```
    Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $True
   ```

   ```
    New-CSHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
   ```

</div>

<span id="b"></span>

<div>

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a><span data-ttu-id="86f04-108">Configurar el inquilino de Skype empresarial online para un espacio de direcciones SIP compartido</span><span class="sxs-lookup"><span data-stu-id="86f04-108">Configure Your Skype for Business Online Tenant for a Shared SIP Address Space</span></span>

<span data-ttu-id="86f04-109">Una dirección de protocolo de inicio de sesión (SIP) es un identificador único para cada usuario de una red, parecido a un número de teléfono o a una dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="86f04-109">A Session Initiation Protocol (SIP) address is a unique identifier for each user on a network, similar to a phone number or an email address.</span></span> <span data-ttu-id="86f04-110">Antes de intentar mover usuarios de Lync de local a Skype empresarial online, tendrá que configurar el inquilino de Office 365 para compartir el espacio de direcciones del Protocolo de inicio de sesión (SIP) compartido con la implementación local.</span><span class="sxs-lookup"><span data-stu-id="86f04-110">Before you try to move Lync users from on-premises to Skype for Business Online, you’ll need to configure your Office 365 tenant to share the Shared Session Initiation Protocol (SIP) address space with your on-premises deployment.</span></span> <span data-ttu-id="86f04-111">Si no lo configura, es probable que se le presente el siguiente mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="86f04-111">If this is not configured, you may see the following error message:</span></span>

<span data-ttu-id="86f04-112">Move-CsUser: HostedMigration fault: Error=(510), Description=(El inquilino de este usuario no está habilitado para el espacio de dirección SIP compartido).</span><span class="sxs-lookup"><span data-stu-id="86f04-112">Move-CsUser : HostedMigration fault: Error=(510), Description=(This user’s tenant is not enabled for shared sip address space.)</span></span>

<span data-ttu-id="86f04-113">Para configurar un espacio de direcciones SIP compartido, establezca una sesión PowerShell remota con Skype empresarial online y, a continuación, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="86f04-113">To configure a shared SIP address space, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>

    Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true

<span data-ttu-id="86f04-114">Para establecer una sesión PowerShell remota con Skype empresarial online, primero tiene que instalar el módulo Skype empresarial online para Windows PowerShell, que puede obtener aquí: [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911).</span><span class="sxs-lookup"><span data-stu-id="86f04-114">To establish a remote PowerShell session with Skype for Business Online, you first need to install the Skype for Business Online module for Windows PowerShell, which you can get here: [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911).</span></span>

<span data-ttu-id="86f04-115">Después de instalar el módulo, puede establecer una sesión remota con los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="86f04-115">After you install the module, you can establish a remote session with the following cmdlets:</span></span>

   ```
    Import-Module LyncOnlineConnector
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

<span data-ttu-id="86f04-116">Para obtener más información sobre cómo establecer una sesión remota de PowerShell con Skype empresarial online, consulte [conectarse a Skype empresarial online mediante Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="86f04-116">For more information about how to establish a remote PowerShell session with Skype for Business Online, see [Connecting to Skype for Business Online by using Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

<span data-ttu-id="86f04-117">Para obtener más información sobre el uso del módulo de PowerShell Skype empresarial online, consulte [usar Windows PowerShell para administrar Skype empresarial online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="86f04-117">For more information about using the Skype for Business Online PowerShell module, see [Using Windows PowerShell to manage Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="86f04-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="86f04-118">See Also</span></span>


[<span data-ttu-id="86f04-119">Nuevo: CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="86f04-119">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

