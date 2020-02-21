---
title: 'Lync Server 2013: requisitos técnicos para la omisión de medios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for media bypass
ms:assetid: 6162a204-0e7c-460a-8eb2-e592c6590a8a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398435(v=OCS.15)
ms:contentKeyID: 48184321
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e81a90ff0fa7b33bb83e8abbb4ccb6819d6ac11
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194863"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="ea8f3-102">Requisitos técnicos para la omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ea8f3-102">Technical requirements for media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea8f3-103">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="ea8f3-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="ea8f3-104">Por cada llamada a la RTC, el servidor de mediación determina si los medios del punto de conexión de Lync de origen se pueden enviar directamente a un servidor de mediación del mismo nivel sin atravesar el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="ea8f3-104">For each call to the PSTN, the Mediation Server determines whether media from the Lync endpoint of origin can be sent directly to a Mediation Server peer without traversing the Mediation Server.</span></span> <span data-ttu-id="ea8f3-105">El componente del mismo nivel puede ser una puerta de enlace RTC, un sistema IP-PBX o un controlador SBC en un proveedor de servicios de telefonía por Internet (ITSP) asociado con el tronco entre el servidor de mediación hacia el que se ha enrutado la llamada.</span><span class="sxs-lookup"><span data-stu-id="ea8f3-105">The peer can be a PSTN gateway, IP-PBX, or Session Border Controller (SBC) at an Internet telephony service provider (ITSP) that is associated with the trunk between the Mediation Server where the call is routed.</span></span>

<span data-ttu-id="ea8f3-106">Puede emplearse el desvío de medios cuando se reúnen los siguientes requisitos:</span><span class="sxs-lookup"><span data-stu-id="ea8f3-106">Media bypass can be employed when the following requirements are met:</span></span>

  - <span data-ttu-id="ea8f3-107">Un elemento del mismo nivel del servidor de mediación debe admitir las capacidades necesarias para la omisión de medios, la más importante es la capacidad para controlar varias respuestas bifurcadas (conocidas como "cuadros de diálogo iniciales").</span><span class="sxs-lookup"><span data-stu-id="ea8f3-107">A Mediation Server peer must support the necessary capabilities for media bypass, the most important being the ability to handle multiple forked responses (known as “early dialogs”).</span></span> <span data-ttu-id="ea8f3-108">Póngase en contacto con el fabricante de su puerta de enlace, sistema PBX o ITSP para obtener el valor del número máximo de diálogos iniciales que la puerta de enlace, el sistema PBX o el SBC puede aceptar.</span><span class="sxs-lookup"><span data-stu-id="ea8f3-108">Contact the manufacturer of your gateway or PBX, or your ITSP, to obtain the value for the maximum number of early dialogs that the gateway, PBX, or SBC can accept.</span></span>

  - <span data-ttu-id="ea8f3-109">El servidor de mediación del mismo nivel debe aceptar el tráfico de medios directamente desde los puntos de conexión de Lync.</span><span class="sxs-lookup"><span data-stu-id="ea8f3-109">The Mediation Server peer must accept media traffic directly from Lync endpoints.</span></span> <span data-ttu-id="ea8f3-110">Muchas ITSPs permiten que SBC reciba el tráfico solo del servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="ea8f3-110">Many ITSPs allow their SBC to receive traffic only from the Mediation Server.</span></span> <span data-ttu-id="ea8f3-111">Póngase en contacto con el ITSP para determinar si el SBC acepta el tráfico de medios directamente desde los puntos de conexión de Lync.</span><span class="sxs-lookup"><span data-stu-id="ea8f3-111">Contact your ITSP to determine whether its SBC accepts media traffic directly from Lync endpoints.</span></span>

  - <span data-ttu-id="ea8f3-112">Los clientes de Lync y un servidor de mediación deben estar bien conectados, lo que significa que ya se encuentran en la misma región de red o en sitios de red que se conectan a la región a través de vínculos WAN que no tienen restricciones de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="ea8f3-112">Lync clients and a Mediation Server peer must be well connected, meaning that they are either located in the same network region or at network sites that connect to the region over WAN links that have no bandwidth constraints</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="ea8f3-113">Consulta también</span><span class="sxs-lookup"><span data-stu-id="ea8f3-113">See Also</span></span>


[<span data-ttu-id="ea8f3-114">Modos de omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ea8f3-114">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)  
[<span data-ttu-id="ea8f3-115">Omisión de medios y control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ea8f3-115">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

