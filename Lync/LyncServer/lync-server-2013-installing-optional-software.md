---
title: 'Lync Server 2013: instalar software opcional'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing optional software
ms:assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615032(v=OCS.15)
ms:contentKeyID: 51541509
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 080f27b1e01f86d23fd5fd7bf6fdb9e9a05c0742
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045272"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-optional-software-in-lync-server-2013"></a><span data-ttu-id="a70fe-102">Instalación de software opcional en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a70fe-102">Installing optional software in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a70fe-103">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="a70fe-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="a70fe-104">La herramienta de planeación 2013 de Microsoft Lync Server está diseñada para exportar a Microsoft Excel y Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="a70fe-104">The Microsoft Lync Server 2013, Planning Tool is designed to export to Microsoft Excel and Microsoft Visio.</span></span> <span data-ttu-id="a70fe-105">Aunque estas aplicaciones no son necesarias para el funcionamiento de la herramienta de planeación, agregan un valor significativo a la implementación y la documentación del diseño.</span><span class="sxs-lookup"><span data-stu-id="a70fe-105">While these applications are not required for the operation of the Planning Tool, they do add significant value to the deployment and documentation of your design.</span></span>

<div>

## <a name="optional-software"></a><span data-ttu-id="a70fe-106">Software opcional</span><span class="sxs-lookup"><span data-stu-id="a70fe-106">Optional Software</span></span>

<div>

## <a name="microsoft-excel"></a><span data-ttu-id="a70fe-107">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="a70fe-107">Microsoft Excel</span></span>

<span data-ttu-id="a70fe-108">La exportación de su diseño a Microsoft Excel genera un informe que muestra siete pestañas en la hoja de cálculo:</span><span class="sxs-lookup"><span data-stu-id="a70fe-108">Exporting your design to Microsoft Excel creates a report that displays seven tabs in the spreadsheet:</span></span>

  - <span data-ttu-id="a70fe-109">Resumen: muestra información sobre la configuración del sitio, incluidos el número de usuarios, la configuración de capacidad y la información de perfil del servidor.</span><span class="sxs-lookup"><span data-stu-id="a70fe-109">Summary – Displays information on site configuration, including user count, capacity settings, and server profile information.</span></span>

  - <span data-ttu-id="a70fe-110">Perfil de hardware: muestra un informe sobre las configuraciones de hardware recomendadas para los servidores que se especifican en la topología, incluida la CPU, la memoria, el disco y la interfaz de red.</span><span class="sxs-lookup"><span data-stu-id="a70fe-110">Hardware Profile – Displays a report on the recommended hardware configurations for servers that are specified in the topology, including CPU, memory, disk, and network interface.</span></span> <span data-ttu-id="a70fe-111">También se incluye la cantidad y las especificaciones recomendadas para los componentes del servidor.</span><span class="sxs-lookup"><span data-stu-id="a70fe-111">The quantity and recommended specifications for the server components are also included.</span></span> <span data-ttu-id="a70fe-112">Además, cada servidor se define por sitio para proporcionar una representación completa de los requisitos del servidor por sitio.</span><span class="sxs-lookup"><span data-stu-id="a70fe-112">In addition, each server is defined by site to provide a complete representation of server requirements by site.</span></span>

  - <span data-ttu-id="a70fe-113">Requisitos de puertos: muestra un informe de todos los puertos que están habilitados y la asociación con el equilibrio de carga del sistema de nombres de dominio (DNS LB) y los equilibradores de carga de hardware (HLB).</span><span class="sxs-lookup"><span data-stu-id="a70fe-113">Ports Requirements – Displays a report of all ports that are enabled, and the association to Domain Name System load balancing (DNS LB) and hardware load balancers (HLB).</span></span> <span data-ttu-id="a70fe-114">Debe usar este informe para planear el firewall y las configuraciones de DNS LB y HLB.</span><span class="sxs-lookup"><span data-stu-id="a70fe-114">You should use this report to plan your firewall and DNS LB and HLB configurations.</span></span>

  - <span data-ttu-id="a70fe-115">Informe de Resumen: muestra el resumen general de la configuración necesaria para configurar la red del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="a70fe-115">Summary Report – Displays the general summary of the settings that are required to set up your Edge Server network.</span></span>

  - <span data-ttu-id="a70fe-116">Informe de certificados: muestra el nombre del sujeto y los nombres alternativos de sujeto necesarios para los certificados necesarios para obtener los servidores perimetrales que ejecutan.</span><span class="sxs-lookup"><span data-stu-id="a70fe-116">Certificates Report – Displays the subject name and subject alternate names that are required for the certificates needed to get the Edge Servers running.</span></span>

  - <span data-ttu-id="a70fe-117">Informe de Firewall: muestra los puertos de origen y de destino, así como las direcciones IP de las interfaces externas e internas.</span><span class="sxs-lookup"><span data-stu-id="a70fe-117">Firewall Report – Displays the source and destination ports and IP addresses for both External and Internal interfaces.</span></span>

  - <span data-ttu-id="a70fe-118">Informe de DNS: muestra el nombre de dominio completo (FQDN) y las direcciones IP/VIP necesarias para cada entrada de DNS que cree.</span><span class="sxs-lookup"><span data-stu-id="a70fe-118">DNS Report – Displays the fully qualified domain name (FQDN) and IP/VIP addresses required for each DNS entry that you create.</span></span>

</div>

<div>

## <a name="microsoft-visio"></a><span data-ttu-id="a70fe-119">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="a70fe-119">Microsoft Visio</span></span>

<span data-ttu-id="a70fe-120">La exportación de su diseño a Microsoft Visio crea un diagrama para su uso en los fines de documentación de la topología y la infraestructura configuradas.</span><span class="sxs-lookup"><span data-stu-id="a70fe-120">Exporting your design to Microsoft Visio creates a diagram for use in your documentation purposes of your configured topology and infrastructure.</span></span> <span data-ttu-id="a70fe-121">El diagrama importado puede editarse y reorganizarse para satisfacer las necesidades de documentación.</span><span class="sxs-lookup"><span data-stu-id="a70fe-121">The imported diagram can be edited and rearranged to meet your documentation needs.</span></span> <span data-ttu-id="a70fe-122">El diagrama típico de Visio incluirá:</span><span class="sxs-lookup"><span data-stu-id="a70fe-122">The typical Visio diagram will include:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a70fe-123">Si el diseño es lo suficientemente grande como para requerir más de tres servidores front-end, se creará una página adicional para el grupo de servidores front-end, los servidores front-end, el equipo que ejecuta SQL Server, las direcciones IP y los FQDN.</span><span class="sxs-lookup"><span data-stu-id="a70fe-123">If your design is large enough to require more than three Front End Servers, an additional page will be created for the Front End pool, Front End Servers, the computer running SQL Server, IP addresses, and FQDNs.</span></span>



</div>

  - <span data-ttu-id="a70fe-124">Topología global: Diagrama de sitios configurados de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a70fe-124">Global Topology – Diagram of configured Lync Server 2013 sites.</span></span>

  - <span data-ttu-id="a70fe-125">Ficha nombre de sitio: muestra la topología de configuración de sitio con servidor perimetral, firewall, red telefónica conmutada (RTC) con puertas de enlace y la implementación de servidor interna.</span><span class="sxs-lookup"><span data-stu-id="a70fe-125">Site Name tab – Displays the site configuration topology with Edge Server, firewall, public switched telephone network (PSTN) with gateways, and the internal server deployment.</span></span> <span data-ttu-id="a70fe-126">La implementación interna consta de servidores y grupos de servidores configurados, incluidos los grupos de servidores front-end, los servidores basados en SQL Server, los servicios de dominio de Active Directory, los directores, los servidores de mensajería unificada de Exchange, los servidores de buzones de Exchange y los servidores de Office Web Apps. Servidores de mediación y servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="a70fe-126">Internal deployment consists of configured servers and pools, including the Front End pools, SQL Server-based servers, Active Directory Domain Services, Directors, Exchange Unified Messaging (UM) servers, Exchange Mailbox Servers, Office Web Apps Servers, Mediation Servers, and Persistent Chat Servers.</span></span>

  - <span data-ttu-id="a70fe-127">Diagrama de red perimetral: diagrama que detalla la configuración del servidor perimetral con las direcciones IP y los FQDN asociados.</span><span class="sxs-lookup"><span data-stu-id="a70fe-127">Edge Network Diagram – Diagram detailing the Edge Server configuration with associated IP addresses and FQDNs.</span></span> <span data-ttu-id="a70fe-128">También se incluyen equilibrio de carga de DNS y equilibradores de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="a70fe-128">DNS load balancing and hardware load balancers are also included.</span></span> <span data-ttu-id="a70fe-129">Además, se muestran los directores y el servidor front-end o el grupo de servidores front-end, con el DNS LB o HLB asociado y la dirección IP asignada (la herramienta de planeación admite direcciones IPv4 e IPv6) y el FQDN.</span><span class="sxs-lookup"><span data-stu-id="a70fe-129">Additionally, Directors and the Front End Server or Front End pool are displayed, with associated DNS LB or HLB and the assigned IP address (the Planning Tool supports both IPv4 and IPv6 addresses) and FQDN.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a70fe-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="a70fe-130">See Also</span></span>


[<span data-ttu-id="a70fe-131">Instalar la herramienta de planeación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a70fe-131">Installing the Planning Tool in Lync Server 2013</span></span>](lync-server-2013-installing-the-planning-tool.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

