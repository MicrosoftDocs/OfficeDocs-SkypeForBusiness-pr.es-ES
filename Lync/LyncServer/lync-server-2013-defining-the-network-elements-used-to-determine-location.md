---
title: 'Lync Server 2013: definir los elementos de red que se usan para determinar la ubicación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining the network elements used to determine location
ms:assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398567(v=OCS.15)
ms:contentKeyID: 48184508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 572e7e5392390e659b52853cb47e30f696c65e91
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835705"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-network-elements-used-to-determine-location-in-lync-server-2013"></a><span data-ttu-id="06ad4-102">Definir los elementos de red que se usan para determinar la ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="06ad4-102">Defining the network elements used to determine location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06ad4-103">_**Última modificación del tema:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="06ad4-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="06ad4-104">Si está configurando su infraestructura de Lync Server para admitir la detección automática de la ubicación del cliente, primero debe decidir qué elementos de la red va a usar para asignar las personas que llaman a ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="06ad4-104">If you are setting up your Lync Server infrastructure to support automatic client location detection, you first need to decide which network elements you are going to use to map callers to locations.</span></span> <span data-ttu-id="06ad4-105">En Lync Server 2013, puede asociar los siguientes elementos de red de la capa 2 y la capa 3 con ubicaciones:</span><span class="sxs-lookup"><span data-stu-id="06ad4-105">In Lync Server 2013, you can associate the following Layer 2 and Layer 3 network elements with locations:</span></span>

  - <span data-ttu-id="06ad4-106">Direcciones de identificación básica de conjunto de servicio (BSSID) con punto de acceso inalámbrico (WAP) (nivel 2)</span><span class="sxs-lookup"><span data-stu-id="06ad4-106">Wireless access point (WAP) Basic Service Set Identification (BSSID) addresses (Layer 2)</span></span>

  - <span data-ttu-id="06ad4-107">Puerto del conmutador LLDP (nivel 2)</span><span class="sxs-lookup"><span data-stu-id="06ad4-107">LLDP switch port (Layer 2)</span></span>

  - <span data-ttu-id="06ad4-108">Identificadores del chasis del conmutador LLDP (nivel 2)</span><span class="sxs-lookup"><span data-stu-id="06ad4-108">LLDP switch chassis IDs (Layer 2)</span></span>

  - <span data-ttu-id="06ad4-109">Subredes IP (nivel 3)</span><span class="sxs-lookup"><span data-stu-id="06ad4-109">IP subnets (Layer 3)</span></span>

  - <span data-ttu-id="06ad4-110">Direcciones MAC de cliente (nivel 2)</span><span class="sxs-lookup"><span data-stu-id="06ad4-110">Client MAC addresses (Layer 2)</span></span>

<span data-ttu-id="06ad4-111">Los elementos de red se enumeran en orden de prioridad.</span><span class="sxs-lookup"><span data-stu-id="06ad4-111">The network elements are listed in order of precedence.</span></span> <span data-ttu-id="06ad4-112">Si un cliente puede encontrarse usando más de un elemento de red, Lync Server usa el orden de prioridad para determinar qué mecanismo usar.</span><span class="sxs-lookup"><span data-stu-id="06ad4-112">If a client can be located by using more than one network element, Lync Server uses the order of precedence to determine which mechanism to use.</span></span>

<span data-ttu-id="06ad4-113">En las siguientes secciones se proporciona más información sobre el uso de cada elemento de red.</span><span class="sxs-lookup"><span data-stu-id="06ad4-113">The following sections provide more details for using each network element.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="06ad4-114">Al usar elementos de red para asignar las personas que llaman a ubicaciones, es muy importante que mantenga actualizada la base de datos del servicio de información de ubicación.</span><span class="sxs-lookup"><span data-stu-id="06ad4-114">When you use network elements to map callers to locations, it is of utmost importance that you keep the Location Information service database up-to-date.</span></span> <span data-ttu-id="06ad4-115">Por ejemplo, si agregas o cambias un elemento de red, como cuando agregas un WAP, necesitarás eliminar la entrada antigua y agregar la nueva a la base de datos de ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="06ad4-115">For example, if you add or change a network element, such as adding a WAP, you must delete the old entry and add the new entry in the location database.</span></span>



</div>

<div>

## <a name="wireless-access-point"></a><span data-ttu-id="06ad4-116">Punto de acceso inalámbrico</span><span class="sxs-lookup"><span data-stu-id="06ad4-116">Wireless Access Point</span></span>

<span data-ttu-id="06ad4-117">Cuando un cliente se conecta a la red de manera inalámbrica, la solicitud de ubicación determina la ubicación al usar la dirección BSSID del WAP.</span><span class="sxs-lookup"><span data-stu-id="06ad4-117">When a client connects to the network wirelessly, the location request uses the BSSID address of the WAP to determine its location.</span></span> <span data-ttu-id="06ad4-118">Si el cliente está utilizando un perfil móvil, puede que el WAP indicado sea el más cercano y es posible, incluso, conectarse a un WAP que se encuentre en otra planta del edificio.</span><span class="sxs-lookup"><span data-stu-id="06ad4-118">If the client is roaming, the WAP indicated may not be the closest one, and it’s even possible to pick up a WAP that is on a different floor of the building.</span></span> <span data-ttu-id="06ad4-119">Para indicar que la ubicación es aproximada, puedes anteponer Near o Close to al valor de ubicación del descriptor.</span><span class="sxs-lookup"><span data-stu-id="06ad4-119">To indicate that the location is approximate, you can prepend the location value with a Near or Close to descriptor.</span></span>

<span data-ttu-id="06ad4-120">Este método de ubicación supone que el BSSID de cada WAP es estático.</span><span class="sxs-lookup"><span data-stu-id="06ad4-120">This location method assumes that the BSSID of each WAP is static.</span></span> <span data-ttu-id="06ad4-121">Sin embargo, si su proveedor WAP usa BSSIDs asignados dinámicamente, los BSSID que se obtengan de un WAP podrían cambiar (esto puede ocurrir después de un cambio de configuración WAP), y los clientes inalámbricos podrían permanecer en una situación en la que no reciban una ubicación.</span><span class="sxs-lookup"><span data-stu-id="06ad4-121">However, if your WAP vendor uses dynamically-assigned BSSIDs, the BSSID that is obtained from a WAP could change (this can happen following a WAP configuration change), and wireless clients could be left in a situation where they don’t receive a location.</span></span> <span data-ttu-id="06ad4-122">Para evitar esta posibilidad, debe rellenar la base de datos de servicios de información de ubicación con ERLs para todas las direcciones BSSID posibles que cada WAP usa.</span><span class="sxs-lookup"><span data-stu-id="06ad4-122">To prevent this possibility, you need to populate the Location Information service database with ERLs for all possible BSSID addresses used by each WAP.</span></span>

</div>

<div>

## <a name="lldp-ports-and-switches"></a><span data-ttu-id="06ad4-123">Conmutadores y puertos LLDP</span><span class="sxs-lookup"><span data-stu-id="06ad4-123">LLDP Ports and Switches</span></span>

<span data-ttu-id="06ad4-p106">Los conmutadores Ethernet administrados que admiten el Protocolo de detección de nivel de vínculo: detección de extremos de medios (LLDP-MED) pueden anunciar su identidad e información de puertos a los clientes compatibles con LLDP-MED. Esta información, a su vez, puede consultarse en la base de datos de ubicaciones para obtener la ubicación del dispositivo. Puedes asociar las ERL únicamente en el identificador de chasis del conmutador, o bien los puedes asignar en el puerto.</span><span class="sxs-lookup"><span data-stu-id="06ad4-p106">Managed Ethernet switches that support Link Layer Discovery Protocol-Media Endpoint Discover (LLDP-MED) can advertise their identity and port information to LLDP-MED compatible clients, which then can be queried against the location database to provide the location of the device. You can associate ERLs solely on the switch chassis ID, or you can map them down to the port level.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="06ad4-126">Lync Server 2013 admite el uso de LLDP-MED para determinar las ubicaciones de los dispositivos Lync Phone Edition y de Lync 2013 en Windows 8.</span><span class="sxs-lookup"><span data-stu-id="06ad4-126">Lync Server 2013 supports using LLDP-MED for determining locations only of Lync Phone Edition devices and Lync 2013 running on Windows 8.</span></span> <span data-ttu-id="06ad4-127">Si necesita usar datos de capa 2 a nivel de conmutador para determinar la ubicación de otros clientes de Lync basados en PC con cable, debe usar el método de dirección MAC del cliente.</span><span class="sxs-lookup"><span data-stu-id="06ad4-127">If you need to use switch-level Layer 2 data to determine the location of other wired PC-based Lync clients, you need to use the client MAC address method.</span></span>



</div>

</div>

<div>

## <a name="subnet"></a><span data-ttu-id="06ad4-128">Subred</span><span class="sxs-lookup"><span data-stu-id="06ad4-128">Subnet</span></span>

<span data-ttu-id="06ad4-129">Las subredes IP de nivel 3 proporcionan un mecanismo compatible con todos los clientes de Lync Server que se pueden usar para detectar automáticamente la ubicación de los clientes.</span><span class="sxs-lookup"><span data-stu-id="06ad4-129">Layer 3 IP subnets provide a mechanism supported by all Lync Server clients that can be used to automatically detect client location.</span></span> <span data-ttu-id="06ad4-130">El uso de subredes IP es el método de ubicación más sencillo para configurar y administrar clientes cableados.</span><span class="sxs-lookup"><span data-stu-id="06ad4-130">Using IP subnets is the easiest location method to configure and manage wired clients.</span></span> <span data-ttu-id="06ad4-131">Pero, antes de decidir usar subredes, necesitarás hacerte las siguientes preguntas para determinar si la ubicación de la subred es lo suficientemente específica para localizar con precisión a un cliente:</span><span class="sxs-lookup"><span data-stu-id="06ad4-131">Before you decide to use subnets, however, use the following questions to help determine if the location specificity of the subnet is sufficiently fine to accurately locate a client:</span></span>

  - <span data-ttu-id="06ad4-132">¿Existe una o más subredes de clientes que cubran varios pisos?</span><span class="sxs-lookup"><span data-stu-id="06ad4-132">Do one or more client subnets cover multiple floors?</span></span>

  - <span data-ttu-id="06ad4-133">¿Existe una o más subredes que cubran más de un edificio?</span><span class="sxs-lookup"><span data-stu-id="06ad4-133">Do one or more subnets cover more than one building?</span></span>

  - <span data-ttu-id="06ad4-134">¿Cuánto espacio del piso queda cubierto por cada subred de cliente?</span><span class="sxs-lookup"><span data-stu-id="06ad4-134">How much floor space is covered by each client subnet?</span></span>

<span data-ttu-id="06ad4-p109">Si la subred cubre un área demasiado extensa, es posible que debas usar otro mecanismo para ubicar a clientes. Pero, si resulta práctico, recomendamos que los clientes reorganicen su subred IP para cumplir con los requisitos de especificidad de la ubicación ERL en lugar de incurrir en el coste y la complejidad de soluciones basadas en SNMP de terceros.</span><span class="sxs-lookup"><span data-stu-id="06ad4-p109">If the subnet covers too broad an area, you may need to use another mechanism to locate clients. However, if at all practical, we recommend that customers reorganize their IP subnetting to meet the ERL location specificity requirements rather than incurring the cost and complexity of third-party SNMP-based solutions.</span></span>

</div>

<div>

## <a name="client-mac-address"></a><span data-ttu-id="06ad4-137">Dirección MAC de cliente</span><span class="sxs-lookup"><span data-stu-id="06ad4-137">Client MAC Address</span></span>

<span data-ttu-id="06ad4-138">Para usar la dirección MAC de un equipo cliente para ubicar a una persona que llama, necesita conmutadores Ethernet administrados y debe implementar una solución SNMP de terceros que pueda descubrir las direcciones MAC de los clientes de Lync conectados a ellos (o a través de ellos).</span><span class="sxs-lookup"><span data-stu-id="06ad4-138">To use a client computer's MAC address to locate a caller, you need managed Ethernet switches, and you must deploy a third-party SNMP solution that can discover the MAC addresses of Lync clients connected to (or through) those switches.</span></span> <span data-ttu-id="06ad4-139">La solución de SNMP sondea continuamente los conmutadores administrados para obtener las asignaciones actuales de las direcciones MAC de los extremos conectadas a cada puerto y obtiene los identificadores de puerto correspondientes.</span><span class="sxs-lookup"><span data-stu-id="06ad4-139">The SNMP solution continually polls the managed switches to get the current mappings of the endpoint MAC addresses connected to each port and obtains the corresponding port IDs.</span></span> <span data-ttu-id="06ad4-140">Durante la solicitud de un cliente de Lync al servicio de información de ubicación, el servicio de información de ubicación consulta la aplicación de terceros usando la dirección MAC del cliente y, a continuación, devuelve las direcciones IP del modificador y los identificadores de Puerto coincidentes.</span><span class="sxs-lookup"><span data-stu-id="06ad4-140">During a Lync client’s request to the Location Information service, the Location Information service queries the third-party application by using the client’s MAC address, and then returns any matching switch IP addresses and port IDs.</span></span> <span data-ttu-id="06ad4-141">El servicio de información de ubicación usa esta información para consultar sus Wiremap de capa 2 publicadas y devuelve la ubicación al cliente.</span><span class="sxs-lookup"><span data-stu-id="06ad4-141">The Location Information service uses this information to query its published Layer 2 wiremap for a matching record and returns the location to the client.</span></span> <span data-ttu-id="06ad4-142">Si utilizas esta opción, asegúrate de que los identificadores de puerto del conmutador son consistentes entre la aplicación SNMP y los registros de la base de datos de ubicación publicados.</span><span class="sxs-lookup"><span data-stu-id="06ad4-142">If you use this option, make sure that the switch port identifiers are consistent between the SNMP application and the published location database records.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="06ad4-143">Algunas soluciones SNMP de terceros pueden admitir modificadores de acceso no administrados; Si el modificador que ofrece servicio al cliente de Lync no está administrado pero tiene un vínculo superior a un conmutador de distribución administrada, el conmutador administrado puede informar a la aplicación SNMP de las direcciones MAC de los clientes conectados al conmutador de acceso.</span><span class="sxs-lookup"><span data-stu-id="06ad4-143">Some third-party SNMP solutions can support unmanaged access switches; if the switch that services the Lync client is unmanaged but has an uplink to a managed distribution switch, the managed switch can report back to the SNMP application the MAC addresses of the clients connected to the access switch.</span></span> <span data-ttu-id="06ad4-144">Esta información permite que el servicio de información de ubicación identifique la ubicación del usuario.</span><span class="sxs-lookup"><span data-stu-id="06ad4-144">This information enables the Location Information service to identify the location of the user.</span></span> <span data-ttu-id="06ad4-145">Pero, es posible asignar solo una única ERL a todos los puertos en el conmutador no administrado, por lo que la especificidad de la ubicación está disponible solamente en el chasis del conmutador de acceso, pero no en el puerto.</span><span class="sxs-lookup"><span data-stu-id="06ad4-145">However, it is possible to assign only a single ERL to all ports on the unmanaged switch, so the location specificity is available only at the chassis level of the access switch, not the port level.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

