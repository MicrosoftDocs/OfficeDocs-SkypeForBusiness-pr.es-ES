---
title: 'Lync Server 2013: administración de la infraestructura de red de Lync Server 2013'
description: 'Lync Server 2013: administración de la infraestructura de red de Lync Server 2013.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing the Lync Server 2013 network infrastructure
ms:assetid: cb13456a-8f66-4595-be21-8887f30ad4eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182585(v=OCS.15)
ms:contentKeyID: 48185638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab1b5c6fe52374b012063ac26640e9bb25496ad7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564106"
---
# <a name="managing-the-lync-server-2013-network-infrastructure"></a><span data-ttu-id="98629-103">Administración de la infraestructura de red de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98629-103">Managing the Lync Server 2013 network infrastructure</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98629-104">_**Última modificación del tema:** 2014-02-11_</span><span class="sxs-lookup"><span data-stu-id="98629-104">_**Topic Last Modified:** 2014-02-11_</span></span>

<span data-ttu-id="98629-105">Microsoft Lync Server 2013 incluye compatibilidad con el control de admisión de llamadas (CAC) y la omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="98629-105">Microsoft Lync Server 2013 includes support for call admission control (CAC) and media bypass.</span></span> <span data-ttu-id="98629-106">Para implementar estas características, debe configurar una red de regiones, sitios, subredes, etc., que le permitan administrar el ancho de banda en situaciones en las que las transmisiones de audio y vídeo deban restringirse.</span><span class="sxs-lookup"><span data-stu-id="98629-106">To implement these features you must configure a network of regions, sites, subnets, and so on that will allow you to manage bandwidth in situations where audio and video transmissions need to be restricted.</span></span> <span data-ttu-id="98629-107">También puede usar la tecnología de red Calidad de servicio (QoS) para ayudar a proporcionar una experiencia de usuario final óptima en las comunicaciones de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="98629-107">You can also use the Quality of Service (QoS) networking technology to help provide an optimal end-user experience for audio and video communications.</span></span>

<span data-ttu-id="98629-108">Puede usar el panel de control de Lync Server para configurar y administrar el CAC, el desvío de medios y la QoS.</span><span class="sxs-lookup"><span data-stu-id="98629-108">You can use the Lync Server Control Panel to set up and manage CAC, media bypass, and QoS.</span></span> <span data-ttu-id="98629-109">En los temas siguientes se indican los pasos para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="98629-109">The following topics provide steps for how to do this.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="98629-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="98629-110">In This Section</span></span>

  - [<span data-ttu-id="98629-111">Administración de la calidad de servicio (QoS) en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98629-111">Managing Quality of Service (QoS) in Lync Server 2013</span></span>](lync-server-2013-managing-quality-of-service-qos.md)

  - [<span data-ttu-id="98629-112">Administración del control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98629-112">Managing call admission control in Lync Server 2013</span></span>](lync-server-2013-managing-call-admission-control.md)

  - [<span data-ttu-id="98629-113">Interfaces de red de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98629-113">Lync Server 2013 network interfaces</span></span>](lync-server-2013-lync-server-network-interfaces.md)

  - [<span data-ttu-id="98629-114">Impedir nuevas conexiones a Lync Server 2013 para el mantenimiento del servidor</span><span class="sxs-lookup"><span data-stu-id="98629-114">Prevent new connections to Lync Server 2013 for server maintenance</span></span>](lync-server-2013-prevent-new-connections-to-lync-server-for-server-maintenance.md)

  - [<span data-ttu-id="98629-115">Metodología de calidad de llamadas de Lync en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98629-115">Lync Call Quality Methodology in Lync Server 2013</span></span>](lync-server-2013-poster-lync-call-quality-methodology.md)

  - [<span data-ttu-id="98629-116">Indicadores de estado clave en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98629-116">Key Health Indicators in Lync Server 2013</span></span>](lync-server-2013-poster-key-health-indicators.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

