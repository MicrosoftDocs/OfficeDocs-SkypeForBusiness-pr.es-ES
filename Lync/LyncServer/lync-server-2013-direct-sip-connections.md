---
title: 'Lync Server 2013: conexiones SIP directas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Direct SIP connections
ms:assetid: 0a37737d-9628-4e36-b27b-c134fa5a3882
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398151(v=OCS.15)
ms:contentKeyID: 48183357
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05b2f00e9af5a88fe3e7c5cfe27cd88c2b33a102
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519937"
---
# <a name="direct-sip-connections-in-lync-server-2013"></a><span data-ttu-id="91e4e-102">Conexiones SIP directas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91e4e-102">Direct SIP connections in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91e4e-103">_**Última modificación del tema:** 2012-08-13_</span><span class="sxs-lookup"><span data-stu-id="91e4e-103">_**Topic Last Modified:** 2012-08-13_</span></span>

<span data-ttu-id="91e4e-104">Puede usar *las conexiones SIP directas* para conectar Lync Server a cualquiera de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="91e4e-104">You can use *direct SIP connections* to connect Lync Server to either of the following:</span></span>

  - <span data-ttu-id="91e4e-105">Un IP-PBX (para obtener más información, consulte [Opciones de implementación SIP directa en Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md)).</span><span class="sxs-lookup"><span data-stu-id="91e4e-105">An IP-PBX (for details, see [Direct SIP deployment options in Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md)).</span></span>

  - <span data-ttu-id="91e4e-106">Una puerta de enlace RTC (para obtener más información, consulte [Opciones de implementación de la puerta de enlace RTC en Lync Server 2013](lync-server-2013-pstn-gateway-deployment-options.md)).</span><span class="sxs-lookup"><span data-stu-id="91e4e-106">A PSTN gateway (for details, see [PSTN gateway deployment options in Lync Server 2013](lync-server-2013-pstn-gateway-deployment-options.md)).</span></span>

<span data-ttu-id="91e4e-107">Para implementar una conexión SIP directa, deberá seguir básicamente los mismos pasos de implementación que seguiría para implementar un tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="91e4e-107">To implement a direct SIP connection, you follow essentially the same deployment steps as you would to implement a SIP trunk.</span></span> <span data-ttu-id="91e4e-108">En ambos casos, la conexión se implementa mediante la interfaz externa de un servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="91e4e-108">In both cases, you implement the connection by using the external interface of a Mediation Server.</span></span> <span data-ttu-id="91e4e-109">La única diferencia es que los troncos SIP se conectan a una entidad externa, como, por ejemplo, una puerta de enlace del proveedor de servicios de telefonía por Internet (ITSP), mientras que las conexiones SIP se conectan a una entidad interna de la red local, como, por ejemplo, una puerta de enlace de red telefónica conmutada (RTC) o un sistema IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="91e4e-109">The only difference is that you connect SIP trunks to an external entity, such as an ITSP gateway, and you connect direct SIP connections to an internal entity within your local network, such as an IP-PBX or a public switched telephone network (PSTN) gateway.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="91e4e-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="91e4e-110">In This Section</span></span>

  - [<span data-ttu-id="91e4e-111">Opciones de implementación SIP directa en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91e4e-111">Direct SIP deployment options in Lync Server 2013</span></span>](lync-server-2013-direct-sip-deployment-options.md)

  - [<span data-ttu-id="91e4e-112">Opciones de implementación de la puerta de enlace RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91e4e-112">PSTN gateway deployment options in Lync Server 2013</span></span>](lync-server-2013-pstn-gateway-deployment-options.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

