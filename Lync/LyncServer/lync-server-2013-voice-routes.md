---
title: 'Lync Server 2013: Rutas de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Voice routes
ms:assetid: a2ddf327-2ec4-407b-af0f-276f2b13eefd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412757(v=OCS.15)
ms:contentKeyID: 48185038
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e46b4074d41d2ac79dfe63bc99411a7aba72a88c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850031"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voice-routes-in-lync-server-2013"></a><span data-ttu-id="ce66f-102">Rutas de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce66f-102">Voice routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce66f-103">_**Última modificación del tema:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="ce66f-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="ce66f-104">Las rutas de llamadas especifican cómo Lync Server administra las llamadas salientes que hacen los usuarios de telefonía IP.</span><span class="sxs-lookup"><span data-stu-id="ce66f-104">Call routes specify how Lync Server handles outbound calls placed by Enterprise Voice users.</span></span> <span data-ttu-id="ce66f-105">Cuando un usuario marca un número, el servidor front-end normaliza la cadena de marcado al formato E. 164, si es necesario, e intenta hacerlo coincidir con el URI del SIP.</span><span class="sxs-lookup"><span data-stu-id="ce66f-105">When a user dials a number, the Front End Server normalizes the dial string to E.164 format, if necessary, and attempts to match it to a SIP URI.</span></span> <span data-ttu-id="ce66f-106">Si el servidor no puede establecer esa coincidencia, aplicará la lógica de enrutamiento de llamadas salientes basándose en el número.</span><span class="sxs-lookup"><span data-stu-id="ce66f-106">If the server cannot make the match, it applies outgoing call routing logic based on the number.</span></span> <span data-ttu-id="ce66f-107">El paso final para definir la lógica consiste en crear una ruta de llamada con nombre independiente para cada conjunto de números de teléfono de destino indicados en cada plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="ce66f-107">The final step in defining that logic is to create a separate named call route for each set of destination phone numbers that are listed in each dial plan.</span></span>

<span data-ttu-id="ce66f-108">Antes de definir las rutas de llamadas salientes, necesitas completar los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="ce66f-108">Before you define outbound call routes, you should complete the following steps:</span></span>

  - <span data-ttu-id="ce66f-109">Implementa uno o más troncos.</span><span class="sxs-lookup"><span data-stu-id="ce66f-109">Deploy one or more trunks.</span></span>

  - <span data-ttu-id="ce66f-110">Crea planes de marcado, según sea necesario, para sitios, usuarios individuales y objetos de contacto.</span><span class="sxs-lookup"><span data-stu-id="ce66f-110">Create dial plans as needed for sites, individuals, and Contact objects.</span></span>

  - <span data-ttu-id="ce66f-111">Crea registros de uso de la red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="ce66f-111">Create public switched telephone network (PSTN) usage records.</span></span>

<span data-ttu-id="ce66f-p102">Además, para habilitar el enrutamiento de llamadas salientes, necesitas crear y asignar una o más directivas de voz. Puedes hacerlo antes o después de definir las rutas de llamadas salientes.</span><span class="sxs-lookup"><span data-stu-id="ce66f-p102">Additionally, to enable outbound call routing, you must create and assign one or more voice policies. You can do this either before or after you define outbound call routes.</span></span>

<span data-ttu-id="ce66f-114">Para cada ruta, necesitas especificar:</span><span class="sxs-lookup"><span data-stu-id="ce66f-114">For each route, you must specify:</span></span>

  - <span data-ttu-id="ce66f-115">Un nombre con el que se pueda identificar fácilmente la ruta.</span><span class="sxs-lookup"><span data-stu-id="ce66f-115">A name by which the route can be easily identified.</span></span>

  - <span data-ttu-id="ce66f-116">Una descripción opcional en los casos en que el nombre no sea suficiente para describir la ruta.</span><span class="sxs-lookup"><span data-stu-id="ce66f-116">An optional description in cases where the name alone may not be sufficient to describe the route.</span></span>

  - <span data-ttu-id="ce66f-117">El patrón coincidente de la expresión regular que identifica los números de teléfono de destino a los que se aplica la ruta, junto con excepciones a las que no se necesita aplicar el patrón coincidente.</span><span class="sxs-lookup"><span data-stu-id="ce66f-117">The regular expression matching pattern that identifies the destination phone numbers to which the route is applied, along with exceptions to which the matching pattern is not to be applied.</span></span>

  - <span data-ttu-id="ce66f-118">Uno o más troncos que deseas asignar a la ruta.</span><span class="sxs-lookup"><span data-stu-id="ce66f-118">One or more trunks that you want to assign to the route.</span></span>

  - <span data-ttu-id="ce66f-119">Los registros de uso de RTC que los usuarios necesitan tener para llamar a los números que coincidan con la expresión regular del número de teléfono de destino.</span><span class="sxs-lookup"><span data-stu-id="ce66f-119">The PSTN usage records that users must have in order to call numbers matching the destination phone number regular expression.</span></span>

<span data-ttu-id="ce66f-120">Puede especificar rutas de llamadas en el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ce66f-120">You can specify call routes in the Lync Server Control Panel.</span></span> <span data-ttu-id="ce66f-121">Estas rutas de llamadas rellenan la tabla de enrutamiento del servidor, que Lync Server usa para enrutar las llamadas dirigidas a la RTC.</span><span class="sxs-lookup"><span data-stu-id="ce66f-121">These call routes populate the server routing table, which Lync Server uses to route calls that are destined for the PSTN.</span></span>

<div>

## <a name="mn-trunk-support"></a><span data-ttu-id="ce66f-122">Compatibilidad con troncos M:N</span><span class="sxs-lookup"><span data-stu-id="ce66f-122">M:N Trunk Support</span></span>

<span data-ttu-id="ce66f-123">Lync Server proporciona flexibilidad a la hora de enrutar las llamadas a la RTC.</span><span class="sxs-lookup"><span data-stu-id="ce66f-123">Lync Server provides flexibility in how calls are routed to the PSTN.</span></span> <span data-ttu-id="ce66f-124">Una ruta de voz especifica a la RTC un conjunto de troncos que pueden usarse para una llamada de voz concreta.</span><span class="sxs-lookup"><span data-stu-id="ce66f-124">A voice route specifies a set of trunks to the PSTN that can be used for a particular voice call.</span></span> <span data-ttu-id="ce66f-125">Un tronco asocia un servidor de mediación y un número de puerto con una puerta de enlace RTC y un número de puerto de escucha.</span><span class="sxs-lookup"><span data-stu-id="ce66f-125">A trunk associates a Mediation Server and a port number with a PSTN gateway and listening port number.</span></span> <span data-ttu-id="ce66f-126">Esta asociación lógica permite asociar un servidor de mediación con varias puertas de enlace y tener varias conexiones a la misma puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="ce66f-126">This logical association enables a Mediation Server to be associated with multiple gateways and have multiple connections to the same gateway.</span></span> <span data-ttu-id="ce66f-127">Al definir una ruta de llamada, especifica los troncos asociados a esa ruta, pero no especifica qué servidores de mediación están asociados a la ruta.</span><span class="sxs-lookup"><span data-stu-id="ce66f-127">When defining a call route, you specify the trunks associated with that route, but you do not specify which Mediation Servers are associated with the route.</span></span> <span data-ttu-id="ce66f-128">Para crear troncos definiendo las relaciones entre los servidores de mediación y las puertas de enlace RTC, IP-PBX y los controladores de borde de sesión (SBCs), use el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="ce66f-128">To create trunks by defining the relationships between Mediation Servers and PSTN gateways, IP-PBXs, and Session Border Controllers (SBCs), use the Topology Builder.</span></span>

</div>

<div>

## <a name="least-cost-routing"></a><span data-ttu-id="ce66f-129">Enrutamiento de menor coste</span><span class="sxs-lookup"><span data-stu-id="ce66f-129">Least-Cost Routing</span></span>

<span data-ttu-id="ce66f-p105">La capacidad para especificar los troncos a los que se redirigen varios números te permite determinar e implementar las rutas de menor coste. La regla general para seleccionar troncos es elegir el que tenga la puerta de enlace más cercana a la ubicación del número de destino a fin de minimizar los gastos de larga distancia. Por ejemplo, si te encontraras en Nueva York y llamaras a Roma, llevarías la llamada a través de la red IP hasta el tronco con la puerta de enlace más cercana a la oficina de Roma, por lo que solo necesitarías pagar el precio de una llamada local.</span><span class="sxs-lookup"><span data-stu-id="ce66f-p105">The ability to specify the trunks to which various numbers are routed enables you to determine which routes incur the lowest costs and implement them accordingly. The general rule in selecting trunks is to choose the trunk with the closest gateway to the location of the destination number in order to minimize long-distance charges. For example, if you are in New York and calling a number in Rome, you would carry the call over the IP network to the trunk with the gateway in your Rome office, thereby incurring a charge only for a local call.</span></span>

<span data-ttu-id="ce66f-133">Para obtener un ejemplo de cómo se puede usar el enrutamiento de menor costo, considere lo siguiente: fabrikam decide permitir que los usuarios de alemán llamen a números de Estados Unidos con el tronco de Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="ce66f-133">For an example of how least-cost routing might be used, consider the following: Fabrikam decides to enable German users to dial U.S. numbers by using the U.S. trunk.</span></span> <span data-ttu-id="ce66f-134">Fabrikam también desea configurar el sistema para que todas las llamadas de los usuarios del servidor de Lync de Estados Unidos a Alemania y países o regiones adyacentes terminen en el tronco con el Gateway en Alemania.</span><span class="sxs-lookup"><span data-stu-id="ce66f-134">Fabrikam also wants to configure the system so that all calls from U.S. Lync Server users to Germany and adjacent countries/regions terminate on the trunk with the gateway in Germany.</span></span> <span data-ttu-id="ce66f-135">Este enrutamiento ahorrará dinero, porque una llamada de Alemania a Austria, por ejemplo, es menos costosa que una llamada de Estados Unidos a Austria.</span><span class="sxs-lookup"><span data-stu-id="ce66f-135">This routing will save money, because a call from Germany to Austria, for example, is less expensive than a call from the U.S. to Austria.</span></span>

</div>

<div>

## <a name="translating-outbound-dial-strings"></a><span data-ttu-id="ce66f-136">Convertir cadenas de marcado salientes</span><span class="sxs-lookup"><span data-stu-id="ce66f-136">Translating Outbound Dial Strings</span></span>

<span data-ttu-id="ce66f-137">Lync Server 2013, al igual que sus predecesores inmediatos, requiere normalizar todas las cadenas de marcado al formato E. 164 con el fin de realizar la búsqueda de números inversos (RNL).</span><span class="sxs-lookup"><span data-stu-id="ce66f-137">Lync Server 2013, like its immediate predecessors, requires all dial strings to be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="ce66f-138">Para los troncos con puertas de enlace o las sucursales privadas (PBX) que requieren números traducidos a formatos de marcado locales, Lync Server 2013 le permite crear una o más reglas que ayuden a manipular el número llamado (es decir, URI de solicitud) antes de enrutarlo al tronco.</span><span class="sxs-lookup"><span data-stu-id="ce66f-138">For trunks with gateways or private branch exchanges (PBXs) that require numbers translated in local dialing formats, Lync Server 2013 enables you to create one or more rules that assist in manipulating the called number (i.e. Request URI) prior to routing it to the trunk.</span></span> <span data-ttu-id="ce66f-139">Por ejemplo, podrías escribir una regla para quitar +44 del encabezado de la cadena de marcado y cambiarlo por 0144.</span><span class="sxs-lookup"><span data-stu-id="ce66f-139">For example, you could write a rule to remove +44 from the head of a dial string and replace it with 0144.</span></span>

<span data-ttu-id="ce66f-140">Con Lync Server 2013, es posible crear una o más reglas que ayuden a manipular el número de llamada antes de enrutarlo al tronco.</span><span class="sxs-lookup"><span data-stu-id="ce66f-140">With Lync Server 2013, it is possible to create one or more rules that assist in manipulating the calling number prior to routing it to the trunk.</span></span>

<span data-ttu-id="ce66f-141">En el planeamiento de los troncos que asocian puertas de enlace: pares de puertos con el servidor de mediación: pares de puertos, puede ser útil agrupar los troncos con requisitos de marcado local similares y, por lo tanto, reducir el número de reglas de traducción necesarias y el tiempo que se tarda en escribirlas.</span><span class="sxs-lookup"><span data-stu-id="ce66f-141">In planning your trunks that associate gateways:port pairs with Mediation Server:port pairs, it may be useful to group trunks with similar local dialing requirements, and therefore reduce the number of required translation rules and the time it takes to write them.</span></span>

</div>

<div>

## <a name="configuring-caller-id"></a><span data-ttu-id="ce66f-142">Configurar el identificador de llamada</span><span class="sxs-lookup"><span data-stu-id="ce66f-142">Configuring Caller ID</span></span>

<span data-ttu-id="ce66f-143">Lync Server proporciona una forma de manipular la identificación de llamadas para las llamadas salientes.</span><span class="sxs-lookup"><span data-stu-id="ce66f-143">Lync Server provides a way to manipulate the caller ID for outbound calls.</span></span> <span data-ttu-id="ce66f-144">Por ejemplo, si una organización desea enmascarar las extensiones de marcado directo de los empleados y reemplazarlas con el número de departamento o corporativo genérico, un administrador puede hacerlo con el panel de control de Lync Server para suprimir la identificación de llamadas y reemplazarla por una IDENTIFICADOR de llamada alternativo especificado.</span><span class="sxs-lookup"><span data-stu-id="ce66f-144">For example, if an organization wants to mask employees’ direct-dial extensions and replace them with the generic corporate or departmental number, an administrator can do that by using Lync Server Control Panel to suppress the caller ID and replace it with a specified alternative caller ID.</span></span> <span data-ttu-id="ce66f-145">Al planificar la lógica de enrutamiento, ten en cuenta si querrás esta opción para usuarios individuales, grupos o sitios o, incluso, para todos los empleados.</span><span class="sxs-lookup"><span data-stu-id="ce66f-145">In planning your routing logic, consider which individuals, groups, sites you’ll want this option for—perhaps, even, for all employees.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ce66f-p109">En el caso de las llamadas que se desvían a través de la RTC, se presentará el identificador de llamada genérico en lugar del identificador de llamada original. Esto puede hacer que la llamada omita la configuración de privacidad o de No molestar que pueda haber establecido el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="ce66f-p109">For calls that are rerouted over the PSTN, the generic caller ID will be presented instead of the original caller ID. This can cause the call to bypass Do Not Disturb or privacy settings that the callee may have configured.</span></span>



</div>

</div>

<div>

## <a name="additional-routing-logic"></a><span data-ttu-id="ce66f-148">Lógica de enrutamiento adicional</span><span class="sxs-lookup"><span data-stu-id="ce66f-148">Additional Routing Logic</span></span>

<span data-ttu-id="ce66f-149">Al crear rutas de llamadas salientes, necesitas tener en cuenta los siguientes factores que pueden afectar a la lógica de enrutamiento:</span><span class="sxs-lookup"><span data-stu-id="ce66f-149">In creating outbound call routes, you should be aware of the following factors that can affect routing logic:</span></span>

  - <span data-ttu-id="ce66f-150">Si se establece una llamada a través de un límite federado, la parte correspondiente al dominio en el URI se usa para redirigir la llamada a la empresa responsable de aplicar la lógica de enrutamiento saliente.</span><span class="sxs-lookup"><span data-stu-id="ce66f-150">Where a call is established over a federated boundary, the domain portion of the URI is used to route the call over to the enterprise that is responsible for applying the outbound routing logic.</span></span>

  - <span data-ttu-id="ce66f-151">Si la parte correspondiente al dominio en el URI de la solicitud no contiene un dominio compatible para la empresa, el componente de enrutamiento saliente en el servidor no procesará la llamada.</span><span class="sxs-lookup"><span data-stu-id="ce66f-151">If the domain portion of the request URI does not contain a supported domain for the enterprise, the outbound routing component on the server does not process the call.</span></span>

  - <span data-ttu-id="ce66f-152">Si un usuario no está habilitado para Enterprise Voice, el servidor aplicará otra lógica de enrutamiento, según corresponda.</span><span class="sxs-lookup"><span data-stu-id="ce66f-152">If a user is not enabled for Enterprise Voice, the server applies other routing logic, as appropriate.</span></span>

  - <span data-ttu-id="ce66f-p110">Si se redirige una llamada a una puerta de enlace totalmente ocupada (todas las principales líneas de conexión están ocupadas), la puerta de enlace rechaza la llamada y la lógica de enrutamiento saliente redirige la llamada a la siguiente ruta de menor coste. Esto necesita analizarse minuciosamente, ya que una puerta de enlace con un tamaño adecuado para una oficina pequeña internacional (por ejemplo, de Zúrich), podría transportar una cantidad importante de tráfico no local para las llamadas internacionales a Suiza. Si el tamaño de la puerta de enlace no se diseñara correctamente para este tráfico adicional, las llamadas a Suiza podrían redirigirse a través de una puerta de enlace de Alemania, lo que daría lugar a tarifas más altas.</span><span class="sxs-lookup"><span data-stu-id="ce66f-p110">If a call is routed to a gateway that is fully occupied (all trunk lines are busy), the gateway rejects the call and the outbound routing logic redirects the call to the next-least-cost route. Give this careful consideration, because a gateway sized for a small office overseas (for example, Zurich) may actually carry a significant amount of nonlocal traffic for international calls to Switzerland. If the gateway is not correctly sized for this additional traffic, calls to Switzerland may be routed by way of a gateway in Germany, resulting in larger toll charges.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

