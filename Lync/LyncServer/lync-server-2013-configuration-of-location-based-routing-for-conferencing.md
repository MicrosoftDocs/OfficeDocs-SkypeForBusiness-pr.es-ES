---
title: 'Lync Server 2013: configuración del enrutamiento basado en ubicación para conferencias'
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
ms.openlocfilehash: d9ea90f30dcd9ec9fdde2e6f4db25e7d27ad12cd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756374"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuration-of-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="f3f09-102">Configuración del enrutamiento basado en ubicación para conferencias de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3f09-102">Configuration of Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3f09-103">_**Última modificación del tema:** 2013-09-11_</span><span class="sxs-lookup"><span data-stu-id="f3f09-103">_**Topic Last Modified:** 2013-09-11_</span></span>

<span data-ttu-id="f3f09-104">La aplicación de conferencia de enrutamiento basada en la ubicación se basa en la configuración del enrutamiento basado en la ubicación 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f3f09-104">The Location-Based Routing Conferencing application relies on the configuration of Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="f3f09-105">Las siguientes son las opciones de configuración principales:</span><span class="sxs-lookup"><span data-stu-id="f3f09-105">The main configurations are the following:</span></span>

  - <span data-ttu-id="f3f09-106">La ubicación de los participantes que se unen a una reunión se determina a partir de su sitio de red.</span><span class="sxs-lookup"><span data-stu-id="f3f09-106">The location of participants joining a meeting is determined based on their network site.</span></span> <span data-ttu-id="f3f09-107">Para aplicar el enrutamiento basado en la ubicación, se debe definir un sitio de red y sus subredes de red asociadas.</span><span class="sxs-lookup"><span data-stu-id="f3f09-107">A network site and its associated network subnets must be defined in Lync Server in order to enforce Location-Based Routing.</span></span>

  - <span data-ttu-id="f3f09-108">Para aplicar el enrutamiento basado en la ubicación de las reuniones, los participantes de Lync deben estar habilitados para el enrutamiento basado en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="f3f09-108">To enforce Location-Based Routing of meetings, Lync participants must be enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="f3f09-109">Para aplicar el enrutamiento basado en la ubicación de los puntos de conexión RTC que se unen a las reuniones, el troncal SIP usado para conectar los puntos de conexión RTC debe estar configurado para el enrutamiento basado en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="f3f09-109">To enforce Location-Based Routing of PSTN endpoints joining meetings, the SIP trunk used to connect the PSTN endpoints must be configured for Location-Based Routing.</span></span>

<span data-ttu-id="f3f09-110">Para obtener más información sobre cómo implementar y configurar el enrutamiento basado en la ubicación 2013 de Lync Server, consulte Configuración del [enrutamiento basado en la ubicación](lync-server-2013-configuring-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="f3f09-110">For additional information on deploying and configuring Lync Server 2013 Location-Based Routing, please refer Configuring [Location-Based Routing](lync-server-2013-configuring-location-based-routing.md).</span></span>

<div>

## <a name="enabling-the-location-based-routing-conferencing-application"></a><span data-ttu-id="f3f09-111">Habilitar la aplicación de conferencia de enrutamiento basada en la ubicación</span><span class="sxs-lookup"><span data-stu-id="f3f09-111">Enabling the Location-Based Routing Conferencing Application</span></span>

<span data-ttu-id="f3f09-112">La aplicación de conferencia de enrutamiento basada en la ubicación está deshabilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="f3f09-112">The Location-Based Routing Conferencing application is disabled by default.</span></span> <span data-ttu-id="f3f09-113">Antes de habilitar esta aplicación, tienes que determinar la prioridad adecuada para asignar a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f3f09-113">Before enabling this application, you need to determine the right priority to assign for the application.</span></span> <span data-ttu-id="f3f09-114">Para determinar esta prioridad, ejecute el siguiente cmdlet en el shell de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="f3f09-114">To determine this priority, run the following cmdlet in Lync Server Management Shell:</span></span>

<span data-ttu-id="f3f09-115">Get-CsServerApplication-Identity Service: registrar:\<FQDN del grupo de servidores\></span><span class="sxs-lookup"><span data-stu-id="f3f09-115">Get-CsServerApplication -Identity Service:Registrar:\<Pool FQDN\></span></span>

<span data-ttu-id="f3f09-116">En este cmdlet, \<FQDN\> del grupo es el grupo en el que se va a habilitar la aplicación de conferencia de enrutamiento basado en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="f3f09-116">In this cmdlet, \<Pool FQDN\> is the pool in which the Location-Based Routing Conferencing application is to be enabled.</span></span>

<span data-ttu-id="f3f09-117">Este cmdlet devolverá la lista de las aplicaciones hospedadas por Lync Server y el valor de prioridad de cada una de ellas.</span><span class="sxs-lookup"><span data-stu-id="f3f09-117">This cmdlet will return the list of the applications hosted by Lync Server and the priority value for each of them.</span></span> <span data-ttu-id="f3f09-118">La aplicación de conferencia de enrutamiento basada en la ubicación debe tener asignado un valor de prioridad mayor que el de la aplicación "UdcAgent" y menor que las aplicaciones "DefaultRouting", "ExumRouting" y "OutboundRouting".</span><span class="sxs-lookup"><span data-stu-id="f3f09-118">The Location-Based Routing Conferencing application needs to be assigned a priority value larger than the “UdcAgent” application and smaller than the “DefaultRouting”, “ExumRouting” and “OutboundRouting” applications.</span></span> <span data-ttu-id="f3f09-119">Le recomendamos que asigne la aplicación de conferencia de enrutamiento basada en la ubicación un valor de prioridad que sea un punto superior al valor de prioridad de la aplicación "UdcAgent".</span><span class="sxs-lookup"><span data-stu-id="f3f09-119">We recommend that you assign the Location-Based Routing Conferencing application a priority value that is one point higher than the priority value of the “UdcAgent” application.</span></span>

<span data-ttu-id="f3f09-120">Por ejemplo, si la aplicación "UdcAgent" tiene un valor de prioridad de "2", la aplicación "DefaultRouting" tiene un valor de prioridad de "8", la aplicación "ExumRouting" tiene un valor de prioridad de "9" y la aplicación "OutboundRouting" tiene un valor de prioridad de "10" y, a continuación, debe asignar a la aplicación de conferencia de enrutamiento basada en la ubicación un valor de prioridad de "3".</span><span class="sxs-lookup"><span data-stu-id="f3f09-120">For example, if the “UdcAgent” application has a priority value of “2”, the “DefaultRouting” application has a priority value of “8”, the “ExumRouting” application has a priority value of “9” and the “OutboundRouting” application has a priority value of “10” then you should assign the Location-Based Routing Conferencing application a priority value of “3”.</span></span> <span data-ttu-id="f3f09-121">Al hacerlo, la prioridad de las aplicaciones quedará ordenada así: otras aplicaciones (prioridades: de 0 a 1), “UdcAgent” (prioridad: 2), aplicación de conferencias con enrutamiento basado en ubicación (prioridad: 3), otras aplicaciones (prioridades: de 4 a 8), “DefaultRouting” (prioridad: 9), “ExumRouting” (prioridad: 10) y “OutboundRouting” (prioridad: 11).</span><span class="sxs-lookup"><span data-stu-id="f3f09-121">Doing so would place the priority of the applications in the following order: Other applications (Priorities: 0 to 1), “UdcAgent” (Priority: 2), Location-Based Routing Conferencing application (Priority: 3), other applications (Priorities: 4 to 8), “DefaultRouting” (Priority: 9), “ExumRouting” (Priority: 10) and “OutboundRouting” (Priority: 11).</span></span>

<span data-ttu-id="f3f09-122">Después de encontrar el valor de prioridad correcto para la aplicación de conferencia de enrutamiento basado en la ubicación, escriba el siguiente cmdlet para cada grupo de servidores front-end o un servidor Standard Edition que aloje usuarios habilitado para el enrutamiento basado en la ubicación:</span><span class="sxs-lookup"><span data-stu-id="f3f09-122">After you find the correct priority value for the Location-Based Routing Conferencing application, type the following cmdlet for each Front-End pool or Standard Edition Server that homes users enabled for Location-Based Routing:</span></span>

<span data-ttu-id="f3f09-123">New-CsServerApplication-Identity Service: registrar:\<FQDN\>del grupo de/LBRouting \<-priority Application priority\> Enabled $true-URI $true-URIhttp://www.microsoft.com/LCS/LBRouting</span><span class="sxs-lookup"><span data-stu-id="f3f09-123">New-CsServerApplication -Identity Service:Registrar:\<Pool FQDN\>/LBRouting -Priority \<Application Priority\> -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting</span></span>

<span data-ttu-id="f3f09-124">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f3f09-124">For example:</span></span>

<span data-ttu-id="f3f09-125">New-CsServerApplication-Identity Service:Registrar:LS2013CU2LBRPool. contoso. com/LBRouting-Priority 3-habilitado $true-$true-URIhttp://www.microsoft.com/LCS/LBRouting</span><span class="sxs-lookup"><span data-stu-id="f3f09-125">New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting</span></span>

<span data-ttu-id="f3f09-126">Después de usar este cmdlet, reinicie todos los servidores front-end del grupo o los servidores Standard Edition donde se haya habilitado la aplicación de conferencia de enrutamiento basado en ubicación.</span><span class="sxs-lookup"><span data-stu-id="f3f09-126">After using this cmdlet, restart all Front End servers in the pool or the Standard Edition Servers where the Location-Based Routing Conferencing application has been enabled.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f3f09-127">Los cumplimientos de enrutamiento basado en la ubicación de las conferencias o las transferencias de asesoría no se aplicarán hasta que se reinicien todos los servidores front-end de los servidores Standard Edition o Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f3f09-127">Location-Based Routing enforcements to conferences or consultative transfers won’t be enforced until all the Front End Servers in the applicable pools or the Standard Edition Servers are restarted.</span></span>



</div>

<span data-ttu-id="f3f09-128">Una vez que la aplicación de conferencia de enrutamiento basada en ubicación se haya habilitado correctamente y se hayan reiniciado todos los servidores de Lync aplicables, se supervisarán todas las conferencias organizadas por usuarios de Lync habilitados para el enrutamiento basado en la ubicación para evitar el bypass de llamadas RTC.</span><span class="sxs-lookup"><span data-stu-id="f3f09-128">Once the Location-Based Routing Conferencing application has been successfully enabled and all applicable Lync servers have been restarted, all conferences organized by Lync users enabled for Location-Based Routing will be monitored to prevent PSTN toll bypass</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

