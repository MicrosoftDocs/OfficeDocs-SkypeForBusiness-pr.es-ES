---
title: 'Lync Server 2013: Lista de comprobación de la implementación del acceso de usuarios externos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for external user access
ms:assetid: 3f55f502-88a0-4315-8783-45a32a0b78ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425910(v=OCS.15)
ms:contentKeyID: 48183947
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c8831e8bd94040095fabd9fb335113b62b5287b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835518"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="938d1-102">Lista de comprobación de la implementación del acceso de usuarios externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="938d1-102">Deployment checklist for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="938d1-103">_**Última modificación del tema:** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="938d1-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="938d1-104">Antes de implementar la red perimetral e implementar compatibilidad para usuarios externos, ya debe haber implementado sus servidores internos de Microsoft Lync Server 2013, incluido un grupo de servidores front-end o un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="938d1-104">Before you deploy your perimeter network and implement support for external users, you must already have deployed your Microsoft Lync Server 2013 internal servers, including a Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="938d1-105">Si planea implementar los directores opcionales en su red interna, también debe implementarlos antes de implementar servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="938d1-105">If you plan to deploy the optional Directors in your internal network, you should also deploy them prior to deploying Edge Servers.</span></span> <span data-ttu-id="938d1-106">Para obtener más información sobre el proceso de implementación de Director, consulte [escenarios del Director de Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="938d1-106">For details about the Director deployment process, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in the Planning documentation.</span></span>

<span data-ttu-id="938d1-107">Microsoft Lync Server 2013 incluye herramientas para facilitar la planificación y la implementación de servidores internos y servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="938d1-107">Microsoft Lync Server 2013 includes tools to facilitate planning and deployment of both internal servers and Edge Servers.</span></span> <span data-ttu-id="938d1-108">Una vez completada la topología, publique la definición de topología resultante en su entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="938d1-108">After the topology is completed, publish the resulting topology definition to your production environment.</span></span> <span data-ttu-id="938d1-109">Para ello, debe ser miembro del grupo **administradores de dominio** y del grupo **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="938d1-109">To do this, you must be a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group.</span></span>

  - <span data-ttu-id="938d1-110">**Herramienta**   de planeación Office Communications Server 2007 R2 incluye una herramienta de planificación y una herramienta de planeación de bordes que puede usar para guiar el diseño de la topología.</span><span class="sxs-lookup"><span data-stu-id="938d1-110">**Planning Tool**   Office Communications Server 2007 R2 included a Planning Tool and an Edge Planning Tool that you could use to help guide topology design.</span></span> <span data-ttu-id="938d1-111">En Lync Server 2010, estas dos herramientas se combinaron en una sola herramienta de planeación con características y funciones adicionales, como la recopilación de recuento de usuarios planificados, los requisitos de voz, los tipos de acceso de usuarios externos y las opciones de Federación.</span><span class="sxs-lookup"><span data-stu-id="938d1-111">In Lync Server 2010, these two tools were combined into a single Planning Tool that has additional features and functionality, such as collecting planned user count, voice requirements, external user access types, and federation options.</span></span> <span data-ttu-id="938d1-112">Además, puede planear los parámetros de red de la infraestructura, como direcciones IP, tipos de equilibradores de carga y otras consideraciones de la red perimetral.</span><span class="sxs-lookup"><span data-stu-id="938d1-112">Additionally, you can plan your infrastructure’s network parameters, such as IP addresses, load balancer types and other perimeter network considerations.</span></span>

  - <span data-ttu-id="938d1-113">\*\*\*\*   El generador de topologías Lync Server 2013 Builder le ayuda a definir su topología y sus componentes.</span><span class="sxs-lookup"><span data-stu-id="938d1-113">**Topology Builder**   Lync Server 2013 Topology Builder helps you define your topology and components.</span></span> <span data-ttu-id="938d1-114">El generador de topología es esencial para implementar servidores que ejecuten Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="938d1-114">Topology Builder is essential to deploying servers running Lync Server 2013.</span></span> <span data-ttu-id="938d1-115">El generador de topología publica los resultados en un almacén de administración central que se usa para configurar todos los servidores que ejecutan Lync Server 2013 de su organización.</span><span class="sxs-lookup"><span data-stu-id="938d1-115">Topology Builder publishes the results to a Central Management store that is used to configure all of the servers running Lync Server 2013 in your organization.</span></span> <span data-ttu-id="938d1-116">No puede instalar Lync Server 2013 en servidores sin usar el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="938d1-116">You cannot install Lync Server 2013 on servers without using Topology Builder.</span></span>

<span data-ttu-id="938d1-117">Si ha diseñado su topología perimetral durante el proceso de planeación, incluida la ejecución del generador de topología para definir la topología perimetral, puede usar esos resultados para iniciar la implementación del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="938d1-117">If you designed your edge topology during your planning process, including running Topology Builder to define your edge topology, you can use those results to start your Edge Server deployment.</span></span> <span data-ttu-id="938d1-118">Si no ha terminado de crear la topología de borde antes o quiere cambiar la información que especificó anteriormente, debe terminar de ejecutar el generador de topología antes de seguir con otros pasos de implementación.</span><span class="sxs-lookup"><span data-stu-id="938d1-118">If you did not finish building your edge topology earlier or you want to change the information you previously specified, you must finish running Topology Builder before proceeding with other deployment steps.</span></span> <span data-ttu-id="938d1-119">Para obtener más información sobre cómo crear su topología, consulte [escenarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="938d1-119">For details about how to build your topology, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="938d1-120">Para obtener más información sobre la herramienta de planificación y el generador de topología, consulte [comenzar el proceso de planeación de Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="938d1-120">For details about the Planning Tool and Topology Builder, see [Beginning the planning process for Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) in the Planning documentation.</span></span>

<span data-ttu-id="938d1-121">En la tabla siguiente se proporciona una descripción general del proceso de implementación del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="938d1-121">The following table provides an overview of the Edge Server deployment process.</span></span> <span data-ttu-id="938d1-122">Para revisar las decisiones de planeación que se deben realizar antes de implementar el acceso de usuarios externos, consulte [escenarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="938d1-122">To review the planning decisions that must be made before deploying external user access, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="938d1-123">La información de la tabla siguiente se centra en una nueva implementación.</span><span class="sxs-lookup"><span data-stu-id="938d1-123">The information in the following table focuses on a new deployment.</span></span> <span data-ttu-id="938d1-124">Si ha implementado servidores perimetrales en un entorno de Lync Server 2010, Office Communications Server 2007 R2 u Office Communications Server 2007, consulte la <A href="migration.md">migración</A> para obtener más detalles sobre cómo migrar a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="938d1-124">If you have deployed Edge Servers in a Lync Server 2010, Office Communications Server 2007 R2 or Office Communications Server 2007 environment, see the <A href="migration.md">Migration</A> for details about migrating to Lync Server 2013.</span></span> <span data-ttu-id="938d1-125">La migración no es compatible desde ninguna versión anterior a Office Communications Server 2007 R2, incluidos Office Communications Server 2007, Live Communications Server 2005 y Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="938d1-125">Migration is not supported from any version prior to Office Communications Server 2007 R2, including Office Communications Server 2007, Live Communications Server 2005, and Live Communications Server 2003.</span></span>



</div>

<span data-ttu-id="938d1-126">Para mejorar la seguridad y el rendimiento del servidor perimetral, y para facilitar la implementación, aplique los siguientes procedimientos recomendados al implementar la red perimetral y los servidores perimetrales:</span><span class="sxs-lookup"><span data-stu-id="938d1-126">To enhance Edge Server performance and security, and to facilitate deployment, apply the following best practices when you deploy your perimeter network and Edge Servers:</span></span>

  - <span data-ttu-id="938d1-127">Implemente servidores perimetrales solo después de probar y comprobar el funcionamiento de Lync Server 2013 dentro de su organización.</span><span class="sxs-lookup"><span data-stu-id="938d1-127">Deploy Edge Servers only after you have tested and verified operation of Lync Server 2013 inside your organization.</span></span>

  - <span data-ttu-id="938d1-128">Le recomendamos que implemente servidores perimetrales en un grupo de trabajo en lugar de un dominio.</span><span class="sxs-lookup"><span data-stu-id="938d1-128">We recommend that you deploy Edge Servers in a workgroup rather than a domain.</span></span> <span data-ttu-id="938d1-129">Esto simplifica la instalación y mantiene fuera de la red perimetral los servicios de dominio de Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="938d1-129">Doing so simplifies installation and keeps Active Directory Domain Services (AD DS) out of the perimeter network.</span></span> <span data-ttu-id="938d1-130">Localizar AD DS en la red perimetral puede representar un importante riesgo para la seguridad.</span><span class="sxs-lookup"><span data-stu-id="938d1-130">Locating AD DS in the perimeter network can present a significant security risk.</span></span>

  - <span data-ttu-id="938d1-131">Unirse a un servidor perimetral a un dominio ubicado por completo en la red perimetral es compatible, pero no recomendado.</span><span class="sxs-lookup"><span data-stu-id="938d1-131">Joining an Edge Server to a domain located entirely in the perimeter network is supported but not recommended.</span></span> <span data-ttu-id="938d1-132">Un servidor perimetral como parte del dominio interno infringe los límites de la red de confianza, donde Internet es de menor confianza, la red perimetral es más confiable que Internet y la red interna es de mayor confianza.</span><span class="sxs-lookup"><span data-stu-id="938d1-132">An Edge Server as part of the internal domain violates trusted network boundaries, where the Internet is least trusted, perimeter network is more trusted than the Internet, and the internal network is most trusted.</span></span> <span data-ttu-id="938d1-133">Un servidor perimetral como miembro del dominio es automáticamente una parte de la red de mayor confianza, pero reside en una red de menos confianza (el perímetro).</span><span class="sxs-lookup"><span data-stu-id="938d1-133">An Edge server as a member of the domain is automatically a part of the most trusted network, but resides in a less trusted network (the perimeter).</span></span>

<div>

## <a name="deployment-process-for-edge-servers"></a><span data-ttu-id="938d1-134">Proceso de implementación para servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="938d1-134">Deployment Process for Edge Servers</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="938d1-135">Fase</span><span class="sxs-lookup"><span data-stu-id="938d1-135">Phase</span></span></th>
<th><span data-ttu-id="938d1-136">Pasos</span><span class="sxs-lookup"><span data-stu-id="938d1-136">Steps</span></span></th>
<th><span data-ttu-id="938d1-137">Permisos</span><span class="sxs-lookup"><span data-stu-id="938d1-137">Permissions</span></span></th>
<th><span data-ttu-id="938d1-138">Documentación</span><span class="sxs-lookup"><span data-stu-id="938d1-138">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="938d1-139">Cree la topología de arista adecuada y determine los componentes apropiados.</span><span class="sxs-lookup"><span data-stu-id="938d1-139">Create the appropriate edge topology and determine the appropriate components.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="938d1-140">Ejecute el generador de topología para establecer la configuración del servidor perimetral, crear y publicar la topología y, a continuación, usar el shell de administración de Lync Server para exportar el archivo de configuración de topología.</span><span class="sxs-lookup"><span data-stu-id="938d1-140">Run Topology Builder to configure Edge Server settings and create and publish the topology, and then use Lync Server Management Shell to export the topology configuration file.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="938d1-141">Grupo <strong>administradores de dominio</strong> y grupo <strong>RTCUniversalServerAdmins</strong> o <strong>CsAdmins</strong></span><span class="sxs-lookup"><span data-stu-id="938d1-141"><strong>Domain Admins</strong> group and <strong>RTCUniversalServerAdmins</strong> or <strong>CsAdmins</strong> group</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="938d1-142">Puede definir una topología con una cuenta que sea miembro del grupo usuarios locales, pero la publicación de una topología requiere una cuenta que sea miembro del grupo <STRONG>administradores de dominio</STRONG> y del grupo <STRONG>RTCUniversalServerAdmins</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="938d1-142">You can define a topology using an account that is a member of the local users group, but publishing a topology requires an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group.</span></span>


</div></td>
<td><p><span data-ttu-id="938d1-143"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Creación de una topología de Edge y Director en Lync Server 2013</a> en la documentación de implementación</span><span class="sxs-lookup"><span data-stu-id="938d1-143"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Building an edge and Director topology in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="938d1-144">Prepararse para la configuración.</span><span class="sxs-lookup"><span data-stu-id="938d1-144">Prepare for setup.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="938d1-145">Asegúrese de que se cumplan los requisitos previos del sistema.</span><span class="sxs-lookup"><span data-stu-id="938d1-145">Ensure that system prerequisites are met.</span></span></p></li>
<li><p><span data-ttu-id="938d1-146">Configure las direcciones IP (IPv4 e IPv6, si las hay) para las interfaces de red orientadas interna y pública en cada servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="938d1-146">Configure IP addresses (IPv4 and IPv6, if used) for both internal and public facing network interfaces on each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="938d1-147">Configure los registros DNS internos y externos (host A y AAAA para IPv4 e IPv6), incluyendo la configuración del sufijo DNS en el equipo que se va a implementar como servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="938d1-147">Configure internal and external DNS records (host A and AAAA for IPv4 and IPv6), including configuring the DNS suffix on the computer to be deployed as an Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="938d1-148">Faculta Crear e instalar certificados públicos.</span><span class="sxs-lookup"><span data-stu-id="938d1-148">(Optional) Create and install public certificates.</span></span> <span data-ttu-id="938d1-149">El tiempo necesario para obtener certificados depende de la entidad emisora de certificados (CA) que emite el certificado.</span><span class="sxs-lookup"><span data-stu-id="938d1-149">The time required to obtain certificates depends on which certification authority (CA) issues the certificate.</span></span> <span data-ttu-id="938d1-150">Si no realiza este paso en este punto, debe hacerlo durante la instalación del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="938d1-150">If you do not perform this step at this point, you must do it during Edge Server installation.</span></span> <span data-ttu-id="938d1-151">Los servicios del servidor perimetral no se pueden iniciar hasta que se obtengan e instalen certificados.</span><span class="sxs-lookup"><span data-stu-id="938d1-151">The Edge Server services cannot be started until certificates are obtained and installed.</span></span></p></li>
<li><p><span data-ttu-id="938d1-152">Proporcionar compatibilidad con la conectividad de mensajería instantánea pública, si su implementación es compatible con las comunicaciones con Windows Live, AOL o Yahoo!</span><span class="sxs-lookup"><span data-stu-id="938d1-152">Provision support for public IM connectivity, if your deployment is to support communications with Windows Live, AOL, or Yahoo!</span></span> <span data-ttu-id="938d1-153">User.</span><span class="sxs-lookup"><span data-stu-id="938d1-153">users.</span></span></p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="938d1-154">A partir del 1 de septiembre de 2012, la licencia de suscripción de usuario de conectividad de mensajería instantánea pública de Microsoft Lync ("PIC USL") ya no está disponible para la compra de contratos nuevos o de renovación.</span><span class="sxs-lookup"><span data-stu-id="938d1-154">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="938d1-155">Los clientes con licencias activas podrán seguir federando a Yahoo!</span><span class="sxs-lookup"><span data-stu-id="938d1-155">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="938d1-156">Messenger hasta que se cierre la fecha del servicio.</span><span class="sxs-lookup"><span data-stu-id="938d1-156">Messenger until the service shut down date.</span></span> <span data-ttu-id="938d1-157">Una fecha de fin de vida de junio de 2014 para AOL y Yahoo!</span><span class="sxs-lookup"><span data-stu-id="938d1-157">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="938d1-158">ha sido anunciado.</span><span class="sxs-lookup"><span data-stu-id="938d1-158">has been announced.</span></span> <span data-ttu-id="938d1-159">Para obtener más información, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">compatibilidad de la conectividad de mensajería instantánea pública en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="938d1-159">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="938d1-160">El PIC USL es una licencia por usuario por mes de suscripción que es necesaria para que Lync Server o Office Communications Server se federe con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="938d1-160">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="938d1-161">Mensajería.</span><span class="sxs-lookup"><span data-stu-id="938d1-161">Messenger.</span></span> <span data-ttu-id="938d1-162">La capacidad de Microsoft para proporcionar este servicio está supeditada al soporte de Yahoo!, el contrato subyacente para el que se está pospuesto.</span><span class="sxs-lookup"><span data-stu-id="938d1-162">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="938d1-163">Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="938d1-163">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="938d1-164">La Federación con Windows Live Messenger no requiere licencias adicionales para usuarios y dispositivos más allá de la CAL de Lync Standard.</span><span class="sxs-lookup"><span data-stu-id="938d1-164">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="938d1-165">La Federación de Skype se agrega a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas con la mensajería instantánea y la voz.</span><span class="sxs-lookup"><span data-stu-id="938d1-165">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


</div></li>
<li><p><span data-ttu-id="938d1-166">Soporte técnico para la compatibilidad con la compatibilidad con la Federación de Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 Partners, si la implementación va a usar estos</span><span class="sxs-lookup"><span data-stu-id="938d1-166">Provision support for XMPP and federation support for Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 partners, if your deployment will use these</span></span></p></li>
<li><p><span data-ttu-id="938d1-167">Configurar firewalls.</span><span class="sxs-lookup"><span data-stu-id="938d1-167">Configure firewalls.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="938d1-168">Según corresponda a su organización</span><span class="sxs-lookup"><span data-stu-id="938d1-168">As appropriate to your organization</span></span></p></td>
<td><p><span data-ttu-id="938d1-169"><a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Prepararse para la instalación de servidores en la red perimetral para Lync Server 2013</a> en la documentación de implementación</span><span class="sxs-lookup"><span data-stu-id="938d1-169"><a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Preparing for installation of servers in the perimeter network for Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="938d1-170">Configurar proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="938d1-170">Set up reverse proxy.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="938d1-171">Configurar el proxy inverso (por ejemplo, para Microsoft Forefront Threat Management Gateway 2010 o Microsoft Internet Security and Acceleration (ISA) Server con Service Pack 1) en la red perimetral, obtener los certificados públicos necesarios y configurar los reglas de publicación web en el servidor proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="938d1-171">Set up the reverse proxy (for example, for Microsoft Forefront Threat Management Gateway 2010 or Microsoft Internet Security and Acceleration (ISA) Server with Service Pack 1) in the perimeter network, obtain the necessary public certificates, and configure the web publishing rules on the reverse proxy server.</span></span></p>
<p><span data-ttu-id="938d1-172">Prepare el proxy inverso para los servicios de movilidad si ha planeado para la movilidad y va a implementar los servicios de movilidad en el grupo de servidores front-end o en el servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="938d1-172">Prepare the reverse proxy for Mobility services if you have planned for Mobility and are deploying the Mobility services on the Front End pool or Standard Edition server.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="938d1-173">Grupo <strong>administradores</strong> o administrador de proxy inverso</span><span class="sxs-lookup"><span data-stu-id="938d1-173"><strong>Administrators</strong> group or Reverse Proxy administrator</span></span></p></td>
<td><p><span data-ttu-id="938d1-174"><a href="lync-server-2013-setting-up-reverse-proxy-servers.md">Configuración de servidores proxy inversos para Lync Server 2013</a> en la documentación de implementación</span><span class="sxs-lookup"><span data-stu-id="938d1-174"><a href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="938d1-175">Configurar un director (opcional).</span><span class="sxs-lookup"><span data-stu-id="938d1-175">Setup a Director (optional).</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="938d1-176">Faculta Instale y configure uno o más directores en la red interna.</span><span class="sxs-lookup"><span data-stu-id="938d1-176">(Optional) Install and configure one or more Directors in the internal network.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="938d1-177">Grupo <strong>administradores</strong></span><span class="sxs-lookup"><span data-stu-id="938d1-177"><strong>Administrators</strong> group</span></span></p></td>
<td><p><span data-ttu-id="938d1-178"><a href="lync-server-2013-setting-up-the-director.md">Configuración del Director de Lync Server 2013</a> en la documentación de implementación</span><span class="sxs-lookup"><span data-stu-id="938d1-178"><a href="lync-server-2013-setting-up-the-director.md">Setting up the Director in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="938d1-179">Configurar servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="938d1-179">Set up Edge Servers.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="938d1-180">Instale el software necesario.</span><span class="sxs-lookup"><span data-stu-id="938d1-180">Install prerequisite software.</span></span></p></li>
<li><p><span data-ttu-id="938d1-181">Transporte el archivo de configuración de la topología exportada a cada servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="938d1-181">Transport the exported topology configuration file to each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="938d1-182">Instale el software Lync Server 2013 en cada servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="938d1-182">Install the Lync Server 2013 software on each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="938d1-183">Configurar los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="938d1-183">Configure the Edge Servers.</span></span></p></li>
<li><p><span data-ttu-id="938d1-184">Solicite e instale certificados para cada servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="938d1-184">Request and install certificates for each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="938d1-185">Inicie los servicios del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="938d1-185">Start the Edge Server services.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="938d1-186">Grupo <strong>administradores</strong></span><span class="sxs-lookup"><span data-stu-id="938d1-186"><strong>Administrators</strong> group</span></span></p></td>
<td><p><span data-ttu-id="938d1-187"><a href="lync-server-2013-setting-up-edge-servers.md">Configuración de servidores perimetrales en Lync Server 2013</a> en la documentación de implementación</span><span class="sxs-lookup"><span data-stu-id="938d1-187"><a href="lync-server-2013-setting-up-edge-servers.md">Setting up Edge Servers in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="938d1-188">Configurar la implementación para el acceso de usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="938d1-188">Configure deployment for external user access.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="938d1-189">Use el panel de control de Lync Server para configurar la compatibilidad de cada uno de los siguientes (según corresponda):</span><span class="sxs-lookup"><span data-stu-id="938d1-189">Use the Lync Server Control Panel to configure support for each of the following (as applicable):</span></span></p>
<ul>
<li><p><span data-ttu-id="938d1-190">Relé multimedia</span><span class="sxs-lookup"><span data-stu-id="938d1-190">Media relay</span></span></p></li>
<li><p><span data-ttu-id="938d1-191">Ruta de Federación</span><span class="sxs-lookup"><span data-stu-id="938d1-191">Federation route</span></span></p></li>
<li><p><span data-ttu-id="938d1-192">Acceso de usuarios remotos</span><span class="sxs-lookup"><span data-stu-id="938d1-192">Remote user access</span></span></p></li>
<li><p><span data-ttu-id="938d1-193">Federación con Lync Server, Office Communications Server y Live Communications Server</span><span class="sxs-lookup"><span data-stu-id="938d1-193">Federation with Lync Server, Office Communications Server and Live Communications Server</span></span></p></li>
<li><p><span data-ttu-id="938d1-194">Conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="938d1-194">Public IM connectivity</span></span></p></li>
<li><p><span data-ttu-id="938d1-195">Federación XMPP</span><span class="sxs-lookup"><span data-stu-id="938d1-195">XMPP federation</span></span></p></li>
<li><p><span data-ttu-id="938d1-196">Usuarios anónimos</span><span class="sxs-lookup"><span data-stu-id="938d1-196">Anonymous users</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="938d1-197">Configurar cuentas de usuario para el acceso de usuarios remotos, la Federación, la conectividad de mensajería instantánea pública, el XMPP y la compatibilidad con usuarios anónimos (según corresponda)</span><span class="sxs-lookup"><span data-stu-id="938d1-197">Configure user accounts for remote user access, federation, public IM connectivity, XMPP and anonymous user support (as applicable)</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="938d1-198"><strong>RTCUniversalServerAdmins</strong> una cuenta de usuario o grupo que está asignada al rol <strong>CSAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="938d1-198"><strong>RTCUniversalServerAdmins</strong> group or user account that is assigned to the <strong>CSAdministrator</strong> role</span></span></p></td>
<td><p><span data-ttu-id="938d1-199">Configuración de la compatibilidad con el <a href="lync-server-2013-configuring-support-for-external-user-access.md">acceso de usuarios externos en Lync Server 2013</a> en la documentación de implementación</span><span class="sxs-lookup"><span data-stu-id="938d1-199"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configuring support for external user access in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="938d1-200">Verifica la configuración del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="938d1-200">Verify your Edge Server configuration.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="938d1-201">Comprobar la Conectividad del servidor y la replicación de datos de configuración desde servidores internos.</span><span class="sxs-lookup"><span data-stu-id="938d1-201">Verify server connectivity and replication of configuration data from internal servers.</span></span></p></li>
<li><p><span data-ttu-id="938d1-202">Compruebe que los usuarios externos pueden conectarse, incluidos los usuarios remotos, los usuarios de dominios federados, los usuarios de mensajería instantánea pública y los usuarios anónimos, según corresponda a su implementación.</span><span class="sxs-lookup"><span data-stu-id="938d1-202">Verify that external users can connect, including remote users, users in federated domains, public IM users, and anonymous users, as appropriate to your deployment.</span></span></p></li>
<li><p><span data-ttu-id="938d1-203">Comprobar la configuración y la comunicación con el analizador de conectividad remota de Lync Server<a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a></span><span class="sxs-lookup"><span data-stu-id="938d1-203">Verify configuration and communication using the Lync Server Remote Connectivity Analyzer <a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a></span></span></p></li>
<li><p><span data-ttu-id="938d1-204">Solucionar problemas de configuración y comunicación</span><span class="sxs-lookup"><span data-stu-id="938d1-204">Troubleshoot configuration and communication difficulties</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="938d1-205">Para la verificación de la replicación, <strong>RTCUniversalServerAdmins</strong> cuenta de usuario o de grupo que está asignada al rol <strong>CSAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="938d1-205">For verification of replication, <strong>RTCUniversalServerAdmins</strong> group or user account that is assigned to the <strong>CSAdministrator</strong> role</span></span></p>
<p><span data-ttu-id="938d1-206">Para comprobar la conectividad de los usuarios, un usuario para cada tipo de acceso de usuarios externos que admita</span><span class="sxs-lookup"><span data-stu-id="938d1-206">For verification of user connectivity, a user for each type of external user access that you support</span></span></p>
<p><span data-ttu-id="938d1-207">Usuarios remotos</span><span class="sxs-lookup"><span data-stu-id="938d1-207">Remote users</span></span></p></td>
<td><p><span data-ttu-id="938d1-208"><a href="lync-server-2013-verifying-your-edge-deployment.md">Comprobar la implementación de extremos en Lync Server 2013</a> en la documentación de implementación</span><span class="sxs-lookup"><span data-stu-id="938d1-208"><a href="lync-server-2013-verifying-your-edge-deployment.md">Verifying your edge deployment in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

