---
title: 'Lync Server 2013: administración de control de admisión de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing call admission control
ms:assetid: b0bd4783-6f47-408d-b010-2e30f9bc1770
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721851(v=OCS.15)
ms:contentKeyID: 49733784
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65b45ee414a1087bbfb6a5e3a774dedc074cd992
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828155"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="a7aa9-102">Administración del control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7aa9-102">Managing call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7aa9-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a7aa9-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a7aa9-104">El control de admisión de llamadas (CAC) determina, en base al ancho de banda de la red disponible, si está permitido establecer sesiones de comunicación en tiempo real, como son las llamadas de voz o vídeo.</span><span class="sxs-lookup"><span data-stu-id="a7aa9-104">Call admission control (CAC) determines, based on available network bandwidth, whether to allow real-time communications sessions such as voice or video calls to be established.</span></span> <span data-ttu-id="a7aa9-105">Use los procedimientos siguientes para administrar las distintas características de CAC para el entorno de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a7aa9-105">Use the following procedures to manage different CAC features for your Lync Server 2013 environment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a7aa9-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a7aa9-106">In This Section</span></span>

  - [<span data-ttu-id="a7aa9-107">Habilitar el control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7aa9-107">Enabling call admission control in Lync Server 2013</span></span>](lync-server-2013-enabling-call-admission-control.md)

  - [<span data-ttu-id="a7aa9-108">Administrar perfiles de directiva de ancho de banda de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7aa9-108">Managing network bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-managing-network-bandwidth-policy-profiles.md)

  - [<span data-ttu-id="a7aa9-109">Regiones de red de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7aa9-109">Network regions in Lync Server 2013</span></span>](lync-server-2013-network-regions.md)

  - [<span data-ttu-id="a7aa9-110">Rutas de la región de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7aa9-110">Network region routes in Lync Server 2013</span></span>](lync-server-2013-network-region-routes.md)

  - [<span data-ttu-id="a7aa9-111">Control de admisión de llamadas para sitios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7aa9-111">Call admission control for sites in Lync Server 2013</span></span>](lync-server-2013-call-admission-control-for-sites.md)

  - [<span data-ttu-id="a7aa9-112">Habilitar y deshabilitar la omisión de elementos multimedia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7aa9-112">Enabling and disabling media bypass in Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-media-bypass.md)

  - [<span data-ttu-id="a7aa9-113">Vincular regiones de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7aa9-113">Linking network regions in Lync Server 2013</span></span>](lync-server-2013-linking-network-regions.md)

  - [<span data-ttu-id="a7aa9-114">Administración de subredes de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7aa9-114">Managing network subnets in Lync Server 2013</span></span>](lync-server-2013-managing-network-subnets.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a7aa9-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7aa9-115">See Also</span></span>


[<span data-ttu-id="a7aa9-116">Información general sobre el control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7aa9-116">Overview of call admission control in Lync Server 2013</span></span>](lync-server-2013-overview-of-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

