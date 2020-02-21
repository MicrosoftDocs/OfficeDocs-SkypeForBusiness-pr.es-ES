---
title: Sitios de 2013 de Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Sites
ms:assetid: 022cb6dd-37e2-4882-a53e-5ddfdbc6f53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398076(v=OCS.15)
ms:contentKeyID: 48183233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37843e85f5da250b3cb3d8e0fa4cdccdf506176d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200273"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-sites-for-lync-server-2013"></a><span data-ttu-id="7e520-102">Sitios de Lync Server para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e520-102">Lync Server sites for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e520-103">_**Última modificación del tema:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="7e520-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="7e520-104">En Lync Server, puede definir *sitios* en la red que contengan componentes de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7e520-104">In Lync Server, you define *sites* on your network that contain Lync Server components.</span></span> <span data-ttu-id="7e520-105">Un sitio es un conjunto de equipos con una buena conexión de red de alta velocidad y baja latencia, como, por ejemplo, una red de área local (LAN) única o dos redes conectadas a través de una red de fibra óptica de alta velocidad.</span><span class="sxs-lookup"><span data-stu-id="7e520-105">A site is a set of computers that is well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> <span data-ttu-id="7e520-106">Tenga en cuenta que los sitios de Lync Server son un concepto independiente de los sitios de servicios de dominio de Active Directory y los sitios de Microsoft Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="7e520-106">Note that Lync Server sites are a separate concept from Active Directory Domain Services sites and Microsoft Exchange Server sites.</span></span> <span data-ttu-id="7e520-107">No es necesario que los sitios de Lync Server correspondan con sus sitios de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7e520-107">Your Lync Server sites do not need to correspond to your Active Directory sites.</span></span>

<div>

## <a name="site-types"></a><span data-ttu-id="7e520-108">Tipos de sitio</span><span class="sxs-lookup"><span data-stu-id="7e520-108">Site Types</span></span>

<span data-ttu-id="7e520-109">Cada sitio puede ser un *sitio central*, que contiene al menos un grupo de servidores front-end o un servidor Standard Edition, o un *sitio de sucursal*.</span><span class="sxs-lookup"><span data-stu-id="7e520-109">Each site is either a *central site*, which contains at least one Front End pool or a Standard Edition server, or a *branch site*.</span></span> <span data-ttu-id="7e520-110">Cada sitio de sucursal está asociado exactamente a un sitio central y los usuarios del sitio de sucursal obtienen la mayor parte de su funcionalidad de Lync Server de los servidores en el sitio central asociado.</span><span class="sxs-lookup"><span data-stu-id="7e520-110">Each branch site is associated with exactly one central site, and the users at the branch site get most of their Lync Server functionality from the servers at the associated central site.</span></span>

<span data-ttu-id="7e520-111">Cada una de las sucursales contiene uno de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="7e520-111">Each branch site contains one of the following:</span></span>

  - <span data-ttu-id="7e520-112">Una aplicación de sucursal con funciones de *supervivencia (SBA)*, que es un servidor blade estándar de la industria con un registrador de Lync Server y un servidor de mediación que se ejecuta en Windows Server.</span><span class="sxs-lookup"><span data-stu-id="7e520-112">A *Survivable Branch Appliance (SBA)*, which is an industry-standard blade server with a Lync Server Registrar and a Mediation Server running on Windows Server.</span></span> <span data-ttu-id="7e520-113">La aplicación de sucursal con funciones de supervivencia también contiene una puerta de enlace de red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="7e520-113">The Survivable Branch Appliance also contains a public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="7e520-114">La aplicación de sucursal con funciones de supervivencia está diseñada para sitios de sucursal con entre 25 y 1000 usuarios.</span><span class="sxs-lookup"><span data-stu-id="7e520-114">The Survivable Branch Appliance is designed for branch sites with between 25 and 1000 users.</span></span>

  - <span data-ttu-id="7e520-115">Un servidor de sucursal con funciones de *supervivencia (SBS)*, que es un servidor que ejecuta Windows Server y que cumple los requisitos de hardware especificados y que tiene instalado el software del servidor de mediación y el registrador de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7e520-115">A *Survivable Branch Server (SBS)*, which is a server running Windows Server that meets specified hardware requirements, and that has Lync Server Registrar and Mediation Server software installed on it.</span></span> <span data-ttu-id="7e520-116">Debe conectarse a una puerta de enlace RTC o a un tronco SIP hacia un proveedor de servicios telefónicos.</span><span class="sxs-lookup"><span data-stu-id="7e520-116">It must connect to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span> <span data-ttu-id="7e520-117">El servidor de sucursal con funciones de supervivencia está diseñado para sucursales de entre 1.000 y 5.000 usuarios.</span><span class="sxs-lookup"><span data-stu-id="7e520-117">The Survivable Branch Server is designed for branch sites with between 1000 and 5000 users.</span></span>

  - <span data-ttu-id="7e520-118">Una puerta de enlace RTC y, opcionalmente, un *servidor de mediación*.</span><span class="sxs-lookup"><span data-stu-id="7e520-118">A PSTN gateway, and, optionally, a *Mediation Server*.</span></span> <span data-ttu-id="7e520-119">Para obtener más información sobre este y otros roles de servidor, consulte [roles de servidor en Lync server 2013](lync-server-2013-server-roles.md).</span><span class="sxs-lookup"><span data-stu-id="7e520-119">For details on this and other server roles, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md).</span></span>

<span data-ttu-id="7e520-120">Una sucursal con un vínculo de red de área extensa (WAN) resistente hacia un sitio central puede usar la tercera opción, una puerta de enlace RTC y, opcionalmente, un servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="7e520-120">A branch office with a resilient wide area network (WAN) link to a central site can use the third option—a PSTN gateway, and, optionally, a Mediation Server.</span></span> <span data-ttu-id="7e520-121">Los sitios de sucursal con vínculos menos resistentes deben usar una aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia, que proporcionan resistencia en momentos de errores de red de área extensa.</span><span class="sxs-lookup"><span data-stu-id="7e520-121">Branch office sites with less-resilient links should use a Survivable Branch Appliance or Survivable Branch Server, which provide resiliency in times of wide-area network failures.</span></span> <span data-ttu-id="7e520-122">Por ejemplo, en un sitio con una aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia implementado, los usuarios pueden seguir realizando y recibiendo llamadas de telefonía IP empresarial si la WAN que conecta el sitio de sucursal al sitio central no está disponible.</span><span class="sxs-lookup"><span data-stu-id="7e520-122">For example, in a site with a Survivable Branch Appliance or Survivable Branch Server deployed, users can still make and receive Enterprise Voice calls if the WAN connecting the branch site to the central site is down.</span></span> <span data-ttu-id="7e520-123">Para obtener más información sobre la aplicación de sucursal con funciones de supervivencia, el servidor de sucursal con funciones de supervivencia y la resistencia, consulte [Planning for Enterprise Voice Resiliency in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="7e520-123">For details about the Survivable Branch Appliance, Survivable Branch Server, and resiliency, see [Planning for Enterprise Voice resiliency in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="site-topologies"></a><span data-ttu-id="7e520-124">Topología de sitios</span><span class="sxs-lookup"><span data-stu-id="7e520-124">Site Topologies</span></span>

<span data-ttu-id="7e520-125">La implementación debe incluir un sitio central como mínimo, y puede incluir de ninguna a muchas sucursales.</span><span class="sxs-lookup"><span data-stu-id="7e520-125">Your deployment must include at least one central site, and can include zero to many branch sites.</span></span> <span data-ttu-id="7e520-126">Cada una de las sucursales está afiliada a un sitio central.</span><span class="sxs-lookup"><span data-stu-id="7e520-126">Each branch site is affiliated with one central site.</span></span> <span data-ttu-id="7e520-127">El sitio central proporciona los servicios de Lync Server al sitio de sucursal que no se hospedan de forma local en el sitio de sucursal, como la presencia y la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="7e520-127">The central site provides the Lync Server services to the branch site that are not hosted locally at the branch site, such as presence and conferencing.</span></span>

<span data-ttu-id="7e520-128">Si tiene varios sitios, puede emparejar los grupos de servidores de front-end en diferentes sitios para habilitar capacidades de recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="7e520-128">If you have multiple sites, you can pair together the Front End pools at different sites to enable disaster recovery abilities.</span></span> <span data-ttu-id="7e520-129">Para obtener más información, consulte [compatibilidad con alta disponibilidad y recuperación ante desastres en Lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md).</span><span class="sxs-lookup"><span data-stu-id="7e520-129">For details, see [High availability and disaster recovery support in Lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7e520-130">Consulta también</span><span class="sxs-lookup"><span data-stu-id="7e520-130">See Also</span></span>


[<span data-ttu-id="7e520-131">Roles de servidor en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e520-131">Server roles in Lync Server 2013</span></span>](lync-server-2013-server-roles.md)  
[<span data-ttu-id="7e520-132">Compatibilidad de alta disponibilidad y recuperación ante desastres en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e520-132">High availability and disaster recovery support in Lync Server 2013</span></span>](lync-server-2013-high-availability-and-disaster-recovery-support.md)  


[<span data-ttu-id="7e520-133">Planeación de la resistencia de la telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e520-133">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

