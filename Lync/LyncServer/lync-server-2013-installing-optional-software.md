---
title: 'Lync Server 2013: instalación de software opcional'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing optional software
ms:assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615032(v=OCS.15)
ms:contentKeyID: 51541509
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6723d005a41b52025c7e3e475bc3b3a108f2c3d6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834974"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-optional-software-in-lync-server-2013"></a><span data-ttu-id="91d6b-102">Instalar software opcional en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91d6b-102">Installing optional software in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91d6b-103">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="91d6b-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="91d6b-104">La herramienta de planeación de Microsoft Lync Server 2013 está diseñada para exportar a Microsoft Excel y Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="91d6b-104">The Microsoft Lync Server 2013, Planning Tool is designed to export to Microsoft Excel and Microsoft Visio.</span></span> <span data-ttu-id="91d6b-105">Si bien estas aplicaciones no son necesarias para el funcionamiento de la herramienta de planeación, pueden agregar valor significativo a la implementación y la documentación del diseño.</span><span class="sxs-lookup"><span data-stu-id="91d6b-105">While these applications are not required for the operation of the Planning Tool, they do add significant value to the deployment and documentation of your design.</span></span>

<div>

## <a name="optional-software"></a><span data-ttu-id="91d6b-106">Software opcional</span><span class="sxs-lookup"><span data-stu-id="91d6b-106">Optional Software</span></span>

<div>

## <a name="microsoft-excel"></a><span data-ttu-id="91d6b-107">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="91d6b-107">Microsoft Excel</span></span>

<span data-ttu-id="91d6b-108">La exportación de su diseño a Microsoft Excel genera un informe con cuatro pestañas en la hoja de cálculo:</span><span class="sxs-lookup"><span data-stu-id="91d6b-108">Exporting your design to Microsoft Excel creates a report that displays seven tabs in the spreadsheet:</span></span>

  - <span data-ttu-id="91d6b-109">Resumen: Muestra información sobre la configuración local, incluidos el recuento de usuario, la configuración de capacidad, los roles virtualizados e información del perfil del servidor.</span><span class="sxs-lookup"><span data-stu-id="91d6b-109">Summary – Displays information on site configuration, including user count, capacity settings, and server profile information.</span></span>

  - <span data-ttu-id="91d6b-p102">Perfil de hardware: Muestra un informe sobre las configuraciones de hardware recomendadas para los servidores que se especifican en la topología, incluidos la CPU, la memoria, el disco y la interfaz de red. También contempla la cantidad y las especificaciones recomendadas para los componentes de servidor. De igual modo, cada servidor está definido por el sitio para proporcionar una representación completa de los requisitos del servidor por sitio.</span><span class="sxs-lookup"><span data-stu-id="91d6b-p102">Hardware Profile – Displays a report on the recommended hardware configurations for servers that are specified in the topology, including CPU, memory, disk, and network interface. The quantity and recommended specifications for the server components are also included. In addition, each server is defined by site to provide a complete representation of server requirements by site.</span></span>

  - <span data-ttu-id="91d6b-p103">Requisitos de los puertos: Muestra un informe de todos los puertos que están habilitados y la asociación con el equilibrio de carga del Sistema de nombres de dominio (DNS LB) y los equilibradores de carga de hardware (HLB). Este informe es útil para planear las configuraciones de DNS LB y HLB y del firewall.</span><span class="sxs-lookup"><span data-stu-id="91d6b-p103">Ports Requirements – Displays a report of all ports that are enabled, and the association to Domain Name System load balancing (DNS LB) and hardware load balancers (HLB). You should use this report to plan your firewall and DNS LB and HLB configurations.</span></span>

  - <span data-ttu-id="91d6b-115">Informe Resumen: muestra el resumen general de la configuración necesaria para configurar la red de su servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="91d6b-115">Summary Report – Displays the general summary of the settings that are required to set up your Edge Server network.</span></span>

  - <span data-ttu-id="91d6b-116">Informe de certificados: muestra el nombre del sujeto y los nombres alternativos de asunto necesarios para los certificados necesarios para obtener los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="91d6b-116">Certificates Report – Displays the subject name and subject alternate names that are required for the certificates needed to get the Edge Servers running.</span></span>

  - <span data-ttu-id="91d6b-117">Informe de firewall: Muestra los puertos de origen y de destino y direcciones IP de las interfaces tanto interna como externa.</span><span class="sxs-lookup"><span data-stu-id="91d6b-117">Firewall Report – Displays the source and destination ports and IP addresses for both External and Internal interfaces.</span></span>

  - <span data-ttu-id="91d6b-118">Informe DNS: Muestra el nombre de dominio completo (FQDN) y direcciones IP/VIP que se necesitan para cada entrada DNS que se cree.</span><span class="sxs-lookup"><span data-stu-id="91d6b-118">DNS Report – Displays the fully qualified domain name (FQDN) and IP/VIP addresses required for each DNS entry that you create.</span></span>

</div>

<div>

## <a name="microsoft-visio"></a><span data-ttu-id="91d6b-119">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="91d6b-119">Microsoft Visio</span></span>

<span data-ttu-id="91d6b-p104">La exportación del diseño a Microsoft Visio genera un diagrama para su uso en fines de documentación de la topología y la infraestructura configuradas. El diagrama importado se puede modificar y reorganizar para adaptarlo a sus necesidades de documentación. El típico diagrama de Visio incluirá:</span><span class="sxs-lookup"><span data-stu-id="91d6b-p104">Exporting your design to Microsoft Visio creates a diagram for use in your documentation purposes of your configured topology and infrastructure. The imported diagram can be edited and rearranged to meet your documentation needs. The typical Visio diagram will include:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="91d6b-123">Si el diseño es lo suficientemente grande para requerir más de tres servidores front-end, se creará una página adicional para el grupo front-end, los servidores front-end, el equipo con SQL Server, las direcciones IP y los FQDN.</span><span class="sxs-lookup"><span data-stu-id="91d6b-123">If your design is large enough to require more than three Front End Servers, an additional page will be created for the Front End pool, Front End Servers, the computer running SQL Server, IP addresses, and FQDNs.</span></span>



</div>

  - <span data-ttu-id="91d6b-124">Topología global: Diagrama de sitios de 2013 de Lync Server configurados.</span><span class="sxs-lookup"><span data-stu-id="91d6b-124">Global Topology – Diagram of configured Lync Server 2013 sites.</span></span>

  - <span data-ttu-id="91d6b-125">Ficha nombre del sitio: muestra la topología de configuración del sitio con servidor perimetral, firewall, red de telefonía pública conmutada (RTC) con puertas de enlace y la implementación de servidor interno.</span><span class="sxs-lookup"><span data-stu-id="91d6b-125">Site Name tab – Displays the site configuration topology with Edge Server, firewall, public switched telephone network (PSTN) with gateways, and the internal server deployment.</span></span> <span data-ttu-id="91d6b-126">La implementación interna consta de servidores y grupos de servidores, entre los que se incluyen las secciones front end, los servidores basados en SQL Server, los servicios de dominio de Active Directory, los directores, los servidores de mensajería unificada de Exchange (UM), los servidores de buzón de Exchange y los servidores de Office Web Apps. Servidores de mediación y servidores de chat persistentes.</span><span class="sxs-lookup"><span data-stu-id="91d6b-126">Internal deployment consists of configured servers and pools, including the Front End pools, SQL Server-based servers, Active Directory Domain Services, Directors, Exchange Unified Messaging (UM) servers, Exchange Mailbox Servers, Office Web Apps Servers, Mediation Servers, and Persistent Chat Servers.</span></span>

  - <span data-ttu-id="91d6b-127">Diagrama de red perimetral: diagrama que detalla la configuración del servidor perimetral con las direcciones IP y FQDN asociados.</span><span class="sxs-lookup"><span data-stu-id="91d6b-127">Edge Network Diagram – Diagram detailing the Edge Server configuration with associated IP addresses and FQDNs.</span></span> <span data-ttu-id="91d6b-128">El equilibrio de carga de DNS y los equilibradores de carga de hardware también están incluidos.</span><span class="sxs-lookup"><span data-stu-id="91d6b-128">DNS load balancing and hardware load balancers are also included.</span></span> <span data-ttu-id="91d6b-129">Además, se muestran los directores y el servidor front-end o el grupo front-end, con el DNS LB o HLB asociado y la dirección IP asignada (la herramienta de planeación admite direcciones IPv4 e IPv6) y FQDN.</span><span class="sxs-lookup"><span data-stu-id="91d6b-129">Additionally, Directors and the Front End Server or Front End pool are displayed, with associated DNS LB or HLB and the assigned IP address (the Planning Tool supports both IPv4 and IPv6 addresses) and FQDN.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="91d6b-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="91d6b-130">See Also</span></span>


[<span data-ttu-id="91d6b-131">Instalar la herramienta de planeación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91d6b-131">Installing the Planning Tool in Lync Server 2013</span></span>](lync-server-2013-installing-the-planning-tool.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

