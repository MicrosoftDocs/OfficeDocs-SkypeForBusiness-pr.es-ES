---
title: 'Lync Server 2013: configuración de red para las características de telefonía avanzada empresarial'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network settings for the advanced Enterprise Voice features
ms:assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398637(v=OCS.15)
ms:contentKeyID: 48184632
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1ce4983f7744158c9c9ff56cdfdde818fdc8e14
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765881"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-lync-server-2013"></a><span data-ttu-id="663d4-102">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="663d4-102">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="663d4-103">_**Última modificación del tema:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="663d4-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="663d4-104">Lync Server tiene tres características avanzadas de Enterprise Voice: control de admisión de llamadas (CAC), servicios de emergencia (E9-1-1) y omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="663d4-104">Lync Server has three advanced Enterprise Voice features: call admission control (CAC), emergency services (E9-1-1), and media bypass.</span></span> <span data-ttu-id="663d4-105">Estas características comparten determinados requisitos de configuración para regiones de red, sitios de red y Asociación de cada subred en la topología de Lync Server con un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="663d4-105">These features share certain configuration requirements for network regions, network sites, and association of each subnet in the Lync Server topology with a network site.</span></span> <span data-ttu-id="663d4-106">Para obtener más información sobre cómo planear la implementación de estas características, consulte:</span><span class="sxs-lookup"><span data-stu-id="663d4-106">For details about planning for deployment of these features, see:</span></span>

  - [<span data-ttu-id="663d4-107">Planear el control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="663d4-107">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)

  - [<span data-ttu-id="663d4-108">Planeación de los servicios de emergencia (E9-1-1) en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="663d4-108">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [<span data-ttu-id="663d4-109">Planificar la omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="663d4-109">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)

<span data-ttu-id="663d4-110">Para obtener detalles sobre la implementación de cada una de estas características, consulte [implementar características avanzadas de telefonía empresarial en Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="663d4-110">For details about deploying each of these features, see [Deploying advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md) in the Deployment documentation.</span></span>

<span data-ttu-id="663d4-111">Este tema proporciona una descripción general de los requisitos de configuración comunes a las tres características avanzadas de telefonía empresarial.</span><span class="sxs-lookup"><span data-stu-id="663d4-111">This topic provides an overview of the configuration requirements that are common to all three advanced Enterprise Voice features.</span></span>

<div>

## <a name="network-regions"></a><span data-ttu-id="663d4-112">Regiones de red</span><span class="sxs-lookup"><span data-stu-id="663d4-112">Network Regions</span></span>

<span data-ttu-id="663d4-113">Una región de red es un concentrador de red o una red troncal de red que solo se usa en la configuración del servicio de control de admisión de llamadas (CAC), E9-1-1 y la omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="663d4-113">A network region is a network hub or network backbone used only in the configuration of call admission control (CAC), E9-1-1, and media bypass.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="663d4-114">Las regiones de red no son las mismas que las regiones de conferencia de acceso telefónico local de Lync Server, que son necesarias para asociar los números de acceso de las conferencias de acceso telefónico local a uno o varios planes de marcado de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="663d4-114">Network regions are not the same as Lync Server dial-in conferencing regions, which are required to associate dial-in conferencing access numbers with one or more Lync Server dial plans.</span></span> <span data-ttu-id="663d4-115">Para obtener más información sobre las regiones de conferencia de acceso telefónico local, consulte <A href="lync-server-2013-dial-in-conferencing-requirements.md">requisitos de conferencia de acceso telefónico local en Lync Server 2013</A> en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="663d4-115">For details about dial-in conferencing regions, see <A href="lync-server-2013-dial-in-conferencing-requirements.md">Dial-in conferencing requirements in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<span data-ttu-id="663d4-116">CAC requiere que cada región de la red tenga un sitio de Lync Server central asociado, que administra el tráfico multimedia dentro de la región (es decir, toma decisiones basadas en las directivas que haya configurado, sobre si una sesión de audio o vídeo en tiempo real puede establecerse).</span><span class="sxs-lookup"><span data-stu-id="663d4-116">CAC requires that every network region have an associated Lync Server central site, which manages media traffic within the region (that is, it makes decisions based on policies that you have configured, regarding whether or not a real-time audio or video session can be established).</span></span> <span data-ttu-id="663d4-117">Los sitios centrales de Lync Server no representan ubicaciones geográficas, sino grupos lógicos de servidores que están configurados como un grupo o un conjunto de grupos.</span><span class="sxs-lookup"><span data-stu-id="663d4-117">Lync Server central sites do not represent geographical locations, but rather logical groups of servers that are configured as a pool or a set of pools.</span></span> <span data-ttu-id="663d4-118">Para obtener más información sobre los sitios centrales, consulte [topologías de referencia en Lync Server 2013](lync-server-2013-reference-topologies.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="663d4-118">For details about central sites, see [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md) in the Planning documentation.</span></span> <span data-ttu-id="663d4-119">Consulte también las [topologías compatibles en Lync Server 2013](lync-server-2013-supported-topologies.md) en la documentación de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="663d4-119">Also see [Supported topologies in Lync Server 2013](lync-server-2013-supported-topologies.md) in the Supportability documentation.</span></span>

<span data-ttu-id="663d4-120">Para configurar una región de red, puede usar la pestaña **regiones** de la sección **configuración de red** del panel de control de Lync Server o ejecutar los cmdlets del shell de administración de Lync Server **New-CsNetworkRegion** o **set-CsNetworkRegion** .</span><span class="sxs-lookup"><span data-stu-id="663d4-120">To configure a network region, you can either use the **Regions** tab on the **Network Configuration** section of Lync Server Control Panel, or run the **New-CsNetworkRegion** or **Set-CsNetworkRegion** Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="663d4-121">Para obtener instrucciones, consulte [crear o modificar una región de red en Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) en la documentación de implementación o consulte la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="663d4-121">For instructions, see [Create or modify a network region in Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

<span data-ttu-id="663d4-122">Las mismas definiciones de regiones de red son compartidas por las tres características avanzadas de Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="663d4-122">The same network region definitions are shared by all three advanced Enterprise Voice features.</span></span> <span data-ttu-id="663d4-123">Si ya has creado las regiones de red de una característica, no necesitarás crear regiones de red para las otras características.</span><span class="sxs-lookup"><span data-stu-id="663d4-123">If you have already created network regions for one feature, you do not need to create new network regions for the other features.</span></span> <span data-ttu-id="663d4-124">Pero, es posible que necesites modificar una definición de región de red existente para aplicar una configuración específica de una característica.</span><span class="sxs-lookup"><span data-stu-id="663d4-124">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="663d4-125">Por ejemplo, si has creado las regiones de red de E9-1-1 (que no necesitan tener asociado un sitio central) y, más tarde, implementas el servicio de control de admisión de llamadas, necesitas modificar cada una de las definiciones de las regiones de red para especificar un sitio central.</span><span class="sxs-lookup"><span data-stu-id="663d4-125">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and, later, you deploy call admission control, you must modify each of the network region definitions to specify a central site.</span></span>

<span data-ttu-id="663d4-126">Para asociar un sitio central de Lync Server a una región de red, especifique el nombre del sitio central, ya sea mediante la sección de **configuración de red** del panel de control de Lync Server, o ejecutando los cmdlets de Shell de administración de Lync Server **New-CsNetworkRegion** o **set-CsNetworkRegion** .</span><span class="sxs-lookup"><span data-stu-id="663d4-126">To associate a Lync Server central site with a network region, you specify the central site name, either by using the **Network Configuration** section of Lync Server Control Panel, or by running the **New-CsNetworkRegion** or **Set-CsNetworkRegion** Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="663d4-127">Para obtener instrucciones, consulte [crear o modificar una región de red en Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) en la documentación de implementación o consulte la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="663d4-127">For instructions, see [Create or modify a network region in Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="network-sites"></a><span data-ttu-id="663d4-128">Sitios de red</span><span class="sxs-lookup"><span data-stu-id="663d4-128">Network Sites</span></span>

<span data-ttu-id="663d4-p107">Un sitio de red representa una ubicación geográfica, como una oficina de sucursal, una oficina regional o una oficina principal. Cada sitio de red necesita asociarse con una región de red determinada.</span><span class="sxs-lookup"><span data-stu-id="663d4-p107">A network site represents a geographical location, such as a branch office, a regional office, or a main office. Each network site must be associated with a specific network region.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="663d4-131">Los sitios de red solo se usan con las características avanzadas de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="663d4-131">Network sites are used only by the advanced Enterprise Voice features.</span></span> <span data-ttu-id="663d4-132">No son iguales a los sitios de sucursales que se configuran en la topología de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="663d4-132">They are not the same as the branch sites that you configure in your Lync Server topology.</span></span> <span data-ttu-id="663d4-133">Para obtener más información sobre sitios de sucursales, consulte <A href="lync-server-2013-reference-topologies.md">topologías de referencia en Lync Server 2013</A> en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="663d4-133">For details about branch sites, see <A href="lync-server-2013-reference-topologies.md">Reference topologies in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="663d4-134">Consulte también las <A href="lync-server-2013-supported-topologies.md">topologías compatibles en Lync Server 2013</A> en la documentación de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="663d4-134">Also see <A href="lync-server-2013-supported-topologies.md">Supported topologies in Lync Server 2013</A> in the Supportability documentation.</span></span>



</div>

<span data-ttu-id="663d4-135">Para configurar un sitio de red y asociarlo a una región de red, puede usar la sección de **configuración de red** del panel de control de Lync Server o ejecutar el shell de administración de Lync Server **New-CsNetworkSite** o **set-CsNetworkSite** .</span><span class="sxs-lookup"><span data-stu-id="663d4-135">To configure a network site and associate it with a network region, you can either use the **Network Configuration** section of Lync Server Control Panel, or run the Lync Server Management Shell **New-CsNetworkSite** or **Set-CsNetworkSite** cmdlets.</span></span> <span data-ttu-id="663d4-136">Para obtener más información, vea [crear o modificar un sitio de red en Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md) en la documentación de implementación o consulte la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="663d4-136">For details, see [Create or modify a network site in Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="identify-ip-subnets"></a><span data-ttu-id="663d4-137">Identificar subredes IP</span><span class="sxs-lookup"><span data-stu-id="663d4-137">Identify IP Subnets</span></span>

<span data-ttu-id="663d4-p110">Para cada sitio de red, tendrás que trabajar con el administrador de la red para determinar qué subredes IP están asignadas a cada sitio de red. Si el administrador de la red ya ha organizado las subredes IP en regiones de red y sitios de red, tu trabajo se habrá simplificado en gran medida.</span><span class="sxs-lookup"><span data-stu-id="663d4-p110">For each network site, you will need to work with your network administrator to determine which IP subnets are assigned to each network site. If your network administrator has already organized the IP subnets into network regions and network sites, then your work is significantly simplified.</span></span>

<span data-ttu-id="663d4-p111">Por ejemplo, el sitio Nueva York de la región Norteamérica puede tener asignadas las siguientes subredes IP: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Si Alberto, que normalmente trabaja en Detroit, viaja a la oficina de Nueva York para recibir formación, y enciende su PC y se conecta a la red, su PC obtendrá una dirección IP de uno de los cuatro rangos asignados a Nueva York, por ejemplo, 172.29.80.103.</span><span class="sxs-lookup"><span data-stu-id="663d4-p111">For example, the New York site in the North America region can be assigned the following IP subnets: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. If Bob, who usually works in Detroit, travels to the New York office for training, turns on his computer and connects to the network, his computer will get an IP address in one of the four ranges that are allocated for New York—for example, 172.29.80.103.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="663d4-142">Las subredes IP especificadas durante la configuración de red del servidor necesitan coincidir con el formato que proporcionan los equipos cliente para que se puedan usar adecuadamente para la omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="663d4-142">The IP subnets specified during network configuration on the server must match the format that is provided by client computers in order to be properly used for media bypass.</span></span> <span data-ttu-id="663d4-143">Un cliente de Lync toma su dirección IP local y enmascara la dirección IP con la máscara de subred asociada.</span><span class="sxs-lookup"><span data-stu-id="663d4-143">A Lync client takes its local IP address and masks the IP address with the associated subnet mask.</span></span> <span data-ttu-id="663d4-144">Al determinar el identificador de omisión asociado a cada cliente, el registrador comparará la lista de subredes IP asociadas con cada sitio de red con la subred indicada por el cliente para comprobar que coincidan exactamente.</span><span class="sxs-lookup"><span data-stu-id="663d4-144">When determining the bypass ID associated with each client, the Registrar will compare the list of IP subnets associated with each network site against the subnet that is provided by the client for an exact match.</span></span> <span data-ttu-id="663d4-145">Por este motivo, es importante que las subredes introducidas durante la configuración de la red del servidor sean subredes reales y no virtuales.</span><span class="sxs-lookup"><span data-stu-id="663d4-145">For this reason, it is important that subnets entered during network configuration on the server are actual subnets instead of virtual subnets.</span></span> <span data-ttu-id="663d4-146">(Si implementas el servicio de control de admisión de llamadas, pero no la omisión de medios, el servicio de control de admisión de llamadas funcionará correctamente incluso aunque configures subredes virtuales).</span><span class="sxs-lookup"><span data-stu-id="663d4-146">(If you deploy call admission control, but not media bypass, call admission control will function properly even if you configure virtual subnets.)</span></span><BR><span data-ttu-id="663d4-147">Por ejemplo, si un cliente de Lync inicia sesión en un equipo con una dirección IP de 172.29.81.57 con una máscara de subred IP 255.255.255.0, se solicitará el identificador de omisión asociado a la 172.29.81.0 de subred.</span><span class="sxs-lookup"><span data-stu-id="663d4-147">For example, if a Lync client signs in on a computer with an IP address of 172.29.81.57 with an IP subnet mask of 255.255.255.0, it will request the bypass ID that is associated with subnet 172.29.81.0.</span></span> <span data-ttu-id="663d4-148">Si la red se define como 172.29.0.0/16, aunque el cliente pertenezca a una subred virtual, el registrador no lo considerará una coincidencia porque el registrador está buscando específicamente la subred 172.29.81.0.</span><span class="sxs-lookup"><span data-stu-id="663d4-148">If the subnet is defined as 172.29.0.0/16, although the client belongs to the virtual subnet, the Registrar will not consider this a match because the Registrar is specifically looking for subnet 172.29.81.0.</span></span> <span data-ttu-id="663d4-149">Por lo tanto, es importante que el administrador escriba las subredes exactamente como se proporciona en los clientes de Lync (que se aprovisionan con subredes durante la configuración de red, ya sea estáticamente o mediante el protocolo de configuración dinámica de host (DHCP)).</span><span class="sxs-lookup"><span data-stu-id="663d4-149">Therefore, it is important that the administrator enters subnets exactly as provided by Lync clients (which are provisioned with subnets during network configuration, either statically or by Dynamic Host Configuration Protocol (DHCP).)</span></span>



</div>

</div>

<div>

## <a name="associating-subnets-with-network-sites"></a><span data-ttu-id="663d4-150">Asociar subredes con sitios de red</span><span class="sxs-lookup"><span data-stu-id="663d4-150">Associating Subnets with Network Sites</span></span>

<span data-ttu-id="663d4-151">Cada subred de la red empresarial necesita asociarse a un sitio de red (es decir, cada subred tiene que estar asociada a una ubicación geográfica).</span><span class="sxs-lookup"><span data-stu-id="663d4-151">Every subnet in the enterprise network must be associated with a network site (that is, every subnet needs to be associated with a geographic location).</span></span> <span data-ttu-id="663d4-152">Esta asociación de subredes permite a las características avanzadas de telefonía a empresas ubicar los puntos de conexión geográficamente.</span><span class="sxs-lookup"><span data-stu-id="663d4-152">This association of subnets enables the advanced Enterprise Voice features to locate the endpoints geographically.</span></span> <span data-ttu-id="663d4-153">Por ejemplo, ubicar los extremos permite al CAC regular el flujo de datos de audio y vídeo que recibe y envía el sitio de red en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="663d4-153">For example, locating the endpoints enables CAC to regulate the flow of real-time audio and video data going to and from the network site.</span></span>

<span data-ttu-id="663d4-154">Para asociar subredes a sitios de red, puede usar la sección **configuración de red** del panel de control de Lync Server, o bien, puede usar el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="663d4-154">To associate subnets with network sites, you can either use the **Network Configuration** section of Lync Server Control Panel, or you can use the Lync Server Management Shell.</span></span> <span data-ttu-id="663d4-155">Para obtener instrucciones, consulte [asociar una subred con un sitio de red en Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) en la documentación de implementación o consulte la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="663d4-155">For instructions, see [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="663d4-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="663d4-156">See Also</span></span>


[<span data-ttu-id="663d4-157">Planear el control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="663d4-157">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)  
[<span data-ttu-id="663d4-158">Planeación de los servicios de emergencia (E9-1-1) en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="663d4-158">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>](lync-server-2013-planning-for-emergency-services-e9-1-1.md)  
[<span data-ttu-id="663d4-159">Planificar la omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="663d4-159">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

