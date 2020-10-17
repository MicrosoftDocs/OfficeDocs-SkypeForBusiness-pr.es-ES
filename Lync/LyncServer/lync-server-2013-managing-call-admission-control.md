---
title: 'Lync Server 2013: administración del control de admisión de llamadas'
description: 'Lync Server 2013: administración del control de admisión de llamadas.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing call admission control
ms:assetid: b0bd4783-6f47-408d-b010-2e30f9bc1770
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721851(v=OCS.15)
ms:contentKeyID: 49733784
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a1c01bff6d1dce48dea314b6704cc0f5ff7d6b2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549466"
---
# <a name="managing-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="dadfa-103">Administración del control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dadfa-103">Managing call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dadfa-104">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="dadfa-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="dadfa-105">El control de admisión de llamadas (CAC) determina, en base al ancho de banda de la red disponible, si está permitido establecer sesiones de comunicación en tiempo real, como son las llamadas de voz o vídeo.</span><span class="sxs-lookup"><span data-stu-id="dadfa-105">Call admission control (CAC) determines, based on available network bandwidth, whether to allow real-time communications sessions such as voice or video calls to be established.</span></span> <span data-ttu-id="dadfa-106">Use los siguientes procedimientos para administrar las distintas características de CAC para su entorno de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dadfa-106">Use the following procedures to manage different CAC features for your Lync Server 2013 environment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="dadfa-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="dadfa-107">In This Section</span></span>

  - [<span data-ttu-id="dadfa-108">Habilitación del control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dadfa-108">Enabling call admission control in Lync Server 2013</span></span>](lync-server-2013-enabling-call-admission-control.md)

  - [<span data-ttu-id="dadfa-109">Administración de perfiles de directiva de ancho de banda de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dadfa-109">Managing network bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-managing-network-bandwidth-policy-profiles.md)

  - [<span data-ttu-id="dadfa-110">Regiones de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dadfa-110">Network regions in Lync Server 2013</span></span>](lync-server-2013-network-regions.md)

  - [<span data-ttu-id="dadfa-111">Rutas de región de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dadfa-111">Network region routes in Lync Server 2013</span></span>](lync-server-2013-network-region-routes.md)

  - [<span data-ttu-id="dadfa-112">Control de admisión de llamadas para sitios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dadfa-112">Call admission control for sites in Lync Server 2013</span></span>](lync-server-2013-call-admission-control-for-sites.md)

  - [<span data-ttu-id="dadfa-113">Habilitación y deshabilitación de la omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dadfa-113">Enabling and disabling media bypass in Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-media-bypass.md)

  - [<span data-ttu-id="dadfa-114">Vincular regiones de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dadfa-114">Linking network regions in Lync Server 2013</span></span>](lync-server-2013-linking-network-regions.md)

  - [<span data-ttu-id="dadfa-115">Administración de subredes de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dadfa-115">Managing network subnets in Lync Server 2013</span></span>](lync-server-2013-managing-network-subnets.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dadfa-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dadfa-116">See Also</span></span>


[<span data-ttu-id="dadfa-117">Información general sobre el control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dadfa-117">Overview of call admission control in Lync Server 2013</span></span>](lync-server-2013-overview-of-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

