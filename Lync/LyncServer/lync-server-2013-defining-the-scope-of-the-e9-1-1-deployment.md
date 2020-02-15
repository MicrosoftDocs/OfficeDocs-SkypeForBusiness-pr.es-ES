---
title: 'Lync Server 2013: definir el ámbito de la implementación de E9-1-1'
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
ms.openlocfilehash: be9dee7f4e79492e62e04441b6fa56d4e04ff45a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043782"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-scope-of-the-e9-1-1-deployment-in-lync-server-2013"></a><span data-ttu-id="2c58a-102">Definir el ámbito de la implementación de E9-1-1 en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c58a-102">Defining the scope of the E9-1-1 deployment in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c58a-103">_**Última modificación del tema:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="2c58a-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="2c58a-104">Antes de configurar Microsoft Lync Server 2013 para E9-1-1, debe planear la implementación de E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="2c58a-104">Before you configure Microsoft Lync Server 2013 for E9-1-1, you need to plan your E9-1-1 deployment.</span></span> <span data-ttu-id="2c58a-105">Algunas de las preguntas que se deben tener en cuenta son:</span><span class="sxs-lookup"><span data-stu-id="2c58a-105">Some of the questions to consider include:</span></span>

  - <span data-ttu-id="2c58a-106">**¿Cuáles son las obligaciones legales y la Directiva de su organización con respecto a E9-1-1?**</span><span class="sxs-lookup"><span data-stu-id="2c58a-106">**What are your organization’s policy and legal obligations with regard to E9-1-1?**</span></span>  
    <span data-ttu-id="2c58a-107">Los requisitos legales de E9-1-1 para PBX (llamados sistemas telefónicos de varias líneas o MLTS, en lenguaje E9-1-1) difieren de un estado a un estado.</span><span class="sxs-lookup"><span data-stu-id="2c58a-107">E9-1-1 legal requirements for PBXs (called Multi-line Telephone Systems, or MLTS, in E9-1-1 parlance) differ from state to state.</span></span> <span data-ttu-id="2c58a-108">Debe consultar a su equipo jurídico para conocer las obligaciones que se pueden aplicar a su implementación de Lync Server en las ubicaciones geográficas pertinentes.</span><span class="sxs-lookup"><span data-stu-id="2c58a-108">You should consult with your legal team to understand the obligations that may apply to your deployment of Lync Server in your relevant geographies.</span></span>

<!-- end list -->

  - <span data-ttu-id="2c58a-109">**¿Qué áreas de la empresa deben estar habilitadas para E9-1-1?**</span><span class="sxs-lookup"><span data-stu-id="2c58a-109">**What areas within your enterprise need to be enabled for E9-1-1?**</span></span>  
    <span data-ttu-id="2c58a-110">Puede habilitar E9-1-1 para toda la empresa o para ubicaciones seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="2c58a-110">You can enable E9-1-1 for the entire enterprise or for selected locations.</span></span> <span data-ttu-id="2c58a-111">Por ejemplo, puede que tenga que variar E9-1-1 requisitos para oficinas en diferentes Estados o puede que desee excluir sitios de fuera de Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="2c58a-111">For example, you may have varying E9-1-1 requirements for offices in different states, or you may want to exclude sites outside the U.S.</span></span>

<!-- end list -->

  - <span data-ttu-id="2c58a-112">**¿Cómo implementará E9-1-1 en los sitios de sucursal?**</span><span class="sxs-lookup"><span data-stu-id="2c58a-112">**How will you deploy E9-1-1 to branch sites?**</span></span>  
    <span data-ttu-id="2c58a-113">La resistencia de voz es un concepto importante que debe comprender al implementar E9-1-1 en un sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="2c58a-113">Voice resiliency is an important concept to understand when deploying E9-1-1 at a branch site.</span></span> <span data-ttu-id="2c58a-114">Si tiene troncos E-9-1-1 SIP centralizados y se produce una interrupción de la WAN, es posible que los clientes que inicien sesión no puedan obtener una ubicación del servicio de información de ubicaciones o para conectarse al proveedor de servicios de emergencias.</span><span class="sxs-lookup"><span data-stu-id="2c58a-114">If you have centralized E-9-1-1 SIP trunks and a WAN outage occurs, clients signing in may not be able to obtain a location from Location Information service or to connect to the emergency services service provider.</span></span> <span data-ttu-id="2c58a-115">Lync Server ofrece varias estrategias para controlar la resistencia de voz en las sucursales, entre las que se incluyen: tener redes de datos resistentes, implementar un tronco SIP en cada sucursal o presionar llamadas de emergencia a la puerta de enlace local durante las interrupciones.</span><span class="sxs-lookup"><span data-stu-id="2c58a-115">Lync Server provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing emergency calls out to the local gateway during outages.</span></span> <span data-ttu-id="2c58a-116">Para obtener más información, consulte [Planning for Branch-site Voice Resiliency en Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span><span class="sxs-lookup"><span data-stu-id="2c58a-116">For details, see [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span></span>

<!-- end list -->

  - <span data-ttu-id="2c58a-117">**¿Se habilitará E9-1-1 para los usuarios que trabajan fuera de la red?**</span><span class="sxs-lookup"><span data-stu-id="2c58a-117">**Will you enable E9-1-1 for users working outside the network?**</span></span>  
    <span data-ttu-id="2c58a-118">La adquisición de ubicación automática solo está disponible para los clientes que se encuentran dentro de la red de la organización, por lo que su organización debe decidir si será compatible con las llamadas de E9-1-1 realizadas desde los clientes de Lync mientras se encuentran fuera del entorno.</span><span class="sxs-lookup"><span data-stu-id="2c58a-118">Automatic location acquisition is available only for clients located inside the organization’s network, so your organization needs to decide whether it will support E9-1-1 calls made from Lync clients while off-premises.</span></span> <span data-ttu-id="2c58a-119">Por ejemplo, ¿permitirá que los usuarios realicen llamadas de emergencia si están trabajando desde casa o desde un sitio del cliente?</span><span class="sxs-lookup"><span data-stu-id="2c58a-119">For example, will you enable users to place emergency calls if they are working from home or from a customer site?</span></span> <span data-ttu-id="2c58a-120">Si un cliente se encuentra fuera de la red de la empresa, se puede configurar el cliente para que solicite una ubicación al usuario.</span><span class="sxs-lookup"><span data-stu-id="2c58a-120">If a client is located outside the enterprise network, the client can be configured to prompt the user for a location.</span></span> <span data-ttu-id="2c58a-121">Sin embargo, debido a que estas ubicaciones proporcionadas por el usuario no se pueden prevalidar con respecto a la guía de dirección principal (MSAG), el distribuidor de proveedores de servicios de emergencias deberá confirmar la validez de la ubicación verbalmente con la persona que realiza la llamada antes de la distribución la llamada al punto de respuesta de seguridad pública (PSAP).</span><span class="sxs-lookup"><span data-stu-id="2c58a-121">However, because these user-provided locations cannot be prevalidated against the Master Street Address Guide (MSAG), the emergency services service provider dispatcher will need to confirm the validity of the location verbally with the caller before routing the call to the Public Safety Answering Point (PSAP).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2c58a-122">Los clientes de Lync de los usuarios que se conectan a la red de su organización mediante VPN pueden recoger la información de dirección IP interna, pero debido a que estas direcciones no se pueden usar para identificar la ubicación real del usuario, es esencial que las subredes VPN se excluyan del Servicio de información de ubicación.</span><span class="sxs-lookup"><span data-stu-id="2c58a-122">Lync clients of users who connect to your organization’s network by using VPN can pick up internal IP address information, but because these addresses cannot be used to identify the user’s actual location, it is essential that VPN subnets are excluded from the Location Information service.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="2c58a-123">**¿Desea proporcionar el enrutamiento de llamadas de emergencia a sitios fuera de Estados Unidos?**</span><span class="sxs-lookup"><span data-stu-id="2c58a-123">**Do you want to provide emergency call routing to sites outside the U.S.?**</span></span>  
    <span data-ttu-id="2c58a-124">Es posible que desee proporcionar enrutamiento de emergencia a áreas de su compañía que no atienda un proveedor de servicios de emergencia (por ejemplo, ubicaciones internacionales).</span><span class="sxs-lookup"><span data-stu-id="2c58a-124">You may want to provide emergency routing to areas of your company not served by an emergency services service provider (for example, international locations).</span></span> <span data-ttu-id="2c58a-125">Para ello, cree un nuevo sitio y, a continuación, asigne directivas de voz a los sitios que hacen referencia a un uso de RTC que enruta la llamada a través de la puerta de enlace RTC local.</span><span class="sxs-lookup"><span data-stu-id="2c58a-125">To do this, create a new site, and then assign voice policies to the sites that refer to a PSTN usage that routes the call through the local PSTN gateway.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

