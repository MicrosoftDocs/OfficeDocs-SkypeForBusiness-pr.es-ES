---
title: 'Lync Server 2013: requisitos de resistencia de sitios de sucursal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency requirements
ms:assetid: a570922c-52bd-42d7-bd64-226578b3d110
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412772(v=OCS.15)
ms:contentKeyID: 48184984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 563179eb5933a6f2c1ab996fb1e20c7b047a2ae3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031034"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-requirements-for-lync-server-2013"></a><span data-ttu-id="9cfbf-102">Requisitos de resistencia de sitios de sucursal para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9cfbf-102">Branch-site resiliency requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9cfbf-103">_**Última modificación del tema:** 2014-02-25_</span><span class="sxs-lookup"><span data-stu-id="9cfbf-103">_**Topic Last Modified:** 2014-02-25_</span></span>

<span data-ttu-id="9cfbf-104">Este tema le ayudará a preparar a los usuarios para la resistencia del sitio de sucursal y la supervivencia del correo de voz, y también especifica los requisitos de hardware y software relevantes.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-104">This topic will help you to prepare users for branch-site resiliency and voice mail survivability, and also specifies the relevant hardware and software requirements.</span></span>

<div>

## <a name="preparing-branch-users-for-branch-site-resiliency"></a><span data-ttu-id="9cfbf-105">Preparación de usuarios de sucursal para la resistencia de sitios de sucursal</span><span class="sxs-lookup"><span data-stu-id="9cfbf-105">Preparing Branch Users for Branch-Site Resiliency</span></span>

<span data-ttu-id="9cfbf-106">Preparar a los usuarios para la resistencia de sitios de sucursal mediante la configuración de su grupo de registrador como aplicación de sucursal con funciones de supervivencia (SBA) o servidor de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-106">Prepare users for branch-site resiliency by setting their Registrar pool as the Survivable Branch Appliance (SBA) or Survivable Branch Server.</span></span>

<div>

## <a name="registrar-assignments-for-branch-users"></a><span data-ttu-id="9cfbf-107">Registrar asignaciones para usuarios de sucursal</span><span class="sxs-lookup"><span data-stu-id="9cfbf-107">Registrar Assignments for Branch Users</span></span>

<span data-ttu-id="9cfbf-108">Independientemente de la solución de resistencia de sitios de sucursal que elija, tendrá que asignar un registrador principal a cada usuario.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-108">Regardless of which branch-site resiliency solution you choose, you will need to assign a primary Registrar to each user.</span></span> <span data-ttu-id="9cfbf-109">Los usuarios de sitios de sucursal siempre deben registrarse con el registrador en el sitio de sucursal, independientemente de si el registrador reside en la aplicación de sucursal con funciones de supervivencia, en un servidor de sucursal con funciones de supervivencia o en un servidor de Lync Server 2013 Standard o Enterprise Edition independiente.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-109">Branch site users should always register with the Registrar at the branch site, regardless of whether that Registrar resides in the Survivable Branch Appliance, Survivable Branch Server, or stand-alone Lync Server 2013 Standard or Enterprise Edition server.</span></span> <span data-ttu-id="9cfbf-110">Se necesita un registro de recursos de servicio (SRV) de sistema de nombres de dominio (DNS) para que un cliente pueda detectar su grupo de registradores.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-110">A domain name system (DNS) service (SRV) resource record is required so that a client can discover its Registrar pool.</span></span> <span data-ttu-id="9cfbf-111">Si la aplicación de sucursal con funciones de supervivencia deja de estar disponible, este es el modo en que los clientes del sitio de sucursal detectarán automáticamente el registrador de reserva.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-111">If the Survivable Branch Appliance becomes unavailable, this is how branch site clients will automatically discover the backup Registrar.</span></span>

<span data-ttu-id="9cfbf-112">Si un sitio de sucursal no tiene un servidor DNS, hay dos formas alternativas de configurar la detección de la aplicación de sucursal con funciones de supervivencia o del servidor de sucursal con funciones de supervivencia:</span><span class="sxs-lookup"><span data-stu-id="9cfbf-112">If a branch site does not have a DNS server, there are two alternative ways to configure discovery of the Survivable Branch Appliance or Survivable Branch Server:</span></span>

  - <span data-ttu-id="9cfbf-113">Configure la opción de DHCP 120 en el servidor de protocolo de configuración dinámica de host (DHCP) del sitio de sucursal para que apunte al nombre de dominio completo (FQDN) de la aplicación de sucursal con funciones de supervivencia o del servidor de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-113">Configure DHCP option 120 on the branch site’s Dynamic Host Configuration Protocol (DHCP) server to point to the fully qualified domain name (FQDN) of the Survivable Branch Appliance or Survivable Branch Server.</span></span>

  - <span data-ttu-id="9cfbf-114">Configure la aplicación de sucursal con funciones de supervivencia o el servidor de sucursal con funciones de supervivencia para responder a las consultas DHCP 120.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-114">Configure the Survivable Branch Appliance or Survivable Branch Server to respond to DHCP 120 queries.</span></span>

</div>

<div>

## <a name="voice-routing-for-branch-users"></a><span data-ttu-id="9cfbf-115">Enrutamiento de voz para usuarios de sucursal</span><span class="sxs-lookup"><span data-stu-id="9cfbf-115">Voice Routing for Branch Users</span></span>

<span data-ttu-id="9cfbf-116">Le recomendamos que cree una directiva de protocolo de voz sobre IP (VoIP) de nivel de usuario independiente para los usuarios de un sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-116">We recommend that you create a separate user-level Voice over Internet Protocol (VoIP) policy for users in a branch site.</span></span> <span data-ttu-id="9cfbf-117">Esta Directiva debe incluir una ruta principal que use la aplicación de sucursal con funciones de supervivencia o la puerta de enlace del servidor de sucursal, y una o varias rutas de copia de seguridad que usen un tronco con una puerta de enlace de red telefónica conmutada (RTC) en el sitio central.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-117">This policy should include a primary route that uses the Survivable Branch Appliance or branch server gateway, and one or more backup routes that use a trunk with a public switched telephone network (PSTN) gateway at the central site.</span></span> <span data-ttu-id="9cfbf-118">Si la ruta principal no está disponible, se usa en su lugar la ruta de la copia de seguridad que usa una o más puertas de enlace de sitio central.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-118">If the primary route is unavailable, the backup route that uses one or more central site gateways is used instead.</span></span> <span data-ttu-id="9cfbf-119">De este modo, independientemente de dónde esté registrado un usuario (en el registrador de sitios de sucursal o del grupo de registrador de reserva en el sitio central), la Directiva de VoIP del usuario siempre está en vigor.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-119">This way, regardless of where a user is registered—on the branch site Registrar or the backup Registrar pool at the central site—the user’s VoIP policy is always in effect.</span></span> <span data-ttu-id="9cfbf-120">Esta es una consideración importante para los escenarios de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-120">This is an important consideration for failover scenarios.</span></span> <span data-ttu-id="9cfbf-121">Por ejemplo, si necesita cambiar el nombre de la aplicación de sucursal con funciones de supervivencia o reconfigurar la aplicación de sucursal con funciones de supervivencia para conectarse a un grupo de registradores de copia de seguridad en el sitio central, debe mover a los usuarios del sitio de sucursal al sitio central durante el período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-121">For example, if you need to rename the Survivable Branch Appliance or reconfigure the Survivable Branch Appliance to connect to a backup Registrar pool at the central site, then you must move branch site users to the central site for the duration.</span></span> <span data-ttu-id="9cfbf-122">(Para obtener más información sobre cómo cambiar el nombre o volver a configurar una aplicación de sucursal con funciones de supervivencia, consulte [Apéndice B: administración de una aplicación de sucursal con funciones de supervivencia en Lync Server 2013](lync-server-2013-appendix-b-managing-a-survivable-branch-appliance.md) en la documentación de implementación). Si esos usuarios no tienen directivas de VoIP en el nivel de usuario o planes de marcado de nivel de usuario, cuando los usuarios se mueven a otro sitio, las directivas VoIP de nivel de sitio y los planes de marcado de nivel de sitio del sitio central se aplican a los usuarios de forma predeterminada, en lugar de los planes de marcado y las directivas VoIP de nivel de sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-122">(For details about renaming or reconfiguring a Survivable Branch Appliance, see [Appendix B: Managing a Survivable Branch Appliance in Lync Server 2013](lync-server-2013-appendix-b-managing-a-survivable-branch-appliance.md) in the Deployment documentation.) If those users do not have user-level VoIP policies or user-level dial plans, when the users are moved to another site, the site-level VoIP policies and site-level dial plans of the central site apply to the users by default, instead of the branch site site-level VoIP policies and dial plans,.</span></span> <span data-ttu-id="9cfbf-123">En este escenario, a menos que las directivas VoIP de nivel de sitio y los planes de marcado de nivel de sitio que usa el grupo de registrador de reserva también se apliquen a los usuarios del sitio de sucursal, se producirá un error en sus llamadas.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-123">In this scenario, unless the site-level VoIP policies and site-level dial plans used by the backup Registrar pool can also apply to the branch site users, their calls will fail.</span></span> <span data-ttu-id="9cfbf-124">Por ejemplo, si los usuarios de un sitio de sucursal ubicados en Japón se mueven a un sitio central en Redmond, un plan de marcado con reglas de normalización que anteponga + 1425 a todas las llamadas de 7 dígitos es improbable que las llamadas a dichos usuarios se traduzcan correctamente.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-124">For example, if users from a branch site located in Japan are moved to a central site in Redmond, then a dial plan with normalization rules that prepend +1425 to all 7-digit calls is unlikely to appropriately translate calls for those users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9cfbf-125">Al crear una ruta de copia de seguridad de sucursal, se recomienda agregar dos registros de uso de teléfono RTC a la Directiva de usuario de sucursal y asignar rutas independientes a cada uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-125">When you create a branch office backup route, we recommend that you add two PSTN phone usage records to the branch office user policy and assign separate routes to each one.</span></span> <span data-ttu-id="9cfbf-126">La primera, o principal, dirige las llamadas a la puerta de enlace asociada con la aplicación de sucursal con funciones de supervivencia (SBA) o el servidor de sucursal; la segunda, o la ruta de la copia de seguridad, dirige las llamadas a la puerta de enlace en el sitio central.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-126">The first, or primary, route would direct calls to the gateway associated with the Survivable Branch Appliance (SBA) or branch server; the second, or backup, route would direct calls to the gateway at the central site.</span></span> <span data-ttu-id="9cfbf-127">En las llamadas directas, el servidor SBA o Branch intentará todas las rutas asignadas al primer registro de uso de RTC antes de intentar el segundo registro de uso.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-127">In directing calls, the SBA or branch server will attempt all routes assigned to the first PSTN usage record before attempting the second usage record.</span></span>



</div>

<span data-ttu-id="9cfbf-128">Para ayudar a garantizar que las llamadas entrantes a los usuarios de sitios de sucursal llegarán a los usuarios cuando la puerta de enlace de sucursal o el componente de Windows del sitio de aplicación de sucursal con funciones de supervivencia no estén disponibles (lo que ocurriría, por ejemplo, si la aplicación de sucursal o sucursal con funciones de supervivencia la puerta de enlace no estaba disponible para el mantenimiento), cree una ruta de conmutación por error en la puerta de enlace (o trabaje con su proveedor de marcado hacia adentro directo) para redirigir las llamadas entrantes al grupo de registrador de reserva en el sitio central.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-128">To help ensure that inbound calls to branch site users will reach those users when the branch gateway or the Windows component of the Survivable Branch Appliance site is unavailable (which would happen, for example, if the Survivable Branch Appliance or branch gateway were down for maintenance), create a failover route on the gateway (or work with your Direct Inward Dialing (DID) provider) to redirect incoming calls to the backup Registrar pool at the central site.</span></span> <span data-ttu-id="9cfbf-129">Desde allí, las llamadas se enrutarán a través del vínculo WAN a los usuarios de la sucursal.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-129">From there, the calls will be routed over the WAN link to branch users.</span></span> <span data-ttu-id="9cfbf-130">Asegúrese de que la ruta traduce los números para que se ajusten a la puerta de enlace RTC o a otros formatos de número de teléfono aceptado del interlocutor del tronco.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-130">Be sure that the route translates numbers to comply with the PSTN gateway or other trunk peer’s accepted phone number formats.</span></span> <span data-ttu-id="9cfbf-131">Para obtener información detallada sobre cómo crear una ruta de conmutación por error, consulte [configuración de una ruta de conmutación por error en Lync Server 2013](lync-server-2013-configuring-a-failover-route.md).</span><span class="sxs-lookup"><span data-stu-id="9cfbf-131">For details about creating a failover route, see [Configuring a failover route in Lync Server 2013](lync-server-2013-configuring-a-failover-route.md).</span></span> <span data-ttu-id="9cfbf-132">Cree también planes de marcado de nivel de servicio para el tronco asociado con la puerta de enlace en el sitio de sucursal para normalizar las llamadas entrantes.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-132">Also create service-level dial plans for the trunk associated with the gateway at the branch site to normalize incoming calls.</span></span> <span data-ttu-id="9cfbf-133">Si tiene dos aplicaciones de sucursal con funciones de supervivencia en un sitio de sucursal, puede crear un plan de marcado de nivel de sitio para ambas, a menos que sea necesario un plan de nivel de servicio independiente para cada uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-133">If you have two Survivable Branch Appliances at a branch site, you can create a site-level dial plan for both unless a separate service-level plan for each is necessary.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9cfbf-134">Para tener en cuenta el consumo de recursos del sitio central por parte de los usuarios de sitios de sucursal que dependen del sitio central para la presencia, la Conferencia o la conmutación por error, se recomienda considerar a cada usuario del sitio de sucursal como si el usuario estuviera registrado en el sitio central.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-134">To account for the consumption of central site resources by any branch site users that rely on the central site for presence, conferencing, or failover, we recommend that you consider each branch site user as if the user were registered with the central site.</span></span> <span data-ttu-id="9cfbf-135">Actualmente no hay ningún límite en el número de usuarios del sitio de sucursal, incluidos los usuarios registrados con una aplicación de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-135">There are currently no limits on the number of branch site users, including users registered with a Survivable Branch Appliance.</span></span>



</div>

<span data-ttu-id="9cfbf-136">También se recomienda crear un plan de marcado de nivel de usuario y una directiva de voz y, a continuación, asignarlo a los usuarios del sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-136">We also recommend that you create a user-level dial plan and voice policy, and then assign it to branch site users.</span></span> <span data-ttu-id="9cfbf-137">Para obtener más información, consulte [crear un plan de marcado en Lync server 2013](lync-server-2013-create-a-dial-plan.md) y [crear la Directiva de enrutamiento VoIP para usuarios de sucursal en Lync Server 2013](lync-server-2013-create-the-voip-routing-policy-for-branch-users.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-137">For details, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) and [Create the VoIP routing policy for branch users in Lync Server 2013](lync-server-2013-create-the-voip-routing-policy-for-branch-users.md) in the Deployment documentation.</span></span>

<div>

## <a name="routing-extension-numbers"></a><span data-ttu-id="9cfbf-138">Números de extensión de enrutamiento</span><span class="sxs-lookup"><span data-stu-id="9cfbf-138">Routing Extension Numbers</span></span>

<span data-ttu-id="9cfbf-139">Al preparar planes de marcado y directivas de voz para usuarios de sitios de sucursal, asegúrese de incluir reglas de normalización y reglas de conversión que coinciden con las cadenas y el formato de número que se usan en el atributo msRTCSIP-line (o URI de línea), de modo que las llamadas de Lync 2013 a habilitada entre bifurcación los usuarios del sitio y los usuarios del sitio central se enrutarán correctamente, especialmente cuando las llamadas se deben desviar a través de la RTC porque el vínculo WAN no está disponible.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-139">When preparing dial plans and voice policies for branch site users, be sure to include normalization rules and translation rules that match the strings and number format used in the msRTCSIP-line (or Line URI) attribute, so that Lync 2013 calls enabled between branch site users and central site users will be routed correctly—particularly when calls must be rerouted over the PSTN because the WAN link is unavailable.</span></span> <span data-ttu-id="9cfbf-140">Además, hay consideraciones especiales para los números marcados que incluyen números de extensión, en lugar de números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-140">Additionally, there are special considerations for dialed numbers that include extension numbers, rather just phone numbers.</span></span>

<span data-ttu-id="9cfbf-141">Reglas de normalización y traducciones que coinciden con los URI de línea que contienen un número de extensión, ya sea en exclusiva o además de un número de teléfono E. 164 completo, tienen requisitos adicionales.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-141">Normalization rules and translations rules that match Line URIs that contain an extension number, whether exclusively or in addition to a full E.164 phone number, have additional requirements.</span></span> <span data-ttu-id="9cfbf-142">En esta sección se describen varios escenarios de ejemplo para enrutar las llamadas de URI de línea con un número de extensión.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-142">This section describes several example scenarios to route calls for Line URIs with an extension number.</span></span>

<span data-ttu-id="9cfbf-143">Si su organización no tiene números de teléfono de marcado directo (DID) configurados para usuarios individuales y el URI de línea de cada usuario está configurado *solo* con un número de extensión, los usuarios internos pueden llamarse a otro marcando solo un número de extensión.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-143">If your organization does not have Direct Inward Dial (DID) phone numbers configured for individual users and the Line URI of each user is configured with *only* an extension number, internal users can call one another by dialing only an extension number.</span></span> <span data-ttu-id="9cfbf-144">Sin embargo, debe configurar las reglas de normalización que se pueden aplicar a las llamadas de un usuario de sitio de sucursal a un usuario del sitio central, que coinciden con los números de extensión.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-144">However, you must configure normalization rules that can apply to calls from a branch site user to a central site user, that match the extension numbers.</span></span>

<span data-ttu-id="9cfbf-145">En un escenario en el que el vínculo WAN entre un sitio de sucursal y un sitio central está disponible, las llamadas de los usuarios de sitios de sucursal a los usuarios de sitios centrales no requieren la regla de normalización de coincidencia para traducir el número, ya que la llamada no se enruta a través de la RTC.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-145">In a scenario where the WAN link between a branch site and a central site is available, calls from branch site users to central site users do not require the matching normalization rule to translate the number because the call is not routed over the PSTN.</span></span> <span data-ttu-id="9cfbf-146">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9cfbf-146">For example:</span></span>


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9cfbf-147">Nombre de regla</span><span class="sxs-lookup"><span data-stu-id="9cfbf-147">Rule name</span></span></th>
<th><span data-ttu-id="9cfbf-148">Descripción</span><span class="sxs-lookup"><span data-stu-id="9cfbf-148">Description</span></span></th>
<th><span data-ttu-id="9cfbf-149">Modelo de número</span><span class="sxs-lookup"><span data-stu-id="9cfbf-149">Number pattern</span></span></th>
<th><span data-ttu-id="9cfbf-150">Translation</span><span class="sxs-lookup"><span data-stu-id="9cfbf-150">Translation</span></span></th>
<th><span data-ttu-id="9cfbf-151">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9cfbf-151">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9cfbf-152">5digitExtensions</span><span class="sxs-lookup"><span data-stu-id="9cfbf-152">5digitExtensions</span></span></p></td>
<td><p><span data-ttu-id="9cfbf-153">No traduce números de 5 dígitos</span><span class="sxs-lookup"><span data-stu-id="9cfbf-153">Does not translate 5-digit numbers</span></span></p></td>
<td><p><span data-ttu-id="9cfbf-154">^ (\d{5}) $</span><span class="sxs-lookup"><span data-stu-id="9cfbf-154">^(\d{5})$</span></span></p></td>
<td><p><span data-ttu-id="9cfbf-155">$1</span><span class="sxs-lookup"><span data-stu-id="9cfbf-155">$1</span></span></p></td>
<td><p><span data-ttu-id="9cfbf-156">10001 no se traduce</span><span class="sxs-lookup"><span data-stu-id="9cfbf-156">10001 is not translated</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9cfbf-157">También debe acomodar los números de extensión para escenarios específicos, como cuando el vínculo WAN entre un sitio de sucursal y el sitio central no está disponible y una llamada desde un sitio de sucursal debe enrutarse a través de la RTC.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-157">You must also accommodate extension numbers for specific scenarios, such as when the WAN link between a branch site and central site is unavailable and a call from a branch site must be routed over the PSTN.</span></span> <span data-ttu-id="9cfbf-158">Durante una interrupción de la WAN, si un usuario del sitio de sucursal solo llama a un usuario del sitio central mediante la marcación de la extensión del usuario del sitio central, debe tener una regla de conversión de salida que agregue el número de teléfono completo del usuario del sitio central.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-158">During a WAN outage, if a branch site user calls a central site user only by dialing the central site user’s extension, you must have an outbound translation rule that adds the central site user’s full phone number.</span></span> <span data-ttu-id="9cfbf-159">Si el URI de línea de un usuario contiene el número de teléfono completo de la organización y el número de extensión único del usuario en lugar de un número de teléfono completo único para el usuario, debe tener una regla de conversión de salida que agregue el número de teléfono completo de la organización en su lugar. .</span><span class="sxs-lookup"><span data-stu-id="9cfbf-159">If a user’s Line URI contains your organization’s full phone number and the user’s unique extension number instead of a full phone number that is unique to the user, then you must have an outbound translation rule that adds your organization’s full phone number instead.</span></span> <span data-ttu-id="9cfbf-160">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9cfbf-160">For example:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9cfbf-161">Descripción</span><span class="sxs-lookup"><span data-stu-id="9cfbf-161">Description</span></span></th>
<th><span data-ttu-id="9cfbf-162">Modelo de coincidencia</span><span class="sxs-lookup"><span data-stu-id="9cfbf-162">Matching pattern</span></span></th>
<th><span data-ttu-id="9cfbf-163">Translation</span><span class="sxs-lookup"><span data-stu-id="9cfbf-163">Translation</span></span></th>
<th><span data-ttu-id="9cfbf-164">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9cfbf-164">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9cfbf-165">Traduce números de 5 dígitos al número de teléfono y la extensión de un usuario</span><span class="sxs-lookup"><span data-stu-id="9cfbf-165">Translates 5-digit numbers to a user’s phone number and extension</span></span></p></td>
<td><p><span data-ttu-id="9cfbf-166">^ (\d{5}) $</span><span class="sxs-lookup"><span data-stu-id="9cfbf-166">^(\d{5})$</span></span></p></td>
<td><p><span data-ttu-id="9cfbf-167">+ 14255550123; EXT = $1</span><span class="sxs-lookup"><span data-stu-id="9cfbf-167">+14255550123;ext=$1</span></span></p></td>
<td><p><span data-ttu-id="9cfbf-168">10001 se convierte en + 14255550123; ext = 10001</span><span class="sxs-lookup"><span data-stu-id="9cfbf-168">10001 is translated to +14255550123;ext=10001</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9cfbf-169">Traduce números de 5 dígitos al número de teléfono de la organización y a la extensión de un usuario</span><span class="sxs-lookup"><span data-stu-id="9cfbf-169">Translates 5-digit numbers to your organization’s phone number and a user’s extension</span></span></p></td>
<td><p><span data-ttu-id="9cfbf-170">^ (\d{5}) $</span><span class="sxs-lookup"><span data-stu-id="9cfbf-170">^(\d{5})$</span></span></p></td>
<td><p><span data-ttu-id="9cfbf-171">+ 14255550100; EXT = $1</span><span class="sxs-lookup"><span data-stu-id="9cfbf-171">+14255550100;ext=$1</span></span></p></td>
<td><p><span data-ttu-id="9cfbf-172">10001 se convierte en + 14255550100; ext = 10001</span><span class="sxs-lookup"><span data-stu-id="9cfbf-172">10001 is translated to +14255550100;ext=10001</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9cfbf-173">En este escenario, si el tronco del mismo nivel que controla el redireccionamiento a la RTC no admite números de extensión, la regla de conversión de salida también debe quitar el número de extensión.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-173">In this scenario, if the trunk peer that handles rerouting to the PSTN does not support extension numbers, then the outbound translation rule must also remove the extension number.</span></span> <span data-ttu-id="9cfbf-174">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9cfbf-174">For example:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9cfbf-175">Descripción</span><span class="sxs-lookup"><span data-stu-id="9cfbf-175">Description</span></span></th>
<th><span data-ttu-id="9cfbf-176">Modelo de coincidencia</span><span class="sxs-lookup"><span data-stu-id="9cfbf-176">Matching pattern</span></span></th>
<th><span data-ttu-id="9cfbf-177">Translation</span><span class="sxs-lookup"><span data-stu-id="9cfbf-177">Translation</span></span></th>
<th><span data-ttu-id="9cfbf-178">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9cfbf-178">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9cfbf-179">Quita la extensión de los números de teléfono con extensiones</span><span class="sxs-lookup"><span data-stu-id="9cfbf-179">Removes extension from phone numbers with extensions</span></span></p></td>
<td><p><span data-ttu-id="9cfbf-180">^\+(\d *); EXT = (\d*) $</span><span class="sxs-lookup"><span data-stu-id="9cfbf-180">^\+(\d *);ext=(\d*)$</span></span></p></td>
<td><p><span data-ttu-id="9cfbf-181">+ $1</span><span class="sxs-lookup"><span data-stu-id="9cfbf-181">+$1</span></span></p></td>
<td><p><span data-ttu-id="9cfbf-182">+ 14255550123; ext = 10001 se convierte en + 14255550123</span><span class="sxs-lookup"><span data-stu-id="9cfbf-182">+14255550123;ext=10001 is translated to +14255550123</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9cfbf-183">Si un vínculo WAN está o no disponible, si la organización no tiene los números realizados para usuarios individuales y el URI de línea de un usuario contiene el número de teléfono de la organización y el número de extensión único del usuario, debe configurar el URI de línea de número de teléfono de la organización con un número que es accesible para el tronco del mismo nivel o la puerta de enlace RTC en el sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-183">Whether or not a WAN link is available, if your organization does not have DID numbers configured for individual users and the Line URI for a user contains your organization’s phone number and the user’s unique extension number, then you must configure your organization’s phone number Line URI with a number that is reachable by the trunk peer or PSTN gateway at the branch site.</span></span> <span data-ttu-id="9cfbf-184">También debe configurar el URI de línea de número de teléfono de la organización para que incluya su propia extensión única para que las llamadas se enruten a ese número.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-184">You must also configure your organization’s phone number Line URI to include its own unique extension for calls to be routed to that number.</span></span>

<span data-ttu-id="9cfbf-185">Para obtener información detallada sobre las llamadas realizadas desde un usuario del sitio central a un usuario de un sitio de sucursal cuando no está disponible el vínculo WAN entre los sitios, consulte "preparación para la supervivencia del correo de voz" más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-185">For details about calls from a central site user to a branch site user when the WAN link between the sites is unavailable, see "Preparing for Voice Mail Survivability" later in this topic.</span></span> <span data-ttu-id="9cfbf-186">Para obtener más información sobre los planes de marcado y las reglas de normalización, incluidas otras reglas de ejemplo, consulte [planes de marcado y reglas de normalización en Lync server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) en la documentación de planeación y [configuración de planes de marcado en Lync Server 2013](lync-server-2013-configuring-dial-plans.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-186">For details about dial plans and normalization rules, including other sample rules, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in the Planning documentation and [Configuring dial plans in Lync Server 2013](lync-server-2013-configuring-dial-plans.md) in the Deployment documentation.</span></span> <span data-ttu-id="9cfbf-187">Para obtener más información sobre las reglas de conversión de salida, consulte [reglas de traducción en Lync server 2013](lync-server-2013-translation-rules.md) en la documentación de planeación y [definición de reglas de conversión en Lync Server 2013](lync-server-2013-defining-translation-rules.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-187">For details about outbound translation rules, see [Translation rules in Lync Server 2013](lync-server-2013-translation-rules.md) in the Planning documentation and [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>

</div>

</div>

</div>

<div>

## <a name="preparing-for-voice-mail-survivability"></a><span data-ttu-id="9cfbf-188">Preparación para la supervivencia del correo de voz</span><span class="sxs-lookup"><span data-stu-id="9cfbf-188">Preparing for Voice Mail Survivability</span></span>

<span data-ttu-id="9cfbf-189">La mensajería unificada (MU) de Exchange suele instalarse únicamente en un sitio central y no en sitios de sucursal.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-189">Exchange Unified Messaging (UM) is usually installed only at a central site and not at branch sites.</span></span> <span data-ttu-id="9cfbf-190">Un autor de llamada debe poder dejar un mensaje de correo de voz, incluso si el vínculo WAN entre el sitio de sucursal y el sitio central no está disponible.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-190">A caller should be able to leave a voice mail message, even if the WAN link between branch site and central site is unavailable.</span></span> <span data-ttu-id="9cfbf-191">Como resultado, la configuración del URI de línea para el número de teléfono del operador automático de mensajería unificada de Exchange que proporciona correo de voz para los usuarios del sitio de sucursal requiere consideraciones especiales, además de la Directiva de voz, el plan de marcado y las reglas de normalización que se aplican a ese correo de voz números.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-191">As a result, configuring the Line URI for the Exchange UM Auto Attendant phone number that provides voice mail for branch site users requires special considerations, in addition to the voice policy, dial plan, and normalization rules applicable to that voice mail number.</span></span>

<span data-ttu-id="9cfbf-192">Las aplicaciones de sucursal con funciones de supervivencia (las) y servidores de sucursal con funciones de supervivencia proporcionan supervivencia de correo de voz para usuarios de sucursal durante una interrupción de la WAN.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-192">Survivable Branch Appliances (SBAs) and Survivable Branch Servers provide voice mail survivability for branch users during a WAN outage.</span></span> <span data-ttu-id="9cfbf-193">En concreto, si está usando una aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia y la WAN deja de estar disponible, el servidor de sucursal o el servidor de sucursal con funciones de supervivencia redirige las llamadas no respondidas a través de la RTC a la mensajería unificada de Exchange en el sitio central.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-193">Specifically, if you are using a Survivable Branch Appliance or Survivable Branch Server and the WAN becomes unavailable, the SBA or Survivable Branch Server reroutes unanswered calls over the PSTN to Exchange UM at the central site.</span></span> <span data-ttu-id="9cfbf-194">Con una SBA o un servidor de sucursal con funciones de supervivencia, los usuarios también pueden recuperar los mensajes de correo de voz a través de la RTC durante una interrupción de la WAN.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-194">With a SBA or Survivable Branch Server, users can also retrieve voice mail messages through the PSTN during a WAN outage.</span></span> <span data-ttu-id="9cfbf-195">Por último, durante una interrupción de la WAN, la aplicación de sucursal con funciones de supervivencia o el servidor de sucursal con funciones de supervivencia colocan en cola las notificaciones de llamadas perdidas y, después, las carga en el servidor de mensajería unificada de Exchange cuando se restaura la WAN.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-195">Finally, during a WAN outage the Survivable Branch Appliance or Survivable Branch Server queues missed-call notifications and then uploads them to the Exchange UM server when the WAN is restored.</span></span> <span data-ttu-id="9cfbf-196">Para ayudar a garantizar que el reenrutamiento del correo de voz sea resistente, asegúrese de agregar una entrada para el FQDN del grupo de sitios central y una entrada para el FQDN del servidor perimetral al archivo de hosts en el servidor de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-196">To help ensure that voice mail rerouting is resilient, be sure that you add an entry for the central site pool’s FQDN and an entry for the Edge Server FQDN to the hosts file on the Survivable Branch Server.</span></span> <span data-ttu-id="9cfbf-197">De lo contrario, la resolución de DNS puede agotar el tiempo de espera si no dispone de un servidor DNS en el sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-197">Otherwise, DNS resolution can time out if you do not have a DNS server at the branch site.</span></span>

<span data-ttu-id="9cfbf-198">Se recomiendan las siguientes configuraciones para la supervivencia del correo de voz para los usuarios de sitios de sucursal:</span><span class="sxs-lookup"><span data-stu-id="9cfbf-198">We recommend the following configurations for voice mail survivability for branch site users:</span></span>

  - <span data-ttu-id="9cfbf-199">Un administrador de Microsoft Exchange debe configurar el operador automático de mensajería unificada (AA) de Exchange para que sólo acepte mensajes.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-199">An Microsoft Exchange administrator should configure Exchange UM Auto Attendant (AA) to accept messages only.</span></span> <span data-ttu-id="9cfbf-200">Esta configuración deshabilita todas las demás funcionalidades genéricas, como la transferencia a un usuario o la transferencia a un operador, y limita el AA para que solo acepte mensajes.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-200">This configuration disables all other generic functionality, such as transfer to a user or transfer to an operator, and limits the AA to only accepting messages.</span></span> <span data-ttu-id="9cfbf-201">Como alternativa, el administrador de Exchange puede usar un AA genérico o un AA personalizado para enrutar la llamada a un operador.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-201">Alternatively, the Exchange administrator can use a generic AA or an AA customized to route the call to an operator.</span></span>

  - <span data-ttu-id="9cfbf-202">El administrador de Lync Server debe tomar el número de teléfono y usarlo como el número de **operador automático de mensajería unificada de Exchange** en la configuración de reenrutamiento del correo de voz para la aplicación de sucursal o el servidor de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-202">The Lync Server administrator should take the AA phone number and use that phone number as the **exchange um auto attendant** number in the voice mail rerouting settings for the Survivable Branch Appliance or branch server.</span></span>

  - <span data-ttu-id="9cfbf-203">El administrador de Lync Server debe obtener el número de teléfono de acceso de suscriptor de mensajería unificada de Exchange y usar ese número como el número de **acceso de suscriptor** en la configuración de reenrutamiento del correo de voz para la aplicación de sucursal con funciones de supervivencia o el servidor de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-203">The Lync Server administrator should get the Exchange UM subscriber access phone number and use that number as the **subscriber access** number in the voice mail rerouting settings for the Survivable Branch Appliance or Survivable Branch Server.</span></span>

  - <span data-ttu-id="9cfbf-204">El administrador de Lync Server debe configurar la mensajería unificada de Exchange para que solo se asocie un plan de marcado a todos los usuarios de la sucursal que necesiten obtener acceso al correo de voz durante una interrupción de la WAN.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-204">The Lync Server administrator should configure Exchange UM so that only one dial plan is associated with all branch users who need access to voice mail during a WAN outage.</span></span>

  - <span data-ttu-id="9cfbf-205">Cuando el vínculo WAN no está disponible, las llamadas a los usuarios de un sitio de sucursal se pueden enrutar al buzón de voz de mensajería unificada (MU) de Exchange del usuario, pero solo si la Directiva de voz aplicada a la llamada especifica un número de teléfono de correo de voz que es único y no incluye una extensión números.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-205">When the WAN link is unavailable, calls to branch site users can be routed to the user’s Exchange Unified Messaging (UM) voice mailbox, but only if the voice policy applied to the call specifies a voice mail phone number that is unique and does not include an extension number.</span></span>

</div>

<div>

## <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a><span data-ttu-id="9cfbf-206">Requisitos de hardware y software para la resistencia de sitios de sucursal</span><span class="sxs-lookup"><span data-stu-id="9cfbf-206">Hardware and Software Requirements for Branch-Site Resiliency</span></span>

<span data-ttu-id="9cfbf-207">Los requisitos de hardware y software varían en función de la solución de resistencia.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-207">The hardware and software requirements vary, depending on your resiliency solution.</span></span>

<div>

## <a name="requirements-for-survivable-branch-appliances"></a><span data-ttu-id="9cfbf-208">Requisitos para aplicaciones de sucursal con funciones de supervivencia</span><span class="sxs-lookup"><span data-stu-id="9cfbf-208">Requirements for Survivable Branch Appliances</span></span>

<span data-ttu-id="9cfbf-209">El hardware y el software necesarios están integrados en la aplicación de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-209">Required hardware and software is built into the Survivable Branch Appliance.</span></span> <span data-ttu-id="9cfbf-210">Sin embargo, también se recomienda que cada sitio de sucursal implemente un servidor DHCP para obtener las direcciones IP de cliente; de lo contrario, cuando expire la concesión DHCP, los clientes no tendrán conectividad IP.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-210">However, we also recommend that each branch site deploy a DHCP server to obtain client IP addresses; otherwise, when the DHCP lease expires, clients will not have IP connectivity.</span></span>

<span data-ttu-id="9cfbf-211">Si los servidores DNS de empresa solo se encuentran en sitios centrales, los usuarios de sitios de sucursal no podrán conectarse a ellos durante una interrupción de la WAN y, por lo tanto, se producirá un error en la detección de Lync Server que usa el registro de recursos SRV (servicio (SRV) de DNS.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-211">If the enterprise DNS servers are located only in central sites, branch site users will be unable to connect to them during a WAN outage, and therefore Lync Server discovery that uses DNS SRV (service (SRV) resource record) will fail.</span></span> <span data-ttu-id="9cfbf-212">Para garantizar el reenrutamiento de la solicitud durante una interrupción de la WAN, los registros DNS deben almacenarse en caché en el sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-212">To assure prompt rerouting during a WAN outage, DNS records must be cached at the branch site.</span></span> <span data-ttu-id="9cfbf-213">Si el enrutador de sucursal lo admite, active el almacenamiento en caché de DNS.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-213">If the branch router supports it, turn on DNS caching.</span></span> <span data-ttu-id="9cfbf-214">O bien, puede implementar un servidor DNS en la sucursal.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-214">Or, you can deploy a DNS server at the branch.</span></span> <span data-ttu-id="9cfbf-215">Puede ser un servidor independiente o una versión de la aplicación de sucursal con funciones de supervivencia que admita capacidades DNS.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-215">This can be a stand-alone server or a version of the Survivable Branch Appliance that supports DNS capabilities.</span></span> <span data-ttu-id="9cfbf-216">Para obtener más información, póngase en contacto con su proveedor de aplicación de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-216">For details, contact your Survivable Branch Appliance provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9cfbf-217">No es necesario tener un controlador de dominio en un sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-217">It is not necessary to have a domain controller at a branch site.</span></span> <span data-ttu-id="9cfbf-218">La aplicación de sucursal con funciones de supervivencia autentica a los clientes con un certificado especial que envía al cliente en respuesta a la solicitud del certificado del cliente cuando inicia sesión.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-218">The Survivable Branch Appliance authenticates clients by using a special certificate that it sends the client in response to the client’s certificate request when it signs in.</span></span>



</div>

<span data-ttu-id="9cfbf-219">Los clientes de Lync pueden detectar el servidor Lync mediante la opción DHCP 120 (opción registrador SIP).</span><span class="sxs-lookup"><span data-stu-id="9cfbf-219">Lync clients can discover the Lync Server by using DHCP Option 120 (SIP Registrar Option).</span></span> <span data-ttu-id="9cfbf-220">Esto se puede configurar de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="9cfbf-220">This can be configured in one of two ways:</span></span>

  - <span data-ttu-id="9cfbf-221">Configure el servidor DHCP en el sitio de sucursal para responder a las consultas de DHCP 120, que devuelven el FQDN del registrador en la aplicación de sucursal con funciones de supervivencia o el servidor de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-221">Configure the DHCP server at the branch site to reply to DHCP 120 queries, which return the FQDN of the Registrar on the Survivable Branch Appliance or Survivable Branch Server.</span></span>

  - <span data-ttu-id="9cfbf-222">Active el DHCP de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-222">Turn on Lync Server DHCP.</span></span> <span data-ttu-id="9cfbf-223">Cuando esta opción está activada, el registrador de Lync Server responde a la opción DHCP 120 consultas.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-223">When this is turned on, the Lync Server Registrar responds to DHCP Option 120 queries.</span></span> <span data-ttu-id="9cfbf-224">Tenga en cuenta que el registrador no responde a ninguna consulta DHCP distinta de las opciones de DHCP 120.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-224">Note that the Registrar does not respond to any DHCP queries other than DHCP Options 120.</span></span>

<span data-ttu-id="9cfbf-225">Además, en el caso de sitios de sucursal más grandes con varias subredes, los agentes de retransmisión DHCP deben estar habilitados para reenviar la opción DHCP 120 consultas al servidor DHCP (configuración 1) o al registrador (configuración 2).</span><span class="sxs-lookup"><span data-stu-id="9cfbf-225">Additionally, for larger branch sites that have multiple subnets, DHCP relay agents should be enabled to forward DHCP Option 120 queries to the DHCP Server (configuration 1) or to the Registrar (configuration 2).</span></span>

<span data-ttu-id="9cfbf-226">Por último, los usuarios de sitios de sucursal deben estar configurados para telefonía IP empresarial y aprovisionados con un extremo de comunicaciones unificadas adecuado.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-226">Finally, branch site users must be configured for Enterprise Voice and provisioned with an appropriate unified communications endpoint.</span></span>

</div>

<div>

## <a name="requirements-for-survivable-branch-servers"></a><span data-ttu-id="9cfbf-227">Requisitos para servidores de sucursal con funciones de supervivencia</span><span class="sxs-lookup"><span data-stu-id="9cfbf-227">Requirements for Survivable Branch Servers</span></span>

<span data-ttu-id="9cfbf-228">Los requisitos de los servidores de sucursal con funciones de supervivencia son los mismos que para un servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-228">The requirements for Survivable Branch Servers are the same as the requirements for a Front End Server.</span></span> <span data-ttu-id="9cfbf-229">Para obtener más información, consulte [plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-229">For details, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="requirements-for-full-scale-lync-server-branch-site-deployments"></a><span data-ttu-id="9cfbf-230">Requisitos para implementaciones de sitio de sucursal de Lync Server a escala completa</span><span class="sxs-lookup"><span data-stu-id="9cfbf-230">Requirements for Full-Scale Lync Server Branch-Site Deployments</span></span>

<span data-ttu-id="9cfbf-231">Para obtener más información, consulte [determining Your Infrastructure Requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="9cfbf-231">For details, see [Determining your infrastructure requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) in the Planning documentation.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

