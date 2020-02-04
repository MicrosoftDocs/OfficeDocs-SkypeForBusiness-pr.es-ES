---
title: 'Lync Server 2013: planificación e implementación de video'
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
ms.openlocfilehash: 2662a6397bc096969ca73baab096bc886de65ce3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755160"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-and-deploying-video-in-lync-server-2013"></a><span data-ttu-id="268f2-102">Planificación e implementación de vídeo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="268f2-102">Planning and deploying video in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="268f2-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="268f2-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="268f2-104">Lync Server 2013 presenta las siguientes características nuevas de vídeo:</span><span class="sxs-lookup"><span data-stu-id="268f2-104">Lync Server 2013 introduces the following new video features:</span></span>

  - <span data-ttu-id="268f2-105">\*\*\*\*   Los usuarios de video de alta definición pueden experimentar resoluciones de alta definición (HD) completas (es decir, 1920 x 1080) en llamadas de dos participantes y en conferencias de varias partes.</span><span class="sxs-lookup"><span data-stu-id="268f2-105">**HD video**   Users can experience resolutions up to full high definition (HD) (that is, 1920 x 1080) in two-party calls and multiparty conferences.</span></span>

  - <span data-ttu-id="268f2-106">**Vista de Galería**   en las videoconferencias que tengan más de dos personas, los usuarios pueden ver vídeos de los participantes de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="268f2-106">**Gallery View**   In video conferences that have more than two people, users can see videos of participants in the conference.</span></span> <span data-ttu-id="268f2-107">Si la Conferencia tiene más de cinco participantes, el vídeo de los participantes más activos aparecerá en la fila superior y se mostrará una foto para el resto de los participantes.</span><span class="sxs-lookup"><span data-stu-id="268f2-107">If the conference has more than five participants, video of only the most active participants appears in the top row, and a photo appears for the other participants.</span></span>

  - <span data-ttu-id="268f2-108">**Vídeo h. 264**   el códec de vídeo h. 264 es ahora el predeterminado para la codificación de video en clientes de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="268f2-108">**H.264 video**   The H.264 video codec is now the default for encoding video on Lync 2013 clients.</span></span> <span data-ttu-id="268f2-109">El video H. 264 soporta una mayor variedad de resoluciones y velocidades de fotogramas, y mejora la escalabilidad de video.</span><span class="sxs-lookup"><span data-stu-id="268f2-109">H.264 video supports a greater range of resolutions and frame rates, and improves video scalability.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="268f2-110">Lync Server 2013 aún admite el códec VC1 para la interoperabilidad con versiones anteriores de Lync.</span><span class="sxs-lookup"><span data-stu-id="268f2-110">Lync Server 2013 still supports the VC1 codec for interoperability with previous versions of Lync.</span></span> <span data-ttu-id="268f2-111">Para obtener detalles e información general sobre el nuevo códec de vídeo, consulte el artículo del blog de Jeff Schertz, "interoperabilidad de vídeo <A class=uri href="http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/">http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/</A>en Lync 2013", en.</span><span class="sxs-lookup"><span data-stu-id="268f2-111">For details and background information about the new video codec, see Jeff Schertz's Blog article, "Video Interoperability in Lync 2013," at <A class=uri href="http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/">http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/</A>.</span></span>

    
    </div>

<span data-ttu-id="268f2-112">En esta sección se describe cómo administrar el ancho de banda para vídeo en Lync Server 2013 y cómo configurar las características de vídeo.</span><span class="sxs-lookup"><span data-stu-id="268f2-112">This section describes how to manage bandwidth for video in Lync Server 2013 and how to configure video features.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="268f2-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="268f2-113">In This Section</span></span>

  - [<span data-ttu-id="268f2-114">Configuración del ancho de banda de vídeo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="268f2-114">Configuring video bandwidth in Lync Server 2013</span></span>](lync-server-2013-configuring-video-bandwidth.md)

  - [<span data-ttu-id="268f2-115">Configuración de la vista de galería en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="268f2-115">Configuring Gallery View in Lync Server 2013</span></span>](lync-server-2013-configuring-gallery-view.md)

  - [<span data-ttu-id="268f2-116">Configuración de escenarios de ejemplo de vídeo para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="268f2-116">Configuring video example scenarios for Lync Server 2013</span></span>](lync-server-2013-configuring-video-example-scenarios.md)

  - [<span data-ttu-id="268f2-117">Consideraciones de interoperabilidad para videoconferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="268f2-117">Interoperability considerations for video conferencing in Lync Server 2013</span></span>](lync-server-2013-interoperability-considerations-for-video-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

