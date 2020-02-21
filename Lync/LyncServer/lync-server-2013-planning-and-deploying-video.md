---
title: 'Lync Server 2013: Planeación e implementación de vídeo'
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
ms.openlocfilehash: a6cc926ecdf990c9d82c4a088a77611ad0fd5806
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215456"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-and-deploying-video-in-lync-server-2013"></a><span data-ttu-id="fb36e-102">Planeación e implementación de vídeo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb36e-102">Planning and deploying video in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb36e-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="fb36e-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="fb36e-104">Lync Server 2013 presenta las siguientes características de vídeo nuevas:</span><span class="sxs-lookup"><span data-stu-id="fb36e-104">Lync Server 2013 introduces the following new video features:</span></span>

  - <span data-ttu-id="fb36e-105">**Vídeo HD los**   usuarios pueden experimentar resoluciones de hasta alta definición completa (HD) (es decir, 1920 x 1080) en llamadas de dos participantes y conferencias con varios participantes.</span><span class="sxs-lookup"><span data-stu-id="fb36e-105">**HD video**   Users can experience resolutions up to full high definition (HD) (that is, 1920 x 1080) in two-party calls and multiparty conferences.</span></span>

  - <span data-ttu-id="fb36e-106">**Vista de Galería**   en videoconferencias que tienen más de dos personas, los usuarios pueden ver vídeos de los participantes de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="fb36e-106">**Gallery View**   In video conferences that have more than two people, users can see videos of participants in the conference.</span></span> <span data-ttu-id="fb36e-107">Si la conferencia tiene más de cinco participantes, en la fila superior aparecerán solo los vídeos de los participantes más activos, y una foto para los demás participantes.</span><span class="sxs-lookup"><span data-stu-id="fb36e-107">If the conference has more than five participants, video of only the most active participants appears in the top row, and a photo appears for the other participants.</span></span>

  - <span data-ttu-id="fb36e-108">**Vídeo h. 264**   el códec de vídeo h. 264 ahora es el predeterminado para la codificación de vídeo en clientes de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="fb36e-108">**H.264 video**   The H.264 video codec is now the default for encoding video on Lync 2013 clients.</span></span> <span data-ttu-id="fb36e-109">El vídeo H.264 admite un rango mayor de resoluciones y velocidades de fotogramas y mejora la escalabilidad del vídeo.</span><span class="sxs-lookup"><span data-stu-id="fb36e-109">H.264 video supports a greater range of resolutions and frame rates, and improves video scalability.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fb36e-110">Lync Server 2013 todavía admite el códec VC1 para la interoperabilidad con versiones anteriores de Lync.</span><span class="sxs-lookup"><span data-stu-id="fb36e-110">Lync Server 2013 still supports the VC1 codec for interoperability with previous versions of Lync.</span></span> <span data-ttu-id="fb36e-111">Para obtener detalles e información general sobre el nuevo códec de vídeo, consulte el artículo del blog de Jeff Schertz, "interoperabilidad de vídeo <A class=uri href="http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/">http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/</A>en Lync 2013," en.</span><span class="sxs-lookup"><span data-stu-id="fb36e-111">For details and background information about the new video codec, see Jeff Schertz's Blog article, "Video Interoperability in Lync 2013," at <A class=uri href="http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/">http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/</A>.</span></span>

    
    </div>

<span data-ttu-id="fb36e-112">En esta sección se describe cómo administrar el ancho de banda para vídeo en Lync Server 2013 y cómo configurar las características de vídeo.</span><span class="sxs-lookup"><span data-stu-id="fb36e-112">This section describes how to manage bandwidth for video in Lync Server 2013 and how to configure video features.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fb36e-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="fb36e-113">In This Section</span></span>

  - [<span data-ttu-id="fb36e-114">Configuración del ancho de banda de vídeo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb36e-114">Configuring video bandwidth in Lync Server 2013</span></span>](lync-server-2013-configuring-video-bandwidth.md)

  - [<span data-ttu-id="fb36e-115">Configuración de la vista de galería en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb36e-115">Configuring Gallery View in Lync Server 2013</span></span>](lync-server-2013-configuring-gallery-view.md)

  - [<span data-ttu-id="fb36e-116">Configuración de escenarios de ejemplo de vídeo para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb36e-116">Configuring video example scenarios for Lync Server 2013</span></span>](lync-server-2013-configuring-video-example-scenarios.md)

  - [<span data-ttu-id="fb36e-117">Consideraciones sobre interoperabilidad para la Conferencia de vídeo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb36e-117">Interoperability considerations for video conferencing in Lync Server 2013</span></span>](lync-server-2013-interoperability-considerations-for-video-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

