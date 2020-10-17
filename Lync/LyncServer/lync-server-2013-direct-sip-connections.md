---
title: 'Lync Server 2013: conexiones SIP directas'
description: 'Lync Server 2013: conexiones SIP directas.'
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
ms.openlocfilehash: ebc42cd26472bbb19c7ef886a9449ab453b90680
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559676"
---
# <a name="direct-sip-connections-in-lync-server-2013"></a><span data-ttu-id="e85e5-103">Conexiones SIP directas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e85e5-103">Direct SIP connections in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e85e5-104">_**Última modificación del tema:** 2012-08-13_</span><span class="sxs-lookup"><span data-stu-id="e85e5-104">_**Topic Last Modified:** 2012-08-13_</span></span>

<span data-ttu-id="e85e5-105">Puede usar *las conexiones SIP directas* para conectar Lync Server a cualquiera de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="e85e5-105">You can use *direct SIP connections* to connect Lync Server to either of the following:</span></span>

  - <span data-ttu-id="e85e5-106">Un IP-PBX (para obtener más información, consulte [Opciones de implementación SIP directa en Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md)).</span><span class="sxs-lookup"><span data-stu-id="e85e5-106">An IP-PBX (for details, see [Direct SIP deployment options in Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md)).</span></span>

  - <span data-ttu-id="e85e5-107">Una puerta de enlace RTC (para obtener más información, consulte [Opciones de implementación de la puerta de enlace RTC en Lync Server 2013](lync-server-2013-pstn-gateway-deployment-options.md)).</span><span class="sxs-lookup"><span data-stu-id="e85e5-107">A PSTN gateway (for details, see [PSTN gateway deployment options in Lync Server 2013](lync-server-2013-pstn-gateway-deployment-options.md)).</span></span>

<span data-ttu-id="e85e5-108">Para implementar una conexión SIP directa, deberá seguir básicamente los mismos pasos de implementación que seguiría para implementar un tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="e85e5-108">To implement a direct SIP connection, you follow essentially the same deployment steps as you would to implement a SIP trunk.</span></span> <span data-ttu-id="e85e5-109">En ambos casos, la conexión se implementa mediante la interfaz externa de un servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="e85e5-109">In both cases, you implement the connection by using the external interface of a Mediation Server.</span></span> <span data-ttu-id="e85e5-110">La única diferencia es que los troncos SIP se conectan a una entidad externa, como, por ejemplo, una puerta de enlace del proveedor de servicios de telefonía por Internet (ITSP), mientras que las conexiones SIP se conectan a una entidad interna de la red local, como, por ejemplo, una puerta de enlace de red telefónica conmutada (RTC) o un sistema IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="e85e5-110">The only difference is that you connect SIP trunks to an external entity, such as an ITSP gateway, and you connect direct SIP connections to an internal entity within your local network, such as an IP-PBX or a public switched telephone network (PSTN) gateway.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e85e5-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e85e5-111">In This Section</span></span>

  - [<span data-ttu-id="e85e5-112">Opciones de implementación SIP directa en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e85e5-112">Direct SIP deployment options in Lync Server 2013</span></span>](lync-server-2013-direct-sip-deployment-options.md)

  - [<span data-ttu-id="e85e5-113">Opciones de implementación de la puerta de enlace RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e85e5-113">PSTN gateway deployment options in Lync Server 2013</span></span>](lync-server-2013-pstn-gateway-deployment-options.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

