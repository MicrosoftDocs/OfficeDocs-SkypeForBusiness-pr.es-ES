---
title: Configurar la detección automática para movilidad con implementaciones híbridas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Autodiscover for mobility with hybrid deployments
ms:assetid: f838af79-d8b4-4122-b81c-7889573d143e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215885(v=OCS.15)
ms:contentKeyID: 48706012
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1865cab188bace472996db6207de62ce8498976
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842276"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-autodiscover-in-lync-server-2013-for-mobility-with-hybrid-deployments"></a><span data-ttu-id="dec63-102">Configurar la detección automática para movilidad con implementaciones híbridas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dec63-102">Configuring Autodiscover in Lync Server 2013 for mobility with hybrid deployments</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dec63-103">_**Última modificación del tema:** 2014-06-18_</span><span class="sxs-lookup"><span data-stu-id="dec63-103">_**Topic Last Modified:** 2014-06-18_</span></span>

<span data-ttu-id="dec63-104">Las implementaciones híbridas son configuraciones que usan el servicio en la nube de Microsoft Lync Online y la implementación local.</span><span class="sxs-lookup"><span data-stu-id="dec63-104">Hybrid Deployments are configurations that use both the Microsoft Lync Online cloud service and the on premises deployment.</span></span> <span data-ttu-id="dec63-105">En este tipo de configuración, el servicio Detección automática debe poder ubicar dónde se encuentra realmente el usuario.</span><span class="sxs-lookup"><span data-stu-id="dec63-105">In this type of configuration, the Autodiscover service must be able to locate where the user is actually located.</span></span> <span data-ttu-id="dec63-106">Es decir, la detección automática ayuda a buscar la cuenta de usuario y dónde se encuentra el servidor que hospeda la cuenta del usuario, independientemente de si se encuentra en la implementación local o en la implementación de Lync Online.</span><span class="sxs-lookup"><span data-stu-id="dec63-106">That is to say, Autodiscover aids in finding the user account and where the server that hosts the user’s account is, regardless if it is in the on premises deployment or in the Lync Online deployment.</span></span>

<span data-ttu-id="dec63-107">Por ejemplo, si la cuenta de un usuario se hospeda en un servidor de Lync Online, el intento de ubicar al usuario tendrá el siguiente aspecto, en un proceso conocido como *descubrimiento*:</span><span class="sxs-lookup"><span data-stu-id="dec63-107">For example, if a user’s account is hosted on a server in Lync Online, the attempt to locate the user will happen as follows, in a process known as *discoverability*:</span></span>

  - <span data-ttu-id="dec63-108">El usuario inicia un intento de conexión a la implementación local, **contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="dec63-108">User initiates a connection attempt to the on premises deployment, **contoso.com**.</span></span>

  - <span data-ttu-id="dec63-109">El intento se envía a lyncdiscover.contoso.com, el nombre DNS asociado al servicio Detección automática.</span><span class="sxs-lookup"><span data-stu-id="dec63-109">The attempt is sent to lyncdiscover.contoso.com, the DNS name associated with the Autodiscover service.</span></span>

  - <span data-ttu-id="dec63-110">Detección automática hace referencia al grupo de registradores supuesto en la implementación local de contoso.com y se le proporciona información sobre el servidor principal real del usuario hospedado en Lync Online.</span><span class="sxs-lookup"><span data-stu-id="dec63-110">Autodiscover refers to the assumed registrar pool at the contoso.com on premises deployment and is given information on the user’s actual home server hosted in Lync Online.</span></span> <span data-ttu-id="dec63-111">La detección automática después envía al usuario una referencia al servicio de detección automática de **Lync.com** online.</span><span class="sxs-lookup"><span data-stu-id="dec63-111">Autodiscover then sends the user a referral to the **lync.com** online Autodiscover service.</span></span>

  - <span data-ttu-id="dec63-112">El usuario inicia un intento de conexión al servicio de detección automática de lync.com online y puede ubicar la cuenta del usuario y el servidor principal del usuario.</span><span class="sxs-lookup"><span data-stu-id="dec63-112">The user initiates a connection attempt to the lync.com online Autodiscover service and is able to locate the user’s account and the user’s home server.</span></span>

<span data-ttu-id="dec63-113">Para que los clientes móviles puedan descubrir la implementación donde se encuentra el servidor principal del usuario, debe configurar el servicio Detección automática con un nuevo localizador de recursos uniforme (URL).</span><span class="sxs-lookup"><span data-stu-id="dec63-113">To enable mobile clients to discover the deployment where the user home server is located, you must configure the Autodiscover service with a new uniform resource locator (URL).</span></span> <span data-ttu-id="dec63-114">Siga este procedimiento para configurar el servicio Detección automática.</span><span class="sxs-lookup"><span data-stu-id="dec63-114">Do the following to configure the Autodiscover service.</span></span>

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a><span data-ttu-id="dec63-115">Configuración de detección automática para implementaciones híbridas</span><span class="sxs-lookup"><span data-stu-id="dec63-115">Configuring Autodiscover for Hybrid Deployments</span></span>

1.  <span data-ttu-id="dec63-116">Use Get-CsHostingProvider para recuperar el valor del atributo ProxyFQDN.</span><span class="sxs-lookup"><span data-stu-id="dec63-116">You use Get-CsHostingProvider to retrieve the value of the attribute ProxyFQDN.</span></span>

2.  <span data-ttu-id="dec63-117">Desde el shell de administración de Lync Server, escriba</span><span class="sxs-lookup"><span data-stu-id="dec63-117">From the Lync Server Management Shell, type</span></span>
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
    
    <span data-ttu-id="dec63-118">Donde \[identidad\] se reemplaza con el nombre de dominio del espacio de direcciones SIP compartido.</span><span class="sxs-lookup"><span data-stu-id="dec63-118">Where \[identity\] is replaced with the domain name of the shared SIP address space.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dec63-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="dec63-119">See Also</span></span>


<span data-ttu-id="dec63-120">[Get-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg413078(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="dec63-120">[Get-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg413078(v=OCS.15))</span></span>  
<span data-ttu-id="dec63-121">[Set-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398532(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="dec63-121">[Set-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398532(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

