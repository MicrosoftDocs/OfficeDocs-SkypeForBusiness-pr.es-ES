---
title: 'Lync Server 2013: definir los elementos de red que se usan para determinar la ubicación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the network elements used to determine location
ms:assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398567(v=OCS.15)
ms:contentKeyID: 48184508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6cfedb09cdcdebdc12cdd2aed69e56532dcca5ad
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504507"
---
# <a name="defining-the-network-elements-used-to-determine-location-in-lync-server-2013"></a><span data-ttu-id="be996-102">Definición de los elementos de red que se usan para determinar la ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be996-102">Defining the network elements used to determine location in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be996-103">_**Última modificación del tema:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="be996-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="be996-104">Si está configurando su infraestructura de Lync Server para admitir la detección automática de ubicaciones de clientes, primero debe decidir qué elementos de red va a usar para asignar los autores de las llamadas a las ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="be996-104">If you are setting up your Lync Server infrastructure to support automatic client location detection, you first need to decide which network elements you are going to use to map callers to locations.</span></span> <span data-ttu-id="be996-105">En Lync Server 2013, puede asociar los siguientes elementos de red de nivel 2 y 3 con ubicaciones:</span><span class="sxs-lookup"><span data-stu-id="be996-105">In Lync Server 2013, you can associate the following Layer 2 and Layer 3 network elements with locations:</span></span>

  - <span data-ttu-id="be996-106">Direcciones de identificación de conjunto de servicio (BSSID) básicas de punto de acceso inalámbrico (WAP) (nivel 2)</span><span class="sxs-lookup"><span data-stu-id="be996-106">Wireless access point (WAP) Basic Service Set Identification (BSSID) addresses (Layer 2)</span></span>

  - <span data-ttu-id="be996-107">Puerto del conmutador LLDP (nivel 2)</span><span class="sxs-lookup"><span data-stu-id="be996-107">LLDP switch port (Layer 2)</span></span>

  - <span data-ttu-id="be996-108">Identificadores del chasis del conmutador LLDP (nivel 2)</span><span class="sxs-lookup"><span data-stu-id="be996-108">LLDP switch chassis IDs (Layer 2)</span></span>

  - <span data-ttu-id="be996-109">Subredes IP (nivel 3)</span><span class="sxs-lookup"><span data-stu-id="be996-109">IP subnets (Layer 3)</span></span>

  - <span data-ttu-id="be996-110">Direcciones MAC de cliente (nivel 2)</span><span class="sxs-lookup"><span data-stu-id="be996-110">Client MAC addresses (Layer 2)</span></span>

<span data-ttu-id="be996-111">Los elementos de la red se muestran en orden de prioridad.</span><span class="sxs-lookup"><span data-stu-id="be996-111">The network elements are listed in order of precedence.</span></span> <span data-ttu-id="be996-112">Si un cliente se puede ubicar mediante más de un elemento de red, Lync Server usa el orden de prioridad para determinar el mecanismo que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="be996-112">If a client can be located by using more than one network element, Lync Server uses the order of precedence to determine which mechanism to use.</span></span>

<span data-ttu-id="be996-113">En las secciones siguientes se proporcionan más detalles sobre el uso de cada elemento de red.</span><span class="sxs-lookup"><span data-stu-id="be996-113">The following sections provide more details for using each network element.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="be996-114">Cuando se usan elementos de red para asignar los autores de las llamadas a las ubicaciones, es fundamental tener la actualización de la base de datos del servicio de información de ubicación.</span><span class="sxs-lookup"><span data-stu-id="be996-114">When you use network elements to map callers to locations, it is of utmost importance that you keep the Location Information service database up-to-date.</span></span> <span data-ttu-id="be996-115">Por ejemplo, si agregas o cambias un elemento de red, como agregar un WAP, deberás eliminar la entrada antigua y agregar la nueva a la base de datos de ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="be996-115">For example, if you add or change a network element, such as adding a WAP, you must delete the old entry and add the new entry in the location database.</span></span>



</div>

<div>

## <a name="wireless-access-point"></a><span data-ttu-id="be996-116">Punto de acceso inalámbrico</span><span class="sxs-lookup"><span data-stu-id="be996-116">Wireless Access Point</span></span>

<span data-ttu-id="be996-117">Cuando un cliente se conecta a la red de manera inalámbrica, la solicitud de ubicación usa la dirección BSSID del WAP para determinar su ubicación.</span><span class="sxs-lookup"><span data-stu-id="be996-117">When a client connects to the network wirelessly, the location request uses the BSSID address of the WAP to determine its location.</span></span> <span data-ttu-id="be996-118">Si el cliente está en itinerancia, el WAP indicado puede que no sea el más próximo, y es incluso posible retomar un WAP que se encuentra en un piso diferente del edificio.</span><span class="sxs-lookup"><span data-stu-id="be996-118">If the client is roaming, the WAP indicated may not be the closest one, and it’s even possible to pick up a WAP that is on a different floor of the building.</span></span> <span data-ttu-id="be996-119">Para indicar que la ubicación es aproximada, puede anteponer el valor de ubicación con un descriptor near o Close.</span><span class="sxs-lookup"><span data-stu-id="be996-119">To indicate that the location is approximate, you can prepend the location value with a Near or Close to descriptor.</span></span>

<span data-ttu-id="be996-120">Este método de ubicación presupone que el BSSID de cada WAP es estático.</span><span class="sxs-lookup"><span data-stu-id="be996-120">This location method assumes that the BSSID of each WAP is static.</span></span> <span data-ttu-id="be996-121">Sin embargo, si su proveedor WAP usa BSSIDs asignada dinámicamente, los BSSID que se obtienen de un WAP podrían cambiar (esto puede ocurrir después de un cambio de configuración WAP) y los clientes inalámbricos pueden quedar en una situación en la que no reciben una ubicación.</span><span class="sxs-lookup"><span data-stu-id="be996-121">However, if your WAP vendor uses dynamically-assigned BSSIDs, the BSSID that is obtained from a WAP could change (this can happen following a WAP configuration change), and wireless clients could be left in a situation where they don’t receive a location.</span></span> <span data-ttu-id="be996-122">Para evitar esta posibilidad, debe rellenar la base de datos del servicio de información de ubicaciones con Erl para todas las direcciones BSSID posibles usadas por cada WAP.</span><span class="sxs-lookup"><span data-stu-id="be996-122">To prevent this possibility, you need to populate the Location Information service database with ERLs for all possible BSSID addresses used by each WAP.</span></span>

</div>

<div>

## <a name="lldp-ports-and-switches"></a><span data-ttu-id="be996-123">Conmutadores y puertos LLDP</span><span class="sxs-lookup"><span data-stu-id="be996-123">LLDP Ports and Switches</span></span>

<span data-ttu-id="be996-124">Los conmutadores Ethernet administrados que admiten la detección de la capa de vínculo Protocol-Media detección de extremos (LLDP-MED) pueden anunciar información de identidades y puertos a clientes compatibles con LLDP-MED, que se pueden consultar en la base de datos de ubicaciones para proporcionar la ubicación del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="be996-124">Managed Ethernet switches that support Link Layer Discovery Protocol-Media Endpoint Discover (LLDP-MED) can advertise their identity and port information to LLDP-MED compatible clients, which then can be queried against the location database to provide the location of the device.</span></span> <span data-ttu-id="be996-125">Puede asociar ERL únicamente en el identificador del chasis del conmutador, o puede asignarlos al nivel de puerto.</span><span class="sxs-lookup"><span data-stu-id="be996-125">You can associate ERLs solely on the switch chassis ID, or you can map them down to the port level.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="be996-126">Lync Server 2013 admite el uso de LLDP-MED para determinar las ubicaciones de los dispositivos Lync Phone Edition y Lync 2013 en Windows 8.</span><span class="sxs-lookup"><span data-stu-id="be996-126">Lync Server 2013 supports using LLDP-MED for determining locations only of Lync Phone Edition devices and Lync 2013 running on Windows 8.</span></span> <span data-ttu-id="be996-127">Si necesita usar datos de capa 2 a nivel de conmutador para determinar la ubicación de otros clientes de Lync basados en PC cableados, debe usar el método de dirección MAC del cliente.</span><span class="sxs-lookup"><span data-stu-id="be996-127">If you need to use switch-level Layer 2 data to determine the location of other wired PC-based Lync clients, you need to use the client MAC address method.</span></span>



</div>

</div>

<div>

## <a name="subnet"></a><span data-ttu-id="be996-128">Subred</span><span class="sxs-lookup"><span data-stu-id="be996-128">Subnet</span></span>

<span data-ttu-id="be996-129">Las subredes IP de nivel 3 proporcionan un mecanismo compatible con todos los clientes de Lync Server que se pueden usar para detectar automáticamente la ubicación del cliente.</span><span class="sxs-lookup"><span data-stu-id="be996-129">Layer 3 IP subnets provide a mechanism supported by all Lync Server clients that can be used to automatically detect client location.</span></span> <span data-ttu-id="be996-130">El uso de subredes IP es el método de ubicación más fácil para configurar y administrar clientes con cable.</span><span class="sxs-lookup"><span data-stu-id="be996-130">Using IP subnets is the easiest location method to configure and manage wired clients.</span></span> <span data-ttu-id="be996-131">Sin embargo, antes de decidirse a usar subredes, puede usar las siguientes preguntas para determinar si la especificidad de la ubicación de la subred es lo suficientemente adecuada como para buscar un cliente de forma precisa:</span><span class="sxs-lookup"><span data-stu-id="be996-131">Before you decide to use subnets, however, use the following questions to help determine if the location specificity of the subnet is sufficiently fine to accurately locate a client:</span></span>

  - <span data-ttu-id="be996-132">¿Hay una o más subredes de clientes que cubran varios pisos?</span><span class="sxs-lookup"><span data-stu-id="be996-132">Do one or more client subnets cover multiple floors?</span></span>

  - <span data-ttu-id="be996-133">¿Hay una o más subredes que cubran más de un edificio?</span><span class="sxs-lookup"><span data-stu-id="be996-133">Do one or more subnets cover more than one building?</span></span>

  - <span data-ttu-id="be996-134">¿Cuánto espacio de planta cubre cada subred de cliente?</span><span class="sxs-lookup"><span data-stu-id="be996-134">How much floor space is covered by each client subnet?</span></span>

<span data-ttu-id="be996-135">Si la subred cubre un área demasiado amplia, es posible que deba usar otro mecanismo para localizar clientes.</span><span class="sxs-lookup"><span data-stu-id="be996-135">If the subnet covers too broad an area, you may need to use another mechanism to locate clients.</span></span> <span data-ttu-id="be996-136">Sin embargo, si es posible, recomendamos que los clientes reorganicen sus subredes IP para cumplir con los requisitos de especificidad de la ubicación ERL, en lugar de incurrir en el coste y la complejidad de las soluciones basadas en SNMP de terceros.</span><span class="sxs-lookup"><span data-stu-id="be996-136">However, if at all practical, we recommend that customers reorganize their IP subnetting to meet the ERL location specificity requirements rather than incurring the cost and complexity of third-party SNMP-based solutions.</span></span>

</div>

<div>

## <a name="client-mac-address"></a><span data-ttu-id="be996-137">Dirección MAC del cliente</span><span class="sxs-lookup"><span data-stu-id="be996-137">Client MAC Address</span></span>

<span data-ttu-id="be996-138">Para usar la dirección MAC de un equipo cliente para localizar a una persona que llama, necesita conmutadores Ethernet administrados y debe implementar una solución SNMP de terceros que pueda detectar las direcciones MAC de los clientes de Lync conectados a los clientes (o a través de los mismos).</span><span class="sxs-lookup"><span data-stu-id="be996-138">To use a client computer's MAC address to locate a caller, you need managed Ethernet switches, and you must deploy a third-party SNMP solution that can discover the MAC addresses of Lync clients connected to (or through) those switches.</span></span> <span data-ttu-id="be996-139">La solución SNMP sondea continuamente los conmutadores administrados para obtener las asignaciones actuales de las direcciones MAC de extremo conectadas a cada puerto y obtiene los identificadores de Puerto correspondientes.</span><span class="sxs-lookup"><span data-stu-id="be996-139">The SNMP solution continually polls the managed switches to get the current mappings of the endpoint MAC addresses connected to each port and obtains the corresponding port IDs.</span></span> <span data-ttu-id="be996-140">Durante la solicitud de un cliente de Lync al servicio de información de ubicación, el servicio de información de ubicación consulta a la aplicación de terceros usando la dirección MAC del cliente y, a continuación, devuelve las direcciones IP del conmutador y los identificadores de Puerto correspondientes.</span><span class="sxs-lookup"><span data-stu-id="be996-140">During a Lync client’s request to the Location Information service, the Location Information service queries the third-party application by using the client’s MAC address, and then returns any matching switch IP addresses and port IDs.</span></span> <span data-ttu-id="be996-141">El servicio de información de ubicación usa esta información para consultar sus cableado de capa 2 publicadas para un registro que coincida y devuelve la ubicación al cliente.</span><span class="sxs-lookup"><span data-stu-id="be996-141">The Location Information service uses this information to query its published Layer 2 wiremap for a matching record and returns the location to the client.</span></span> <span data-ttu-id="be996-142">Si usa esta opción, asegúrese de que los identificadores de puerto del conmutador sean coherentes entre la aplicación SNMP y los registros de la base de datos de ubicación publicada.</span><span class="sxs-lookup"><span data-stu-id="be996-142">If you use this option, make sure that the switch port identifiers are consistent between the SNMP application and the published location database records.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="be996-143">Algunas soluciones SNMP de terceros pueden admitir conmutadores de acceso no administrados; Si el conmutador que dirige el cliente de Lync no está administrado pero tiene un vínculo superior a un conmutador de distribución administrada, el conmutador administrado puede informar a la aplicación SNMP de las direcciones MAC de los clientes conectados al conmutador de acceso.</span><span class="sxs-lookup"><span data-stu-id="be996-143">Some third-party SNMP solutions can support unmanaged access switches; if the switch that services the Lync client is unmanaged but has an uplink to a managed distribution switch, the managed switch can report back to the SNMP application the MAC addresses of the clients connected to the access switch.</span></span> <span data-ttu-id="be996-144">Esta información permite que el servicio de información de ubicación identifique la ubicación del usuario.</span><span class="sxs-lookup"><span data-stu-id="be996-144">This information enables the Location Information service to identify the location of the user.</span></span> <span data-ttu-id="be996-145">Sin embargo, es posible asignar un solo ERL a todos los puertos del conmutador no administrado, por lo que la especificidad de la ubicación solo está disponible en el nivel de chasis del conmutador de acceso, no en el nivel de puerto.</span><span class="sxs-lookup"><span data-stu-id="be996-145">However, it is possible to assign only a single ERL to all ports on the unmanaged switch, so the location specificity is available only at the chassis level of the access switch, not the port level.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

