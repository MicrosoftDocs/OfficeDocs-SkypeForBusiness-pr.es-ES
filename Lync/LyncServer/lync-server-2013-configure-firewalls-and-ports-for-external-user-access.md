---
title: 'Lync Server 2013: configurar firewalls y puertos para el acceso de usuarios externos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure firewalls and ports for external user access
ms:assetid: cacb3832-f8db-4009-bfcf-6f5c15c236ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398848(v=OCS.15)
ms:contentKeyID: 48185430
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8f8ac768256a45e908905e3eed1c0fc343b6da9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213136"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-firewalls-and-ports-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="4d199-102">Configurar firewalls y puertos para el acceso de usuarios externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d199-102">Configure firewalls and ports for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d199-103">_**Última modificación del tema:** 2012-05-21_</span><span class="sxs-lookup"><span data-stu-id="4d199-103">_**Topic Last Modified:** 2012-05-21_</span></span>

<span data-ttu-id="4d199-104">Para configurar firewalls y puertos, debe configurarlos para servidores perimetrales, servidores proxy inversos y probablemente equilibradores de carga de hardware (para una implementación escalada que no usa equilibrio de carga de DNS).</span><span class="sxs-lookup"><span data-stu-id="4d199-104">To configure firewalls and ports, you need to configure them for Edge Servers, reverse proxy servers, and possibly hardware load balancers (for a scaled deployment that does not use DNS load balancing).</span></span> <span data-ttu-id="4d199-105">En esta sección se proporciona información sobre los requisitos de firewall y de puerto para todos los componentes de servidores perimetrales y la configuración de los puertos de firewall para servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="4d199-105">This section provides information about firewall and port requirements for all Edge Server components and the configuration of firewall ports for Edge Servers.</span></span> <span data-ttu-id="4d199-106">Para obtener más información sobre cómo configurar puertos para servidores de proxy inverso, consulte [configuración de servidores proxy inversos para Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md).</span><span class="sxs-lookup"><span data-stu-id="4d199-106">For details about configuring ports for reverse proxy servers, see [Setting up reverse proxy servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md).</span></span> <span data-ttu-id="4d199-107">Si está implementando una topología perimetral escalada y está usando el equilibrio de carga de hardware en lugar del equilibrio de carga de DNS, consulte [escalado consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md) en la documentación de planeación para obtener información detallada sobre cómo configurar los puertos para equilibradores de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="4d199-107">If you are deploying a scaled edge topology and are using hardware load balancing instead of DNS load balancing, see [Scaled consolidated edge with hardware load balancers in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md) in the Planning documentation for details about configuring ports for hardware load balancers.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="4d199-108">Consulta también</span><span class="sxs-lookup"><span data-stu-id="4d199-108">See Also</span></span>


[<span data-ttu-id="4d199-109">Determinación de los requisitos de los puertos y el Firewall de A/V externos para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d199-109">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

