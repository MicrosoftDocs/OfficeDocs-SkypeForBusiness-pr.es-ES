---
title: 'Lync Server 2013: edición del diagrama de configuración de red'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Editing the network configuration diagram
ms:assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558643(v=OCS.15)
ms:contentKeyID: 51541469
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2772cad1d1a16aa0363b1ab50d0bcaadacb91a08
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835319"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="editing-the-network-configuration-diagram-in-lync-server-2013"></a><span data-ttu-id="5ea7f-102">Editar el diagrama de configuración de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ea7f-102">Editing the network configuration diagram in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ea7f-103">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="5ea7f-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="5ea7f-104">La mayoría del trabajo que un diseñador hace en Lync Server 2013, la herramienta de planeación consiste en definir las entradas de las direcciones IP y los nombres de dominio completos (FQDN) de las entradas del diagrama de red.</span><span class="sxs-lookup"><span data-stu-id="5ea7f-104">Most of the work that a designer does in the Lync Server 2013, Planning Tool consists of defining the entries for the IP addresses and fully qualified domain names (FQDNs) for the entries on the network diagram.</span></span> <span data-ttu-id="5ea7f-105">La información que se introduce en esta página se repite en los informes y otra información de la herramienta de planificación.</span><span class="sxs-lookup"><span data-stu-id="5ea7f-105">The information that is entered on this page carries over into the reports and other information contained in the Planning Tool.</span></span>

<span data-ttu-id="5ea7f-106">![Diagrama de red] de la herramienta de planificación (images/Gg558643.eeabee2d-698c-4b79-baa5-caa4cfb7edb3(OCS.15).jpg "Diagrama de red") de la herramienta de planificación</span><span class="sxs-lookup"><span data-stu-id="5ea7f-106">![Planning Tool Network diagram](images/Gg558643.eeabee2d-698c-4b79-baa5-caa4cfb7edb3(OCS.15).jpg "Planning Tool Network diagram")</span></span>

<span data-ttu-id="5ea7f-107">La herramienta de planeación crea un diagrama de red con texto predeterminado para las direcciones IP y FQDN.</span><span class="sxs-lookup"><span data-stu-id="5ea7f-107">The Planning Tool creates a network diagram with default text for IP addresses and FQDNs.</span></span>

<span data-ttu-id="5ea7f-108">Para editar el diagrama de red y los valores de entrada:</span><span class="sxs-lookup"><span data-stu-id="5ea7f-108">To edit the network diagram and input values:</span></span>

1.  <span data-ttu-id="5ea7f-p102">Elija una sección de la red en la cual comenzar a trabajar. Por ejemplo, haga doble clic en el texto, **access1.contoso.com**. En el cuadro de diálogo que se abre, escriba el FQDN real del servidor access1.contoso.com y la dirección IP real en lugar de 131.107.155.3.</span><span class="sxs-lookup"><span data-stu-id="5ea7f-p102">Choose a section of the network to begin working on. For example, double-click the text, **access1.contoso.com**. In the dialog box that opens, type the actual FQDN of the server access1.contoso.com and the actual IP address, replacing the 131.107.155.3.</span></span>

2.  <span data-ttu-id="5ea7f-112">Haga clic en **Aceptar** para guardar las entradas.</span><span class="sxs-lookup"><span data-stu-id="5ea7f-112">Click **OK** to save the entries.</span></span>

3.  <span data-ttu-id="5ea7f-113">Continúe con la edición de direcciones IP y FQDN y proporcione direcciones IP virtuales para equilibradores de carga de hardware o entradas de servidores para el equilibrio de carga del Sistema de nombres de dominio (DNS) para servidores incluidos en grupos.</span><span class="sxs-lookup"><span data-stu-id="5ea7f-113">Continue to edit IP addresses and FQDNs, providing virtual IP addresses for hardware load balancers or server entries for Domain Name System (DNS) load balancing for servers in pools.</span></span>

<span data-ttu-id="5ea7f-p103">Una característica útil de la herramienta de planeación es que puede asignar de forma gradual un rango de direcciones IP y nombres de host de servidor, en lugar de requerir que el diseñador edite por separado cada servidor de un grupo. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5ea7f-p103">A helpful feature of the Planning Tool is that it can incrementally assign a range of IP addresses and server host names, rather than requiring the designer to edit each separate server in a pool. For example:</span></span>

1.  <span data-ttu-id="5ea7f-p104">Haga doble clic en los servidores front-end agrupados. Cuando se abra el cuadro de diálogo, seleccione **¿Desea usar las direcciones IP y el FQDN como puntos de inicio para todos los servidores equivalentes de este clúster?**.</span><span class="sxs-lookup"><span data-stu-id="5ea7f-p104">Double-click the pooled Front End Servers. When the dialog box opens, select **Do you want to use the IPs and FQDN as starting points for all equivalent servers in this cluster?**.</span></span>

2.  <span data-ttu-id="5ea7f-118">Por ejemplo, el valor de inicio para el primer servidor es fe0101.contoso.com y la dirección IP es 192.168.21.122.</span><span class="sxs-lookup"><span data-stu-id="5ea7f-118">For example, the starting value for the first server is fe0101.contoso.com and an IP address of 192.168.21.122.</span></span>

3.  <span data-ttu-id="5ea7f-119">Escriba **fe0.contoso.com** en **FQDN de servidor front-end**, escriba **192.168.21.131** en **Dirección IP de servidor front-end** y, después haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5ea7f-119">Type **fe0.contoso.com** in **Front End Server FQDN**, type **192.168.21.131** in **Front End Server IP address**, and then click **OK**.</span></span>

4.  <span data-ttu-id="5ea7f-120">La característica de incremento automático actualiza todos los servidores del grupo a fe01 hasta fe06 y todas las direcciones IP desde 192.168.21.131 hasta 136.</span><span class="sxs-lookup"><span data-stu-id="5ea7f-120">The auto-increment feature updates all servers in the pool to fe01 through fe06, and all IP address from 192.168.21.131 to 136.</span></span>

<span data-ttu-id="5ea7f-121">Una vez completadas todas las modificaciones, guarde la topología. Para ello, siga los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="5ea7f-121">After you have completed all edits, save the topology by completing the following steps:</span></span>

<span data-ttu-id="5ea7f-122">Para guardar el diseño de la herramienta de planeación, haga clic en **archivo**y, a continuación, haga clic en **Guardar topología** o **Guardar topología como**.</span><span class="sxs-lookup"><span data-stu-id="5ea7f-122">To save the Planning Tool design, click **File**, and then click **Save Topology** or **Save Topology As**.</span></span> <span data-ttu-id="5ea7f-123">Si aparece el cuadro de diálogo **Guardar herramienta de planeación como**, escriba el nombre del archivo en **Nombre de archivo** y haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="5ea7f-123">If a **Save Planning Tool As** dialog box appears, type a name for the file in **File name**, and then click **Save**.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="5ea7f-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ea7f-124">See Also</span></span>


[<span data-ttu-id="5ea7f-125">Edición del diseño en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ea7f-125">Editing the design in Lync Server 2013</span></span>](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

