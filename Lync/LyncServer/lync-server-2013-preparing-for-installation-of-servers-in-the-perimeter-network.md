---
title: Preparar la instalación de los servidores en la red del perímetro
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing for installation of servers in the perimeter network
ms:assetid: 5e6c457a-f964-4ef7-a709-97abda9c673a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398416(v=OCS.15)
ms:contentKeyID: 48184292
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8474ea56062a89952001850b1a78fd86f5843cc1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823885"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-for-installation-of-servers-in-the-perimeter-network-for-lync-server-2013"></a><span data-ttu-id="f4266-102">Preparar la instalación de los servidores en la red del perímetro para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4266-102">Preparing for installation of servers in the perimeter network for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4266-103">_**Última modificación del tema:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="f4266-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="f4266-104">Antes de configurar los componentes del servidor perimetral, debe asegurarse de que los equipos que está configurando cumplan los requisitos del sistema y completar otros pasos previos necesarios para la implementación de los componentes del servidor EDGE.</span><span class="sxs-lookup"><span data-stu-id="f4266-104">Before you set up Edge Server components, you need to ensure that computers that you are setting up meet system requirements and complete other prerequisite steps required for deployment of Edge Server components.</span></span>

<span data-ttu-id="f4266-105">Antes de empezar, revise los detalles de los temas siguientes en la documentación de planeación de la arquitectura de referencia que desea implementar:</span><span class="sxs-lookup"><span data-stu-id="f4266-105">Before you begin, review the details in the following topics in the Planning documentation for the reference architecture that you want to deploy:</span></span>

  - [<span data-ttu-id="f4266-106">Servidor perimetral consolidado simple con direcciones IP privadas y NAT en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4266-106">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [<span data-ttu-id="f4266-107">Topología perimetral consolidada de un solo equipo con direcciones IP públicas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4266-107">Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="f4266-108">Servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP privadas mediante NAT en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4266-108">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="f4266-109">Perímetro consolidado escalado, equilibrio de carga DNS con direcciones IP públicas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4266-109">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="f4266-110">Servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4266-110">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>

## <a name="in-this-section"></a><span data-ttu-id="f4266-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f4266-111">In This Section</span></span>

  - [<span data-ttu-id="f4266-112">Configurar DNS para admitir servidores perimetrales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4266-112">Configure DNS for edge support in Lync Server 2013</span></span>](lync-server-2013-configure-dns-for-edge-support.md)

  - [<span data-ttu-id="f4266-113">Configurar equilibradores de carga de hardware para topologías perimetrales escaladas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4266-113">Set up hardware load balancers for scaled edge topologies in Lync Server 2013</span></span>](lync-server-2013-set-up-hardware-load-balancers-for-scaled-edge-topologies.md)

  - [<span data-ttu-id="f4266-114">Configurar los firewall y puertos para el acceso de usuarios externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4266-114">Configure firewalls and ports for external user access in Lync Server 2013</span></span>](lync-server-2013-configure-firewalls-and-ports-for-external-user-access.md)

  - [<span data-ttu-id="f4266-115">Determinar los requisitos de los puertos y el firewall de A/V externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4266-115">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [<span data-ttu-id="f4266-116">Solicitar certificados para componentes perimetrales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4266-116">Request certificates for edge components in Lync Server 2013</span></span>](lync-server-2013-request-certificates-for-edge-components.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

