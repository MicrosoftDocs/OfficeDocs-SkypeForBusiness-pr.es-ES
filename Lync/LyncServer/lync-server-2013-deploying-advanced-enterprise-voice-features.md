---
title: 'Lync Server 2013: implementación de características avanzadas de telefonía IP empresarial'
description: 'Lync Server 2013: implementación de características avanzadas de telefonía IP empresarial.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying advanced Enterprise Voice features
ms:assetid: 286d9c0b-9442-448f-a6e5-95b3034278fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425753(v=OCS.15)
ms:contentKeyID: 48183675
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e5cab05de60e1df1611a14af1f5239c24402c6d9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558586"
---
# <a name="deploying-advanced-enterprise-voice-features-in-lync-server-2013"></a><span data-ttu-id="39beb-103">Implementación de características avanzadas de telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39beb-103">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39beb-104">_**Última modificación del tema:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="39beb-104">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="39beb-105">Una vez que haya configurado las funciones básicas de Enterprise Voice para su organización, puede implementar una o más características avanzadas de telefonía IP empresarial siguiendo los procedimientos de esta sección.</span><span class="sxs-lookup"><span data-stu-id="39beb-105">After you have configured basic Enterprise Voice functionality for your organization, you can optionally deploy one or more advanced Enterprise Voice features by following the procedures in this section.</span></span>

<span data-ttu-id="39beb-106">Para obtener más información sobre las características avanzadas de telefonía IP empresarial, consulte las siguientes secciones de la documentación de [planeación de Lync Server 2013](lync-server-2013-planning.md) :</span><span class="sxs-lookup"><span data-stu-id="39beb-106">For details about the advanced Enterprise Voice features, see the following sections of the [Planning for Lync Server 2013](lync-server-2013-planning.md) documentation:</span></span>

  - [<span data-ttu-id="39beb-107">Planeación del control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39beb-107">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)

  - [<span data-ttu-id="39beb-108">Planeación de los servicios de emergencia (E9-1-1) en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39beb-108">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [<span data-ttu-id="39beb-109">Planeación de la omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39beb-109">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)

<div>

## <a name="in-this-section"></a><span data-ttu-id="39beb-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="39beb-110">In This Section</span></span>

  - [<span data-ttu-id="39beb-111">Acerca de las regiones de red, sitios y subredes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39beb-111">About network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-about-network-regions-sites-and-subnets.md)

  - [<span data-ttu-id="39beb-112">Crear o modificar una región de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39beb-112">Create or modify a network region in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-region.md)

  - [<span data-ttu-id="39beb-113">Crear o modificar un sitio de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39beb-113">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)

  - [<span data-ttu-id="39beb-114">Asociar una subred a un sitio de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39beb-114">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)

  - [<span data-ttu-id="39beb-115">Configurar el control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39beb-115">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)

  - [<span data-ttu-id="39beb-116">Configurar 9-1-1 mejorado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39beb-116">Configure Enhanced 9-1-1 in Lync Server 2013</span></span>](lync-server-2013-configure-enhanced-9-1-1.md)

  - [<span data-ttu-id="39beb-117">Configurar la omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39beb-117">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

