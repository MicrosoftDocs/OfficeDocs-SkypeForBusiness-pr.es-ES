---
title: 'Lync Server 2013: Procedimientos recomendados para el servicio de control de admisión de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for call admission control
ms:assetid: 97173cca-8175-4ae2-a247-eb7ef809da93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398770(v=OCS.15)
ms:contentKeyID: 48184913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d8f75c546b2307de8f55504c2c6ebaab5c48f7c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741680"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="25e50-102">Procedimientos recomendados para el servicio de control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25e50-102">Best practices for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25e50-103">_**Última modificación del tema:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="25e50-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="25e50-104">Para mejorar el rendimiento y facilitar la implementación, sigue los procedimientos recomendados descritos a continuación a la hora de implementar el servicio de control de admisión de llamadas:</span><span class="sxs-lookup"><span data-stu-id="25e50-104">To enhance performance and facilitate deployment, apply the following best practices when you deploy call admission control:</span></span>

  - <span data-ttu-id="25e50-105">Comprueba que las redes WAN estén correctamente aprovisionadas para el tráfico de medios actual y previsto.</span><span class="sxs-lookup"><span data-stu-id="25e50-105">Ensure that WANs are adequately provisioned for current and anticipated media traffic.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="25e50-p101">Recomendamos tener en cuenta un búfer además de los límites de ancho de banda. Existen escenarios, como condiciones de carrera, que afectan al ancho de banda total usado y pueden dar lugar a situaciones en que se supera el límite de ancho de banda. Por ejemplo, si se intentan iniciar dos llamadas cuando el tráfico de medios está alcanzando un límite de ancho de banda, es posible que una de ellas sea denegada porque la otra intentó iniciarse primero.</span><span class="sxs-lookup"><span data-stu-id="25e50-p101">We recommend that you factor in a buffer to your bandwidth limits. There are scenarios such as race conditions that affect the total bandwidth used and can result in situations where the bandwidth limit is exceeded. For example, if two calls try to start while media traffic is approaching a bandwidth limit, one of them may be denied because the other managed to start first.</span></span>

    
    </div>

  - <span data-ttu-id="25e50-109">Supervisa el uso de red y los registros de detalles de llamadas para que puedas elegir una configuración óptima de CAC y actualizarla conforme el uso de la red va cambiando.</span><span class="sxs-lookup"><span data-stu-id="25e50-109">Monitor network usage and call detail records so that you can choose optimal CAC settings and update CAC settings as network usage changes.</span></span>

  - <span data-ttu-id="25e50-110">Usa directivas de ancho de banda de CAC para complementar la configuración de QoS.</span><span class="sxs-lookup"><span data-stu-id="25e50-110">Use CAC bandwidth policies to complement QoS settings.</span></span>

  - <span data-ttu-id="25e50-111">Si deseas volver a redirigir llamadas bloqueadas a la RTC, comprueba la capacidad y las funciones de la RTC.</span><span class="sxs-lookup"><span data-stu-id="25e50-111">If you want to re-route blocked calls onto the PSTN, verify PSTN functionality and capacity.</span></span> <span data-ttu-id="25e50-112">Para obtener más información, consulte [planear el enrutamiento de voz saliente en Lync Server 2013](lync-server-2013-planning-outbound-voice-routing.md).</span><span class="sxs-lookup"><span data-stu-id="25e50-112">For details, see [Planning outbound voice routing in Lync Server 2013](lync-server-2013-planning-outbound-voice-routing.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="25e50-113">La capacidad hace referencia a la cantidad de puertos que necesitas abrir para admitir un nuevo posible enrutamiento de la RTC.</span><span class="sxs-lookup"><span data-stu-id="25e50-113">Capacity refers to the number of ports you need to open to support potential PSTN re-routing.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

