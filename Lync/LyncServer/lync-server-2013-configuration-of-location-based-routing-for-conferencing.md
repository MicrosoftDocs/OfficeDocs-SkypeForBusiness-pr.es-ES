---
title: 'Lync Server 2013: configuración del enrutamiento de Location-Based para conferencias'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration of Location-Based Routing for conferencing
ms:assetid: d8c708cc-a1b1-48b1-808c-a64df15f7701
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362846(v=OCS.15)
ms:contentKeyID: 56335088
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd5ada5e4af1ed4ed43434ddf4d82abc25f4cd5e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507807"
---
# <a name="configuration-of-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="8bb5b-102">Configuración del enrutamiento de Location-Based para conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8bb5b-102">Configuration of Location-Based Routing for conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8bb5b-103">_**Última modificación del tema:** 2013-09-11_</span><span class="sxs-lookup"><span data-stu-id="8bb5b-103">_**Topic Last Modified:** 2013-09-11_</span></span>

<span data-ttu-id="8bb5b-104">La aplicación de conferencia de Location-Based enrutamiento depende de la configuración del enrutamiento de Lync Server 2013 Location-Based.</span><span class="sxs-lookup"><span data-stu-id="8bb5b-104">The Location-Based Routing Conferencing application relies on the configuration of Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="8bb5b-105">Las configuraciones principales son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="8bb5b-105">The main configurations are the following:</span></span>

  - <span data-ttu-id="8bb5b-106">La ubicación de los participantes que se unen a una reunión se determina en función de su sitio de red.</span><span class="sxs-lookup"><span data-stu-id="8bb5b-106">The location of participants joining a meeting is determined based on their network site.</span></span> <span data-ttu-id="8bb5b-107">Un sitio de red y sus subredes de red asociadas deben definirse en Lync Server para aplicar el enrutamiento de Location-Based.</span><span class="sxs-lookup"><span data-stu-id="8bb5b-107">A network site and its associated network subnets must be defined in Lync Server in order to enforce Location-Based Routing.</span></span>

  - <span data-ttu-id="8bb5b-108">Para aplicar Location-Based el enrutamiento de reuniones, los participantes de Lync deben estar habilitados para Location-Based enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="8bb5b-108">To enforce Location-Based Routing of meetings, Lync participants must be enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="8bb5b-109">Para aplicar Location-Based enrutamiento de extremos RTC que se unen a las reuniones, el tronco SIP que se usa para conectar los extremos de RTC debe configurarse para el enrutamiento de Location-Based.</span><span class="sxs-lookup"><span data-stu-id="8bb5b-109">To enforce Location-Based Routing of PSTN endpoints joining meetings, the SIP trunk used to connect the PSTN endpoints must be configured for Location-Based Routing.</span></span>

<span data-ttu-id="8bb5b-110">Para obtener más información sobre la implementación y la configuración del enrutamiento de Lync Server 2013 Location-Based, consulte Configuring [location-based Routing](lync-server-2013-configuring-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="8bb5b-110">For additional information on deploying and configuring Lync Server 2013 Location-Based Routing, please refer Configuring [Location-Based Routing](lync-server-2013-configuring-location-based-routing.md).</span></span>

<div>

## <a name="enabling-the-location-based-routing-conferencing-application"></a><span data-ttu-id="8bb5b-111">Habilitación de la aplicación de conferencia de Location-Based enrutamiento</span><span class="sxs-lookup"><span data-stu-id="8bb5b-111">Enabling the Location-Based Routing Conferencing Application</span></span>

<span data-ttu-id="8bb5b-112">La aplicación de conferencia de enrutamiento de Location-Based está deshabilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="8bb5b-112">The Location-Based Routing Conferencing application is disabled by default.</span></span> <span data-ttu-id="8bb5b-113">Antes de habilitar esta aplicación, debe determinar la prioridad correcta que se asignará a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8bb5b-113">Before enabling this application, you need to determine the right priority to assign for the application.</span></span> <span data-ttu-id="8bb5b-114">Para determinar esta prioridad, ejecute el siguiente cmdlet en el shell de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="8bb5b-114">To determine this priority, run the following cmdlet in Lync Server Management Shell:</span></span>

```powershell
Get-CsServerApplication -Identity Service:Registrar:<Pool FQDN>
```

<span data-ttu-id="8bb5b-115">En este cmdlet, \<Pool FQDN\> es el grupo de servidores en el que se va a habilitar la aplicación de conferencia de enrutamiento de Location-Based.</span><span class="sxs-lookup"><span data-stu-id="8bb5b-115">In this cmdlet, \<Pool FQDN\> is the pool in which the Location-Based Routing Conferencing application is to be enabled.</span></span>

<span data-ttu-id="8bb5b-116">Este cmdlet devolverá la lista de las aplicaciones hospedadas en Lync Server y el valor de prioridad de cada una de ellas.</span><span class="sxs-lookup"><span data-stu-id="8bb5b-116">This cmdlet will return the list of the applications hosted by Lync Server and the priority value for each of them.</span></span> <span data-ttu-id="8bb5b-117">La aplicación de conferencia de Location-Based enrutamiento debe tener asignado un valor de prioridad mayor que el de la aplicación "UdcAgent" y menor que el de las aplicaciones "DefaultRouting", "ExumRouting" y "OutboundRouting".</span><span class="sxs-lookup"><span data-stu-id="8bb5b-117">The Location-Based Routing Conferencing application needs to be assigned a priority value larger than the “UdcAgent” application and smaller than the “DefaultRouting”, “ExumRouting” and “OutboundRouting” applications.</span></span> <span data-ttu-id="8bb5b-118">Le recomendamos que asigne a la aplicación de conferencia de enrutamiento de Location-Based un valor de prioridad que sea un punto superior al valor de prioridad de la aplicación "UdcAgent".</span><span class="sxs-lookup"><span data-stu-id="8bb5b-118">We recommend that you assign the Location-Based Routing Conferencing application a priority value that is one point higher than the priority value of the “UdcAgent” application.</span></span>

<span data-ttu-id="8bb5b-119">Por ejemplo, si la aplicación "UdcAgent" tiene un valor de prioridad de "2", la aplicación "DefaultRouting" tiene un valor de prioridad de "8", la aplicación "ExumRouting" tiene un valor de prioridad de "9" y la aplicación "OutboundRouting" tiene un valor de prioridad de "10", debe asignar a la aplicación de conferencia de Location-Based enrutamiento un valor de prioridad de</span><span class="sxs-lookup"><span data-stu-id="8bb5b-119">For example, if the “UdcAgent” application has a priority value of “2”, the “DefaultRouting” application has a priority value of “8”, the “ExumRouting” application has a priority value of “9” and the “OutboundRouting” application has a priority value of “10” then you should assign the Location-Based Routing Conferencing application a priority value of “3”.</span></span> <span data-ttu-id="8bb5b-120">Si lo hace, se colocará la prioridad de las aplicaciones en el siguiente orden: otras aplicaciones (prioridades: 0 a 1), "UdcAgent" (prioridad: 2), Location-Based aplicación de conferencia de enrutamiento (prioridad: 3), otras aplicaciones (prioridades: 4 a 8), "DefaultRouting" (prioridad: 9), "ExumRouting" (prioridad: 10) y "OutboundRouting" (prioridad: 11).</span><span class="sxs-lookup"><span data-stu-id="8bb5b-120">Doing so would place the priority of the applications in the following order: Other applications (Priorities: 0 to 1), “UdcAgent” (Priority: 2), Location-Based Routing Conferencing application (Priority: 3), other applications (Priorities: 4 to 8), “DefaultRouting” (Priority: 9), “ExumRouting” (Priority: 10) and “OutboundRouting” (Priority: 11).</span></span>

<span data-ttu-id="8bb5b-121">Una vez que haya encontrado el valor de prioridad correcto para la aplicación de conferencia de enrutamiento de Location-Based, escriba el siguiente cmdlet para cada Front-End servidor Standard Edition o grupo de servidores que aloje a los usuarios habilitados para Location-Based enrutamiento:</span><span class="sxs-lookup"><span data-stu-id="8bb5b-121">After you find the correct priority value for the Location-Based Routing Conferencing application, type the following cmdlet for each Front-End pool or Standard Edition Server that homes users enabled for Location-Based Routing:</span></span>

```powershell
New-CsServerApplication -Identity Service:Registrar:<Pool FQDN>/LBRouting -Priority <Application Priority> -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting
```

<span data-ttu-id="8bb5b-122">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8bb5b-122">For example:</span></span>

```powershell
New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting
```

<span data-ttu-id="8bb5b-123">Después de usar este cmdlet, reinicie todos los servidores front-end en el grupo o los servidores Standard Edition donde se haya habilitado la aplicación de conferencia de enrutamiento de Location-Based.</span><span class="sxs-lookup"><span data-stu-id="8bb5b-123">After using this cmdlet, restart all Front End servers in the pool or the Standard Edition Servers where the Location-Based Routing Conferencing application has been enabled.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8bb5b-124">Location-Based las fuerzas de enrutamiento a las conferencias o las transferencias de consulta no se aplicarán hasta que se reinicien todos los servidores front-end de los grupos de servidores correspondientes o los servidores Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="8bb5b-124">Location-Based Routing enforcements to conferences or consultative transfers won’t be enforced until all the Front End Servers in the applicable pools or the Standard Edition Servers are restarted.</span></span>



</div>

<span data-ttu-id="8bb5b-125">Una vez que la aplicación de Location-Based de conferencia de enrutamiento se haya habilitado correctamente y se hayan reiniciado todos los servidores de Lync aplicables, se supervisarán todas las conferencias organizadas por usuarios de Lync habilitados para Location-Based enrutamiento para evitar el desvío de llamadas RTC.</span><span class="sxs-lookup"><span data-stu-id="8bb5b-125">Once the Location-Based Routing Conferencing application has been successfully enabled and all applicable Lync servers have been restarted, all conferences organized by Lync users enabled for Location-Based Routing will be monitored to prevent PSTN toll bypass</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

