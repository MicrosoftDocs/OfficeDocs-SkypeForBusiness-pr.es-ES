---
title: 'Lync Server 2013: servidores perimetrales de audio y vídeo (A/V)'
description: 'Lync Server 2013: servidores perimetrales de audio y vídeo (A/V).'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Audio/Video (A/V) Edge Servers
ms:assetid: b0cc538b-77eb-47fb-be82-5ab0631c6219
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721852(v=OCS.15)
ms:contentKeyID: 49733785
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5aefd4516540485b84ba0eb80f1a809d89eba0e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568796"
---
# <a name="audiovideo-av-edge-servers-in-lync-server-2013"></a><span data-ttu-id="a8171-103">Servidores perimetrales de audio y vídeo (A/V) en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8171-103">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8171-104">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a8171-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a8171-p101">El servicio perimetral A/V permite que los usuarios internos (usuarios conectados a la red de la organización) compartan audio y vídeo con usuarios externos (usuarios no conectados a la red de la organización). Además de audio y vídeo, el servicio perimetral A/V permite compartir el escritorio y transferir archivos, entre otras tareas.</span><span class="sxs-lookup"><span data-stu-id="a8171-p101">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network). In addition to audio and video, the A/V Edge service also provides support for such things desktop sharing and file transfer.</span></span>

<span data-ttu-id="a8171-p102">El servicio perimetral A/V se administra principalmente con la configuración del servidor perimetral A/V. Estas opciones permiten administrar la cantidad máxima de ancho de banda que se asignará por puerto y por usuario, y especificar el tiempo durante el que se puede usar un token de autenticación antes de que se deba renovar. Las opciones de configuración del servidor perimetral A/V se pueden aplicar a sitios o a servidores perimetrales A/V individuales. Cuando determine qué colección de opciones tendrá prioridad, use la siguiente guía:</span><span class="sxs-lookup"><span data-stu-id="a8171-p102">The A/V Edge service is primarily managed by using A/V Edge configuration; these settings enable you to manage the maximum amount of bandwidth to be allocated per port and per user, and to specify the length of time that an authentication token can be used before that token must be renewed. A/V Edge configuration settings can be applied to sites or to individual A/V Edge servers. When determining which collection of settings will take priority, use the following guide:</span></span>

  - <span data-ttu-id="a8171-110">
Las opciones configuradas en el ámbito de servicio (es decir, en un servidor individual) tienen prioridad sobre todo lo demás.</span><span class="sxs-lookup"><span data-stu-id="a8171-110">Settings configured at the service scope (that is, on an individual server) take priority over everything.</span></span>

  - <span data-ttu-id="a8171-p103">
Las opciones configuradas en el ámbito de sitio tienen prioridad sobre las opciones configuradas en el ámbito global. Pero las opciones del ámbito de servicio tienen prioridad sobre las opciones del ámbito de sitio.</span><span class="sxs-lookup"><span data-stu-id="a8171-p103">Settings configured at the site scope take priority over settings configured at the global scope. However, service scope settings will also supersede site-scope settings.</span></span>

  - <span data-ttu-id="a8171-113">
Las opciones configuradas en el ámbito global se usarán solo si no hay opciones de servicio configuradas en el servidor individual y si no hay opciones de sitio configuradas para el sitio en el que se encuentra el servidor.</span><span class="sxs-lookup"><span data-stu-id="a8171-113">Settings at the global scope will be used only if there are no service settings configured on the individual server and if there are no site settings for the site where that server is located.</span></span>

<span data-ttu-id="a8171-114">El servicio perimetral A/V solo se puede administrar con Lync Server PowerShell y los cmdlets CsAVEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="a8171-114">The A/V Edge service can only be managed by using Lync Server PowerShell and the CsAVEdgeConfiguration cmdlets.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a8171-115">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a8171-115">In This Section</span></span>

  - [<span data-ttu-id="a8171-116">Devolver información de configuración del servidor perimetral A/V en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8171-116">Return A/V Edge Server configuration information in Lync Server 2013</span></span>](lync-server-2013-return-a-v-edge-server-configuration-information.md)

  - [<span data-ttu-id="a8171-117">Crear o modificar una colección de opciones de configuración del servidor perimetral A/V en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8171-117">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)

  - [<span data-ttu-id="a8171-118">Eliminar una colección existente de opciones de configuración del servidor perimetral A/V en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8171-118">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

