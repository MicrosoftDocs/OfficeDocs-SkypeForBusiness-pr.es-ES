---
title: 'Lync Server 2013: implementación de telefonía IP empresarial'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Enterprise Voice
ms:assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412876(v=OCS.15)
ms:contentKeyID: 48185207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf57d55899d556ddfde633c975ae9f0516e48e14
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733630"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="52ca3-102">Implementación de telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52ca3-102">Deploying Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52ca3-103">_**Última modificación del tema:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="52ca3-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="52ca3-104">Lync Server 2013, Enterprise Voice, forma parte de la infraestructura de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="52ca3-104">Lync Server 2013, Enterprise Voice is part of the Lync Server 2013 infrastructure.</span></span>

<span data-ttu-id="52ca3-105">La implementación de la telefonía IP empresarial requiere que:</span><span class="sxs-lookup"><span data-stu-id="52ca3-105">Deploying Enterprise Voice requires that you:</span></span>

<div id="sectionSection0" class="section">

1.  <span data-ttu-id="52ca3-106">Revise la sección [planear la telefonía IP empresarial en Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) de la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="52ca3-106">Review the [Planning for Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) section of the Planning documentation.</span></span>

2.  <span data-ttu-id="52ca3-107">Finalizar planes de características y componentes para implementar con esta carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="52ca3-107">Finalize plans for features and components to deploy with this workload.</span></span>

3.  <span data-ttu-id="52ca3-108">Ejecute la herramienta de planeación para diseñar una topología que refleje las decisiones de implementación.</span><span class="sxs-lookup"><span data-stu-id="52ca3-108">Run Planning Tool to design a topology that reflects your deployment decisions.</span></span>

4.  <span data-ttu-id="52ca3-109">Abra el diseño de topología en el generador de topologías, como se describe en [definir y configurar la topología de Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="52ca3-109">Open the topology design in Topology Builder, as described in [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="52ca3-110">La instalación de Topology Builder forma parte del proceso de implementación del grupo interno.</span><span class="sxs-lookup"><span data-stu-id="52ca3-110">Installation of Topology Builder is part of the deployment process for the internal pool.</span></span> <span data-ttu-id="52ca3-111">Para obtener más información, vea <A href="lync-server-2013-install-lync-server-administrative-tools.md">instalar las herramientas administrativas 2013 de Lync Server</A> en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="52ca3-111">For details, see <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 administrative tools</A> in the Deployment documentation.</span></span>

    
    </div>

<span data-ttu-id="52ca3-112">Además, debe haber implementado ya implementado Lync Server, Enterprise Edition en sitios centrales y sitios de sucursales que corresponden a la topología de referencia que elige implementar.</span><span class="sxs-lookup"><span data-stu-id="52ca3-112">Additionally, you must have already deployed Lync Server, Enterprise Edition at central sites and branch sites that correspond to the reference topology that you choose to deploy.</span></span> <span data-ttu-id="52ca3-113">No puede implementar componentes de voz empresarial hasta que haya definido, publicado e instalado archivos para al menos un grupo interno, y debe usar el generador de topología para definir y publicar un grupo interno.</span><span class="sxs-lookup"><span data-stu-id="52ca3-113">You can’t deploy Enterprise Voice components until you have defined, published, and installed files for at least one internal pool, and you must use Topology Builder to define and publish an internal pool.</span></span>

</div>

<div id="sectionSection1" class="section">

<div class="subSection">

<span data-ttu-id="52ca3-114">Para ver las topologías de referencia con ejemplos de dónde se pueden implementar los roles de servidor de telefonía IP (y su relación entre sí y otros roles de servidor de Lync Server 2013), vea [topologías de referencia en Lync server 2013](lync-server-2013-reference-topologies.md) en la documentación de planificación.</span><span class="sxs-lookup"><span data-stu-id="52ca3-114">To view reference topologies with examples of where Enterprise Voice server roles can be deployed (and their relationship to one another and other Lync Server 2013 server roles), see [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md) in the Planning documentation.</span></span>

<span data-ttu-id="52ca3-115">Para ver una topología de referencia que ilustre y explique una implementación de control de admisión de llamadas de ejemplo, incluidas las regiones de red, los sitios de red y las subredes, vea [ejemplo: recopilar los requisitos para el control de admisión de llamadas en Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="52ca3-115">To view a reference topology that illustrates and explains a sample call admission control deployment, including network regions, network sites, and subnets, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

</div>

</div>

<div id="sectionSection2" class="section">

<div>


> [!IMPORTANT]  
> <span data-ttu-id="52ca3-116">Para implementar la telefonía IP empresarial en un sitio central, siga leyendo los temas de esta sección.</span><span class="sxs-lookup"><span data-stu-id="52ca3-116">To deploy Enterprise Voice at a central site, continue reading the topics in this section.</span></span> <span data-ttu-id="52ca3-117">Para implementar la telefonía IP empresarial en un sitio de sucursal, vaya a <A href="lync-server-2013-deploying-branch-sites.md">implementar sitios de sucursales en Lync Server 2013</A> en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="52ca3-117">To deploy Enterprise Voice at a branch site, skip to <A href="lync-server-2013-deploying-branch-sites.md">Deploying branch sites in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="52ca3-118">La documentación de esta sección incluye procedimientos para implementaciones en las que se instala un servidor de mediación en cada servidor front-end o servidor Standard Edition, como se recomienda, y también para implementaciones con un grupo de servidores de mediación independiente.</span><span class="sxs-lookup"><span data-stu-id="52ca3-118">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="52ca3-119">Puede omitir el siguiente contenido si usó el generador de topología para definir y publicar una topología que collocates un servidor de mediación en cada servidor front-end o un servidor Standard Edition, ya que el Asistente para la implementación ya instaló automáticamente los archivos para Servidor de mediación al instalar archivos para el grupo de servidores front-end o el servidor Standard Edition:</span><span class="sxs-lookup"><span data-stu-id="52ca3-119">You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>

  - [<span data-ttu-id="52ca3-120">Configuración de troncos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52ca3-120">Configuring trunks in Lync Server 2013</span></span>](lync-server-2013-configuring-trunks.md)

<span data-ttu-id="52ca3-121">Si usó el generador de topología para definir y publicar un servidor de mediación en un grupo independiente, puede usar el siguiente contenido:</span><span class="sxs-lookup"><span data-stu-id="52ca3-121">If you used Topology Builder to define and publish a Mediation Server in a stand-alone pool, you can use the following content:</span></span>

  - <span data-ttu-id="52ca3-122">Compruebe que su topología cumpla los requisitos previos del software y el entorno, según se describe en [requisitos previos de telefonía IP empresarial para Lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="52ca3-122">Verify that your topology meets the software and environment prerequisites, as described in [Enterprise Voice prerequisites for Lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md).</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="52ca3-123">En esta sección</span><span class="sxs-lookup"><span data-stu-id="52ca3-123">In This Section</span></span>

  - <span></span>  
    [<span data-ttu-id="52ca3-124">Requisitos previos de la telefonía IP empresarial para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52ca3-124">Enterprise Voice prerequisites for Lync Server 2013</span></span>](lync-server-2013-enterprise-voice-prerequisites.md)

  - <span></span>  
    [<span data-ttu-id="52ca3-125">Implementar servidores de mediación y definir servidores del mismo nivel en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52ca3-125">Deploying Mediation Servers and defining peers in Lync Server 2013</span></span>](lync-server-2013-deploying-mediation-servers-and-defining-peers.md)

  - <span></span>  
    [<span data-ttu-id="52ca3-126">Configuración de troncos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52ca3-126">Configuring trunks in Lync Server 2013</span></span>](lync-server-2013-configuring-trunks.md)

  - <span></span>  
    [<span data-ttu-id="52ca3-127">Configurar planes de marcado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52ca3-127">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)

  - <span></span>  
    [<span data-ttu-id="52ca3-128">Configuración de directivas de voz, registros de uso de RTC y rutas de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52ca3-128">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)

  - <span></span>  
    [<span data-ttu-id="52ca3-129">Exportar e importar la configuración del enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52ca3-129">Exporting and importing voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - <span></span>  
    [<span data-ttu-id="52ca3-130">Probar el enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52ca3-130">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)

  - <span></span>  
    [<span data-ttu-id="52ca3-131">Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52ca3-131">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - <span></span>  
    [<span data-ttu-id="52ca3-132">Implementar la mensajería unificada de Exchange local para proporcionar correo de voz de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52ca3-132">Deploying on-premises Exchange UM to provide Lync Server 2013 voice mail</span></span>](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)

  - <span></span>  
    [<span data-ttu-id="52ca3-133">Proporcionar correo de voz a usuarios de Lync Server 2013 en la mensajería unificada de Exchange hospedada</span><span class="sxs-lookup"><span data-stu-id="52ca3-133">Providing Lync Server 2013 users voice mail on hosted Exchange UM</span></span>](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)

  - <span></span>  
    [<span data-ttu-id="52ca3-134">Configuración de la integración de Lync Server 2013 local con Exchange Online</span><span class="sxs-lookup"><span data-stu-id="52ca3-134">Configuring on-premises Lync Server 2013 integration with Exchange Online</span></span>](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)

  - <span></span>  
    [<span data-ttu-id="52ca3-135">Implementación de características avanzadas de telefonía empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52ca3-135">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)
    
      - [<span data-ttu-id="52ca3-136">Acerca de las regiones de red, sitios y subredes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52ca3-136">About network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-about-network-regions-sites-and-subnets.md)
    
      - [<span data-ttu-id="52ca3-137">Crear o modificar una región de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52ca3-137">Create or modify a network region in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-region.md)
    
      - [<span data-ttu-id="52ca3-138">Crear o modificar un sitio de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52ca3-138">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)
    
      - [<span data-ttu-id="52ca3-139">Asociar una subred a un sitio de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52ca3-139">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)
    
      - [<span data-ttu-id="52ca3-140">Configurar el control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52ca3-140">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)
    
      - [<span data-ttu-id="52ca3-141">Configurar 9-1-1 mejorado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52ca3-141">Configure Enhanced 9-1-1 in Lync Server 2013</span></span>](lync-server-2013-configure-enhanced-9-1-1.md)
    
      - [<span data-ttu-id="52ca3-142">Configurar la omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52ca3-142">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)

  - <span></span>  
    [<span data-ttu-id="52ca3-143">Habilitar usuarios para telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52ca3-143">Enable users for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-enterprise-voice.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="52ca3-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="52ca3-144">See Also</span></span>


[<span data-ttu-id="52ca3-145">Implementación de sitios de sucursales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52ca3-145">Deploying branch sites in Lync Server 2013</span></span>](lync-server-2013-deploying-branch-sites.md)  
[<span data-ttu-id="52ca3-146">Configurar una conferencia de acceso telefónico local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52ca3-146">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)  
[<span data-ttu-id="52ca3-147">Configurar el estacionamiento de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52ca3-147">Configuring Call Park in Lync Server 2013</span></span>](lync-server-2013-configuring-call-park.md)  
[<span data-ttu-id="52ca3-148">Configuración de anuncios para números sin asignar en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52ca3-148">Configuring announcements for unassigned numbers in Lync Server 2013</span></span>](lync-server-2013-configuring-announcements-for-unassigned-numbers.md)  
[<span data-ttu-id="52ca3-149">Implementación de la supervisión en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52ca3-149">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

