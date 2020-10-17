---
title: 'Lync Server 2013: rutas de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Voice routes
ms:assetid: a2ddf327-2ec4-407b-af0f-276f2b13eefd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412757(v=OCS.15)
ms:contentKeyID: 48185038
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0f457fc96981927ea2b6cb4d4177488dc3f5231
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535497"
---
# <a name="voice-routes-in-lync-server-2013"></a><span data-ttu-id="20be0-102">Rutas de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20be0-102">Voice routes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20be0-103">_**Última modificación del tema:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="20be0-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="20be0-104">Las rutas de llamadas especifican cómo Lync Server administra las llamadas salientes realizadas por los usuarios de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="20be0-104">Call routes specify how Lync Server handles outbound calls placed by Enterprise Voice users.</span></span> <span data-ttu-id="20be0-105">Cuando un usuario marca un número, el servidor front-end normaliza la cadena de marcado al formato E. 164, si es necesario, e intenta establecer una coincidencia con un URI de SIP.</span><span class="sxs-lookup"><span data-stu-id="20be0-105">When a user dials a number, the Front End Server normalizes the dial string to E.164 format, if necessary, and attempts to match it to a SIP URI.</span></span> <span data-ttu-id="20be0-106">Si el servidor no puede realizar la coincidencia, aplica la lógica de enrutamiento de llamadas salientes en función del número.</span><span class="sxs-lookup"><span data-stu-id="20be0-106">If the server cannot make the match, it applies outgoing call routing logic based on the number.</span></span> <span data-ttu-id="20be0-107">El último paso para definir la lógica es crear una ruta de llamada con nombre independiente para cada conjunto de números de teléfono de destino que se enumeran en cada plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="20be0-107">The final step in defining that logic is to create a separate named call route for each set of destination phone numbers that are listed in each dial plan.</span></span>

<span data-ttu-id="20be0-108">Antes de definir las rutas de llamadas salientes, debe completar los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="20be0-108">Before you define outbound call routes, you should complete the following steps:</span></span>

  - <span data-ttu-id="20be0-109">Implementar uno o más troncos.</span><span class="sxs-lookup"><span data-stu-id="20be0-109">Deploy one or more trunks.</span></span>

  - <span data-ttu-id="20be0-110">Crear planes de marcado según sea necesario para los sitios, los individuos y los objetos de contacto.</span><span class="sxs-lookup"><span data-stu-id="20be0-110">Create dial plans as needed for sites, individuals, and Contact objects.</span></span>

  - <span data-ttu-id="20be0-111">Crear registros de uso de la red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="20be0-111">Create public switched telephone network (PSTN) usage records.</span></span>

<span data-ttu-id="20be0-112">Además, para habilitar el enrutamiento de llamadas salientes, debe crear y asignar una o más directivas de voz.</span><span class="sxs-lookup"><span data-stu-id="20be0-112">Additionally, to enable outbound call routing, you must create and assign one or more voice policies.</span></span> <span data-ttu-id="20be0-113">Puede hacer esto ya sea antes o después de definir las rutas de llamadas salientes.</span><span class="sxs-lookup"><span data-stu-id="20be0-113">You can do this either before or after you define outbound call routes.</span></span>

<span data-ttu-id="20be0-114">Para cada ruta, debe especificar:</span><span class="sxs-lookup"><span data-stu-id="20be0-114">For each route, you must specify:</span></span>

  - <span data-ttu-id="20be0-115">Nombre por el que se puede identificar fácilmente la ruta.</span><span class="sxs-lookup"><span data-stu-id="20be0-115">A name by which the route can be easily identified.</span></span>

  - <span data-ttu-id="20be0-116">Una descripción opcional en los casos en los que el nombre solo puede no ser suficiente para describir la ruta.</span><span class="sxs-lookup"><span data-stu-id="20be0-116">An optional description in cases where the name alone may not be sufficient to describe the route.</span></span>

  - <span data-ttu-id="20be0-117">El patrón de coincidencia de expresión regular que identifica los números de teléfono de destino a los que se aplica la ruta, junto con las excepciones a las que no se aplica el patrón de coincidencia.</span><span class="sxs-lookup"><span data-stu-id="20be0-117">The regular expression matching pattern that identifies the destination phone numbers to which the route is applied, along with exceptions to which the matching pattern is not to be applied.</span></span>

  - <span data-ttu-id="20be0-118">Uno o más troncos que desea asignar a la ruta.</span><span class="sxs-lookup"><span data-stu-id="20be0-118">One or more trunks that you want to assign to the route.</span></span>

  - <span data-ttu-id="20be0-119">Los registros de uso de RTC que los usuarios deben tener para llamar a los números que coinciden con la expresión regular del número de teléfono de destino.</span><span class="sxs-lookup"><span data-stu-id="20be0-119">The PSTN usage records that users must have in order to call numbers matching the destination phone number regular expression.</span></span>

<span data-ttu-id="20be0-120">Puede especificar rutas de llamadas en el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="20be0-120">You can specify call routes in the Lync Server Control Panel.</span></span> <span data-ttu-id="20be0-121">Estas rutas de llamadas rellenan la tabla de enrutamiento del servidor, que Lync Server usa para enrutar las llamadas dirigidas a la RTC.</span><span class="sxs-lookup"><span data-stu-id="20be0-121">These call routes populate the server routing table, which Lync Server uses to route calls that are destined for the PSTN.</span></span>

<div>

## <a name="mn-trunk-support"></a><span data-ttu-id="20be0-122">Compatibilidad con troncos M:N</span><span class="sxs-lookup"><span data-stu-id="20be0-122">M:N Trunk Support</span></span>

<span data-ttu-id="20be0-123">Lync Server proporciona flexibilidad en la forma en que las llamadas se enrutan a la RTC.</span><span class="sxs-lookup"><span data-stu-id="20be0-123">Lync Server provides flexibility in how calls are routed to the PSTN.</span></span> <span data-ttu-id="20be0-124">Una ruta de voz especifica un conjunto de troncos a la RTC que se pueden usar para una llamada de voz en particular.</span><span class="sxs-lookup"><span data-stu-id="20be0-124">A voice route specifies a set of trunks to the PSTN that can be used for a particular voice call.</span></span> <span data-ttu-id="20be0-125">Un tronco asocia un servidor de mediación y un número de puerto con una puerta de enlace RTC y un número de puerto de escucha.</span><span class="sxs-lookup"><span data-stu-id="20be0-125">A trunk associates a Mediation Server and a port number with a PSTN gateway and listening port number.</span></span> <span data-ttu-id="20be0-126">Esta asociación lógica permite asociar un servidor de mediación con varias puertas de enlace y tener varias conexiones a la misma puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="20be0-126">This logical association enables a Mediation Server to be associated with multiple gateways and have multiple connections to the same gateway.</span></span> <span data-ttu-id="20be0-127">Al definir una ruta de llamada, se especifican los troncos asociados con dicha ruta, pero no se especifica qué servidores de mediación están asociados a la ruta.</span><span class="sxs-lookup"><span data-stu-id="20be0-127">When defining a call route, you specify the trunks associated with that route, but you do not specify which Mediation Servers are associated with the route.</span></span> <span data-ttu-id="20be0-128">Para crear troncos mediante la definición de las relaciones entre los servidores de mediación y las puertas de enlace RTC, las IP-PBX y los controladores de borde de sesión (SBC), use el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="20be0-128">To create trunks by defining the relationships between Mediation Servers and PSTN gateways, IP-PBXs, and Session Border Controllers (SBCs), use the Topology Builder.</span></span>

</div>

<div>

## <a name="least-cost-routing"></a><span data-ttu-id="20be0-129">Enrutamiento de Least-Cost</span><span class="sxs-lookup"><span data-stu-id="20be0-129">Least-Cost Routing</span></span>

<span data-ttu-id="20be0-130">La capacidad de especificar los troncos a los que se redirigen varios números le permite determinar qué rutas incurren en el menor costo y las implementan en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="20be0-130">The ability to specify the trunks to which various numbers are routed enables you to determine which routes incur the lowest costs and implement them accordingly.</span></span> <span data-ttu-id="20be0-131">La regla general en la selección de troncos es elegir el tronco con la puerta de enlace más cercana a la ubicación del número de destino con el fin de minimizar los gastos de larga distancia.</span><span class="sxs-lookup"><span data-stu-id="20be0-131">The general rule in selecting trunks is to choose the trunk with the closest gateway to the location of the destination number in order to minimize long-distance charges.</span></span> <span data-ttu-id="20be0-132">Por ejemplo, si se encuentran en Nueva York y se llama a un número en Roma, se llevará a cabo la llamada a través de la red IP al tronco con la puerta de enlace en la oficina de la Roma, por lo que incurre en una carga solo para una llamada local.</span><span class="sxs-lookup"><span data-stu-id="20be0-132">For example, if you are in New York and calling a number in Rome, you would carry the call over the IP network to the trunk with the gateway in your Rome office, thereby incurring a charge only for a local call.</span></span>

<span data-ttu-id="20be0-133">Para obtener un ejemplo de cómo se puede usar el enrutamiento menos costoso, tenga en cuenta lo siguiente: fabrikam decide habilitar a los usuarios alemanes para marcar números de Estados Unidos mediante el tronco de Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="20be0-133">For an example of how least-cost routing might be used, consider the following: Fabrikam decides to enable German users to dial U.S. numbers by using the U.S. trunk.</span></span> <span data-ttu-id="20be0-134">Fabrikam también desea configurar el sistema para que todas las llamadas de los usuarios de Lync Server de Estados Unidos a Alemania y países o regiones adyacentes terminen en el tronco con la puerta de enlace en Alemania.</span><span class="sxs-lookup"><span data-stu-id="20be0-134">Fabrikam also wants to configure the system so that all calls from U.S. Lync Server users to Germany and adjacent countries/regions terminate on the trunk with the gateway in Germany.</span></span> <span data-ttu-id="20be0-135">Este enrutamiento ahorrará dinero, ya que una llamada de Alemania a Austria, por ejemplo, es menos costosa que una llamada de Estados Unidos a Austria.</span><span class="sxs-lookup"><span data-stu-id="20be0-135">This routing will save money, because a call from Germany to Austria, for example, is less expensive than a call from the U.S. to Austria.</span></span>

</div>

<div>

## <a name="translating-outbound-dial-strings"></a><span data-ttu-id="20be0-136">Traducción de las cadenas de marcado salientes</span><span class="sxs-lookup"><span data-stu-id="20be0-136">Translating Outbound Dial Strings</span></span>

<span data-ttu-id="20be0-137">Lync Server 2013, al igual que sus predecesoras inmediatas, requiere que todas las cadenas de marcado se puedan normalizar al formato E. 164 con el propósito de realizar la búsqueda inversa de números (RNL).</span><span class="sxs-lookup"><span data-stu-id="20be0-137">Lync Server 2013, like its immediate predecessors, requires all dial strings to be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="20be0-138">Para los troncos con puertas de enlace o centrales de conmutación (PBX) que requieran números traducidos en formatos de marcado locales, Lync Server 2013 permite crear una o más reglas que ayuden a manipular el número llamado (es decir, el URI de solicitud) antes de enrutarlo al tronco.</span><span class="sxs-lookup"><span data-stu-id="20be0-138">For trunks with gateways or private branch exchanges (PBXs) that require numbers translated in local dialing formats, Lync Server 2013 enables you to create one or more rules that assist in manipulating the called number (i.e. Request URI) prior to routing it to the trunk.</span></span> <span data-ttu-id="20be0-139">Por ejemplo, podría escribir una regla para quitar + 44 del encabezado de una cadena de marcado y reemplazarla por 0144.</span><span class="sxs-lookup"><span data-stu-id="20be0-139">For example, you could write a rule to remove +44 from the head of a dial string and replace it with 0144.</span></span>

<span data-ttu-id="20be0-140">Con Lync Server 2013, es posible crear una o más reglas que ayuden a manipular el número de llamada antes de enrutarlo al tronco.</span><span class="sxs-lookup"><span data-stu-id="20be0-140">With Lync Server 2013, it is possible to create one or more rules that assist in manipulating the calling number prior to routing it to the trunk.</span></span>

<span data-ttu-id="20be0-141">En la planeación de los troncos que asocian puertas de enlace: pares de puertos con servidor de mediación: pares de puertos, puede ser útil agrupar los troncos con requisitos de marcado local similares y, por tanto, reducir el número de reglas de conversión necesarias y el tiempo que se tarda en escribirlas.</span><span class="sxs-lookup"><span data-stu-id="20be0-141">In planning your trunks that associate gateways:port pairs with Mediation Server:port pairs, it may be useful to group trunks with similar local dialing requirements, and therefore reduce the number of required translation rules and the time it takes to write them.</span></span>

</div>

<div>

## <a name="configuring-caller-id"></a><span data-ttu-id="20be0-142">Configuración del identificador de llamada</span><span class="sxs-lookup"><span data-stu-id="20be0-142">Configuring Caller ID</span></span>

<span data-ttu-id="20be0-143">Lync Server proporciona una forma de manipular el identificador de llamada para las llamadas salientes.</span><span class="sxs-lookup"><span data-stu-id="20be0-143">Lync Server provides a way to manipulate the caller ID for outbound calls.</span></span> <span data-ttu-id="20be0-144">Por ejemplo, si una organización desea enmascarar las extensiones de marcado directo de los empleados y reemplazarlas por el número genérico Corporate o departamental, un administrador puede hacerlo mediante el panel de control de Lync Server para suprimir el identificador de llamada y reemplazarlo por un identificador de llamada alternativo especificado.</span><span class="sxs-lookup"><span data-stu-id="20be0-144">For example, if an organization wants to mask employees’ direct-dial extensions and replace them with the generic corporate or departmental number, an administrator can do that by using Lync Server Control Panel to suppress the caller ID and replace it with a specified alternative caller ID.</span></span> <span data-ttu-id="20be0-145">En planear la lógica de enrutamiento, tenga en cuenta qué individuos, grupos y sitios desea que tenga esta opción (quizá, incluso, para todos los empleados).</span><span class="sxs-lookup"><span data-stu-id="20be0-145">In planning your routing logic, consider which individuals, groups, sites you’ll want this option for—perhaps, even, for all employees.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="20be0-146">Para las llamadas que se redirigen a través de la RTC, se presentará el identificador de llamada genérico en lugar del identificador de llamada original.</span><span class="sxs-lookup"><span data-stu-id="20be0-146">For calls that are rerouted over the PSTN, the generic caller ID will be presented instead of the original caller ID.</span></span> <span data-ttu-id="20be0-147">Esto puede hacer que la llamada para omitir no moleste o la configuración de privacidad que el destinatario de la llamada haya configurado.</span><span class="sxs-lookup"><span data-stu-id="20be0-147">This can cause the call to bypass Do Not Disturb or privacy settings that the callee may have configured.</span></span>



</div>

</div>

<div>

## <a name="additional-routing-logic"></a><span data-ttu-id="20be0-148">Lógica de enrutamiento adicional</span><span class="sxs-lookup"><span data-stu-id="20be0-148">Additional Routing Logic</span></span>

<span data-ttu-id="20be0-149">Al crear rutas de llamadas salientes, debe tener en cuenta los siguientes factores que pueden afectar a la lógica de enrutamiento:</span><span class="sxs-lookup"><span data-stu-id="20be0-149">In creating outbound call routes, you should be aware of the following factors that can affect routing logic:</span></span>

  - <span data-ttu-id="20be0-150">Cuando se establece una llamada a través de un límite federado, la parte de dominio del URI se usa para enrutar la llamada a la empresa que es responsable de aplicar la lógica de enrutamiento de salida.</span><span class="sxs-lookup"><span data-stu-id="20be0-150">Where a call is established over a federated boundary, the domain portion of the URI is used to route the call over to the enterprise that is responsible for applying the outbound routing logic.</span></span>

  - <span data-ttu-id="20be0-151">Si la parte de dominio del URI de la solicitud no contiene un dominio compatible para la empresa, el componente de enrutamiento de salida en el servidor no procesa la llamada.</span><span class="sxs-lookup"><span data-stu-id="20be0-151">If the domain portion of the request URI does not contain a supported domain for the enterprise, the outbound routing component on the server does not process the call.</span></span>

  - <span data-ttu-id="20be0-152">Si un usuario no está habilitado para telefonía IP empresarial, el servidor aplicará otra lógica de enrutamiento, según corresponda.</span><span class="sxs-lookup"><span data-stu-id="20be0-152">If a user is not enabled for Enterprise Voice, the server applies other routing logic, as appropriate.</span></span>

  - <span data-ttu-id="20be0-153">Si una llamada se redirige a una puerta de enlace que está completamente ocupada (todas las líneas troncales están ocupadas), la puerta de enlace rechaza la llamada y la lógica de enrutamiento de salida redirige la llamada a la siguiente-menos costosa ruta.</span><span class="sxs-lookup"><span data-stu-id="20be0-153">If a call is routed to a gateway that is fully occupied (all trunk lines are busy), the gateway rejects the call and the outbound routing logic redirects the call to the next-least-cost route.</span></span> <span data-ttu-id="20be0-154">Preste especial atención, ya que el tamaño de una puerta de enlace para una oficina pequeña del extranjero (por ejemplo, Zurich) puede llevar una cantidad importante de tráfico no local para las llamadas internacionales a Suiza.</span><span class="sxs-lookup"><span data-stu-id="20be0-154">Give this careful consideration, because a gateway sized for a small office overseas (for example, Zurich) may actually carry a significant amount of nonlocal traffic for international calls to Switzerland.</span></span> <span data-ttu-id="20be0-155">Si la puerta de enlace no tiene el tamaño correcto para este tráfico adicional, las llamadas a Suiza pueden enrutarse a través de una puerta de enlace en Alemania, lo que da como resultado mayores gastos de llamadas.</span><span class="sxs-lookup"><span data-stu-id="20be0-155">If the gateway is not correctly sized for this additional traffic, calls to Switzerland may be routed by way of a gateway in Germany, resulting in larger toll charges.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

