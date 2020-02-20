---
title: 'Lync Server 2013: configuración de troncos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring trunks
ms:assetid: 0c339511-a185-484e-94f0-dbe918b7e48a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398170(v=OCS.15)
ms:contentKeyID: 48183389
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09151bf1e5fab592f8051878bcd8218690583309
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154192"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-trunks-in-lync-server-2013"></a><span data-ttu-id="d7066-102">Configuración de troncos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7066-102">Configuring trunks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d7066-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="d7066-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="d7066-104">Como parte de la implementación de telefonía IP empresarial, puede configurar un tronco entre un servidor de mediación y uno o más de los siguientes homólogos para proporcionar conectividad de red telefónica conmutada (RTC) para clientes y dispositivos de telefonía IP empresarial en su organización:</span><span class="sxs-lookup"><span data-stu-id="d7066-104">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>

  - <span data-ttu-id="d7066-105">Conexión basada en troncos SIP para un proveedor de servicio s de telefonía</span><span class="sxs-lookup"><span data-stu-id="d7066-105">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>

  - <span data-ttu-id="d7066-106">Puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="d7066-106">PSTN gateway</span></span>

  - <span data-ttu-id="d7066-107">Central de conmutación (PBX)</span><span class="sxs-lookup"><span data-stu-id="d7066-107">Private branch exchange (PBX)</span></span>

<span data-ttu-id="d7066-108">Para obtener más información, consulte [planeación de la conectividad con RTC en Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="d7066-108">For details, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) in the Planning documentation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d7066-109">Antes de iniciar la configuración de troncos, verifique que se ha creado la topología y que el servidor de mediación y su par se han configurado y asociado entre sí.</span><span class="sxs-lookup"><span data-stu-id="d7066-109">Before you begin trunk configuration, verify that the topology has been created and that the Mediation Server and its peer have been configured and associated with one another.</span></span> <span data-ttu-id="d7066-110">Para obtener más información, consulte <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">definir una puerta de enlace en el generador de topologías en Lync Server 2013</A> en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="d7066-110">For details, see <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Define a gateway in Topology Builder in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="d7066-111">Como parte de la configuración del tronco, puede habilitar la característica de omisión de medios de Lync Server 2013, que permite que los medios omitan el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="d7066-111">As a part of trunk configuration, you can enable the Lync Server 2013 media bypass feature, which enables media to bypass the Mediation Server.</span></span> <span data-ttu-id="d7066-112">Los troncos pueden configurarse con el desvío de medios habilitado o deshabilitado, aunque le recomendamos que lo habilite.</span><span class="sxs-lookup"><span data-stu-id="d7066-112">Trunks can be configured either with or without media bypass enabled, but we strongly recommend that you enable it.</span></span> <span data-ttu-id="d7066-113">Para obtener más información, consulte <A href="lync-server-2013-planning-for-media-bypass.md">planeación de la omisión de medios en Lync Server 2013</A> en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="d7066-113">For details, see <A href="lync-server-2013-planning-for-media-bypass.md">Planning for media bypass in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d7066-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d7066-114">In This Section</span></span>

  - [<span data-ttu-id="d7066-115">Compatibilidad con varios tronco en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7066-115">Multiple trunk support in Lync Server 2013</span></span>](lync-server-2013-multiple-trunk-support.md)

  - [<span data-ttu-id="d7066-116">Enrutamiento entre tronco en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7066-116">Inter-trunk routing in Lync Server 2013</span></span>](lync-server-2013-inter-trunk-routing.md)

  - [<span data-ttu-id="d7066-117">Ver la información de configuración de tronco en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7066-117">View trunk configuration information in Lync Server 2013</span></span>](lync-server-2013-view-trunk-configuration-information.md)

  - [<span data-ttu-id="d7066-118">Configurar un tronco con la omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7066-118">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [<span data-ttu-id="d7066-119">Configurar un tronco sin omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7066-119">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)

  - [<span data-ttu-id="d7066-120">Crear una nueva colección de opciones de configuración de tronco en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7066-120">Create a new collection of trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-a-new-collection-of-trunk-configuration-settings.md)

  - [<span data-ttu-id="d7066-121">Eliminar una colección existente de opciones de configuración de tronco SIP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7066-121">Delete an existing collection of SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="d7066-122">Modificar las opciones de configuración de tronco SIP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7066-122">Modify SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-modify-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="d7066-123">Probar las opciones de configuración de tronco SIP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7066-123">Test SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-test-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="d7066-124">Ver información sobre troncos SIP individuales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7066-124">View information about individual SIP trunks in Lync Server 2013</span></span>](lync-server-2013-view-information-about-individual-sip-trunks.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d7066-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="d7066-125">See Also</span></span>


[<span data-ttu-id="d7066-126">Definir una puerta de enlace en el generador de topologías de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7066-126">Define a gateway in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-gateway-in-topology-builder.md)  


[<span data-ttu-id="d7066-127">Planeación de la conectividad con RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7066-127">Planning for PSTN connectivity in Lync Server 2013</span></span>](lync-server-2013-planning-for-pstn-connectivity.md)  
[<span data-ttu-id="d7066-128">Planeación de la omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7066-128">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

