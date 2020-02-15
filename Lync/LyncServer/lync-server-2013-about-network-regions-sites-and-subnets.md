---
title: 'Lync Server 2013: acerca de regiones de red, sitios y subredes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: About network regions, sites, and subnets
ms:assetid: 6662123a-d011-408c-a290-92b2a8589943
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398467(v=OCS.15)
ms:contentKeyID: 48184335
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2f6de7a39b3029f1edc1252b90ec264d774632f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037932"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="about-network-regions-sites-and-subnets-in-lync-server-2013"></a><span data-ttu-id="c8c06-102">Acerca de las regiones de red, sitios y subredes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8c06-102">About network regions, sites, and subnets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8c06-103">_**Última modificación del tema:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="c8c06-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="c8c06-p101">Las características avanzadas de Telefonía IP empresarial que se describen en esta sección comparten ciertos requisitos de configuración de regiones de red, sitios de red y subredes. Por ejemplo, las tres características avanzadas requieren que cada una de las subredes de la topología estén asociadas a un *sitio de red* específico, y cada uno de los sitios de red deben estar asociados a una *región de red*.</span><span class="sxs-lookup"><span data-stu-id="c8c06-p101">The advanced Enterprise Voice features described in this section share certain configuration requirements for network regions, network sites, and subnets. For example, all three advanced features require that each subnet in your topology be associated with a specific *network site*, and each network site must be associated with a *network region*.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c8c06-106">Antes de comenzar la configuración de red para el control de admisión de llamadas, E9-1-1 o el desvío de medios, asegúrese de que ha revisado información adicional acerca de la configuración de red en el tema <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">configuración de red para las características avanzadas de telefonía IP en Lync Server 2013</A> de la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="c8c06-106">Before you begin network configuration for call admission control, E9-1-1, or media bypass, make sure that you reviewed additional information about network settings in the <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Network settings for the advanced Enterprise Voice features in Lync Server 2013</A> topic in the Planning documentation.</span></span> <span data-ttu-id="c8c06-107">Para obtener más información acerca de la configuración de red principalmente sobre el control de admisión de llamadas, consulte también <A href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">definir los requisitos para el control de admisión de llamadas en Lync Server 2013</A> en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="c8c06-107">For details about network configuration primarily about call admission control, also see <A href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<span data-ttu-id="c8c06-108">El control de admisión de llamadas y E9-1-1 tienen requisitos de configuración adicionales para los sitios de red:</span><span class="sxs-lookup"><span data-stu-id="c8c06-108">Call admission control and E9-1-1 have additional configuration requirements for network sites:</span></span>

  - <span data-ttu-id="c8c06-109">El control de admisión de llamadas requiere que se especifique un *perfil de directiva de ancho de banda* para cada uno de los sitios restringidos con limitaciones de ancho de banda WAN.</span><span class="sxs-lookup"><span data-stu-id="c8c06-109">Call admission control requires that a *bandwidth policy profile* be specified for each site that is constrained by WAN bandwidth limitations.</span></span> <span data-ttu-id="c8c06-110">Si planea implementar el control de admisión de llamadas, debe [crear perfiles de directiva de ancho de banda en Lync Server 2013 antes de](lync-server-2013-create-bandwidth-policy-profiles.md) configurar los sitios de red.</span><span class="sxs-lookup"><span data-stu-id="c8c06-110">If you plan to deploy call admission control, you must [Create bandwidth policy profiles in Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md) before you configure your network sites.</span></span>

  - <span data-ttu-id="c8c06-111">E9-1-1 requiere que se especifique una *directiva de ubicación* para cada uno de los sitios.</span><span class="sxs-lookup"><span data-stu-id="c8c06-111">E9-1-1 requires that a *location policy* be specified for each site.</span></span> <span data-ttu-id="c8c06-112">Si tiene previsto implementar E9-1-1, debe [crear directivas de ubicación en Lync Server 2013](lync-server-2013-create-location-policies.md) antes de configurar los sitios de red.</span><span class="sxs-lookup"><span data-stu-id="c8c06-112">If you plan to deploy E9-1-1, you must [Create location policies in Lync Server 2013](lync-server-2013-create-location-policies.md) before you configure your network sites.</span></span>

<div>

## <a name="create-or-modify-network-regions-network-sites-and-subnets"></a><span data-ttu-id="c8c06-113">Crear o modificar regiones de red, sitios de red y subredes</span><span class="sxs-lookup"><span data-stu-id="c8c06-113">Create or Modify Network Regions, Network Sites, and Subnets</span></span>

<span data-ttu-id="c8c06-p105">En los siguientes temas se proporcionan pasos para crear o modificar regiones de red y sitios de red, y para asociar subredes a sitios de red. Estos temas no son específicos de ninguna característica avanzada de Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="c8c06-p105">The following topics provide steps to create or modify network regions and network sites, and to associate subnets with network sites. These topics are not specific to any particular advanced Enterprise Voice feature.</span></span>

  - [<span data-ttu-id="c8c06-116">Crear o modificar una región de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8c06-116">Create or modify a network region in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-region.md)

  - [<span data-ttu-id="c8c06-117">Crear o modificar un sitio de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8c06-117">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)

  - [<span data-ttu-id="c8c06-118">Asociar una subred a un sitio de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8c06-118">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

