---
title: 'Lync Server 2013: Planeación de resistencia de voz de sitio central'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for central site voice resiliency
ms:assetid: 52dd0c3e-cd3c-44cf-bef5-8c49ff5e4c7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398347(v=OCS.15)
ms:contentKeyID: 48184164
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13195c50e88c035b0775d2958cf62cf71f7924c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825145"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-central-site-voice-resiliency-in-lync-server-2013"></a><span data-ttu-id="f6be5-102">Planeación de resistencia de voz de sitio central en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6be5-102">Planning for central site voice resiliency in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6be5-103">_**Última modificación del tema:** 2013-10-30_</span><span class="sxs-lookup"><span data-stu-id="f6be5-103">_**Topic Last Modified:** 2013-10-30_</span></span>

<span data-ttu-id="f6be5-104">Cada vez más, las empresas tienen varios sitios diseminados por todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="f6be5-104">Increasingly, enterprises have multiple sites spread across the globe.</span></span> <span data-ttu-id="f6be5-105">El mantenimiento de los servicios de emergencia, el acceso al Departamento de soporte técnico y la capacidad de realizar tareas críticas empresariales cuando un sitio central está fuera de servicio es esencial para cualquier solución de resiliencia de telefonía empresarial.</span><span class="sxs-lookup"><span data-stu-id="f6be5-105">Maintaining emergency services, access to help desk, and the ability to conduct critical business tasks when a central site is out of service is essential for any Enterprise Voice resiliency solution.</span></span> <span data-ttu-id="f6be5-106">Cuando un sitio central deja de estar disponible, se deben cumplir las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="f6be5-106">When a central site becomes unavailable, the following conditions must be met:</span></span>

  - <span data-ttu-id="f6be5-107">Debe proporcionarse la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="f6be5-107">Voice failover must be provided.</span></span>

  - <span data-ttu-id="f6be5-108">Los usuarios que normalmente se registran con el grupo de servidores front-end en el sitio central deben poder registrarse con un grupo de servidores front-end alternativo.</span><span class="sxs-lookup"><span data-stu-id="f6be5-108">Users who ordinarily register with the Front End pool at the central site must be able to register with an alternative Front End pool.</span></span> <span data-ttu-id="f6be5-109">Esto puede hacerse creando varios registros SRV de DNS, cada uno de los cuales se resuelve en un grupo de directores o grupo de servidores front-end en cada uno de sus sitios centrales.</span><span class="sxs-lookup"><span data-stu-id="f6be5-109">This can be done by creating multiple DNS SRV records, each of which resolves to a Director pool or Front End pool in each of your central sites.</span></span> <span data-ttu-id="f6be5-110">Puede ajustar la prioridad y los pesos de los registros SRV para que los usuarios atendidos por ese sitio central obtengan el director y el grupo de servidores front-end correspondiente antes que los de otros registros SRV.</span><span class="sxs-lookup"><span data-stu-id="f6be5-110">You can adjust the priority and weights of the SRV records so that users who are served by that central site get the corresponding Director and Front End pool ahead of those in other SRV records.</span></span>

  - <span data-ttu-id="f6be5-111">Las llamadas entre usuarios que se encuentren en otros sitios deben ser redirigidas a la RTC.</span><span class="sxs-lookup"><span data-stu-id="f6be5-111">Calls to and from users located at other sites must be rerouted to the PSTN.</span></span>

<span data-ttu-id="f6be5-112">En este tema se describe la solución recomendada para proteger la resistencia de voz del sitio central.</span><span class="sxs-lookup"><span data-stu-id="f6be5-112">This topic describes the recommended solution for securing central site voice resiliency.</span></span>

<div>

## <a name="architecture-and-topology"></a><span data-ttu-id="f6be5-113">Arquitectura y topología</span><span class="sxs-lookup"><span data-stu-id="f6be5-113">Architecture and Topology</span></span>

<span data-ttu-id="f6be5-114">La planificación de resistencia de voz en un sitio central requiere un conocimiento básico del rol central que desempeña el registrador de Lync Server 2013 registrador en habilitar la conmutación por error de voz.</span><span class="sxs-lookup"><span data-stu-id="f6be5-114">Planning for voice resiliency at a central site requires a basic understanding of the central role played by the Lync Server 2013 Registrar in enabling voice failover.</span></span> <span data-ttu-id="f6be5-115">El registrador de Lync Server es un rol de servidor que permite la autenticación y el registro de clientes, y proporciona servicios de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="f6be5-115">The Lync Server Registrar is a server role that enables client registration and authentication and provides routing services.</span></span> <span data-ttu-id="f6be5-116">Se encuentra junto con otros componentes en un servidor Standard Edition, un servidor front-end, un director o un equipo de sucursales con la supervivencia.</span><span class="sxs-lookup"><span data-stu-id="f6be5-116">It resides along with other components on a Standard Edition server, Front End Server, Director, or Survivable Branch Appliance.</span></span> <span data-ttu-id="f6be5-117">Un grupo de registradores consta de registrar servicios que se ejecutan en el grupo de servidores front-end y que residen en el mismo sitio.</span><span class="sxs-lookup"><span data-stu-id="f6be5-117">A Registrar pool consists of Registrar Services running on the Front End pool and residing at the same site.</span></span> <span data-ttu-id="f6be5-118">El grupo de servidores front-end debe tener equilibrio de carga.</span><span class="sxs-lookup"><span data-stu-id="f6be5-118">The Front End pool must be load balanced.</span></span> <span data-ttu-id="f6be5-119">Se recomienda el equilibrio de carga de DNS, pero el equilibrio de carga de hardware es aceptable.</span><span class="sxs-lookup"><span data-stu-id="f6be5-119">DNS load balancing is recommended, but hardware load balancing is acceptable.</span></span> <span data-ttu-id="f6be5-120">Un cliente de Lync detecta el grupo de servidores front-end mediante el siguiente mecanismo de detección:</span><span class="sxs-lookup"><span data-stu-id="f6be5-120">A Lync client discovers the Front End pool through the following discovery mechanism:</span></span>

1.  <span data-ttu-id="f6be5-121">Registro SRV de DNS</span><span class="sxs-lookup"><span data-stu-id="f6be5-121">DNS SRV record</span></span>

2.  <span data-ttu-id="f6be5-122">Servicio Web de descubrimiento automático (nuevo en Lync Server 2013)</span><span class="sxs-lookup"><span data-stu-id="f6be5-122">Autodiscovery Web Service (new in Lync Server 2013)</span></span>

3.  <span data-ttu-id="f6be5-123">Opción de DHCP 120</span><span class="sxs-lookup"><span data-stu-id="f6be5-123">DHCP option 120</span></span>

<span data-ttu-id="f6be5-124">Después de que el cliente Lync se conecte al grupo de servidores front-end, lo dirigirá el equilibrador de carga a uno de los servidores front-end en el grupo.</span><span class="sxs-lookup"><span data-stu-id="f6be5-124">After the Lync client connects to the Front End pool, it is directed by the load balancer to one of the Front End Servers in the pool.</span></span> <span data-ttu-id="f6be5-125">Ese servidor front-end, a su vez, redirige al cliente a un registrador preferido en el grupo.</span><span class="sxs-lookup"><span data-stu-id="f6be5-125">That Front End Server, in turn, redirects the client to a preferred Registrar in the pool.</span></span>

<span data-ttu-id="f6be5-126">Cada usuario habilitado para telefonía IP se asigna a un grupo de registrador concreto, que se convierte en el grupo de registrador principal de ese usuario.</span><span class="sxs-lookup"><span data-stu-id="f6be5-126">Each user enabled for Enterprise Voice is assigned to a particular Registrar pool, which becomes that user’s primary Registrar pool.</span></span> <span data-ttu-id="f6be5-127">En un sitio determinado, cientos o miles de usuarios suelen compartir un único grupo de servidores principal.</span><span class="sxs-lookup"><span data-stu-id="f6be5-127">At a given site, hundreds or thousands of users typically share a single primary Registrar pool.</span></span> <span data-ttu-id="f6be5-128">Para tener en cuenta el consumo de recursos del sitio central por parte de los usuarios de un sitio de sucursal que dependen del sitio central para la presencia, la Conferencia o la conmutación por error, le recomendamos que considere a cada usuario del sitio de sucursal como si el usuario fuera un usuario registrado con el sitio central.</span><span class="sxs-lookup"><span data-stu-id="f6be5-128">To account for the consumption of central site resources by any branch site users that rely on the central site for presence, conferencing, or failover, we recommend that you consider each branch site user as though the user were a user registered with the central site.</span></span> <span data-ttu-id="f6be5-129">Por el momento, no hay límites en el número de usuarios de la sucursal, incluidos los registrados en un equipo de sucursales con la supervivencia.</span><span class="sxs-lookup"><span data-stu-id="f6be5-129">There are currently no limits on the number of branch site users, including users registered with a Survivable Branch Appliance.</span></span>

<span data-ttu-id="f6be5-130">Para garantizar la resistencia de voz en el caso de que se produzca un error en un sitio central, el grupo de registrador principal debe tener un único grupo de registrador de copia de seguridad ubicado en otro sitio.</span><span class="sxs-lookup"><span data-stu-id="f6be5-130">To assure voice resiliency in the event of a central site failure, the primary Registrar pool must have a single designated backup Registrar pool located at another site.</span></span> <span data-ttu-id="f6be5-131">La copia de seguridad se puede configurar con la configuración de resistencia del generador de topología.</span><span class="sxs-lookup"><span data-stu-id="f6be5-131">The backup can be configured by using Topology Builder resiliency settings.</span></span> <span data-ttu-id="f6be5-132">Suponiendo un vínculo WAN resistente entre los dos sitios, los usuarios cuyo grupo principal ya no esté disponible se dirigen automáticamente al grupo de registro de la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f6be5-132">Assuming a resilient WAN link between the two sites, users whose primary Registrar pool is no longer available are automatically directed to the backup Registrar pool.</span></span>

<span data-ttu-id="f6be5-133">Los pasos siguientes describen el proceso de detección y registro de clientes:</span><span class="sxs-lookup"><span data-stu-id="f6be5-133">The following steps describe the client discovery and registration process:</span></span>

1.  <span data-ttu-id="f6be5-134">Un cliente Descubre Lync Server a través de registros SRV de DNS.</span><span class="sxs-lookup"><span data-stu-id="f6be5-134">A client discovers Lync Server through DNS SRV records.</span></span> <span data-ttu-id="f6be5-135">En Lync Server 2013, los registros SRV de DNS se pueden configurar para que devuelvan más de un FQDN a la consulta SRV de DNS.</span><span class="sxs-lookup"><span data-stu-id="f6be5-135">In Lync Server 2013, DNS SRV records can be configured to return more than one FQDN to the DNS SRV query.</span></span> <span data-ttu-id="f6be5-136">Por ejemplo, si Enterprise Contoso tiene tres sitios centrales (Norteamérica, Europa y Asia Pacífico) y un grupo de directores en cada sitio central, los registros SRV de DNS pueden apuntar a los FQDN del grupo de directores en cada una de las tres ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="f6be5-136">For example, if enterprise Contoso has three central sites (North America, Europe, and Asia-Pacific) and a Director pool at each central site, DNS SRV records can point to the Director pool FQDNs in each of the three locations.</span></span> <span data-ttu-id="f6be5-137">Siempre que el grupo de directores esté disponible en una de las ubicaciones, el cliente puede conectarse al primer salto de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f6be5-137">As long as the Director pool in one of the locations is available, the client can connect to the first hop Lync Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f6be5-138">El uso de un grupo de directores es opcional.</span><span class="sxs-lookup"><span data-stu-id="f6be5-138">Using a Director pool is optional.</span></span> <span data-ttu-id="f6be5-139">En su lugar, se puede usar un grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="f6be5-139">A Front End pool can be used instead.</span></span>

    
    </div>

2.  <span data-ttu-id="f6be5-140">El grupo de directores informa al cliente de Lync sobre el grupo de registradores principal del usuario y el grupo de registro de la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f6be5-140">The Director pool informs the Lync client about the user’s primary Registrar pool and backup Registrar pool.</span></span>

3.  <span data-ttu-id="f6be5-141">En primer lugar, el cliente de Lync intenta conectarse al grupo de registrador principal del usuario.</span><span class="sxs-lookup"><span data-stu-id="f6be5-141">The Lync client attempts to connect to the user’s primary Registrar pool first.</span></span> <span data-ttu-id="f6be5-142">Si el registrador principal está disponible, el registrador acepta el registro.</span><span class="sxs-lookup"><span data-stu-id="f6be5-142">If the primary Registrar pool is available, the Registrar accepts the registration.</span></span> <span data-ttu-id="f6be5-143">Si el registrador principal del registrador no está disponible, el cliente de Lync intenta conectarse al grupo de registro de la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f6be5-143">If the primary Registrar pool is unavailable, the Lync client attempts to connect to the backup Registrar pool.</span></span> <span data-ttu-id="f6be5-144">Si el grupo de registro de la copia de seguridad está disponible y ha determinado que el registrador principal del usuario no está disponible (al detectar la falta de latido para un intervalo de conmutación por error especificado) el grupo de registro de la copia de seguridad acepta el registro del usuario.</span><span class="sxs-lookup"><span data-stu-id="f6be5-144">If the backup Registrar pool is available and has determined that the user’s primary Registrar pool is unavailable (by detecting a lack of heartbeat for a specified failover interval) the backup Registrar pool accepts the user’s registration.</span></span> <span data-ttu-id="f6be5-145">Después de que el registrador de la copia de seguridad detecta que el registrador principal está de nuevo disponible, el grupo de registro de la copia de seguridad redirigirá los clientes de Lync a su grupo principal.</span><span class="sxs-lookup"><span data-stu-id="f6be5-145">After the backup Registrar detects that the primary Registrar is again available, the backup Registrar pool will redirect failover Lync clients to their primary pool.</span></span>

<span data-ttu-id="f6be5-146">La siguiente ilustración muestra la topología recomendada para garantizar una resistencia de sitio central.</span><span class="sxs-lookup"><span data-stu-id="f6be5-146">The following figure shows the recommended topology for assuring central site resiliency.</span></span> <span data-ttu-id="f6be5-147">Los dos sitios están conectados mediante un vínculo WAN resistente.</span><span class="sxs-lookup"><span data-stu-id="f6be5-147">The two sites are connected by a resilient WAN link.</span></span> <span data-ttu-id="f6be5-148">Si el sitio central no está disponible, los usuarios asignados a ese grupo se dirigen al sitio de copia de seguridad para su registro.</span><span class="sxs-lookup"><span data-stu-id="f6be5-148">If the central site becomes unavailable, users who are assigned to that pool are directed to the backup site for registration.</span></span>

<span data-ttu-id="f6be5-149">**Topología recomendada para resistencia de voz de sitio central**</span><span class="sxs-lookup"><span data-stu-id="f6be5-149">**Recommended topology for central site voice resiliency**</span></span>

<span data-ttu-id="f6be5-150">![Topología para resliency de voz de sitio central] (images/Gg398347.19ea3e74-8a5c-488c-a34e-fc180ab9a50a(OCS.15).jpg "Topología para resliency de voz de sitio central")</span><span class="sxs-lookup"><span data-stu-id="f6be5-150">![Topology for central site voice resliency](images/Gg398347.19ea3e74-8a5c-488c-a34e-fc180ab9a50a(OCS.15).jpg "Topology for central site voice resliency")</span></span>

</div>

<div>

## <a name="requirements-and-recommendations"></a><span data-ttu-id="f6be5-151">Requisitos y recomendaciones</span><span class="sxs-lookup"><span data-stu-id="f6be5-151">Requirements and Recommendations</span></span>

<span data-ttu-id="f6be5-152">Los siguientes requisitos y recomendaciones para implementar la resistencia de voz de sitio central son adecuados para la mayoría de las organizaciones:</span><span class="sxs-lookup"><span data-stu-id="f6be5-152">The following requirements and recommendations for implementing central site voice resiliency are appropriate for most organizations:</span></span>

  - <span data-ttu-id="f6be5-153">Los sitios en los que residen los grupos principal y de registro de la entidad de seguridad deben conectarse con un vínculo WAN resistente.</span><span class="sxs-lookup"><span data-stu-id="f6be5-153">The sites in which the primary and backup Registrar pools reside should be connected by a resilient WAN link.</span></span>

  - <span data-ttu-id="f6be5-154">Cada sitio central debe contener un grupo de registradores formado por uno o varios registradores.</span><span class="sxs-lookup"><span data-stu-id="f6be5-154">Each central site must contain a Registrar pool consisting of one or more Registrars.</span></span>

  - <span data-ttu-id="f6be5-155">Cada grupo de registrador debe tener equilibrio de carga mediante el equilibrio de carga de DNS, el equilibrio de carga de hardware o ambos.</span><span class="sxs-lookup"><span data-stu-id="f6be5-155">Each Registrar pool must be load-balanced by using DNS load balancing, hardware load balancing, or both.</span></span> <span data-ttu-id="f6be5-156">Para obtener información detallada sobre cómo planear la configuración del equilibrio de carga, consulte [requisitos de equilibrio de carga para Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6be5-156">For detailed information about planning your load balancing configuration, see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

  - <span data-ttu-id="f6be5-157">Cada usuario debe estar asignado a un grupo de registrador principal mediante el cmdlet **de Shell Set-CsUser** del shell de administración de Lync Server o el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f6be5-157">Each user must be assigned to a primary Registrar pool by using either the Lync Server Management Shell **set-CsUser** cmdlet or the Lync Server Control Panel.</span></span>

  - <span data-ttu-id="f6be5-158">El grupo de registrador principal debe tener un único grupo de registradores de copia de seguridad ubicado en un sitio central diferente.</span><span class="sxs-lookup"><span data-stu-id="f6be5-158">The primary Registrar pool must have a single backup Registrar pool located in a different central site.</span></span>

  - <span data-ttu-id="f6be5-159">El grupo de registrador principal debe configurarse para conmutar por error al grupo de registro de la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f6be5-159">The primary Registrar pool must be configured to fail over to the backup Registrar pool.</span></span> <span data-ttu-id="f6be5-160">De forma predeterminada, el registrador principal se establece para migrar tras un intervalo de 300 segundos.</span><span class="sxs-lookup"><span data-stu-id="f6be5-160">By default, the primary Registrar is set to fail over to the backup Registrar pool after an interval of 300 seconds.</span></span> <span data-ttu-id="f6be5-161">Puede cambiar este intervalo mediante el generador de topología de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f6be5-161">You can change this interval by using the Lync Server 2013 Topology Builder.</span></span>

  - <span data-ttu-id="f6be5-162">Configure una ruta de conmutación por error, como se describe en el tema "[configuración de una ruta de conmutación por error en Lync Server 2013](lync-server-2013-configuring-a-failover-route.md)" en la documentación de planificación.</span><span class="sxs-lookup"><span data-stu-id="f6be5-162">Configure a failover route, as described in the “[Configuring a failover route in Lync Server 2013](lync-server-2013-configuring-a-failover-route.md)” topic in the Planning documentation.</span></span> <span data-ttu-id="f6be5-163">Al configurar la ruta, especifique una puerta de enlace que se encuentre en un sitio diferente de la puerta de enlace especificada en la ruta principal.</span><span class="sxs-lookup"><span data-stu-id="f6be5-163">When configuring the route, specify a gateway that is located at a different site from the gateway specified in the primary route.</span></span>

  - <span data-ttu-id="f6be5-164">Si el sitio central contenía su servidor de administración principal y es probable que el sitio esté inactiva durante un período prolongado, tendrá que volver a instalar las herramientas de administración en el sitio de copia de seguridad. de lo contrario, no podrá cambiar ninguna configuración de administración.</span><span class="sxs-lookup"><span data-stu-id="f6be5-164">If the central site contained your primary management server and the site is likely to be down for an extended period, you will need to reinstall your management tools at the backup site; otherwise, you won’t be able to change any management settings.</span></span>

</div>

<div>

## <a name="dependencies"></a><span data-ttu-id="f6be5-165">Dependencias</span><span class="sxs-lookup"><span data-stu-id="f6be5-165">Dependencies</span></span>

<span data-ttu-id="f6be5-166">Lync Server depende de los siguientes componentes de infraestructura y software para garantizar la resistencia de la voz:</span><span class="sxs-lookup"><span data-stu-id="f6be5-166">Lync Server depends on the following infrastructure and software components to assure voice resiliency:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f6be5-167"><strong>Componente</strong></span><span class="sxs-lookup"><span data-stu-id="f6be5-167"><strong>Component</strong></span></span></p></td>
<td><p><span data-ttu-id="f6be5-168"><strong>Funcionan</strong></span><span class="sxs-lookup"><span data-stu-id="f6be5-168"><strong>Functional</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6be5-169">DNS</span><span class="sxs-lookup"><span data-stu-id="f6be5-169">DNS</span></span></p></td>
<td><p><span data-ttu-id="f6be5-170">Resolver registros SRV y A para la conectividad de servidor-servidor y servidor-cliente</span><span class="sxs-lookup"><span data-stu-id="f6be5-170">Resolving SRV records and A records for server-server and server-client connectivity</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6be5-171">Exchange y Exchange Web Services (EWS)</span><span class="sxs-lookup"><span data-stu-id="f6be5-171">Exchange and Exchange Web Services (EWS)</span></span></p></td>
<td><p><span data-ttu-id="f6be5-172">Almacenamiento de contactos; datos de calendario</span><span class="sxs-lookup"><span data-stu-id="f6be5-172">Contact storage; calendar data</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6be5-173">Mensajería unificada de Exchange y servicios Web de Exchange</span><span class="sxs-lookup"><span data-stu-id="f6be5-173">Exchange Unified Messaging and Exchange Web Services</span></span></p></td>
<td><p><span data-ttu-id="f6be5-174">Registros de llamadas, lista de correo de voz, correo de voz</span><span class="sxs-lookup"><span data-stu-id="f6be5-174">Call logs, voice mail list, voice mail</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6be5-175">Opciones de DHCP 120</span><span class="sxs-lookup"><span data-stu-id="f6be5-175">DHCP Options 120</span></span></p></td>
<td><p><span data-ttu-id="f6be5-176">Si SRV de DNS no está disponible, el cliente intentará usar la opción 120 de DHCP para descubrir el registrador.</span><span class="sxs-lookup"><span data-stu-id="f6be5-176">If DNS SRV is unavailable, the client will attempt to use DHCP Option 120 to discover the Registrar.</span></span> <span data-ttu-id="f6be5-177">Para que esto funcione, se debe configurar un servidor DHCP o Lync Server 2013 DHCP debe estar habilitado.</span><span class="sxs-lookup"><span data-stu-id="f6be5-177">For this to work, either a DHCP server must be configured or Lync Server 2013 DHCP must be enabled.</span></span> <span data-ttu-id="f6be5-178">Para obtener más información, vea requisitos de hardware y software para la resistencia a sitios de sucursal en <a href="lync-server-2013-branch-site-resiliency-requirements.md">la sección requisitos de resistencia de sitios de sucursales para Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f6be5-178">For details, see Hardware and Software Requirements for Branch-Site Resiliency in <a href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site resiliency requirements for Lync Server 2013</a> section.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="survivable-voice-features"></a><span data-ttu-id="f6be5-179">Características de voz revivientes</span><span class="sxs-lookup"><span data-stu-id="f6be5-179">Survivable Voice Features</span></span>

<span data-ttu-id="f6be5-180">Si se han implementado los requisitos y las recomendaciones anteriores, el grupo de registro de la copia de seguridad proporcionará las siguientes características de voz:</span><span class="sxs-lookup"><span data-stu-id="f6be5-180">If the preceding requirements and recommendations have been implemented, the following voice features will be provided by the backup Registrar pool:</span></span>

  - <span data-ttu-id="f6be5-181">Llamadas RTC salientes</span><span class="sxs-lookup"><span data-stu-id="f6be5-181">Outbound PSTN calls</span></span>

  - <span data-ttu-id="f6be5-182">Llamadas RTC entrantes, si el proveedor de servicios de telefonía admite la posibilidad de migrar por error a un sitio de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="f6be5-182">Inbound PSTN calls, if the telephony service provider supports the ability to fail over to a backup site</span></span>

  - <span data-ttu-id="f6be5-183">Llamadas empresariales entre usuarios en el mismo sitio y entre dos sitios diferentes</span><span class="sxs-lookup"><span data-stu-id="f6be5-183">Enterprise calls between users at both the same site and between two different sites</span></span>

  - <span data-ttu-id="f6be5-184">Manejo básico de llamadas, que incluye la llamada en espera, la recuperación y la transferencia</span><span class="sxs-lookup"><span data-stu-id="f6be5-184">Basic call handling, including call hold, retrieval, and transfer</span></span>

  - <span data-ttu-id="f6be5-185">Mensajería instantánea de dos participantes y uso compartido de audio y vídeo entre usuarios del mismo sitio</span><span class="sxs-lookup"><span data-stu-id="f6be5-185">Two-party instant messaging and sharing audio and video between users at the same site</span></span>

  - <span data-ttu-id="f6be5-186">Desvío de llamadas, llamadas simultáneas a puntos de conexión, Delegación de llamadas y servicios de llamada de equipo, pero solo si las dos partes para llamar a la delegación o todos los miembros del equipo, se configuran en el mismo sitio.</span><span class="sxs-lookup"><span data-stu-id="f6be5-186">Call forwarding, simultaneous ringing of endpoints, call delegation, and team call services, but only if both parties to call delegation, or all team members, are configured at the same site.</span></span>

  - <span data-ttu-id="f6be5-187">Los teléfonos y clientes existentes siguen funcionando.</span><span class="sxs-lookup"><span data-stu-id="f6be5-187">Existing phones and clients continue to work.</span></span>

  - <span data-ttu-id="f6be5-188">Registro detallado de llamadas (CDR)</span><span class="sxs-lookup"><span data-stu-id="f6be5-188">Call detail recording (CDR)</span></span>

  - <span data-ttu-id="f6be5-189">Autenticación y autorización</span><span class="sxs-lookup"><span data-stu-id="f6be5-189">Authentication and authorization</span></span>

<span data-ttu-id="f6be5-190">Según el modo en que estén configuradas, las siguientes características de voz pueden funcionar o no cuando un sitio central principal está fuera de servicio:</span><span class="sxs-lookup"><span data-stu-id="f6be5-190">Depending on how they are configured, the following voice features may or may not work when a primary central site is out of service:</span></span>

  - <span data-ttu-id="f6be5-191">Depósito y recuperación de correo de voz</span><span class="sxs-lookup"><span data-stu-id="f6be5-191">Voice mail deposit and retrieval</span></span>
    
    <span data-ttu-id="f6be5-192">Si desea que la mensajería unificada de Exchange esté disponible cuando el sitio central principal está fuera de servicio, debe realizar una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="f6be5-192">If you want to make Exchange UM available when the primary central site is out of service, you must do one of the following:</span></span>
    
      - <span data-ttu-id="f6be5-193">Cambie los registros SRV de DNS para que los servidores de mensajería unificada de Exchange en el sitio central apunten a la copia de seguridad de los servidores MU de otro sitio.</span><span class="sxs-lookup"><span data-stu-id="f6be5-193">Change DNS SRV records so that the Exchange UM servers at the central site point to backup Exchange UM servers at another site.</span></span>
    
      - <span data-ttu-id="f6be5-194">Configure el plan de marcado de MU de Exchange de cada usuario para incluir servidores MU de Exchange en el sitio central y en el sitio de copia de seguridad, pero designe los servidores de Exchange UM como deshabilitados.</span><span class="sxs-lookup"><span data-stu-id="f6be5-194">Configure each user’s Exchange UM dial plan to include Exchange UM servers at both the central site and the backup site, but designate the backup Exchange UM servers as disabled.</span></span> <span data-ttu-id="f6be5-195">Si el sitio primario no está disponible, el administrador de Exchange tiene que marcar los servidores de mensajería unificada de Exchange en el sitio de copia de seguridad como habilitado.</span><span class="sxs-lookup"><span data-stu-id="f6be5-195">If the primary site becomes unavailable, the Exchange administrator has to mark the Exchange UM servers at the backup site as enabled.</span></span>
    
    <span data-ttu-id="f6be5-196">Si ninguna de las soluciones anteriores es posible, la mensajería unificada de Exchange no estará disponible en caso de que el sitio central deje de estar disponible.</span><span class="sxs-lookup"><span data-stu-id="f6be5-196">If neither of the preceding solutions is possible, then Exchange UM will not be available in the event the central site becomes unavailable.</span></span>

  - <span data-ttu-id="f6be5-197">Conferencias de todos los tipos</span><span class="sxs-lookup"><span data-stu-id="f6be5-197">Conferencing of all types</span></span>
    
    <span data-ttu-id="f6be5-198">Un usuario que conmuta por error a un sitio de copia de seguridad puede unirse a una conferencia creada o hospedada por un organizador cuyo grupo está disponible, pero no puede crear ni hospedar una conferencia en su propio grupo principal, que ya no está disponible.</span><span class="sxs-lookup"><span data-stu-id="f6be5-198">A user who has failed over to a backup site can join a conference that is created or hosted by an organizer whose pool is available but cannot create or host a conference on his or her own primary pool, which is no longer available.</span></span> <span data-ttu-id="f6be5-199">De forma similar, otros usuarios no pueden unirse a conferencias hospedadas en el grupo primario del usuario afectado.</span><span class="sxs-lookup"><span data-stu-id="f6be5-199">Similarly, others users cannot join conferences that are hosted on the affected user’s primary pool.</span></span>

<span data-ttu-id="f6be5-200">Las siguientes características de voz no funcionan cuando un sitio central principal está fuera de servicio:</span><span class="sxs-lookup"><span data-stu-id="f6be5-200">The following voice features do not work when a primary central site is out of service:</span></span>

  - <span data-ttu-id="f6be5-201">Operador automático de conferencia</span><span class="sxs-lookup"><span data-stu-id="f6be5-201">Conference Auto-Attendant</span></span>

  - <span data-ttu-id="f6be5-202">Presencia y enrutamiento basado en DND</span><span class="sxs-lookup"><span data-stu-id="f6be5-202">Presence and DND-based routing</span></span>

  - <span data-ttu-id="f6be5-203">Actualización de la configuración del desvío de llamadas</span><span class="sxs-lookup"><span data-stu-id="f6be5-203">Updating call forwarding settings</span></span>

  - <span data-ttu-id="f6be5-204">Servicio de grupo de respuesta y Parque de llamadas</span><span class="sxs-lookup"><span data-stu-id="f6be5-204">Response Group service and Call Park</span></span>

  - <span data-ttu-id="f6be5-205">Aprovisionamiento de nuevos teléfonos y clientes</span><span class="sxs-lookup"><span data-stu-id="f6be5-205">Provisioning new phones and clients</span></span>

  - <span data-ttu-id="f6be5-206">Búsqueda en Internet de la libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="f6be5-206">Address Book Web Search</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f6be5-207">Vea también</span><span class="sxs-lookup"><span data-stu-id="f6be5-207">See Also</span></span>


[<span data-ttu-id="f6be5-208">Planificar la resistencia de voz en sitios de sucursal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6be5-208">Planning for branch-site voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-branch-site-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

