---
title: 'Lync Server 2013: Configuración de troncos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring trunks
ms:assetid: 0c339511-a185-484e-94f0-dbe918b7e48a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398170(v=OCS.15)
ms:contentKeyID: 48183389
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d40a290f75ae48b73a4695e04ea2934b0c4d695
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842165"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-trunks-in-lync-server-2013"></a><span data-ttu-id="c7c55-102">Configuración de troncos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7c55-102">Configuring trunks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7c55-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c7c55-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c7c55-104">Como parte de la implementación de telefonía IP empresarial, puede configurar un tronco entre un servidor de mediación y uno o más de los siguientes elementos para proporcionar conectividad de red telefónica conmutada (RTC) pública para los clientes y dispositivos de voz de su organización:</span><span class="sxs-lookup"><span data-stu-id="c7c55-104">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>

  - <span data-ttu-id="c7c55-105">Conexión basada en troncos SIP para un proveedor de servicio s de telefonía</span><span class="sxs-lookup"><span data-stu-id="c7c55-105">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>

  - <span data-ttu-id="c7c55-106">Puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="c7c55-106">PSTN gateway</span></span>

  - <span data-ttu-id="c7c55-107">Central de conmutación (PBX)</span><span class="sxs-lookup"><span data-stu-id="c7c55-107">Private branch exchange (PBX)</span></span>

<span data-ttu-id="c7c55-108">Para obtener más información, consulte [planificación de la conectividad RTC en Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="c7c55-108">For details, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) in the Planning documentation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c7c55-109">Antes de comenzar con la configuración troncal, verifique que se haya creado la topología y que el servidor de mediación y sus pares se hayan configurado y asociado entre sí.</span><span class="sxs-lookup"><span data-stu-id="c7c55-109">Before you begin trunk configuration, verify that the topology has been created and that the Mediation Server and its peer have been configured and associated with one another.</span></span> <span data-ttu-id="c7c55-110">Para obtener más información, vea <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">definir una puerta de enlace en el generador de topologías de Lync Server 2013</A> en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="c7c55-110">For details, see <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Define a gateway in Topology Builder in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="c7c55-111">Como parte de la configuración troncal, puede habilitar la característica de omisión de medios de Lync Server 2013, que permite a los medios omitir el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="c7c55-111">As a part of trunk configuration, you can enable the Lync Server 2013 media bypass feature, which enables media to bypass the Mediation Server.</span></span> <span data-ttu-id="c7c55-112">Los troncos se pueden configurar con o sin omisión de medios habilitados, pero le recomendamos encarecidamente que lo habilite.</span><span class="sxs-lookup"><span data-stu-id="c7c55-112">Trunks can be configured either with or without media bypass enabled, but we strongly recommend that you enable it.</span></span> <span data-ttu-id="c7c55-113">Para obtener más información, consulte <A href="lync-server-2013-planning-for-media-bypass.md">planificación de la omisión de medios en Lync Server 2013</A> en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="c7c55-113">For details, see <A href="lync-server-2013-planning-for-media-bypass.md">Planning for media bypass in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c7c55-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c7c55-114">In This Section</span></span>

  - [<span data-ttu-id="c7c55-115">Compatibilidad con varios troncales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7c55-115">Multiple trunk support in Lync Server 2013</span></span>](lync-server-2013-multiple-trunk-support.md)

  - [<span data-ttu-id="c7c55-116">Enrutamiento entre troncales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7c55-116">Inter-trunk routing in Lync Server 2013</span></span>](lync-server-2013-inter-trunk-routing.md)

  - [<span data-ttu-id="c7c55-117">Ver la información de configuración troncal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7c55-117">View trunk configuration information in Lync Server 2013</span></span>](lync-server-2013-view-trunk-configuration-information.md)

  - [<span data-ttu-id="c7c55-118">Configure a trunk with media bypass in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7c55-118">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [<span data-ttu-id="c7c55-119">Configurar un tronco sin omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7c55-119">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)

  - [<span data-ttu-id="c7c55-120">Crear una nueva colección de opciones de configuración de troncal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7c55-120">Create a new collection of trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-a-new-collection-of-trunk-configuration-settings.md)

  - [<span data-ttu-id="c7c55-121">Eliminar una colección existente de parámetros de configuración del tronco de SIP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7c55-121">Delete an existing collection of SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="c7c55-122">Modificar la configuración de los enlaces de SIP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7c55-122">Modify SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-modify-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="c7c55-123">Probar la configuración del tronco del SIP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7c55-123">Test SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-test-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="c7c55-124">Ver información sobre los troncos SIP individuales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7c55-124">View information about individual SIP trunks in Lync Server 2013</span></span>](lync-server-2013-view-information-about-individual-sip-trunks.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c7c55-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="c7c55-125">See Also</span></span>


[<span data-ttu-id="c7c55-126">Definir una puerta de enlace en el generador de topología de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7c55-126">Define a gateway in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-gateway-in-topology-builder.md)  


[<span data-ttu-id="c7c55-127">Planificación de la conectividad RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7c55-127">Planning for PSTN connectivity in Lync Server 2013</span></span>](lync-server-2013-planning-for-pstn-connectivity.md)  
[<span data-ttu-id="c7c55-128">Planificar la omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7c55-128">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

