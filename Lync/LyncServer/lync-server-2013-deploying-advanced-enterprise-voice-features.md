---
title: 'Lync Server 2013: implementar características avanzadas de telefonía empresarial'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying advanced Enterprise Voice features
ms:assetid: 286d9c0b-9442-448f-a6e5-95b3034278fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425753(v=OCS.15)
ms:contentKeyID: 48183675
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7fff128d98f82745e471f39e8f172c6ddb7a8a52
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835567"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-advanced-enterprise-voice-features-in-lync-server-2013"></a><span data-ttu-id="f5b0a-102">Implementación de características avanzadas de telefonía empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5b0a-102">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5b0a-103">_**Última modificación del tema:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="f5b0a-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="f5b0a-104">Tras haber configurado las funciones básicas de Telefonía IP empresarial en la organización, se puede optar por implementar una o más características avanzadas de Telefonía IP empresarial siguiendo los procedimientos de esta sección.</span><span class="sxs-lookup"><span data-stu-id="f5b0a-104">After you have configured basic Enterprise Voice functionality for your organization, you can optionally deploy one or more advanced Enterprise Voice features by following the procedures in this section.</span></span>

<span data-ttu-id="f5b0a-105">Para obtener más información sobre las características avanzadas de telefonía empresarial, consulte las siguientes secciones de la documentación de [planeación de Lync Server 2013](lync-server-2013-planning.md) :</span><span class="sxs-lookup"><span data-stu-id="f5b0a-105">For details about the advanced Enterprise Voice features, see the following sections of the [Planning for Lync Server 2013](lync-server-2013-planning.md) documentation:</span></span>

  - [<span data-ttu-id="f5b0a-106">Planear el control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5b0a-106">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)

  - [<span data-ttu-id="f5b0a-107">Planeación de los servicios de emergencia (E9-1-1) en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5b0a-107">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [<span data-ttu-id="f5b0a-108">Planificar la omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5b0a-108">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)

<div>

## <a name="in-this-section"></a><span data-ttu-id="f5b0a-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f5b0a-109">In This Section</span></span>

  - [<span data-ttu-id="f5b0a-110">Acerca de las regiones de red, sitios y subredes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5b0a-110">About network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-about-network-regions-sites-and-subnets.md)

  - [<span data-ttu-id="f5b0a-111">Crear o modificar una región de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5b0a-111">Create or modify a network region in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-region.md)

  - [<span data-ttu-id="f5b0a-112">Crear o modificar un sitio de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5b0a-112">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)

  - [<span data-ttu-id="f5b0a-113">Asociar una subred a un sitio de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5b0a-113">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)

  - [<span data-ttu-id="f5b0a-114">Configurar el control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5b0a-114">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)

  - [<span data-ttu-id="f5b0a-115">Configurar 9-1-1 mejorado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5b0a-115">Configure Enhanced 9-1-1 in Lync Server 2013</span></span>](lync-server-2013-configure-enhanced-9-1-1.md)

  - [<span data-ttu-id="f5b0a-116">Configurar la omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5b0a-116">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

