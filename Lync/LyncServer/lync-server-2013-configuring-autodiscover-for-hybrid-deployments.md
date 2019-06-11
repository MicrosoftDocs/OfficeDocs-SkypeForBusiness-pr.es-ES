---
title: 'Lync Server 2013: configuración de detección automática para implementaciones híbridas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Autodiscover for hybrid deployments
ms:assetid: ca605e62-181c-42ca-80a1-e37e610f8277
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945653(v=OCS.15)
ms:contentKeyID: 51541521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc2c28d42569d2f52b55dd04a90f5a788969c3ab
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842277"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-autodiscover-in-lync-server-2013-for-hybrid-deployments"></a><span data-ttu-id="d49e0-102">Configuración de la detección automática en Lync Server 2013 para implementaciones híbridas</span><span class="sxs-lookup"><span data-stu-id="d49e0-102">Configuring Autodiscover in Lync Server 2013 for hybrid deployments</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d49e0-103">_**Última modificación del tema:** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="d49e0-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="d49e0-104">Las implementaciones híbridas son configuraciones que usan el servicio en la nube de Microsoft Lync Online y la implementación local.</span><span class="sxs-lookup"><span data-stu-id="d49e0-104">Hybrid Deployments are configurations that use both the Microsoft Lync Online cloud service and the on premises deployment.</span></span> <span data-ttu-id="d49e0-105">En este tipo de configuración, el servicio Detección automática debe poder ubicar dónde se encuentra realmente el usuario.</span><span class="sxs-lookup"><span data-stu-id="d49e0-105">In this type of configuration, the Autodiscover service must be able to locate where the user is actually located.</span></span> <span data-ttu-id="d49e0-106">Es decir, la detección automática ayuda a buscar la cuenta de usuario y dónde se encuentra el servidor que hospeda la cuenta del usuario, independientemente de si se encuentra en la implementación local o en la implementación de Lync Online.</span><span class="sxs-lookup"><span data-stu-id="d49e0-106">That is to say, Autodiscover aids in finding the user account and where the server that hosts the user’s account is, regardless if it is in the on premises deployment or in the Lync Online deployment.</span></span>

<span data-ttu-id="d49e0-107">Por ejemplo, si la cuenta de un usuario se hospeda en un servidor de Lync Online, el intento de ubicar al usuario tendrá el siguiente aspecto, en un proceso conocido como *descubrimiento*:</span><span class="sxs-lookup"><span data-stu-id="d49e0-107">For example, if a user’s account is hosted on a server in Lync Online, the attempt to locate the user will happen as follows, in a process known as *discoverability*:</span></span>

  - <span data-ttu-id="d49e0-108">El usuario inicia un intento de conexión a la implementación local, **contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="d49e0-108">User initiates a connection attempt to the on premises deployment, **contoso.com**.</span></span>

  - <span data-ttu-id="d49e0-109">El intento se envía a lyncdiscover.contoso.com, el nombre DNS asociado al servicio Detección automática.</span><span class="sxs-lookup"><span data-stu-id="d49e0-109">The attempt is sent to lyncdiscover.contoso.com, the DNS name associated with the Autodiscover service.</span></span>

  - <span data-ttu-id="d49e0-110">Detección automática hace referencia al grupo de registradores supuesto en la implementación local de contoso.com y se le proporciona información sobre el servidor principal real del usuario hospedado en Lync Online.</span><span class="sxs-lookup"><span data-stu-id="d49e0-110">Autodiscover refers to the assumed registrar pool at the contoso.com on premises deployment and is given information on the user’s actual home server hosted in Lync Online.</span></span> <span data-ttu-id="d49e0-111">La detección automática después envía al usuario una referencia al servicio de detección automática de **Lync.com** online.</span><span class="sxs-lookup"><span data-stu-id="d49e0-111">Autodiscover then sends the user a referral to the **lync.com** online Autodiscover service.</span></span>

  - <span data-ttu-id="d49e0-112">El usuario inicia un intento de conexión al servicio de detección automática de lync.com online y puede ubicar la cuenta del usuario y el servidor principal del usuario.</span><span class="sxs-lookup"><span data-stu-id="d49e0-112">The user initiates a connection attempt to the lync.com online Autodiscover service and is able to locate the user’s account and the user’s home server.</span></span>

<span data-ttu-id="d49e0-113">Para permitir que los clientes descubran la implementación en la que se encuentra el servidor principal del usuario, debe configurar el servicio Detección automática con un localizador de recursos uniforme (URL) nuevo.</span><span class="sxs-lookup"><span data-stu-id="d49e0-113">To enable clients to discover the deployment where the user home server is located, you must configure the Autodiscover service with a new uniform resource locator (URL).</span></span> <span data-ttu-id="d49e0-114">Siga este procedimiento para configurar el servicio Detección automática.</span><span class="sxs-lookup"><span data-stu-id="d49e0-114">Do the following to configure the Autodiscover service.</span></span>

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a><span data-ttu-id="d49e0-115">Configuración de detección automática para implementaciones híbridas</span><span class="sxs-lookup"><span data-stu-id="d49e0-115">Configuring Autodiscover for Hybrid Deployments</span></span>

1.  <span data-ttu-id="d49e0-116">En el tema [requisitos del servicio Autodiscover para Lync Server 2013](lync-server-2013-autodiscover-service-requirements.md), use Get-CsHostingProvider para recuperar el valor del atributo ProxyFQDN.</span><span class="sxs-lookup"><span data-stu-id="d49e0-116">In the topic, [Autodiscover service requirements for Lync Server 2013](lync-server-2013-autodiscover-service-requirements.md), you use Get-CsHostingProvider to retrieve the value of the attribute ProxyFQDN.</span></span>

2.  <span data-ttu-id="d49e0-117">Desde el shell de administración de Lync Server, escriba</span><span class="sxs-lookup"><span data-stu-id="d49e0-117">From the Lync Server Management Shell, type</span></span>
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodisccoverservice.svc/root
    
    <span data-ttu-id="d49e0-118">Donde \[identidad\] se reemplaza con el nombre de dominio del espacio de direcciones SIP compartido.</span><span class="sxs-lookup"><span data-stu-id="d49e0-118">Where \[identity\] is replaced with the domain name of the shared SIP address space.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d49e0-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="d49e0-119">See Also</span></span>


[<span data-ttu-id="d49e0-120">Get-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="d49e0-120">Get-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostingProvider)  
[<span data-ttu-id="d49e0-121">Set-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="d49e0-121">Set-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

