---
title: 'Lync Server 2013: configurar registros de host DNS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS Host records
ms:assetid: 78a1afcf-41c8-4da5-8740-c6570c19078c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398593(v=OCS.15)
ms:contentKeyID: 48184577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c688d09e1aababd384c28c5a79989fc5d93e69b8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204540"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-dns-host-records-for-lync-server-2013"></a><span data-ttu-id="985b1-102">Configurar registros de host DNS para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="985b1-102">Configure DNS Host records for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="985b1-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="985b1-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="985b1-104">Para completar correctamente este procedimiento, debe iniciar sesión en el servidor o dominio como mínimo como miembro del grupo administradores del dominio o como miembro del grupo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="985b1-104">To successfully complete this procedure, you should be logged on to the server or domain at minimum as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<div>

## <a name="to-configure-dns-host-a-records"></a><span data-ttu-id="985b1-105">Para configurar los registros de host DNS A</span><span class="sxs-lookup"><span data-stu-id="985b1-105">To configure DNS Host A records</span></span>

1.  <span data-ttu-id="985b1-106">En el servidor del Sistema de nombres de dominio (DNS), haga clic en **Inicio**, \*\*Herramientas administrativas \*\* y, a continuación, en **DNS**.</span><span class="sxs-lookup"><span data-stu-id="985b1-106">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="985b1-107">En el árbol de la consola del dominio, expanda **zonas de búsqueda directa**y, a continuación, haga clic con el botón secundario en el dominio en el que se instalará Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="985b1-107">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="985b1-108">Haga clic en **Host nuevo (A o AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="985b1-108">Click **New Host (A or AAAA)**.</span></span>

4.  <span data-ttu-id="985b1-109">Haga clic en **nombre**, escriba el nombre de host del grupo de servidores (el nombre de dominio se asume de la zona en la que se define el registro y no es necesario introducirlo como parte del registro A).</span><span class="sxs-lookup"><span data-stu-id="985b1-109">Click **Name**, type the host name for the pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>

5.  <span data-ttu-id="985b1-110">Haga clic en **dirección IP**, escriba la IP virtual (VIP) del equilibrador de carga para el grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="985b1-110">Click **IP Address**, type the virtual IP (VIP) of the load balancer for the Front End pool.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="985b1-111">En las implementaciones que usan un grupo de directores, los registros de host (A) para las direcciones URL simples deben apuntar a la VIP del equilibrador de carga de director.</span><span class="sxs-lookup"><span data-stu-id="985b1-111">In deployments that use a Director pool, the host (A) records for the simple URLs should point to the VIP of the Director load balancer.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="985b1-112">Si implementa un solo servidor Enterprise Edition o un director que está conectado a la topología sin un equilibrador de carga, o si implementa un servidor Standard Edition, escriba la dirección IP del servidor Enterprise Edition, el servidor Standard Edition o el director.</span><span class="sxs-lookup"><span data-stu-id="985b1-112">If you deploy only one Enterprise Edition server or Director that is connected to the topology without a load balancer, or if you deploy a Standard Edition server, type the IP address of the Enterprise Edition server, Standard Edition server, or Director.</span></span> <span data-ttu-id="985b1-113">Se requiere un equilibrador de carga si se implementa más de un servidor Enterprise Edition o Director en un grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="985b1-113">A load balancer is required if you deploy more than one Enterprise Edition server or Director in a pool.</span></span> <span data-ttu-id="985b1-114">Los equilibradores de carga no se usan con los servidores Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="985b1-114">Load balancers are not used with Standard Edition servers.</span></span>

    
    </div>

6.  <span data-ttu-id="985b1-115">Haga clic en **Agregar host** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="985b1-115">Click **Add Host**, and then click **OK**.</span></span>

7.  <span data-ttu-id="985b1-116">Para crear un registro A adicional, repita los pasos 4 y 5.</span><span class="sxs-lookup"><span data-stu-id="985b1-116">To create an additional A record, repeat steps 4 and 5.</span></span>

8.  <span data-ttu-id="985b1-117">Cuando termine de crear todos los registros A que necesita, haga clic en **listo**.</span><span class="sxs-lookup"><span data-stu-id="985b1-117">When you are finished creating all the A records that you need, click **Done**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

