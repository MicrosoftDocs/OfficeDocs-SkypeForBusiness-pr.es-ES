---
title: 'Lync Server 2013: definir el ámbito de la implementación de E9-1-1'
description: 'Lync Server 2013: definir el ámbito de la implementación de E9-1-1.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the scope of the E9-1-1 deployment
ms:assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425775(v=OCS.15)
ms:contentKeyID: 48183707
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14e442718b7230dbc94aebdf6099aae9b430d5e9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567542"
---
# <a name="defining-the-scope-of-the-e9-1-1-deployment-in-lync-server-2013"></a><span data-ttu-id="25aef-103">Definir el ámbito de la implementación de E9-1-1 en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25aef-103">Defining the scope of the E9-1-1 deployment in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25aef-104">_**Última modificación del tema:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="25aef-104">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="25aef-105">Antes de configurar Microsoft Lync Server 2013 para E9-1-1, debe planear la implementación de E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="25aef-105">Before you configure Microsoft Lync Server 2013 for E9-1-1, you need to plan your E9-1-1 deployment.</span></span> <span data-ttu-id="25aef-106">Algunas de las preguntas que se deben tener en cuenta son:</span><span class="sxs-lookup"><span data-stu-id="25aef-106">Some of the questions to consider include:</span></span>

  - <span data-ttu-id="25aef-107">**¿Cuáles son las obligaciones legales y la Directiva de su organización con respecto a E9-1-1?**</span><span class="sxs-lookup"><span data-stu-id="25aef-107">**What are your organization’s policy and legal obligations with regard to E9-1-1?**</span></span>  
    <span data-ttu-id="25aef-108">Los requisitos legales de E9-1-1 para PBX (llamados sistemas telefónicos de varias líneas o MLTS, en lenguaje E9-1-1) difieren de un estado a un estado.</span><span class="sxs-lookup"><span data-stu-id="25aef-108">E9-1-1 legal requirements for PBXs (called Multi-line Telephone Systems, or MLTS, in E9-1-1 parlance) differ from state to state.</span></span> <span data-ttu-id="25aef-109">Debe consultar a su equipo jurídico para conocer las obligaciones que se pueden aplicar a su implementación de Lync Server en las ubicaciones geográficas pertinentes.</span><span class="sxs-lookup"><span data-stu-id="25aef-109">You should consult with your legal team to understand the obligations that may apply to your deployment of Lync Server in your relevant geographies.</span></span>

<!-- end list -->

  - <span data-ttu-id="25aef-110">**¿Qué áreas de la empresa deben estar habilitadas para E9-1-1?**</span><span class="sxs-lookup"><span data-stu-id="25aef-110">**What areas within your enterprise need to be enabled for E9-1-1?**</span></span>  
    <span data-ttu-id="25aef-111">Puede habilitar E9-1-1 para toda la empresa o para ubicaciones seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="25aef-111">You can enable E9-1-1 for the entire enterprise or for selected locations.</span></span> <span data-ttu-id="25aef-112">Por ejemplo, puede que tenga que variar E9-1-1 requisitos para oficinas en diferentes Estados o puede que desee excluir sitios de fuera de Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="25aef-112">For example, you may have varying E9-1-1 requirements for offices in different states, or you may want to exclude sites outside the U.S.</span></span>

<!-- end list -->

  - <span data-ttu-id="25aef-113">**¿Cómo implementará E9-1-1 en los sitios de sucursal?**</span><span class="sxs-lookup"><span data-stu-id="25aef-113">**How will you deploy E9-1-1 to branch sites?**</span></span>  
    <span data-ttu-id="25aef-114">La resistencia de voz es un concepto importante que debe comprender al implementar E9-1-1 en un sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="25aef-114">Voice resiliency is an important concept to understand when deploying E9-1-1 at a branch site.</span></span> <span data-ttu-id="25aef-115">Si tiene troncos E-9-1-1 SIP centralizados y se produce una interrupción de la WAN, es posible que los clientes que inicien sesión no puedan obtener una ubicación del servicio de información de ubicaciones o para conectarse al proveedor de servicios de emergencias.</span><span class="sxs-lookup"><span data-stu-id="25aef-115">If you have centralized E-9-1-1 SIP trunks and a WAN outage occurs, clients signing in may not be able to obtain a location from Location Information service or to connect to the emergency services service provider.</span></span> <span data-ttu-id="25aef-116">Lync Server ofrece varias estrategias para controlar la resistencia de voz en las sucursales, entre las que se incluyen: tener redes de datos resistentes, implementar un tronco SIP en cada sucursal o presionar llamadas de emergencia a la puerta de enlace local durante las interrupciones.</span><span class="sxs-lookup"><span data-stu-id="25aef-116">Lync Server provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing emergency calls out to the local gateway during outages.</span></span> <span data-ttu-id="25aef-117">Para obtener más información, consulte [Planning for Branch-site Voice Resiliency en Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span><span class="sxs-lookup"><span data-stu-id="25aef-117">For details, see [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span></span>

<!-- end list -->

  - <span data-ttu-id="25aef-118">**¿Se habilitará E9-1-1 para los usuarios que trabajan fuera de la red?**</span><span class="sxs-lookup"><span data-stu-id="25aef-118">**Will you enable E9-1-1 for users working outside the network?**</span></span>  
    <span data-ttu-id="25aef-119">La adquisición de ubicación automática solo está disponible para los clientes que se encuentran dentro de la red de la organización, por lo que su organización debe decidir si será compatible con las llamadas de E9-1-1 realizadas desde los clientes de Lync mientras se encuentran fuera del entorno.</span><span class="sxs-lookup"><span data-stu-id="25aef-119">Automatic location acquisition is available only for clients located inside the organization’s network, so your organization needs to decide whether it will support E9-1-1 calls made from Lync clients while off-premises.</span></span> <span data-ttu-id="25aef-120">Por ejemplo, ¿permitirá que los usuarios realicen llamadas de emergencia si están trabajando desde casa o desde un sitio del cliente?</span><span class="sxs-lookup"><span data-stu-id="25aef-120">For example, will you enable users to place emergency calls if they are working from home or from a customer site?</span></span> <span data-ttu-id="25aef-121">Si un cliente se encuentra fuera de la red de la empresa, se puede configurar el cliente para que solicite una ubicación al usuario.</span><span class="sxs-lookup"><span data-stu-id="25aef-121">If a client is located outside the enterprise network, the client can be configured to prompt the user for a location.</span></span> <span data-ttu-id="25aef-122">Sin embargo, debido a que estas ubicaciones proporcionadas por el usuario no se pueden prevalidar con respecto a la guía de dirección principal (MSAG), el distribuidor de proveedores de servicios de emergencias deberá confirmar la validez de la ubicación verbalmente con la persona que realiza la llamada antes de enrutar la llamada al punto de respuesta de seguridad pública (PSAP).</span><span class="sxs-lookup"><span data-stu-id="25aef-122">However, because these user-provided locations cannot be prevalidated against the Master Street Address Guide (MSAG), the emergency services service provider dispatcher will need to confirm the validity of the location verbally with the caller before routing the call to the Public Safety Answering Point (PSAP).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="25aef-123">Los clientes de Lync de los usuarios que se conectan a la red de su organización mediante VPN pueden recoger información de direcciones IP internas, pero como estas direcciones no se pueden usar para identificar la ubicación real del usuario, es esencial que las subredes VPN se excluyan del servicio de información de ubicación.</span><span class="sxs-lookup"><span data-stu-id="25aef-123">Lync clients of users who connect to your organization’s network by using VPN can pick up internal IP address information, but because these addresses cannot be used to identify the user’s actual location, it is essential that VPN subnets are excluded from the Location Information service.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="25aef-124">**¿Desea proporcionar el enrutamiento de llamadas de emergencia a sitios fuera de Estados Unidos?**</span><span class="sxs-lookup"><span data-stu-id="25aef-124">**Do you want to provide emergency call routing to sites outside the U.S.?**</span></span>  
    <span data-ttu-id="25aef-125">Es posible que desee proporcionar enrutamiento de emergencia a áreas de su compañía que no atienda un proveedor de servicios de emergencia (por ejemplo, ubicaciones internacionales).</span><span class="sxs-lookup"><span data-stu-id="25aef-125">You may want to provide emergency routing to areas of your company not served by an emergency services service provider (for example, international locations).</span></span> <span data-ttu-id="25aef-126">Para ello, cree un nuevo sitio y, a continuación, asigne directivas de voz a los sitios que hacen referencia a un uso de RTC que enruta la llamada a través de la puerta de enlace RTC local.</span><span class="sxs-lookup"><span data-stu-id="25aef-126">To do this, create a new site, and then assign voice policies to the sites that refer to a PSTN usage that routes the call through the local PSTN gateway.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

