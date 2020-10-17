---
title: 'Lync Server 2013: configuración de detección automática para implementaciones híbridas'
description: 'Lync Server 2013: configuración de detección automática para implementaciones híbridas.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Autodiscover for hybrid deployments
ms:assetid: ca605e62-181c-42ca-80a1-e37e610f8277
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945653(v=OCS.15)
ms:contentKeyID: 51541521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6797e3f6b77e3016f6cef87f2a930f5a7c1fce6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562496"
---
# <a name="configuring-autodiscover-in-lync-server-2013-for-hybrid-deployments"></a><span data-ttu-id="ce61b-103">Configuración de detección automática en Lync Server 2013 para implementaciones híbridas</span><span class="sxs-lookup"><span data-stu-id="ce61b-103">Configuring Autodiscover in Lync Server 2013 for hybrid deployments</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce61b-104">_**Última modificación del tema:** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="ce61b-104">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="ce61b-105">Las implementaciones híbridas son configuraciones que usan el servicio en la nube de Microsoft Lync Online y la implementación local.</span><span class="sxs-lookup"><span data-stu-id="ce61b-105">Hybrid Deployments are configurations that use both the Microsoft Lync Online cloud service and the on premises deployment.</span></span> <span data-ttu-id="ce61b-106">En este tipo de configuración, el servicio de detección automática puede determinar dónde está ubicado realmente el usuario.</span><span class="sxs-lookup"><span data-stu-id="ce61b-106">In this type of configuration, the Autodiscover service must be able to locate where the user is actually located.</span></span> <span data-ttu-id="ce61b-107">Es decir, detección automática ayuda a encontrar la cuenta de usuario y donde se encuentra el servidor que hospeda la cuenta del usuario, independientemente de si se encuentra en la implementación local o en la implementación de Lync Online.</span><span class="sxs-lookup"><span data-stu-id="ce61b-107">That is to say, Autodiscover aids in finding the user account and where the server that hosts the user’s account is, regardless if it is in the on premises deployment or in the Lync Online deployment.</span></span>

<span data-ttu-id="ce61b-108">Por ejemplo, si una cuenta de usuario está hospedada en un servidor de Lync Online, el intento de ubicar al usuario ocurrirá como sigue, en un proceso conocido como *detectabilidad*:</span><span class="sxs-lookup"><span data-stu-id="ce61b-108">For example, if a user’s account is hosted on a server in Lync Online, the attempt to locate the user will happen as follows, in a process known as *discoverability*:</span></span>

  - <span data-ttu-id="ce61b-109">El usuario inicia un intento de conexión en la implementación local, **contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="ce61b-109">User initiates a connection attempt to the on premises deployment, **contoso.com**.</span></span>

  - <span data-ttu-id="ce61b-110">Se envía el intento a lyncdiscover.contoso.com, el nombre de DNS asociado al servicio de detección automática.</span><span class="sxs-lookup"><span data-stu-id="ce61b-110">The attempt is sent to lyncdiscover.contoso.com, the DNS name associated with the Autodiscover service.</span></span>

  - <span data-ttu-id="ce61b-111">Detección automática hace referencia al grupo de registradores supuesto en la implementación local de contoso.com y recibe información sobre el servidor principal real del usuario hospedado en Lync Online.</span><span class="sxs-lookup"><span data-stu-id="ce61b-111">Autodiscover refers to the assumed registrar pool at the contoso.com on premises deployment and is given information on the user’s actual home server hosted in Lync Online.</span></span> <span data-ttu-id="ce61b-112">La detección automática envía al usuario una derivación al servicio de detección automática en línea de **lync.com**.</span><span class="sxs-lookup"><span data-stu-id="ce61b-112">Autodiscover then sends the user a referral to the **lync.com** online Autodiscover service.</span></span>

  - <span data-ttu-id="ce61b-113">El usuario inicia un intento de conexión al servicio de detección automática en línea de lync.com y puede localizar la cuenta de usuario y el servidor principal del usuario.</span><span class="sxs-lookup"><span data-stu-id="ce61b-113">The user initiates a connection attempt to the lync.com online Autodiscover service and is able to locate the user’s account and the user’s home server.</span></span>

<span data-ttu-id="ce61b-114">Para permitir que los clientes detecten la implementación en la que se encuentra el servidor principal del usuario, debe configurar el servicio de detección automática con un nuevo localizador de recursos uniforme (URL).</span><span class="sxs-lookup"><span data-stu-id="ce61b-114">To enable clients to discover the deployment where the user home server is located, you must configure the Autodiscover service with a new uniform resource locator (URL).</span></span> <span data-ttu-id="ce61b-115">Para configurar el servicio de detección automática, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ce61b-115">Do the following to configure the Autodiscover service.</span></span>

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a><span data-ttu-id="ce61b-116">Configuración de detección automática para implementaciones híbridas</span><span class="sxs-lookup"><span data-stu-id="ce61b-116">Configuring Autodiscover for Hybrid Deployments</span></span>

1.  <span data-ttu-id="ce61b-117">En el tema, [requisitos del servicio Detección automática para Lync Server 2013](lync-server-2013-autodiscover-service-requirements.md), use Get-CsHostingProvider para recuperar el valor del atributo ProxyFQDN.</span><span class="sxs-lookup"><span data-stu-id="ce61b-117">In the topic, [Autodiscover service requirements for Lync Server 2013](lync-server-2013-autodiscover-service-requirements.md), you use Get-CsHostingProvider to retrieve the value of the attribute ProxyFQDN.</span></span>

2.  <span data-ttu-id="ce61b-118">Desde el shell de administración de Lync Server, escriba</span><span class="sxs-lookup"><span data-stu-id="ce61b-118">From the Lync Server Management Shell, type</span></span>
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodisccoverservice.svc/root
    
    <span data-ttu-id="ce61b-119">Donde \[ \] la identidad se reemplaza con el nombre de dominio del espacio de direcciones SIP compartido.</span><span class="sxs-lookup"><span data-stu-id="ce61b-119">Where \[identity\] is replaced with the domain name of the shared SIP address space.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ce61b-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ce61b-120">See Also</span></span>


[<span data-ttu-id="ce61b-121">Get-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="ce61b-121">Get-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostingProvider)  
[<span data-ttu-id="ce61b-122">Set-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="ce61b-122">Set-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

