---
title: 'Lync Server 2013: Planeación e implementación de vídeo'
description: 'Lync Server 2013: Planeación e implementación de vídeo.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning and deploying video
ms:assetid: dadfb7f3-dfd6-4847-b137-17dacafd7368
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205307(v=OCS.15)
ms:contentKeyID: 48185558
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9fd8a93f890295daebd2bc887414a2417b86395
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578176"
---
# <a name="planning-and-deploying-video-in-lync-server-2013"></a><span data-ttu-id="8f0c8-103">Planeación e implementación de vídeo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f0c8-103">Planning and deploying video in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8f0c8-104">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="8f0c8-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="8f0c8-105">Lync Server 2013 presenta las siguientes características de vídeo nuevas:</span><span class="sxs-lookup"><span data-stu-id="8f0c8-105">Lync Server 2013 introduces the following new video features:</span></span>

  - <span data-ttu-id="8f0c8-106">**Vídeo HD**     Los usuarios pueden experimentar resoluciones de hasta alta definición completa (HD) (es decir, 1920 x 1080) en llamadas de dos participantes y conferencias con varios participantes.</span><span class="sxs-lookup"><span data-stu-id="8f0c8-106">**HD video**   Users can experience resolutions up to full high definition (HD) (that is, 1920 x 1080) in two-party calls and multiparty conferences.</span></span>

  - <span data-ttu-id="8f0c8-107">**Vista**     de Galería En las conferencias de vídeo que tienen más de dos personas, los usuarios pueden ver vídeos de participantes en la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="8f0c8-107">**Gallery View**   In video conferences that have more than two people, users can see videos of participants in the conference.</span></span> <span data-ttu-id="8f0c8-108">Si la conferencia tiene más de cinco participantes, en la fila superior aparecerán solo los vídeos de los participantes más activos, y una foto para los demás participantes.</span><span class="sxs-lookup"><span data-stu-id="8f0c8-108">If the conference has more than five participants, video of only the most active participants appears in the top row, and a photo appears for the other participants.</span></span>

  - <span data-ttu-id="8f0c8-109">Vídeo H. **264**     El códec de vídeo H. 264 ahora es el predeterminado para la codificación de vídeo en clientes de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="8f0c8-109">**H.264 video**   The H.264 video codec is now the default for encoding video on Lync 2013 clients.</span></span> <span data-ttu-id="8f0c8-110">El vídeo H.264 admite un rango mayor de resoluciones y velocidades de fotogramas y mejora la escalabilidad del vídeo.</span><span class="sxs-lookup"><span data-stu-id="8f0c8-110">H.264 video supports a greater range of resolutions and frame rates, and improves video scalability.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8f0c8-111">Lync Server 2013 todavía admite el códec VC1 para la interoperabilidad con versiones anteriores de Lync.</span><span class="sxs-lookup"><span data-stu-id="8f0c8-111">Lync Server 2013 still supports the VC1 codec for interoperability with previous versions of Lync.</span></span> <span data-ttu-id="8f0c8-112">Para obtener detalles e información general sobre el nuevo códec de vídeo, consulte el artículo del blog de Jeff Schertz, "interoperabilidad de vídeo en Lync 2013," en <A class=uri href="http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/">http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/</A> .</span><span class="sxs-lookup"><span data-stu-id="8f0c8-112">For details and background information about the new video codec, see Jeff Schertz's Blog article, "Video Interoperability in Lync 2013," at <A class=uri href="http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/">http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/</A>.</span></span>

    
    </div>

<span data-ttu-id="8f0c8-113">En esta sección se describe cómo administrar el ancho de banda para vídeo en Lync Server 2013 y cómo configurar las características de vídeo.</span><span class="sxs-lookup"><span data-stu-id="8f0c8-113">This section describes how to manage bandwidth for video in Lync Server 2013 and how to configure video features.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8f0c8-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="8f0c8-114">In This Section</span></span>

  - [<span data-ttu-id="8f0c8-115">Configuración del ancho de banda de vídeo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f0c8-115">Configuring video bandwidth in Lync Server 2013</span></span>](lync-server-2013-configuring-video-bandwidth.md)

  - [<span data-ttu-id="8f0c8-116">Configuración de la vista de galería en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f0c8-116">Configuring Gallery View in Lync Server 2013</span></span>](lync-server-2013-configuring-gallery-view.md)

  - [<span data-ttu-id="8f0c8-117">Configuración de escenarios de ejemplo de vídeo para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f0c8-117">Configuring video example scenarios for Lync Server 2013</span></span>](lync-server-2013-configuring-video-example-scenarios.md)

  - [<span data-ttu-id="8f0c8-118">Consideraciones sobre interoperabilidad para la Conferencia de vídeo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f0c8-118">Interoperability considerations for video conferencing in Lync Server 2013</span></span>](lync-server-2013-interoperability-considerations-for-video-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

