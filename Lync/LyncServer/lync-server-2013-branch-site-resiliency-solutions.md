---
title: 'Lync Server 2013: Soluciones de resistencia de sitios de sucursales'
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
ms.openlocfilehash: 16261d4add87462991c877e85cc6a0ff1e7fdfd4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741840"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-solutions-in-lync-server-2013"></a><span data-ttu-id="75cea-102">Soluciones de resistencia de sitios de sucursales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75cea-102">Branch-site resiliency solutions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75cea-103">_**Última modificación del tema:** 2014-12-10_</span><span class="sxs-lookup"><span data-stu-id="75cea-103">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="75cea-104">Existen ventajas obvias para proporcionar resistencia a sitios de sucursales a su organización.</span><span class="sxs-lookup"><span data-stu-id="75cea-104">There are obvious advantages to providing branch-site resiliency to your organization.</span></span> <span data-ttu-id="75cea-105">En concreto, si pierde la conexión con el sitio central, los usuarios del sitio de la sucursal seguirán teniendo el servicio de voz empresarial y el correo de voz (si configura el redireccionamiento de correo de voz; para obtener más información, consulte [requisitos de resistencia de sitio de sucursal para Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md)).</span><span class="sxs-lookup"><span data-stu-id="75cea-105">Specifically, if you lose the connection to the central site, branch site users will continue to have Enterprise Voice service and voice mail (if you configure voice mail rerouting settings; for details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md)).</span></span> <span data-ttu-id="75cea-106">Sin embargo, en el caso de sitios con menos de 25 usuarios, una solución de resistencia puede no proporcionar un retorno de la inversión suficiente.</span><span class="sxs-lookup"><span data-stu-id="75cea-106">However, for sites with fewer than 25 users, a resiliency solution may not provide a sufficient return on investment.</span></span>

<span data-ttu-id="75cea-107">Si decide proporcionar resistencia a sitios de sucursales, tiene tres opciones.</span><span class="sxs-lookup"><span data-stu-id="75cea-107">If you decide to provide branch-site resiliency, you have three options.</span></span> <span data-ttu-id="75cea-108">La siguiente tabla puede ayudarle a determinar la mejor opción para su organización.</span><span class="sxs-lookup"><span data-stu-id="75cea-108">The following table can help you determine the best option for your organization.</span></span>

<div>



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="75cea-109">Si...</span><span class="sxs-lookup"><span data-stu-id="75cea-109">If you…</span></span></th>
<th><span data-ttu-id="75cea-110">Le recomendamos que use un...</span><span class="sxs-lookup"><span data-stu-id="75cea-110">We recommend that you use a…</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="75cea-111">Hospedar entre 25 y 1000 usuarios de su sitio de sucursal y si el retorno de la inversión no admite una implementación completa o si no está disponible el soporte administrativo local</span><span class="sxs-lookup"><span data-stu-id="75cea-111">Host between 25 and 1000 users at your branch site, and if the return on investment does not support a full deployment or where local administrative support is unavailable</span></span></p></td>
<td><p><span data-ttu-id="75cea-112">Aplicación de sucursal con funciones de supervivencia</span><span class="sxs-lookup"><span data-stu-id="75cea-112">Survivable Branch Appliance</span></span></p>
<p><span data-ttu-id="75cea-113">El equipo de rama con más supervivencia es un servidor blade estándar de la industria con un registrador de Lync Server y un servidor de mediación que se ejecuta en Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="75cea-113">The Survivable Branch Appliance is an industry-standard blade server with a Lync Server Registrar and Mediation Server running on Windows Server 2008 R2.</span></span> <span data-ttu-id="75cea-114">El dispositivo de sucursal con la supervivencia también contiene una puerta de enlace de red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="75cea-114">The Survivable Branch Appliance also contains a public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="75cea-115">Los dispositivos de terceros cualificados (desarrollados por socios de Microsoft en el programa de certificación/titulación de la aplicación de rama superviviente (SBA) proporcionan una conexión RTC continua en el caso de una falla de WAN, pero este enfoque no proporciona presencia y conferencias resistentes porque estas características dependen de servidores frontales en el sitio central.</span><span class="sxs-lookup"><span data-stu-id="75cea-115">Qualified third-party devices (developed by Microsoft partners in the Survivable Branch Appliance (SBA) qualification/certification program) provide a continuous PSTN connection in the event of WAN failure, but this approach does not provide resilient presence and conferencing because these features depend on Front End Servers at the central site.</span></span></p>
<p><span data-ttu-id="75cea-116">Para obtener más información sobre los equipos de las &quot;sucursales que son supervivientes&quot; , vea detalles sobre el equipo de la aplicación que más se muestra en este tema.</span><span class="sxs-lookup"><span data-stu-id="75cea-116">For details about Survivable Branch Appliances, see &quot;Survivable Branch Appliance Details,&quot; later in this topic.</span></span></p>
<p><span data-ttu-id="75cea-117"><strong>Nota:</strong> Si decide usar también un tronco de SIP con su equipo de sucursal con la supervivencia, póngase en contacto con el proveedor de su equipo de sucursales con la supervivencia para obtener información sobre el proveedor de servicios más adecuado para su organización.</span><span class="sxs-lookup"><span data-stu-id="75cea-117"><strong>Note:</strong> If you decide to also use a SIP trunk with your Survivable Branch Appliance, contact your Survivable Branch Appliance vendor to learn about which service provider is best for your organization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75cea-118">Hospedar entre usuarios de 1000 y 2000 en su sitio de sucursal, carecer de una conexión WAN resistente y tener disponibles los administradores de Lync Server capacitados</span><span class="sxs-lookup"><span data-stu-id="75cea-118">Host between 1000 and 2000 users at your branch site, lack a resilient WAN connection, and have trained Lync Server administrators available</span></span></p></td>
<td><p><span data-ttu-id="75cea-119">Servidor de sucursal superviviente o dos dispositivos de sucursal con la supervivencia.</span><span class="sxs-lookup"><span data-stu-id="75cea-119">Survivable Branch Server or two Survivable Branch Appliances.</span></span></p>
<p><span data-ttu-id="75cea-120">El servidor de sucursal con la supervivencia es un servidor de Windows que cumple los requisitos de hardware especificados que tienen instalado Lync Server registrador y el software Media Server.</span><span class="sxs-lookup"><span data-stu-id="75cea-120">The Survivable Branch Server is a Windows Server meeting specified hardware requirements that has Lync Server Registrar and Mediation Server software installed on it.</span></span> <span data-ttu-id="75cea-121">Debe conectarse a una puerta de enlace PSTN o a un tronco SIP a un proveedor de servicios telefónicos.</span><span class="sxs-lookup"><span data-stu-id="75cea-121">It must connect to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span></p>
<p><span data-ttu-id="75cea-122">Para obtener más información sobre los servidores de sucursal &quot;que se van a&quot; utilizar, consulte detalles de servidores de sucursal que se más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="75cea-122">For details about Survivable Branch Servers, see &quot;Survivable Branch Server Details,&quot; later in this topic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75cea-123">Si necesita características de presencia y de conferencia, además de características de voz para un máximo de 5000 usuarios, y tiene los administradores de Lync Server capacitados disponibles</span><span class="sxs-lookup"><span data-stu-id="75cea-123">If you require presence and conferencing features in addition to voice features for up to 5000 users, and have trained Lync Server administrators available</span></span></p></td>
<td><p><span data-ttu-id="75cea-124">Implementar como un sitio central con un servidor Standard Edition en lugar de como un sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="75cea-124">Deploy as a central site with a Standard Edition server rather than as a branch site.</span></span></p>
<p><span data-ttu-id="75cea-125">Una implementación de Lync Server a escala completa proporciona una conexión RTC continua y una presencia resistente y conferencias en caso de que se produzca un error de WAN.</span><span class="sxs-lookup"><span data-stu-id="75cea-125">A full-scale Lync Server deployment provides a continuous PSTN connection and resilient presence and conferencing in the event of WAN failure.</span></span></p>
<p><span data-ttu-id="75cea-126">Para obtener más información sobre la preparación para esta solución, consulte Planificación de la <a href="lync-server-2013-planning-for-your-organization.md">organización para Lync server 2013</a>, determinación de los <a href="lync-server-2013-determining-your-system-requirements.md">requisitos del sistema para Lync Server 2013</a>, determinación de los <a href="lync-server-2013-determining-your-infrastructure-requirements.md">requisitos de infraestructura para Lync Server 2013</a>y otras secciones relevantes de la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="75cea-126">For details about preparing for this solution, see <a href="lync-server-2013-planning-for-your-organization.md">Organization planning for Lync Server 2013</a>, <a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a>, <a href="lync-server-2013-determining-your-infrastructure-requirements.md">Determining your infrastructure requirements for Lync Server 2013</a>, and other relevant sections of the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="resiliency-topologies"></a><span data-ttu-id="75cea-127">Topologías de resiliencia</span><span class="sxs-lookup"><span data-stu-id="75cea-127">Resiliency Topologies</span></span>

<span data-ttu-id="75cea-128">En la siguiente ilustración se muestran las topologías recomendadas para la resistencia a sitios de sucursales.</span><span class="sxs-lookup"><span data-stu-id="75cea-128">The following figure shows the recommended topologies for branch-site resiliency.</span></span>

<span data-ttu-id="75cea-129">**Opciones de resistencia de sitio de sucursal**</span><span class="sxs-lookup"><span data-stu-id="75cea-129">**Branch site resiliency options**</span></span>

<span data-ttu-id="75cea-130">![Opciones de resistencia de voz para sucursal](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "Opciones de resistencia de voz para sucursal")</span><span class="sxs-lookup"><span data-stu-id="75cea-130">![Voice Branch Resiliency Options](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "Voice Branch Resiliency Options")</span></span>

</div>

<div>

## <a name="survivable-branch-appliance-details"></a><span data-ttu-id="75cea-131">Detalles de los dispositivos de rama supervivientes</span><span class="sxs-lookup"><span data-stu-id="75cea-131">Survivable Branch Appliance Details</span></span>

<span data-ttu-id="75cea-132">El equipo de sucursal con supervivencia de Lync Server incluye los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="75cea-132">The Lync Server Survivable Branch Appliance includes the following components:</span></span>

  - <span data-ttu-id="75cea-133">Un registrador para la autenticación de usuarios, registro y enrutamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="75cea-133">A Registrar for user authentication, registration and call routing</span></span>

  - <span data-ttu-id="75cea-134">Un servidor de mediación para controlar la señalización entre el registrador y una puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="75cea-134">A Mediation Server for handling signaling between the Registrar and a PSTN gateway</span></span>

  - <span data-ttu-id="75cea-135">Una puerta de enlace RTC para el enrutamiento de llamadas a la RTC como transporte de reserva en el caso de una interrupción de la WAN</span><span class="sxs-lookup"><span data-stu-id="75cea-135">A PSTN gateway for routing calls to the PSTN as a fallback transport in the event of a WAN outage</span></span>

  - <span data-ttu-id="75cea-136">SQL Server Express para almacenamiento de datos de usuario local</span><span class="sxs-lookup"><span data-stu-id="75cea-136">SQL Server Express for local user data storage</span></span>

<span data-ttu-id="75cea-137">El dispositivo de sucursal con la supervivencia también incluye troncos de la RTC, puertos análogos y un adaptador Ethernet.</span><span class="sxs-lookup"><span data-stu-id="75cea-137">The Survivable Branch Appliance also includes PSTN trunks, analog ports, and an Ethernet adapter.</span></span>

<span data-ttu-id="75cea-138">Si la conexión WAN del sitio de la sucursal a un sitio central no está disponible, los usuarios de la sucursal interna siguen registrándose con el registrador de la aplicación de rama superviviente y obtienen un servicio de voz ininterrumpido usando la conexión de la aplicación de la aplicación de supervivencia a la RTC.</span><span class="sxs-lookup"><span data-stu-id="75cea-138">If the branch site’s WAN connection to a central site becomes unavailable, internal branch users continue to be registered with the Survivable Branch Appliance Registrar and obtain uninterrupted voice service by using the Survivable Branch Appliance connection to the PSTN.</span></span> <span data-ttu-id="75cea-139">Los usuarios de un sitio de sucursal que se conecten desde casa u otras ubicaciones remotas podrán registrarse con un servidor de registro en un sitio central si el vínculo WAN al sitio de la sucursal no está disponible.</span><span class="sxs-lookup"><span data-stu-id="75cea-139">Branch site users who connect from home or other remote locations will be able to register with a Registrar server at a central site if the WAN link to the branch site is unavailable.</span></span> <span data-ttu-id="75cea-140">Estos usuarios tendrán una funcionalidad de comunicaciones unificadas completa, con la única excepción de que las llamadas entrantes al sitio de la sucursal Irán a correo de voz.</span><span class="sxs-lookup"><span data-stu-id="75cea-140">These users will have full unified communications functionality, with the one exception that inbound calls to the branch site will go to voice mail.</span></span> <span data-ttu-id="75cea-141">Cuando la conexión WAN esté disponible, la funcionalidad completa debe restaurarse a los usuarios del sitio de la sucursal.</span><span class="sxs-lookup"><span data-stu-id="75cea-141">When the WAN connection becomes available, full functionality should be restored to branch site users.</span></span> <span data-ttu-id="75cea-142">Ni la conmutación por error a la aplicación de rama superviviente ni la restauración de servicio requiere la presencia de un administrador de ti.</span><span class="sxs-lookup"><span data-stu-id="75cea-142">Neither the failover to the Survivable Branch Appliance nor the restoration of service requires the presence of an IT administrator.</span></span>

<span data-ttu-id="75cea-143">Lync Server admite hasta dos sucursales de superviviente en un sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="75cea-143">Lync Server supports up to two Survivable Branch Appliance at a branch site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="75cea-144">Los usuarios que estén alojados en un equipo con la aplicación de Lync Server superviviente no pueden crear nuevos salones de chat o ver la tarjeta de la sala de las habitaciones existentes.</span><span class="sxs-lookup"><span data-stu-id="75cea-144">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new Chat Rooms or view the Room Card for existing rooms.</span></span>



</div>

<div>

## <a name="survivable-branch-appliance-deployment-overview"></a><span data-ttu-id="75cea-145">Descripción general de la implementación de dispositivos de sucursales</span><span class="sxs-lookup"><span data-stu-id="75cea-145">Survivable Branch Appliance Deployment Overview</span></span>

<span data-ttu-id="75cea-146">El equipo de sucursales que es superviviente es fabricado por los fabricantes de equipos originales en colaboración con Microsoft y distribuido en su nombre por tiendas minoristas de valor añadido.</span><span class="sxs-lookup"><span data-stu-id="75cea-146">The Survivable Branch Appliance is manufactured by original equipment manufacturers in partnership with Microsoft and deployed on their behalf by value-added retailers.</span></span> <span data-ttu-id="75cea-147">Esta implementación solo debe realizarse después de que Lync Server se haya implementado en el sitio central, una conexión WAN al sitio de la sucursal esté en vigor y los usuarios del sitio de la sucursal estén habilitados para telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="75cea-147">This deployment should occur only after Lync Server has been deployed at the central site, a WAN connection to the branch site is in place, and branch site users are enabled for Enterprise Voice.</span></span>

<span data-ttu-id="75cea-148">Para obtener más información sobre estas fases, consulte [implementación de un dispositivo de sucursal o servidor con Lync server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="75cea-148">For details about these phases, see [Deploying a Survivable Branch Appliance or Server with Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="75cea-149">Fase</span><span class="sxs-lookup"><span data-stu-id="75cea-149">Phase</span></span></th>
<th><span data-ttu-id="75cea-150">Pasos</span><span class="sxs-lookup"><span data-stu-id="75cea-150">Steps</span></span></th>
<th><span data-ttu-id="75cea-151">Derechos de usuario</span><span class="sxs-lookup"><span data-stu-id="75cea-151">User Rights</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="75cea-152">Configurar los servicios de dominio de Active Directory para la aplicación de rama superviviente</span><span class="sxs-lookup"><span data-stu-id="75cea-152">Set up Active Directory Domain Services for the Survivable Branch Appliance</span></span></p></td>
<td><p><span data-ttu-id="75cea-153"><strong>En el sitio central:</strong></span><span class="sxs-lookup"><span data-stu-id="75cea-153"><strong>At the central site:</strong></span></span></p>
<ol>
<li><p><span data-ttu-id="75cea-154">Cree una cuenta de usuario de dominio (o identidad empresarial) para el técnico que instalará y activará la aplicación de la rama que tiene el mismo nivel en el sitio de la sucursal.</span><span class="sxs-lookup"><span data-stu-id="75cea-154">Create a domain user account (or enterprise identity) for the technician who will install and activate the Survivable Branch Appliance at the branch site.</span></span></p></li>
<li><p><span data-ttu-id="75cea-155">Cree una cuenta de equipo (con el nombre de dominio completo aplicable (FQDN)) para el equipo de sucursales supervivientes en los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="75cea-155">Create a computer account (with the applicable fully qualified domain name (FQDN)) for Survivable Branch Appliance in Active Directory Domain Services.</span></span></p></li>
<li><p><span data-ttu-id="75cea-156">En el generador de topologías, cree y publique la aplicación de rama que sea superviviente.</span><span class="sxs-lookup"><span data-stu-id="75cea-156">In Topology Builder, create and publish the Survivable Branch Appliance.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="75cea-157">La cuenta de usuario del técnico debe ser miembro de RTCUniversalSBATechnicians.</span><span class="sxs-lookup"><span data-stu-id="75cea-157">The technician user account must be a member of RTCUniversalSBATechnicians.</span></span> <span data-ttu-id="75cea-158">La aplicación de la rama superviviente debe pertenecer al grupo RTCSBAUniversalServices, que se produce automáticamente al utilizar Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="75cea-158">The Survivable Branch Appliance must belong to the RTCSBAUniversalServices group, which happens automatically when you use Topology Builder.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75cea-159">Instale y active la aplicación de rama que sea superviviente.</span><span class="sxs-lookup"><span data-stu-id="75cea-159">Install, and activate the Survivable Branch Appliance.</span></span></p></td>
<td><p><span data-ttu-id="75cea-160"><strong>En el sitio de la sucursal:</strong></span><span class="sxs-lookup"><span data-stu-id="75cea-160"><strong>At the branch site:</strong></span></span></p>
<ol>
<li><p><span data-ttu-id="75cea-161">Conecte el equipo con la sucursal que sea superviviente a un puerto Ethernet y Puerto RTC.</span><span class="sxs-lookup"><span data-stu-id="75cea-161">Connect the Survivable Branch Appliance to an Ethernet port and PSTN port.</span></span></p></li>
<li><p><span data-ttu-id="75cea-162">Inicia la aplicación de la sucursal que sea superviviente.</span><span class="sxs-lookup"><span data-stu-id="75cea-162">Start the Survivable Branch Appliance.</span></span></p></li>
<li><p><span data-ttu-id="75cea-163">Únase al dominio de la sucursal con la que se pueda hacer uso de la cuenta de usuario de dominio que se creó para la aplicación de la rama superviviente en el sitio central.</span><span class="sxs-lookup"><span data-stu-id="75cea-163">Join the Survivable Branch Appliance to the domain, using the domain user account created for the Survivable Branch Appliance at the central site.</span></span> <span data-ttu-id="75cea-164">Establezca el FQDN y la dirección IP para que coincidan con el FQDN creado en la cuenta del equipo.</span><span class="sxs-lookup"><span data-stu-id="75cea-164">Set the FQDN and IP address to match the FQDN created in the computer account.</span></span></p></li>
<li><p><span data-ttu-id="75cea-165">Configure el equipo con la interfaz de usuario OEM.</span><span class="sxs-lookup"><span data-stu-id="75cea-165">Configure the Survivable Branch Appliance using the OEM user interface.</span></span></p></li>
<li><p><span data-ttu-id="75cea-166">Pruebe la conectividad RTC.</span><span class="sxs-lookup"><span data-stu-id="75cea-166">Test PSTN connectivity.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="75cea-167">La cuenta de usuario del técnico debe ser miembro de RTCUniversalSBATechnicians.</span><span class="sxs-lookup"><span data-stu-id="75cea-167">The technician user account must be a member of RTCUniversalSBATechnicians.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="survivable-branch-server-details"></a><span data-ttu-id="75cea-168">Detalles del servidor de sucursal superviviente</span><span class="sxs-lookup"><span data-stu-id="75cea-168">Survivable Branch Server Details</span></span>

<span data-ttu-id="75cea-169">En el generador de topología, cree el sitio de sucursal, agregue el servidor de sucursal con la supervivencia y, a continuación, ejecute el Asistente para la implementación de Lync Server en el equipo en el que desea instalar el rol.</span><span class="sxs-lookup"><span data-stu-id="75cea-169">In Topology Builder create the branch site, add the Survivable Branch Server to that site, and then run the Lync Server Deployment Wizard on the computer where you want to install the role.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="75cea-170">Vea también</span><span class="sxs-lookup"><span data-stu-id="75cea-170">See Also</span></span>


[<span data-ttu-id="75cea-171">Implementar Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75cea-171">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

