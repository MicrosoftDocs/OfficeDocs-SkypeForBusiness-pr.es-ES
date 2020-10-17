---
title: 'Lync Server 2013: soluciones de resistencia de sitios de sucursal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency solutions
ms:assetid: 1700f99b-709c-4e47-88eb-c0a5490e26e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398234(v=OCS.15)
ms:contentKeyID: 48183517
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 25541f7681ece7b299d6e4c8076fb190382650ba
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512987"
---
# <a name="branch-site-resiliency-solutions-in-lync-server-2013"></a><span data-ttu-id="2b3eb-102">Soluciones de resistencia de sitios de sucursal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b3eb-102">Branch-site resiliency solutions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b3eb-103">_**Última modificación del tema:** 2014-12-10_</span><span class="sxs-lookup"><span data-stu-id="2b3eb-103">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="2b3eb-104">Las ventajas que una organización obtiene al disponer de resistencia en las sucursales son más que evidentes.</span><span class="sxs-lookup"><span data-stu-id="2b3eb-104">There are obvious advantages to providing branch-site resiliency to your organization.</span></span> <span data-ttu-id="2b3eb-105">En concreto, si pierde la conexión con el sitio central, los usuarios del sitio de sucursal seguirán teniendo el servicio de telefonía IP y el correo de voz (si configura la configuración de reenrutamiento del correo de voz; para obtener más información, consulte [Branch-site Resiliency Requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md)).</span><span class="sxs-lookup"><span data-stu-id="2b3eb-105">Specifically, if you lose the connection to the central site, branch site users will continue to have Enterprise Voice service and voice mail (if you configure voice mail rerouting settings; for details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md)).</span></span> <span data-ttu-id="2b3eb-106">Sin embargo, una solución de resistencia probablemente no compense lo suficiente en sitios con menos de 25 usuarios.</span><span class="sxs-lookup"><span data-stu-id="2b3eb-106">However, for sites with fewer than 25 users, a resiliency solution may not provide a sufficient return on investment.</span></span>

<span data-ttu-id="2b3eb-p102">Si decide proporcionar resistencia en las sucursales, tiene tres maneras de hacerlo. La siguiente tabla puede ayudarle a saber cuál es la mejor opción para su organización.</span><span class="sxs-lookup"><span data-stu-id="2b3eb-p102">If you decide to provide branch-site resiliency, you have three options. The following table can help you determine the best option for your organization.</span></span>

<div>



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2b3eb-109">Si...</span><span class="sxs-lookup"><span data-stu-id="2b3eb-109">If you…</span></span></th>
<th><span data-ttu-id="2b3eb-110">Se recomienda...</span><span class="sxs-lookup"><span data-stu-id="2b3eb-110">We recommend that you use a…</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2b3eb-111">Hospeda entre 25 y 1000 usuarios en la sucursal y no compensa una implementación completa o no se dispone de asistencia administrativa local</span><span class="sxs-lookup"><span data-stu-id="2b3eb-111">Host between 25 and 1000 users at your branch site, and if the return on investment does not support a full deployment or where local administrative support is unavailable</span></span></p></td>
<td><p><span data-ttu-id="2b3eb-112">Aplicación de sucursal con funciones de supervivencia</span><span class="sxs-lookup"><span data-stu-id="2b3eb-112">Survivable Branch Appliance</span></span></p>
<p><span data-ttu-id="2b3eb-113">La aplicación de sucursal con funciones de supervivencia es un servidor blade estándar de la industria con un registrador de Lync Server y un servidor de mediación que se ejecuta en Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="2b3eb-113">The Survivable Branch Appliance is an industry-standard blade server with a Lync Server Registrar and Mediation Server running on Windows Server 2008 R2.</span></span> <span data-ttu-id="2b3eb-114">La aplicación de sucursal con funciones de supervivencia también contiene una puerta de enlace de red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="2b3eb-114">The Survivable Branch Appliance also contains a public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="2b3eb-115">Los dispositivos de otros fabricantes calificados (desarrollados por socios de Microsoft en el programa de certificación/calificación de aplicación de sucursal con funciones de supervivencia [SBA]) ofrecen una conexión RTC ininterrumpida en caso de que se produzca un error de WAN, aunque este enfoque no proporciona presencia y conferencia resistentes, ya que ambas características dependen de los servidores front-end del sitio central.</span><span class="sxs-lookup"><span data-stu-id="2b3eb-115">Qualified third-party devices (developed by Microsoft partners in the Survivable Branch Appliance (SBA) qualification/certification program) provide a continuous PSTN connection in the event of WAN failure, but this approach does not provide resilient presence and conferencing because these features depend on Front End Servers at the central site.</span></span></p>
<p><span data-ttu-id="2b3eb-116">Para obtener más información sobre las aplicaciones de sucursal con funciones de supervivencia, consulte &quot; detalles de aplicación de sucursal con funciones de supervivencia, &quot; más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="2b3eb-116">For details about Survivable Branch Appliances, see &quot;Survivable Branch Appliance Details,&quot; later in this topic.</span></span></p>
<p><span data-ttu-id="2b3eb-117"><strong>Nota:</strong> Si decide usar también un tronco SIP con la aplicación de sucursal con funciones de supervivencia, póngase en contacto con el proveedor de la aplicación de sucursal con funciones de supervivencia para obtener información sobre qué proveedor de servicios es el mejor para su organización.</span><span class="sxs-lookup"><span data-stu-id="2b3eb-117"><strong>Note:</strong> If you decide to also use a SIP trunk with your Survivable Branch Appliance, contact your Survivable Branch Appliance vendor to learn about which service provider is best for your organization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b3eb-118">Host entre los usuarios de 1000 y 2000 en su sitio de sucursal, carecen de una conexión WAN resistente y tienen los administradores de Lync Server capacitados disponibles</span><span class="sxs-lookup"><span data-stu-id="2b3eb-118">Host between 1000 and 2000 users at your branch site, lack a resilient WAN connection, and have trained Lync Server administrators available</span></span></p></td>
<td><p><span data-ttu-id="2b3eb-119">Servidor de sucursal con funciones de supervivencia o dos aplicaciones de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="2b3eb-119">Survivable Branch Server or two Survivable Branch Appliances.</span></span></p>
<p><span data-ttu-id="2b3eb-120">El servidor de sucursal con funciones de supervivencia es un servidor de Windows Server que cumple los requisitos de hardware especificados que tiene instalado el software del servidor de mediación y el registrador de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2b3eb-120">The Survivable Branch Server is a Windows Server meeting specified hardware requirements that has Lync Server Registrar and Mediation Server software installed on it.</span></span> <span data-ttu-id="2b3eb-121">Debe conectarse a una puerta de enlace RTC o a un tronco SIP hacia un proveedor de servicios telefónicos.</span><span class="sxs-lookup"><span data-stu-id="2b3eb-121">It must connect to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span></p>
<p><span data-ttu-id="2b3eb-122">Para obtener más información sobre los servidores de sucursal con funciones de supervivencia, vea &quot; detalles del servidor de sucursal con funciones de supervivencia, &quot; más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="2b3eb-122">For details about Survivable Branch Servers, see &quot;Survivable Branch Server Details,&quot; later in this topic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b3eb-123">Si necesita características de presencia y Conferencia además de las características de voz para un máximo de 5000 usuarios y tiene los administradores de Lync Server capacitados disponibles</span><span class="sxs-lookup"><span data-stu-id="2b3eb-123">If you require presence and conferencing features in addition to voice features for up to 5000 users, and have trained Lync Server administrators available</span></span></p></td>
<td><p><span data-ttu-id="2b3eb-124">Realizar una implementación como un sitio central con un servidor Standard Edition en lugar de como una sucursal.</span><span class="sxs-lookup"><span data-stu-id="2b3eb-124">Deploy as a central site with a Standard Edition server rather than as a branch site.</span></span></p>
<p><span data-ttu-id="2b3eb-125">Una implementación de Lync Server a gran escala proporciona una conexión RTC continua y una presencia resistente y conferencias en caso de que se produzca un error de WAN.</span><span class="sxs-lookup"><span data-stu-id="2b3eb-125">A full-scale Lync Server deployment provides a continuous PSTN connection and resilient presence and conferencing in the event of WAN failure.</span></span></p>
<p><span data-ttu-id="2b3eb-126">Para obtener información detallada sobre la preparación para esta solución, consulte <a href="lync-server-2013-planning-for-your-organization.md">Organization Planning for Lync server 2013</a>, <a href="lync-server-2013-determining-your-system-requirements.md">determining Your System Requirements for Lync Server 2013</a>, <a href="lync-server-2013-determining-your-infrastructure-requirements.md">determining Your Infrastructure requirements for Lync Server 2013</a>y otras secciones relevantes de la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="2b3eb-126">For details about preparing for this solution, see <a href="lync-server-2013-planning-for-your-organization.md">Organization planning for Lync Server 2013</a>, <a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a>, <a href="lync-server-2013-determining-your-infrastructure-requirements.md">Determining your infrastructure requirements for Lync Server 2013</a>, and other relevant sections of the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="resiliency-topologies"></a><span data-ttu-id="2b3eb-127">Topologías de resistencia</span><span class="sxs-lookup"><span data-stu-id="2b3eb-127">Resiliency Topologies</span></span>

<span data-ttu-id="2b3eb-128">La siguiente figura refleja las topologías recomendadas de resistencia en las sucursales.</span><span class="sxs-lookup"><span data-stu-id="2b3eb-128">The following figure shows the recommended topologies for branch-site resiliency.</span></span>

<span data-ttu-id="2b3eb-129">**Opciones de resistencia de las sucursales**</span><span class="sxs-lookup"><span data-stu-id="2b3eb-129">**Branch site resiliency options**</span></span>

<span data-ttu-id="2b3eb-130">![Opciones de resistencia de bifurcación de voz](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "Opciones de resistencia de bifurcación de voz")</span><span class="sxs-lookup"><span data-stu-id="2b3eb-130">![Voice Branch Resiliency Options](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "Voice Branch Resiliency Options")</span></span>

</div>

<div>

## <a name="survivable-branch-appliance-details"></a><span data-ttu-id="2b3eb-131">Detalles de la aplicación de sucursal con funciones de supervivencia</span><span class="sxs-lookup"><span data-stu-id="2b3eb-131">Survivable Branch Appliance Details</span></span>

<span data-ttu-id="2b3eb-132">La aplicación de sucursal con funciones de supervivencia de Lync Server incluye los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="2b3eb-132">The Lync Server Survivable Branch Appliance includes the following components:</span></span>

  - <span data-ttu-id="2b3eb-133">Un registrador para la autenticación y registro de usuarios y el enrutado de llamadas</span><span class="sxs-lookup"><span data-stu-id="2b3eb-133">A Registrar for user authentication, registration and call routing</span></span>

  - <span data-ttu-id="2b3eb-134">Un servidor de mediación para controlar la señalización entre el registrador y una puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="2b3eb-134">A Mediation Server for handling signaling between the Registrar and a PSTN gateway</span></span>

  - <span data-ttu-id="2b3eb-135">Una puerta de enlace RTC para enrutar llamadas a la RTC a modo de transporte de reserva en caso de que se produzca una interrupción en la red WAN</span><span class="sxs-lookup"><span data-stu-id="2b3eb-135">A PSTN gateway for routing calls to the PSTN as a fallback transport in the event of a WAN outage</span></span>

  - <span data-ttu-id="2b3eb-136">SQL Server Express para el almacenamiento local de los datos de usuario</span><span class="sxs-lookup"><span data-stu-id="2b3eb-136">SQL Server Express for local user data storage</span></span>

<span data-ttu-id="2b3eb-137">La aplicación de sucursal con funciones de supervivencia también incluye troncos RTC, puertos analógicos y un adaptador Ethernet.</span><span class="sxs-lookup"><span data-stu-id="2b3eb-137">The Survivable Branch Appliance also includes PSTN trunks, analog ports, and an Ethernet adapter.</span></span>

<span data-ttu-id="2b3eb-138">Si la conexión WAN del sitio de sucursal a un sitio central deja de estar disponible, los usuarios de la sucursal interna siguen registrándose con el registrador de la aplicación de sucursal con funciones de supervivencia y obtienen un servicio de voz sin interrupciones mediante la conexión de aplicación de sucursal con funciones de supervivencia a la RTC.</span><span class="sxs-lookup"><span data-stu-id="2b3eb-138">If the branch site’s WAN connection to a central site becomes unavailable, internal branch users continue to be registered with the Survivable Branch Appliance Registrar and obtain uninterrupted voice service by using the Survivable Branch Appliance connection to the PSTN.</span></span> <span data-ttu-id="2b3eb-139">En caso de que el vínculo WAN a una sucursal no esté disponible, los usuarios de sucursal que se conecten desde casa o desde otras ubicaciones remotas tendrán la posibilidad de registrarse con un servidor registrador ubicado en el sitio central.</span><span class="sxs-lookup"><span data-stu-id="2b3eb-139">Branch site users who connect from home or other remote locations will be able to register with a Registrar server at a central site if the WAN link to the branch site is unavailable.</span></span> <span data-ttu-id="2b3eb-140">Estos usuarios disfrutarán de la funcionalidad de comunicaciones unificadas completa, con la única salvedad de que las llamadas entrantes a la sucursal se trasladarán al correo de voz.</span><span class="sxs-lookup"><span data-stu-id="2b3eb-140">These users will have full unified communications functionality, with the one exception that inbound calls to the branch site will go to voice mail.</span></span> <span data-ttu-id="2b3eb-141">Cuando la conexión WAN vuelva, deberá restaurarse la funcionalidad completa para los usuarios de las sucursales.</span><span class="sxs-lookup"><span data-stu-id="2b3eb-141">When the WAN connection becomes available, full functionality should be restored to branch site users.</span></span> <span data-ttu-id="2b3eb-142">Ni la conmutación por error a la aplicación de sucursal con funciones de supervivencia ni la restauración del servicio requiere la presencia de un administrador de ti.</span><span class="sxs-lookup"><span data-stu-id="2b3eb-142">Neither the failover to the Survivable Branch Appliance nor the restoration of service requires the presence of an IT administrator.</span></span>

<span data-ttu-id="2b3eb-143">Lync Server admite hasta dos dispositivos de sucursal con funciones de supervivencia en un sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="2b3eb-143">Lync Server supports up to two Survivable Branch Appliance at a branch site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2b3eb-144">Los usuarios hospedados en una aplicación de sucursal con funciones de supervivencia de Lync Server no pueden crear salones de chat nuevos ni ver la tarjeta de la sala para las salas existentes.</span><span class="sxs-lookup"><span data-stu-id="2b3eb-144">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new Chat Rooms or view the Room Card for existing rooms.</span></span>



</div>

<div>

## <a name="survivable-branch-appliance-deployment-overview"></a><span data-ttu-id="2b3eb-145">Descripción general de la implementación de la aplicación de sucursal con funciones de supervivencia</span><span class="sxs-lookup"><span data-stu-id="2b3eb-145">Survivable Branch Appliance Deployment Overview</span></span>

<span data-ttu-id="2b3eb-146">La aplicación de sucursal con funciones de supervivencia la fabrican los fabricantes de equipos originales en asociación con Microsoft y se implementan en su nombre por parte de distribuidores de valor agregado.</span><span class="sxs-lookup"><span data-stu-id="2b3eb-146">The Survivable Branch Appliance is manufactured by original equipment manufacturers in partnership with Microsoft and deployed on their behalf by value-added retailers.</span></span> <span data-ttu-id="2b3eb-147">Esta implementación solo debe realizarse después de que Lync Server se haya implementado en el sitio central, una conexión WAN con el sitio de sucursal esté en su lugar y los usuarios de sitios de sucursal estén habilitados para telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="2b3eb-147">This deployment should occur only after Lync Server has been deployed at the central site, a WAN connection to the branch site is in place, and branch site users are enabled for Enterprise Voice.</span></span>

<span data-ttu-id="2b3eb-148">Para obtener más información sobre estas fases, consulte [Deploying a supervivenciaable Branch Appliance or Server with Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="2b3eb-148">For details about these phases, see [Deploying a Survivable Branch Appliance or Server with Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2b3eb-149">Fase</span><span class="sxs-lookup"><span data-stu-id="2b3eb-149">Phase</span></span></th>
<th><span data-ttu-id="2b3eb-150">Pasos</span><span class="sxs-lookup"><span data-stu-id="2b3eb-150">Steps</span></span></th>
<th><span data-ttu-id="2b3eb-151">Derechos de usuario</span><span class="sxs-lookup"><span data-stu-id="2b3eb-151">User Rights</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2b3eb-152">Configurar los servicios de dominio de Active Directory para la aplicación de sucursal con funciones de supervivencia</span><span class="sxs-lookup"><span data-stu-id="2b3eb-152">Set up Active Directory Domain Services for the Survivable Branch Appliance</span></span></p></td>
<td><p><span data-ttu-id="2b3eb-153"><strong>En el sitio central:</strong></span><span class="sxs-lookup"><span data-stu-id="2b3eb-153"><strong>At the central site:</strong></span></span></p>
<ol>
<li><p><span data-ttu-id="2b3eb-154">Cree una cuenta de usuario de dominio (o identidad empresarial) para el técnico que vaya a instalar y activar la aplicación de sucursal con funciones de supervivencia en el sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="2b3eb-154">Create a domain user account (or enterprise identity) for the technician who will install and activate the Survivable Branch Appliance at the branch site.</span></span></p></li>
<li><p><span data-ttu-id="2b3eb-155">Cree una cuenta de equipo (con el nombre de dominio completo (FQDN) aplicable) para la aplicación de sucursal con funciones de supervivencia en los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2b3eb-155">Create a computer account (with the applicable fully qualified domain name (FQDN)) for Survivable Branch Appliance in Active Directory Domain Services.</span></span></p></li>
<li><p><span data-ttu-id="2b3eb-156">En el generador de topologías, cree y publique la aplicación de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="2b3eb-156">In Topology Builder, create and publish the Survivable Branch Appliance.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="2b3eb-157">La cuenta de usuario del técnico debe ser miembro de RTCUniversalSBATechnicians.</span><span class="sxs-lookup"><span data-stu-id="2b3eb-157">The technician user account must be a member of RTCUniversalSBATechnicians.</span></span> <span data-ttu-id="2b3eb-158">La aplicación de sucursal con funciones de supervivencia debe pertenecer al grupo RTCSBAUniversalServices, que se produce automáticamente al usar el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="2b3eb-158">The Survivable Branch Appliance must belong to the RTCSBAUniversalServices group, which happens automatically when you use Topology Builder.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b3eb-159">Instale y active la aplicación de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="2b3eb-159">Install, and activate the Survivable Branch Appliance.</span></span></p></td>
<td><p><span data-ttu-id="2b3eb-160"><strong>En la sucursal:</strong></span><span class="sxs-lookup"><span data-stu-id="2b3eb-160"><strong>At the branch site:</strong></span></span></p>
<ol>
<li><p><span data-ttu-id="2b3eb-161">Conecte la aplicación de sucursal con funciones de supervivencia a un puerto Ethernet y a un puerto RTC.</span><span class="sxs-lookup"><span data-stu-id="2b3eb-161">Connect the Survivable Branch Appliance to an Ethernet port and PSTN port.</span></span></p></li>
<li><p><span data-ttu-id="2b3eb-162">Inicie la aplicación de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="2b3eb-162">Start the Survivable Branch Appliance.</span></span></p></li>
<li><p><span data-ttu-id="2b3eb-163">Únase a la aplicación de sucursal con funciones de supervivencia en el dominio con la cuenta de usuario de dominio creada para la aplicación de sucursal con funciones de supervivencia en el sitio central.</span><span class="sxs-lookup"><span data-stu-id="2b3eb-163">Join the Survivable Branch Appliance to the domain, using the domain user account created for the Survivable Branch Appliance at the central site.</span></span> <span data-ttu-id="2b3eb-164">Establezca el FQDN y la dirección IP de forma que coincidan con el FQDN creado en la cuenta del equipo.</span><span class="sxs-lookup"><span data-stu-id="2b3eb-164">Set the FQDN and IP address to match the FQDN created in the computer account.</span></span></p></li>
<li><p><span data-ttu-id="2b3eb-165">Configure la aplicación de sucursal con funciones de supervivencia mediante la interfaz de usuario OEM.</span><span class="sxs-lookup"><span data-stu-id="2b3eb-165">Configure the Survivable Branch Appliance using the OEM user interface.</span></span></p></li>
<li><p><span data-ttu-id="2b3eb-166">Compruebe la conectividad RTC.</span><span class="sxs-lookup"><span data-stu-id="2b3eb-166">Test PSTN connectivity.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="2b3eb-167">La cuenta de usuario del técnico debe ser miembro de RTCUniversalSBATechnicians.</span><span class="sxs-lookup"><span data-stu-id="2b3eb-167">The technician user account must be a member of RTCUniversalSBATechnicians.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="survivable-branch-server-details"></a><span data-ttu-id="2b3eb-168">Detalles del servidor de sucursal con funciones de supervivencia</span><span class="sxs-lookup"><span data-stu-id="2b3eb-168">Survivable Branch Server Details</span></span>

<span data-ttu-id="2b3eb-169">En el generador de topologías, cree el sitio de sucursal, agregue el servidor de sucursal con funciones de supervivencia al sitio y, a continuación, ejecute el Asistente para la implementación de Lync Server en el equipo en el que desea instalar el rol.</span><span class="sxs-lookup"><span data-stu-id="2b3eb-169">In Topology Builder create the branch site, add the Survivable Branch Server to that site, and then run the Lync Server Deployment Wizard on the computer where you want to install the role.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2b3eb-170">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2b3eb-170">See Also</span></span>


[<span data-ttu-id="2b3eb-171">Implementar Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b3eb-171">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

